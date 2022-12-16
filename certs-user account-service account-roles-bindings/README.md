To Genarate a new key using "openssl"
openssl genrsa -out key_name.key 2048


To generate a CSR
openssl req -new -key key_name.key -subj "/CN=randeer"  -out new_csr.csr

To verfiy the certificate
openssl x509 -in my-cert.crt -text -noot

-------------------------------------------------
For a service account:
kubectl create clusterrolebinding user_name-binding --clusterrole=cluster_role_name --serviceaccount=namespace:user_name