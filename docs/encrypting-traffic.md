# Encrypting Traffic


## Create the Certificates Extension

```
kubectl create -f extensions/certificate.yaml
```

## Create the kube-cert-manager deployment

```
kubectl create -f deployments/kube-cert-manager.yaml
```

## Create the lobsters certificate

Create a secret to hold the Google DNS service account credentials:

```
kubectl create secret generic hightowerlabs --from-file service-account.json
```

Create the lobsters.hightowerlabs.com certificate config:

```
kubectl create -f certificates/lobsters.yaml
```

## Update the lobsters deployment 

Create the nginx configmap:

```
kubectl create configmap nginx --from-file configs/lobsters.conf
```

Update the lobsters deployment:

```
kubectl apply -f deployments/lobsters-secure.yaml
```
