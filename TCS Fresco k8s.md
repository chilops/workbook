---
title: 'TCS Fresco k8s '
uuid: 220df7a8-c99d-11ef-b41f-0dd507f23cb3
version: 81
created: '2025-01-03T12:06:58+05:30'
---

**Minikube installation**

```
sudo chmod 777 /var/run/docker.sock
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
```

```
rm -rf minikube_latest_amd64.deb
```

\

\

**Start Minikube** and execute this command to sync host docker with minikube docker

```
minikube start
minikube -p minikube docker-env
eval $(minikube docker-env)
```

\

\

You can create a pod object using the kubectl run command with the specified image and expose it on port 8080 with the following command:

```
kubectl run firstapp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080
kubectl get pod firstapp        --> to check if pod isrunning or not
```

\

Expose the application to the local VM by creating a Service object of type NodePort.

To expose your application to the local VM by creating a Service object of type NodePort, you can use the following kubectl

\

**Expose command:**

```
kubectl expose pod firstapp --type=NodePort --port=8080
```

```
kubectl get svc firstapp
```

\

\

Create another deployment using a 'YAML' file, create a deployment.yaml file that contains information of the number of replicas and the images to be used. Use an nginx image to deploy. Name the deployment as 'nginx'

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

\

```
kubectl apply -f deployment.yaml
```

```
kubectl get deployment nginx
```

\

Create a NodePort type service using a 'YAML' file, create a service.yaml file that contains information of the type of service and the port numbers. Name the Service nginx-svc and use port 30080 for node Port.

\

```
apiVersion: v1
kind: Service
metadata:
  name: nginx-svc
spec:
  type: NodePort
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
      nodePort: 30080
```

\

```
kubectl apply -f service.yaml
```

```
kubectl get svc nginx-svc
```

\

Use kubectl exec command to get inside the running nginx pod and write the string 'Welcome to fresco nginx pod' to /usr/share/nginx/html/index.html file

```
kubectl get pods -l app=nginx
```

\

```
kubectl exec <nginx-pod-name> -- sh -c 'echo "Welcome to fresco nginx pod" > /usr/share/nginx/html/index.html'
kubectl exec -it nginx-pod-name -- /bin/sh -c "echo 'Welcome to fresco nginx pod' > /usr/share/nginx/html/index.html"
```