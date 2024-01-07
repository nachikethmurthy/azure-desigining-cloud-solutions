# install VS code 
 - installation - link (https://code.visualstudio.com/download)
 - Install VS Code extension - azure resource manager tools extension (https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools)
 - install git bash on your system(windows) : https://git-scm.com/download/win
 - Install CLI on the local PC:
https://learn.microsoft.com/en-us/cli/azure/

- verify the installation (git bash (windows) /terminal  (mac)):
`az --version`

# Getting Started with Azure Resource Manager
```
az login
az group create --name arm-vscode --location eastus

az deployment group create --resource-group arm-vscode --template-file 1.azuredeploy.json --parameters 1.azuredeploy.parameters.json
```

# Delete the Resources
`az group delete --name arm-vscode`

# Functions

```
az deployment group create --name addlocationparameter --resource-group myResourceGroup --template-file 2.template-functions.json --parameters storageName={new-unique-name}
```

# Variables

```
az deployment group create --name addnamevariable --resource-group myResourceGroup --template-file 3.variables.json --parameters '{"storagePrefix": {"value":"store"}}' '{"storageSKU": {"value":"Standard_LRS"}}'
```

# Outputs

```
az deployment group create --name addoutputs --resource-group myResourceGroup --template-file 4.outputs.json --parameters storagePrefix=store storageSKU=Standard_LRS
```