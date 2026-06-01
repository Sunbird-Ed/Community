# Database Migration: Sunbird ED 8.1.0 → Sunbird Spark

## Database Migration: Sunbird ED 8.1.0 → Sunbird Spark

End-to-end runbook for migrating data from a Sunbird ED 8.1.0 cluster into a new Sunbird Spark cluster.

**Supported clouds:** Azure / GCP / AWS (Blob / GCS / S3)

> **Note:** Same-domain migration only (DNS swap at cutover). Different-domain migrations are not validated by this guide.

***

### Prerequisites — One-time setup

Before starting, complete the **one-time setup** in [`private-repo-setup/README.md`](https://github.com/Sunbird-Spark/sunbird-spark-installer/blob/main/private-repo-setup/README.md). Required for **both** paths:

**GitHub Action path (primary)**

* Create private repo
* Copy workflows
* Encrypt config
* Configure Azure OIDC + GitHub secrets/environment

**VM path (alternative — see Appendix)**

* Install CLI tools: `jq`, `yq`, `opentofu`, `terragrunt`, `kubectl`, `helm`, `postman`, `az/gcloud`
* Clone repos on VM
* Place config at `opentofu/<cloud>/<env>/`

Finish that setup, then return here for the migration phases.

***

### Architecture

```
SOURCE CLUSTER                  OBJECT STORAGE                TARGET CLUSTER
(Sunbird ED 8.1.0)             (Blob / GCS / S3)            (Sunbird Spark)

+-----------------+             +----------------+            +------------------+
| PostgreSQL    --|--> dump --> |                |--> load -->| YugabyteDB YSQL  |
| Cassandra     --|--> CSV  --> |   Artifacts    |--> load -->| YugabyteDB YCQL  |
| Neo4j         --|--> CSV  --> |                |--> load -->| JanusGraph       |
| Elasticsearch --|--> snap --> |                |--> load -->| Elasticsearch    |
+-----------------+             +----------------+            +------------------+

     PHASE 1 (export.sh)           HANDOFF                   PHASE 4 (migrate.sh)
```

***

### Orchestration scripts

Three shell scripts drive the helm-based migration steps. **Use these — do not run `helm upgrade --install` directly.**

| Script                      | Runs on     | What it drives                                                    |
| --------------------------- | ----------- | ----------------------------------------------------------------- |
| `migration/export.sh`       | OLD cluster | Phase 1 — exports 4 source DBs to object storage                  |
| `migration/migrate.sh`      | NEW cluster | Phase 4 — restores data one DB at a time + DB-only fixups         |
| `migration/post-migrate.sh` | NEW cluster | Phase 6 — post-deploy reconciles with service-readiness preflight |

Each script wraps `helm upgrade --install` calls and manages the `enabled/disabled` flag toggling between steps automatically. Scripts use `set -euo pipefail` — any failure halts immediately.

**Run all steps:**

```bash
./migration/export.sh          # Phase 1 (OLD cluster)
./migration/migrate.sh         # Phase 4 (NEW cluster)
./migration/post-migrate.sh    # Phase 6 (NEW cluster)
```

**Run individual steps (recommended for first-time runs):**

```bash
./migration/export.sh 1.1      # run only step 1.1
./migration/migrate.sh 4.3     # run only step 4.3
./migration/post-migrate.sh 6.2
```

**Configurable env vars (all have defaults):**

| Var            | Default        | Purpose                |
| -------------- | -------------- | ---------------------- |
| `NAMESPACE`    | `migration`    | Helm release namespace |
| `RELEASE`      | `db-migration` | Helm release name      |
| `HELM_TIMEOUT` | `60m`          | Per-upgrade timeout    |

***

### Migration Phases — Overview

> **Warning:** Run phases **in order**. Do not skip ahead.

| Phase | What it does                                    | Where it runs                   |
| ----- | ----------------------------------------------- | ------------------------------- |
| 1     | Export DBs from OLD cluster into object storage | OLD cluster — `export.sh`       |
| 2     | Provision NEW infra (no apps yet)               | Private repo + Cloud            |
| 3     | Install data-tier only on NEW cluster           | NEW cluster — GitHub Action     |
| 4     | Restore data one DB at a time                   | NEW cluster — `migrate.sh`      |
| 5     | Install all remaining services                  | NEW cluster — GitHub Action     |
| 6     | Post-deploy reconciles                          | NEW cluster — `post-migrate.sh` |
| 7     | DNS swap (cutover)                              | DNS provider                    |
| 8     | Validate                                        | NEW cluster — GitHub Action     |

***

### Phase 1 — Export from OLD Cluster

Runs inside the **source ED 8.1.0 cluster**. Produces tarballs in object storage.

#### 1.1 Configure export values

Edit [`migration/database/export/values.yaml`](https://github.com/Sunbird-Spark/sunbird-spark-installer/blob/main/migration/database/export/values.yaml) with source DB endpoints and storage credentials:

| Cloud | Required fields                                           |
| ----- | --------------------------------------------------------- |
| Azure | `storageAccount` + `accessKey`                            |
| GCP   | `bucket` + `serviceAccountKey`                            |
| AWS   | `s3Bucket` + `accessKeyId` + `secretAccessKey` + `region` |

#### 1.2 Run the export

**Run all 4 steps at once:**

```bash
./migration/export.sh
```

**Run step by step:**

```bash
./migration/export.sh 1.1   # PostgreSQL → <bucket>/postgresql/*.sql.gz
./migration/export.sh 1.2   # Cassandra  → <bucket>/cassandra/<keyspace>.tar.gz
./migration/export.sh 1.3   # Neo4j      → <bucket>/neo4j/neo4j_export.tar.gz
./migration/export.sh 1.4   # Elasticsearch snapshot → <bucket>/cluster-1/snapshots/...
```

#### 1.3 Verify artifacts in cloud storage

| Path                                   | Content                |
| -------------------------------------- | ---------------------- |
| `<bucket>/postgresql/*.sql.gz`         | PostgreSQL dumps       |
| `<bucket>/cassandra/<keyspace>.tar.gz` | Cassandra keyspaces    |
| `<bucket>/neo4j/neo4j_export.tar.gz`   | Neo4j export           |
| `<bucket>/cluster-1/snapshots/...`     | Elasticsearch snapshot |

***

### Phase 2 — Provision NEW Spark Cluster (Infra Only)

Uses the **private-repo GitHub Action** (`sunbird-spark-platform.yaml`).

> **Note:** This phase reuses OLD storage — it does **not** create a new storage account. The `skip_storage_module: true` flag prevents OpenTofu from provisioning new storage.

#### 2.1 Copy config templates into private repo

```
opentofu/<cloud>/template/global-values.yaml       →  configs/<env>/global-values.yaml
opentofu/<cloud>/template/global-cloud-values.yaml →  configs/<env>/global-cloud-values.yaml
```

#### 2.2 Edit `global-values.yaml`

* Set `resource_group_name` as needed
* Set `skip_storage_module: true` ← **critical**

#### 2.3 Fetch OLD cluster's encryption key

```bash
kubectl --context <OLD-CLUSTER-CONTEXT> \
  get configmap learn-service -n sunbird -o yaml \
  | grep sunbird_encryption_key
```

> **Note:** This key is needed so the NEW cluster can decrypt PII (email/phone) migrated into YugabyteDB.

#### 2.4 Edit `global-cloud-values.yaml`

Prefill with OLD storage references and the encryption key:

```yaml
global:
  cloud_storage_access_key:          <OLD storage account name>
  public_container_name:             <OLD public container>
  private_container_name:            <OLD private container>
  velero_storage_container_private:  <OLD velero container>
  sunbird_encryption_key:            "<OLD encryption key>"
```

**Why these settings matter:**

* **OLD storage refs** — The NEW cluster reads existing user uploads, content, and certs directly from OLD storage. No data copy needed.
* **OLD encryption key** — The `learn-service` configmap uses `{{ default .Values.global.random_string .Values.global.sunbird_encryption_key }}`. Without the OLD key, PII columns will not decrypt and logins will fail.
* **Do not touch `random_string`** — Keycloak client secrets, kong consumers, player session secret, and flink all depend on it. It is managed by OpenTofu's keys module.

#### 2.5 Encrypt and commit both config files

```bash
ansible-vault encrypt \
  configs/<env>/global-values.yaml \
  configs/<env>/global-cloud-values.yaml

git push
```

#### 2.6 Trigger GitHub Action — infra only

| Input                 | Value |
| --------------------- | ----- |
| `create_tf_backend`   | ✅     |
| `backup_configs`      | ✅     |
| `create_tf_resources` | ✅     |

Wait for AKS/GKE and supporting infra to complete before proceeding.

***

### Phase 3 — Install Data-Tier Only

> **Warning:** Do **not** install `learnbb` or `knowledgebb` yet — they would repopulate schemas before import runs.

Trigger the GitHub Action **3 times** in order with `install_helm: true` and `helm_mode: selective`:

| Run | Bundle        | `specific_charts`  | Installs           |
| --- | ------------- | ------------------ | ------------------ |
| 1   | `edbb`        | `kafka yugabytedb` | Kafka + YugabyteDB |
| 2   | `learnbb`     | `elasticsearch`    | Elasticsearch      |
| 3   | `knowledgebb` | `janusgraph`       | JanusGraph         |

After Run 3, all target databases exist (empty/freshly schema'd) and are ready for import.

***

### Phase 4 — Import Data

**Before running:** edit [`migration/database/import/values.yaml`](https://github.com/Sunbird-Spark/sunbird-spark-installer/blob/main/migration/database/import/values.yaml) with target DB endpoints, storage credentials, and step-specific settings (see each sub-step below).

> **Warning:** Run steps **in order**. Each step is safe to rerun individually if it fails.

**Run all 6 steps at once:**

```bash
./migration/migrate.sh
```

**Run step by step (recommended first time — verify each before moving on):**

```bash
./migration/migrate.sh 4.1
./migration/migrate.sh 4.2
./migration/migrate.sh 4.3
./migration/migrate.sh 4.4
./migration/migrate.sh 4.5
./migration/migrate.sh 4.6
```

#### 4.1 PostgreSQL → YugabyteDB YSQL

No extra config beyond target DB connection settings already in `values.yaml`.

**Verify after:**

```bash
kubectl exec -it -n sunbird yb-tserver-0 -- ysqlsh -c '\l'
# Expected: keycloak and registry databases visible
```

***

#### 4.2 Rotate Keycloak Credentials

The PostgreSQL restore brought in OLD keycloak admin password and client secrets. Rotate them now so the NEW keycloak service (Phase 5) finds matching credentials.

Set in `migration/database/import/values.yaml` before running:

```yaml
dbFixups:
  keycloakCredentials:
    adminPassword: "<keycloak_password from NEW cluster's global-values.yaml>"
    secretSuffix:  "<random_string from NEW cluster's global-cloud-values.yaml>"
```

| Field           | Source                                                                                    |
| --------------- | ----------------------------------------------------------------------------------------- |
| `adminPassword` | `keycloak_password` in NEW `global-values.yaml`                                           |
| `secretSuffix`  | `random_string` in NEW `global-cloud-values.yaml` (auto-generated by OpenTofu in Phase 2) |

> **Tip:** Writes directly to YSQL (`keycloak` DB). No keycloak service needed. Safe to rerun.

***

#### 4.3 Cassandra → YugabyteDB YCQL

Set in `migration/database/import/values.yaml` before running:

```yaml
databases:
  ycql:
    sourcePrefix: "sb_"
    targetPrefix: "<global.env from NEW cluster's global-values.yaml>_"
```

> **Warning:** `targetPrefix` must match the NEW cluster's `global.env` with a trailing underscore. Example: `env: "dv"` → `targetPrefix: "dv_"`

Logs show `==> keyspace X -> Y` per keyspace and `<== Y done: tables=N rows=M`.

***

#### 4.4 Neo4j → JanusGraph

No extra config beyond JanusGraph connection settings in `values.yaml`.

Runs `import_data.groovy` → `set_graphid.groovy` → `verify_migration.groovy` inside the JanusGraph pod.

***

#### 4.5 Elasticsearch → Elasticsearch

No extra config beyond storage and ES connection settings in `values.yaml`.

Restores snapshot via `repository-azure` (or GCS / S3) plugin.

***

#### 4.6 Backfill `createdat` Column

Backfills the `createdat` column on the YugabyteDB user table (not populated in ED 8.1.0). No service dependency. No extra config needed.

***

### Phase 5 — Install All Remaining Services

Trigger the GitHub Action with:

| Input          | Value |
| -------------- | ----- |
| `install_helm` | ✅     |
| `helm_mode`    | `all` |

Runs all 7 bundles: `monitoring`, `edbb`, `learnbb`, `knowledgebb`, `obsrvbb`, `inquirybb`, `additional`. Charts already installed in Phase 3 upgrade in place — no data loss.

***

### Phase 6 — Post-Deploy Reconciles

> **Warning:** Run **after Phase 5** — requires running keycloak, knowlg-service, and lern-service.

`post-migrate.sh` checks readiness before running: it queries those three Deployments in the `sunbird` namespace and exits immediately if any has 0 Ready replicas. Wait for Phase 5 Action to finish and pods to become Ready, then run.

**Before running:** set step-specific values in `migration/database/import/values.yaml`.

**Run all 3 steps at once:**

```bash
./migration/post-migrate.sh
```

**Run step by step:**

```bash
./migration/post-migrate.sh 6.1
./migration/post-migrate.sh 6.2
./migration/post-migrate.sh 6.3
```

#### 6.1 Keycloak Realm Reconcile

Reconciles the migrated keycloak realm with the NEW chart's `realm.json` (locales, refresh-token policy, client redirectUris, auth flows).

> **Note:** Migrated user accounts and passwords are **never touched**.

Set in `migration/database/import/values.yaml`:

```yaml
postMigration:
  keycloakRealmReconcile:
    adminPassword: "<keycloak_password from NEW cluster's global-values.yaml>"
```

***

#### 6.2 Hierarchy Fix

Regenerates content hierarchy relations via `knowlg-service`. No extra config beyond connection settings in `values.yaml`.

***

#### 6.3 User Progress Sync

Syncs user course progress across frontend and backend. Required when migrating from older Sunbird versions where progress data may be out of sync.

Set in `migration/database/import/values.yaml`:

```yaml
postMigration:
  userProgressSync:
    adminUsername: "<admin-user>"
    adminPassword: "<admin-password>"
    dryRun: false
```

> **Note:** `adminUsername` and `adminPassword` must match the admin credentials created during initialization (e.g., `admin@yopmail.com` / `Admin@123`). Job automatically disables `filter_processed_enrolments` in lern-env ConfigMap before sync and re-enables it after completion.

***

### Phase 7 — DNS Swap (Cutover)

#### 7.1 Get the NEW cluster's nginx IP

```bash
kubectl get svc -n sunbird ingress-nginx-controller \
  -o jsonpath='{.status.loadBalancer.ingress[0].ip}'
```

#### 7.2 Update DNS

In the DNS provider (Route53 / Cloud DNS / etc.), update the A record for the OLD domain to point to the new nginx IP. Wait 5–30 minutes for propagation.

```bash
dig +short <your-domain>   # should resolve to new IP
```

***

### Recovery — Missed `sunbird_encryption_key` in Phase 2

> **Caution:** If `sunbird_encryption_key` was not set in `global-cloud-values.yaml` during Phase 2, `learn-service` falls back to `random_string` as the encryption key — causing login failures and garbled PII columns.

**Step 1 — Fetch OLD key:**

```bash
kubectl --context <OLD-CLUSTER-CONTEXT> \
  get configmap learn-service -n sunbird -o yaml \
  | grep sunbird_encryption_key
```

**Step 2 — Add to NEW cluster's `global-cloud-values.yaml`:**

```yaml
global:
  sunbird_encryption_key: "<value from OLD cluster>"
  # Do NOT touch random_string
```

**Step 3 — Re-encrypt, commit, and redeploy `learn-service`:**

```
helm_mode: selective   bundle: learnbb   specific_charts: learn-service
```

***

### Phase 8 — Validate

Trigger the GitHub Action with:

| Input                  | Purpose                                       |
| ---------------------- | --------------------------------------------- |
| `generate_postman_env` | Builds `env.json` with NEW cluster endpoints  |
| `migrate_forms`        | Seeds System Settings + creates/updates Forms |

**Form migration behaviour (`migrate_forms.py`):**

| API response | Action                                                    |
| ------------ | --------------------------------------------------------- |
| `404`        | Create form                                               |
| `200`        | Update form                                               |
| Skipped      | 6 Spark Portal Creation forms (left untouched if present) |

> **Note:** `run_post_install` is not needed for migrations — it is for fresh installs only.

**Manual sanity checks:**

* Login with a migrated user → password works (encryption key correct, keycloak reconciled)
* Old user-uploaded content is visible (storage refs correct)
* API endpoints return data
* Mobile app authenticates (android client redirectUris reconciled in Phase 6.1)

***

### End-to-end command reference

```bash
# ── OLD cluster (kubectl context = OLD) ──────────────────────────────────────
# Phase 1 — export 4 source DBs to object storage
./migration/export.sh

# ── switch kubectl context to NEW cluster ────────────────────────────────────

# Phase 2 — trigger GitHub Action: create_tf_backend + backup_configs + create_tf_resources
# Phase 3 — trigger GitHub Action 3 times:
#   Run 1: bundle=edbb,        specific_charts="kafka yugabytedb"
#   Run 2: bundle=learnbb,     specific_charts="elasticsearch"
#   Run 3: bundle=knowledgebb, specific_charts="janusgraph"

# Phase 4 — DB imports + DB-only fixups
./migration/migrate.sh

# Phase 5 — trigger GitHub Action: install_helm=true, helm_mode=all
#   Wait until Deployments in ns/sunbird are Ready.

# Phase 6 — post-deploy reconciles (preflight checks services first)
./migration/post-migrate.sh

# Phase 8 — trigger GitHub Action: generate_postman_env + migrate_forms

# Phase 7 — DNS swap (manual)
```

***

### Idempotency

All import steps are safe to rerun:

| Step                      | How idempotency is achieved                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------- |
| 4.1 PostgreSQL restore    | `DROP/CREATE` database before restore                                                    |
| 4.2 Keycloak credentials  | `UPDATE` — no insert conflicts                                                           |
| 4.3 Cassandra → YCQL      | `TRUNCATE` before load (controlled by `truncateBeforeLoad` in values.yaml)               |
| 4.4 Neo4j → JanusGraph    | `verify_migration.groovy` validates; re-import overwrites                                |
| 4.5 Elasticsearch restore | Deletes non-system indices before restoring snapshot                                     |
| 4.6 createdat backfill    | `ALTER TABLE … ADD IF NOT EXISTS`; ES `_update_by_query` is a no-op if already populated |
| 6.1 Realm reconcile       | `PUT` (idempotent) for realm and client settings                                         |
| 6.2 Hierarchy fix         | `POST` to knowlg-service is idempotent per identifier                                    |
| 6.3 User progress sync    | `POST` to lern activity API is idempotent per enrolment                                  |

***

### Troubleshooting

| Symptom                              | Likely cause                                           | Fix                                                        |
| ------------------------------------ | ------------------------------------------------------ | ---------------------------------------------------------- |
| Login fails / PII columns garbled    | `sunbird_encryption_key` not set                       | See Recovery section above                                 |
| Old uploads return 404               | Wrong storage container names                          | Re-verify Phase 2.4                                        |
| Keycloak admin login fails           | `keycloakCredentials` not run or wrong `adminPassword` | Rerun step 4.2                                             |
| Client secret invalid                | Wrong `secretSuffix` in step 4.2                       | Re-read `random_string` from config, rerun step 4.2        |
| Refresh token rejected               | Realm reconcile did not apply                          | Rerun step 6.1                                             |
| YCQL keyspace not found              | `targetPrefix` mismatch vs `global.env`                | Fix prefix in values.yaml, rerun step 4.3                  |
| Mobile app cannot login              | android client redirectUris not updated                | Check step 6.1 job logs                                    |
| `helm timeout` on import job         | Job is working but slow                                | Set `HELM_TIMEOUT=120m` env var before running the script  |
| `post-migrate.sh` exits at preflight | keycloak/knowlg-service/lern-service not Ready         | Wait for Phase 5 Action to finish + pods Ready, then rerun |

***

### File Reference

| Path                                                                | Purpose                                                                       |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `migration/export.sh`                                               | Phase 1 — orchestrates 4 export steps on OLD cluster                          |
| `migration/migrate.sh`                                              | Phase 4 — orchestrates 6 import/fixup steps on NEW cluster                    |
| `migration/post-migrate.sh`                                         | Phase 6 — orchestrates 3 post-deploy reconciles with readiness preflight      |
| `migration/database/export/values.yaml`                             | Phase 1 config — source DB endpoints + storage credentials                    |
| `migration/database/import/values.yaml`                             | Phase 4 + 6 config — target DB endpoints, fixup values, post-migration values |
| `migration/database/import/files/keycloak_apply_realm_reconcile.py` | Step 6.1 realm reconciler                                                     |
| `migration/database/import/files/user-progress-sync.py`             | Step 6.3 user progress sync                                                   |
| `migration/migrate_forms.py`                                        | Phase 8 — seed System Settings and Forms                                      |

***

### Appendix — Running Without GitHub Action (VM path)

GitHub Action is the primary path. For the VM path, complete the one-time VM setup in [`private-repo-setup/README.md`](https://github.com/Sunbird-Spark/sunbird-spark-installer/blob/main/private-repo-setup/README.md) first (CLI tools, repo clone, config placement).

| Phase        | GitHub Action inputs                                         | VM equivalent                                                       |
| ------------ | ------------------------------------------------------------ | ------------------------------------------------------------------- |
| 2            | `create_tf_backend`, `backup_configs`, `create_tf_resources` | `./install.sh create_tf_backend backup_configs create_tf_resources` |
| 3 — Run 1    | `edbb`, `specific_charts: kafka yugabytedb`                  | `./install.sh install_service edbb kafka yugabytedb`                |
| 3 — Run 2    | `learnbb`, `specific_charts: elasticsearch`                  | `./install.sh install_service learnbb elasticsearch`                |
| 3 — Run 3    | `knowledgebb`, `specific_charts: janusgraph`                 | `./install.sh install_service knowledgebb janusgraph`               |
| 5            | `helm_mode: all`                                             | `./install.sh install_helm_components`                              |
| 7 (recovery) | `learnbb`, `specific_charts: learn-service`                  | `./install.sh install_service learnbb learn-service`                |
| 8            | `generate_postman_env`, `migrate_forms`                      | `./install.sh generate_postman_env migrate_forms`                   |

> **Note:** Phases 1, 4, and 6 use `export.sh` / `migrate.sh` / `post-migrate.sh` directly and run identically in both paths.
