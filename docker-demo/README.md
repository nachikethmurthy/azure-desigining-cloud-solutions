# Instructions
1. Install Azure Tools and Docker Extensions in VS Code
2. Login with Azure account on Azure Tools
3. Add ACR to Docker Registry under the Docker extension
4. Perform Login to ACR after connecting
5. Create Dockerfile
6. Perform build using the short cut - `F1` (also CLI can be used) - (ensure to tag as : nachiketh555.azurecr.io/azuretraining:latest)
7. Perform Push from Docker extension to Container Registry (ensure to specify the your ACR id at the start of docker image - nachiketh555.azurecr.io/azuretraining:latest)
8. Under the Docker Extension, right click on the image and select the option of Deploy Container image