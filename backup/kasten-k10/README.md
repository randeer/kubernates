## Installing K10 on Other Kubernetes Distributions

`helm repo add kasten https://charts.kasten.io/`

`kubectl create namespace kasten-io`

##### Pre-flight Checks
`curl https://docs.kasten.io/tools/k10_primer.sh | bash`

##### To install it:
`helm install k10 kasten/k10 --namespace=kasten-io -f values.yaml`