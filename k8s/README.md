```
#Create ConfigMaps
kubectl create configmap mysql-credentials --from-literal=username=callicoder --from-literal=password=c@ll1c0d3r --from-literal=root-password=R00t --dry-run=client -oyaml

#Create Secrets
kubectl create secret generic mysql-root-pass --from-literal=password=R00t

kubectl create secret generic mysql-user-pass --from-literal=username=callicoder --from-literal=password=c@ll1c0d3r

kubectl create secret generic mysql-db-url --from-literal=database=polls --from-literal=url='jdbc:mysql://polling-app-mysql:3306/polls?useSSL=false&serverTimezone=UTC&useLegacyDatetimeCode=false'

#Create Deployment
kubectl create deployment polling-app-mysql --image=mysql --port=3306 --dry-run=client -oyaml
```