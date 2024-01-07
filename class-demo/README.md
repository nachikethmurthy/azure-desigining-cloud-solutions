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