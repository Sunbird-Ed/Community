# Provision Cloud Infrastructure

#### **Creating the AKS cluster from the Azure console**

> To create AKS cluster follow the steps given below to create the Kubernetes cluster in Azure. The AKS cluster and VM’s should be in same vnet. If they are in different vnet, you have to peer the vnets. To successfully peer, the IP address of the vnets should not overlap.

* Create a service principal and assign a contributor role to the service principal. Ref: [https://learn.microsoft.com/en-us/cli/azure/azure-cli-sp-tutorial-1?tabs=bash](https://learn.microsoft.com/en-us/cli/azure/azure-cli-sp-tutorial-1?tabs=bash)
* Get the secrets and client ID of service principal
* Create the AKS cluster either via the Azure portal or using `az aks` command line
* Refer to Azure documentation for all the available options
* Below is a sample command that you can use&#x20;

```bash
  az aks create --resource-group <resouse-group-name> --node-resource-group <k8s-resource-group-name> --name <cluster name>  --node-count 5 --admin-username deployer --kubernetes-version 1.24 --service-principal "<service principal id>" --node-vm-size Standard_D4s_v3 --client-secret "<client id>" --network-plugin azure --ssh-key-value @deployer.pub -l <region> --vm-set-type VirtualMachineScaleSets --vnet-subnet-id /subscriptions/<subscription id>/resourceGroups/<resouse-group-name>/providers/Microsoft.Network/virtualNetworks/<vnet-name>/subnets/<subnet name>
```

> Note: Ensure you have allocated at least 1024 IPs for your Kubernetes subnet (CIDR notation as x.x.x.x/22)

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

#### **Provisioning infrastructure on other cloud service providers except Azure**

* Object storage with CORS enabled
* Virtual network to host VM's and Kubernetes cluster
* Kubernetes cluster with 5 worker nodes each node with 4 Core, 16GB RAM configuration
* Create Compute Instances/VM's as mentioned in pre-requisites section
* Make sure kubernetes cluster and VM's can communicate with each other
