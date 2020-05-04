
# Mongo Cluster

## helm v2
```
# helm install --name myapp-mongo mongo-cluster \
  --namespace myapp \
  --set db.username="myapp" \
  --set db.password="myapp-secret-pass" \
  --set db.secretkey="`openssl rand -base64 756`"
```

## helm v3
```
# helm install mongo mongo-cluster \
  --namespace myapp \
  --set db.username="myapp" \
  --set db.password="myapp-secret-pass" \
  --set db.secretkey="`openssl rand -base64 756`"
```