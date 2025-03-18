---
title: Minikube Installation & ALL
uuid: 1a951a6e-feff-11ef-b328-05c51be8b43a
version: 1232
created: '2025-03-12T10:31:48+05:30'
---

\

### **Installing Minikube in Ubuntu server (Digital Ocean)**<!-- {"collapsed":true} -->

\

**Step1: Install docker**

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker apt repository. Afterward, you can install and update Docker from the repository.

\

**Setup Docker's apt repository.**

\

\# Add Docker's official GPG key:

```
sudo apt-get update
```

```
sudo apt-get install ca-certificates curl
```

```
sudo install -m 0755 -d /etc/apt/keyrings
```

```
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
```

```
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

\

\# Add the repository to Apt sources:

```
echo \
 "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
 $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
 sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```
sudo apt-get update
```

\

**Install the Docker packages.**

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

\

\

**Verify that the installation is successful by running the hello-world image:**

```
sudo docker run hello-world
```

\

\

**Step2: Minikube installation**

```
sudo chmod 777 /var/run/docker.sock
sudo curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
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
or 
minikube start --force
snap install kubectl --classic       --> this will install kubectl if it not present
minikube -p minikube docker-env
eval $(minikube docker-env)
or
eval $(minikube -p minikube docker-env)
```

\

**Command to check if cluster is running:**

```
kubectl config view
```

\

```
kubectl get nodes
```

\

**Install fish to get colored interface in only UBUNTU server (not necessary)**

```
sudo apt install fish
```

execute below command to enter fish terminal

```
fish
```

<mark style="background-color:#F9B68D;">Minikube installation completed.<!-- {"backgroundCycleColor":"13"} --></mark>

\

\

### **Simple Deployment**<!-- {"collapsed":true} -->

**Creating simple deployment:**

```
kubectl create deployment hello-node1 --image=k8s.gcr.io/echoserver:1.10
```

To check the current deployments:

```
kubectl get deployment
```

To check running pods:

```
kubectl get pods
```

\

**To expose our POD to external world (Internet), for that we are going to create service**

```
kubectl expose deployment hello-node1 --type=LoadBalancer --port=8080 
```

\

To check if service created:

```
kubectl get service
```

\

To get the URL access

```
minikube service hello-node1
```

\

To delete the service

```
kubectl delete service hello-node1
```

\

To delete the deployment. (All PODS associated under deployment will be deleted.)

```
kubectl delete deployment hello-node1
kubectl get deployment
kubectl get pods
```


---

### **Namespaces**<!-- {"collapsed":true} -->

To get all current namespaces in k8s cluster

```
kubectl get namespace
```

\

To get resources under particular namespace

```
kubectl get pods --namespace kube-system
```

\

To get all pods running in all namespaces

```
kubectl get pods --all-namespaces
```

\

To create a new namespace

```
kubectl create namespace mynamespace
```

```
kubectl get namespaces
```

\

To delete a namespace

```
kubectl create namespace mynamespace
```

```
kubectl get namespaces
```


---

### **Kubernetes cluster upgrade process**<!-- {"collapsed":true} -->

**K8s Upgrade Master: Upgrading Control Plane Node.**

- Drain Control Plane Node.

- Plan the Upgrade. 

- Apply the Upgrade.

- Upgrade kubectl & kubelet on control plane node. 

- Uncordon the Master Node.

**K8s Upgrade Worker: Upgrading Worker Node.**

- Drain Worker Node.

- Upgrade kubeadm.

- Upgrade kubelet config. 

- Upgrade kubectl and kubelet. 

- Uncordon the Worker Node.

**\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Upgrade Control Plane Node \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

\

1\. Get the Running Node and Version

```
kubectl get nodes
```

\

2\. Drain Master Node

```
kubectl drain <node-to-drain> --ignore-daemonsets
```

\

3\. Upgrade kubeadm

```plain
sudo apt-get updatesudo apt-get install -y --allow-change-held-packages kubeadm=1.21.1-00
```

\

4\. Verify that the download works and has the expected version:

```
kubeadm version
```

\

5\. Verify the upgrade plan

```
sudo kubeadm upgrade plan v1.21.1-00
```

\

6\. Apply the Upgrade

```
sudo kubeadm upgrade apply v1.21.1
```

\

7\. Upgrade kubelet and kubectl packages

```plain
sudo apt-get updatesudo apt-get install -y --allow-change-held-packages kubelet=1.21.1-00 kubectl=1.21.1-00
```

\

8\. Restart the kubelet:

```plain
sudo systemctl daemon-reloadsudo systemctl restart kubelet
```

\

10\. Get the Running Node and Version

```
kubectl get nodes
```

\

11\. Uncordon the Node

```
kubectl uncordon <node-to-uncordon>
```

\

\

**\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Upgrade Worker Node \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

\

1\. Drain Worker Node

```
kubectl drain <node-to-drain> --ignore-daemonsets --force
```

\

2\. Upgrade kubeadm

```plain
sudo apt-get updatesudo apt-get install -y --allow-change-held-packages kubeadm=1.21.1-00
```

\
3\. Verify that the download works and has the expected version:

```
kubeadm version
```

\

4\. For worker nodes this upgrades the local kubelet configuration

```
sudo kubeadm upgrade node
```

\

5\. Upgrade kubelet and kubectl packages

```plain
sudo apt-get updatesudo apt-get install -y --allow-change-held-packages kubelet=1.21.1-00 kubectl=1.21.1-00
```

\

6\. Restart the kubelet:

```plain
sudo systemctl daemon-reloadsudo systemctl restart kubelet
```

\

7\. Get the Running Node and Version

```
kubectl get nodes
```

\

8\. Uncordon the Node

```
kubectl uncordon <node-to-uncordon>
```

\

\

\

\

\

\

\

\

\

\

\

\

\

\

\


---

### **Kubectl commands usage**<!-- {"collapsed":true} -->

Kubectl is a command line tool for a Kubernetes.

- **Kubectl get**           --> kubectl get is used to get the objects present in k8s cluster.

- **Kubectl describe** --> You can get detailed information about any Kubernetes Objects.

- **Kubectl create**     --> You can create any k8s object using kubectl create.

- **Kubectl apply**       --> kubectl apply is similar to kubectl create, diff is creating command will fail if resource already exist in k8s cluster, whereas apply command will execute if same resource already exist.

- **Kubectl delete**     --> kubectl delete will delete the object from k8s cluster.

- **Kubectl exec**        --> Kubectl exec is used to run commands inside containers.

```
mkdir k8sresources
```

```
cd k8sresources
```

```
vi pod1.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: mypod1
  labels:
    tier: frontend
spec:
  containers:
    - name: nginx
      image: nginx:latest
      ports:
        - containerPort: 80
  restartPolicy: OnFailure
```

```
kubectl create -f pod1.yaml       ---> POD created
```

```
kubectl get pods
```

```
kubectl get po
```

```
kubectl get pods mypod1
```

```
kubectl get pods mypod1 -o wide    ---> To get complete information of POD
```

```javascript
kubectl get pods mypod1 -o json    ---> same info as above for program language usage
```

```
kubectl get pods mypod1 -o yaml    ---> To get in yaml format
```

```
kubectl get po -n kube-system
```

```
kubectl api-resources
```

```
kubectl describe pods mypod1       ---> it shows complete information about POD.
```

```c
kubectl exec mypod1 -c nginx -- cat /etc/nginx/nginx.conf
    ---> it executes inside pod and get info, in this case nginx.conf file data will show.
```

```
kubectl delete pods mypod1
```

```
kubectl get pods
```

```
vi replica.yaml
```

```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replicaset
  labels:
    app: nginx
    tier: frontend
spec:
  replicas: 3   # modify replicas according to your case
  selector:
    matchLabels:
      app: nginx
      tier: frontend
  template:
    metadata:
      labels:
        app: nginx
        tier: frontend
    spec:
      containers:
      - name: nginx
        image: nginx:mainline-alpine3.18-perl
```

\

```
kubectl get pods
```

```
kubectl apply -f replica.yaml
```

```
kubectl get pods
```

\

Now changing replicas from 3 to 2

```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replicaset
  labels:
    app: nginx
    tier: frontend
spec:
  replicas: 2   # modify replicas according to your case
  selector:
    matchLabels:
      app: nginx
      tier: frontend
  template:
    metadata:
      labels:
        app: nginx
        tier: frontend
    spec:
      containers:
      - name: nginx
        image: nginx:mainline-alpine3.18-perl
```

```
kubectl get pods
```

\

```
kubectl delete pods <pod name>
```

Or

```
kubectl delete pods --all      
```

```
kubectl delete rs nginx-replicaset      ---> To delete replicaset pods
```

\

\

### **NGINX webapp to outside world**

To get public IP

```
curl -s https://ipinfo.io/ip
```

output can be as: 159.203.160.39

```
vi nginxinternet.yaml
```

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3  # Number of Nginx pods
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
---
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  type: LoadBalancer  # Exposes service to the internet
  ports:
  - protocol: TCP
    port: 80  # External port
    targetPort: 80  # Nginx container port
```

\

```
kubectl apply -f nginxinternet.yaml
```

```
kubectl get deployment
```

```
kubectl get pods
```

```
kubectl get svc nginx-service
```

output:

```
NAME            TYPE           CLUSTER-IP     EXTERNAL-IP      PORT(S)        AGE
nginx-service   LoadBalancer   10.104.45.80   159.203.160.39   80:31248/TCP   9m19s
```

The above will work only if you have load balancer created. so, for me it's not working.

\

\

So, I have only option to check if it's working internally

```
kubectl exec <nginx-pod-name> -- sh -c 'echo "Welcome to fresco nginx pod" > /usr/share/nginx/html/index.html'
```

```
kubectl exec -it nginx-pod-name -- /bin/sh -c "echo 'Welcome to fresco nginx pod' > /usr/share/nginx/html/index.html"
```

This command gives output as below

```
kubectl exec -it nginx-pod-name -- cat /usr/share/nginx/html/index.html
```

```
Welcome to fresco nginx pod
```


---

### **ConfigMap & Secret commands**<!-- {"collapsed":true} -->

```
vi secret.yaml
```

```
apiVersion: v1
 kind: Secret
 metadata:
 name: mysecret-manifest
 type: Opaque
 data:
 username: YW5zaHVsY2hhdWhhbg==
 password: VGVzdGt1VybmV0ZXMxMjM0NQ==
```

```
kubectl get secrets
```

```
kubectl describe secrets <secret name>
```

Same for ConfigMaps

```c
kubectl get configmap
kubectl describe configmap <config name>
```

\

<mark style="background-color:#FFF7CB;">**Examples how to use ConfigMaps & secrets by using environment variables:**<!-- {"backgroundCycleColor":"3"} --></mark>

\

config file

```
vi example-configMap.yaml
```

```
apiVersion: v1
kind: ConfigMap
metadata:
  name: player-pro-demo
data:
  # property-like keys; each key maps to a simple value
  player_lives: "5"
  properties_file_name: "user-interface.properties"

  # file-like keys
  base.properties: |
    enemy.types=aliens,monsters
    player.maximum-lives=10   
  user-interface.properties: |
    color.good=purple
    color.bad=yellow
    allow.textmode=true  
```

\

```
kubectl apply -f example-configMap.yaml
```

```
kubectl get configmaps
```

```
kubectl describe configmap player-pro-demo
```

\

\

Secret file

```
vi example-secret.yaml
```

```
apiVersion: v1
kind: Secret
metadata:
  name: example-secret
type: Opaque
stringData:
  username: YWRtaW4=
  password: YWRtaW5wYXNzd29yZA==
```

\

```
kubectl apply -f example-secret.yaml
```

```
kubectl get secrets
```

```
kubectl describe secrets example-secret
```

\

\

POD yaml file where we use configmap & secrets environment variables

```
vi pod1-env.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: pod-env-demo
spec:
  containers:
    - name: configmap-demo
      image: alpine
      command: ["sleep", "3600"]
      env:
        # Define the environment variable
        - name: PLAYER_LIVES
          valueFrom:
            configMapKeyRef:
              name: player-pro-demo  # The ConfigMap this value comes from.
              key: player_lives # The key to fetch.
        - name: PROPERTIES_FILE_NAME
          valueFrom:
            configMapKeyRef:
              name: player-pro-demo
              key: properties_file_name
        - name: SECRET_USERNAME
          valueFrom:
            secretKeyRef:
              name: example-secret
              key: username
        - name: SECRET_PASSWORD
          valueFrom:
            secretKeyRef:
              name: example-secret
              key: password
```

\

```
kubectl apply -f pod1-env.yaml
```

```
kubectl get pods
```

\

entering inside the POD

```
kubectl exec pod-env-demo -it -- sh
```

```
ls
echo $PLAYER_LIVES
echo $PROPERTIES_FILE_NAME
echo $SECRET_USERNAME
printenv                   --> This is to print all environment variables
exit                       --> To exit from POD
```

\

### **ConfigMaps using mount volumes**<!-- {"collapsed":true} -->

Here we are not going to use environment variables, but we will use the mount volume option.

\

config file

```
vi example-configMap.yaml
```

```
apiVersion: v1
kind: ConfigMap
metadata:
  name: player-pro-demo
data:
  # property-like keys; each key maps to a simple value
  player_lives: "5"
  properties_file_name: "user-interface.properties"

  # file-like keys
  base.properties: |
    enemy.types=aliens,monsters
    player.maximum-lives=10   
  user-interface.properties: |
    color.good=purple
    color.bad=yellow
    allow.textmode=true  
```

\

```
kubectl apply -f example-configMap.yaml
```

```
kubectl get configmaps
```

```
kubectl describe configmap player-pro-demo
```

\

Secret file

```
vi example-secret.yaml
```

```
apiVersion: v1
kind: Secret
metadata:
  name: example-secret
type: Opaque
stringData:
  username: YWRtaW4=
  password: YWRtaW5wYXNzd29yZA==
```

\

```
kubectl apply -f example-secret.yaml
```

```
kubectl get secrets
```

```
kubectl describe secrets example-secret
```

\

Volume mount file

```
vi configmap-vol-demo.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: configmap-vol-demo
spec:
  containers:
    - name: configmap-vol-demo
      image: alpine
      command: ["sleep", "3600"]
      volumeMounts:
      - name: player-map
        mountPath: /etc/config/configMap
      - name: player-secret
        mountPath: /etc/config/secret
  volumes:
    # You set volumes at the Pod level, then mount them into containers inside that Pod
    - name: player-map
      configMap:
        # Provide the name of the ConfigMap you want to mount.
        name: player-pro-demo
    - name: player-secret
      secret:
        secretName: example-secret
```

\

```
kubectl apply -f configmap-vol-demo.yaml
```

```
kubectl get pods
```

\

To enter into POD

```
kubectl exec configmap-vol-demo -it -- sh
```

\

The mount paths we used here is /etc/config/configMap , /etc/config/secret

```
cd /etc/config/configMap
ls
cat user-interface.properties    --> we will get below 3 env values info
color.good=purple
color.bad=yellow
allow.textmode=true
```

\

\


---

### **Simple way of using ConfigMaps using POSIX**<!-- {"collapsed":true} -->

Here only difference with POSIX is that we are not defining each and every env variable separately but we are using **envFrom**. 

\

configmap file

```
vi example-posix-configmap.yaml
```

```
apiVersion: v1
kind: ConfigMap
metadata:
  name: player-posix-demo
data:
  PLAYER_LIVES: "5"
  PROPERTIES_FILE_NAME: "user-interface.properties"
  BASE_PROPERTIES: "Template1"
  USER_INTERFACE_PROPERTIES: "Dark"
```

```c
kubectl get configmap
```

```
kubectl describe configmap player-posix-demo
```

\

POD file

```
vi configmap-posix-pod.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: configmap-posix-demo
spec:
  containers:
    - name: configmap-posix
      image: anshuldevops/kubernetes-web:1.10.6
      ports:
        - containerPort: 8080
      envFrom:
        - configMapRef:
            name: player-posix-demo
```

```
kubectl apply -f configmap-posix-pod.yaml
```

```
kubectl get pods
```

```
kubectl describe pod configmap-posix-demo
```

```
kubectl exec configmap-posix-demo -it -- /bin/bash
```

```
ll
or
ls    --> inside POD
printenv
exit
```

\


---

### **Creating NGINX POD using configmap & secrets**

Update packages

```
sudo apt-get update
```

Installing Apache

```
apt install apache2-utils
```

To create a ht access file (user & psw creating)

```
htpasswd -c .htpasswd user
New password:
Re-type new password:
Adding password for user user
```

```
ls -a    --> to see htpassword file
```

\

**creating a secret file**

```
kubectl create secret generic nginx-htpasswd --from-file .htpasswd
```

```
kubectl get secrets
```

```
kubectl describe secrets nginx-htpasswd
```

\

since we created secret, so now we can delete .htpasswd file from server.

```
rm -rf .htpasswd
```

\

**Now creating configmap** 

```
vi nginx.conf
```

```
user nginx;
worker_processes auto;

error_log /var/log/nginx/error.log notice;
pid /var/run/nginx.pid;

events
{
  worker_connections 1024;
}

http
{
  server
  {
    listen 80 default_server;
    listen [::]:80 default_server;
    server_name localhost;

    location /
    {
      root /usr/share/nginx/html;
      index index.html index.htm;
    }

    auth_basic "Secure Site";
    auth_basic_user_file conf/.htpasswd;
  }
}
```

\

```c
kubectl create configmap nginx-config-file --from-file nginx.conf
```

```
kubectl get configmaps
```

```
kubectl describe configmaps nginx-config-file
```

\

**Now creating a POD**

```
vi nginx-pod.yaml
```

```
apiVersion: v2
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
    - name: nginx-container
      image: 'nginx:1.19.1'
      ports:
        - containerPort: 80
      volumeMounts:
        - name: nginx-config-volume
          mountPath: /etc/nginx
        - name: htpasswd-volume
          mountPath: /etc/nginx/conf
  volumes:
    - name: nginx-config-volume
      configMap:
        name: nginx-config-file
    - name: htpasswd-volume
      secret:
        secretName: nginx-htpasswd

apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: nginx-container
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

\

\

```
kubectl apply -f nginx-pod.yaml
```

```
kubectl get pods
```

```
kubectl get pods -o wide
```

\

```
kubectl port-forward nginx-pod 8080:80            --> this may require
```

```
curl -u user:password123 10.244.0.20           --for me this is not working
```

or 

```
curl http://localhost:8080
```

```
output     
curl: (3) URL rejected: Port number was not a decimal number between 0 and 65535
<html>
<head><title>401 Authorization Required</title></head>
<body>
<center><h1>401 Authorization Required</h1></center>
<hr><center>nginx/1.19.1</center>
</body>
</html>
```

\