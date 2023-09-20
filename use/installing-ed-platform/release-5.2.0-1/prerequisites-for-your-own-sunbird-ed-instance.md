# Prerequisites for your own Sunbird ED Instance

#### Recommended Permissions and Experience <a href="#recommended-permissions-and-experience" id="recommended-permissions-and-experience"></a>

To successfully complete Sunbird installation, you need to have:

* System administrator permissions on and all servers
* Hands-on experience in administering and debugging Linux systems
* Hands-on experience using Docker and Kubernetes to run containerized services

> **Note:** Sunbird is tested only on cloud hosted Ubuntu servers. We do not provide any support for installing Sunbird on other operating systems.

#### Infra Requirements <a href="#infra-requirements" id="infra-requirements"></a>

* Kubernetes Cluster with 4 worker nodes each of 4 Core 16 GB RAM
* Total 6 VM's are required each of 4 Core 16 GB RAM
* Private GitHub repository to store ansible inventory
* Fully Qualified Domain Name (FQDN) with SSL
* Object Storage
* Docker hub account or Any docker registry
* Public IP
* Google OAuth Credentials

> **Steps to create:** https://developers.google.com/workspace/guides/create-credentials#oauth-client-id

* Google V3 ReCaptcha Credentials

> **Steps to create:** Login to https://www.google.com/recaptcha/admin and create one for domain

* Maxmind city database (free or paid)
* A SMTP account (any email provider works, except Gmail for now)
* All ports must be open for internal communication between the VM's/Servers provisioned for the installation

> **Note:** If resources are isolated by subnets, then subnet-to-subnet communication needs to be enabled by security rules

* Enable internet and outbound access from VMs.&#x20;

> **Note:** This is required to install dependent packages from the ubuntu package manager and other open source repositories

* A sms service provider API Token (optional)

> **Note:** This is required to get OTP's to registered email address when user register or reset

* YouTube API Token (optional)

> **Note:** This is required to upload video content directly using youtube URL

* Slack account and slack bot with API Token (optional)

#### Provisioning Servers <a href="#provisioning-servers" id="provisioning-servers"></a>

Before you start the installation process, ensure that you have the required infrastructure mentioned above is provisioned. Every component in Sunbird can scale horizontally / vertically by adding additional resources. Please find the mapping between server and the application components below.

<table><thead><tr><th>APPLICATION COMPONENT</th><th>SERVER CONFIG</th><th width="192.33333333333331">COUNT</th></tr></thead><tbody><tr><td>Jenkins</td><td>4core 16GB RAM 250G HDD</td><td>1</td></tr><tr><td>KP</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>DP</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>DB</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>Learning</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>Druid</td><td>4core 16GB RAM 60G HDD</td><td>1</td></tr><tr><td>Basic Load Balancers</td><td>Layer 4</td><td>2 (Optional)</td></tr></tbody></table>
