# Easy installer (Draft)

## Overview:&#x20;

Easy installer is meant to install Sunbird Ed platform on Kubernetes cluster which helps the adopter to setup Sunbird Ed platform within in few hours.&#x20;

## Pre-requisites:

* Server or Laptop with Ubuntu 20.04 LTS operating system
* Azure Kubernets Cluster
* Azure Storage Account
* Domain name and SSL Certificates
* Google re-captcha
* Google OAuth Credentials

To successfully complete Sunbird installation, you need to have:

* System administrator permissions to the cloud resources
* Hands-on experience in administering and debugging Linux systems
* Hands-on experience using Docker and Kubernetes to run containerized workloads

## Steps:

1.  Provision Pre-requisites: Current easy installer supports azure cloud service provider. Please provision the following resources required&#x20;

    * Azure Kuberentes Cluster: Please follow the steps mentioned in the below documentation tp provision AKS cluster and generate the kubeconfig file for the same and save it in the server/local machine from where you will be running the installer script.&#x20;

    &#x20;     kubernetes version: 1.24.x , Node size: 4 Core, 16 GB RAM, Node count range: 1 to 8&#x20;

&#x20;     [https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli)

* Azure Storage account with following containers
  * `sunbird-contents-dev` public container
  * `flink-storage` private container
*   Google re-captcha : Follow the steps mentioned in the below link. Select Challenge(v2) -> Invisible reCAPTCHA badge

    [https://www.google.com/recaptcha/admin/create](https://www.google.com/recaptcha/admin/create)
*   Google OAuth Credentials: Follow the steps mentioned in the below link and update the variables in global-vars.yaml

    [https://developers.google.com/workspace/guides/create-credentials#oauth-client-id](https://developers.google.com/workspace/guides/create-credentials#oauth-client-id)
*   Domain name and SSL Certificates

    You can create free Letsencrypt SSL certificates using [https://punchsalad.com/ssl-certificate-generator/](https://punchsalad.com/ssl-certificate-generator/)  for the domain which is valid for 90 days. Or purchase the SSL certs from Godaddy or Namecheap like vendors&#x20;

1. Update environment values
   *   Clone the repository

       ```
       git clone https://github.com/project-sunbird/sunbird-devops -b oneclickinstaller
       cd sunbird-devops/oneclickinstaller
       chmod +x *sh
       ```
   * Use your favourite text editor and update variables mentioned in global-values.yaml. Follow the instructions mentioned in the `global-values.yaml` file under every variable
2. Run the Ed easy installer bash script. While the installer is running, you can view the deployments to the kubernetes cluster using any kubernetes client like kubectl or k9s

K9s download link: [https://k9scli.io/topics/install/](https://k9scli.io/topics/install/)&#x20;

```
bash ./install-ed.sh /path/to/kubeconfig.yaml -i ed-install
```

4. Manual keycloak configurations

`NOTE: These manual configurations will be automated in the next consequent releases`

*   Port forward to keycloak pod to access admin console through web browser. Make sure there is no process running on port 8080 on the system from where you are running the installer



    ```
    POD_NAME=$(kubectl get pods -n dev | grep keycloak | awk '{print $1}')
    ```

    ```
    kubectl port-forward -n dev "$POD_NAME" 8080:8080 
    ```


*   Goto `http://localhost:8080/auth/admin/master/console/#/realms/sunbird/clients`

    * Click `lms` client -> Select `service account roles` -> Click on `Client roles` drop down -> Select `realm management` -> Select `manage-users in` Available Roles -> Click on `Add Selected`
    * Click on `lms` client -> `Credentials` -> Copy the secret value -> Update `sunbird_sso_client_secret` variable value in `global-vars.yaml` with the copied secret value
    * Click on  `Keys`, copy the public key. Update the variable `sunbird_sso_publickey` in `global-vars.yaml` with the copied public key


* Goto `http://localhost:8080/auth/admin/master/console/#/realms/sunbird/user-federation` Click on `cassandra-storage-provider` -> Copy the provider key. Update the `sunbird_keycloak_user_federation_provider_id` variable in `global-vars.yaml` with the copied provider key

5. Run the Ed easy installer post install script

```
bash ./install-ed.sh /path/to/kubeconfig.yaml -i postscript
```

6. Update the DNS record. Fetch the public ip using kubectl command. Access the Ed instance using https://{domain-name}



