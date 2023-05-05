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

1. Provision Pre-requisites: Current easy installer supports azure cloud service provider. Please provision the following resources required&#x20;
   * Azure Kuberentes Cluster: Please follow the steps mentioned in the below documentation tp provision AKS cluster and generate the kubeconfig file for the same and save it in the server/local machine from where you will be running the installer script. kubernetes version: 1.24.x , Node size: 4 Core, 16 GB RAM, Node count range: 1 to 8   [https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli)
   * Install az cli [https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt)
   *   Azure Storage account with following containers

       * `sunbird-content-dev` public container
       * `flink-state-backend` private container


   * Google re-captcha : Follow the steps mentioned in the below link. Select Challenge(v2) -> Invisible reCAPTCHA badge. [https://www.google.com/recaptcha/admin/create](https://www.google.com/recaptcha/admin/create)
   * Google OAuth Credentials: Follow the steps mentioned in the below link and set `Authorised redirect URIs` value to https://{domain-name}/oauth2/callback .  Save Client id and Client secret values. [https://developers.google.com/workspace/guides/create-credentials#oauth-client-id](https://developers.google.com/workspace/guides/create-credentials#oauth-client-id)
   * Domain name and SSL Certificates: You can create free Letsencrypt SSL certificates using [https://punchsalad.com/ssl-certificate-generator/](https://punchsalad.com/ssl-certificate-generator/)  for the domain which is valid for 90 days. Or purchase the SSL certs from Godaddy or Namecheap like vendors&#x20;
2. Update environment values
   *   Clone the repository

       ```
       git clone https://github.com/project-sunbird/sunbird-devops -b oneclickinstaller
       cd sunbird-devops/oneclickinstaller
       chmod +x *sh
       ```

       * Use your favourite text editor and update variables mentioned in global-values.yaml. Follow the instructions mentioned in the `global-values.yaml` file under every variable
3. Run the Ed easy installer bash script. While the installer is running, you can view the deployments to the kubernetes cluster using any kubernetes client like kubectl or k9s. This will take 45 min to 1 hour based on the internet speed on the machine where you are running the script. Take a break and check back !

K9s download link: [https://k9scli.io/topics/install/](https://k9scli.io/topics/install/)&#x20;

```
bash ./install-ed.sh /path/to/kubeconfig.yaml -i ed-install  
```

4. Manual keycloak configurations

`NOTE: These manual configurations will be automated in the next consequent releases`

*   Port forward to keycloak pod to access admin console through web browser. Make sure there is no process running on port 8080 on the system from where you are running the installer. Also, make sure context to kubectl is set to the right kubernetes cluster.



    ```
    POD_NAME=$(kubectl get pods -n dev | grep keycloak | awk '{print $1}')
    ```

    ```
    kubectl port-forward -n dev "$POD_NAME" 8080:8080 
    ```


*   Goto `http://localhost:8080/auth/admin/master/console/#/realms/sunbird/clients`&#x20;

    username: admin password: admin

    * Click `lms` client -> Select `service account roles` -> Click on `Client roles` drop down -> Select `realm management` -> Select `manage-users in` Available Roles -> Click on `Add Selected`
    * Click on  `Credentials TAB`-> Copy the secret value -> Update `sunbird_sso_client_secret` variable value in `global-values.yaml` with the copied secret value
    * Click on `Realm Settings`-> `Keys` -> Click on `public key` button-> Copy the key. Update the variables `sunbird_sso_publickey` and `keycloak_sunbird_realm_public_key` in `global-values.yaml` with the copied public key
    * Click on `Realm Settings` -> Click on Themes -> Select `sunbird` as a login theme -> click save


* Goto `http://localhost:8080/auth/admin/master/console/#/realms/sunbird/user-federation` Click on `cassandra-storage-provider` -> Copy the `Provider ID`. Update the `sunbird_keycloak_user_federation_provider_id` variable in `global-values.yaml` with the copied Provider ID
* Goto `http://localhost:8080/auth/admin/master/console/#/realms/sunbird/keys` -> copy KID of Type RSA . Update the variable `keycloak_sunbird_realm_kid` in global-values.yaml

5. Run the Ed easy installer post install script

```
bash ./install-ed.sh /path/to/kubeconfig.yaml -i postscript  
```

6. Update the DNS record: Get the public ip printed on the console and add DNS A record for the same domain you have added to global-values.yaml. Access the Ed instance using https://{domain-name}

Once this is done, functional configurations to be setup based on the use case you would like to implement Sunbird Ed for.&#x20;

Please refer the below mentioned postman collection to setup minimal functional configuration for content and course creation workflow. We will be automating this process in the coming sprints and update the documentation here. Please check this page for updates.&#x20;

#### Postman Collection

Download the postman collection of Sunbird-Ed configuration

[https://api.postman.com/collections/4214340-ae9d4061-2dff-4605-8579-a55563e46c75?access\_key=PMAT-01GZKEBEAZW1WSGF3WVS95D8RT](https://api.postman.com/collections/4214340-ae9d4061-2dff-4605-8579-a55563e46c75?access\_key=PMAT-01GZKEBEAZW1WSGF3WVS95D8RT)

#### **Postman environment variables:**

Download the postman environment variables & update the values after importing to postman.

Please refer global\_values.yaml file for varaible values.

| Environment key name    | global\_values.yaml key name          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ----------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| host                    | domain                                | http://example.co.oin                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| kong\_api\_key          | Bearer \{{sunbird\_encryption\_key\}} | Bearer xxx.yyy.zzz                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| keycloak\_access\_token |                                       | <p>Generate using Auth-Token API<br><a href="https://www.postman.com/sunbird-building-blocks/workspace/sunbird-ed/documentation/25186239-6547f9fc-5f16-495c-b5e0-d76f5a78d66d?entity=request-81d7a679-2c0d-4413-9d63-868d4fdd0b67">https://www.postman.com/sunbird-building-blocks/workspace/sunbird-ed/documentation/25186239-6547f9fc-5f16-495c-b5e0-d76f5a78d66d?entity=request-81d7a679-2c0d-4413-9d63-868d4fdd0b67</a><br>Copy "access_token" value from response</p> |
| auth\_client\_id        |                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| auth\_client\_secret    | sunbird\_sso\_client\_secret          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| auth\_grantType         |                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

[https://github.com/vinukumar-vs/Sunbird\_ED\_Postman/blob/master/Sunbird-Ed%20template.postman\_environment.json](https://github.com/vinukumar-vs/Sunbird\_ED\_Postman/blob/master/Sunbird-Ed%20template.postman\_environment.json)\
\
How to import environment variables into postman.

[https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data)\
\
Install Newman & run configuration postman collection on server from where easy installer has initiated(./install-ed.sh) using below commands.

<pre><code><strong>$ npm install -g newman
</strong></code></pre>

<pre class="language-bash"><code class="lang-bash"><strong>$ newman run path_to_Sunbird_ED_collection.json -e path_to_environment.json
</strong></code></pre>

{% embed url="https://learning.postman.com/docs/collections/using-newman-cli/installing-running-newman/" %}

If you have any queries or facing issues please create thread at [https://github.com/orgs/Sunbird-Ed/discussions/categories/installation](https://github.com/orgs/Sunbird-Ed/discussions/categories/installation)&#x20;

