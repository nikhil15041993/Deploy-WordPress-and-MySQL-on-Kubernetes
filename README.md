
# Deploying WordPress and MySQL with Persistent Volumes

# Objectives
Create PersistentVolumeClaims and PersistentVolumes

    1. mysql.yaml (MySQL resource configs)
    2. wordpress.yaml ( WordPress resource configs)
    3. mysql-configmap.yaml 
    4. secretfile.yaml ( mysql password file)
    Apply all the files  by kubectl apply -k ./
    







MySQL and Wordpress each require a PersistentVolume to store data. Their PersistentVolumeClaims will be created at the deployment step.
Many cluster environments have a default StorageClass installed. When a StorageClass is not specified in the PersistentVolumeClaim, the cluster's default StorageClass is used instead.
When a PersistentVolumeClaim is created, a PersistentVolume is dynamically provisioned based on the StorageClass configuration.
