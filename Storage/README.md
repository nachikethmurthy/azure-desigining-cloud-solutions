# CLI reference

https://learn.microsoft.com/en-us/cli/azure/service-page/storage?view=azure-cli-latest

# Steps to create Storage Account 
```
az login
az group create --name myDemoGroup --location 'Central US'

az storage account create --name nachiketh1dksmgansjl --resource-group myDemoGroup --location 'Central US' --publish-internet-endpoints true

az storage container create --name mycontainer --account-name nachiketh1dksmgansjl

az storage blob upload --account-name nachiketh1dksmgansjl --container-name mycontainer --name README.md --file README.md 

az group delete -n myDemoGroup
```
# Storage Explorer

https://learn.microsoft.com/en-us/azure/storage/blobs/quickstart-storage-explorer