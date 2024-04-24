## Kube Config

### View config:

```shell
kubectl config view
```

```shell
kubectl confgi view --kubeconfig custom-config.yaml
```

### Switch the context:

```shell
kubectl config use-context kube-admin@kube-cluster
```

### Send secured request to the kubernetes API:

```shell
curl https://kube-host-or-ip:6443/api/v1/pods --key admin.key --cert admin.crt --cacert ca.crt
```

```shell
kubectl get pods --server kube-host-or-ip:6443 --client-key admin.key --client-certificate admin.crt --certificate-authority ca.crt
```

### Config file

$HOME/.kube/config

```text
--server kube-host-or-ip:6443
--client-key admin.key
--client-certificate admin.crt
--certificate-authority ca.crt
```
