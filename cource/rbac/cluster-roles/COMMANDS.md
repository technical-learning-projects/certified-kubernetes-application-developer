# Cluster roles

### Create cluster role:

```shell
kubectl create -f administrator-cluster-role.yaml
```

### Create cluster role binding:

```shell
kubectl create -f administrator-cluster-role-binding.yaml
```

### Count cluster roles without headers:

```shell
k get clusterroles --no-headers | wc -l
```