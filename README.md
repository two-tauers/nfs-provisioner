# nfs-provisioner

NFS storage provisioner for a kubernetes cluster, using a hard drive mounted on a node.

## Prerequisites

Storage mounted on one of the node.

## Install

1. Label the node that has a drive attached (named `sauron` here):

```
kubectl label node sauron storage=enabled
```

The node selector can be changed in `values.yaml`.

2. Deploy the helm chart

```
helm repo add two-tauers https://two-tauers.github.io/helm-charts
helm install nfs-provisioner two-tauers/nfs-provisioner --namespace storage --create-namespace
```

The chart will deploy nfs-server to share the storage across the cluster and a storage class `managed-nfs-storage` that uses it.

## Uninstall

```
helm delete nfs-provisioner -n storage
```

## values.yaml

See comments in [values.yaml](values.yaml)
