Force HTTPS trafic to your k8s cluster, we need to have certificate first

openssl req -new -newkey rsa:2048 -days 365 -nodes -x509 -keyout nginx-selfsigned.key -out nginx-selfsigned.crt

kubectl create secret tls nginx-tls-secret --cert=nginx-selfsigned.crt --key=nginx-selfsigned.key -n nginx-test
