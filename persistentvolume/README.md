persistentvolume/ README

Purpose:
PersistentVolume and PersistentVolumeClaim examples for different storage backends: local volume, NFS, Azure Files, and Azure Blobfuse.

Quick start:
- Inspect the appropriate subfolder for your backend (nfs, local-volume, azure-files, azure-blob).
- Create PV/PVC and then deploy pods that reference them. Example: kubectl apply -f persistentvolume/nfs/nfs-pv.yml

Notes:
- Cloud-specific manifests require corresponding cloud resources and proper storage classes. Update access credentials and endpoints before applying.