net-pol/ README

Purpose:
NetworkPolicy examples showing deny-by-default and selective allow rules for namespaces and pods.

Quick start:
- Review net-pol-2-*.yaml to understand namespace-wide and pod-specific policy examples.
- Apply a policy: kubectl apply -f net-pol/net-pol-2-all-deny.yaml

Notes:
- NetworkPolicies require a CNI that enforces them (e.g., Calico). Test policies in a non-production cluster before wide rollout.