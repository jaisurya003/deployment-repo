# deployment-repo
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mypod
  labels:
    app: mypod
spec:
  replicas: 3
  selector:
    matchLabels:
      app: mypod
  template:
    metadata:
      labels:
        app: mypod
    spec:
      containers:
        - name: cont1
          image: 301804611986.dkr.ecr.ap-south-1.amazonaws.com/my-ecr-repo:latest  # in this line it should be latest while running 
          imagePullPolicy: IfNotPresent                                             # 128913199644.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest
          ports:
            - containerPort: 80
          resources:
            requests:
              cpu: "100m"
              memory: "128Mi"
            limits:
              cpu: "500m"
              memory: "256Mi"
          env:
            - name: ENV
              value: "dev"

```
