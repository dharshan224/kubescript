# kubescript
-
  one pod with one container with container name signup with image ubuntu to print the content signup in the dev namespace
  pod.yml
  ```
  apiVersion: v1
  kind: Pod
  metadata:
    name: shan
  spec:
  containers:
    - name: log
      image: ubuntu
      command: ["/bin/bash", "-c", "while true; do echo shanup; sleep 1; done"]
  ```
  ```
  apiVersion: v1
  kind: Namespace
  metadata:
    name: dev
  ```
- ggvg

```
apiVersion: v1
kind: ReplicationController
metadata:
  name: flipkart
spec:
  replicas: 2
  selector:
    app: nginx
  template:
    metadata:
      name: dev
      labels:
        app: nginx
    spec:
      containers:
        - name: login
          image: nginx
          ports:
            - containerPort: 80
 ```
