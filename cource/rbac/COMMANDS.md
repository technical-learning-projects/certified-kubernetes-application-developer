## RBAC Commands

Create role:

```shell
kubectl create -f developer-role.yaml
```

```shell
kubectl create role developer --namespace=default --verb=list,create,delete --resource=pods
```

Create binding:

```shell
kubectl create -f dev-user-developer-binding.yaml
```

```shell
kubectl create rolebinding dev-user-binding --namespace=default --role=developer --user=dev-user
```

Get roles:

```shell
kubectl get roles
```

Get bindings:

```shell
kubectl get rolebindings
```

Describe role:

```shell
kubectl describe role developer
```

Describe role binding:

```shell
kubectl describe rolebinding dev-user-developer-binding
```

Can I:

```shell
kubectl auth can-i create deployments --as dev-user --namespace test
```

Describe control-plane:

```shell
kubectl describe pod kube-apiserver-controlplane -n kube-system
```

```shell
ps
```
