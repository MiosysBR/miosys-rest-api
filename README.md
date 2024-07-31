# miosys-rest-api

```
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/miosys-route.yaml
```

```
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/miosys-api-route.yaml
```

```
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.11.0/cert-manager.yaml
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout miosys-com-br-tls.key -out miosys-com-br-tls.crt -subj "/CN=miosys.com.br"
kubectl create secret tls miosys-com-br-tls --key="miosys-com-br-tls.key" --cert="miosys-com-br-tls.crt"
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/miosys-gateway-http.yaml
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/issuer-lets-encrypt-staging.yaml
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/miosys-gateway-https.yaml
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/certificate.yaml
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/issuer-lets-encrypt-production.yaml
kubectl apply -f https://raw.githubusercontent.com/MiosysBR/miosys-rest-api/main/certificate.yaml
```