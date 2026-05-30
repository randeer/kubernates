teleport/ README

Purpose:
Teleport deployment examples for providing secure SSH and Kubernetes access. Contains Helm values, k8s manifests, and docker-compose examples.

Quick start:
- Review teleport/config/teleport.yaml and values.yml.
- Deploy with helm or kubectl: kubectl apply -f teleport/k8s.yaml (adjust secrets and storage claims)

Notes:
- Teleport requires secure secrets management for tokens and TLS certs. Replace example secrets with values from a vault and secure cluster access.