## Replica Set
Get replica sets:
```shell
kubectl get rs -o wide
```
```shell
kubectl get replicaset
```
Replace/update replica set:
```shell
kubectl replace -f replica-set-definition.yml
```
Scale replica set:
```shell
kubectl scale -f replica-set-definition.yml --replicas=3
```
```shell
kubectl scale rs replica-set-name --replicas=6
```
Delete replica set:
```shell
kubectl delete rs replica-set-name
```
```shell
kubectl delete replicaset replica-set-name
```
