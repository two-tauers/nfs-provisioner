# nfs-provisioner

NFS storage provisioner for the raspberry pi kubernetes cluster, using a hard drive connected to the master node.

## Install

```
helm install nfs-test nfs-provisioner --namespace storage --create-namespace
```

## Uninstall

```
helm delete nfs-test -n storage
```
