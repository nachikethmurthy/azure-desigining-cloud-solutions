# install VS code 
 - Install VS Code extension
 - Install CLI on the local PC:
https://learn.microsoft.com/en-us/cli/azure/

- verify the installation:
`az --version`

# Getting Started with Azure Resource Manager
```
az login
az group create --name arm-vscode --location eastus

az deployment group create --resource-group arm-vscode --template-file 1.azuredeploy.json --parameters 1.azuredeploy.parameters.json```

# Delete the Resources
`az group delete --name arm-vscode`

# Functions

```az deployment group create --name addlocationparameter --resource-group myResourceGroup --template-file 2.template-functions.json --parameters storageName={new-unique-name}```

# Variables

```
az deployment group create --name addnamevariable --resource-group myResourceGroup --template-file 3.variables.json --parameters '{"storagePrefix": {"value":"store"}}' '{"storageSKU": {"value":"Standard_LRS"}}'
```

# Outputs

```az deployment group create --name addoutputs --resource-group myResourceGroup --template-file 4.outputs.json --parameters storagePrefix=store storageSKU=Standard_LRS```