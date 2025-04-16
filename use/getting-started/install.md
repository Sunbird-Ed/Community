# Install

To commence your journey with SunbirdEd, follow these guidelines:&#x20;

* **Choose Cloud Platform:** Your first step is to create an account on a cloud platform that best fits your needs. Whether you opt for Azure, AWS, GCP, or OCI, your choice should be guided by considerations like your budget, available technical resources, and the degree of control you wish to have over your deployment. You can also leverage an existing account if it aligns with your requirements.
* **Provision Cloud Infrastructure**: In order to provision the infra please refer to the [Pre-requisites](pre-requisites.md) and ensure the requirements are met.

## Prepare the Environment

1. Copy the template directory

```
bash cd terraform/<cloud-provider> # Replace <cloud-provider> with your cloud provider 
cp -r template <env> # for reference
```

2. Ensure the required values in `<env>/global-values.yaml` are populated properly by following the prerequisites.

## Provision Infra and Install Services

In order to provision infra and install all services, run the following command

1.  Ensure you are in the respective environment related folder\


    ```
    cd terraform/<cloud-provider>/<env>
    ```
2.  Run the `install.sh` script that provisions the infra and installs the services\


    ```
    time ./install.sh
    ```



\
