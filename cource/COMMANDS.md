### Shortcuts 
* `po`     - pods
* `rs`     - replica sets
* `deploy` - deployments
* `svc`    - services
* `netpol` - network policies
* `pv`     - persistent volumes
* `pvc`    - persistent volume claims
* `sa`     - service accounts

## Common Commands
Get all resources:
```shell
kubectl get all
```
Get in different formats:
```shell
kubectl get pod -o wide
```
Explore configuration structure for (pod, rs, deployment etc.):
```shell
kubectl explain pod
```
Execute command inside pod:
```shell
kubectl exec pod-name
```
#### VIM
Hit the Esc key to enter "Normal mode". Then you can type : to enter "Command-line mode". A colon (:) will appear at the bottom of the screen and you can type in one of the following commands. To execute a command, press the Enter key.

:q to quit (short for :quit)
:q! to quit without saving (short for :quit!)
:wq to write and quit
:wq! to write and quit, attempting to force the write if the file lacks write permission
:x to write and quit; like :wq but writes only if modified (short for :exit)
:qa to quit all (short for :quitall)
:cq to quit, without saving, with a nonzero exit code to indicate failure (short for :cquit)
You can also quit Vim directly from "Normal mode" by typing ZZ to save and quit (same as :x) or ZQ to just quit (same as :q!). (Note that case is important here. ZZ and zz do not mean the same thing.)

Vim has extensive help - that you can access with the :help command - where you can find answers to all your questions and a tutorial for beginners.
