Kubernetes 001

Build the image with tag
---
docker build . -t <your-acr-name>/myweb

Login to Azure container registry
---
az login
az acr login --name <your-acr-name>

Push the image to ACR
---
docker push <your-acr-name>.azurecr.io/<your-image>:<tag>

Deploy 2 deploy
---
k apply -f k8s-web-to-nginx.yaml -f nginx.yaml

Delete all resources
---
k delete -f nginx.yaml -f k8s-web-to-nginx.yaml
