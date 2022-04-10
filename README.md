# nfs-provisioner

NFS storage provisioner for the raspberry pi kubernetes cluster, using a hard drive connected to the master node.

## Install

1. Label the node that has a drive attached (named `sauron` here):

```
kubectl label node sauron storage=enabled
```
sauron: 

2. Deploy the helm chart

```
helm install nfs-provisioner charts/nfs-provisioner --namespace storage --create-namespace
```

## Uninstall

```
helm delete nfs-provisioner -n storage
```
