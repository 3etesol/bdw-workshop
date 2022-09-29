## Install Argo CD

```shell
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
## Make Argo CD manage itself

1. Apply the main app that will manage all files in this repository
```shell
kubectl apply -f applications/main-app.yaml
```
After applying the manifest Argo CD will manage itself. 
Every push to this repository will be applied automatically by Argo CD.

2. Access the UI
https://localhost/

Username: admin  
Password
```sh
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo
```
