# Infra Provisioning

> **Note:** We have automated infra provision scripts available for azure, if you using any other cloud service provider other than azure provision infrastructure manually.

**Provisioning infrastructure on other cloud service providers (except Azure)**

* Object storage with CORS enabled
* Virtual network with 2 subnets, one for VM's and other for kubernetes cluster
* Managed Kubernetes cluster with 4 worker nodes each node with 4 Core, 16GB RAM configuration
* Create VM's as mentioned in prerequisites
* Enable communication between above created two subnets, so that kubernetes cluster and VM'S created can communicate with each other

**Provisioning infrastructure on Azure**

You can run the following steps to create azure infrastructure using ansible.

Easiest way to use the script will be to use azure cloud shell, as the cloud shell comes with all prerequisites bundled.

* login to portal.azure.com
* click on the cloudshell -> select bash ( if you’re using it for the first time )

If you want to run this on your local machine, Follow this [guide](https://docs.microsoft.com/en-us/azure/developer/ansible/install-on-linux-vm?tabs=azure-cli#install-ansible-on-the-virtual-machine).

```
  git clone https://github.com/project-sunbird/sunbird-devops -b release-5.1.0
cd sunbird-devops/deploy
# Update the necessary variables in playbook
ansible-playbook -c local azure-provision.yaml
# Resulting infrastructure infromation will be stored in sunbird-devops/deploy/azure-resources.txt file.
```

**Creating the AKS cluster**

> **Note** Follow the steps given below to create the Kubernetes cluster in Azure. For other clouds, please visit the respective cloud provider website The AKS cluster and VM’s should be in same vnet. If they are in different vnet, you have to peer the vnets. To successfully peer, the IP address of the vnets should not overlap.

* Create a service principal and assign contributor role to service principal
* Get the secrets and client id of service principal
* Click [here](https://docs.microsoft.com/en-us/cli/azure/create-an-azure-service-principal-azure-cli) for more details
* Create the AKS cluster either via Azure portal or using `az aks` command line
* Refer to Azure documentation for all the available options
* Below is a sample command which you can use -

```bash
  az aks create --resource-group <resouse-group-name> --node-resource-group <k8s-resource-group-name> --name <cluster name>  --node-count 4 --admin-username deployer --kubernetes-version 1.19.9 --service-principal "<service principal id>" --node-vm-size Standard_D4s_v3 --client-secret "<client id>" --network-plugin azure --ssh-key-value @deployer.pub -l <region> --vm-set-type VirtualMachineScaleSets --vnet-subnet-id /subscriptions/<subscription id>/resourceGroups/<resouse-group-name>/providers/Microsoft.Network/virtualNetworks/<vnet-name>/subnets/<subnet name>
```

> Note: Ensure you have allocated at least 1024 IP’s for your Kubernetes subnet (CIDR notation as x.x.x.x/22)

Get the kubeconfig file for your cluster with the below command -

```bash
  az aks get-credentials --resource-group <resource group name> --name <cluster name> --file  k8s.yaml
```

#### Configuring the Azure storage account <a href="#configuring-the-azure-storage-account" id="configuring-the-azure-storage-account"></a>

* Update the CORS rule for the storage account as follows:

```bash
    Allowed Origins: *
    Allowed Methods: GET,HEAD,OPTIONS, PUT
    Allowed Headers: Access-Control-Allow-Origin,Access-Control-Allow-Method,Origin,x-ms-meta-qq,x-ms-blob-type,x-ms-blob-content-type,Content-Type
    Exposed Headers: Access-Control-Allow-Origin,Access-Control-Allow-Methods
    Max Age: 200

```

* Disable **Secure transfer required** in storage account configuration

***
