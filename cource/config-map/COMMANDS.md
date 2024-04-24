## Config Map
### Create config map:
```shell
kubectl create configmap configmap-name --from-literal=APP_COLOR=blue --from-literal=APP_MODE=production
```
```shell
kubectl create configmap --form-file=custom-config-data.properties
```
```shell
kubectl create -f config-map-definition.yml
```
### Get config map:
```shell
kubectl get cm
```
```shell
kubectl get configmaps
```
