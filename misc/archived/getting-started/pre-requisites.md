# Pre-requisites

#### **Recommended Permissions and Experience**

To successfully complete Sunbird ED installation, you need to have:

* System administrator permissions on all servers
* Hands-on experience in administering and debugging Linux systems
* Hands-on experience using Docker and Kubernetes to run containerised services

> **Note:** Sunbird ED is tested only on cloud hosted Ubuntu servers.&#x20;

#### **Infra Requirements**

* Kubernetes Cluster\[1.27.x] with 5 worker nodes each of 4 Core 16 GB RAM
* Total 6 VM's are required each of 4 Core 16 GB RAM
* Private GitHub repository to store ansible inventory
* Fully Qualified Domain Name (FQDN) with SSL
* Object Storage with CORS enabled
* Docker hub account or Any docker registry
* Public IP
* Google OAuth Credentials

> **Steps to create:** https://developers.google.com/workspace/guides/create-credentials#oauth-client-id

* Google V3 ReCaptcha Credentials

> **Steps to create:** Login to https://www.google.com/recaptcha/admin and create one for the domain

* Maxmind city database (free or paid)
* Email service provider
* All ports must be open for internal communication between the VM's/Servers provisioned for the installation

> **Note:** If subnets isolate resources, then subnet-to-subnet communication needs to be enabled by security rules

* Enable internet and outbound access from VMs.

> **Note:** This is required to install dependent packages from the Ubuntu package manager and other open-source repositories

* MSG91 sms service provider API Token (optional)

> **Note:** This is required to get OTPs to registered email addresses when a user registers or resets

* YouTube API Token (optional)

> **Note:** This is required to upload video content directly using the YouTube URL

* Slack account and slack bot with API Token for monitoring alerts(optional)

#### **Provisioning Servers**

Before you start the installation process, ensure the required infrastructure mentioned above is provisioned. Every component in SunbirdEd can scale horizontally/vertically by adding additional resources. Please find the mapping between the server and the application components below.

<table><thead><tr><th>APPLICATION COMPONENT</th><th>SERVER CONFIG</th><th width="192.33333333333331">COUNT</th></tr></thead><tbody><tr><td>Jenkins</td><td>4core 16GB RAM 250G HDD</td><td>1</td></tr><tr><td>KP</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>DP</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>DB</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>Learning</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>Druid</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>Load Balancers</td><td>Layer 4</td><td>2 (Optional)</td></tr></tbody></table>

