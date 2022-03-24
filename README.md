# aci-availability-zones

## Prerequisites

The following tools are required before using this example:

- Azure CLI, version 2.30.0 or later

Login to `az` and select your subscription (if necessary):

```sh
az login
az account set --subscription "YOUR_SUBSCRIPTION_ID"
```

## Deploy with Bicep

First, copy the `main.parameters.sample.json` file to `main.parameters.json`.
Then, update the values of `containerGroupBaseName` and `trafficManagerName` to
something unique.

Next, create the resource group that you will be deploying into:

```sh
# Change location and resource-group to your preferred values
az group create --location eastus --resource-group rg-your-resource-group-name
```

Finally, deploy the bicep template with `az`:

```sh
az deployment group create -n DeployingAciToMultipleAvailabilityZones --resource-group rg-your-resource-group-name --template-file main.bicep --parameters main.parameters.json
```

Wait for the deployment to finish, then check the Azure Portal for the status of
the resources.

## More Information

For more information, see the following Microsoft Docs:

- [Deploy an Azure Container Instances (ACI) container group in an availability zone (preview)](https://docs.microsoft.com/azure/container-instances/availability-zones)
