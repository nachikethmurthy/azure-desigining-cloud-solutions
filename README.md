# Hands On Code

## Create Ubuntu VM from Portal
```
chmod 400 ~/Downloads/myKey.pem
ssh -i ~/Downloads/myKey.pem azureuser@10.111.12.123
sudo apt-get -y update
sudo apt-get -y install nginx
```

## Create Ubuntu VM from CLI
```
export RESOURCE_GROUP_NAME=myResourceGroup
export LOCATION=eastus
export VM_NAME=myVM
export VM_IMAGE=debian
export ADMIN_USERNAME=azureuser

az group create --name $RESOURCE_GROUP_NAME --location $LOCATION


az vm create --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME --image $VM_IMAGE --admin-username $ADMIN_USERNAME --generate-ssh-keys --public-ip-sku Standard

export IP_ADDRESS=$(az vm show --show-details --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME --query publicIps --output tsv)

az vm run-command invoke --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME --command-id RunShellScript --scripts "sudo apt-get update && sudo apt-get install -y nginx"

az vm open-port --port 80 --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME

curl $IP_ADDRESS

az group delete --name $RESOURCE_GROUP_NAME --no-wait --yes --verbose
```
