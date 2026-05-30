aks/ README

Purpose:
AKS-specific manifests and configuration for deploying sample apps and TLS/certificate settings to Azure Kubernetes Service. Includes ingress and cert-manager examples tuned for AKS.

Quick start:
- Replace placeholders (secrets, DNS) before applying.
- Apply manifests: kubectl apply -f aks/
- For cert-manager, ensure clusterissuers and secrets are configured.

Notes:
- Many files assume Azure resources (KeyVault, AzureFile/Blob storage). Review and replace cloud-specific secrets and storage classes before use.