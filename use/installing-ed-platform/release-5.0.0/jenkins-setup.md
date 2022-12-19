# Jenkins Setup

Jenkins is used to build, deploy and setup the infrastructure for Sunbird. Almost everything in Sunbird is automated using Jenkins pipelines which integrates with ansible and other tools.

*   SSH to the Jenkins server and enter the following commands -

    ```bash
       git clone https://github.com/project-sunbird/sunbird-devops.git
       cd sunbird-devops && git checkout tags/release-5.0.0 -b release-5.0.0
       cd deploy/jenkins
       sudo bash jenkins-server-setup.sh
    ```
* Open Jenkins UI in a browser by visiting **JENKINS\_IP:8080**
* Enter the initial password and follow the on-screen instructions. Choose **Install suggested plugin** and create an admin user
* Go to **http://JENKINS\_IP:8080/pluginManager/available** -> Search for ‘Configuration as Code Plugin’ and install the plugin without restart.

> Don’t run the following until above steps finished

*   Run the below commands on Jenkins server -

    ```bash
      sudo bash jenkins-plugins-setup.sh
      cp envOrder.txt.sample envOrder.txt
      vi envOrder.txt
    ```
*   Update the environment list as per your requirement in ascending order. For example, if you want to have dev, staging and production environments, your **envOrder.txt** will look like -

    ```bash
      dev=0
      staging=1
      production=2
    ```
*   Run the below script on Jenkins server and provide input as required (case sensitive) -

    ```bash
      sudo bash jenkins-jobs-setup.sh
    ```
*   Restart jenkins

    ```bash
      sudo service jenkins restart
    ```
*   Configure Jenkins

    ```
    sudo su jenkins
    curl -SsL -o ~/jenkins.yaml https://raw.githubusercontent.com/project-sunbird/sunbird-devops/release-5.0.0/deploy/jenkins/jenkins.yaml
      
    # Replace all placeholders ${VALUE} with proper values
    # For example, 
    # username: "${GH_USERNAME}" to  username: "mygithubusername"
    vim ~/jenkins.yaml
    ```
*   Run the below commands on Jenkins server -

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
