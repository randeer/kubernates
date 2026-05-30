# kubernates — Kubernetes examples, manifests, and KIND configs

Repository purpose

This repository collects Kubernetes manifests, Kind (Kubernetes-in-Docker) configurations, Helm helper scripts, and examples used to deploy and test services locally and on cloud providers (AKS). It is intended as a reference and convenience repo for: local development with kind, ingress and MetalLB setup, sample apps and TLS/cert-manager examples, Argo CD manifests, and Teleport access examples.

Top-level layout

- aks/                     — AKS-specific manifests, ingress, and cert configuration
- argocd/                  — Argo CD manifests and ingress examples
- cert-manager/            — cert-manager configuration and ACME/http-challenge examples
- ingress/                 — ingress examples (nginx, Traefik) and TLS helpers
- kind-config*.yaml        — kind cluster configs used for local clusters
- kind-ingress/            — ingress controller manifests tuned for kind
- metallb/                 — MetalLB address pool and configuration
- persistentvolume/        — PV/PVC examples (nfs, local, azure-files/blob)
- teleport/                — Teleport deployment examples and k8s manifests
- get_helm.sh              — helper script to install Helm client/requirements
- net-pol/                 — network policy examples
- backup/                  — backup operator examples (e.g., Kasten K10)

Quickstart: run a local kind cluster (recommended flow)

Prerequisites:
- Docker
- kind (https://kind.sigs.k8s.io)
- kubectl
- helm (optional, for helm charts)

Example steps:
1. Create a kind cluster using the provided config (adjust hostPorts if needed):
   kind create cluster --config kind-config-new.yaml --name my-kind

2. Install MetalLB (for LoadBalancer support in kind):
   kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.13.9/config/manifests/metallb-native.yaml
   kubectl apply -f metallb/first-pool.yaml

3. Install an ingress controller (nginx or traefik) using manifests in kind-ingress/ or ingress/.

4. Deploy sample app (AKS examples or myapp in aks/deployment) or apply manifests in aks/:
   kubectl apply -f aks/deployment/myapp.yaml

5. Use kubectl port-forward, or access services via the MetalLB IPs / nodePorts shown by kubectl get svc.

Deploying Argo CD / Teleport / cert-manager

- Argo CD manifests live in argocd/ — apply the server ingress or install via helm.
- Teleport manifests and values are in teleport/ — follow its README within that folder.
- cert-manager folder includes cluster issuer examples and HTTP challenge ingress configs. Replace DNS/cloud credentials with your own secrets before applying.

Security & secrets

This repo contains example secret manifests and certificate files in places (for demonstration). DO NOT apply those to production clusters. Replace credentials, cloud API keys, and TLS secrets with values stored in a vault or Kubernetes Secret managed securely.

Notes and caveats

- Many manifests assume a non-production/test environment. Review hostPorts, NodePort ranges, and privileged settings before use.
- KIND clusters are ephemeral and run inside Docker; some cloud-specific features (e.g., Azure files, managed load balancers) require cloud provider setup.
- Some files reference domain names and DNS providers — update ACME and DNS records appropriately.

Contributing

Contributions welcome. Open an issue or PR describing the change. When adding manifests, include a README in the subfolder explaining how to use them.

License

Check repository root or consult the owner for license details.

Contact

If anything in this README needs tailoring to a specific workflow (AKS, GKE, or an automated GitOps flow), say which and a focused README can be created for that target environment.
#### What is Kubernetes?
Kubernetes is a container orchestration platform that automates the deployment, scaling, and management of containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).

#### What is KIND?
KIND (Kubernetes in Docker) is a tool for running local Kubernetes clusters using Docker container "nodes". It provides a lightweight and easy-to-use way to set up and test Kubernetes applications in a local environment.
