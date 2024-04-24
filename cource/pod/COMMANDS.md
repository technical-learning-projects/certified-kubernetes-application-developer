## Pod
Get pods with additional info:
```shell
kubectl get pods -o wide
```
Save pod configuration to `.yml` file (pod will not be instantiated):
```shell
kubectl run redis --image=redis --dry-run=client -o yaml > redis.yml
```
Save pod configuration to `.yml` file form instantiated pod:
```shell
kubectl get pod redis -o yaml > redis.yml
```
Apply changes to pod:
```shell
kubectl apply -f redis.yml
```
Edit pod:
```shell
kubectl edit pod redis
```
Replace existing pod (will delete existing pod and create a new one):
```shell
kubectl replace --force -f redis.yml
```
Execute command inside pod:
```shell
kubectl exec pod-name
```
