# Deploy MySQL

## Create Google Persistent Disk

```
gcloud compute disks create mysql
```

## Create mysql Secrets

```
kubectl create secret generic lobsters \
  --from-literal=root-password=l0bst3rs \
  --from-literal=mysql-password=lobsters \
  --from-literal='database-url=mysql2://lobsters:lobsters@mysql:3306/lobsters'
```

## Create mysql Deployment

```
kubectl create -f deployments/mysql.yaml 
```

## Create mysql Service

```
kubectl create -f services/mysql.yaml
```
