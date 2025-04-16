# Adding Support for a New Cloud Provider

## Requirements

#### Cluster Specifications

* **Minimum Requirements:**
  * CPU: 48 vCPUs
  * Memory: 192 GB
* **Recommended Node Size:**
  * 3 nodes of each of 16 vCPUs 64 GB RAM

#### Networking

* Public Subnet

#### Storage Buckets

Create the following buckets:

1. `private_container_name`
2. `public_container_name`
3. `dial_state_container_public`

#### Additional Requirements

1. Storage Account
2. Random String
3. Encryption String
4. JWT Tokens
5. RSA Keys

***

### Steps to Add a New Cloud Provider

#### Step 1: Create a New Folder

* Navigate to the `terraform` directory and create a folder for the new cloud provider.\
  Example: `terraform/gcp/`

#### Step 2: Recommended Folder Structure

Organize the folder as follows:

```plaintext
terraform/<cloud_provider>/
├── _common
│   ├── kubernetescluster.hcl
│   ├── keys.hcl
│   ├── network.hcl
│   ├── output-file.hcl
│   ├── serviceaccount.hcl
│   ├── storage.hcl
│   └── upload-files.hcl
├── modules
│   ├── kubernetescluster
│   ├── keys
│   ├── network
│   ├── output-file
│   ├── serviceaccount
│   ├── storage
│   └── upload-files
└── template/
    ├── kubernetescluster
    │   └── terragrunt.hcl
    ├── create_tf_backend.sh
    ├── global-values.yaml
    ├── install.sh
    ├── keys
    │   └── terragrunt.hcl
    ├── network
    │   └── terragrunt.hcl
    ├── output-file
    │   └── terragrunt.hcl
    ├── postman.env.json
    ├── storage
    │   └── terragrunt.hcl
    ├── terragrunt.hcl
    └── upload-files
        └── terragrunt.hcl
```

#### Step 3: Copy Template Files

Copy the template files from the Azure configuration:

```sh
cp sunbird-ed-installer/terraform/azure/template/{global-values.yaml,install.sh} sunbird-ed-installer/terraform/gcp/template/
In global-values.yaml, add this variable:
cloud_provider: "REPLACE_ME" # for configuring GCP and AWS installations
```

#### Step 4: Structuring Output Files

This will become the input for Helm bundles:

```plaintext
  global-cloud-values.yaml
  global-values.yaml 
```

#### Step 5: Helm Changes

In Helm charts, wherever cloud values are being referred to, use the following format:

```yaml
{{- if eq .Values.global.cloud_storage_provider "aws" }}
# AWS Specific Values
{{- else if eq .Values.global.cloud_storage_provider "gcp" }}
# GCP Specific Values
{{- end }}
```

**Example:**

In **Helm charts**, using a direct reference for **Azure**:

```yaml
container_name: "{{ .Values.global.public_container_name }}"
```

Using an `if-else` condition for multiple cloud providers:

```yaml
container_name: 
  {{- if eq .Values.global.cloud_storage_provider "aws" }}
  "{{ .Values.global.public_container_name }}"
  {{- else if eq .Values.global.cloud_storage_provider "gcp" }}
  "{{ .Values.global.public_container_namee }}"
  {{- else }}
  "{{ .Values.telemetry_container_private }}"
  {{- end }}
```

#### Step 6: Enable Service Account and Add Annotations

When using storage buckets, ensure the appropriate service account is enabled and annotated\
For example:

```yaml
serviceAccount:
  create: true
  name: <created at step 2>
  annotations:
    iam.gke.io/gcp-service-account: iam.gke.io/gcp-service-account: <service-account-name>@<project-id>.iam.gserviceaccount.com
```

For **Azure installation**, please refer to the documentation:`/sunbird-ed-installer/README.md`
