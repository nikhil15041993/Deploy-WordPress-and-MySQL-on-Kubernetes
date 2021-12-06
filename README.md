# How to deploy WordPress and MySQL on Kubernetes

## Steps


* Create PersistentVolumeClaims and PersistentVolumes
* Create a Secret for MySQL
* Deploy MySQL
* Deploy WordPress
* Troubleshooting

## Create a Secret for MySQL Password

A Secret is an object that stores a piece of sensitive data like a password or key.
```
apiVersion: v1
kind: Secret
metadata:
  name: mysql-pass
type: Opaque
data:
        
  password: password
  ```
  
Then run:
```
kubectl create -f secret.yml  
```
Deploy MySQL and WordPress 

Here’s the mysql.yaml for MySQL service and wordpress.yaml for WordPress

Now create the deployment and service:
```
kubectl create -f mysql.yaml
kubectl create -f wordpress.yaml
```

## Launch WordPress

```
minikube service <service name>
```

