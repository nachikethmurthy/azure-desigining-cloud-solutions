# Azure Demo - 1
```
az login
az account set --subscription SubscriptionName
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file azuredeploy.json
az group delete --name myDemoGroup
```

# Azure Demo - 2
```
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file parameterdemo.json --parameters storageName="murthy12126trjhbsddn"
az group delete --name myDemoGroup
```

# Azure Demo - 3
```
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file parameterfile.json --parameters parameterfile.parameters.json
az group delete --name myDemoGroup
```

# Create Custom Function:
- https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/user-defined-functions

# Azure Demo - 4
```
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file variables.json --parameters variables.parameters.json
az group delete --name myDemoGroup
```

# Azure Demo 5

```
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file locationexample.json
```

# Azure Demo 5

```
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file output.json --parameters variables.parameters.json
```

# Assignment
- Create a Linux VM using the ARM template (modify the settings)
- Create Storage with type as - Blob using ARM template


# 13 Jan Code


```
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file 13-jan-vm.json --parameters 13-jan-vm.parameters.json
```