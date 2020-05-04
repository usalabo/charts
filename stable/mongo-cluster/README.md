
# Mongo Cluster

## add repository
```
helm repo add usalabo-stable https://usalabo.github.io/charts/stable
```

## install chart

### helm v2
```
# helm install --name myapp-mongo usalabo-stable/mongo-cluster \
  --namespace myapp \
  --set db.username="myapp" \
  --set db.password="myapp-secret-pass" \
  --set db.secretkey="`openssl rand -base64 756`"
```

### helm v3
```
# helm install mongo usalabo-stable/mongo-cluster \
  --namespace myapp \
  --set db.username="myapp" \
  --set db.password="myapp-secret-pass" \
  --set db.secretkey="`openssl rand -base64 756`"
```
