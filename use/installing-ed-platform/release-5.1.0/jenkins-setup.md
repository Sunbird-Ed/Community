# Jenkins Setup

Jenkins is used to build, deploy and setup the infrastructure for Sunbird. Almost everything in Sunbird is automated using Jenkins pipelines which integrates with ansible and other tools.

*   SSH to the Jenkins server and enter the following commands -

    ```bash
       git clone https://github.com/project-sunbird/sunbird-devops.git
       cd sunbird-devops && git checkout tags/release-5.1.0 -b release-5.1.0
       cd deploy/jenkins
       sudo bash jenkins-server-setup.sh
    ```
* Open Jenkins UI in a browser by visiting **JENKINS\_IP:8080**
* Enter the initial password and follow the on-screen instructions. Choose **Install suggested plugin** and create an admin user
* Go to **http://JENKINS\_IP:8080/pluginManager/available** -> Search for ‘Configuration as Code Plugin’ and install the plugin without restart.

> Don’t run the following until above steps finished

*   Run the below commands on Jenkins server to install external plugins

    ```bash
      sudo bash jenkins-plugins-setup.sh
      
    ```
*   Setup environment specific Jenkins jobs. Update the environment list as per your requirement in ascending order. For example, if you want to have dev, staging and production environments, follow the below instructions

    ```bash
      cp envOrder.txt.sample envOrder.txt
      vi envOrder.txt
      dev=0
      staging=1
      production=2
      sudo bash jenkins-jobs-setup.sh
    ```
*   Restart Jenkins

    ```bash
      sudo service jenkins restart
    ```
*   Configure Jenkins

    ```
    sudo su jenkins
    curl -SsL -o ~/jenkins.yaml https://raw.githubusercontent.com/project-sunbird/sunbird-devops/release-5.1.0/deploy/jenkins/jenkins.yaml
      
    # Replace all placeholders ${VALUE} with below mentioned values
    ${DOCKER_REGISTRY_URL} to the container registry URL which you would like to store the container images
    ${GH_USERNAME} to the github username which has access to the private repository
    ${GH_PASSWORD} to the github access token which has access to the private repository
    ${GH_PRIVATE_REPO_URL} to the private github repository URL where the environment variables and servers information is updated
    ${GH_PRIVATE_REPO_BRANCH} to the name of the private repo branch where the environment variables and servers information is updated
    ${GH_PUBLIC_REPO_BRANCH} to "release-5.1.0"
    ${KP_PUBLIC_REPO_BRANCH} to "release-5.2.0"
    ${DP_PUBLIC_REPO_BRANCH} to "release-5.1.0"

    vim ~/jenkins.yaml
    ```
*   Run the below commands on Jenkins server to establish connectivity between Jenkins to kubernetes cluster and servers -

    ```bash
      mkdir -p /var/lib/jenkins/secrets
      cd /var/lib/jenkins/secrets
      touch deployer_ssh_key vault-pass k8s.yaml
      chmod 600 deployer_ssh_key vault-pass k8s.yaml
    ```

    * Copy the contents of your server’s private key into `/var/lib/jenkins/secrets/deployer_ssh_key`
    * Copy the kubernetes config file contents into `/var/lib/jenkins/secrets/k8s.yaml`
    * If you have encrypted your `secrets.yml` using `ansible-vault`, enter the password to decrypt into `/var/lib/jenkins/secrets/vault-pass`. If you have not encrypted, then enter a random value like **12345**
* Run `sudo visudo` on jenkins server and add the below line -

```bash
      jenkins ALL=(ALL) NOPASSWD:ALL
```

* Reboot the Jenkins VM (`sudo reboot`)

