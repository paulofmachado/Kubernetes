# Kubernetes

## Install

* [Rancher Desktop](https://rancherdesktop.io)
* [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli-windows)

## Docker Build and Push Image

### Docker Hub

1. nerdctl build . --file FILE --tag USER/IMAGE
2. nerdctl tag USER/IMAGE USER/IMAGE:VERSION
3. nerdctl login
4. nerdctl push --all-tags USER/IMAGE

### Generic Registry

1. nerdctl build . --file FILE --tag REGISTRY/PROJECT/IMAGE
2. nerdctl tag REGISTRY/PROJECT/IMAGE REGISTRY/PROJECT/IMAGE:VERSION
3. nerdctl login https://REGISTRY
4. nerdctl push --all-tags REGISTRY/PROJECT/IMAGE

## Local

* **Run:** nerdctl run -p PORT:CONTAINER_PORT -d --name CONTAINER IMAGE

* **Compose:** nerdctl-compose up --build -d

## Kubctl

* **Get Contexts:** kubectl config get-contexts

* **Set Current Context:** kubectl config use-context CONTEXT

* **Set Current Namespace:** kubectl config set-context --current --namespace=NAMESPACE

* **Apply File:** kubectl apply -f FILE.yml

* **Apply Files Within Directory:** kubectl apply -f DIRECTORY

* **Restart Deployment:** kubectl rollout restart deploy DEPLOYMENT

* **Get All:** kubectl get all

* **Delete All In Namespace:** kubectl delete all --all -n NAMESPACE

* **Delete Namespace:** kubectl delete namespace NAMESPACE

* **Logs Deployment:** kubectl logs -f deploy/DEPLOYMENT

* **Logs Pod:** kubectl logs -p POD

* **Logs:** kubectl logs --all-containers=true --selector app=APP --since=1h --tail=-1 > C:\Log.txt

## Helm

* **Create Helm Chart:** helm create NAME

* **Apply Helm Chart:** helm upgrade NAME --values VALUES.yaml

## Helm Package

* helm package NAME

* helm repo index REPO/ --url https://USERNAME.github.io/REPO

* helm repo add REPO https://USERNAME.github.io/REPO

* helm install REPO/NAME --name=NAME

## Azure

* **Install Azure Kubernetes CLI:** az aks install-cli

* **Set Subscription:** az account set --subscription SUBSCRIPTION

* **Connect Azure Kubernetes Service:** az aks get-credentials --resource-group RESOURCE_GROUP --name CLUSTER_NAME --admin

* **Export Azure Kubernetes Service Configuration:** az aks get-credentials --resource-group RESOURCE_GROUP --name CLUSTER_NAME --admin --file FILE

* **Create Azure Credentials:** az ad sp create-for-rbac --name NAME --role contributor --scopes /subscriptions/SUBSCRIPTION/resourceGroups/RESOURCE_GROUP --sdk-auth
