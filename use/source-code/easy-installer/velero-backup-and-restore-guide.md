# Velero Backup and Restore Guide

## Overview

This guide explains how **Velero** is used for **backup and restore** processes in the **Sunbird infrastructure**. Velero is installed as part of the [ED Installer ](https://github.com/project-sunbird/sunbird-ed-installer/tree/main/helmcharts/additional)and is used to take entire cluster backups and database-level backups. We use Velero to:

* Schedule and manage database and cluster-wide backups
* Enable volume snapshots for persistent storage
* Restore specific workloads and namespaces as needed

For more detailed features and configurations, refer to the official [Velero ](https://velero.io/docs/)documentation.

### Backup Scheduling

Backups are scheduled using Helm values under the `schedules` section. You can enable or disable specific schedules, change backup times, and set retention policies.

#### Example Velero Schedule Config

```yaml
schedules:
  edcluster-backup:
    disabled: false
    schedule: "0 0 * * *"
    useOwnerReferencesInBackup: false
    template:
      ttl: "240h"
      includedNamespaces:
        - "sunbird"
      snapshotVolumes: true  

  database-backup:
    disabled: true # disabled by default; enable and configure the schedule as per the needs
    schedule: "0 0 * * *"
    useOwnerReferencesInBackup: false
    template:
      ttl: "240h"
      includedNamespaces:
        - "sunbird"
      labelSelector:
        matchExpressions:
          - key: app.kubernetes.io/name
            operator: In
            values:
              - cassandra
              - neo4j
              - redis
              - postgresql
      snapshotVolumes: true
```

### Restoring from Backup

#### Retrieving Backup Names

To find the backup names in your cluster where Velero is installed, execute the following command:

```sh
velero get backups
```

This will list all the backups available, allowing you to choose the specific `<backup-name>` for restoration.

#### Namespace Level Restore

To restore a specific namespace from a backup, use the following command:

```sh
velero restore create --from-backup <backup-name> --namespace-mappings <source-namespace>:<target-namespace>
```

Replace `<backup-name>`, `<source-namespace>`, and `<target-namespace>` with your specific backup and namespace details.

#### Service Level Restore

For service level restoration, you might need to specify particular resources. Here’s an example command:

```sh
velero restore create --from-backup <backup-name> --include-resources <resource-type>
```

**Example**: The following command demonstrates how to restore the entire Cassandra service, including all associated resources and volumes:

```sh
velero restore create cassandra-restore-test \
  --from-backup <backup-name> \
  --namespace-mappings sunbird:sunbird \
  --selector app.kubernetes.io/name=cassandra \
  --restore-volumes
```

This ensures that all components of the Cassandra service are restored from the specified backup.

#### Entire Cluster Restore

To restore the entire cluster from a backup, execute the following command:

```sh
velero restore create --from-backup <backup-name>
```

Replace `<backup-name>` with the name of your specific backup to initiate a full cluster restoration.



References:

1. Velero - [https://velero.io/docs/main/](https://velero.io/docs/main/)
