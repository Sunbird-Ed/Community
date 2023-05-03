# Easy installer (Draft)

## Overview:&#x20;

Easy installer is meant to install Sunbird Ed platform on Kubernetes cluster which helps the adopter to setup Sunbird Ed platform within in few hours.&#x20;

## Pre-requisites:

Server or Laptop with Ubuntu 20.04 LTS operating system

Azure Kubernets Cluster

Azure Storage Account

Domain name

SSL Certificates

## Steps:

1.  Provision infrastructure and Pre-requisites: Current easy installer supports azure cloud service provider. Please provision the following resources required&#x20;

    * Azure Kuberentes Cluster: Please follow the steps mentioned in the below documentation&#x20;

    [https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli)

    * Storage account with following containers
      * sunbird-contents-dev
    *   Google re-captcha : Follow the steps mentioned in the below link and fetch the values and update var1 var2??

        [https://www.google.com/recaptcha/admin/create](https://www.google.com/recaptcha/admin/create)
    *   Google OAuth Credentials: Follow the steps mentioned in the below link and update the variables in global-vars.yaml

        [https://developers.google.com/workspace/guides/create-credentials#oauth-client-id](https://developers.google.com/workspace/guides/create-credentials#oauth-client-id)
    * Domain name and SSL Certificates
      * You can create free Letsencrypt SSL certificates using [https://punchsalad.com/ssl-certificate-generator/](https://punchsalad.com/ssl-certificate-generator/)  for the domain which is valid for 90 days. Or purchase the SSL certs from Godaddy or Namecheap like vendors&#x20;
2. Update environment values
   *   Clone the repository

       ```
       git clone https://github.com/project-sunbird/sunbird-devops -b oneclickinstaller
       cd oneclickinstaller
       ```
   * Use your favourite text editor and update variables mentioned in global-values.yaml
3. Run the Ed easy installer bash script

```
bash ./install-ed.sh k8s-config.yaml
```

5. Manual configurations
   1. Do port forward to keycloak pod
   2. Login to keycloak using http://localhost:8081/auth
   3. Update the values to globar-vars.yaml
6. Run the Ed easy installer post install script

## Known Issues:



