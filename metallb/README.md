metallb/ README

Purpose:
MetalLB configuration and address pool examples for providing LoadBalancer service support in bare-metal or kind clusters.

Quick start:
1. Install MetalLB: kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.13.9/config/manifests/metallb-native.yaml
2. Apply the address pool: kubectl apply -f metallb/first-pool.yaml

Notes:
- Update the IP range in first-pool.yaml to an address range available in your environment. Do not overlap existing network allocations.