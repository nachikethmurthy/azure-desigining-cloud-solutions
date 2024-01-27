# Deploy to Azure App using Zip

```
RESOURCE_GROUP_NAME = 'python-flasknachiketh_group'
APP_SERVICE_NAME = 'python-flasknachiketh'


az webapp config appsettings set \
--resource-group $RESOURCE_GROUP_NAME \
--name $APP_SERVICE_NAME \
--settings SCM_DO_BUILD_DURING_DEPLOYMENT=true

az webapp deploy \
--name $APP_SERVICE_NAME 
--resource-group $RESOURCE_GROUP_NAME
--src-path msdocs-python-flask-webapp-quickstart-main.zip
```

## Git

az webapp up --runtime PYTHON:3.10 --sku B1 --logs

az webapp config appsettings set \
--resource-group $RESOURCE_GROUP_NAME \
--name $APP_SERVICE_NAME \
--output tsv

az webapp deplopyment list-publishing-credentials \
--name $APP_SERVICE_NAME \
--resource-group $RESOURCE_GROUP_NAME \
--query "{Username:publishingUsername, Password:publishingPassword}" \
--output table

git remote add azure <git-url>