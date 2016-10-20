# Encrypting Traffic


Create the Certificates Extension

```
kubectl create -f extensions/certificate.yaml
```

Create the google cloud account secret

```
kubectl create secret generic hightowerlabs --from-file service-account.json
```

```
kubectl create -f deployments/kube-cert-manager.yaml
```

```
kubectl get secrets
```

```
kubectl get certificates
```

```
kubectl create -f certificates/lobsters.yaml
```
