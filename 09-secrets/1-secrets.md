# Secrets

### passwords

```s
kubectl apply -f secrets.yaml
kubectl describe secrets credentials
kubectl get secrets credentials -o jsonpath='{.data.username}'
kubectl get secrets credentials -o jsonpath='{.data.password}' | base64 -d

kubectl apply -f test-pod-secrets.yaml
kubectl logs pod/test-pod
```

### certificates

```s
openssl genrsa -out ssl.key 2048
openssl req -new -x509 -key ssl.key -out ssl.cert -days 360 -subj /CN=secret-server.demo.com

kubectl create secret tls certificates  --key ssl.key --cert ssl.cert
kubectl describe secrets certificates

kubectl apply -f test-pod-tls-as-volume.yaml
kubectl logs pod/test-pod
```
