# graylog-kube
# graylog cluster in kubernetes
# Steps to install graylog cluster 

### 1. Make sure kubectl is up and working , connecting to kubenetes

### 2. Modify you host on the graylog deployment and set you environment
```
 - name: GRAYLOG_WEB_ENDPOINT_URI
   value: http://your_host/api
 - name: GRAYLOG_PASSWORD_SECRET
   value: somesaltpassword
 - name: GRAYLOG_ROOT_PASSWORD_SHA2
   value: 5D5E792708BFA15F0AB42E817B4E69379777D2722E0529DFB031C0B847DB137D
```

### 3. Run graylog cluster 
```
 kubectl create -f elasticsearch-deployment.yaml,elasticsearch-service.yaml,graylog-service.yaml,graylog-deployment.yaml,mongo-service.yaml,mongo-deployment.yaml
```
