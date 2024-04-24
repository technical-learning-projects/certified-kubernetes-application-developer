## Labels Selectors Annotations
Get all objects by selectors:
```shell
kubectl get all --selector app=demo,function=backend
```
Get all pods:
```shell
kubectl get pods --selector app=demo,function=backend
```
Gat amount of all objects:
```shell
kubectl get all --selector app=demo,function=backend --no-headers | wc -l
```

