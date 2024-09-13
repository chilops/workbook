---
title: 48_49_50Day_Docker
uuid: f7349cfe-3828-11ef-8d44-26e37c279344
version: 1885
created: '2024-07-02T09:40:06+05:30'
tags:
  - docker
---

# <mark style="background-color:#f8914d;">**Docker & Containerization**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![a2cae7c1-519c-4230-8c94-d4eaf7d9edba.png|893](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/a2cae7c1-519c-4230-8c94-d4eaf7d9edba.png) [^1]

![9376520c-ac8b-42f0-82da-4faa0524a104.png|803](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/9376520c-ac8b-42f0-82da-4faa0524a104.png) [^2]

![3bcaedff-c9cd-4c99-8bd9-33e9ad89239f.png|849.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3bcaedff-c9cd-4c99-8bd9-33e9ad89239f.png) [^3]

![70451df5-5696-4c88-ab87-405346d12931.png|524](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/70451df5-5696-4c88-ab87-405346d12931.png) [^4]

![aeeb6492-d01d-44f7-8bc5-4b8c6371b489.png|981.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/aeeb6492-d01d-44f7-8bc5-4b8c6371b489.png) [^5]

\

<mark>**Docker Images are Immutable images - Can take from DEV to PROD (Docker is portable)**</mark>

![5685e55b-e622-404f-b735-5bc2234f807d.png|1005.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/5685e55b-e622-404f-b735-5bc2234f807d.png) [^6]

\

# <mark style="background-color:#f8914d;">**Docker Installation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Create a VM.

![659bd927-7f4b-430b-bae1-485b60838c4b.png|805.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/659bd927-7f4b-430b-bae1-485b60838c4b.png) [^7]

\

<mark>**Install docker engine**</mark>

![eef63c2c-8d71-40de-9bbd-62127633565a.png|897.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/eef63c2c-8d71-40de-9bbd-62127633565a.png) [^8]

\

Setting up a repo

```
sudo su -
yum install -y yum-utils
```

![7e0af630-f4c7-4bf1-a126-80f6c7bcfd97.png|889](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7e0af630-f4c7-4bf1-a126-80f6c7bcfd97.png) [^9]

\

```
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

![c82e085f-f1b9-4853-b6dc-cd1ebcf8c491.png|1094.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c82e085f-f1b9-4853-b6dc-cd1ebcf8c491.png) [^10]

\

Installing Docker engine

```
yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

![c0fe049c-56f0-47b2-b3ee-a6afe7cb04ae.png|1171.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c0fe049c-56f0-47b2-b3ee-a6afe7cb04ae.png) [^11]

\

Start the docker

```
systemctl start docker
systemctl enable docker
systemctl status docker
```

![6526b73b-b77e-43d1-a0a7-10a69a5c9385.png|1076.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6526b73b-b77e-43d1-a0a7-10a69a5c9385.png) [^12]

\

```
docker
docker ps
```

![94d4f81e-8cad-4a52-bd53-5233bd789592.png|830](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/94d4f81e-8cad-4a52-bd53-5233bd789592.png) [^13]

\

<mark>Docker users can only use docker commands</mark>

When you install docker a group named DOCKER is created

Giving permission to users

usermod -aG docker centos

![eb960104-d9bc-4352-a0c0-19740af2d2e1.png|739](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/eb960104-d9bc-4352-a0c0-19740af2d2e1.png) [^14]

\

Reconnect to instance and try docker commands with normal user.

```
docker ps
```

![b05f4f0b-7518-4527-b989-d33565018ad3.png|837](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b05f4f0b-7518-4527-b989-d33565018ad3.png) [^15]

\

# <mark style="background-color:#F8914D;">**Docker Commands**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Container is the running version of an image

![86af9860-3fc2-4fcd-a454-c4717c7caba9.png|383](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/86af9860-3fc2-4fcd-a454-c4717c7caba9.png) [^16]

\

currently no images

```
docker images
```

\

Now pulling nginx image (its pull image from docker hub)

```
docker pull nginx
```

![776a54fa-dc1c-4b8c-99e4-4bcedd57449a.png|1045](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/776a54fa-dc1c-4b8c-99e4-4bcedd57449a.png) [^17]

\

```
docker images
```

![c4125d97-85a5-4291-8d0a-dae71d2e836a.png|852](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c4125d97-85a5-4291-8d0a-dae71d2e836a.png) [^18]

![bc571d17-1012-44d9-b176-891e8eba3ff5.png|757](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/bc571d17-1012-44d9-b176-891e8eba3ff5.png) [^19]

\

# <mark style="background-color:#F8914D;">**Docker HUB**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

All the Images(Nginx) are pulled from Docker HUB

![e5463bb8-4331-4b5d-b0a6-8fe693933185.png|975.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/e5463bb8-4331-4b5d-b0a6-8fe693933185.png) [^20]

![1802b04b-0861-433c-9a22-9013e5dfedb0.png|1023.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/1802b04b-0861-433c-9a22-9013e5dfedb0.png) [^21]

\

# <mark style="background-color:#F8914D;">**Image Tags**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

```
docker pull nginx:stable-bullseye
docker images
```

![187aaffa-baf9-43d6-867c-ffaaecf7c31c.png|1068.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/187aaffa-baf9-43d6-867c-ffaaecf7c31c.png) [^22]

![f07f72e0-af58-4220-b2e7-6373e293438f.png|859](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/f07f72e0-af58-4220-b2e7-6373e293438f.png) [^23]

\

alpine nginx images has very less space occupied(50MB)

```
docker pull nginx:alpine
docker images
```

![c24ecb94-76e5-4868-a2fb-a3b339a1d16f.png|877](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c24ecb94-76e5-4868-a2fb-a3b339a1d16f.png) [^24]

\

# <mark style="background-color:#F8914D;">**Create containers from Docker image**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

It's a running version of an image

\

docker create <image ID>/<image-name>:version             -- container will be created

```
docker create nginx:latest
```

![be8bb557-ea43-4f11-a4a9-2d6a69cbbfaf.png|843](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/be8bb557-ea43-4f11-a4a9-2d6a69cbbfaf.png) [^25]

\

\

docker ps -- <mark>running containers</mark>

docker ps -a    -- <mark>all containers with all status (created or running)</mark> 

To check which docker container (It shows only running containers)

```
docker ps
docker ps -a
```

\

![0079a9e2-eef4-4e68-8f9c-72863ed13398.png|1029.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/0079a9e2-eef4-4e68-8f9c-72863ed13398.png) [^26]

\

To start the docker 

```
docker start <container ID>
docker ps
```

![b3c98058-4855-4d3e-bcd6-8d30f1fa33fe.png|1151.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b3c98058-4855-4d3e-bcd6-8d30f1fa33fe.png) [^27]

![8b69f0c9-441e-4da1-b662-302353f11ff4.png|1125.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/8b69f0c9-441e-4da1-b662-302353f11ff4.png) [^28]

\

we cannot remove when its running

```
docker rm <container ID>
```

![c2272e8d-ed7a-45d0-aeaf-c1d3ce4a50b5.png|1179.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c2272e8d-ed7a-45d0-aeaf-c1d3ce4a50b5.png) [^29]

\

stop the docker and remove it

```
docker stop <container ID>
docker rm <container ID>
docker ps -a
```

![e342d191-2f49-4e9e-9fce-6e845b41a8f3.png|866](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/e342d191-2f49-4e9e-9fce-6e845b41a8f3.png) [^30]

\

![abd360e7-2256-4833-b650-57aaa4773c9a.png|763](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/abd360e7-2256-4833-b650-57aaa4773c9a.png) [^31]

\

\

removing images

```
docker images
docker rmi <image name>/ID
```

![488df64f-2dd5-4f0d-9757-a57e1aeaa5f3.png|1151.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/488df64f-2dd5-4f0d-9757-a57e1aeaa5f3.png) [^32]

\

To remove all images at one go

```
docker images -a -q                               -- It will show image id's output
docker rmi $(docker images -a -q)            -- It will remove all images at one go
```

![2bda0cf9-f354-464b-ae9c-b7dc335f2175.png|1089.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/2bda0cf9-f354-464b-ae9c-b7dc335f2175.png) [^33]

\

To pull+create+run image at one go below is the command

```
docker run nginx
```

![4a325c92-224c-461e-8127-57184ab58f3f.png|1103.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4a325c92-224c-461e-8127-57184ab58f3f.png) [^34]

![1acfbed8-d977-4d6c-b2dd-df97d0d361d1.png|1101.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/1acfbed8-d977-4d6c-b2dd-df97d0d361d1.png) [^35]

\

```
docker ps -a
```

![062b32de-cd1e-4ca2-a202-f746b429c3ed.png|1121.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/062b32de-cd1e-4ca2-a202-f746b429c3ed.png) [^36]

\

To run docker images in background (-d is for detach)

```
docker run -d nginx 
docker ps
```

![e0997fc6-20c2-4425-bb0f-4cfbc1d5942b.png|980.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/e0997fc6-20c2-4425-bb0f-4cfbc1d5942b.png) [^37]

\

docker rm -f <container id>    it will remove without stopping

![b4232f0b-18e4-4546-b477-ad806f9b5799.png|1043.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b4232f0b-18e4-4546-b477-ad806f9b5799.png) [^38]

\

\

# <mark style="background-color:#F8914D;">**Port Forwarding**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![4f84dd9c-93f3-4cd5-ab17-caf642303b37.png|517](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4f84dd9c-93f3-4cd5-ab17-caf642303b37.png) [^39]

![9b85c2f5-79e3-4f68-bf78-e6c70ab5b2c0.png|782](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/9b85c2f5-79e3-4f68-bf78-e6c70ab5b2c0.png) [^40]

![dcbc4a5a-d327-45bd-b26d-d471e4af1ade.png|724](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/dcbc4a5a-d327-45bd-b26d-d471e4af1ade.png) [^41]

\

\

docker run -d -p <VM port no>:<docker container port no> nginx     (VM port you can take any port, but container port should be same which nginx is using)

```
docker run -d -p 8080:80 nginx 
```

![12762e1c-7eb9-4b8a-8792-7525b9285f25.png|747](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/12762e1c-7eb9-4b8a-8792-7525b9285f25.png) [^42]

\

Now Nginx is communicating to outside world and working

![7aabc12d-0c5b-4bce-b159-8d63e9877bb3.png|1007.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7aabc12d-0c5b-4bce-b159-8d63e9877bb3.png) [^43]

\

we can use more containers with different VM port number(same VM port cannot be used)

<mark>**Below ex is 3 Nginx docker containers are running with different ports (3 different static websites can be run and at least we can 10 to 15 websites on single VM)**</mark>

![76e4ba42-30f9-45a6-8fb9-719a27d6dc6d.png|1023.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/76e4ba42-30f9-45a6-8fb9-719a27d6dc6d.png) [^44]

![7799b3a2-0867-4dd0-a1e7-a6191a29973e.png|766](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7799b3a2-0867-4dd0-a1e7-a6191a29973e.png) [^45]

\

# <mark style="background-color:#F8914D;">**Assign name to container**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

```
docker run -d -p 8083:80 --name nginx_chill nginx
```

```
docker ps
```

![34140da2-58cf-47ef-aa2c-f9f4dbc21bb1.png|1155.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/34140da2-58cf-47ef-aa2c-f9f4dbc21bb1.png) [^46]

\

# <mark style="background-color:#F8914D;">**Looking into container**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Now i am inside the container

```c
docker exec -it chill bash                        -- i(input) t(terminal)
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b7b20495-210f-4649-9f6f-01a956339fa9.png) [^47]

\

to check the OS of Docker image (debian OS used as base OS)

```
cat /etc/*release
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/0978047d-b5f3-41f1-9818-4a701c7cb1a7.png) [^48]

\

\

# <mark style="background-color:#F8914D;">**Inspect a container**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

all information about that image/container

```
docker inspect <container ID>
```

![47a23dab-eb34-4476-972b-dca9680f099f.png|1082.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/47a23dab-eb34-4476-972b-dca9680f099f.png) [^49]

![dbf41887-f5ba-4d52-9afc-5e17e5914335.png|1082.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/dbf41887-f5ba-4d52-9afc-5e17e5914335.png) [^50]

\

# <mark style="background-color:#F8914D;">**Docker files - Creating our own docker images (custom images)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

**Docker File** -- A declarative way of creating our own image...

\

**Docker Image** = Base OS (5MB-250MB) + application run time + created users + created a directory + installed application = max 500MB = immutable image = can take from DEV to PROD

\

Create a github folder for docker files

![778f55d7-5137-40cd-b6bb-5073b646f2de.png|481](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/778f55d7-5137-40cd-b6bb-5073b646f2de.png) [^51]

\

Create a new repository before proceeding below commands.

```
cd e/AWSDevOps/Repos/dockerfiles/
git init
git branch -M main
git remote add origin git@github.com:chilops/dockerfiles.git
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/cdededd3-1e38-4a45-826f-9380e37fa0cc.png) [^52]

\

<mark>Now we are learning to how to write instructions, so that we can create our own images of our applications.</mark>

\

# <mark style="background-color:#F8914D;">**From instruction**<!-- {"backgroundCycleColor":"24"} --></mark> --- it's the first instruction<!-- {"collapsed":true} -->

![8f084d67-7a43-493b-9b38-1cc7053029e4.png|1014](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/8f084d67-7a43-493b-9b38-1cc7053029e4.png) [^53]

docker build -t image : version .    --- It means we are creating docker image locally & not pushing to anywhere(docker.io or ECR or Nexus)

![6bd1f5dc-d871-4a47-8b2b-0fe7d2ce2917.png|630](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6bd1f5dc-d871-4a47-8b2b-0fe7d2ce2917.png) [^54]

\

dockerfile with centos 8 version 

![df7c60aa-2d48-474d-bbe8-e9aa886fe8ec.png|663](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/df7c60aa-2d48-474d-bbe8-e9aa886fe8ec.png) [^55]

\

cloning git in docker server and building docker image

```
docker ps
git clone https://github.com/chilops/dockerfiles.git
cd dockerfiles
cd from/
ls
docker build -t from:v1 .            (this is a local image not pushing to docker.io)
```

![efe8f5d7-42bc-4768-bd3c-7fe86a80ee8f.png|903.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/efe8f5d7-42bc-4768-bd3c-7fe86a80ee8f.png) [^56]

![3a98b49e-e803-4653-93db-ce56a81380d0.png|945.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3a98b49e-e803-4653-93db-ce56a81380d0.png) [^57]

\

```
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

![f5e42879-606d-49fe-ba68-19bbd20e4b5e.png|981.6666870117188](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/f5e42879-606d-49fe-ba68-19bbd20e4b5e.png) [^58]

![9340fc19-bc0d-4327-9c67-0e5b0dd48f2f.png|982.6666870117188](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/9340fc19-bc0d-4327-9c67-0e5b0dd48f2f.png) [^59]

![b25bac60-f74e-4cc9-ba76-4fc8b027b6e8.png|985.6666870117188](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b25bac60-f74e-4cc9-ba76-4fc8b027b6e8.png) [^60]

![ce6ee332-8a35-4cb2-bb76-c356a5882c41.png|992.6666870117188](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/ce6ee332-8a35-4cb2-bb76-c356a5882c41.png) [^61]

\

\

# <mark style="background-color:#F8914D;">**RUN instruction**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

RUN is useful when we are building image - its useful to perform software's installations or configurations 

![28a8764f-8143-49df-b298-76ce300469d1.png|855](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/28a8764f-8143-49df-b298-76ce300469d1.png) [^62]

\

```
docker build -t run:v1 .
```

![8e1a7591-6206-4287-a4c3-7b29f1c8acee.png|1065.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/8e1a7591-6206-4287-a4c3-7b29f1c8acee.png) [^63]

```
docker images
```

![b04cd453-fa69-4a43-8ac9-23a2ce82f86f.png|1141.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b04cd453-fa69-4a43-8ac9-23a2ce82f86f.png) [^64]

\

# <mark style="background-color:#F8914D;">**CMD instructions**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

<mark>RUN vs CMD is very popular & mandatory interview question</mark>

![be401b4b-2596-44ec-aa93-5f6ffe1dff5c.png|1029.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/be401b4b-2596-44ec-aa93-5f6ffe1dff5c.png) [^65]

\

systemctl commands will not work in containers

Every container is a process

![3cb93a23-9149-49f1-b2c8-4cbbd6df4987.png|938.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3cb93a23-9149-49f1-b2c8-4cbbd6df4987.png) [^66]

![ecd4bd91-8028-43f3-b534-f5314e69fa2e.png|1126.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/ecd4bd91-8028-43f3-b534-f5314e69fa2e.png) [^67]

![23f09acc-a129-4222-9e9c-1e97aa603463.png|1114.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/23f09acc-a129-4222-9e9c-1e97aa603463.png) [^68]

\

```
docker build -t cmd:v1 .
```

![d1135d63-427a-4520-8f8b-4c2344ce4dc4.png|1107.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/d1135d63-427a-4520-8f8b-4c2344ce4dc4.png) [^69]

\

```
docker run -d -p 80:80 cmd:v1
```

```
docker ps
```

![07ae5f50-b4c6-4430-8220-c197974fd2ab.png|1160.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/07ae5f50-b4c6-4430-8220-c197974fd2ab.png) [^70]

\

Nginx is running & working

![3046daee-92ee-4a65-b39d-079c6244ea46.png|1078.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3046daee-92ee-4a65-b39d-079c6244ea46.png) [^71]

\

# <mark style="background-color:#F8914D;">**Label Instruction**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![c2a06c09-6a32-4488-a569-9af9a0e183d4.png|906.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c2a06c09-6a32-4488-a569-9af9a0e183d4.png) [^72]

![0e3b5780-77ef-4308-bfb4-f6184833b457.png|831](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/0e3b5780-77ef-4308-bfb4-f6184833b457.png) [^73]

![04435e98-11da-4d7e-b4b8-141b991359d3.png|1041.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/04435e98-11da-4d7e-b4b8-141b991359d3.png) [^74]

\

![e84a551f-3f07-4ca9-8a61-4273d2bb2469.png|1089.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/e84a551f-3f07-4ca9-8a61-4273d2bb2469.png) [^75]

\

```
docker build -t label:v1 .
```

![fda9e813-c525-4d76-bd48-7a2f28fa8f2d.png|1172.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/fda9e813-c525-4d76-bd48-7a2f28fa8f2d.png) [^76]

```
docker images
```

![43d2a01f-8463-4206-8bf1-3e3a2e7f1312.png|1103.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/43d2a01f-8463-4206-8bf1-3e3a2e7f1312.png) [^77]

\

to filter with label

```
docker images --filter label=trainer=sivakumar
```

\

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/575d6b0b-5e7b-4620-b31c-8ef131bc2329.png) [^78]

---

# <mark style="background-color:#F8914D;">**EXPOSE Instruction**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

If we want to see which port that docker image is using.. then we can use expose instruction (this is only for information purpose only)

![5729c712-075d-4d91-87ea-dce93980e83e.png|923](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/5729c712-075d-4d91-87ea-dce93980e83e.png) [^79]

![38017223-ca82-4801-b1d7-95065f8b7d67.png|982](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/38017223-ca82-4801-b1d7-95065f8b7d67.png) [^80]

\

```
docker build -t expose:v1 .
```

![5ae164c7-100f-4b09-bf6e-1c4a3e33b6a6.png|1112.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/5ae164c7-100f-4b09-bf6e-1c4a3e33b6a6.png) [^81]

\

```
docker images
docker inspect 809034b75c3e
```

![6543fee6-fd89-4ac9-aaa6-ff6e0c8076e0.png|1200.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6543fee6-fd89-4ac9-aaa6-ff6e0c8076e0.png) [^82]

![ebb522c7-1e55-4ddc-96a8-8b0dfe1360f9.png|1079.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/ebb522c7-1e55-4ddc-96a8-8b0dfe1360f9.png) [^83]

\

# <mark style="background-color:#F8914D;">**ENV Instructions**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![7f3fe1f3-3e64-4b08-9ba9-abcd71ce04e4.png|865](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7f3fe1f3-3e64-4b08-9ba9-abcd71ce04e4.png) [^84]

![bb08c59d-b2c5-47bf-9621-ebff20371ece.png|846](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/bb08c59d-b2c5-47bf-9621-ebff20371ece.png) [^85]

![d60902d9-e32f-4fdd-ab0c-e2b9bc2d3bd8.png|1098.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/d60902d9-e32f-4fdd-ab0c-e2b9bc2d3bd8.png) [^86]

\

```
docker build -t env:v1 .
```

![ff11d3b1-6b4a-4866-9067-ddaef958903a.png|1045.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/ff11d3b1-6b4a-4866-9067-ddaef958903a.png) [^87]

\

```
docker run -d -p 8080:80 env:v1 .
```

```
docker ps
```

\

![5db31468-80a7-422c-bf53-bf81c82de28b.png|1051.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/5db31468-80a7-422c-bf53-bf81c82de28b.png) [^88]

\

```
docker exec -it e232c789e858 bash
```

```
env
```

![bb677df4-ff2f-4857-b8e0-e1efcb6b9ebd.png|1181.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/bb677df4-ff2f-4857-b8e0-e1efcb6b9ebd.png) [^89]

\

# <mark style="background-color:#F8914D;">**COPY Instructions**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

its means copy your files from local to image

\

![4749eade-330f-46f2-b75a-30bf80b0e3ec.png|944.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4749eade-330f-46f2-b75a-30bf80b0e3ec.png) [^90]

![3a37293b-62cd-448b-9881-3d3af72d3565.png|1131.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3a37293b-62cd-448b-9881-3d3af72d3565.png) [^91]

\

```
docker build -t copy:v1 .
```

![c1437659-472a-4d49-a500-a8b1bfec5263.png|1194.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c1437659-472a-4d49-a500-a8b1bfec5263.png) [^92]

\

to remove running containers

![b683dea0-d78b-4655-86fe-ce0e336145e9.png|1138.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b683dea0-d78b-4655-86fe-ce0e336145e9.png) [^93]

\

```
docker run -d -p 80:80 copy:v1 
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/1b5652fe-8374-4c3d-875a-2b8e1163b880.png) [^94]

\

checking if website is working or not

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/13448372-e586-4dda-ab8f-b55f787c3a04.png) [^95]

\

![897e1c29-2aa5-40af-9514-b854662ca262.png|1152.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/897e1c29-2aa5-40af-9514-b854662ca262.png) [^96]

\

# <mark style="background-color:#F8914D;">**ADD Instructions**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

COPY vs ADD popular interview question?

![7aa382b5-bfc0-4aac-bc8e-dd4514d55750.png|1065.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7aa382b5-bfc0-4aac-bc8e-dd4514d55750.png) [^97]

\

![b4b9ade1-2235-47ad-8e9b-4d83bfe8d716.png|1145.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b4b9ade1-2235-47ad-8e9b-4d83bfe8d716.png) [^98]

\

![00f96c3d-edef-4cce-b7ae-0ae56be1bb15.png|1163.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/00f96c3d-edef-4cce-b7ae-0ae56be1bb15.png) [^99]

\

```
docker build -t add:v1 .
```

![fd1291be-63c1-4476-a039-55acd9e2b909.png|1224.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/fd1291be-63c1-4476-a039-55acd9e2b909.png) [^100]

\

```
docker run -d -p 80:80 add:v1
```

![b42c2594-a659-454e-aaa4-50873d933d4f.png|1248.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b42c2594-a659-454e-aaa4-50873d933d4f.png) [^101]

\

# <mark style="background-color:#F8914D;">**ENTRYPOINT Instruction ---VVVIMP topic**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

CMD vs ENTRYPOINT

![4b49b5b7-0e88-4eb4-ba13-d111f2a97168.png|1065.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4b49b5b7-0e88-4eb4-ba13-d111f2a97168.png) [^102]

\

In below example i am using cmd command to ping google.com continually

![37efdf3f-2742-4233-a7f8-cc5e73f7f7c2.png|1164.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/37efdf3f-2742-4233-a7f8-cc5e73f7f7c2.png) [^103]

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c09c7aea-edbb-43f6-90e5-d57c30855e1e.png) [^104]

\

```
docker build -t entry:v1 .
```

![4b7d3bc9-001a-4f49-95d3-13bb9c260d0a.png|1268.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4b7d3bc9-001a-4f49-95d3-13bb9c260d0a.png) [^105]

\

```
docker run entry:v1
```

![6bd28a6b-24a2-46a7-9517-26537d348d9e.png|1029.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6bd28a6b-24a2-46a7-9517-26537d348d9e.png) [^106]

\

docker ps -a

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3457b524-97df-489c-8ff3-49d15c3b09c1.png) [^107]

```
docker ps -a
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/3457b524-97df-489c-8ff3-49d15c3b09c1.png) [^108]

\

now i given to ping yahoo.com 

```
docker run entry:v1 ping yahoo.com
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6b668234-08f0-44ab-ae15-48581d8f79d5.png) [^109]

```
docker ps -a
```

![f614a98f-db8d-4c74-8205-642d71c95769.png|1282.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/f614a98f-db8d-4c74-8205-642d71c95769.png) [^110]

\

Instead of CMD now i am using entry point

![522b174b-35ba-4df9-88cc-d52a51e07f39.png|1123.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/522b174b-35ba-4df9-88cc-d52a51e07f39.png) [^111]

\

![c7e8793d-5b8f-4d5d-8a18-5e9941d76a56.png|1200.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c7e8793d-5b8f-4d5d-8a18-5e9941d76a56.png) [^112]

\

rebuild

```
docker build -t entry:v1
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4e4ff149-a09a-4d91-bc1d-ddf506612977.png) [^113]

\

it pings google.com

```
docker run entry:v1
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/35ffcf9d-7b98-4f6c-a01c-c3390fe7c620.png) [^114]

\

if we try to override and run ping yahoo.com then it will fail

![9dd48c64-a531-4d0d-9742-66d5e8f7d1fc.png|1294.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/9dd48c64-a531-4d0d-9742-66d5e8f7d1fc.png) [^115]

\

```
docker ps -a --no-trunc
```

![897d3b38-c512-442a-ab47-b0e92dfcaee5.png|1287.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/897d3b38-c512-442a-ab47-b0e92dfcaee5.png) [^116]

\

Now using both cmd & entrypoint combinations

![5611caef-f1b9-4344-b83a-4a5c03cc1190.png|1147](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/5611caef-f1b9-4344-b83a-4a5c03cc1190.png) [^117]

\

```
docker build -t entry:v1 .
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/be4943e6-9e36-4db8-966c-7461b003fb58.png) [^118]

\

running docker image

```
docker run entry:v1
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/632f4f2d-c774-4429-9493-857b93eb59a3.png) [^119]

\

![593a583d-e2ba-480d-b89d-ac9852637a76.png|1133.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/593a583d-e2ba-480d-b89d-ac9852637a76.png) [^120]

now you can run yahoo.com as it can override cmd arguments

```
docker run entry:v1 yahoo.com
```

![](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/49f84f59-0af4-4f56-b777-02fc3ece8771.png) [^121]

\

# <mark style="background-color:#F8914D;">**USER Instructions**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

we should not use docker container with root users. if you do so its a security leakage and anyone can get the complete storage access

\

to disable we use user instruction

![7ef99011-a870-4434-b01a-d8fa05bbbdb3.png|895](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7ef99011-a870-4434-b01a-d8fa05bbbdb3.png) [^122]

\

![dad759ab-598c-4a55-8c7b-19aab11d7816.png|1024.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/dad759ab-598c-4a55-8c7b-19aab11d7816.png) [^123]

\

```
docker build -t user:v1 .
```

![9ed409a7-3bc4-4a17-9159-b998246eae50.png|1145.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/9ed409a7-3bc4-4a17-9159-b998246eae50.png) [^124]

\

```
docker run -d user:v1 
```

Now you are not root user

```
docker exec -it 7d6fddb bash
```

```
id
```

![dc77d964-8964-4da4-9859-0f73718def8a.png|1017.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/dc77d964-8964-4da4-9859-0f73718def8a.png) [^125]

\

# <mark style="background-color:#F8914D;">**WORKDIR Instructions**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![09dd4567-a12d-4d59-976f-e3c6cb71198a.png|1039.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/09dd4567-a12d-4d59-976f-e3c6cb71198a.png) [^126]

\

![d8519870-b836-4575-aaf7-8e6e94963e33.png|1047.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/d8519870-b836-4575-aaf7-8e6e94963e33.png) [^127]

\

```
docker build -t work:v1 .
```

![ee9cb29f-9f30-4e7d-a09d-9f116f5cc5b4.png|1060.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/ee9cb29f-9f30-4e7d-a09d-9f116f5cc5b4.png) [^128]

\

```
docker run -d it work:v1
```

![c462ec90-95aa-4a29-ba12-7bee98f2ec75.png|1171.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c462ec90-95aa-4a29-ba12-7bee98f2ec75.png) [^129]

\

```
docker exec -it f90a9c509 bash
```

![f8d16c6f-e22e-4aa0-aedd-cd58c805371c.png|1102.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/f8d16c6f-e22e-4aa0-aedd-cd58c805371c.png) [^130]

\

# <mark style="background-color:#F8914D;">**ARG Instruction**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

ARG vs ENV popular interview question

![2be3e05a-8770-40b3-94f7-d20d049ee263.png|1009.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/2be3e05a-8770-40b3-94f7-d20d049ee263.png) [^131]

\

![4bc26621-b793-4433-947b-7c505005b879.png|1000](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/4bc26621-b793-4433-947b-7c505005b879.png) [^132]

![46fca588-672c-4b4c-b1e1-5909c44623f0.png|1104.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/46fca588-672c-4b4c-b1e1-5909c44623f0.png) [^133]

\

```
docker build -t arg:v1 .
```

![c7e8a0d9-e015-4514-a9e1-11b16c3909de.png|1130.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c7e8a0d9-e015-4514-a9e1-11b16c3909de.png) [^134]

\

got the error because at build time i didn't pass user details

![776812b0-efc8-4da0-9945-224ab93b4ed7.png|1190.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/776812b0-efc8-4da0-9945-224ab93b4ed7.png) [^135]

\

now rebuilding by passing variables

```
docker build -t arg:v1 --build-arg username=satya .
```

![0e787e0b-7945-4efe-9ea3-9c740197998a.png|1185.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/0e787e0b-7945-4efe-9ea3-9c740197998a.png) [^136]

\

```
docker run -d arg:v1
docker exec -it 3966445 bash
id
```

![ce404d2d-a8f8-4abc-9158-0893f30a60d6.png|1165.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/ce404d2d-a8f8-4abc-9158-0893f30a60d6.png) [^137]

\

\

using best combination with arg & env

![cdaad16d-8b74-400d-8507-7f6430e9bd5a.png|1030.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/cdaad16d-8b74-400d-8507-7f6430e9bd5a.png) [^138]

![d89cea25-215b-4a2d-a552-45b9b95cca05.png|1123.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/d89cea25-215b-4a2d-a552-45b9b95cca05.png) [^139]

\

```
docker build -t arg:v1 --build-arg username=siva --build-arg course=devops --build-arg trainer=chowdary .
```

![d9ebb148-e21a-4a03-8afb-1a23484125a6.png|1038.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/d9ebb148-e21a-4a03-8afb-1a23484125a6.png) [^140]

\

```
docker run -d arg:v1
```

![e8453e12-e70f-4f2a-9735-683d28bcbef2.png|1133.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/e8453e12-e70f-4f2a-9735-683d28bcbef2.png) [^141]

\

```
docker exec -it fd88dfdf0 bash
env
```

![01a33eaa-560d-40d0-8fd9-03d191f2670e.png|1130.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/01a33eaa-560d-40d0-8fd9-03d191f2670e.png) [^142]

\

# <mark style="background-color:#F8914D;">**ONBUILD Instruction**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![042172e2-c160-49eb-900c-e8dfa4d76f9f.png|1043.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/042172e2-c160-49eb-900c-e8dfa4d76f9f.png) [^143]

![66b58e1a-29b1-45a5-a00f-8fc0805aae69.png|1077.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/66b58e1a-29b1-45a5-a00f-8fc0805aae69.png) [^144]

\

![7a5ea49d-bf78-4ce6-995d-8987db0f471f.png|1103.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7a5ea49d-bf78-4ce6-995d-8987db0f471f.png) [^145]

\

```
docker build -t on:v1 .
```

![0c832ccd-d4ec-4017-897d-68829a8f87d7.png|1098.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/0c832ccd-d4ec-4017-897d-68829a8f87d7.png) [^146]

\

![feea4aea-0d20-4b5f-8e30-ba5ac3f00f07.png|1121](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/feea4aea-0d20-4b5f-8e30-ba5ac3f00f07.png) [^147]

\

![03673ae9-e16c-4b87-a62f-f5037372fd4b.png|1118.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/03673ae9-e16c-4b87-a62f-f5037372fd4b.png) [^148]

\

without index.html it will through error as below

```
docker build -t on-test:v1 .
```

![6625ea5d-f19d-44e1-b56e-efb6ad0c5141.png|1131.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6625ea5d-f19d-44e1-b56e-efb6ad0c5141.png) [^149]

![65956a39-ec53-4a9d-a3f2-2d24881d2374.png|1135.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/65956a39-ec53-4a9d-a3f2-2d24881d2374.png) [^150]

\

now we can have index.html file 

![1f170690-3d43-4e67-88ee-498dd1f2240a.png|941.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/1f170690-3d43-4e67-88ee-498dd1f2240a.png) [^151]

\

```
docker build -t on-test:v1 .
```

![25e1d917-6329-4a86-822e-d9b1961aeba9.png|1089.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/25e1d917-6329-4a86-822e-d9b1961aeba9.png) [^152]

\

\

```
docker run -d -p 8083:80 on-test:v1
```

![b6906812-d19e-4b46-b06b-a06b4a864b14.png|1266.3333740234375](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b6906812-d19e-4b46-b06b-a06b4a864b14.png) [^153]

\

it worked

![9d60cab6-fca0-4a8f-afc3-29099344a0e7.png|849](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/9d60cab6-fca0-4a8f-afc3-29099344a0e7.png) [^154]

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

[^1]: Physical Servers, Virtualisation, Containerization
    Independent houses, apartments, individual rooms
    Independent houses
    advantages :
    \* own space, privacy
    dis advantages :
    \* electricity
    \* water
    \* internet
    \* 6months - 1year time
    I
    \* only one family can stay

[^2]: Physical Servers --> booting time is very high
    16GB RAM, 1TB HD

[^3]: apartments/Virtualisation
    dis advantages:
    \* shared area (corridor, park, lift, badminton court, pool, etc. )
    advantages :
    \* water, electricity, internet everything will be taken care
    \* construction time is relatively very less
    \* cost is medium
    booting time is very less compared to physical server
    a big physical server will be there --> 16GB RAM, 1TB HD
    we will divide this big server into multiple logical servers
    Host OS --> windows
    VM Ware --> Hypervisor I
    Guest OS
    1GB RAM
    Ubuntu

[^4]: Guest OS-3
    1GB RAM
    Fedora
    100GB HD
    0. 1GB RAM, 10GB HD
    resource utilisation is good in VM

[^5]: single rooms
    1 flat --> 3BHK
    everyone will take one room, hall and kitchen are shared
    advantages :
    \* very fast
    \* very less cost
    we will have containers installed in VM. ..
    containers are isolated from each other, system resources are shared. ..
    containers take resources based on demand, it don't block resources
    boot time is very less --> with in seconds your application is available

[^6]: configuration == all your things
    container/image = Fat OS (4GB/3GB) + application run time + created users + created a
    directory + installed application
    AMI = server + configured the server using ansible + stop server + take AMI
    Amazon machine image
    docker image = Base OS (5MB-250MB) + application run time + created users + created a
    directory + installed application = max 500MB
    legacy = frontend+backend ==> war file and ear file = 100MB
    frontend and backend divided
    VM for monolithic apps
    frontend = UI = VM-1 = 50 MB
    backend = cart+catalogue+user = VM-2 = 50MB
    Microservices --> completely independent applications
    10/5MB you dont need VM to run a microservice. containers are a best approach

[^7]: Instances (1/4) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    < 1 >
    -
    Name _
    Instance ID
    Instance state
    4
    Instance type
    Status check
    Alarm status
    Availab
    O
    Jenkins
    i-Of92b41f9c2767aa7
    Stopped Q Q
    t3.small
    View alarms +
    us-east
    O
    Agent
    i-061d15bcdfe 1375e6
    Stopped Q Q
    3.small
    View alarms +
    us-east
    docker
    i-0296302f249f8ccb2
    Pending Q Q
    t2.micro
    View alarms +
    us-east
    nexus
    i-0c90690a9a2d9179a
    Stopped Q Q
    t3.medium
    View alarms +
    us-east

[^8]: X
    docs.docker.com/engine/install/centos/
    docker
    Manuals
    Samples
    FAQ
    docs
    Guides
    Reference
    Overview
    Manuals / Docker Engine / Install / CentOS
    Get Docker
    Docker Desktop
    <
    Install Docker Engine on CentOS
    Docker Extensions
    V
    To get started with Docker Engine on CentOS, make sure you meet the prerequisites, and then follow the
    <
    Docker Scout
    installation steps.
    Docker Engine
    >
    Overview
    Prerequisites
    Install
    OS requirements
    Overview
    To install Docker Engine, you need a maintained version of one of the following CentOS versions:
    CentOS
    Debian
    . CentOS 7
    Fedora
    . CentOS 8 (stream)
    RHEL ($390x)
    . CentOS 9 (stream)
    SLES
    The centos-extras repository must be enabled. This repository is enabled by default. If you have disabled it.
    Ubuntu
    you need to re-enable it.

[^9]: 54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ sudo su -
    54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2. micro \| null
    \[ root@ip-172-31-88-21 \~ \]# yum install -y yum-utils
    Centos Stream 8 - AppStream
    Centos Stream 8 -
    BaseOS
    Centos Stream 8 - Extras

[^10]: 54 . 173 . 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# yum-config-manager --add-repo https: / /download. docker. com/linux/centos/docker-ce . repo
    Adding repo from: https: / /download. docker. com/linux/centos/docker-ce . repo
    54 . 173. 241. 201 \| 172. 31. 88.21 \| t2. micro \| null
    root@ip-172-31-88-21

[^11]: 54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# yum install docker-ce docker-ce-cli containerd. io docker-buildx-plugin docker-compose-plugin
    Docker CE Stable - x86 64
    835 kB/s \| 57 kB
    00: 00

[^12]: 54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# systemctl start docker
    54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# systemctl enable docker
    Created symlink /etc/systemd/system/multi-user . target. wants/docker . service - /usr/lib/systemd/system/docker . service.
    54 . 173 . 241. 201 \| 172.31.88.21 \| t2.micro \| null
    root@ip-172-31-88-21 \~ \]# systemctl status docker
    docker . service - Docker Application Container Engine
    Loaded: loaded (/usr/lib/systemd/system/docker . service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2024-02-08 02:36:47 UTC; 10s ago
    Docs: https: / /docs . docker . com
    Main PID: 6512 (dockerd)
    Tasks : 7
    Memory: 64 . 3M
    CGroup: /system. slice/docker . service
    -6512 /usr/bin/dockerd -H fd: // --containerd=/run/containerd/containerd. sock
    Feb 08 02:36:47 ip-172-31-88-21. ec2. internal systemd \[1\] : Starting Docker Application Container Engine.. .
    Feb 08 02:36:47 ip-172-31-88-21. ec2. internal dockerd \[6512\]: time="2024-02-08T02: 36: 47.2950925752" level=info msg="Starting

[^13]: 54 . 173. 241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES

[^14]: \[ centos@ip-172-31-88-21 \~ \]$ sudo su
    Last login: Thu Feb 8 02:35:18 UTC 2024 on pts/0
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# usermod -aG docker centos
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# exit
    logout

[^15]: 54 . 173. 241. 201 \| 172.31.88.21 \| t2. micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    54 . 173. 241 . 201 \| 172. 31.88.21 \| t2. micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$

[^16]: image vs container
    AMI vs EC2 instance

[^17]: \[ centos@ip-172-31-88-21 \~ \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    54 . 173. 241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker pull nginx
    Using default tag: latest
    latest: Pulling from library/nginx
    c57ee5000d61: Pull complete
    960163235c08: Pull complete
    f24a6f652778: Pull complete
    9f3589a5fc50: Pull complete
    fObd99a47d4a: Pull complete
    398157bc5c51: Pull complete
    lef1cla36ec2: Pull complete
    Digest: sha256: 84c52did55c467e12ef85cad6a252c0990564f03c4850799bf41dd738738691f
    Status: Downloaded newer image for nginx : latest
    docker . io/library/nginx : latest

[^18]: 54. 173. 241.201 \| 172.31.88.21 \| t2.micro \| null
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

[^19]: docker images --> show you the images exist in server
    docker pull nginx
    nginx AMI = any OS + install nginx = nginx AMI
    nginx image = base os + nginx installed

[^20]: Instances \| EC2 \| us-east-1
    x . Why Containerization is popul X \| G docker install - Google Search
    X
    Docker Hub
    X
    C hub.docker.com/explore
    dockerhub
    Explore
    Repositories
    Organizations
    Search Docker Hub
    hs
    joindevops
    Search by repository nam Q
    All Content
    Create repository
    joindevops / shipping
    & Inactive : 0
    $ 159
    Public
    Contains: Image \| Last pushed: 3 months ago
    joindevops / user
    Q Inactive : 0
    2 161
    Public
    Contains: Image \| Last pushed: 3 months ago
    joindevops / catalogue
    & Inactive
    $ 190
    Public
    Contains: Image \| Last pushed: 3 months ago
    joindevops / app2
    Q inactive : 0
    $ 3
    Public
    Contains: Image \| Last pushed: 3 months ago
    joindevops / app1
    @ Inactive # 0
    $ 3
    Public
    Contains: Image \| Last pushed: 3 months ago

[^21]: F
    C hub.docker.com/search?q=nginx
    ah dockerhub
    Explore
    Repositories
    Organizations
    nginx
    ?
    Filters
    1 - 25 of 10,000 results for nginx.
    Best Match
    Products
    Images
    nginx @
    $18+ . 10K+
    Pulls: 48,038,433
    Extensions
    Updated a day ago
    Last week
    Plugins
    Official build of Nginx.
    Linux unknown PowerPC 64 LE IBMZ x86-64 ARM unknown ARM 64 386
    Trusted Content
    mips64le
    Learn more C
    Docker Official Image
    > verified Publisher
    unit
    $ 100K+ . 21
    Pulls: 9,531
    Sponsored OSS
    N Unit
    Updated 2 hours ago
    Last week
    Official build of NGINX Unit: Universal Web App Server
    Operating Systems
    Linux unknown unknown x86-64 ARM 64
    Linux
    Learn more
    Windows
    nginxinc/nginx-unprivileged
    $ 500M+ . $140
    Pulls: 6,408,484
    Architectures
    N
    By NGINX Inc. . Updated 9 days ago
    Last week
    ARM
    Unprivileged NGINX Dockerfiles
    ARM 64
    unknown Linux arm64 mips64le ppc64le IBMZ unknown 386 x86-64 arm
    Learn more C
    IBM POWER

[^22]: 54 . 173 . 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker pull nginx : stable-bullseye
    stable-bullseye: Pulling from library/nginx
    70ba6f391a98: Extracting \[===
    \] 5. 898MB/31 . 42MB
    19952d9b2082: Download complete
    5e6eddd75528: Download complete
    d66396a24267: Download complete
    bel10caac6d: Download complete

[^23]: 54 . 173 . 241. 201 \| 172. 31.88.21 \| t2. micro \| null
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
    nginx
    stable-bullseye
    3a8963c304a2
    10 months ago
    142MB
    54 . 173 . 241.201 \| 172. 31.88.21 \| t2. micro \| null
    \[ centos(ip-172-31-88-21 \~ \]$

[^24]: 54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker pull nginx : alpine
    alpine: Pulling from library/nginx
    619be1103602: Pull complete
    6c866301bd2c: Pull complete
    9e03973bc803: Pull complete
    a3a550dcd386: Pull complete
    d18780149681: Pull complete
    4ea31a8fb875: Pull complete
    e57ebb3e2067: Pull complete
    efb7d60b16cf: Pull complete
    Digest: sha256: f2802c2a9d09c7aa3ace27445dfc5656ff24355da28e7b958074a0111e3fc076
    Status: Downloaded newer image for nginx : alpine
    docker . io/library/nginx : alpine
    54 . 173 . 241.201 \| 172.31. 88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    nginx
    alpine
    2b70e4aaac6b
    3 months ago
    42 . 6MB
    nginx
    latest
    b690f5f0a2d5
    3 months ago
    187MB
    nginx
    stable-bullseye
    3a8963c304a2
    10 months ago
    142MB

[^25]: 54. 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker create nginx: latest
    ebad478b491f981ae8bad90bfb863ble7dd84f725786e04b5683df22c26202

[^26]: 54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    eb6ad478b491
    nginx : latest
    " / docker-entrypoint..."
    About a minute ago
    Created
    goofy blackwell
    54 . 173 . 241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ centos(ip-172-31-88-21 \~ \]$

[^27]: 54. 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    eb6ad478b491
    nginx : latest
    " /docker-entrypoint...."
    About a minute ago
    Created
    goofy_blackwell
    54 . 173. 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker start ebbad478b491
    ebbad478b491

[^28]: 54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    ebbad478b491
    nginx : latest
    "/ docker-entrypoint ...."
    About a minute ago
    Up 3 seconds
    80/tcp
    goofy_blackwell
    54 . 173 . 241 . 201 \| 172. 31. 88.21 \| t2. micro \| null

[^29]: 54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    eb6ad478b491
    nginx : latest
    "/docker-entrypoint..."
    About a minute ago
    Up 3 seconds
    80/tcp
    goofy_blackwell
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker rm ebbad478b491
    Error response from daemon: cannot remove container "/goofy_blackwell": container is running: stop the container before removing or fo
    ce remove

[^30]: 54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker stop ebbad478b491
    eb6ad478b491
    54. 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker rm ebbad478b491
    ebbad478b4191

[^31]: docker rm container id
    remove images --> docker rmi <image-name>/id
    pull+create+start = docker run

[^32]: 54 . 173 . 241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    alpine
    latest
    05455a08881e
    12 days ago
    7. 38MB
    nginx
    alpine
    2b70e4aaac6b
    3 months ago
    42 . 6MB
    nginx
    latest
    b690f5f0a2d5
    3 months ago
    187MB
    nginx
    stable-bullseye
    3a8963c304a2
    10 months ago
    142MB
    54 . 173 . 241.201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker rmi 05455a0888le
    Untagged: alpine : latest
    Untagged: alpine@sha256: c5b1261d6d3e43071626931fc004f70149baeba2c8ec672bd4f27761f8elad6b
    Deleted: sha256: 05455a0888lea9cf0e752bc48e61bbd71a34c029bb13df01e40e3e70e0d007bd
    Deleted: sha256: d4fc045c9e3a848011de66f34b81f052d4f2c15a17bb196d637e526349601820
    54. 173 . 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker rmi 2b70e4aaac6b
    Untagged: nginx : alpine
    Untagged: nginx@sha256: f2802c2a9d09c7aa3ace27445dfc5656ff24355da28e7b958074a011le3fc076
    Deleted: sha256: 2b70e4aaac6b5370bf3a556f5e13156692351696dd5d7c5530d117aa21772748
    Deleted: sha256: a496f0b961a246ab175cffe3e3f7f6cf332bb58be9687f987b89b1d2e5cobbd2
    Deleted: sha256: f1d5cb8658ff325f7fdddc83454db20b289fOfc5f56453f31e32a6aa81d9e528
    Deleted: sha256: 7e79374bbe3e19366e34c8d7c9cf0844e7f49822e6fcd63e2d5db9cac6004034

[^33]: 54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker images -a -q
    b690f5f0a2d5
    3a8963c304a2
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker rmi docker images -a -q'
    Untagged: nginx: latest
    Untagged: nginx@sha256: 84c52dfd55c467e12ef85cad6a252c0990564f03c4850799bf41dd738738691f
    Deleted: sha256: b690f5f0a2d535cee5e08631aa508fef339c43bb91d5b1f7d77ala05cea021a8
    Deleted: sha256: 2599673318db03e2df10bca9b4167be668b9579d72c3cedd1436addcbc4686f
    Deleted: sha256: 3dfa00af383371dobb76086fde405df32b75247bdf6db81110d992284140c5a3
    Deleted: sha256: 22b6d0744dd5a77166622ec69cc6520f63cdfOdd65b9c96934658c3684aef14
    256
    2fob

[^34]: \[ centos@ip-172-31-88-21 \~ \]$ docker run nginx
    Unable to find image 'nginx: latest' locally
    latest: Pulling from library/nginx
    c57ee5000d61: Extracting \[==
    \] 27. 13MB/29 . 15MB
    960163235c08: Download complete
    f24a6f652778: Download complete
    9f3589a5fc50: Download complete
    fObd99a47d4a: Download complete
    398157bc5c51: Download complete

[^35]: 9f3589a5fc50: Pull complete
    fObd99a47d4a: Pull complete
    398157bc5c51: Pull complete
    lef1cla36ec2: Pull complete
    Digest: sha256: 84c52dfd55c467e12ef85cad6a252c0990564f03c4850799bf41dd738738691f
    Status: Downloaded newer image for nginx : latest
    /docker-entrypoint. sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
    /docker-entrypoint. sh: Looking for shell scripts in /docker-entrypoint.d/
    /docker-entrypoint. sh: Launching /docker-entrypoint. d/10-listen-on-ipv6-by-default. sh
    10-listen-on-ipv6-by-default. sh: info: Getting the checksum of /etc/nginx/conf.d/default. conf
    10-listen-on-ipv6-by-default. sh: info: Enabled listen on IPV6 in /etc/nginx/conf.d/default. conf
    /docker-entrypoint. sh: Sourcing /docker-entrypoint. d/15-local-resolvers . envsh
    /docker-entrypoint. sh: Launching /docker-entrypoint. d/20-envsubst-on-templates . sh
    /docker-entrypoint. sh: Launching /docker-entrypoint. d/30-tune-worker-processes . sh
    /docker-entrypoint. sh: Configuration complete; ready for start up
    2024/02/08 02:50:56 \[notice\] 1#1: using the "epoll" event method
    2024/02/08 02:50:56 \[notice\] 1#1: nginx/1.25.3
    2024/02/08 02:50:56 \[notice\] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14)
    2024/02/08 02:50:56 \[notice\] 1#1: OS: Linux 4.18.0-535.e18.x86 64
    2024/02/08 02:50:56 \[notice\] 1#1: getrlimit (RLIMIT NOFILE) : 1048576: 1048576
    2024/02/08 02:50:56 \[notice\] 1#1: start worker processes
    2024/02/08 02:50:56 \[notice\] 1#1: start worker process 29

[^36]: 54 . 173 . 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    cb399239ceed
    nginx
    " / docker-entrypoint...."
    20 seconds ago
    Exited (0) 3 seconds ago
    vigorous mestorf
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2. micro \| null
    172-31-88-21

[^37]: 54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker run -d nginx
    61afeb4751bb34848b452077d8c1b8c692cc12593682f983cb2a88494f3c382f
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    61afeb4751bb
    nginx
    "/ docker-entrypoint ...."
    3 seconds ago
    Up 2 seconds
    80/top
    unruffled carver
    54 . 173 . 241 . 201 \| 172. 31.88.21 \| t2. micro \| null
    -88-2

[^38]: 54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    61afeb4751bb
    nginx
    " /docker-entrypoint ...."
    3 seconds ago
    Up 2 seconds
    80/tcp
    unruffled carver
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker rm -f 61afeb4751bb
    61afeb4751bb

[^39]: 0-65, 535 ports
    0-65, 535 a container will have

[^40]: C
    Not secure 54.173.241.201
    This site can't be reached
    54.173.241.201 refused to connect.
    Try.
    . Checking the connection
    . Checking the proxy and the firewall
    ERR CONNECTION_REFUSED

[^41]: VM
    8080
    docker
    80

[^42]: 54. 173. 241.201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker run -d -p 8080:80 nginx
    8553a2804a0921e3580960e61d1f0a90030e66dd77b1700174195edeaaacd2e
    54. 173 .241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$

[^43]: F
    A Not secure 54.173.241.201:8080
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^44]: \[ centos@ip-172-31-88-21 \~ \]$ docker run -d -p 8080:80 nginx
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

[^45]: C
    - . . .
    docker
    8080
    docker
    80
    docker

[^46]: 54 . 173. 241 . 201 \| 172 . 31. 88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker run -d -p 8082:80 --name nginx daws76s nginx
    a764b7f56dbbb1la66b30feffc3d37c6506520f0006de497ebc696af59bbcla9
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docke rps
    -bash: docke: command not found
    54 . 173 . 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    a764b7 f56dbb
    nginx
    "/ docker-entrypoint...."
    5 seconds ago
    Up 4 seconds
    0. 0. 0. 0:8082->80/tcp, : : : 8082->80/tcp
    nginx daws 76s
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    centos@ip-172-31-88-21

[^47]: 54 . 173. 241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker exec -it nginx daws76s bash
    root@a764b7 f56dbb : /#

[^48]: \[ centos@ip-172-31-88-21 \~ \]$ docker exec -it nginx daws76s bash
    root@a764b7f56dbb: /# cat /etc/\*release
    PRETTY NAME="Debian GNU/Linux 12 (bookworm) "
    NAME="Debian GNU/Linux"
    VERSION ID="12"
    VERSION="12 (bookworm)
    VERSION CODENAME=bookworm
    ID=debian
    HOME URL="https: //www. debian.org/"
    SUPPORT URL="https : //www. debian . org/support"
    BUG REPORT URL="https : //bugs . debian.org/"
    root@a 764b7 f56dbb : /#

[^49]: \[ centos@ip-172-31-88-21 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    S
    a764b7 f56dbb
    nginx
    " /docker-entrypoint...."
    About a minute ago
    Up About a minute
    x daws 76s
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ docker inspect a764b7f56dbb
    "Id": "a764b7f56dbbb1la66b30feffc3d37c6506520f0006de497ebc696af59bbcla9",
    "Created": "2024-02-08T03 : 01 : 04 .2670157212",
    "Path": "/docker-entrypoint. sh",

[^50]: "Networks" : {
    "bridge" : {
    " IPAMConfig" : null,
    "Links": null,
    "Aliases": null,
    "MacAddress": "02 : 42: ac: 11 : 00:02"
    "NetworkID": "82e677c16175d903bc48e37a47ac77d292bb36fddf2ae0ba286a82d4566982c4",
    "EndpointID": "4al167e2dc9768b6c49c1f2f6134a014b3655b8bc5dadebe7677e8ff6f25b654",
    "Gateway": "172. 17.0.1"
    "IPAddress": "172 . 17.0.2"
    "IPPrefixLen" : 16,
    "IPV6Gateway" : ""
    "GlobalIPV6Address" : ""
    "GlobalIPv6PrefixLen" : 0,
    "DriverOpts": null,
    "DNSNames": null

[^51]: XJ
    File Edit Selection View Go
    EXPLORER
    ...\\shipp
    V
    REPOS
    user
    40
    > .github
    19
    > ansible
    50
    > catalogue
    51
    > catalogue-deploy
    52
    > concepts
    53
    > dockerfiles
    54
    55
    > learn-git
    56

[^52]: chowd@chowdary MINGW64
    $ cd e/AWSDevops /Repos /dockerfiles/
    chowd@chowdary MINGW64 /e/AWSDevops /Repos /dockerfiles (main)
    $ git init
    Initialized empty Git repository in E: /AWSDevops/Repos/dockerfiles/.git/
    chowd@chowdary MINGW64 /e/AWSDevops/Repos/dockerfiles (main)
    $ git remote add origin git@github . com: chilops/dockerfiles. git
    chowd@Chowdary MINGW64 /e/AWSDevops/Repos /dockerfiles (main)

[^53]: FROM
    it should be the first instruction in Dockerfile
    docker build -t <URL>/<USERNAME> /<IMAGE : <VERSION> .
    url --> docker . io
    ECR -->
    Nexus Docker registry -->
    docker build -t joindevops/from: v1 .
    docker login I
    docker build -t image : version

[^54]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/notes (master)
    $ cd . ./dockerfiles/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/dockerfiles (main)
    S git add . ; git commit -m "docker"; git push origin master
    \[main (root-commit) 39448c9\] docker
    1 file changed, 1 insertion(+)
    create mode 100644 FROM/Dockerfile
    error: src refspec master does not match any
    error: failed to push some refs to 'github.com: daws-76s/dockerfiles.git'
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/dockerfiles (main)
    S git add . ; git commit -m "docker"; git push origin main
    On branch main
    nothing to commit, working tree clean

[^55]: File Edit Selection View Go
    . .
    9 repos
    EXPLORER
    Dockerfile U X
    V
    REPOS
    dockerfiles > FROM > < Dockerfile > ...
    > .github
    1
    FROM centos : 8
    > ansible
    90
    > catalogue
    10
    > catalogue-deploy
    > concepts
    dockerfiles \\ FROM
    Dockerfile
    U
    learn-git

[^56]: 34.229.144.33
    34 . 229. 144. 33 \| 172.31.22.2 \| t2.micro \| null
    \[ centos@ip-172-31-22-2 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    34. 229. 144. 33 \| 172.31.22.2 \| t2.micro \| null
    \[ centos@ip-172-31-22-2 \~ \]$ git clone https: //github. com/daws-76s/dockerfiles. git
    Cloning into 'dockerfiles'
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4), done.
    remote: Total 4 (delta 0) , reused 4 (delta 0) , pack-reused 0
    Receiving objects: 100% (4/4) , done.
    34 . 229. 144. 33 \| 172.31.22.2 \| t2. micro \| null
    \[ centos@ip-172-31-22-2 \~ \]$

[^57]: 34. 229. 144. 33 \| 172.31.22.2 \| t2. micro \| null
    \[ centos@ip-172-31-22-2 \~ \]$ cd dockerfiles/
    34 . 229. 144. 33 \| 172.31.22.2 \| t2.micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos(ip-172-31-22-2 \~/dockerfiles \]$ cd FROM/
    34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles . git
    \[ centos(ip-172-31-22-2 \~/dockerfiles/FROM \] $

[^58]: 34 . 226.215.227 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centos@ip-172-31-44-186 \~/dockerfiles/from \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    from
    v1
    6677f032afc5
    2 years ago
    231MB

[^59]: 34 . 226. 215.227 \| 172. 31. 44.186 \| t2.micro \| https: / /github. com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/from \]$ docker tag from:v1 chilops/repol:v1
    34 . 226. 215.227 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centos@ip-172-31-44-186 \~/dockerfiles/from \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    from
    v1
    6677f032afc5
    2 years ago
    231MB
    chilops/repol
    v1
    6677 f032afc5
    2 years ago
    231MB
    34 . 226.215.227 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centos@ip-172-31-44-186 \~/dockerfiles/from \]$ docker push chilops/repol:v1
    The push refers to repository \[docker . io/chilops/repol\]
    74dddec08fa: Pushed
    v1: digest: sha256: 07402cbec165bf29801e72fc0e680f9baa8f1666c2cf2dla87c0fbelb3850bla size: 529

[^60]: 34 . 226. 215.227 \| 172 . 31. 44.186 \| t2.micro \| https: / /github. com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/from \]$ docker tag from:v1 chilops/repol:v2
    34 . 226. 215.227 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centos@ip-172-31-44-186 \~/dockerfiles/from \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    chilops/repol
    v1
    6677f032afc5
    2 years ago
    231MB
    chilops/repol
    v2
    6677f032afc5
    2 years ago
    231MB
    from
    v1
    6677f032afc5
    2 years ago
    231MB
    34. 226.215.227 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centos@ip-172-31-44-186 \~/dockerfiles/from \]$ docker push chilops/repol :v2
    The push refers to repository \[docker . io/chilops/repol\]
    74dddec08fa: Layer already exists
    v2: digest: sha256: 07402cbec165bf2980le72fc0e680f9baa8f1666c2cf2dla87c0fbelb3850bla size: 529

[^61]: C
    https://hub.docker.com/repository/docker/chilops/repo1/general
    I CP
    NO
    . . .
    docker hub
    Explore
    Repositories
    Organizations
    Q
    Search Docker Hub
    ctrl+K
    ?
    C
    chilops / Repositories / repo1 / General
    Using 0 of 1 private repositories.
    General
    Tags
    Builds
    Collaborators
    Webhooks
    Settings
    chilops/repo1
    Docker commands
    Public View
    Updated 7 minutes ago
    To push a new tag to this repository:
    My Working repository for chilops
    docker push chilops/repol:tagname
    This repository does not have a category INCOMPLETE
    Tags
    Automated Builds
    This repository contains 2 tag(s).
    Manually pushing images to Hub? Connect your account to GitHub or Bitbucket to
    automatically build and tag new images whenever your code is updated, so you
    Tag
    OS
    Type
    Pulled
    Pushed
    can focus your time on creating.
    O v2
    Image
    34 minutes ago
    7 minutes ago
    Available with Pro, Team and Business subscriptions. Read more about automated
    builds 7.
    O v1
    Image
    34 minutes ago
    9 minutes ago
    Upgrade
    See all

[^62]: EXPLORER
    Dockerfile X
    V
    REPOS
    dockerfiles > RUN > Dockerfile
    dockerfiles
    1
    #almalinux is same as centos
    FROM
    2
    FROM almalinux : 8
    3
    Dockerfile
    RUN yum install nginx -y
    V
    RUN
    I
    Dockerfile

[^63]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/RUN \]$ docker build -t run: v1
    +\] Building 0.2s (7/7) FINISHED
    docker : defa
    =>
    \[internal\] load build definition from Dockerfile
    => => transferring dockerfile: 1078
    =>
    \[internal\] load metadata for docker. io/library/almalinux : 8
    OO
    =>
    \[auth\] library/almalinux:pull token for registry-1 . docker . io
    =>
    \[internal\] load . dockerignore
    =>
    => transferring context: 2B

[^64]: 34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/RUN \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    run
    v1
    7e91b3bed90f
    23 hours ago
    303MB
    from
    v1
    22773018c042
    2 years ago
    231MB
    joindevops/from
    v1
    22773018c042
    2 years ago
    231MB

[^65]: RUN VS CMD
    systemctl start catalogue
    it will create one nodej's process and this process will run for infinte time...
    CMD instruction is to make your container running..
    RUN --> runs at the time of image building
    CMD
    --> runs at the time container creation

[^66]: V
    REPOS
    dockerfiles > CMD > Dockerfile
    dockerfiles
    FROM almalinux : 8
    2
    V CMD
    RUN yum install nginx -y
    3
    CMD
    U
    \[ "nginx", "-g", "daemon off;\]
    Dockerfile
    V FROM
    Dockerfile
    > RUN

[^67]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos
    $ cd dockerfiles/
    X1 carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/dockerfiles (main)
    $ git add . ; git commit -m "dockerfiles"; git push origin main

[^68]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/RUN \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 4 (delta 0) , reused 4 (delta 0) , pack-reused 0

[^69]: \[ centos@ip-172-31-22-2 \~/dockerfiles/CMD \]$ docker build -t cmd:v1 .
    \[+\] Building 0.2s (7/7) FINISHED
    docker : default
    => \[internal\] load build definition from Dockerfile
    0 . 0s
    => => transferring dockerfile: 1118
    0 . 0s
    =>
    (internal\] load metadata for docker . io/library/almalinux: 8
    0 . 1s
    =>
    \[auth\] library/almalinux :pull token for registry-1 . docker . io
    0 . 0s
    =>
    \[internal\] load . dockerignore
    0 . 0s
    =>
    => transferring context: 2B
    0 . 0s
    =>
    \[1/2\] FROM docker . io/library/almalinux: 80sha256: 286bebaacc46c498394238b7a276991921829Ed94460b
    0 . 0s
    =>
    CACHED (2/2\] RUN yum install nginx -y
    0 . 0s
    => exporting to image
    0 . 0s
    =>
    => exporting layers
    0 . 0s
    =>
    => writing image sha256: 189laa2abbb64c5a50e67d456847abaa6c9c73f5bfa91cbea844bef3bfeef48a
    0 . 0s
    => => naming to docker . io/library/cad: v1
    0 . 03

[^70]: \[ centos@ip-172-31-22-2 \~/dockerfiles/CMD \]$ docker run -d -p 80:80 cmd: v1
    29fca49f712e54b3aecf7896513155cd99b800612589c209bcfbdae726a196ce
    34 . 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/CMD \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    29fca49f712e
    cmd : v1
    "nginx -g 'daemon of.."
    2 seconds ago
    Up 1 second
    0. 0. 0. 0:80->80/tcp, : : :8
    0->80/tcp
    nervous dubinsky

[^71]: Instances \| EC X () daws-76s/doc x @ Dockerfile ref. X \| G nginx running X N Deploying NC X \] & docker - How X
    Test Page for X
    +
    -
    C
    A Not secure 34.229.144.33
    Welcome to nginx on AlmaLinux!
    This page is used to test the proper operation of the nginx HTTP server after it has been installed. If you can read this page, it means that the web server installed at th
    working properly.
    Website Administrator
    This is the default index. html page that is distributed with nginx on AlmaLinux. It is located in /usr/share/nginx/html.
    You should now put your content in a location of your choice and edit the root configuration directive in the nginx configuration file /etc/nginx/nginx. conf.

[^72]: 100 shopping covers all are white, you know only when you open them
    you can give some lables to them to identify easily

[^73]: LABEL
    LABEL <key>=<value> <key>=<value> <key>=<value> ...
    The LABEL instruction adds metadata to an image. A LABEL is a key-value pair. To include spaces within
    a LABEL value, use quotes and backslashes as you would in command-line parsing. A few usage
    examples:
    LABEL "com . example . vendor" ="ACME Incorporated"
    LABEL com . example . label-with-value="foo"
    LABEL version="1.0"
    LABEL description="This text illustrates
    that label-values can span multiple lines."

[^74]: EXPLORER
    . .
    Dockerfile .. \\RUN
    Dockerfile ... \\CMD
    Dockerfile .. \\LABEL X
    REPOS
    dockerfiles > LABEL > Dockerfile
    dockerfiles
    FROM almalinux : 8
    N
    V CMD
    LABEL TRAINING="DEVOPS"
    1
    3
    Dockerfile
    TRAINER="Sivakumar"
    4
    DURATION="120HRS" \\
    FROM
    5
    org. opencontainers . image . authors="info@joindevops . com"
    Dockerfile
    V LABEL
    Dockerfile
    > RUN

[^75]: 34 . 229. 144. 33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/CMD \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 4 (delta 0) , reused 4 (delta 0) , pack-reused 0
    Unpacking objects: 100% (4/4) , 425 bytes \| 425.00 KiB/s, done.

[^76]: \[ centos@ip-172-31-22-2 \~/dockerfiles/LABEL \]$ docker build -t. label:v1
    \[+\] Building 0.2s (2/3)
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 . 0s
    =>
    => transferring dockerfile: 1318
    0 . 0=
    => \[internal\] load metadata for docker . io/library/almalinux: 8
    0. 2s

[^77]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/LABEL \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    run
    7e91b3bed90f
    24 hours ago
    303MB
    cmd
    1891aa2abbb6
    24 hours ago
    303MB
    label
    be35001a56e3
    2 months ago
    190MB
    joindevops/from
    22773018c042
    4 years ago
    231MB
    from
    22773018c042
    2 years ago
    231MB

[^78]: \[ centos@ip-172-31-22-2 \~/dockerfiles/LABEL \]$ docker images --filter label=TRAINER=Sivakumar
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    label
    v1
    be35001a56e3
    2 months ago
    190MB
    34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/LABEL \]$

[^79]: The EXPOSE instruction informs Docker that the container listens on the specified network ports at
    runtime. You can specify whether the port listens on TCP or UDP, and the default is TCP if you don't specify
    a protocol.

[^80]: V REPOS
    dockerfiles > EXPOSE > Dockerfile
    dockerfiles
    H
    FROM almalinux : 8
    CMD
    2
    RUN yum install nginx -y
    2
    EXPOSE 80/tcp
    Dockerfile
    4
    CMD \["nginx", " -g", "daemon off; "\]
    EXPOSE
    Dockerfile
    U
    > FROM

[^81]: 34. 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/LABEL \]$ cd . ./EXPOSE/
    34. 229. 144.33 \| 172. 31.22.2 \| t2.micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/EXPOSE \]$ docker build -t expose:v1 .
    \[+\] Building 0.3s (7/7) FINISHED
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 . 0s
    => => transferring dockerfile: 1258
    0 . 0s
    =>
    \[internal\] load metadata for docker. io/library/almalinux: 8
    0. 23

[^82]: 34. 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/EXPOSE \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    cmd
    v1
    1891aa2abbb6
    24 hours ago
    303MB
    expose
    v1
    809034b75c3e
    24 hours ago
    303MB
    run
    7e91b3bed90f
    24 hours ago
    303MB
    label
    be35001a56e3
    2 months ago
    190MB
    joindevops/from
    22773018c042
    2 years ago
    231MB
    from
    22773018c042
    2 years ago
    231MB
    34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/EXPOSE \]$ docker inspect 809034b75c3e

[^83]: "AttachStdout": false,
    "AttachStderr": false,
    "ExposedPorts": {
    "80/top" : {}
    "Tty": false,
    "OpenStdin" : false,
    "StainOnce": false,
    "Env" :

[^84]: ENV
    ENV <key>=<value> ...
    The ENV instruction sets the environment variable <key> to the value <value> . This value will be in the
    environment for all subsequent instructions in the build stage and can be replaced inline in many as well.
    The value will be interpreted for other environment variables, so quote characters will be removed if they
    are not escaped. Like command line parsing, quotes and backslashes can be used to include spaces
    within values.
    Example:
    ENV MY_NAME="John Doe"
    ENV MY_DOG=Rex\\ The\\ Dog
    ENV MY_CAT=fluffy

[^85]: V REPOS
    dockerfiles > ENV > Dockerfile
    dockerfiles
    FROM almalinux : 8
    2
    CMD
    RUN yum install nginx -y
    3
    ENV TRAINING="DEVOPS"
    Dockerfile
    4
    TRAINER="Sivakumar"
    V ENV
    5
    DURATION="120HRS"
    Dockerfile
    CMD \["nginx", "-g", "daemon off; "\]
    EXPOSE
    Dockerfile

[^86]: 34. 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/EXPOSE \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4) , 416 bytes \| 416.00 KiB/s, done.
    From https://github. com/daws-76s/dockerfiles
    9671ee6. . 4f29f4a main
    -> origin/main

[^87]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENV \]$ docker build -t env:v1
    \[+\] Building 0.2s (6/6) FINISHED
    docker : default
    \[internal\] load build definition from Dockerfile
    0. 0s
    =>
    => transferring dockerfile: 1858
    0. 0s
    =>
    \[internal\] load metadata for docker . io/library/almalinux : 8
    0 . 1s
    =>
    \[internal\] load . dockerignore
    0. 0s
    =>
    => transferring context: 28
    0 . 0s
    =>
    \[1/2\] FROM docker . io/library/almalinux: 80sha256: 286bebaacc46c498394238b7a276991925829Ed94460b
    0. 0s
    =>
    CACHED \[2/2\] RUN yum install nginx -y
    0. 0s
    =>
    exporting to image
    0 . 0s
    =>
    => exporting layers
    0 . 0s
    =>
    =>
    writing image sha256: a51d44132302ee607ad5a47272841le8defef8609cb32d9150ae10laf8c19a37
    0. 0s
    =>
    => naming to docker . io/library/env: v1
    0 . 0s

[^88]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENV \]$ docker run -d -p 8080:80 env:v1
    e252c789e858868327a92ea14592caea2947d766530ce69d1268a70bldfd496e
    34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ENV \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    e252c789e858
    env : v1
    "nginx -g 'daemon of..."
    2 seconds ago
    Up 1 second
    0. 0. 0. 0:8080->80/tcp
    : : : 8080->80/tcp
    bold chaum
    29fca49f712e
    cmd : v1
    "nginx -g 'daemon of..."
    13 minutes ago
    Up 13 minutes
    0. 0.0. 0:80->80/tcp,
    : :80->80/tcp
    nervous_dubinsky
    34 . 229. 144. 33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ENV \] $

[^89]: 34 . 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ENV \]$ docker exec -it e252c789e858 bash
    \[root@e252c789e858 /\]# env
    TRAINING=DEVOPS
    LANG=C. utf8
    HOSTNAME=e252c'789e858
    DURATION=120HRS
    PWD=/
    HOME=/ root
    TERM=xterm
    TRAINER=Sivakumar
    SHLVL=1
    PATH=/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin
    LESSOPEN=\| \| /usr/bin/lesspipe . sh \*s
    =/usr/bin/env
    Troot@e252c789e858 /1#

[^90]: EXPLORER
    Dockerfile ... \\LABEL
    Dockerfile ...\\EXPOSE
    Dockerfile ...\\E
    V
    REPOS
    dockerfiles > COPY > Dockerfile
    dockerfiles
    FROM almalinux : 8
    H
    CMD
    2
    RUN yum install nginx -y
    3
    Dockerfile
    RUN rm -rf /usr/share/nginx/html/index. html
    4
    COPY index. html /usr/share/nginx/html/
    COPY
    5
    CMD \[ "nginx", " -g", "daemon off; "\]
    Dockerfile
    <> index.html
    U

[^91]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/dockerfiles (main)
    $ git add . ; git commit -m "dockerfiles"; git push origin main
    \[main 4a974fb\] dockerfiles
    2 files changed, 6 insertions (+)
    create mode 100644 COPY/Dockerfile
    mode
    100644 Copy /index. html

[^92]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/COPY \]$ docker build -t copy:v1
    \[+\] Building 0.7s (8/9)
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 . 0s
    =>
    => transferring dockerfile: 1968
    0 . 0s
    =>
    \[internal\] load metadata for docker . io/library/almalinux: 8
    0.2s
    =>
    (auth\] library/almalinux :pull token for registry-1 . docker . io
    0 . 0s
    =>
    \[internal\] load . dockerignore
    0 . 03

[^93]: 34 . 229. 144.33 \| 172.31.22.2 \| t2.micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/COPY \]$ docker rm -f docker ps -a -q
    e252c789e858
    29fca49f712e

[^94]: 34. 229. 144.33 \| 172. 31.22.2 \| t2.micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/COPY \]$ docker run -d -p 80:80 copy:v1
    63f1107185117ee868ae3891918b81a41f71ab5b2127f1b33b4a76696c6d1002

[^95]: C
    A Not secure 34.229.144.33
    Hi, Welcome to Docker

[^96]: 34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/COPY \]$ docker rm -f 63f1107185117ee868ae3891918b81a41f71ab5b2127f
    1b33b4a76696c6d1002
    63f1107185117ee868ae3891918b81a41f71ab5b2127f1b33b4a76696c6d1002

[^97]: both are used to copy the files from local to image. . . but ADD have 2 extra
    capabilities
    1. It can directly download files from internet
    2. It can directly untar the tar files

[^98]: EXPLORER
    Dockerfile .. \\EXPOSE
    Dockerfile ... \\ENV
    Dockerfile .. \\COPY
    Dockerfile .. \\ADD U X 92 I
    REPOS
    dockerfiles > ADD > Dockerfile
    dockerfiles
    1
    FROM almalinux : 8
    V ADD
    2
    RUN yum install nginx -y
    3
    Dockerfile
    U
    RUN rm -rf /usr/share/nginx/html/index. html
    4
    ADD https://raw.githubusercontent. com/daws-76s/notes/master/session-01. txt /usr/
    CMD
    share/nginx/html/index. html
    Dockerfile
    5
    CMD \["nginx", "-g", "daemon off; "\]

[^99]: X1 carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/dockerfiles (main)
    $ git add
    . ; git commit -m "dockerfiles"; git push origin main
    \[main e02e09b\] dockerfiles
    1 file changed, 5 insertions (+)
    create mode 100644 ADD/Dockerfile

[^100]: \[ centos@ip-172-31-22-2 \~/dockerfiles/COPY \]$ cd . ./ADD/
    34. 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ADD \]$ docker build -t add: v1
    \[+\] Building 0. 4s (9/9) FINISHED
    docker : default
    => \[internal\] load build definition from Dockerfile
    0 . 0s
    => => transferring dockerfile: 265B
    0 . 0s
    \[internal\] load metadata for docker. io/library/almalinux: 8
    0 . 1s
    =>
    \[internal\] load . dockerignore
    0 . 0s
    => => transferring context: 28
    0 . 0s
    =>
    \[1/4\] FROM docker . io/library/almalinux: 80sha256: 286bebaacc46c498394238b7a27b991921829fd94460b
    0 . 0s
    =>
    https://raw .githubusercontent . com/daws-76s/notes/master/session-01 , txt
    0 . 2s

[^101]: 34. 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github.com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ADD \]$ docker run -d -p 80:80 add:v1
    0b669dbbd391152673b7 fe3ede81d9dadeae1281090052e2f0daee003344754a
    34. 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ADD \] $

[^102]: 1. CMD command can be overridden by another command at run time.
    ping google. com ping yahoo. com
    2. ENTRYPOINT command can't be overridden, if you try to do so, the command you are
    entering at run time will go and append to ENTRYPOINT
    We can use CMD and ENTRYPOINT for best results

[^103]: EXPLORER
    . . .
    Dockerfile ... \\ENV
    Dockerfile ... \\COPY
    Dockerfile
    V REPOS
    dockerfiles > ENTRYPOINT > Dockerfile
    dockerfiles
    1
    FROM almalinux : 8
    > ADD
    2
    CMD \[ "ping", "google.com"\]
    I
    > CMD
    > COPY
    V ENTRYPOINT
    Dockerfile
    U
    ENV

[^104]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ADD \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (1/1) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4), 334 bytes \| 334.00 KiB/s, done.
    From https://github. com/daws-76s/dockerfiles
    97c0443. . 2e9fel4 main
    -> origin/main
    Updating 97c0443. . 2e9fe14

[^105]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ADD \]$ cd . . /ENTRYPOINT/
    34 . 229. 144. 33 \| 172.31.22.2 \| t2. micro \| https: / /github.com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ ocker build -t entry:v1 .
    -bash: ocker: command not found
    34. 229. 144. 33 \| 172.31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker build -t entry:v1 .
    \[+\] Building 0.2s (6/6) FINISHED
    docker : defa
    =>
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 80B
    O
    =>
    \[internal\] load metadata for docker . io/library/almalinux : 8
    O

[^106]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker run entry:v1
    PING google. com (142 . 251.16.113) 56 (84) bytes of data.
    64 bytes from bl-in-f113. le100.net (142. 251. 16.113) : icmp seq=1 tt1=57 time=1 . 78 ms
    64 bytes from bl-in-f113. le100.net (142. 251.16. 113) : icmp seq=2 tt1=57 time=1 . 92 ms
    64 bytes from bl-in-f113. le100.net (142. 251.16.113) : icmp seq=3 tt1=57 time=1. 87 ms

[^107]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT
    \]$ docker ps -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    elaf5c4cea2f
    entry : v1
    "ping google. com"
    26 seconds ago
    Exited (0) 7 seconds ago
    fervent goldberg
    bf0cfdc2ba51
    add: v1
    "nginx -g 'daemon of..."
    3 minutes ago
    Up 3 minutes
    0.0.0.0:8
    0->80/tcp, : : :80->80/tcp
    xenodochial kowalevski

[^108]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT
    \]$ docker ps -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    elaf5c4cea2f
    entry : v1
    "ping google. com"
    26 seconds ago
    Exited (0) 7 seconds ago
    fervent goldberg
    bf0cfdc2ba51
    add: v1
    "nginx -g 'daemon of..."
    3 minutes ago
    Up 3 minutes
    0.0.0.0:8
    0->80/tcp, : : :80->80/tcp
    xenodochial kowalevski

[^109]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker run entry:v1 ping yahoo. com
    PING yahoo. com (74. 6. 143.26) 56 (84) bytes of data.
    64 bytes from media-router-fp74. prod. media. vip. bf1 . yahoo . com (74. 6.143.26) : icmp_seq=1 tt1=49 time=16.2
    ms
    64 bytes from media-router-fp74. prod. media. vip. bf1 . yahoo . com (74.6. 143.26) : icmp_seq=2 tt1=49 time=16.3
    ms
    64 bytes from media-router-fp74. prod. media. vip. bf1 . yahoo . com (74. 6. 143.26) : icmp_seq=3 tt1=50 time=17.7
    ms
    64 bytes from media-router-fp74. prod. media. vip. bf1 . yahoo . com (74. 6.143.26) : icmp_seq=4 tt1=50 time=17.7
    ms
    64 bytes from media-router-fp74. prod. media. vip. bf1 . yahoo . com (74. 6.143.26) : icmp_seq=5 tt1=49 time=16.3
    ms
    64 bytes from media-router-fp74. prod. media. vip. bf1 . yahoo. com (74.6. 143.26) : icmp_seq=6 tt1=50 time=17.7
    ms

[^110]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker ps
    -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    27f242a05329
    entry : v1
    "ping yahoo . com"
    11 seconds ago
    Exited (0) 6 seconds ago
    modest shtern
    elaf5c4cea2f
    entry : v1
    "ping google. com"
    56 seconds ago
    Exited (0) 37 seconds ago
    fervent_goldberg
    bf0cfdc2ba51
    add : v1
    "nginx -g 'daemon of..."
    4 minutes ago
    Up 4 minutes
    0.0.0
    80->80/tcp, : : :80->80/tcp
    xenodochial kowalevski

[^111]: V
    REPOS
    dockerfiles > ENTRYPOINT > Dockerfile
    dockerfiles
    1
    FROM almalinux : 8
    > ADD
    #CMD \["ping", "google. com" \]
    3
    > CMD
    ENTRYPOINT \["ping", "google.com" \]
    > COPY
    ENTRYPOINT
    Dockerfile
    M

[^112]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/dockerfiles (main)
    $ git add . ; git commit -m "dockerfiles"; git push origin main
    \[main 2e48a26\] dockerfiles
    1 file changed, 2 insertions (+), 1 deletion(-)

[^113]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker build -t entry:v1
    \[+\] Building 0.2s (5/5) FINISHED
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 .0s
    => transferring dockerfile: 1158
    0.03
    =>
    \[internal\] load metadata for docker. io/library/almalinux: 8
    0 . 1s
    =>
    \[internal\] load . dockerignore
    0.0
    =>
    => transferring context: 2B
    0. 0s
    CACHED \[1/1\] FROM docker. io/library/almalinux : 80sha256 : 286bebaacc46c498394238b7a276991921829f
    0 . 03

[^114]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker run entry:v1
    PING google. com (172 . 253. 63. 101) 56 (84) bytes of data.
    64 bytes from bi-in-f101. le100.net (172. 253. 63.101) : icmp seq=1 tt1=57 time=1. 96 ms
    64 bytes from bi-in-f101. le100.net (172.253. 63.101) : icmp seq=2 tt1=57 time=2. 03 ms

[^115]: 34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker run entry:v1 ping yahoo. com
    ping: ping: Name or service not known

[^116]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker ps -a --no-trunc
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    e7a51 fab6ed58cc2f9a0a032d5164ff101a7df7acf68e2d46ac385ff0cb0a916
    entry : v1
    "ping google. com ping yahoo . com"
    20 seconds ago
    Exited (2) 19 s
    econds ago
    confident chaum
    79b4197d593080028274f18c794fd9c6268d8a64794749cef3a207d7990bcfe5
    entry : v1
    "ping google. com"
    32 seconds ago
    Exited (0) 28 s
    econds ago
    romantic hawking

[^117]: EXPLORER
    . . .
    Dockerfile ... \\ENV
    Dockerfile ... \\COPY
    Docker
    V REPOS
    dockerfiles > ENTRYPOINT > Dockerfile
    dockerfiles
    1
    FROM almalinux : 8
    > ADD
    2
    #CMD \["ping", "google.com"\]
    3
    > CMD
    CMD \[ "google . com"\]
    4
    ENTRYPOINT \["ping" \]
    > COPY
    V
    ENTRYPOINT
    Dockerfile
    M

[^118]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker build -t entry:v1
    \[+\] Building 0.2s (6/6) FINISHED
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 . 0s
    =>
    => transferring dockerfile: 120B
    0 . 0s
    =>
    \[internal\] load metadata for docker. io/library/almalinux: 8
    0 . 1s
    =>
    \[auth\] library/almalinux : pull token for registry-1. docker . io
    0 .03
    \[internal\] load . dockerignore
    0. 0s

[^119]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker run entry:v1
    PING google. com (142 . 251. 163.138) 56(84) bytes of data.
    64 bytes from wv-in-f138. le100.net (142. 251. 163.138) : icmp seq=1 tt1=57 time=1 . 97 ms
    64 bytes from wv-in-f138. le100.net (142. 251. 163.138) : icmp seq=2 tt1=57 time=1. 100 ms

[^120]: We can use CMD and ENTRYPOINT for best results
    1. You can use CMD instruction to supply default arguements to ENTRYPOINT
    2. user can always override CMD arguements from run time I

[^121]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ENTRYPOINT \]$ docker run entry:v1 yahoo. com
    PING yahoo. com (98. 137. 11.163) 56 (84) bytes of data.
    64 bytes from media-router-fp74. prod. media. vip. gal . yahoo. com (98. 137. 11. 163) : icmp_seq=1 tt1=49 time=59
    7 ms
    64 bytes from media-router-fp74. prod. media. vip. gal . yahoo . com (98. 137. 11. 163) : icmp_seq=2 tt1=49 time=59
    8 ms

[^122]: V
    REPOS
    dockerfiles > USER > Dockerfile
    dockerfiles
    FROM almalinux : 8
    WNH
    RUN adduser sivakumar
    ADD
    USER sivakumar
    > CMD
    4
    T
    CMD . \["sleep", "100"\]
    > COPY
    > ENTRYPOINT
    > ENV
    > EXPOSE
    > FROM
    LABEL
    > RUN
    V USER
    Dockerfile
    M

[^123]: \[ centos@ip-172-31-22-2 \~/dockerfiles/USER \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4), 346 bytes \| 346.00 KiB/s, done.
    From https://github. com/daws-76s/dockerfiles
    95d568a. . el1663f main
    -> origin/main

[^124]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github.com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/USER \]$ docker build -t user: v1
    \[+\] Building 0. 6s (6/6) FINISHED
    docker : def
    =>
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 111B
    =>
    \[internal\] load metadata for docker . io/library/almalinux: 8
    =>
    \[internal\] load . dockerignore
    => transferring context: 28
    CACHED \[1/2\] FROM docker . io/library/almalinux : 80sha256: 286bebaacc46c498394238b7a27b99192829f
    =>
    \[2/2\] RUN adduser sivakumar
    =>
    exporting to image

[^125]: 34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/USER \]$ docker run -d user:v1
    7d6fddb0547b1 fbd0908b7785d33776320aa6516f47ff7e47b49403e78e1115b
    34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/USER \]$ docker exec -it 7d6fddb bash
    \[sivakumar@7d6fddb0547b /\]$ id
    uid=1000 (sivakumar) gid=1000 (sivakumar) groups=1000 (sivakumar)
    \[sivakumar@ 7d6fddb0547b / \] $

[^126]: V
    REPOS
    dockerfiles > WORKDIR > Dockerfile
    dockerfiles
    1
    FROM almalinux : 8
    > ADD
    2
    WORKDIR / tmp
    3
    RUN echo "Hello Docker" > hello. txt
    > CMD
    4
    CMD \[" sleep", "100"\]
    > COPY
    > ENTRYPOINT
    > ENV
    > EXPOSE
    > FROM
    > LABEL
    > RUN
    > USER
    V WORKDIR
    Dockerfile

[^127]: \[ centos@ip-172-31-22-2 \~/dockerfiles/USER \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (1/1) , done.
    remote: Total 4 (delta 2), reused 4 (delta 2) , pack-reused 0
    Unpacking objects: 100% (4/4) , 310 bytes \| 310.00 KiB/s, done.
    From https://github. com/daws-76s/dockerfiles
    70834af. . 26a28fa main
    -> origin/main
    Updating 70834af. . 26a28fa

[^128]: 34 . 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/WORKDIR \]$ docker build -t work:v1.
    \[+\] Building 0.2s (3/4)
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 . 0s
    => transferring dockerfile: 120B
    0.03

[^129]: 34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/WORKDIR \]$ docker run -d -it work: v1
    f90a9c50997c44240e681b126f9d62d5a77eae65bb4141d610c645afd6f7dabb
    34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github.com/daws-76s/dockerfiles. git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/WORKDIR \] $

[^130]: 34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/WORKDIR \]$ docker exec -it 64128c918 bash
    \[root@ 64128c9184d7 tmp\]# 1s
    hello. txt
    \[root@64128c9184d7 tmp\]#

[^131]: ARG VS ENV
    ARG instruction can provide values to the Dockerfile only at buildtime. ENV variables
    have access in the container
    How can I use ARG variables inside container?
    Assign the values of ARG to ENV variables so that you can access them inside container
    as well

[^132]: EXPLORER
    erfile ... \\ENTRYPOINT
    Dockerfile ...\\USER
    Docker
    V
    REPOS
    dockerfiles > ARG > Dockerfile
    dockerfiles
    1
    FROM almalinux : 8
    2
    ARG username
    > ADD
    3
    RUN adduser $username
    V ARG
    4
    USER $username
    Dockerfile
    M
    5
    CMD \["sleep", "100"\]
    > CMD
    > COPY

[^133]: \[ centos@ip-172-31-22-2 \~/dockerfiles/WORKDIR \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4) , 350 bytes \| 350.00 KiB/s, done.
    From https ://github. com/daws-76s/dockerfiles
    de 788a5. . c3d418b main
    -> origin/main
    Updating de788a5. . c3d418b

[^134]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker build -t arg:v1
    \[+\] Building 0. 4s (6/6) FINISHED
    docker : default
    \[internal\] load build definition from Dockerfile
    0 .0s
    => transferring dockerfile: 1098
    0 . 0=
    =>
    \[internal\] load metadata for docker . io/library/almalinux : 8
    0. 3s
    =>
    \[auth\] library/almalinux:pull token for registry-1. docker . io
    0 .0s
    \[internal\] load . dockerignore
    0 . 0s
    => => transferring context: 2B
    0.03

[^135]: 34. 229. 144.33 \| 172.31.22.2 \| t2.micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker run -d arg:v1
    d49ba834f3c3716176f9240807844f2fd06362844bb92ccf12a4e3f35af5c26a
    docker: Error response from daemon: unable to find user adduser : no matching entries in passwd file.

[^136]: 34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https:/ /github.com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker build -t arg:v1 --build-arg username=sivakumar .
    \[+\] Building 0.1s (5/5) FINISHED
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 . 0s
    =>
    => transferring dockerfile: 1098
    0.0s
    =>
    \[internal\] load metadata for docker . io/library/almalinux: 8
    0. 1=
    =>
    \[internal\] load . dockerignore
    0 . 0s
    =>
    => transferring context: 2B
    0.03
    =>
    CACHED \[1/1) FROM docker . io/library/almalinux: 80sha256: 286bebaacc46c498394238b7a276991921829f
    0 . 0s
    =>
    exporting to image
    0. 0s
    =>
    => exporting layers
    0 .0s

[^137]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker run -d arg:v1
    39556e/ 79c85c86ac44f0db9a88d5f87ad386cb88266bca9cc397683aaef5146
    34 . 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: //github.com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker exec -it 39556e7 bash
    \[sivakumar@39556e779c85 /\]$ id
    uid=1000 (sivakumar) gid=1000 (sivakumar) groups=1000 (sivakumar)
    \[sivakumar@39556e779c85 /\] $

[^138]: V
    REPOS
    dockerfiles > ARG > Dockerfile
    dockerfiles
    FROM almalinux : 8
    H
    > ADD
    2
    ARG username
    3
    RUN adduser $username
    V ARG
    4
    USER $username
    Dockerfile
    M
    15
    ARG COURSE
    > CMD
    ARG TRAINER
    > COPY
    RUN echo "Course: ${COURSE}, Trainer: ${TRAINER}"
    > ENTRYPOINT
    8
    ENV COURSE=$ {COURSE}
    > ENV
    9
    ENV TRAINER=$ {TRAINER}
    10
    > EXPOSE
    CMD \[" sleep", "100"\]

[^139]: 34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0

[^140]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker build -t arg:v1 --build-arg username=sivakumar --bu
    1d-arg COURSE=Devops --build-arg TRAINER=Sivakumar
    \[+\] Building 0. 6s (8/8) FINISHED
    docker : default
    \[internal\] load build definition from Dockerfile
    0. 03
    =>
    => transferring dockerfile: 2428
    0 . 0s
    =>
    \[internal\] load metadata for docker. io/library/almalinux : 8
    0 . 1s
    =>
    \[auth\] library/almalinux: pull token for registry-1 . docker. io
    0 . 0s
    =>
    \[internal\] load . dockerignore
    0 . 0s
    =>
    => transferring context: 2B
    0 . 0s
    =>
    \[1/3\] FROM docker. io/library/almalinux: 80sha256: 286bebaacc46c498394238b7a276991926829Ed94460b
    0 . 0s
    =>
    CACHED \[2/3\] RUN adduser sivakumar
    0 . 0s
    =>
    \[3/3\] RUN acho "Course: Devops, Trainer: Sivakumar"I
    0 . 4s
    =>
    exporting to image
    0 . 0s
    =>
    => exporting layers
    0 . 0s
    =>
    => writing image sha256: dd89685720ee4dd973856943d6f123ac60lef5f7aa6103174caf223699589adl
    0 . 0s
    =>
    => naming to docker . io/library/arg: v1
    0 . 0s

[^141]: 34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker run -d arg:v1
    fd90b312ccqc919370c36414223f7c3155c339db46302e3f20246c34a2588340

[^142]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker exec -it fd90b312cc0 bash
    \[sivakumar@fd90b312cc0c /\]$ env
    LANG=C. utf8
    HOSTNAME=fd90b312cc0c
    COURSE=Devops
    PWD=/
    HOME=/home / sivakumar
    TERM=xterm
    TRAINER=Sivakumar
    SHLVL=1
    PATH=/home/sivakumar/. local/bin: /home/sivakumar/bin: /usr/local/sbin: /usr/local/bin
    bin: /bin
    LESSOPEN=\| \| /usr/bin/lesspipe. sh \*s

[^143]: ONBUILD
    author of image: I want to force users of image to follow something

[^144]: EXPLORER
    . . .
    ockerfile ...\\USER
    Dockerfile ...\\WORKDIR
    Dockerfile ... \\ARG
    V REPOS
    dockerfiles > ONBUILD > Dockerfile
    dockerfiles
    FROM almalinux : 8
    > ADD
    2
    RUN yum install nginx -y
    RUN rm -rf /usr/share/nginx/html/index. html
    ARG
    4
    ONBUILD ADD index. html /usr/share/nginx/html/
    > CMD
    5
    CMD \[ "nginx", "-g", "daemon off; "\]
    > COPY
    > ENTRYPOINT
    > ENV
    > EXPOSE
    FROM
    LABEL
    ONBUILD
    Dockerfile
    U

[^145]: 34. 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.g
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4), 414 bytes \| 414.00 KiB/s, done.
    From https: //github. com/daws-76s/dockerfiles

[^146]: 34. 229. 144.33 \| 172.31.22.2 \| t2. micro \| https: / /github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD \]$ docker build -t on:v1
    \[+\] Building 0.3s (7/7) FINISHED
    docker : default
    \[internal\] load build definition from Dockerfile
    0 . 0s
    =>
    =>
    => transferring dockerfile: 203B
    0 . 0s
    0 . 2s
    =>
    \[internal\] load metadata for docker . io/library/almalinux: 8
    \[internal\] load . dockerignore
    0 . 0s
    =>
    => transferring context: 2B
    0 . 0s
    =>
    =>
    \[1/3\] FROM docker . io/library/almalinux : 80 sha256: 286bebaacc46c498394238b7a27b991921829Ed94460b
    0 . 03
    =>
    CACHED \[2/3\] RUN yum install nginx -y
    0 . 0s
    0.03
    =>
    CACHED \[3/3\] RUN am -rf /usr/share/nginx/html/index . html
    exporting to image
    0 . 05
    > exporting layers
    0 . 0s
    =>
    => writing image sha256: 3cf2d27caf9d3a76c6db2dlafeb7d682869969816689096f263515a79098c27
    0 . 0s
    0 . 0s
    =>
    => naming to docker. io/library/on: v1

[^147]: V
    REPOS
    dockerfiles > ONBUILD > test > Dockerfile
    dockerfiles
    1
    FROM on : v1
    > ADD
    > ARG
    > CMD
    > COPY
    > ENTRYPOINT
    >
    ENV
    > EXPOSE
    FROM
    > LABEL
    ONBUILD
    test
    Dockerfile
    U
    Dockerfile

[^148]: 34 . 229. 144. 33 \| 172. 31.22.2 \| t2.micro \| https: / /github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 5 (delta 1) , reused 5 (delta 1) , pack-reused 0
    Unpacking objects: 100% (5/5) , 374 bytes \| 374.00 KiB/s, done.
    From https://github. com/daws-76s/dockerfiles

[^149]: \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD \]$ cd test/
    34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles.git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD/test \]$ docker build -t on-test:v1 .

[^150]: =>
    \[internal\] load build context
    =>
    => transferring context: 2B
    =>
    \[1/1\] FROM docker . io/library/on:v1
    ERROR \[2/1\] ADD index. html /usr/share/nginx/html/
    > \[2/1\] ADD index. html /usr/share/nginx/html/ :
    Dockerfile : 1
    1 \| >>> FROM on: v1
    ERROR: failed to solve: failed to compute cache key: failed to calculate checksum of ref d10
    8df-a5d6-e99049b2f07d: : t2tbvkmy7w7bboae1b9171xyk: "/index. html": not found

[^151]: EXPLORER
    Dockerfile ... \\ARG
    Dockerfile ..\\ONBUILD
    Dockerfile
    REPOS
    dockerfiles > ONBUILD > test > <> index.html > < h1
    dockerfiles
    1
    <h1>Hi, this is from on build test</h1>
    > ADD
    > ARG
    > CMD
    > COPY
    > ENTRYPOINT
    ENV
    > EXPOSE
    > FROM
    > LABEL
    V ONBUILD
    test
    Dockerfile
    <> index.html
    U
    Dockerfile

[^152]: 34 . 229. 144.33 \| 172. 31.22.2 \| t2. micro \| https: //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD/test \]$ docker build -t on-test:v1 .
    \[+\] Building 0.1s (6/7)
    docker : default
    =>
    \[internal\] load build definition from Dockerfile
    0 .0s
    =>
    => transferring dockerfile: 478
    0 . 03
    =>
    \[internal\] load metadata for docker . io/library/on: v1
    0 . 0s
    =>
    \[internal\] load . dockerignore
    0 .03
    =>
    => transferring context: 28
    0 .0s
    \[internal\] load build context
    0 . 0s
    => transferring context: 768
    0 . 0s
    CACHED \[1/1\] FROM docker . io/library/on: v1
    0.03
    =>
    \[2/1\] ADD index. html /usr/share/nginx/html/
    0 . Os
    => exporting to image
    0 . 0s
    =>
    => exporting layers
    0.0s
    writing image sha256: 6700120380d84812b0f481feb979489459a97e4a4f6226c61ec8cf45e3ff7
    0. 0s

[^153]: 34 . 229 . 144 . 35
    172 . 31 .
    t2 .micro \| https : / /github . com/daws-/6s/dockertiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD/test \]$ docker run -d -p 8083:80 on-test:v1
    leee22651f7990eld96558bf621b0cbc1240e4d719335df1795ff5c704ce7104
    34. 229. 144. 33 \| 172. 31.22.2 \| t2. micro \| https : //github. com/daws-76s/dockerfiles .git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ONBUILD/test \]$

[^154]: C
    A Not secure 34.229.144.33:8083
    Hi, this is from on build test

