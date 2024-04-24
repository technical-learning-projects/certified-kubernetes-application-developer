## Ingress
Deploy Ingress Controller:
```shell
helm upgrade --install ingress-nginx ingress-nginx --repo https://kubernetes.github.io/ingress-nginx --namespace ingress-nginx --create-namespace
```
This command is idempotent:
* if the ingress controller is not installed, it will install it;
* if the ingress controller is already installed, it will  upgrade it;

Create:
```shell
kubectl create -f ingress-drfinition.yaml
```
Get ingress:
```shell
kubectl get ingress
```
