---
title: All Commands
uuid: 21c4e692-5479-11ef-9d9d-f2c7410336d6
version: 997
created: '2024-08-07T10:24:29+05:30'
tags:
  - commands
---

# <mark style="background-color:#F8914D;">**Kubernetes:**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

```
Kubectl version                    -- to check the kubectl version
eksctl                             -- basic command
```

\

To create a Eks cluster nodes

```
eksctl create cluster --config-file=eks.yaml
```

\

To check if nodes created and running.

```
kubectl get nodes
```

To create namespace & view 

```
kubectl create -f namespace.yaml
or
kubectl apply-f namespace.yaml       --We use apply instead of create, if not created it will create, if you use again any changes it will update or it will say unchanged.
kubectl get namespaces               --View the namespaces
kubectl get ns                       --View the namespaces
kubectl get deployments -n <namespace>   --To check the deployment status if you deploying new pods etc
```

\

![65d08c3a-add2-4778-b737-2c45421966c0.png|999.201416015625](https://images.amplenote.com/21c4e692-5479-11ef-9d9d-f2c7410336d6/65d08c3a-add2-4778-b737-2c45421966c0.png) [^1]

![c4f80f9d-be9e-432a-9d41-0ee81217268f.png|997.1875610351562](https://images.amplenote.com/21c4e692-5479-11ef-9d9d-f2c7410336d6/c4f80f9d-be9e-432a-9d41-0ee81217268f.png) [^2]

\

To delete a namespace/resource

```
kubectl delete -f namespace.yaml
```

\

To create and delete POD.

```
kubectl apply -f 01-pod.yaml
kubectl delete -f 01-pod.yaml
```

\

To view pods

```
kubectl get pods
```

```
kubectl get pods -n <Namespace>    -- view pod from a particular namespace
kubectl describe pod <POD Name>    -- To view details of POD(IP address, labels etc)
kubectl exec -it <POD Name> -- bash     -- to enter into pod
env
kubectl logs <POD Name>     --To check any Pod logs
```

\

\

To create configmap & to view.

```
kubectl apply -f 07-config-map.yaml
kubectl get configmap
kubectl describe configmap <configmap name>
```

\

To create secret & to view.

```
kubectl apply -f 09-secrets.yaml
kubectl get secret
kubectl exec -it secret-pod -- bash
env
```

\

To view the services

```
kubectl get service
```

\

To view the repilcasets

```
Kubectl get replicaset
or 
kubectl get rs
```

\

To see all API resources

```
kubectl api-resources
```

\

To create Storage class & view

```
kubectl apply -f file.yaml
kubectl get sc
```

\

\

**Helm Commands:**

\

Installing Helm

```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
helm version
```

\

Initializing helm resources(pods)

```
helm install <resource name> .
helm list
or
kubectl get pods
```

\

Upgrade new app version when changes made.

```
helm upgrade <resource name> .
helm list
or
helm history <resource name>
```

\

We can do rollback if upgraded app version is not running well. (how fast we are doing rollback is important) then we will not loose the business

```
helm rollback nginx
kubectl get pods
```

\

**If you want to rollback particular version (out of 10 versions)**

```
helm rollback nginx 2
kubectl get pods
```

\

To see the values present

```
helm show values .
```

\

Helm setting the values through command line (changing replicas from 3 to 10)

```
helm upgrade nginx --set deployment.replicas=10
```

\

Creating helm repo for AWS CSI drivers

```
helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
```

```
helm repo list
helm repo update
```

\

Installing csi drivers

```
helm upgrade --install aws-ebs-csi-driver --namespace kube-system aws-ebs-csi-driver/aws-ebs-csi-driver
```

\

To check if CSI driver installed or not

```
kubectl get pod -n kube-system -l "app.kubernetes.io/name=aws-ebs-csi-driver,app.kubernetes.io/instance=aws-ebs-csi-driver"
or
helm list -n kube-system
```

To Uninstall

```
helm uninstall aws-ebs-csi-driver -n kube-system
helm list -n kube-system
```

\

To uninstall resource

```
helm uninstall <resource name>
```

```
helm list
```

\

to check which pod is using more memory

```
kubectl top pods
```

# <mark style="background-color:#F8914D;">**Docker:**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### **Docker Engine Installation:**

```
sudo su -
```

```
yum install -y yum-utils
```

\

**Downloading/Adding a Repo**

```
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

\

**Docker Engine installing** 

```
yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

\

**Start the docker**

```
systemctl start docker
systemctl enable docker
systemctl status docker
```

\

\

**To list all the running Docker containers on your system.**

```
docker ps         -- Lists all running containers
docker ps -a      -- It includes that are stopped
docker ps -q      -- Lists only the container ID's of running containers
docker ps -s      -- Shows the total file sizes of the container's filesystem.
```

\

**When you install docker a group named DOCKER is created**

**Giving permission to users**

```
usermod -aG docker centos
```

\

**To check any docker images are present in server.**

```
docker images
```

\

**Pulling docker images from Docker Hub**

```
docker pull nginx
```

\

**Pulling docker image with specific tags**

```
docker pull nginx:alpine
docker pull nginx:stable-bulleye
docker ps
```

\

**Create a docker container from a docker image**

```
docker create nginx:alpine
docker create nginx:latest
docker ps -a
docker run -d --name catalogue --network=roboshop catalogue:1
```

![f245c229-36c3-435e-91c4-80c206427480.png|1084.666748046875](https://images.amplenote.com/21c4e692-5479-11ef-9d9d-f2c7410336d6/f245c229-36c3-435e-91c4-80c206427480.png) [^3]

\

**To run/start to docker container**

```
docker start <container ID>
docker ps
```

![cc6aa7eb-d1f7-48a8-a797-171abf1fa97d.png|1086.666748046875](https://images.amplenote.com/21c4e692-5479-11ef-9d9d-f2c7410336d6/cc6aa7eb-d1f7-48a8-a797-171abf1fa97d.png) [^4]

\

**To stop the running container**

```
docker stop <container ID>
```

```
docker ps         -- Lists all running containers
docker ps -a      -- It includes that are stopped
docker ps -q      -- Lists only the container ID's of running containers
docker ps -s      -- Shows the total file sizes of the container's filesystem.
```

\

**To delete the docker container**

```
docker rm <container ID>
docker ps -a
```

\

**To delete the docker image**

```
docker images
docker rmi <Image ID>
docker images
```

\

**To remove all images at one go**

```
docker images -a -q                               -- It will show image id's output
docker rmi $(docker images -a -q)            -- It will remove all images at one go
```

TO stop and delete docker containers which are running all at one go

```
docker ps
docker ps -a -q
docker rm -f $(docker ps -a -q)
docker ps
```

\

**To pull+create+run image at one go below is the command**

```
docker run nginx
```

```
docker run -d nginx        To run docker images in background (-d is for detach)
docker ps
docker ps -a
```

\

**To remove container without stopping**

```c
docker rm -f <container ID>    
```

\

\

**Docker port forwarding**

![4f84dd9c-93f3-4cd5-ab17-caf642303b37.png|434](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4f84dd9c-93f3-4cd5-ab17-caf642303b37.png) [^5]

![dcbc4a5a-d327-45bd-b26d-d471e4af1ade.png|588](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/dcbc4a5a-d327-45bd-b26d-d471e4af1ade.png) [^6]

docker run -d -p <VM port no>:<docker container port no> nginx <mark>**(VM port you can take any port, but container port should be same which nginx is using)**</mark>

```
docker run -d -p 8080:80 nginx
```

![83fb4fcb-5616-4f12-a2d0-bec2ac634b5d.png|930.6666870117188](https://images.amplenote.com/21c4e692-5479-11ef-9d9d-f2c7410336d6/83fb4fcb-5616-4f12-a2d0-bec2ac634b5d.png) [^7]

\

**Note: we can use more containers with different VM port number (same VM port cannot be used)**

<mark>**Below ex is 3 Nginx docker containers are running with different ports (3 different static websites can be run and at least we can 10 to 15 websites on single VM)**</mark>

![76e4ba42-30f9-45a6-8fb9-719a27d6dc6d.png|934](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/76e4ba42-30f9-45a6-8fb9-719a27d6dc6d.png) [^8]

![7799b3a2-0867-4dd0-a1e7-a6191a29973e.png|626](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7799b3a2-0867-4dd0-a1e7-a6191a29973e.png) [^9]

\

\

**Assigning name to docker container**

```
docker run -d -p 8083:80 --name <specify Name> nginx
docker run -d -p 8083:80 --name nginx_chill nginx
docker run -d -p 80:80 cmd:v1
docker run -p 8080:80 -p 8443:443 myimage        -- To assign and expose multiple ports
docker run -d -p 8080:80 env:v1
docker run -d -p 80:80 --name web --network=roboshop web:1    -- To assign and expose multiple ports
```

\

**Login to container**

```
docker exec -it chill bash                        -- i(input) t(terminal)
```

\

**To view all details(inspect) of a docker container**

```
docker inspect <docker ID>
docker inspect dde50c79481c
```

\

\

**Building an image from docker file (local image not uploading to docker.io) and pushing it to docker hub**

```c
docker login                              --> login to docker with user id and password
docker images
docker build -t from:v1 .                 --> buliding a docker image from file alsoing with tag(v1)     
docker images
docker tag from:v1 chilops/repo1:v1      --> retagging with same as your docker user and repo
docker push chilops/repo1:v1                  --> pushing to docker hub
docker tag from:v1 chilops/repo1:v2       --> retagging as version2 and now pushing to docker hub
docker images
docker push chilops/repo1:v2    
```

\

**Docker Inspect commands:**

```
docker inspect <container_id or container_name>
docker inspect <image_id or image_name>
docker inspect <network_id or network_name>
docker inspect <volume_name>
```

\

**To check container logs:**

```
docker logs mongodb
docker logs <container ID>
docker exec -it <container ID> bash    -- To login to container
curl http://catalogue:8080/health
curl localhost/api/catalogue/health
```

\

**Create a docker network:**

```
docker network
```

```
docker network create <network name>
```

```
docker inspect <container ID> | grep IPAddress
```

\

**Docker compose: to bring all container up & down and delete the container with single command**

```
docker compose up -d
docker compose down               --Stops and removes the containers, networks, and volumes created by up.
```

\

```
docker compose up            --Start Services
docker compose build         --Build or Rebuild Services
docker compose start         -- to start the containers
docker compose stop          --Stop Containers
docker compose rm            --Remove Stopped Containers
docker compose logs          -- view logs
docker compose ps            -- listing container
docker compose exec <container name/id> <command>            --Execute a Command in a Running Container
docker compose exec web bash                                 --Runs a command in a specific service's container. For example
```

\

**Docker volumes: Named Volumes**

```
docker volume
docker volume create <volumename>
docker volume create nginx
docker volume inspect nginx
docker run -d -p 80:80 -v nginx:/usr/share/nginx/html nginx
```

\

**All unused data will be deleted**

```
docker system prune
```

---

# <mark style="background-color:#F8914D;">**GIT:**<!-- {"backgroundCycleColor":"24"} --></mark>

\

**Configure git:**

```
git config --global user.name "your name"
git config --global user.email "your mail"
```

\

**Initialize repository:**

```
git init
```

\

**clone a repo:**

```
git clone git@github.com:chilops/shellscripts.git
git clone https://github.com/chilops/shellscripts.git 
```

\

**Remote repository:**

```
git remote add <repo name> <repo url>
git remote -v                 -- list remote repos
git fetch <remote name>       --fetch changes from a remote repo
git pull <remote name> <branch name>    --pull changes from a remote repo
git push <remote name> <branch name>    --push changes to a remote repo
```

\

**Branches:**

```
git branch <new branch>
git checkout <other branch>           --Switch to branch
git checkout -b <other branch>       --Create & switch to branch
git branch                                           --Listing branches
git branch -d <branch name>          --Delete branches
```

\

**To check status:**

```
git status
```

\

**Add files:**

```
git add filename
```

```
git add .
```

\

**Commit changes:**

```
git commit -m "message"
```

\

**push & pull changes:**

```
git push origin <branch name>
git pull origin <branch name>
```

\

**Add files & commit & push at a time:**

```
git add . ; git commit -m "jenkins"; git push origin main
```

\

**Undo changes:**

```
git reset HEAD filename        --To unstage files
git checkout -- filename         --To discard changes
git revert commit-id                --To revert commit
git reset --hard commit-id      --Reset to commit-id
```

\

**logs:**

```
git log
git log --oneline        --show oneline per commit
git diff          --show changes
```

\

**Stashing:**

```
git stash                  --save changes temporarily
git stash apply       --apply most recent stashed changes
git stash list           --list stashed changes
git stash drop        --remove a stashed state.
```

\

**Merging:**

```
git merge <branch name>
```

\

**Rebase:**

```
git rebase <branch name>         --Rebase your current head onto the specified branch
```

[^1]: 18 . 234.197.98 \| 172 . 31. 41.186 \| t2.micro \| https: / /github. com/chilops/k8-resources . git
    \[ centos@ip-172-31-41-186 \~/k8-resources/01-namespace \]$ kubectl apply -f namespace . yaml
    namespace / roboshop created
    18 . 234. 197.98 \| 172. 31. 41.186 \| t2.micro \| https: //github. com/chilops/k8-resources. git
    \[ centosdip-172-31-41-186 \~/k8-resources/01-namespace \]$ kubectl apply -f namespace . yaml
    namespace/roboshop unchanged

[^2]: 18 . 234.197.98 \| 172. 31. 41.186 \| t2.micro \| https: / /github. com/chilops/k8-resources .gi
    \[ centos@ip-172-31-41-186 \~/k8-resources/01-namespace \]$ kubectl get namespaces
    NAME
    STATUS
    AGE
    default
    Active
    43m
    kube-node-lease
    Active
    43m
    kube-public
    Active
    4 3m
    kube-system
    Active
    43m
    roboshop
    Active
    45s

[^3]: 34. 226. 215.227 \| 172. 31. 44.186 \| t2.micro \| null
    \[ centosdip-172-31-44-186 \~ \]$ docker ps
    Fa
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    aal411b3fee7
    nginx : alpine
    "/ docker-entrypoint ....'
    14 seconds ago
    Created
    stupefied bhabha
    5c80328d3137
    nginx : latest
    "/ docker-entrypoint ...."
    23 seconds ago
    Created
    funny_leavitt

[^4]: 34 . 226.215.227 \| 172. 31. 44.186 \| t2.micro \| null
    centosdip-172-31-44-186 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    aal411b3fee7
    nginx : alpine
    "/ docker-entrypoint ...'
    3 minutes ago
    Up 12 seconds
    80/tcp
    stupefied bhabha
    5c80328d3137
    nginx : latest
    "/ docker-entrypoint ....'
    3 minutes ago
    Up 3 seconds
    80/tcp
    funny_leavitt

[^5]: 0-65, 535 ports
    0-65, 535 a container will have

[^6]: VM
    8080
    docker
    80

[^7]: C
    Not secure 34.226.215.227:8080
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^8]: \[ centos@ip-172-31-88-21 \~ \]$ docker run -d -p 8080:80 nginx
    5f502d465b6c98914bba5a34bea 798b266f58b8fea5e3f69643ac46c089651c5
    docker: Error response from daemon: driver failed programming external connectivity on endpoint sharp banach (f44d0fb351e04fd49106d2125
    a03fe184eca4e61lea334457ff2fe2adadea4fa) : Bind for 0.0.0.0:8080 failed: port is already allocated.
    54 . 173 . 241 . 201 \| 172.31.88.21 \| t2. micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker run -d -p 8081:80 nginx
    ff851e3a4251f9f1b0047d7b19eb95c9a2e5351b4ac79083840a98346810e538
    54 . 173. 241.201 \| 172. 31. 88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker run -d -p 8082:80 nginx
    65e5dabd132b4be33b7abab9c0913ae053b2359c8a17e95a61a06ee195deee71
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    nginx
    latest
    b690f5f0a2d5
    3 months ago
    187MB
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAME
    S
    65e5dabd132b
    nginx
    "/docker-entrypoint..."
    8 seconds ago
    Up 7 seconds
    0. 0. 0. 0:8082->80/top, : : :8082->80/top
    sill
    y_heyrovsky
    ff851e3a4251
    nginx
    "/docker-entrypoint..."
    12 seconds ago
    Up 11 seconds
    0. 0. 0. 0: 8081->80/top, : : : 8081->80/top
    rela
    xed darwin
    8553a2804a09
    nginx
    "/ docker-entrypoint.."
    About a minute ago
    Up About a minute
    0. 0. 0. 0:8080->80/tcp, : : : 8080->80/tcp
    stra
    nge_pike
    54. 173. 241 . 201 \| 172. 31. 88.21 \| t2. micro \| null

[^9]: C
    - . . .
    docker
    8080
    docker
    80
    docker

