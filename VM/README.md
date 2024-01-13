# Working with VM

```
chmod 400 myKey.pm
ssh -i myKey.pm azureuser@public-ip

sudo apt-get -y update
sudo apt-get -y install nginx

```

# Create VM with CLI

```
export RESOURCE_GROUP_NAME=myResourceGroup
export LOCATION=eastus
export VM_NAME=myVM
export VM_IMAGE=Debian11
export ADMIN_USERNAME=azureuser

az group create --name $RESOURCE_GROUP_NAME --location $LOCATION

az vm create --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME --image $VM_IMAGE --admin-username $ADMIN_USERNAME --generate-ssh-keys --public-ip-sku Standard

export IP_ADDRESS=$(az vm show --show-details --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME --query publicIps --output tsv)


az vm run-command invoke --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME --command-id RunShellScript --scripts "sudo apt-get update && sudo apt-get install -y nginx"

az vm open-port --port 80 --resource-group $RESOURCE_GROUP_NAME --name $VM_NAME

curl $IP_ADDRESS

az group delete --name $RESOURCE_GROUP_NAME --no-wait --yes --verbose
```

# Create VM with Powershell

```
New-AzVm `
    -ResourceGroupName 'myResourceGroup' `
    -Name 'myVM2' `
    -Location 'East US' `
    -image Debian11 `
    -size Standard_B2s `
    -PublicIpAddressName myPubIP `
    -OpenPorts 80 `
    -GenerateSshKey `
    -SshKeyName mySSHKey

Invoke-AzVMRunCommand `
   -ResourceGroupName 'myResourceGroup' `
   -Name 'myVM2' `
   -CommandId 'RunShellScript' `
   -ScriptString 'sudo apt-get update && sudo apt-get install -y nginx'


Get-AzPublicIpAddress -Name myPubIP -ResourceGroupName myResourceGroup | select "IpAddress"

Remove-AzResourceGroup -Name 'myResourceGroup'
```