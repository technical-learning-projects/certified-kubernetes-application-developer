## Service Account
Get:
```shell
kubectl get as
```
```shell
kubectl get serviceaccounts
```
Create service account:
```shell
kubectl create sa service-account-name
```
```shell
kubectl create serviceaccount service-account-name
```
Create token for service account:
```shell
kubectl create token service-account-name
```
Describe service account:
```shell
kubectl describe sa service-account-name
```
Describe secret:
```shell
kubectl describe secret secret-name
```
