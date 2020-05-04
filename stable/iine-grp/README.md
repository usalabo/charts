# iine GRP

## add repository
```
helm repo add usalabo-stable https://usalabo.github.io/charts/stable
```

## install chart

### helm v2
```
# helm install --name iine-grp usalabo-stable/iine-grp \
  --namespace myapp \
  --set mongo-cluster.db.username="myapp" \
  --set mongo-cluster.db.password="myapp-secret-pass" \
  --set mongo-cluster.db.secretkey="`openssl rand -base64 756`" \
  --set ingress.hosts[0].host="mydomain" \
  --set api.auth.privateKey="secret" \
  --set api.auth.domain="mytenant.auth0.com" \
  --set api.auth.clientId="xxxxx" \
  --set api.auth.clientSecret="xxxxx" \
  --set api.auth.redirectUrl="http://mydomain/callback" \
  --set api.auth.logoutRedirectUrl="http://mydomain/login" \
  --set api.defaultAdminUser.username="root" \
  --set api.defaultAdminUser.password="password"
```

### helm v3
```
# helm install iine-grp usalabo-stable/iine-grp \
  --namespace myapp \
  --set mongo-cluster.db.username="myapp" \
  --set mongo-cluster.db.password="myapp-secret-pass" \
  --set mongo-cluster.db.secretkey="`openssl rand -base64 756`" \
  --set ingress.hosts[0].host="mydomain" \
  --set api.auth.privateKey="secret" \
  --set api.auth.domain="mytenant.auth0.com" \
  --set api.auth.clientId="xxxxx" \
  --set api.auth.clientSecret="xxxxx" \
  --set api.auth.redirectUrl="http://mydomain/callback" \
  --set api.auth.logoutRedirectUrl="http://mydomain/login" \
  --set api.defaultAdminUser.username="root" \
  --set api.defaultAdminUser.password="password"
```

## add user
```
# iine login -e http://mydomain -u root -p password
# iine download-users
# vi users.csv
"ID","姓","名","ロール","有効","SSOユーザーID","ユーザー","パスワード","削除"
"5eb07c08bac603001bce63af","管理","ユーザー","admin","TRUE","","root","",""
"","追加","ユーザー","user","TRUE","user@mydomain","","",""

# iine upload-users
```
