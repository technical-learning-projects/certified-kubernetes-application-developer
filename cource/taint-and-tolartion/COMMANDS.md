## Taints and Tolerations
Taint:
```shell
kubectl taint nodes <node-name> <key>=<value>:<taint-effect>
```
`taint-effect` types:
* NoExecute
* NoSchedule
* PreferNoSchedule
```shell
kubectl taint nodes node-1 app=blue:NoSchedule
```
Describe taint:
```shell
kubectl describe node node-name | grep Taints
```
Un taint:
```shell
kubectl taint nodes <node-name> <key>=<value>:<taint-effect>-
```
```shell
kubectl taint nodes node-1 app=blue:NoSchedule-
```
