---
title: Minikube Installation & ALL
uuid: 1a951a6e-feff-11ef-b328-05c51be8b43a
version: 463
created: '2025-03-12T10:31:48+05:30'
---

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