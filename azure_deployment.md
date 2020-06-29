## Login to Azure Portal

>az login

## Create Resource Group 

>az group create -n "TritechAcr" -l westeurope
az acr create -g "TritechAcr" -n "tritechcontainerregistry" --sku basic --admin-enabled true

To Check Name Availability
https://docs.microsoft.com/en-us/rest/api/containerregistry/registries/checknameavailability

az acr login -n "tritechcontainerregistry" --expose-token 

Copy the Access token

eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IjZRRjI6RkRNTTpSUjQ2OkE3WFg6N0Q3UjpFNE1COkZJMzQ6RENVUzpQR1dLOldPSjc6SktaSjpSTkkyIn0.eyJqdGkiOiJjODIwYWQxNS0zOGE1LTQ2NDAtOGZiZC0yNmU5MDRmMTg2ZTQiLCJzdWIiOiJsaXZlLmNvbSN2ZW51LnNoYXN0cmlAb3V0bG9vay5jb20iLCJuYmYiOjE1OTI4ODgzMDQsImV4cCI6MTU5MjkwMDAwNCwiaWF0IjoxNTkyODg4MzA0LCJpc3MiOiJBenVyZSBDb250YWluZXIgUmVnaXN0cnkiLCJhdWQiOiJ0cml0ZWNoY29udGFpbmVycmVnaXN0cnkuYXp1cmVjci5pbyIsInZlcnNpb24iOiIxLjAiLCJncmFudF90eXBlIjoicmVmcmVzaF90b2tlbiIsInRlbmFudCI6IjNhZjYzNjc1LTcwYTItNDMyZi05MTFkLTY5YzlmYjZkODA2NiIsInBlcm1pc3Npb25zIjp7ImFjdGlvbnMiOlsicmVhZCIsIndyaXRlIiwiZGVsZXRlIl0sIm5vdEFjdGlvbnMiOm51bGx9LCJyb2xlcyI6W119.CNVsn8BQO91CWhNUL0ldD40mGj1JvN2rdqRPA3Pm0wkhrTvsDdOzq-Xk3xBcIJ8IP9M1pt2-kMiI5ZC_6beRcNC3jr1erj8ZqRyVjScuxsQNxq5WXY7IjIhEPZ3birKLc3hKhS0ZwH4XiMzwCfDtZhlpruDrmwEMxAsufYDoN71DwcmDYvW_MZmncq5raTNA49y5-tcJip4MM2tsgR3BuUwodKh8kOu5_u-bzcoWrdg1kjlHVgpStRe3JKxJ-2Lsa4CEps63svhvxq2nri8WkUJknzCjo381wwdfC9ipZg1Pj5vVS0bi5Kgzikl_cLjUTE8Poq9p20BtfVDAOl9QxQ

regitryServerAddress : tritechcontainerregistry.azurecr.io

Login to Server registry
docker login tritechcontainerregistry.azurecr.io -u 00000000-0000-0000-0000-000000000000 -p "accesstoken"

Tag the image 

docker tag rest-example:latest  tritechcontainerregistry.azurecr.io/rest-example:latest 

push the image to azure container registry
docker push tritechcontainerregistry.azurecr.io/rest-example:latest

List Images from the Azure Container Registry
az acr repository list -n tritechcontainerregistry.azurecr.io -o table

Get Tags assoictaed with images 
az acr repository show-tags -n tritechcontainerregistry.azurecr.io --repository rest-example -o table

To delete image
az acr repository delete -n tritechcontainerregistry -t rest-example:latest 


To know the cost of running instance of container
https://azure.microsoft.com/en-us/pricing/details/container-instances
https://azure.microsoft.com/en-us/pricing/calculator/?service=container-instances

To Create an Instance of Docker Image from repository

az container create -g TritechAcr -n restexamplecontainerone --image tritechcontainerregistry.azurecr.io/rest-example:latest --ports 8080 --ip-address public --dns-name-label restexamplecontainer

To View the logs

az  container logs -n restexamplecontainerone  -g TritechAcr


















<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQwMTk2Njg3NF19
-->