# Admission Controller

## View Admission Controllers:

```shell
kube-apiserver -h | grep enable-admission-plugins
```

```shell
ps -ef | grep kube-apiserver | grep admission-plugins
```

```shell
kubectl exec kube-apiserver-controlplane -n kube-system -- kube-apiserver -h | grep enable-admission-plugins
```