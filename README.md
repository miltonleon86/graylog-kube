# graylog-kube
# graylog cluster in kubernetes
# Steps to install graylog cluster 

### 1. Make sure kubectl is up and working , connecting to kubenetes

### 2. Modify you host on the graylog deployment and set your environment
```
 - name: GRAYLOG_WEB_ENDPOINT_URI
   value: http://your_host/api
 - name: GRAYLOG_ELASTICSEARCH_HOSTS
   value: http://your_host:port  
 - name: GRAYLOG_PASSWORD_SECRET
   value: Some_secret_password_321
 - name: GRAYLOG_ROOT_PASSWORD_SHA2
   value: A270CD4BF0378870F296EAB1F8CC52E24D88CE7A2513A57F4CABD9272D097178
```

##### Use this sha256 to test or create you own secret value here:
https://passwordsgenerator.net/sha256-hash-generator/

### 3. Run graylog cluster 
```
 kubectl create -f elasticsearch-deployment.yaml,elasticsearch-service.yaml,graylog-service.yaml,graylog-deployment.yaml,mongo-service.yaml,mongo-deployment.yaml
```

##### Deleting the Pods would mean that you lose all graylog data. Do not use this in production. At least not with the current pod volume yml conf.

* TODOs
  * Check why UDP errors are not being show on the cluster Graylog.
  * Do not open any external endpoint. Graylog should be deployed as a 
  kube-system kubernetes intern api.
