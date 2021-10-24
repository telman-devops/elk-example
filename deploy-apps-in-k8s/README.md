### Deploy the apps from private registry in k8s cluster

##### create docker-registry secret for dockerHub
    DOCKER_REGISTRY_SERVER=docker.io
    DOCKER_USER=870414
    DOCKER_EMAIL=telman.devops@gmail.com
    DOCKER_PASSWORD=your dockerhub pwd, same as for `docker login`

    kubectl create secret docker-registry myregistrysecret \
    --docker-server=$DOCKER_REGISTRY_SERVER \
    --docker-username=$DOCKER_USER \
    --docker-password=$DOCKER_PASSWORD \
    --docker-email=$DOCKER_EMAIL

##### deploy nodejs app
```

apiVersion: apps/v1
kind: Deployment
metadata:
  name: node-app
  labels:
    app: node-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: node-app
  template:
    metadata:
      labels:
        app: node-app
    spec:
      containers:
        - name: node-app
          image: nanajanashia/demo-app:node-1.0
          imagePullPolicy: Always
          ports:
            - containerPort: 3000
      imagePullSecrets:
        - name: myregistrysecret

```
