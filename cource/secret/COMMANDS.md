## Secrets
### Create Secret:
```shell
kubectl create -f secret-definition.yml
```
```shell
kubectl create secret generic secret-name --from-literal=DB_HOST=postgres
```
### Get Secrets:
```shell
kubectl get secrets
```
```shell
kubectl get secrets
```
```shell
kubectl describe secrets
```
```shell
kubectl get secret secret-name -o yaml
```
### Convert string to base64:
```shell
echo -n 'password' | base64
```
```shell
echo -n 'cGFzd3Jk' | base64 --decode
```
