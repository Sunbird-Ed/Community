# Pre-requisites

## **Infra Requirements**

* Kubernetes Cluster with 3 worker nodes each of 16 Core 64 GB RAM
* Fully Qualified Domain Name (FQDN)&#x20;
* SSL Certificate - A FullChain, consisting of the private key and Certificate+CA\_Bundle
* Object Storage with CORS enabled
  *   CORS Policy:<br>

      ```json
      [
        {
          "origin": ["<domain-name>"],
          "method": ["GET", "HEAD", "OPTIONS", "PUT", "POST"],
          "responseHeader": ["Content-Type", "Authorization", "x-goog-resumable", "x-amz-acl", "x-ms-blob-type"],
          "maxAgeSeconds": 3600
        }
      ]
      ```
* Google OAuth Credentials

> **Steps to create:** https://developers.google.com/workspace/guides/create-credentials#oauth-client-id

* Google V3 ReCaptcha Credentials

> **Steps to create:** Login to https://www.google.com/recaptcha/admin and create one for the domain

* Maxmind city database (free or paid)
* Email service provider
* MSG91 sms service provider API Token (optional)

> **Note:** This is required to get OTPs to registered email addresses when a user registers or resets

* YouTube API Token (optional)

> **Note:** This is required to upload video content directly using the YouTube URL

* Slack account and slack bot with API Token for monitoring alerts(optional)

## Required CLI Tools

1. [jq](https://jqlang.github.io/jq/download/)
2. [yq](https://github.com/mikefarah/yq#install) (for YAML processing)
3. [rclone](https://rclone.org/)
4. [Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
5. [Terragrunt](https://terragrunt.gruntwork.io/docs/getting-started/install/)
6. Linux / MacOS / GitBash (Windows)
7. Python 3
8. PyJWT Python Package (install via pip)
9. [kubectl](https://kubernetes.io/docs/tasks/tools/)
10. [helm](https://helm.sh/docs/intro/quickstart/#install-helm)
11. [Postman CLI](https://learning.postman.com/docs/getting-started/installation/installation-and-updates/)
12. Git

## Clone the installation scripts repository

```bash
git clone https://github.com/project-sunbird/sunbird-ed-installer.git
```

## Cloud Specific Tools

Based on the cloud provider, install the respective tools

{% tabs %}
{% tab title="Azure" %}
### **Required tools and permissions**

1. [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
2. Ensure that the user or service principal running the Terraform script has the necessary privileges as [listed here](https://registry.terraform.io/providers/hashicorp/azuread/latest/docs/resources/application#api-permissions)

> NOTE: We will overwrite the following files. Please take a backup of your existing files in the following locations
>
> * `~/.config/rclone/rclone.conf`

### Authentication

Post installation of the CLI tool and providing necessary permissions, use the following command to login to Azure via CLI.

```
az login --tenant <AZURE_TENANT_ID>
```

Note: Make sure you replace the AZURE\_TENANT\_ID with the tenant id from Azure Console.

### **Infra Setup**

Post login, update the `terraform/azure/<env>/global-values.yaml` with the variables as per your environment

```
  building_block: "" # building block name
  env: "" 
  environment: "" # use lowercase alphanumeric string between 1-9 characters
  domain: ""
  subscription_id: ""
  sunbird_cloud_storage_provider: azure 
  sunbird_google_captcha_site_key: 
  google_captcha_private_key: 
  sunbird_google_oauth_clientId: 
  sunbird_google_oauth_clientSecret: 
  mail_server_from_email: ""
  mail_server_password: ""
  mail_server_host: smtp.sendgrid.net
  mail_server_port: "587"
  mail_server_username: apikey
  sunbird_msg_91_auth: ""
  sunbird_msg_sender: ""
  youtube_apikey: ""
  proxy_private_key: |
   <private_key_generated_when_setting_up_ssl>
  proxy_certificate: |
   <certificate_generated_when_setting_up_ssl>
```
{% endtab %}

{% tab title="Google Cloud" %}
Create a project on google cloud and export it as a variable. Please see [Creating and Managing Projects](https://cloud.google.com/resource-manager/docs/creating-managing-projects) for reference and enable the Kubernetes Engine API for the project, as it is required to create and manage Kubernetes clusters within Google Cloud  You can enable the API by following the guide [Enable the Kubernetes Engine API](https://console.cloud.google.com/apis/library/container.googleapis.com).

```
export GOOGLE_PROJECT_ID=<your_project_id>
```

**Required tools and permissions**

1. [<mark style="color:blue;">Google Cloud CLI</mark>](https://cloud.google.com/sdk/docs/install)
2. Ensure that the user or service account running the Terraform script has the necessary privileges as [listed here](https://registry.terraform.io/providers/hashicorp/google/latest/docs/guides/provider_reference#authentication).

> NOTE: We will overwrite the following files. Please take a backup of your existing files in the following locations
>
> * `~/.config/rclone/rclone.conf`

### Authentication

Post installation of the CLI tool and providing necessary permissions, use the following commands to login to GCP via CLI.

```
gcloud auth login
```

Then initialize the GCP configuration:

```
gcloud init
```

Authenticate the application with default credentials:

```
gcloud auth application-default login
```

Install the GKE gcloud authentication plugin:

```
gcloud components install gke-gcloud-auth-plugin
```

Note: Make sure you select the correct project and authenticate with the appropriate credentials.

### **Infra Setup**

Post login, update the `terraform/gcp/<env>/global-values.yaml` with the variables as per your environment

```
building_block: "" # building block name
env: ""
environment: "" # use lowercase alphanumeric string between 1-9 characters
cloud_storage_region: ""
cloud_storage_project: ""
zone: ""
gke_node_pool_instance_type: ""
domain: ""
sunbird_google_captcha_site_key: ""
google_captcha_private_key: ""
sunbird_google_oauth_clientId: ""
sunbird_google_oauth_clientSecret: ""
mail_server_from_email: ""
mail_server_password: ""
mail_server_host: smtp.sendgrid.net
mail_server_port: "587"
mail_server_username: apikey
sunbird_msg_91_auth: ""
sunbird_msg_sender: ""
youtube_apikey: ""
proxy_private_key: |
 <private_key_generated_when_setting_up_ssl>
proxy_certificate: |
 <certificate_generated_when_setting_up_ssl>
```
{% endtab %}

{% tab title="Oracle Cloud" %}
### Coming Soon
{% endtab %}

{% tab title="AWS" %}
### Coming Soon
{% endtab %}
{% endtabs %}



