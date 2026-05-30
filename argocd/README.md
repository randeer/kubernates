argocd/ README

Purpose:
Manifests and ingress examples to install or configure Argo CD. Contains sample ingress/Traefik routes for exposing the Argo CD server.

Quick start:
- Install Argo CD via Helm or manifests, then apply files in this folder as needed.
- Example: kubectl apply -f argocd/argocd-server-ingress.yaml

Notes:
- Replace TLS certs and DNS hostnames with your values. Use GitOps patterns to point Argo CD to this repository as an applications source.