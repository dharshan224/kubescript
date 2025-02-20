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
- ReplicationController

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

- ReplicaSet
 ```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: amazon
spec:
  replicas: 3
  selector:
    matchExpressions:
      - {key: myname, operator: In, values: [signup, login, home]}
      - {key: env, operator: NotIn, values: [amazon]}
  template:
    metadata:
      name: devops
      labels:
        myname: signup
    spec:
      containers:
        - name: signup
          image: httpd
          ports:
            - containerPort: 80
```






