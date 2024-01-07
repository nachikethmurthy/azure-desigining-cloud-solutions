# Azure Demo - 1
```
az login
az account set --subscription SubscriptionName
az group create --name myDemoGroup --location 'Central US'
az deployment group create --name azuredeploy --resource-group myDemoGroup --template-file azuredeploy.json
az group delete --name myDemoGroup
```