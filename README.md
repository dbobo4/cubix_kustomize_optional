# Cubix Kustomize optional homework - Adam Kovacs

## Installation commands

```powershell
kubectl create namespace hw4-optional-dev-backapp --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace hw4-optional-test-backapp --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace hw4-optional-prod-backapp --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace hw4-optional-dev-both --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace hw4-optional-test-both --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace hw4-optional-prod-both --dry-run=client -o yaml | kubectl apply -f -
kubectl apply -k overlays/dev-backapp
kubectl apply -k overlays/test-backapp
kubectl apply -k overlays/prod-backapp
kubectl apply -k overlays/dev-both
kubectl apply -k overlays/test-both
kubectl apply -k overlays/prod-both
```

## Verification commands

```powershell
kubectl get all -n hw4-optional-dev-backapp
kubectl get all -n hw4-optional-test-backapp
kubectl get all -n hw4-optional-prod-backapp
kubectl get all -n hw4-optional-dev-both
kubectl get all -n hw4-optional-test-both
kubectl get all -n hw4-optional-prod-both
kubectl get ingress -n hw4-optional-dev-backapp
kubectl get ingress -n hw4-optional-test-backapp
kubectl get ingress -n hw4-optional-prod-backapp
kubectl get ingress -n hw4-optional-dev-both
kubectl get ingress -n hw4-optional-test-both
kubectl get ingress -n hw4-optional-prod-both
(Invoke-WebRequest -UseBasicParsing http://other.cubix.localhost:8080/dev).Content
(Invoke-WebRequest -UseBasicParsing http://other.cubix.localhost:8080/test).Content
(Invoke-WebRequest -UseBasicParsing http://other.cubix.localhost:8080/prod).Content
(Invoke-WebRequest -UseBasicParsing http://application.cubix.localhost:8080/dev).Content
(Invoke-WebRequest -UseBasicParsing http://application.cubix.localhost:8080/test).Content
(Invoke-WebRequest -UseBasicParsing http://application.cubix.localhost:8080/prod).Content
```
