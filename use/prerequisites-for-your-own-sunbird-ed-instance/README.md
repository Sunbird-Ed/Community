# Prerequisites for your own Sunbird ED Instance

#### Recommended Permissions and Experience <a href="#recommended-permissions-and-experience" id="recommended-permissions-and-experience"></a>

To successfully complete Sunbird installation, you need to have:

* System administrator permissions on and all servers
* Hands-on experience in administering and debugging Linux systems
* Hands-on experience using Docker and Kubernetes to run containerized services

> **Note:** Sunbird is tested only on cloud hosted Ubuntu servers in Azure. We do not provide any support for installing Sunbird on other operating systems. Sunbird might work on other cloud providers, feel free to try it out and let us know. We are actively working on achieving cloud neutrality.

#### Infra Requirements <a href="#infra-requirements" id="infra-requirements"></a>

* Kubernetes Cluster with 4 worker nodes
* Private GitHub repository to store ansible inventory
* Fully Qualified Domain Name (FQDN) with SSL
* Object Storage
* Docker hub account
* Public IP
* Google Oauth Credentials
* Google V3 Recaptcha Credentials
* Maxmind city database (free or paid)
* A SMTP account (any email provider works, except Gmail for now)
* All ports must be open for internal communication (Azure Virtual Network or AWS VPC) between the VMs
* Internet and outbound access from VMs
* A sms service provider API Token (optional)
* YouTube API Token (optional)
* Slack account and slack bot with API Token (optional)

#### Provisioning Servers <a href="#provisioning-servers" id="provisioning-servers"></a>

Before you start the installation process, ensure that you have the required infrastructure mentioned below. It is the bare minimum for a full fledged Sunbird setup. Every component in Sunbird can scale horizontally / vertically by adding additional resources.

| APPLICATION          | SERVER             | COUNT        |
| -------------------- | ------------------ | ------------ |
| Jenkins              | 4core 16G 250G HDD | 1            |
| KP                   | 4core 16G 60G HDD  | 1            |
| DP                   | 4core 16G 60G HDD  | 1            |
| DB                   | 4core 16G 60G HDD  | 1            |
| Yarn                 | 4core 16G 60G HDD  | 1            |
| Other Services       | 4core 16G 60G HDD  | 1            |
| Basic Load Balancers | -                  | 2 (Optional) |
