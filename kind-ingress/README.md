kind-ingress/ README

Purpose:
Ingress controller manifests and tuning suggestions for running ingress (nginx) inside kind clusters. These files are tailored to run inside Docker-backed nodes.

Quick start:
1. Create kind cluster using kind-config-new.yaml
2. Apply ingress manifests: kubectl apply -f kind-ingress/ingress-nginx-kind.yaml
3. Adjust hostPort mappings or NodePorts in the config if ports conflict.

Notes:
- kind does not provide cloud load balancers; use MetalLB or NodePort for service access.