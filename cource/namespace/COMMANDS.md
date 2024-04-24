## Namespace
Create namespace:
```shell
kubectl create -f namespace-definition.yml
```
```shell
kubectl create namespace development
```
Get namespaces:
```shell
kubectl get ns
```
```shell
kubectl get namspace
```
Delete namespaces:
```shell
kubectl delete namespace development
```
Change default namespace:
```shell
kubectl config set-context $(kubectl config current-context) -n development
```
```shell
kubectl config set-context $(kubectl config current-context) --namespace=development
```
Get resource from all namespaces:
```shell
kubectl get pod -A
```
```shell
kubectl get pod --all-namespaces
```
DNS access to same namespace:
```shell
service-name
```
DNS access to different namespace:  
`cluster.local` - default kubernetes cluster domain name
`svc` - subdomain name for service
```shell
service-name.namespace-name.svc.cluster.local
```
