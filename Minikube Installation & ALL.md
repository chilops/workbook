---
title: Minikube Installation & ALL
uuid: 1a951a6e-feff-11ef-b328-05c51be8b43a
version: 3388
created: '2025-03-12T10:31:48+05:30'
---

### **Digital ocean referral link $200**<!-- {"collapsed":true} -->

[DigitalOcean \| Cloud Infrastructure for Developers](https://www.digitalocean.com/?refcode=98ed549bfab5) 

\

1. Enter any one of the below codes to get extra credit:

- `CodeAnywhere10`

- `LOWENDBOX`

- `CODEANYWHERE`

- `DOPRODUCT15`

- `DO10`

- `ALLSSD10`

- `WP10`

- `DROPLET10`

- `BITNAMI`

- `DEPLOY10`

- `ACTIVATE10`

- `DONEWS`

- `FRANKFURT`

From 1st step, you will get your first $100 credit and by using additional promo codes you can get up to $135 of total credits.

Note: Some codes only give more credit on higher plans.

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
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
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
or
docker --version
```

\

**Step2: \*\*\*\*\*\*\*\*\*\* Install KubeCtl \*\*\*\*\*\*\*\*\*\***

\

1\. Download the latest release

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

2\. Install kubectl

```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

3\. Test to ensure the version you installed is up-to-date

```
kubectl version --client
```

\

\

**Step3: \*\*\*\*\*\*\*\*\*\* Install MiniKube \*\*\*\*\*\*\*\*\*\***

\

1\. Download Binay

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```

```
chmod +x minikube-linux-amd64
```

\

2\. Install Minikube

```
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

\
3\. Verify Installation

```
minikube version
```

\
4\. Start Kubernetes Cluster

```
sudo apt install conntrack
```

```c
minikube start --network-plugin=cni --cni=calico --force      --> to start with calico network

minikube start --driver=docker --force
```

\

```
eval $(minikube docker-env)
or
eval $(minikube -p minikube docker-env)
```

\

**Command to check if cluster is running:**

```
kubectl config view
```

```
kubectl cluster-info
```

```
kubectl get nodes
```

\

To check if calico network pods are running or not

```
kubectl get pods -n kube-system | grep calico
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


---

### **Minikube restarting once a server rebooted**<!-- {"collapsed":true} -->

```
minikube start --network-plugin=cni --cni=calico --force 
or
minikube start --force
or
minikube start
```

```
minikube status
```

```
kubectl get nodes
```

```
kubectl config view
```

```
kubectl cluster-info
```

```
kubectl get pods -n kube-system | grep calico
```

### **Simple Deployment**<!-- {"collapsed":true} -->

**Creating simple deployment:**

```
kubectl create deployment hello-pod1 --image=k8s.gcr.io/echoserver:1.10
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
kubectl expose deployment hello-pod1 --type=LoadBalancer --port=8080 
```

\

To check if service created:

```
kubectl get service
```

\

To get the URL access

```
minikube service hello-pod1
```

\

To delete the service

```
kubectl delete service hello-pod1
```

\

To delete the deployment. (All PODS associated under deployment will be deleted.)

```
kubectl delete deployment hello-pod1
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
kubectl delete namespace mynamespace
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

### **NGINX webapp to outside world**<!-- {"collapsed":true} -->

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
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 1  # Number of Nginx pods
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
  externalIPs:
   - 138.197.226.199
```

\

```
kubectl apply -f nginxinternet.yaml
```

```
kubectl get all
```

or

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

or

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

or

```
kubectl exec -it <pod-name> -- curl http://localhost:80
```

or

```
minikube service nginx-service --url
```

http://192.168.49.2:32042

```
curl http://192.168.49.2:32042
or
curl http://159.223.131.186:80
```

Welcome to fresco nginx pod


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

### **Creating NGINX POD using configmap & secrets**<!-- {"collapsed":true} -->

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


---

### **Resource Limits & Request Limits**<!-- {"collapsed":true} -->

**Request Limits**

```
vi request_limit.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: frontend-1
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-2
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-3
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-4
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
```

\

To check CPU usage

```
top
1
```

\

```
kubectl apply -f request_limit.yaml
```

```
kubectl get pods
```

\

Updating my yaml file with CPU 750 for 3, 4 PODS

```
vi request_limit.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: frontend-1
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-2
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-3
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "750m"
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-4
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "750m"
```

\

Gets below error as we don't have enough CPU resources.

```
kubectl apply -f request_limit.yaml
```

![](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/34032edf-ce09-486f-b489-b06743bf0233.png) [^1]

\

Deleting PODS now.

```
kubectl delete -f request_limit.yaml
```

\

Now trying to create PODS to see if we can create PODS with high CPU on 3,4 PODS.

```
kubectl apply -f request_limit.yaml
```

\

1st n 2nd PODS are created but 3rd, 4th PODS are pending as resources are not available

```
kubectl get pods -o wide
```

![a6de82b4-0225-4e7f-8ea6-6bf374cfbea9.png|1146.1112060546875](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/a6de82b4-0225-4e7f-8ea6-6bf374cfbea9.png) [^2]

\

Delete the PODS:

```
kubectl delete -f request_limit.yaml
```

\

**Resource Limits:**

```
vi resource_limits.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: frontend-limit
spec:
  containers:
  - name: app
    image: alpine
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
```

```
kubectl apply -f resource_limits.yaml
```

```
kubectl get pods -o wide
```

\

deleting POD

```
kubectl delete pod frontend-limit
```

\


---

### **Liveness Probe, StartUp Probe, Readiness Probe - K8s Monitoring**<!-- {"collapsed":true} -->

Liveness probe helps user to improve & customized this container monitoring mechanism.

\

Users can execute two types of Liveness probes - RUN Command in Container, Periodic HTTP Health Check.

\

![8c0d46fb-2c61-4691-a117-369057b7360c.png|840.1041870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/8c0d46fb-2c61-4691-a117-369057b7360c.png) [^3]

\

![df757c0d-9ef7-4d5a-9d52-35bc1ee45117.png|832.1065063476562](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/df757c0d-9ef7-4d5a-9d52-35bc1ee45117.png) [^4]

\

\

\

![4ceb24fe-c415-4663-ac6f-f4c15c7ca43e.png|739.9884643554688](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/4ceb24fe-c415-4663-ac6f-f4c15c7ca43e.png) [^5]

![95d75f9e-dd5d-48d6-adbe-0ec765622107.png|811.1111450195312](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/95d75f9e-dd5d-48d6-adbe-0ec765622107.png) [^6]

![7744cec5-3791-45a4-a7ae-13cea6a85d8b.png|811.9907836914062](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/7744cec5-3791-45a4-a7ae-13cea6a85d8b.png) [^7]

![38d65a93-c712-4525-bd79-2fb1825b4887.png|841.1111450195312](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/38d65a93-c712-4525-bd79-2fb1825b4887.png) [^8]

\

### **Self-Healing PODS in kubernetes (POD restart policies)**<!-- {"collapsed":true} -->

\

```
vi podrestrart.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: restart-always-pod
spec:
  restartPolicy: Always
  containers:
    - name: app
      image: alpine
      command: ["sleep", "20"]

---
apiVersion: v1
kind: Pod
metadata:
  name: onfailure-always-pod
spec:
  restartPolicy: OnFailure
  containers:
    - name: app
      image: alpine
      command: ["sleep", "20"]

---
apiVersion: v1
kind: Pod
metadata:
  name: never-always-pod
spec:
  restartPolicy: Never
  containers:
    - name: app
      image: alpine
      command: ["sleep", "20"]
```


---

### **Multi-container**<!-- {"collapsed":true} -->

```
vi multi-container.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: two-containers
spec:
  restartPolicy: OnFailure
  containers:
    - name: nginx-container
      image: nginx
      volumeMounts:
        - name: shared-data
          mountPath: /usr/share/nginx/html
    - name: debian-container
      image: debian
      volumeMounts:
        - name: shared-data
          mountPath: /pod-data
      command: ["/bin/sh"]
      args: ["-c", "echo Hello from the Secondary container > /pod-data/index.html"]
  volumes:
    - name: shared-data
      emptyDir: {}
```

\

```
kubectl apply -f multi-container.yaml
```

```
kubectl get pods -o wide
kubectl get pods
kubectl dsecribe pod two-containers
curl 10.244.0.31     --> this in not working due to network policies in digital ocean
```


---

### **POD scheduling**<!-- {"collapsed":true} -->

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-nodeselector
spec:
  containers:
    - name: nginx
      image: nginx
  nodeSelector:
    disktype: ssd
---
apiVersion: v1
kind: Pod
metadata:
  name: nginx-nodename
spec:
  containers:
    - name: nginx
      image: nginx
  nodeName: k8s-worder-01
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-app
spec:
  containers:
    - name: app
      image: alpine
      command:
        - sleep
        - '3600'
      resources:
        requests:
          memory: 64Mi
          cpu: 1000m
  nodeSelector:
    disktype: ssd
---
apiVersion: v1
kind: Pod
metadata:
  name: frontend-app-2
spec:
  containers:
    - name: app
      image: alpine
      command:
        - sleep
        - '3600'
      resources:
        requests:
          memory: 64Mi
          cpu: 1000m
```


---

### **DeamonSet**<!-- {"collapsed":true} -->

- **Automatically Run a copy of a Pod on Each Node.**

- **DaemonSet run a Copy of a Pod on New Node as they added to Cluster.**

- **DaemonSets follows normal scheduling Rules around node labels, taints and tolerations.**

- **If pods normally not scheduled on a Node, daemonset will also not create copy of Pod on that node.**

```
vi deamonset.yaml
```

```
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: logging
spec:
  selector:
    matchLabels:
      app: httpd-logging
  template:
    metadata:
      labels:
        app: httpd-logging
    spec:
      containers:
        - name: webserver
          image: httpd
          ports:
            - containerPort: 80
```

```
kubectl apply -f deamonset.yaml
```

```
kubectl get daemonsets
```

```
kubectl get pods
```

\


---

### **Node Affinity & Node Anti-Affinity**<!-- {"collapsed":true} -->

- Node Affinity is used for Pods Allocation on Worker Nodes.

- Not to Schedule Pod on Nodes is achieve via Node Anti-Affinity.

- Anti-Affinity is Opposite of Affinity and NodeSelector Concept.

```c
vi node-affinity.yaml    -- to test this we need to have 3 node cluster
```

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-nodeaffinity
spec:
  containers:
    - name: nginx
      image: nginx
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
          - matchExpressions:
              - key: disktype
                operator: In
                values:
                  - ssd
---
apiVersion: v1
kind: Pod
metadata:
  name: nginx-node-anti-affinity
spec:
  containers:
    - name: nginx
      image: nginx
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
          - matchExpressions:
              - key: disktype
                operator: NotIn
                values:
                  - ssd
```


---

### **Scaling Application - ReplicaSet, Deployment**<!-- {"collapsed":true} -->

**Stateless** - 90% frontend services are stateless applications. Stateless app can scale horizontally (increase POD instances).

**Stateful** - stateful applications saves client data & state of the application, Database is typical example for stateful app. DB filesystems can't be split into multiple instances (can't scale Horizontally). Only vertically we can scale it up (can increase memory and CPU).

\

**ReplicaSet** 

```
vi repicaset.yaml
```

```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: myapp-replicas
  labels:
    app: myapp
    tier: frontend
spec:
  replicas: 3
  selector:
    matchExpressions:
      - {key: tier, operator: In, values: [frontend]}
  template:
    metadata:
      labels:
        app: myapp
        tier: frontend
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
```

\

```
kubectl apply -f repicaset.yaml
```

```
kubectl get replicaset
```

```
kubectl get pods
```

```
kubectl describe rs myapp-replicas
```

\

Now to scale the replicas:

```
kubectl scale --replicas=10 rs/myapp-replicas
```

```
kubectl get pods
```

\

To descale the replicas:

```
kubectl scale --replicas=2 rs/myapp-replicas
```

```
kubectl get pods
```

\

**Deployment -** Deployment is one step higher than ReplicaSet. Push new versions of app in controlled manner.

Rolling upgrade - Upgrade application in zero downtime using deployment. even rollback can be done.

\

```
vi deployments.yaml
```

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: chef-server
  labels:
    app: chef
spec:
  replicas: 3
  selector:
    matchLabels:
      app: chef-server
  template:
    metadata:
      labels:
        app: chef-server
    spec:
      containers:
        - name: chef-server
          image: 'chef/chef:18.7.0'
          ports:
            - containerPort: 8080
          command:
            - /bin/sh
          args:
            - '-c'
            - echo Hello from the Chef container; sleep 3600
        - name: ubuntu
          image: 'ubuntu:18.04'
          ports:
            - containerPort: 8080
          command:
            - /bin/sh
          args:
            - '-c'
            - echo Hello from the Ubantu container; sleep 3600
```

\

```
kubectl apply -f deployments.yaml
```

```
kubectl get deployments
```

```
kubectl get pods
```

```
kubectl describe pod chef-server-84b84764b4-z99ld
```

```
kubectl get pods --show-labels
```

To describe deployment

```
kubectl describe  deployment/chef-server
```

\

Even replicaset under this deployment is running to check.

```
kubectl get rs
```

\

To check rollout deployment status

```
kubectl rollout status deployment/chef-server
```

\

**Rolling Upgrade an application:**

image: 'chef/chef:18.7.0' to 18.7.1

```
kubectl set image deployment/chef-server chef-server=chef/chef:18.7.1
```

command to check status of rolling upgrade

```
kubectl rollout status deployment.apps/chef-server
```

To see the rollout history

```
kubectl rollout history deployment.apps/chef-server
```

![7baa475b-b86b-48fa-8a48-d0aaabc49545.png|890.1041870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/7baa475b-b86b-48fa-8a48-d0aaabc49545.png) [^9]

But in the above output we are not seeing change-cause, to get this...

```c
kubectl set image deployment/chef-server chef-server=chef/chef:18.7.2 --record              -- It is recommended cmd
```

```
kubectl rollout status deployment.apps/chef-server
```

```
kubectl rollout history deployment.apps/chef-server
```

![b576404b-ab77-42db-91bd-e0d17e43e9c9.png|907.1065063476562](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/b576404b-ab77-42db-91bd-e0d17e43e9c9.png) [^10]

```
kubectl get pods
```

```
kubectl describe pods chef-server-f47c64b98-2w2fl
```

![0ab417d4-a5e3-4aaa-8d94-a0f00a851a5c.png|1076.1112060546875](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/0ab417d4-a5e3-4aaa-8d94-a0f00a851a5c.png) [^11]

\

**Now to roll back the app changes we have done till now.**

```
kubectl rollout undo deployment.apps/chef-server
```

```
kubectl rollout status deployment.apps/chef-server
```

```
kubectl rollout history deployment.apps/chef-server
```

```
kubectl get pods
```

```
kubectl describe pods chef-server-855485dc5c-87pqn
```

![9d342765-53fe-4204-8f58-716902a9ed78.png|1063.1019287109375](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/9d342765-53fe-4204-8f58-716902a9ed78.png) [^12]

\

\

**Now if i want to rollback to specific revision:**

```
kubectl rollout history deployment.apps/chef-server
```

```
kubectl rollout undo deployment.apps/chef-server --to-revision=2
```

```
kubectl rollout status deployment.apps/chef-server
```

```
kubectl get pods
```

```
kubectl describe pods chef-server-84b84764b4-pc5rm
```

![2536c3df-de72-4ebf-9a9d-f87760110d1a.png|981.1111450195312](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/2536c3df-de72-4ebf-9a9d-f87760110d1a.png) [^13]

```
kubectl rollout history deployment.apps/chef-server
```

\

**To pause the deployment:** This will pause the rollout of our deployment.

```
kubectl rollout pause deployment.apps/chef-server
```

\

try to rollout upgrade, but it won't happen

```
kubectl set image deployment/chef-server chef-server=chef/chef:18.7.0 --record
```

```
kubectl rollout status deployment.apps/chef-server
kubectl rollout history deployment.apps/chef-server
```

 **To resume the deployment:**

```
kubectl rollout resume deployment.apps/chef-server
```

```
kubectl rollout status deployment.apps/chef-server
```

```
kubectl rollout history deployment.apps/chef-server
```

```
kubectl get pods
```

```
kubectl describe pods chef-server-f47c64b98-mfh6w
```

![19384872-87b4-4a90-b037-cc7ab5ea0354.png|826.9907836914062](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/19384872-87b4-4a90-b037-cc7ab5ea0354.png) [^14]

\

**Scaling the Deployment**

```
kubectl scale deployment.apps/chef-server --replicas=5
```

```
kubectl rollout status deployment.apps/chef-server
```

```
kubectl get pods
```


---

### **K8s services**<!-- {"collapsed":true} -->

```
vi pod.yaml
```

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-server
  labels:
    app: frontend
spec:
  replicas: 3
  selector:
    matchLabels:
      app: frontend
  template:
    metadata:
      labels:
        app: frontend
    spec:
      containers:
        - name: nginx
          image: nginx
          ports:
            - containerPort: 80
```

```
kubectl apply -f pod.yaml
```

```
kubectl get deployments
```

```
kubectl get pods
kubectl get pods -o wide
```

```
kubectl describe deployment nginx-server
```

\

Now creating a service:

```
vi clusterip-svc.yaml
```

```
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  type: ClusterIP
  selector:
    app: frontend
  ports:
    - protocol: TCP
      port: 8080
      targetPort: 80
```

```
kubectl apply -f clusterip-svc.yaml
```

```
kubectl get svc
```

```
kubectl describe svc nginx-service
```

\

Could not resolve host & not able to access this service bcz this is clusterIP service

```
curl nginx-service:8080
```

![e090069b-06fc-4531-a26b-9f3df8645f9f.png|584.9884643554688](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/e090069b-06fc-4531-a26b-9f3df8645f9f.png) [^15]

\

```
vi pod-svc.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: pod-svc-test
spec:
  containers:
    - name: busybox
      image: busybox:latest
      command:
        - sleep
        - '3600'
```

```
kubectl apply -f pod-svc.yaml
```

\

```
kubectl exec pod-svc-test -- wget -qO- nginx-service:8080
```

The above output tells it allows only within the k8s cluster.

\

**Now will check how NodePort will work:**

NodePort service means i am able to access the service from outside kubernetes network.

\

```
vi nodeport-svc.yaml
```

```
apiVersion: v1
kind: Service
metadata:
  name: nginx-service-nodeport
spec:
  type: NodePort 
  selector:
    app: frontend
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
      nodePort: 30099
```

```
kubectl apply -f nodeport-svc.yaml
```

```
kubectl get svc
```

```
kubectl describe svc nginx-service-nodeport
```

```
minikube service nginx-service-nodeport --url
```

```
curl http://192.168.49.2:30099
```

```
curl localhost:30099        --This is not working for me
```

\

### **Ingress-controller**<!-- {"collapsed":true} -->

```
vi nginx-deployment.yaml
```

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-official-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx-official
  template:
    metadata:
      labels:
        app: nginx-official
    spec:
      containers:
        - name: nginx-official
          image: 'nginx:latest'
          ports:
            - containerPort: 8080
```

```
kubectl apply -f nginx-deployment.yaml
```

```
kubectl get deployments
kubectl describe deployments nginx-official-deployment
```

```
kubectl get pods
```

\

nginx service

```
vi nginx-svc.yaml
```

```
apiVersion: v1
kind: Service
metadata:
  name: nginx-official-service
spec:
  type: NodePort
  ports:
    - protocol: TCP
      port: 80
      nodePort: 31303
  selector:
    app: nginx-official
```

```
kubectl apply -f nginx-svc.yaml
```

```
kubectl get svc
```

\

This is custom image nginx deployment

```
vi magical-nginx-deployment.yaml
```

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: magicalnginx-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: magical-nginx
  template:
    metadata:
      labels:
        app: magical-nginx
    spec:
      containers:
        - name: magical-nginx
          image: 'anshuldevops/magicalnginx:latest'
          ports:
            - name: nginx-port
              containerPort: 3000
```

```
kubectl apply -f magical-nginx-deployment.yaml
```

\

Now creating magical nginx service

```
vi magical-nginx-svc.yaml
```

```
apiVersion: v1
kind: Service
metadata:
  name: magical-nginx
spec:
  type: NodePort
  ports:
    - protocol: TCP
      port: 80
      nodePort: 31304
      name: http
  selector:
    app: magical-nginx
```

```
kubectl apply -f magical-nginx-svc.yaml
```

```
kubectl get svc
```

\

to get the url

```
minikube service magical-nginx --url
```

```
curl http://192.168.49.2:31304
```

\

Now ingress comes in picture

```
vi IngressController.yaml
```

```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-rules
spec:
  rules:
  - host: nginx-official.example.com
    http:
      paths:
      - path: /
        pathType: Exact
        backend:
          service:
            name: nginx-official-service
            port:
              number: 80
  - host: magical-nginx.example.com
    http:
      paths:
      - path: /
        pathType: Exact
        backend:
          service:
            name: magical-nginx
            port:
              number: 80
```

```
kubectl apply -f IngressController.yaml
```

```
kubectl get ingress
```

```
kubectl describe ingress nginx-rules
```

```
minikube ip
```

```
curl 192.168.49.2 -H 'Host: nginx-official.example.com'            -- this is not working for me
```


---

### **hostpath volumes &** <!-- {"collapsed":true} -->

host path

```
vi hostpath.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: hostpath-pod
spec:
  volumes:
  - name: hostpath-vol
    hostPath:
      path: /var/tmp
  containers:
  - name: hostpath-pod
    image: 'k8s.gcr.io/busybox'
    command: ["/bin/sh", "-c", "echo Hello Team, This is Sample File for HostVolume - $(date) >> /output/output.txt"]
    volumeMounts:
    - name: hostpath-vol
      mountPath: /output
```

```
kubectl apply -f hostpath.yaml
```

```
kubectl get pods
```

```
cd /var/tmp/
```

```
cat /var/tmp/output.txt
```

\

```
kubectl delete hostpath-pod
```

now data present will exist

```
cat /var/tmp/output.txt
```

\

emptydir

```
vi empty.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: redis-emptydir
spec:
  containers:
  - name: redis
    image: redis
    volumeMounts:
    - name: redis-storage
      mountPath: /data/redis
  volumes:
  - name: redis-storage
    emptyDir: {}
```

```
kubectl apply -f empty.yaml
kubectl get pods
```

if you delete this pod the data present inside POD is deleted.

\

\

**Persistent Volumes**

**creating a storage class**

```
vi local_sc.yaml
```

```
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: local-storage
provisioner: kubernetes.io/no-provisioner
volumeBindingMode: WaitForFirstConsumer
allowVolumeExpansion: true
```

```
kubectl apply -f local_sc.yaml
```

```
kubectl get storageclass
```

```
kubectl describe storageclass local-storage
```

\

**Now we need to create persistent volume**

```
vi persistent-vol.yaml
```

```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: my-persistnt-vol
spec:
  storageClassName: local-storage
  persistentVolumeReclaimPolicy: Recycle
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: /var/tmp
```

```
kubectl apply -f persistent-vol.yaml
```

```
kubectl get persistentvolume
kubectl get pv -o wide
```

```
kubectl describe persistentvolume my-persistnt-vol
```

\

**Now creating PVC**

```
vi my-pvc.yaml
```

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  storageClassName: local-storage
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 100Mi
```

```
kubectl apply -f my-pvc.yaml
```

```
kubectl get pvc
kubectl describe pvc my-pvc
```

```
kubectl get pvc -o wide
```

\

**Now creating a POD**

```
vi my-pv-pod.yaml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: my-pv-pod
spec:
  restartPolicy: Never
  containers:
    - name: busybox
      image: busybox
      command: ["sh", "-c", "echo Hello Team, This is Persistnent Volume Claim >> /output/success.txt"]
      volumeMounts:
      - mountPath: /output
        name: my-pv
  volumes:
    - name: my-pv
      persistentVolumeClaim:
        claimName: my-pvc
```

```
kubectl apply -f my-pv-pod.yaml
```

```
kubectl get pods
```

**now get the status of both PV & PVC**

```
kubectl get pvc -o wide
kubectl get pv -o wide
```


---

### **HELM Installation**<!-- {"collapsed":true} -->

official site - [Helm](https://helm.sh/) 

helm installing link - [Helm \| Installing Helm](https://helm.sh/docs/intro/install/) 

\

There are two ways to install HELM

**1st way:**

Get the binary link

![451cbf5a-4234-4579-a9f0-958dc2f40eba.png|746.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/451cbf5a-4234-4579-a9f0-958dc2f40eba.png) [^16]

\

Copy the link

![3ddaef1e-6bd2-4570-9902-d338cdb9e7d6.png|799.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/3ddaef1e-6bd2-4570-9902-d338cdb9e7d6.png) [^17]

\

download

```
wget https://get.helm.sh/helm-v3.17.2-linux-amd64.tar.gz
```

Untar

```
ls
tar -zxvf helm-v3.17.2-linux-amd64.tar.gz
ls
```

Move to local bin

```
mv linux-amd64/helm /usr/local/bin/helm
```

\

Check if helm installed or not

```
helm help
helm version
```

\

**2nd Way:**

![c0acd251-215b-4d51-98c2-c5ea0684fb0d.png|859.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/c0acd251-215b-4d51-98c2-c5ea0684fb0d.png) [^18]


---

### **Working with HELM Repos**<!-- {"collapsed":true} -->

Gives list of repos available

```
helm repo list
```

Adding repo

```
helm repo add bitnami https://charts.bitnami.com/bitnami
```

```
helm repo list
```

\

We can add multiple repos as per our requirement.

```
helm repo add brigade https://brigadecore.github.io/charts
```

```
helm repo list
```

To remove repo

```
helm repo remove brigade
```

```
helm repo list
```

\

To check how many charts are available in repository (**search**)

```
helm search repo mysql    ---search command to check how many MYSQL charts are available
```

```
helm search repo database
helm search repo mysql --versions
```

\

```
helm search hub nginx    --- this will search in aritifacthub.io and get all details.
helm search hub nginx | wc -l      ---total repos count of nginx
```


---

### **Execute services using HELM**<!-- {"collapsed":true} -->

```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo list
```

\

**Installing redis chart (with this single chart we are going to run** PODS, services etc.

```
helm search repo redis --versions
```

```
helm install my-redis bitnami/redis --version 20.11.2        (copy the output content)
```

```
To get your password run:

    export REDIS_PASSWORD=$(kubectl get secret --namespace default my-redis -o jsonpath="{.data.redis-password}" | base64 -d)

To connect to your Redis&reg; server:

1. Run a Redis&reg; pod that you can use as a client:

   kubectl run --namespace default redis-client --restart='Never'  --env REDIS_PASSWORD=$REDIS_PASSWORD  --image docker.io/bitnami/redis:7.4.2-debian-12-r6 --command -- sleep infinity

   Use the following command to attach to the pod:

   kubectl exec --tty -i redis-client \
   --namespace default -- bash

2. Connect using the Redis&reg; CLI:
   REDISCLI_AUTH="$REDIS_PASSWORD" redis-cli -h my-redis-master
   REDISCLI_AUTH="$REDIS_PASSWORD" redis-cli -h my-redis-replicas

To connect to your database from outside the cluster execute the following commands:

    kubectl port-forward --namespace default svc/my-redis-master 6379:6379 &
    REDISCLI_AUTH="$REDIS_PASSWORD" redis-cli -h 127.0.0.1 -p 6379


WARNING: There are "resources" sections in the chart not set. Using "resourcesPreset" is not recommended for production. For production installations, please set the following values according to your workload needs:
  - replica.resources
  - master.resources
+info https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/
```

\

\--download this package's content using this command

```
helm pull oci://registry-1.docker.io/bitnamicharts/redis --version 20.11.2    
```

\

With single helm command PODS, services etc are running.

```
kubectl get pods
kubectl get all
```

\

Using above copied content and checking if its working or not.

![1a23e454-044b-4514-8cd2-2ba9df7a38c4.png|985.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/1a23e454-044b-4514-8cd2-2ba9df7a38c4.png) [^19]

\

To check the deployments.

```
helm list
```

\

### **How to reuse deployment naming**<!-- {"collapsed":true} -->

Is it really possible to reuse the deployment name in the helm? -- Yes, we can, but only in different namespace its possible but not in same namespace

```
helm list
```

```
helm install my-redis bitnami/redis --version 20.11.3
```

output

```
Error: INSTALLATION FAILED: cannot re-use a name that is still in use
```

\

create a different namespace

```
kubectl create namespace redis
kubectl get namespaces
or 
kubectl get ns
```

\

deploying in redis namespace

```
helm install my-redis -n redis bitnami/redis --version 20.11.2
```

```
helm list --namespace redis
or
helm list --all-namespaces
or
helm list -A
```

\

to get the status & details

```
helm status my-redis
helm status my-redis -n redis
```

\

To delete deployment

```
helm delete my-redis
helm delete my-redis -n redis
helm list -A
kubectl get pods -A
```

\

\


---

### **Providing custom values to helm charts**<!-- {"collapsed":true} -->

Sometimes we need to supply some dynamic values while executing some applications.

Ex: mysql DB or MariaDB. 

\

now checking for MariaDB repo in helm repo

[mariadb 20.4.2 · bitnami/bitnami](https://artifacthub.io/packages/helm/bitnami/mariadb) 

\

![09420129-f189-4c9c-9c42-222d26c4c0ff.png|911.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/09420129-f189-4c9c-9c42-222d26c4c0ff.png) [^20]

```
helm install my-mariadb bitnami/mariadb --version 20.4.1
```

```
kubectl get pods
helm list -A
```

```
helm status my-mariadb  
```

to get the password 

```
kubectl get secret --namespace default my-mariadb -o jsonpath="{.data.mariadb-root-password}" | base64 -d
```

```
kubectl run my-mariadb-client --rm --tty -i --restart='Never' --image  docker.io/bitnami/mariadb:11.4.5-debian-12-r9 --namespace default --command -- bash
```

\

inside POD

```
mysql -h my-mariadb.default.svc.cluster.local -uroot -p my_database
```

enter the password  MkkVkXpegz  (psw may vary if you use different versions)

```
show tables;
```

\

**Till now we haven't used custom values....**

creating a new namespace and calling it as database

```
kubectl create namespace database
```

```
kubectl get ns
```

\

```
vi custom-values.yaml
```

```
auth:
  database: "helm_training"
  password: "Test123456"
  username: "custom_usr"
  rootPassword: "Root123456"
```

\

```
helm install --values custom-values.yaml my-mariadb -n database bitnami/mariadb --version 20.4.1
```

```
kubectl get pods -n database
helm list -A
```

```
helm status my-mariadb -n database 
```

from the above output you can see below command and use it.

```
kubectl run my-mariadb-client --rm --tty -i --restart='Never' --image  docker.io/bitnami/mariadb:10.6.11-debian-11-r0 --namespace database --command -- bash
```

\

```
mysql -h my-mariadb.database.svc.cluster.local -uroot -p helm_training
```

use the password which we had given earlier from custom-values.yaml file to access MariaDB.

\

\

\


---

### **Upgrade services using HELM**<!-- {"collapsed":true} -->

Upgrade MariaDB which we used in earlier class

```
helm list -A
```

```
helm status my-mariadb -n database
```

```
helm repo update            ---To update repos
```

\

In this upgrade i am just updating my passwords in yaml file

```
vi custom-values.yaml
```

```
auth:
  database: "helm_training"
  password: "Test1234"
  username: "custom_usr"
  rootPassword: "Root1234"
```

\

```
helm upgrade -n database --values custom-values.yaml my-mariadb bitnami/mariadb --version 20.4.1
```

```
kubectl get pods -n database
```

```c
helm list -A                    --revision got changed here as 2
```

\

\

Now upgrading version

```
helm upgrade -n database --values custom-values.yaml my-mariadb bitnami/mariadb --version 20.4.2
```

```
kubectl get pods -n database
```

```
helm list -A                    --revision got changed here as 3
```


---

### **How Helm maintains Release Records**<!-- {"collapsed":true} -->

It will store previous versions of secrets

```
kubectl get secrets -n database
```

to uninstall 

```
helm uninstall my-mariadb
```

to uninstall by keeping previous version

```
helm uninstall my-mariadb -n database --keep-history
```

```
kubectl get secrets -n database
```


---

### **Validate resources before deployment** (this we can call it as HELM dry run)<!-- {"collapsed":true} -->

This command will execute 1st 4 stages of deployment workflow, but it will not execute the 5th flow where k8s resources actually deployed in the Kubernetes.

```
helm install -n database --values custom-values.yaml my-mariadb bitnami/mariadb --version 20.4.1 --dry-run 
```

It shows pending Install

![d9194497-5bd7-4be8-b05a-2a84e7b81b8d.png|585](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/d9194497-5bd7-4be8-b05a-2a84e7b81b8d.png) [^21]

\

- It will load the chart.

- It will pass the yaml

- It will generate the yaml

- It will validate the yaml against the Kubernetes

- But it will not deploy them on the Kubernetes cluster.

 You will get very long output.

```
helm install -n database --values custom-values.yaml my-mariadb bitnami/mariadb --version 20.4.1 --dry-run        
```

\

### **Generate K8s deployable YAML using HELM**<!-- {"collapsed":true} -->

If we want to generate Kubernetes deployable YAML’s using HELM, is it possible or not… YES, we can...

\

It generates all YAML files

```
helm template -n database --values custom-values.yaml my-mariadb bitnami/mariadb --version 20.4.1
```

\

Few more details about helm deployment releases.

```
kubectl get secrets -n database
```

```
kubectl get secrets -n database sh.helm.release.v1.my-mariadb.v1 -o yaml
```

     

How to get details of Deployed deployment:

```
helm list -A
```

```
helm get notes my-mariadb -n database
```

\

To get user supplied values:

```
helm get values my-mariadb -n database
```

\

I got a requirement where to get the values of revision1 got deployed.

```
helm get values my-mariadb -n database --revision 1
```

\

Now I want to know all values supplied to your deployment.

```
helm get manifest my-mariadb -n database --revision 1
```

\

\

### **Rollback application using HELM**<!-- {"collapsed":true} -->

```
helm list -A
```

```
kubectl get secrets -n database
```

To get the previous versions details

```
helm history my-mariadb -n database   
```

Rolling back to revision1

```
helm rollback my-mariadb 1 -n database 
```

\

```
helm history my-mariadb -n database
```

\

To compare version values

```
helm get values my-mariadb -n database --revision 4
helm get values my-mariadb -n database --revision 3
```

Uninstalling deployment by keeping its history.

```
helm uninstall -n database my-mariadb --keep-history 
```

```
helm list -A
```

```
kubectl get secrets -n database
```

```
helm history my-mariadb -n database
```

\

\

Now to re-install with specific revision

```
helm rollback my-mariadb 3 -n database
```

```
helm history my-mariadb -n database
helm list -A
```

```
kubectl get secrets -n database
```

```
helm get values my-mariadb -n database --revision 5
```

\

### **How we can wait HELM deployment for successful installation**<!-- {"collapsed":true} -->

```
helm list -A
```

Now installing mysql using helm

```
helm install my-mysql bitnami/mysql --version 9.4.4 --wait --timeout 3m      
```

\--- this will help us to wait for the resources to come up with successful status (default wait is 300sec) sometimes pulling images etc will take time, but this is not recommended way...

\

```
kubectl get pods
```

```
helm list -A
```

Now upgrading with wait time

```
helm upgrade  my-mysql bitnami/mysql --version 9.4.5 --wait --timeout 3m
```

```
kubectl get pods
```

```
helm list -A
```

\

Now I am performing wrong upgrade with wrong image, this will come out as its a wrong image & we need to do Ctr+c and this deployment will fail

```
helm upgrade my-mysql bitnami/mysql --version 9.4.2 --set image.pullPolicy="satya" --wait --timeout 3m
```

```
helm list -A
```

```
helm history my-mysql
```

\

Since its wrong upgrade, since we are using **atomic** option, it will roll back to previous version.

```
helm upgrade my-mysql bitnami/mysql --version 9.4.2 --set image.pullPolicy="satya" --atomic
```

```
helm list -A
```

```
helm history my-mysql
```

\


---

### **Create HELM charts**<!-- {"collapsed":true} -->

There are two ways.

1. start writing the helm charts from very scratch, in this case you can create directory, template files, yaml, values etc by our own.

1. create chart with some kind of template and later we can update that template as per our usage. (this is best way)

\

**Going with 2nd way**

created git HELM

![961f6a2f-9c16-427d-800f-06ae9669f11b.png|836.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/961f6a2f-9c16-427d-800f-06ae9669f11b.png) [^22]

\

\

cloning on k8s server

```
git clone https://github.com/chilops/HELM.git
```

![5cd7319d-1f81-42a7-843d-3f588a57254d.png|788.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/5cd7319d-1f81-42a7-843d-3f588a57254d.png) [^23]

\

```
ls
cd HELM
```

```
mkdir create_charts
cd create_charts                         --- Under charts we can create our custom templates
```

![e1a858eb-32a1-4496-9d5d-3bdd54d7c812.png|753](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/e1a858eb-32a1-4496-9d5d-3bdd54d7c812.png) [^24]

\

\

**To Create template with the HELM**

Below command what it does is, Helm will create a basic template for you and that basic template will be driven by the nginx template. **By default, it will take NGINX image**

```
helm create my-first-chart
```

```
ls
cd my-first-chart/
ls
```

![69ec7bd3-e67d-4d8a-b942-59d5757ddfbe.png|772.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/69ec7bd3-e67d-4d8a-b942-59d5757ddfbe.png) [^25]

\

```
cd charts
ls
cd ../templates/
ls
```

![52ff58a0-60d5-448f-9eae-8447b5f650e9.png|867.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/52ff58a0-60d5-448f-9eae-8447b5f650e9.png) [^26]

\

```
cd tests
ls
or
ll
```

![0fb3cb99-d026-4020-a1cc-24a825b0dbe7.png|925.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/0fb3cb99-d026-4020-a1cc-24a825b0dbe7.png) [^27]

\

\

\

\

\

\


---

### **Install custom chart**<!-- {"collapsed":true} -->

```
pwd
```

![400e5744-76cd-42ba-8bfd-d4f5d3cd0af2.png|669](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/400e5744-76cd-42ba-8bfd-d4f5d3cd0af2.png) [^28]

\

to check how many deployments are running now

```
helm list -A
```

\

To deploy my new chart

```
helm install my-deployment my-first-chart/
```

![c4418cd8-7f68-4c0b-8242-eac5b0694344.png|907.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/c4418cd8-7f68-4c0b-8242-eac5b0694344.png) [^29]

\

```
helm list -A
```

```
kubectl get pods             -- by default it will take nginx image/template
```

```
kubectl get all
```

\

chart.yaml contains metadata of your helm charts, where we will mention the application version, type of the application, chart version etc.

\

### **Package your HELM chart**<!-- {"collapsed":true} -->

I made changes in values.yaml file as replicas count as 3 and updated chart.yaml app version as 1.1.0

![](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/55567819-a8d0-4d10-8db3-8540b11f522f.png) [^30]

\

Now packing the helm chart as its modified.

```
helm package my-first-chart/
  or
helm package my-first-chart/ -u        ---use this command if you package has any dependencies(download from other source)
helm package my-first-chart/ -d /root/     ---To save in root location 
ls
```

![](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/f9810e3e-b5b3-428f-94e7-b5b8b191164b.png) [^31]

\

Validating the HELM charts (for errors, information, warnings)

```
helm lint my-first-chart
```

![51887b08-a685-42c7-a87c-d7634696976a.png|780.6666870117188](https://images.amplenote.com/1a951a6e-feff-11ef-b328-05c51be8b43a/51887b08-a685-42c7-a87c-d7634696976a.png) [^32]

\

\

\

[^1]: Containers: \[\] core . Container{
    . . . // 6 identical fields
    EnvFrom: nil,
    Env :
    nil,
    Resources: core . ResourceRequirements {
    Limits: nil,
    Requests: core . ResourceList{
    s"cpu" :
    {i: resource . int64Amount {value: 250, scale: -3), s: "250m", Format: "De
    imalSI"},
    s"cpu" :
    {i: resource . int64Amount {value: 750, scale: -3), s: "750m", Format: "De
    imalSI"},
    s"memory": {i: {. ..), Format: "BinarySI"},
    Claims: nil,
    ResizePolicy: nil,
    RestartPolicy: nil,
    // 13 identical fields

[^2]: root@K8s-Minikube: \~ #
    kubectl get pods -o wide
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    IP
    NODE
    NOMINATED NODE
    READINESS GATES
    frontend-1
    1/1
    Running
    0
    4s
    10 . 244 .0.27
    minikube
    <none>
    <none>
    frontend-2
    1/1
    Running
    0
    As
    10 . 244. 0.26
    minikube
    <none>
    <none>
    frontend-3
    0/1
    Pending
    0
    4s
    <none>
    <none>
    <none>
    <none>
    frontend-4
    0/ 1
    Pending
    0
    4s
    <none>
    <none>
    <none>
    <none>
    root@K8s-Minikube :

[^3]: Liveness Probe
    Liveness via Container Command
    livenessProbe:
    manifest.
    exec:
    command:
    initialDelaySeconds: How long to wait
    -some command here-
    initialDelaySeconds: 5
    before sending a probe after a container
    periodSeconds: 5
    starts.
    periodSeconds: How often a probe will
    be sent.

[^4]: Liveness Probe
    Liveness via HTTP Request
    livenessProbe:
    manifest.
    httpGet:
    path: /health.html
    port: 8080
    timeoutSeconds: How long a
    httpHeaders:
    request can take to respond before
    - name: Custom-Header
    value: Awesome
    it's considered a failure.
    initialDelaySeconds: 3
    periodSeconds: 3
    timeoutSeconds: 1

[^5]: StartUp Probe
    Setting up Liveness probe is very Tricky with Application
    which have Long StartUp Time.
    StartUp probe runs at container StartUp and stop running
    once container success.
    > Once the startup probe has succeeded once, the liveness
    probe takes over to provide a fast response to container
    deadlocks.

[^6]: StartUp Probe
    . -
    - -
    StartUp via HTTP Request manifest.
    1 startupProbe:
    httpGet:
    failure Threshold: When a probe fails,
    path: /health.html
    Kubernetes will try failure Threshold
    port: 8080
    failureThreshold: 30
    times before giving up.
    periodSeconds: 10
    L
    Application will have a maximum of 5
    minutes (30 \* 10 = 300s) to finish its
    startup.

[^7]: Readiness Probe
    Readiness is used to detect if a container is ready to accept
    traffic.
    Sometimes application might need to load large data or
    configuration files during startup, or depend on external
    services after startup.
    NO Traffic will be sent to a pod until container pass the
    Readiness Probe.

[^8]: Readiness Probe
    Readiness Probe manifest.
    readinessProbe:
    exec:
    Configuration for HTTP readiness
    command:
    probes also remains identical to liveness
    - cat
    - /tmp/healthy
    probes.
    initialDelaySeconds: 5
    periodSeconds: 5
    Readiness and liveness probes can be
    used in parallel for the same container.

[^9]: root@Minikube: \~# kubectl rollout history deployment .apps/chef-server
    deployment . apps/chef-server
    REVISION
    CHANGE-CAUSE
    <none>
    WNH
    <none>
    <none>

[^10]: root@Minikube: \~# kubectl rollout history deployment . apps/chef-server
    deployment . apps/chef-server
    REVISION
    CHANGE-CAUSE
    <none>
    <none>
    <none>
    kubectl
    set image deployment/chef-server chef-server=chef/chef : 18.7.2 --record=true

[^11]: root @Minikube: \~# kubectl describe pods chef-server-f47c64698-2w2fl
    Name :
    chef-server-f47c64698-2w2f1
    Namespace :
    default
    Priority:
    0
    Service Account:
    default
    Node :
    minikube/192 . 168 . 49.2
    Start Time :
    Thu, 20 Mar 2025 07:27:09 +0000
    Labels:
    app=chef-server
    pod-template-hash=f47c6498
    Annotations :
    <none>
    Status :
    Running
    IP :
    10 . 244. 0.29
    IPS:
    IP :
    10 . 244.0.29
    Controlled By:
    ReplicaSet/chef-server-f47c64b98
    Containers :
    chef-server:
    Container ID:
    docker: / /42e3176a2ce22590cc1b579fdaf59384103f19586d9a5610808c965c5f
    Image :
    chef/ chef : 18. 7.2
    Image ID:
    docker-pullable: //chef/chef@sha256: 948349f79a53ald2f53dfacb42d0c5fc

[^12]: root@Minikube: \~# kubectl describe pods chef-server-855485dc5c-87pqn
    Name :
    chef-server-855485dc5c-87pqn
    Namespace :
    default
    Priority:
    O
    Service Account :
    default
    Node :
    minikube/192 . 168 . 49.2
    Start Time :
    Thu, 20 Mar 2025 07:36:08 +0000
    Labels :
    app=chef-server
    pod-template-hash=855485dc5c
    Annotations :
    <none>
    Status :
    Running
    IP :
    10 .244 .0 .32
    IPS:
    IP :
    10 .244. 0.32
    Controlled By:
    ReplicaSet/chef-server-855485dc5c
    Containers :
    chef-server :
    Container ID:
    docker : / /118adle88bflecc11440798b32456d80bef7c0e85f1045e0b1233365fabOfdf3
    Image :
    chef/chef : 18 . 7.1
    Image ID:
    docker-pullable: //chef/chef@sha256: 718742e0a2b7c8d8575934ffeb664bde5b97bbd
    Port:
    8080/TCP

[^13]: root@Minikube: \~# kubectl describe pods chef-server-8468476464-pc5rm
    Name :
    chef-server-84684764b4-pc5rm
    Namespace :
    default
    Priority :
    0
    Service Account :
    default
    Node :
    minikube/192 . 168 . 49.2
    Start Time:
    Thu, 20 Mar 2025 07: 41:09 +0000
    Labels :
    app=chef-server
    pod-template-hash=84b84764b4
    Annotations :
    <none>
    Status :
    Running
    IP :
    10 . 244. 0.35
    IPS :
    IP:
    10 . 244. 0.35
    Controlled By:
    ReplicaSet/chef-server-84684764b4
    Containers :
    chef-server:
    Container ID:
    docker : / /d9c975da28ab41c61e28bbb8e 76a89531a0f620768d82175008184f02ad25185
    Image :
    chef/chef : 18 . 7. 0
    Image ID:
    docker-pullable: / /chef/chef@sha256: f103088c54344d7c7e4baac46cf5921485938d

[^14]: root@Minikube : \~# kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    chef-server-f47c64b98-75vsj
    2/2
    Running
    0
    4m24s
    chef-server-f47c64698-gvsr5
    2/2
    Running
    O
    4m18s
    chef-server-f47c64698-mfhow
    2/2
    Running
    O
    37s
    root@Minikube: \~# kubectl describe pods chef-server-f47c64698-mfh6
    Name :
    chef-server-f47c64698-mfh6w
    Namespace :
    default
    Priority :
    O
    Service Account :
    default
    Node :
    minikube/192 . 168 . 49.2
    Start Time:
    Thu, 20 Mar 2025 07:58:26 +0000
    Labels:
    app=chef-server
    pod-template-hash=f47c64b98
    Annotations:
    <none>
    Status :
    Running
    IP:
    10 . 244 .0 . 40
    IPS:
    IP :
    10 . 244 . 0 . 40
    Controlled By:
    ReplicaSet/chef-server-f47c64b98
    Containers:
    chef-server:
    Container ID:
    docker : / /6fd2ac89a93e9b9643880a884653aa4fcf79b
    Image :
    chef/chef : 18 . 7. 2

[^15]: root@Minikube : \~# curl nginx-service : 8080
    curl: (6) Could not resolve host: nginx-service

[^16]: C
    B https://helm.sh/docs/intro/install/
    Update
    No
    ye
    HELM Docs
    Home
    Docs
    Charts
    Blog
    Community
    English v
    V3. 1
    Search . . .
    Docs Home
    From the Binary Releases
    Introduction
    Quickstart Guide
    Every release of Helm provides binary releases for a variety of OSes. These binary versions can be
    Installing Helm
    manually downloaded and installed.
    Using Helm
    Cheat Sheet
    1. Download your desired version
    How - To
    2. Unpack it ( tar - zxvf helm-v3.0.0-linux-amd64. tar. gz )
    3. Find the helm binary in the unpacked directory, and move it to its desired destination ( mv linux-amd64/helm
    Topics
    /usr/local/bin/helm )
    Best Practices

[^17]: & https://github.com/helm/helm/releases
    2 weeks ago
    Helm v3.17.2
    Latest
    mattfarina
    v3.17.2
    O- ccobbbd
    Helm v3.17.2 is a patch release. Users are encouraged to upgrade for the best experience. Users are encouraged to u
    for the best experience.
    Compare
    The community keeps growing, and we'd love to see you there!
    . Join the discussion in Kubernetes Slack:
    o for questions and just to hang out
    o for discussing PRs, code, and bugs
    . Hang out at the Public Developer Call: Thursday, 9:30 Pacific via Zoom
    . Test, debug, and contribute charts: ArtifactHub/packages
    Installation and Upgrading
    Download Helm v3.17.2. The common platform binaries are here:
    . MacOS amd64 (checksum / 3e240238c7a3a10ed37be16615628e94ba5db5957247bb42009bad52f76e9)
    . MacOS arm64 (checksum / b843cebcbebc9eccb 1e43aba9cca7693d32e9f2c4a35344990e367b381933948)
    "Linux amd64 (checksum / 90c28792a1eb5fb0b50028e39ebf826531ebfcf73f599050dbd79bab2f277241)
    Linux arm (checksum / 0b 13ec8580dd549865a2d7cb34146e098049f59500a266db 1bb98f59649eb90a)
    Linux arm64 (checksum / d78d76ec7625a94991887ac049d93f44bd70e48762006945f813c9e 1ed1df7c)

[^18]: C
    https://helm.sh/docs/intro/install/
    Update
    HELM Docs
    Home
    Docs
    Charts
    Blog
    Community
    English v
    V3 . 17.
    Search . . .
    Q
    Docs Home
    From Apt (Debian/Ubuntu)
    Introduction
    Quickstart Guide
    Members of the Helm community have contributed a Helm package for Apt. This package is generally up
    Installing Helm
    to date.
    Using Helm
    Cheat Sheet
    curl https://baltocdn. com/helm/signing. asc \| gpg --dearmor \| sudo tee /usr/share/keyrings/helm.gpg > /dev/null
    How- To
    sudo apt-get install apt-transport-https --yes
    echo "deb \[arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg\] https://baltocdn. com/helm/:
    Topics
    sudo apt-get update
    sudo apt-get install helm
    Best Practices
    Chart Template Guide

[^19]: root@Minikube-helm: \~# export REDIS_PASSWORD=$ (kubectl get secret --namespace default my-redis -o jsonpath=" { . data. redis-pas
    sword}" \| base64 -d)
    root@Minikube-helm: \~# kubectl run --namespace default redis-client --restart='Never'
    --env REDIS PASSWORD=$REDIS PASSWORD
    --image docker . io/bitnami/redis: 7.4.2-debian-12-r6 --command -- sleep infinity
    pod/redis-client created
    root@Minikube-helm: \~ #
    root@Minikube-helm: \~# kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    my-redis-master-0
    1/1
    Running
    0
    10m
    my-redis-replicas-0
    1/1
    Running
    0
    10m
    my-redis-replicas-1
    1/1
    Running
    O
    10m
    my-redis-replicas-2
    1/1
    Running
    9m59s
    OO
    redis-client
    1/1
    Running
    6s
    root@Minikube-helm: \~ #
    root@Minikube-helm: \~ #
    root@Minikube-helm: \~ #
    root@Minikube-helm: \~# kubectl exec --tty -i redis-client \\
    --namespace default -- bash
    I have no name! @redis-client : /$
    I have no name ! @redis-client: /$ REDISCLI AUTH="$REDIS_PASSWORD" redis-cli -h my-redis-master
    my-redis-master : 6379>
    my-redis-master : 6379> SET mykeys "Hello Friends"
    OK
    my-redis-master : 6379> GET mykeys
    "Hello Friends"
    my-redis-master : 6379> exit
    I have no name ! @redis-client : /$
    I have no name ! @redis-client: /$ REDISCLI AUTH="$REDIS_PASSWORD" redis-cli -h my-redis-replicas
    my-redis-replicas : 6379> GET mykeys
    "Hello Friends"
    my-redis-replicas : 6379> exit
    I have no name! @redis-client: /$ exit
    exit
    root @Minikube-helm: \~ #

[^20]: F
    C
    https://artifacthub.io/packages/helm/bitnami/mariadb?modal=install
    O Artifact HUB
    Q mariadb
    X
    DOCS
    STATS
    SIGN UP
    SIGN IN
    < Back to "mariadb" results
    MariaDB
    mariadb
    X
    83
    ...
    mariadb
    Star
    MOM Hel
    MariaDB
    Bitnami Bitnami
    Helm v3
    MariaDB is an open source, community
    aboration with leading tech firms.
    Add repository
    SUBSCR
    helm repo add bitnami https://charts . bitnami . com/bitnami
    Install chart
    mariadb
    & INSTALL
    helm install my-mariadb bitnami/mariadb --version 20.4.2
    TEMPLATES
    Bitnami package fo
    my-mariadb corresponds to the release name, feel free to change it to suit your needs. You can also add additional flags to the helm install
    command if you need to.
    E DEFAULT VALUES
    MariaDB is an open source, community
    "VALUES SCHEMA
    You can also download this package's content using this command
    ity, and collaboration with leading tech
    CHANGELOG

[^21]: NAME : my-mariadb
    LAST DEPLOYED: Wed Mar 26 04:30:06 2025
    NAMESPACE: database
    STATUS: pending-install
    REVISION: 1
    TEST SUITE: None
    HOOKS :
    MANIFEST :

[^22]: C
    & https://github.com/chilops/HELM/tree/main
    =
    chilops / HELM
    Q Type to search
    <> Code O Issues 7 Pull requests
    Actions
    Projects Wiki @ Security L Insights
    to Settings
    HELM Public
    & Pin
    OUnwatch 1
    & main
    & 1 Branch 0 Tags
    Q Go to file
    t
    Add file
    <> Code
    O
    Chowdarychilukuri first commit
    80db5a1 . 1 minute ago 1 Commit
    README.md
    first commit
    1 minute ago
    DO README
    Hello Git

[^23]: root@Minikube-helm: \~# git clone https: //github. com/chilops/HELM. git
    Cloning into 'HELM'
    remote: Enumeratiog objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0 (from 0)
    Receiving objects: 100% (3/3), done.
    root@Minikube-helm: \~ #

[^24]: root@Minikube-helm: \~/HELM# 1s
    README. md StartWithHELM
    root@Minikube-helm: \~/HELM#
    root@Minikube-helm: \~/HELM#
    root@Minikube-helm: \~/HELM# mkdir create charts
    root@Minikube-helm: \~/HELM# cd create_charts/
    root@Minikube-helm: \~/HELM/create charts#

[^25]: root@Minikube-helm: \~/HELM/create_charts/my_first_chart# 1s
    Chart . yaml charts
    templates values. yaml
    root@Minikube-helm: \~/HELM/create charts/my first chart#

[^26]: root@Minikube-helm: \~/HELM/create_charts/my_first_chart# cd charts
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/charts#
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/charts# 1s
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/charts#
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/charts#
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/charts# cd . ./templates/
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/templates# 1s
    NOTES . txt helpers. tpl deployment . yaml hpa . yaml ingress . yaml
    service . yaml
    serviceaccount . yam\] tests
    root@Minikube-helm: \~/HELM/create charts/my first chart/templates# \|\]

[^27]: root@Minikube-helm: \~/HELM/create charts/my first_chart/ templates# cd tests
    root@Minikube-helm: \~/HELM/create_charts/my_first_chart/templates/tests# 1s
    test-connection . yaml

[^28]: root@Minikube-helm: \~/HELM/create_charts# pwd
    / root/HELM/create charts
    root@Minikube-helm: \~/HELM/create charts#

[^29]: root@Minikube-helm: \~/HELM/create_charts# 1s
    my-first-chart
    root @Minikube-helm: \~/HELM/create_charts#
    root @Minikube-helm: \~/HELM/create_charts#
    root@Minikube-helm: \~/HELM/create_charts# helm install my-deployment my-first-chart/
    NAME: my-deployment
    LAST DEPLOYED: Thu Mar 27 04:50:59 2025
    NAMESPACE: default
    STATUS: deployed
    REVISION: 1
    NOTES :
    1. Get the application URL by running these commands:
    export POD NAME=$ (kubectl get pods --namespace default -1 "app. kubernetes. io/name=my-first
    ce=my-deployment" -o jsonpath=" { . items \[0\] .metadata. name}")
    export CONTAINER PORT=$ (kubectl get pod --namespace default $POD_NAME -o jsonpath="{. spec.
    rPort}")
    echo "Visit http://127.0.0.1:8080 to use your application"
    kubectl
    --namespace default port-forward $POD NAME 8080: $CONTAINER PORT

[^30]: root@Minikube-helm: \~/HELM/create_charts/my-first-chart# vi Chart . yaml
    root@Minikube-helm: \~/HELM/create_charts/my-first-chart# vi values. yaml

[^31]: root @Minikube-helm: \~/HELM/create_charts# helm package my-first-chart/
    Successfully packaged chart and saved it to: /root/HELM/create_charts/my-first-chart-1.1.0.tgz
    root@Minikube-helm: \~/HELM/create_charts# 1s
    my-first-chart my-first-chart-1. 1.0. tgz
    root @Minikube-helm: \~/HELM/create charts#

[^32]: root@Minikube-helm: \~/HELM/create_charts# helm lint my-first-chart
    => Linting my-first-chart
    \[INFO\] Chart . yaml: icon is recommended
    1 chart (s) linted, 0 chart (s) failed

