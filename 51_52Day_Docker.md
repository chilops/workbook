---
title: 51_52Day_Docker
uuid: e8fba9fc-39b8-11ef-8998-6ef34fa959ce
version: 1691
created: '2024-07-04T09:23:01+05:30'
tags:
  - docker
---

# <mark style="background-color:#f8914d;">**ROBOSHOP using DOCKER**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Roboshop project already available in internet

![e7d80d5b-746d-40e6-b6aa-2526c3644aff.png|951.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e7d80d5b-746d-40e6-b6aa-2526c3644aff.png) [^1]

![b7dbb8e8-9efe-4b37-83dd-21b6898eb7f4.png|647](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b7dbb8e8-9efe-4b37-83dd-21b6898eb7f4.png) [^2]

\

\

# <mark style="background-color:#f8914d;">**MongoDB docker setup**<!-- {"backgroundCycleColor":"24"} --></mark>

![414c4fef-64d2-44d8-af5d-12e88ad3e7dd.png|852](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/414c4fef-64d2-44d8-af5d-12e88ad3e7dd.png) [^3]

\

PUSH & PULL from github

![34bcecdb-8627-4866-a8ff-490405dbd3be.png|1145](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/34bcecdb-8627-4866-a8ff-490405dbd3be.png) [^4]

\

create an docker instance and pull

![fc1027de-5b84-41c2-8b6a-46e6cd98d795.png|1117.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/fc1027de-5b84-41c2-8b6a-46e6cd98d795.png) [^5]

<mark>**Install docker engine**</mark>

![eef63c2c-8d71-40de-9bbd-62127633565a.png|897](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/eef63c2c-8d71-40de-9bbd-62127633565a.png) [^6]

\

Setting up a repo

```
sudo su -
yum install -y yum-utils
```

![7e0af630-f4c7-4bf1-a126-80f6c7bcfd97.png|889](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/7e0af630-f4c7-4bf1-a126-80f6c7bcfd97.png) [^7]

\

```
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

![c82e085f-f1b9-4853-b6dc-cd1ebcf8c491.png|1094](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c82e085f-f1b9-4853-b6dc-cd1ebcf8c491.png) [^8]

\

Installing Docker engine

```
yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

![c0fe049c-56f0-47b2-b3ee-a6afe7cb04ae.png|1171](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/c0fe049c-56f0-47b2-b3ee-a6afe7cb04ae.png) [^9]

\

Start the docker

```
systemctl start docker
systemctl enable docker
systemctl status docker
```

![6526b73b-b77e-43d1-a0a7-10a69a5c9385.png|1076](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/6526b73b-b77e-43d1-a0a7-10a69a5c9385.png) [^10]

\

```
docker
docker ps
```

![94d4f81e-8cad-4a52-bd53-5233bd789592.png|830](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/94d4f81e-8cad-4a52-bd53-5233bd789592.png) [^11]

\

<mark>Docker users can only use docker commands</mark>

When you install docker a group named DOCKER is created

Giving permission to users

```
sudo su -
```

```
usermod -aG docker centos
```

![eb960104-d9bc-4352-a0c0-19740af2d2e1.png|739](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/eb960104-d9bc-4352-a0c0-19740af2d2e1.png) [^12]

\

Reconnect to instance and try docker commands with normal user.

```
docker ps
```

![b05f4f0b-7518-4527-b989-d33565018ad3.png|837](https://images.amplenote.com/f7349cfe-3828-11ef-8d44-26e37c279344/b05f4f0b-7518-4527-b989-d33565018ad3.png) [^13]

\

\

**Clone the mongodb code to docker server**

![a91944f0-74cb-4328-83b9-18b70ef4d1f7.png|943.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/a91944f0-74cb-4328-83b9-18b70ef4d1f7.png) [^14]

\

![00ab730f-6e72-4904-9e65-a91b180f2ea8.png|1055.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/00ab730f-6e72-4904-9e65-a91b180f2ea8.png) [^15]

\

![528f9e37-04f5-4196-adfb-835914569e06.png|1063.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/528f9e37-04f5-4196-adfb-835914569e06.png) [^16]

\

Building mongodb docker image

```
docker build -t mongodb:1 . 
```

![ec55b354-e8b4-4c74-a204-181c634b803b.png|1142.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/ec55b354-e8b4-4c74-a204-181c634b803b.png) [^17]

![89b2f587-4fb7-4c0e-a65d-722979e94f38.png|1042.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/89b2f587-4fb7-4c0e-a65d-722979e94f38.png) [^18]

\

Image built and ready

```
docker images
```

![4b4be1a6-632b-47fc-9740-e810872f04b3.png|1095.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/4b4be1a6-632b-47fc-9740-e810872f04b3.png) [^19]

\

Now running the docker image( we will give name because IPs may change) Also we are not exposing mongoDB so we are not using -p(port) parameter

```
docker run -d mongodb:1 --name mongodb
```

![16b91b2b-bf18-476c-af9f-0f20e563b288.png|1055.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/16b91b2b-bf18-476c-af9f-0f20e563b288.png) [^20]

\

In our scenario its not running 

![1e898484-10cd-471e-82b8-87102d7727c7.png|1146.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/1e898484-10cd-471e-82b8-87102d7727c7.png) [^21]

\

```
docker run -d --name mongodb mongodb:1 
```

![b0b19298-85f9-4ac6-98f3-d467b7b21ba0.png|1116.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b0b19298-85f9-4ac6-98f3-d467b7b21ba0.png) [^22]

\

```
docker ps
```

![3139e59e-b641-451f-9aac-2b7d603d473d.png|1122.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3139e59e-b641-451f-9aac-2b7d603d473d.png) [^23]

\

to check logs and mongodb is running

```
docker logs mongodb
```

![36ceb73a-d912-4f61-ac21-71b528c07d9c.png|1106.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/36ceb73a-d912-4f61-ac21-71b528c07d9c.png) [^24]

\

# <mark style="background-color:#f8914d;">**Catalogue docker setup**<!-- {"backgroundCycleColor":"24"} --></mark>

![fa655920-0bb1-4cc3-b0d0-a18e2d0a8c8a.png|799](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/fa655920-0bb1-4cc3-b0d0-a18e2d0a8c8a.png) [^25]

\

push & pull - GITHUB

![a6a7174f-63b7-4418-b260-42b9518ced5b.png|988](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/a6a7174f-63b7-4418-b260-42b9518ced5b.png) [^26]

![61f5fa91-3809-48e6-8882-bc2c96398a58.png|1073.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/61f5fa91-3809-48e6-8882-bc2c96398a58.png) [^27]

\

<mark>**Building docker image for catalogue**</mark>

```
docker build -t catalogue:1 .
```

![4f582b01-8ab8-458f-971e-2028530a095a.png|1208.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/4f582b01-8ab8-458f-971e-2028530a095a.png) [^28]

![aca168b0-ae83-4ba3-a8a9-7c54c70ec906.png|1206.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/aca168b0-ae83-4ba3-a8a9-7c54c70ec906.png) [^29]

\

To see Docker images

```
docker images
```

![49c30852-72c7-449f-8252-e95d5fad586a.png|941.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/49c30852-72c7-449f-8252-e95d5fad586a.png) [^30]

\

Now running that image as docker container

```c
docker run -d --name catalogue catalogue:1 
```

![1d014840-470b-4282-9747-ae933ee1932a.png|1119.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/1d014840-470b-4282-9747-ae933ee1932a.png) [^31]

\

To check running containers & check the logs

```
docker ps
```

```
docker logs 432ddfdfdfd1
```

![c09aeb33-e062-45c0-9af8-16c8b4a879aa.png|1016.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c09aeb33-e062-45c0-9af8-16c8b4a879aa.png) [^32]

\

we are seeing errors, so we need to know about docker networking

![720180e0-74f0-4662-bcd0-829a311b4167.png|1056.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/720180e0-74f0-4662-bcd0-829a311b4167.png) [^33]

\

# <mark style="background-color:#f8914d;">**Docker Networking**<!-- {"backgroundCycleColor":"24"} --></mark>

\

```
ifconfig
```

![c8546c25-abd9-4eb0-a68d-34aeaae50181.png|1013.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c8546c25-abd9-4eb0-a68d-34aeaae50181.png) [^34]

![70b358fa-a091-4c5d-b864-688ea1209e02.png|1015.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/70b358fa-a091-4c5d-b864-688ea1209e02.png) [^35]

\

<mark>**172.31.0.103 provided by AWS network through ethernet**</mark>

\

docker0 is gateway for docker containers

![980e2409-279e-4788-b2fe-1552f3714886.png|1137.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/980e2409-279e-4788-b2fe-1552f3714886.png) [^36]

\

To check docker container IP address

```
docker inspect <containerID> | grep ip
or
docker inspect <containerID> 
```

![e012f7e5-35de-4ddb-94eb-fc5595449bbc.png|869.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e012f7e5-35de-4ddb-94eb-fc5595449bbc.png) [^37]

\

docker assigned IP's

![](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/022b7610-9239-4fb7-8eca-5e429281b24c.png) [^38]

\

<mark style="background-color:#f8914d;">**Container cannot communicate each other through if they use docker default network**<!-- {"backgroundCycleColor":"24"} --></mark>

\

In docker we have two types of networking

1. host

1. bridge

In docker we use bridge networking, by default docker will create bridge networking

\

ROBOSHOP or any other project can create its own network.

\

<mark>**How to create network?**</mark> we should not use docker default network, we should create our own network

```
docker network
```

![0c6c6a31-4860-4f72-bea9-dac78547b458.png|918.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/0c6c6a31-4860-4f72-bea9-dac78547b458.png) [^39]

\

```
docker network create roboshop
```

![c353e3e6-571c-47fb-8c0a-32dcc2b7ceb6.png|980.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c353e3e6-571c-47fb-8c0a-32dcc2b7ceb6.png) [^40]

\

roboshop network got created(by default its a bridge network)

```
docker network ls
```

![ad25785b-19b9-4a12-8bd4-97edb2eb17f6.png|947.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/ad25785b-19b9-4a12-8bd4-97edb2eb17f6.png) [^41]

\

```
ifconfig
```

![2f0c386d-2b78-4825-8f41-bb84f5c73991.png|958](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/2f0c386d-2b78-4825-8f41-bb84f5c73991.png) [^42]

\

will remove current/existing containers and will create new one

```
docker rm -f 'docker ps -a -q'
```

![dbb47fe3-a23c-4182-a431-1be799b6d224.png|1127.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/dbb47fe3-a23c-4182-a431-1be799b6d224.png) [^43]

\

```
docker run -d --name mongodb --network=roboshop mongodb:1
```

![](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/757b2a39-13c5-4e4c-9318-d103ce8cfd8a.png) [^44]

\

```
docker ps
docker inspect <containerID>
```

![774bcc92-ce8c-4a26-94cb-7d9ff1633141.png|1041](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/774bcc92-ce8c-4a26-94cb-7d9ff1633141.png) [^45]

\

```
docker run -d --name catalogue --network=roboshop catalogue:1
```

![2b766b54-37ec-442a-8a0d-c2b0753b15dc.png|1085.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/2b766b54-37ec-442a-8a0d-c2b0753b15dc.png) [^46]

\

```
docker ps
```

![c03f652b-133e-4600-b727-658d9c281d71.png|1019.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c03f652b-133e-4600-b727-658d9c281d71.png) [^47]

\

Now mongodb connected **(Container to container communication is happening through roboshop bridge network and container names)**

```
docker logs catalogue
```

![8cfa3690-1ff3-467a-93a7-3e7ed4fc37d1.png|1112.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8cfa3690-1ff3-467a-93a7-3e7ed4fc37d1.png) [^48]

\

# <mark style="background-color:#f8914d;">**WEB docker setup**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![f0c07239-c1e1-4e4a-89ea-05db78797644.png|980](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f0c07239-c1e1-4e4a-89ea-05db78797644.png) [^49]

![d34f6bb6-9fdd-45e0-a62d-876c7a91e372.png|961](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d34f6bb6-9fdd-45e0-a62d-876c7a91e372.png) [^50]

\

push & pull -- github

![ad773f14-98a9-415a-8b42-c799ffb5e928.png|1013.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/ad773f14-98a9-415a-8b42-c799ffb5e928.png) [^51]

\

```
docker build -t web:1 .
```

![b2cc9177-98a9-4080-ae2e-a8fcb3722428.png|1085.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b2cc9177-98a9-4080-ae2e-a8fcb3722428.png) [^52]

\

\

Since it's a web component we need to expose it to outside world.

```
docker run -d -p 80:80 --name web --network=roboshop web:1
docker ps
```

![b9cb12d5-6356-4b03-8a07-0aa5086b77d8.png|1108.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b9cb12d5-6356-4b03-8a07-0aa5086b77d8.png) [^53]

\

now we are able to access the website

![a8bfc0af-d37d-4816-ac7d-0534f634c63b.png|1112.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/a8bfc0af-d37d-4816-ac7d-0534f634c63b.png) [^54]

\

\

<mark>**troubleshoot steps - if categories not loads**</mark>

Now i am inside the web component as categories are not loading with 404 error

```
docker exec -it 27e0eedfc0 bash
```

![898fa289-da68-4dea-8a1d-dbb2ffbcc4e6.png|1061.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/898fa289-da68-4dea-8a1d-dbb2ffbcc4e6.png) [^55]

\

from here catalogue is working

```
curl http://catalogue:8080/health
```

![b3d64858-26f6-4a60-92b3-bc55f70f6841.png|1130](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b3d64858-26f6-4a60-92b3-bc55f70f6841.png) [^56]

\

```
curl localhost/api/catalogue/health
```

![51720adf-b9cd-413c-a0df-32dba3636451.png|1028](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/51720adf-b9cd-413c-a0df-32dba3636451.png) [^57]

\

![9e7f52e5-10f5-4fa6-8c3a-98a625751f69.png|1081.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/9e7f52e5-10f5-4fa6-8c3a-98a625751f69.png) [^58]

============

\

---

# <mark style="background-color:#f8914d;">**DOCKER Compose**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![131442bc-ea69-4301-b7fc-a46b442bbb1e.png|556](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/131442bc-ea69-4301-b7fc-a46b442bbb1e.png) [^59]

Docker compose will make it easy to maintain the docker containers

![576831e0-825f-4aeb-b96b-c0af978e3124.png|931](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/576831e0-825f-4aeb-b96b-c0af978e3124.png) [^60]

![cf6e8ccb-1a47-42a6-911a-ee19d5994df2.png|937](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/cf6e8ccb-1a47-42a6-911a-ee19d5994df2.png) [^61]

\

<mark>**Installing Docker compose**</mark>

command may vary based on centos or OS check in google

```
sudo curl -L https://github.com/docker/compose/releases/download/2.24.5/docker-compose- 'uname -s '-' uname -m' -o /usr/local/bin/docker-compose
```

![b0f3bf33-842b-43c9-b441-1c3ca5d26f79.png|1137.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b0f3bf33-842b-43c9-b441-1c3ca5d26f79.png) [^62]

\

```
sudo chmod +x /usr/local/bin/docker-compose
```

![abd90509-7ab2-449f-9c5a-f9ba62aa5b3a.png|1104.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/abd90509-7ab2-449f-9c5a-f9ba62aa5b3a.png) [^63]

\

```
docker compose
```

![60902cb6-7104-4790-be92-95c25e4bec93.png|1079.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/60902cb6-7104-4790-be92-95c25e4bec93.png) [^64]

\

![98f73110-c2c5-4522-88b6-74590dc96c79.png|845.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/98f73110-c2c5-4522-88b6-74590dc96c79.png) [^65]

docker compose yaml file

![b1730579-f8b2-4350-a66b-75dfc3d62679.png|936.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b1730579-f8b2-4350-a66b-75dfc3d62679.png) [^66]

\

we need to modify this file as per our image names & network name

![a1c2381b-47cb-4cc4-86d2-ff8893bfe4a2.png|1023.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/a1c2381b-47cb-4cc4-86d2-ff8893bfe4a2.png) [^67]

or

![c5b2a77a-6f66-46cc-a75a-4fcbbdde27a5.png|947.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c5b2a77a-6f66-46cc-a75a-4fcbbdde27a5.png) [^68]

\

remove all images before testing docker compose

```
docker rm -f 'docker ps -a -q'
```

![946ece20-3514-4e43-bb9e-02ebc4bc0e0c.png|1025.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/946ece20-3514-4e43-bb9e-02ebc4bc0e0c.png) [^69]

\

git push & pull

![b00be171-5d0b-4c5c-9d6e-c6bba9d85dae.png|1069.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b00be171-5d0b-4c5c-9d6e-c6bba9d85dae.png) [^70]

\

it will check dependencies and create in an order

```
docker compose up -d
```

![a1b2eed4-e85f-4cf4-a4eb-ef4824a6ed9f.png|1117.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/a1b2eed4-e85f-4cf4-a4eb-ef4824a6ed9f.png) [^71]

\

```
docker ps
```

![947c7519-9353-4792-9e8e-38cbcdcfd51e.png|1090.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/947c7519-9353-4792-9e8e-38cbcdcfd51e.png) [^72]

\

our site is working

![bcede28c-0845-4357-afbc-2f92280a42f6.png|1055](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/bcede28c-0845-4357-afbc-2f92280a42f6.png) [^73]

\

If you want to stop/remove containers at a time

```
docker compose down
```

![c4e54145-5204-444d-8f85-6ec4c3ca6d01.png|1083.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c4e54145-5204-444d-8f85-6ec4c3ca6d01.png) [^74]

\

\

---

# <mark style="background-color:#f8914d;">**User & CART docker setup**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![b3e41d91-4705-46fe-9c78-8eccd1479d4c.png|718](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b3e41d91-4705-46fe-9c78-8eccd1479d4c.png) [^75]

![4e060b51-f320-49e3-bac4-91bd9668f7dc.png|736](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/4e060b51-f320-49e3-bac4-91bd9668f7dc.png) [^76]

\

git push & pull

![c593d095-2e7a-44fe-b9a6-82ec83abb36d.png|984.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c593d095-2e7a-44fe-b9a6-82ec83abb36d.png) [^77]

\

<mark>**After creating images only you can use docker compose**</mark>

\

now creating image for user

```
docker build -t user:1 .
```

![cd9bbd7c-172c-4992-ad08-b9359dbb5a12.png|1105.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/cd9bbd7c-172c-4992-ad08-b9359dbb5a12.png) [^78]

\

Cart image creation

```
docker build -t cart:1 .
```

![082e03f5-c6ce-4730-9c69-549867f73b59.png|1114.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/082e03f5-c6ce-4730-9c69-549867f73b59.png) [^79]

\

```
docker images
```

![410b7ea9-fbd6-4605-a22b-8287d810f921.png|1041.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/410b7ea9-fbd6-4605-a22b-8287d810f921.png) [^80]

\

\

<mark>**Now adding user & cart to docker compose**</mark>

![fb3fa205-4c0a-452f-9723-d3b284c2f1cd.png|968](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/fb3fa205-4c0a-452f-9723-d3b284c2f1cd.png) [^81]

\

git push & pull

![06bca982-a9eb-4a95-883d-70ef73e73317.png|1046.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/06bca982-a9eb-4a95-883d-70ef73e73317.png) [^82]

\

```
docker compose up -d
```

![6b4f4da6-3397-49f2-95b6-08f0f4361315.png|1046.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/6b4f4da6-3397-49f2-95b6-08f0f4361315.png) [^83]

\

```
docker ps
```

![1e009b6d-45d6-41ad-9511-06845ac2318e.png|1105.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/1e009b6d-45d6-41ad-9511-06845ac2318e.png) [^84]

\

![3130494b-5dfe-4f64-9e13-6c92c91a371c.png|933](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3130494b-5dfe-4f64-9e13-6c92c91a371c.png) [^85]

---

# <mark style="background-color:#f8914d;">**MYSQL docker setup**<!-- {"backgroundCycleColor":"24"} --></mark>

![21bd8c7e-ed86-4b29-a2ae-2f02b7f3a56d.png|845](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/21bd8c7e-ed86-4b29-a2ae-2f02b7f3a56d.png) [^86]

\

git push & pull

![dd8f57ff-d12f-470d-a458-70a35b01f319.png|1042.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/dd8f57ff-d12f-470d-a458-70a35b01f319.png) [^87]

\

build mysql image

```
docker build -t mysql:1 .
```

![f9364db4-72d7-4766-9268-f481ff804a36.png|1051.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f9364db4-72d7-4766-9268-f481ff804a36.png) [^88]

\

![55a93d8b-5e5e-4c79-9e2d-284d186bed8d.png|833](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/55a93d8b-5e5e-4c79-9e2d-284d186bed8d.png) [^89]

\

git push & pull

\

![b934e4d7-1a82-4880-b6f1-06825fe6b719.png|934](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b934e4d7-1a82-4880-b6f1-06825fe6b719.png) [^90]

\

docker compose

```
docker compose up -d
```

![7362e4ef-d9ca-4353-b298-7ea13e80f021.png|1113.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/7362e4ef-d9ca-4353-b298-7ea13e80f021.png) [^91]

\

```
docker ps
```

![d6bddbba-e641-4dc3-8d1c-753fa29735d4.png|1029.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d6bddbba-e641-4dc3-8d1c-753fa29735d4.png) [^92]

\

names are creating as below

![ac356900-76c5-48e2-a281-0ca2642312a2.png|1111.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/ac356900-76c5-48e2-a281-0ca2642312a2.png) [^93]

\

to check mysql logs

```
docker logs roboshop-docker-mysql-1
```

![2eebce46-2026-4faf-a451-b432d1158d10.png|1061.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/2eebce46-2026-4faf-a451-b432d1158d10.png) [^94]

![cce0cb77-845f-4425-ad2b-8878c17a8961.png|1061.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/cce0cb77-845f-4425-ad2b-8878c17a8961.png) [^95]

\

\

to create name which you want give it in dockerfile as below

![efd85a2f-2038-409a-ba09-10c0ac5a9a78.png|830](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/efd85a2f-2038-409a-ba09-10c0ac5a9a78.png) [^96]

\

after changing the names its recreating

```
docker compose up -d
```

![ed70cdbc-dd9b-4a20-84c4-a485aa94c0df.png|1029.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/ed70cdbc-dd9b-4a20-84c4-a485aa94c0df.png) [^97]

\

Now names changed

```
docker ps
```

![a72f7b88-e7da-4c4e-b9c8-1fa2126fb48f.png|951.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/a72f7b88-e7da-4c4e-b9c8-1fa2126fb48f.png) [^98]

---

# <mark style="background-color:#f8914d;">**Shipping docker setup**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

<mark>**Multi stage build - Mainly for java projects**</mark>

![d7dd1a59-9988-44ce-baab-05d589ccff79.png|796](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d7dd1a59-9988-44ce-baab-05d589ccff79.png) [^99]

\

![c7aa5c52-fad5-4f62-a95e-a0d35110a93d.png|873](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c7aa5c52-fad5-4f62-a95e-a0d35110a93d.png) [^100]

\

git push & pull

![8f19b35c-c78f-4cab-a30c-477770ce0a40.png|965.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8f19b35c-c78f-4cab-a30c-477770ce0a40.png) [^101]

\

Generally java application will have more memory

```
docker build -t shipping:1 .
```

![75591377-93f3-457e-a916-a6f9f3fdabc7.png|1090.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/75591377-93f3-457e-a916-a6f9f3fdabc7.png) [^102]

\

![7d7c5869-68f8-4656-b4c3-1e1d30534876.png|977](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/7d7c5869-68f8-4656-b4c3-1e1d30534876.png) [^103]

\

git push & pull

\

shipping starting

```
docker compose up -d
```

![bd05ecb2-2ae1-4da7-9096-f43cbea278d6.png|1035.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/bd05ecb2-2ae1-4da7-9096-f43cbea278d6.png) [^104]

\

![aae3aa06-eb15-40ae-914e-4a015303c91c.png|682](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/aae3aa06-eb15-40ae-914e-4a015303c91c.png) [^105]

\

# <mark style="background-color:#f8914d;">**RabbitMQ & Payment docket setup**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

only below lines in docker compose file for RabbitMQ

![8d431a03-06ea-4ea8-84c4-da8c4a8bd1ee.png|764](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8d431a03-06ea-4ea8-84c4-da8c4a8bd1ee.png) [^106]

\

<mark>**Payment**</mark>

![bef80223-92d8-472f-ae0f-e9492ff9ca8b.png|794](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/bef80223-92d8-472f-ae0f-e9492ff9ca8b.png) [^107]

\

git push & pull

![01562d95-5cd1-4f4b-9a22-76f172959c99.png|951.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/01562d95-5cd1-4f4b-9a22-76f172959c99.png) [^108]

\

building payments images

```
docker build -t payment:1 .
```

![e8ae3d8a-7574-4bd1-93b5-7599ed256ab9.png|1211.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e8ae3d8a-7574-4bd1-93b5-7599ed256ab9.png) [^109]

\

rebuild the web image also as we changed the web docker file

```
docker build -t web:1 .
```

![87403693-0e5d-4b41-98be-22f1c96470d3.png|1110.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/87403693-0e5d-4b41-98be-22f1c96470d3.png) [^110]

\

```
docker compose up -d
```

![3c02e029-7a0d-4451-a827-3359273c3ed3.png|1038.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3c02e029-7a0d-4451-a827-3359273c3ed3.png) [^111]

![aae3aa06-eb15-40ae-914e-4a015303c91c.png|682](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/aae3aa06-eb15-40ae-914e-4a015303c91c.png) [^112]

\

\

# <mark style="background-color:#f8914d;">**Shell script for docker installation**<!-- {"backgroundCycleColor":"24"} --></mark>

\

![d389dbce-cec1-41e9-9188-87b5e86c6b24.png|939.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d389dbce-cec1-41e9-9188-87b5e86c6b24.png) [^113]

\

On Docker server - it will install docker & docker compose

<mark style="background-color:#f8d616;">curl<!-- {"backgroundCycleColor":"25"} --></mark> [<mark style="background-color:#f8d616;">https://raw.githubusercontent.com/daws-76s/shell-script/main/19-docker-install.sh<!-- {"backgroundCycleColor":"25"} --></mark>](https://raw.githubusercontent.com/daws-76s/shell-script/main/19-docker-install.sh) <mark style="background-color:#f8d616;">\| sudo bash<!-- {"backgroundCycleColor":"25"} --></mark> 

![e5b4548f-31d1-4b0f-9d99-348e043de333.png|1139.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e5b4548f-31d1-4b0f-9d99-348e043de333.png) [^114]

---

# <mark style="background-color:#f8914d;">**Build all Docker Images at one go using for loop shell script**<!-- {"backgroundCycleColor":"24"} --></mark>

```
docker ps
git clone https://github.com/daws-76s/roboshop-docker.git
```

![1d42907a-32c9-499c-9805-d0454f9eb51a.png|1076.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/1d42907a-32c9-499c-9805-d0454f9eb51a.png) [^115]

\

```
cd roboshop-docker
ls 
for i in mongodb mysql catalogue cart user shipping payment web ; do cd $i ; docker build -t $i:v1 . ; cd .. ; done
```

![fe73a148-190c-4af3-8522-09018977ccea.png|1187.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/fe73a148-190c-4af3-8522-09018977ccea.png) [^116]

\

images build completed

```
docker images
```

![9b22fea0-d8e1-45f4-b42d-019e484f92d9.png|1102.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/9b22fea0-d8e1-45f4-b42d-019e484f92d9.png) [^117]

\

Now creating a docker network

```
docker network create roboshop
```

![d6822752-e937-46d8-ba53-93d0a90c5e9f.png|1157.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d6822752-e937-46d8-ba53-93d0a90c5e9f.png) [^118]

\

Now all images will turn into containers and starts running

```
docker compose up -d
```

![e1677688-3b80-4a9e-b72c-bf012d359bce.png|1095.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e1677688-3b80-4a9e-b72c-bf012d359bce.png) [^119]

\

order placed

![](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3a839a32-d9a9-493f-946d-2ba605b6c954.png) [^120]

\

to check the logs 

```
docker logs shipping
docker logs payment
```

\

```
Docker compose down
```

![f1597fd2-9d78-40d9-9831-f37545dd05d1.png|1117.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f1597fd2-9d78-40d9-9831-f37545dd05d1.png) [^121]

\

# <mark style="background-color:#f8914d;">**Docker Best Practices**<!-- {"backgroundCycleColor":"24"} --></mark>

![1043f2d6-3afe-465c-99e5-cfed85a29149.png|966.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/1043f2d6-3afe-465c-99e5-cfed85a29149.png) [^122]

\

# <mark style="background-color:#f8914d;">**Keep containers size small**<!-- {"backgroundCycleColor":"24"} --></mark>

If you see few have high size 1GB crossed <mark style="background-color:#f3de6c;">(best practice is images always less than 1GB)<!-- {"backgroundCycleColor":"14"} --></mark>

```
docker images
```

![691cf9dc-689a-4edb-9602-8f0f4963802b.png|1099.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/691cf9dc-689a-4edb-9602-8f0f4963802b.png) [^123]

\

in docker hub site, search for **alpine images those will have lesser sizes**

![e61666a1-b7c4-4931-b4be-cc4ab660a3d9.png|1027.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e61666a1-b7c4-4931-b4be-cc4ab660a3d9.png) [^124]

![8389e222-71fa-40f4-a842-d3ae0ce12a49.png|1085.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8389e222-71fa-40f4-a842-d3ae0ce12a49.png) [^125]

\

After using alpine images space decreased

![53fc75cb-7de5-4556-8ec5-fa60438fd3d7.png|1006](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/53fc75cb-7de5-4556-8ec5-fa60438fd3d7.png) [^126]

![8d2e53e8-cdeb-403b-b6ee-aa07a507935b.png|1099.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8d2e53e8-cdeb-403b-b6ee-aa07a507935b.png) [^127]

\

# <mark style="background-color:#f8914d;">**MULTI STAGE BUILDS**<!-- {"backgroundCycleColor":"24"} --></mark>

Mostly used in Java projects ( this helps in decreasing size of images)

\

<mark style="background-color:#f8d616;">**Interview Q - What is multi stage builds in Docker?**<!-- {"backgroundCycleColor":"25"} --></mark>

**Ans:** It mainly used in java application, For usually java applications we will get the JAR file as Build, we will use one stage to build the JAR file. Now we will copy the jar file into the another stage(build) where we will have only the JDK & JRE environment. so that we can reduce the image size. We don't need Maven in run time environment. 

\

\

![887e52ec-a93f-4954-9922-7166a678fc53.png|984.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/887e52ec-a93f-4954-9922-7166a678fc53.png) [^128] 

\

ex: two dockers

![6d3c3f51-7c71-4e4d-b455-1cf214832864.png|890](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/6d3c3f51-7c71-4e4d-b455-1cf214832864.png) [^129]

\

# <mark style="background-color:#f8914d;">**Docker Volumes**<!-- {"backgroundCycleColor":"24"} --></mark>

![7b94c3ea-4019-453e-a0f0-740c8fcea676.png|1031.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/7b94c3ea-4019-453e-a0f0-740c8fcea676.png) [^130]

```
docker run -d -p 80:80 nginx
docker ps
```

![b77ac1df-40e5-4ee6-b3d0-4055c7baf2a9.png|1097.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b77ac1df-40e5-4ee6-b3d0-4055c7baf2a9.png) [^131]

```
docker exec -it 5734dgfgdfe32f bash
echo "hello Docker volumes: > volume.html
```

![3636c692-06bf-448e-b0b0-ab88201559a8.png|1111.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3636c692-06bf-448e-b0b0-ab88201559a8.png) [^132]

\

![](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/788046e3-d87f-43e1-8816-713fbe5cf4bd.png) [^133]

```
docker inspect <container id>
```

data stored here

![5765d4c3-4947-4d73-a7c3-56fe75a90e54.png|1033.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/5765d4c3-4947-4d73-a7c3-56fe75a90e54.png) [^134]

\

![9943fae9-5676-4c8d-8685-56f55d901adf.png|1085.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/9943fae9-5676-4c8d-8685-56f55d901adf.png) [^135]

\

Once we kill the docker container.. volume data will be auto deleted.

![d40a0721-8cf2-4af4-9edd-d739b54ef9a3.png|1159.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d40a0721-8cf2-4af4-9edd-d739b54ef9a3.png) [^136]

\

For any stateful applications or databases we need to have the data....

\

Docker volumes are two types

1. Unnamed Volumes

1. Names Volumes

<mark>**Unnamed Volumes  - generally we dont use this**</mark>

creating one directory and give it to docker container

![7b24fc32-edb2-4b85-b030-3dda8b1cd9cd.png|907](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/7b24fc32-edb2-4b85-b030-3dda8b1cd9cd.png) [^137]

\

Mounting that folder while creating container

```
docker run -d -p 80:80 -v /home/centos/nginx-data:/usr/share/nginx/html nginx
```

![76df20b1-ee72-4d4e-9200-ca0be1838761.png|1108.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/76df20b1-ee72-4d4e-9200-ca0be1838761.png) [^138]

\

```
docker ps
```

![b1ff4d5c-9be4-4e98-8113-99b357bbb2e3.png|1120.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/b1ff4d5c-9be4-4e98-8113-99b357bbb2e3.png) [^139]

```
docker exec -it 5734dgfgdfe32f bash
```

```
echo "hello Docker volumes: > volume.html
```

![68ea7a82-3905-419b-bf96-de8ef6d0fc8e.png|1183](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/68ea7a82-3905-419b-bf96-de8ef6d0fc8e.png) [^140]

![c6be9302-7478-4f70-a84a-9ae1b402d237.png|642](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c6be9302-7478-4f70-a84a-9ae1b402d237.png) [^141]

\

Now removing the container

```
docker rm -f <container id>
```

![8601d434-3e5a-44e3-bdde-d0fdc718c630.png|814](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8601d434-3e5a-44e3-bdde-d0fdc718c630.png) [^142]

\

But still nginx folder is there and data under it is not deleted.

\

![5e1d23bf-1caa-4868-b3a9-da7d536109ac.png|748](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/5e1d23bf-1caa-4868-b3a9-da7d536109ac.png) [^143]

\

if i create container again & data still be availble.

```
docker run -d -p 80:80 -v /home/centos/nginx-data:/usr/share/nginx/html nginx
```

![76df20b1-ee72-4d4e-9200-ca0be1838761.png|1108](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/76df20b1-ee72-4d4e-9200-ca0be1838761.png) [^144]

![c6be9302-7478-4f70-a84a-9ae1b402d237.png|642](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/c6be9302-7478-4f70-a84a-9ae1b402d237.png) [^145]

\

\

<mark>**Names Volumes**</mark>

How we create network, same way we can create docker volumes

```
docker volume
```

![d99b350e-5ea8-49d0-9241-ec79d297dd49.png|939](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d99b350e-5ea8-49d0-9241-ec79d297dd49.png) [^146]

\

```
docker volume create nginx
```

![6f27009e-9722-4035-bebd-00f065eaa451.png|953](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/6f27009e-9722-4035-bebd-00f065eaa451.png) [^147]

```
docker volume inspect nginx
```

![846d429d-cae0-4418-95e2-a849c4ca65ab.png|1030](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/846d429d-cae0-4418-95e2-a849c4ca65ab.png) [^148]

\

creating a container using named volume(nginx)

```
docker run -d -p 80:80 -v nginx:/usr/share/nginx/html nginx
```

![e4bb53d7-8743-4734-818f-2f37d01d7d6a.png|1087.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/e4bb53d7-8743-4734-818f-2f37d01d7d6a.png) [^149]

\

\

adding volumes in docker compose file

![bd5864f1-ad31-4c22-8118-5ff2b72700d2.png|987.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/bd5864f1-ad31-4c22-8118-5ff2b72700d2.png) [^150]

\

![74b1c0e4-18da-4038-9b51-61fc82518db2.png|769](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/74b1c0e4-18da-4038-9b51-61fc82518db2.png) [^151]

\

\

After updating volumes and its path

![0ef3ed60-39ec-4868-b031-5cf6fddfbd57.png|1041.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/0ef3ed60-39ec-4868-b031-5cf6fddfbd57.png) [^152]

\

user registered

![35568fb4-9001-4173-8caa-7eb2d3374304.png|553](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/35568fb4-9001-4173-8caa-7eb2d3374304.png) [^153]

\

\

# <mark style="background-color:#f8914d;">**Limit privilege's**<!-- {"backgroundCycleColor":"24"} --></mark>

![be45c32a-97d1-4af7-848f-d114069e773b.png|841](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/be45c32a-97d1-4af7-848f-d114069e773b.png) [^154]

\

It will have access for host file system of base VM

```
docker run -d -p 8080:80 -v /:/test nginx
docker exec -it d102323 bash
```

![3df12646-d202-41b3-b5c2-7a3ebe26a473.png|1059.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3df12646-d202-41b3-b5c2-7a3ebe26a473.png) [^155]

\

<mark>So you should not run container with root privilege's</mark> 

creating user and group and adding user to that group

![0e2f7f0f-1042-4857-8c47-ca0826339867.png|1065](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/0e2f7f0f-1042-4857-8c47-ca0826339867.png) [^156]

\

git push & pull

image build

![fb691869-2110-4823-8221-c977f822a913.png|1025.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/fb691869-2110-4823-8221-c977f822a913.png) [^157]

\

docker containers

![20b493f4-77d9-424c-99ad-50447a5c6e76.png|1072.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/20b493f4-77d9-424c-99ad-50447a5c6e76.png) [^158]

\

Now we don't have root access only normal access

![97170eb6-6b08-478e-b97e-577a39ceb293.png|1140.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/97170eb6-6b08-478e-b97e-577a39ceb293.png) [^159]

\

# <mark>**Security scan - for docker**</mark>

![22305fad-bfad-42aa-a68a-09bfb641dd2e.png|989.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/22305fad-bfad-42aa-a68a-09bfb641dd2e.png) [^160]

\

\

All unused data will be deleted

```
docker system prune
```

![0d07f16b-02d4-481a-b539-f6dc9b061219.png|1097.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/0d07f16b-02d4-481a-b539-f6dc9b061219.png) [^161]

![11706846-d7e0-44bd-ad08-85ed0778b536.png|491](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/11706846-d7e0-44bd-ad08-85ed0778b536.png) [^162]

# 

# <mark>**Docker architecture**</mark> 

How requests(data) is coming & how requests are going..

![f0df8362-a561-4f7f-b23a-1ef74337cb30.png|937.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f0df8362-a561-4f7f-b23a-1ef74337cb30.png) [^163]

![5dc66212-eb15-465b-8b9d-e1e62eaeda0e.png|808](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/5dc66212-eb15-465b-8b9d-e1e62eaeda0e.png) [^164]

![3a5d79e4-1e3f-4960-a77b-b53785dc5f39.png|976](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/3a5d79e4-1e3f-4960-a77b-b53785dc5f39.png) [^165]

![f4eff319-e42b-400b-bcf9-fe606985fed4.png|977](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f4eff319-e42b-400b-bcf9-fe606985fed4.png) [^166]

\

# <mark>**Docker Layers - How docker works**</mark>

![2e1f81c9-68e0-4ba4-8196-ac11231e59aa.png|839](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/2e1f81c9-68e0-4ba4-8196-ac11231e59aa.png) [^167]

![004e11a5-a365-4fae-aa33-5831c74207f4.png|958.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/004e11a5-a365-4fae-aa33-5831c74207f4.png) [^168]

```
docker rmi -f 'docker images -a -q'
```

![90d7e10a-773a-4ccf-8227-c59a553ca1e7.png|1059.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/90d7e10a-773a-4ccf-8227-c59a553ca1e7.png) [^169]

\

![38fb8b18-123a-4724-b174-6559c913e335.png|1087.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/38fb8b18-123a-4724-b174-6559c913e335.png) [^170]

![8bddb25b-820d-40ab-b1a9-5a0e67db958d.png|1105.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/8bddb25b-820d-40ab-b1a9-5a0e67db958d.png) [^171]

\

tagging 

![d23d8291-cf34-40dd-bbdb-2dad9202eade.png|1135.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d23d8291-cf34-40dd-bbdb-2dad9202eade.png) [^172]

\

![dac97de9-3501-4a6a-b4c1-73332ee07c84.png|1157.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/dac97de9-3501-4a6a-b4c1-73332ee07c84.png) [^173]

\

![44ddd02a-025e-4e03-a8fa-0aa83e06565b.png|1124.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/44ddd02a-025e-4e03-a8fa-0aa83e06565b.png) [^174]

\

a small change

run echo hello world

![bfb0dafc-fded-4581-9e6b-96478ad6a193.png|1001](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/bfb0dafc-fded-4581-9e6b-96478ad6a193.png) [^175]

\

git pull

\

![d59a1b70-c38b-44dc-80ec-e4c526fda60e.png|1096.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/d59a1b70-c38b-44dc-80ec-e4c526fda60e.png) [^176]

![5a2aa752-0b25-4611-aa16-3c67a9dfef7d.png|1100.3333740234375](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/5a2aa752-0b25-4611-aa16-3c67a9dfef7d.png) [^177]

[^1]: C
    github.com/instana/robot-shop/blob/master/mongo/Dockerfile
    E
    instana / robot-shop
    Q Type to search
    <> Code O Issues 6 17 Pull requests 8 Actions Projects @ Security \~ Insights
    I Files
    robot-shop / mongo / Dockerfile
    & master
    +
    Q
    steveww update all versions
    Q Go to file
    t
    Code
    Blame 4 lines (2 loc) . 54 Bytes
    .github
    DCOS
    FROM mongo : 5
    K8s
    3
    COPY \*. js / docker-entrypoint-initdb.d/
    OpenShift
    Swarm
    cart
    catalogue
    dispatch
    > fluentd
    >
    load-gen

[^2]: mongodb
    mysql
    redis
    rabbitma
    catalogue
    cart
    user
    shipping
    payment
    web
    create dockerfile, create image, run as contianers

[^3]: EXPLORER
    . .
    test
    <> index.html ..\\test
    Dockerfile ...\\mongodb U X
    JS ca
    REPOS
    roboshop-docker > mongodb > Dockerfile
    > dockerfiles
    FROM mongo:5
    > notes
    2
    COPY \*. js /docker-entrypoint-initdb.d/
    roboshop-docker \\ mongodb __
    JS catalogue.js -
    U
    Dockerfile
    U
    I
    JS user.js
    U

[^4]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/roboshop-docker (main)
    $ git add . ; git commit -m "docker"; git push origin main
    \[main (root-commit) e0c6d6d\] docker
    3 files changed, 46 insertions (+)
    create mode 100644 mongodb /Dockerfile
    create mode 100644 mongodb/catalogue . js
    create
    mode
    100644 mongodb /user is

[^5]: Instances (1) Info
    C
    Connect
    Instance state
    V
    Actions
    Launch instances
    V
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    Name
    Instance ID
    Instance state
    4
    Instance type v Status check
    Alarm status
    Av
    docker
    i-Occ440277055a12b6
    Running Q Q
    t3.medium
    View alarms +
    us

[^6]: X
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

[^7]: 54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ centos@ip-172-31-88-21 \~ \]$ sudo su -
    54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2. micro \| null
    \[ root@ip-172-31-88-21 \~ \]# yum install -y yum-utils
    Centos Stream 8 - AppStream
    Centos Stream 8 -
    BaseOS
    Centos Stream 8 - Extras

[^8]: 54 . 173 . 241 . 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# yum-config-manager --add-repo https: / /download. docker. com/linux/centos/docker-ce . repo
    Adding repo from: https: / /download. docker. com/linux/centos/docker-ce . repo
    54 . 173. 241. 201 \| 172. 31. 88.21 \| t2. micro \| null
    root@ip-172-31-88-21

[^9]: 54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# yum install docker-ce docker-ce-cli containerd. io docker-buildx-plugin docker-compose-plugin
    Docker CE Stable - x86 64
    835 kB/s \| 57 kB
    00: 00

[^10]: 54 . 173 . 241. 201 \| 172. 31. 88.21 \| t2.micro \| null
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

[^11]: 54 . 173. 241. 201 \| 172.31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES

[^12]: \[ centos@ip-172-31-88-21 \~ \]$ sudo su
    Last login: Thu Feb 8 02:35:18 UTC 2024 on pts/0
    54 . 173. 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# usermod -aG docker centos
    54 . 173 . 241. 201 \| 172. 31.88.21 \| t2.micro \| null
    \[ root@ip-172-31-88-21 \~ \]# exit
    logout

[^13]: 54 . 173. 241. 201 \| 172.31.88.21 \| t2. micro \| null
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

[^14]: daws-76s / roboshop-docker
    Q Type to search
    <> Code
    Issues 83 Pull requests
    Actions Projects D Wiki @ Security \~ Insights
    803 Settings
    roboshop-docker (Public
    Edit Pins
    Watch 0
    8 main
    8 1 Branch 0 Tags
    Q Go to file
    t
    Add file
    <> Code
    Local
    Codespaces
    joindevopscloud docker
    > Clone
    (?
    mongodb
    docker
    HTTPS
    SSH
    GitHub CLI
    DO README
    git@github. com: daws-76s/roboshop-dockerygit
    Use a password-protected SSH key.

[^15]: 3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| null
    \[ centos@ip-172-31-0-103 \~ \]$ git clone https: //github. com/daws-76s/roboshop-docker . git
    Cloning into 'roboshop-docker' ..
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.

[^16]: 3. 239. 203.108 \| 172. 31. 0.103 \| t3. medium \| https : //github. com/daws
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ 1s
    mongodb
    3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https : / /github. com/daws
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ cd mongodb/
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$

[^17]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker build -t mongodb : 1 .

[^18]: \[+\] Building 1.5s (4/6)
    =>
    \[internal\] load build definition from Dockerfile
    =>
    transferring dockerfile: 88B
    =
    \[internal\] load metadata for docker. io/library/mongo : 5
    \[internal\] load . dockerignore
    => transferring context: 2B
    (internal\] load build context
    => transferring context: 2.38kB
    =>
    \[1/2\] FROM docker . io/library/mongo : 50sha256 : 8548bb30175da00d18c0a180c649ac
    =>
    resolve docker . io/library/mongo : 50sha256 : 8548bb30175d6a00d18c0a180c649ac
    sha256: acab53147a6ae5a9ald93a8d17c104f7c13a691495921laa3d948b576767a6
    sha256: 7 76101966cfb8bfd93993211014154026599bela4a67ae9d4a30614324b5d5
    =>
    sha256: 005368eded60ec7519a618c0f1cbal2a2ce49d5260471556c7457376ff247f2e
    =>
    sha256: 39e7b26e733bidca330c7331d240c537019cfeeafd2edale5667dfed6664d

[^19]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    mongodb
    1
    9f14f1d4b471
    4 seconds ago
    697MB
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \] $

[^20]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker run -d mongodb:1 --name mongodb
    cbca8cd5069974149e79ff2f7a2657e934a12327670405862689f7995a5bbb46
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker . git

[^21]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https : / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker logs mongodb
    Error response from daemon: No such container: mongodb
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    3. 239. 203. 108 \| 172.31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker ps -a
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    cbca8cd50699
    mongodb : 1
    "docker-entrypoint. s..."
    16 seconds ago
    Exited (2) 15 s
    vigilant hugle

[^22]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker run -d --name mongodb mongodb : 1
    a70a0c88319795202e377c84a156c0e5861ddcd19485fcc29838500b487b2ba6

[^23]: 3. 239. 203. 108 \| 172. 31. 0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    a70a0c883197
    mongodb : 1
    "docker-entrypoint. s..."
    6 seconds ago
    Up 5 seconds

[^24]: {"t": {"$date" : "2024-02-11T02 : 07:26. 037+00:00"}, "s" ; "I",
    "C" : "REPL"
    "id" : 601531
    ten", "msg": "Setting new configuration state", "attr" : {"newState" : "ConfigReplicationDi
    ConfigPreStart"}}
    {"t": {"$date" : "2024-02-11T02 : 07: 26. 039+00:00"}, "s" : "I",
    "C" : "NETWORK"
    "id" : 23015
    "msg" : "Listening on" , "attr" : {"address" : "/tmp/mongodb-27017. sock"}}
    {"t": {"$date" : "2024-02-11T02 : 07: 26. 040+00:00"}, "s" : "I",
    "c" : "NETWORK"
    "id" : 23015
    "msg" : "Listening on" , "attr" : {"address" : "0.0.0.0"}}
    {"t": {"$cate" : "2024-02-11T02 : 07:26. 040+00 :00"}, "s" :"I",
    "C" : "NETWORK"
    "id" : 23016
    "msg" : "Waiting for connections" , "attr": {"port" :27017, "ss1" : "off"}}

[^25]: EXPLORER
    Dockerfile ... \\mongodb
    JS server.js U
    {} packa
    V REPOS
    roboshop-docker > catalogue > Dockerfile
    > dockerfiles
    H
    FROM node : 18
    > notes
    2
    EXPOSE 8080
    3
    roboshop-docker
    WORKDIR /opt/server
    4
    ENV MONGO=true
    catalogue -
    15
    COPY package. json /opt/server/
    Dockerfile -
    U
    6
    COPY server . js /opt/server/
    {} package.json -
    U
    7
    RUN npm install
    JS server.js -
    U
    8
    CMD \[ "node", "server. js"\]
    I
    mongodb

[^26]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/roboshop-docker (main)
    $ git add . ; git commit -m "docker"; git push origin main
    \[main 7f77a04\] docker
    3 files changed, 221 insertions (+)
    create mode 100644 catalogue
    create mode 100644 catalogue
    100614

[^27]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/mongodb \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (6/6) , done.

[^28]: 3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . gi
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker build -t catalogue:1
    \[+\] Building 0.3s (2/2)
    =>
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 1998

[^29]: => extracting sha256: fd653604fd26336c5a52d2549719563635567751646
    \[internal\] load build context
    transferring context: 5. 99kB
    \[2/5\] WORKDIR /opt/server
    \[3/5\] COPY package . json /opt/server/
    (4/5\] COPY server. js /opt/server/
    (5/5\] RUN nom install
    exporting to image
    exporting layers
    writing image sha256: 980ba9875c3985a5eflf2aca07f8c719f56d4b5a
    =>
    naming to docker . io/library/catalogue : 1

[^30]: 3. 239. 203. 108 \| 172. 31. 0.103 \| t3. medium \| https: / /github. com/daws-76s/rob
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    catalogue
    1
    980ba9875c39
    10 seconds ago
    1 . 17GB
    mongodb
    9f14fld4b471
    11 minutes ago
    697MB

[^31]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker run -d --name catalog
    42eca92a4ad10224b22b80c937bf176300cde619cb6a8aa3a958387f192f466c

[^32]: 3. 239. 203. 108 \| 172. 31. 0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-do
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    42eca924adl
    catalogue : 1
    "docker-entrypoint . s..."
    7 seconds ago
    Up 6 seconds
    ue
    a70a0c883197
    mongodb : 1
    "docker-entrypoint . s..."
    9 minutes ago
    Up 9 minutes
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-do
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker logs 42eca92a4ad1

[^33]: { "level" : "error", "time" : 1707617810762, "pid" : 1, "hostname" : "42eca92a4adl" , "msg" : "ERROR {\\"name\\": \\"MongoNe
    tworkError\\"}", "v":1}
    { "level" : "error", "time" : 1707617812768, "pid" : 1, "hostname" : "42eca92a4ad1", "msg" : "ERROR

[^34]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ ifconfig
    docker0: flags=4163<UP, BROADCAST , RUNNING, MULTICAST> mtu 1500
    inet 172.17.0.1 netmask 255.255.0.0 broadcast 172. 17.255.255
    inet6 fe80: : 42: 99ff: fee3: 432c prefixlen 64 scopeid 0x20<link>
    ether 02:42: 99:e3: 43:2c txqueuelen 0 (Ethernet)
    RX packets 5117 bytes 558495 (545.4 KiB)
    RX errors 0 dropped 0 overruns 0 frame 0
    TX packets 4729 bytes 25591271 (24. 4 MiB)
    TX errors 0 dropped 0 overruns 0 carrier 0 collisions 0

[^35]: eth0: flags=4163<UP, BROADCAST, RUNNING, MULTICAST>
    mtu 9001
    inet 172. 31 . 0.103
    netmask 255 . 255. 240.0 broadcast 172. 31. 15
    inet6 fe80: : ef : aoff: fed6: 40ed prefixlen 64 scopeid 0x20<lin
    ether 02:ef: a6:d6:40:ed txqueuelen 1000 (Ethernet)
    RX packets 613288 bytes 877166512 (836.5 MiB)
    RX errors 0 dropped 0 overruns 0 frame 0
    TX packets 56554 bytes 5665298 (5.4 MiB)
    TX errors 0 dropped 0 overruns 0 carrier 0 collisions 0

[^36]: docker0: flags=4163<UP, BROADCAST, RUNNING, MULTICAST>
    mtu 1500
    inet 172. 17.0.1 netmask 255. 255.0.0 broadcast 172. 17. 255.25
    inet6 fe80: : 42: 99ff: fee3: 432c prefixlen 64 scopeid 0x20<lin
    ether 02: 42: 99:e3: 43:2c txqueuelen 0 (Ethernet)
    RX packets 5117 bytes 558495 (545 . 4 KiB)
    RX errors 0 dropped 0 overruns 0 frame 0
    TX packets 4729 bytes 25591271 (24. 4 MiB)
    TX errors 0 dropped 0 overruns 0 carrier 0 collisions 0
    172 . 17.0. 1

[^37]: "Aliases": null,
    "MacAddress": "02: 42: ac: 11 : 00: 03"
    "NetworkID": "3240513bbaf768eb2cdb169bbc9670634e39
    "EndpointID": "15bodf0f9fa930121a6533f20aebee545f8
    "Gateway": "172. 17.0.1"
    " IPAddress": "172. 17.0.3
    "IPPrefixLen" : 16,
    " IPv6Gateway" :
    "GlobalIPV6Address" :
    "GlobalIPv6PrefixLen" : 0,
    "DriverOpts": null,
    "DNSNames": null

[^38]: "Gateway": "172. 17.0.1",
    "IPAddress": "172. 17.0.3" --> catalogue
    "172. 17.0.2" --> mongodb

[^39]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker network
    Usage: docker network COMMAND
    Manage networks
    Commands :
    connect
    Connect a container to a network
    create
    Create a network
    disconnect
    Disconnect a container from a network
    inspect
    Display detailed information on one or more networks
    1s
    List networks
    prune
    Remove all unused networks
    rm
    Remove one or more networks
    Run 'docker network COMMAND --help' for more information on a command.

[^40]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker network create roboshop
    c03649fe02fa96146fecef2b0d075ec28220ceebcebdcfa69488a3a91b07fc5
    3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$

[^41]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker network Is
    NETWORK ID
    NAME
    DRIVER
    SCOPE
    3240513bbaf7
    bridge
    bridge
    local
    cd529a8d74d5
    host
    host
    local
    e8f18552ceb0
    none
    null
    local
    c03649f6e02f
    roboshop
    bridge
    local

[^42]: 3. 239 . 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker network Is
    NETWORK ID
    NAME
    DRIVER
    SCOPE
    3240513bbaf7
    bridge
    bridge
    local
    cd529a8d74d5
    host
    host
    local
    e8f18552ceb0
    none
    null
    local
    c03649f6e02f
    roboshop
    bridge
    local
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ ifconfig
    or-c03649f6e02f: flags=4099<UP , BROADCAST , MULTICAST> mtu 1500
    inet 172. 18.0.1 netmask 255.255.0.0 broadcast 172. 18.255.255
    ether 02:42:19:1c:20:be txqueuelen 0 (Ethernet)
    RX packets 582 bytes 41706 (40.7 KiB)
    RX errors 0 dropped 0 overruns 0 frame 0
    TX packets 594 bytes 86242 (84.2 KiB)
    TX errors 0 dropped 0 overruns 0
    carrier 0
    collisions 0

[^43]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker rm -f docker ps -a -q
    42eca92a4ad1
    a70a0c883197
    cbca8cd50699

[^44]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker run -d --name mongodb --network=roboshop
    mongodb : 1
    e421fled96a17c7bc1646529ee2b8ce286fblad259a284a10cffOf31e78cb563

[^45]: "Gateway": "172 . 18 .0.1"
    "IPAddress": "172 . 18.0.?"
    "IPPrefixLen" : 16,
    "IPv6Gateway" :
    "GlobalIPV6Address" :
    "GlobalIPv6PrefixLen" : 0,
    "DriverOpts": null,
    "DNSNames": \[
    "mongodb"
    "e421f1cd96a1"

[^46]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker run -d --name catalogue --network=robosho
    p catalogue : 1
    de98cecdc6f6b30e22dda83d9a523441d50a230a55e05984593cf0146a4a7db2

[^47]: 3. 239. 203. 108 \| 172. 31.0. 103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-do
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    de98cecdc6f6
    catalogue : 1
    "docker-entrypoint. s..."
    4 seconds ago
    Up 2 second
    ogue
    e421fled96al
    mongodb : 1
    "docker-entrypoint. s..."
    58 seconds ago
    Up 56 secon
    db

[^48]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ docker logs catalogue
    (node : 1) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monitoring engine is
    1 be removed in a future version. To use the new Server Discover and Monitoring engi
    eUnifiedTopology: true } to the MongoClient constructor.
    (Use node --trace-warnings . . . ' to show where the warning was created)
    { "level" : "info" , "time" : 1707618484464, "pid" : 1, "hostname": "de98cecdc6f6" , "msg" : "Starte
    1}
    { "level" ; "info" , "time" : 1707618484490, "pid" :1, "hostname" : "de98cecdc6f6" , "msg" : "MongoD
    3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \] $

[^49]: V REPOS
    roboshop-docker > web >
    Dockerfile
    > dockerfiles
    1
    FROM nginx
    > notes
    2
    RUN rm -rf /usr/share/nginx/html/index. html
    3
    RUN rm -rf /etc/nginx/nginx. conf
    roboshop-docker
    4
    RUN rm -rf /etc/nginx/conf . d/default. conf
    > catalogue
    5
    COPY roboshop. conf /etc/nginx/nginx. conf
    > mongodb
    6
    ADD static /usr/share/nginx/html/
    web
    > static
    Dockerfile
    M
    roboshop.conf
    M

[^50]: REPOS
    roboshop-docker > web > @ roboshop.conf
    > dockerfiles
    1
    proxy_http_version 1.1;
    > notes
    2
    location /images/ {
    13
    roboshop-docker
    expires 5s;
    14
    root /usr/share/nginx/html;
    > catalogue
    5
    try_files $uri /images/placeholder . jpg;
    > mongodb
    6
    web
    17
    location /api/catalogue/ { proxy_pass http://catalogue : 8080/;}
    static
    8
    location /health {
    Dockerfile
    9
    stub_status on;
    10
    access_log off;
    H
    roboshop.conf
    M
    11

[^51]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/roboshop-docker (main)
    $ git add . ; git commit -m "docker"; git push origin main
    warning: in the working copy of 'web/static/cart. html', LF will be replaced by CRLF the n
    warning: in the working copy of 'web/static/css/auto-complete. css', LF will be replaced b
    warning: in the working copy of 'web/static/css/style.css', LF will be replaced by CRLF t
    warning: in the working copy of 'web/static/empty. html', LF will be replaced by CRLF the

[^52]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/catalogue \]$ cd . ./web/
    3. 239.203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker build -t web:1 .
    \[+\] Building 0.3s (2/2)
    =>
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 1818
    => \[internal\] load metadata for docker. io/library/nginx: latest

[^53]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker.
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker run -d -p 80:80 --name web
    --n
    eb : 1
    27e0137d85c049efc3724aa106dd117336059f460507ce92330c4e29fee9eca4
    3. 239 . 203. 108 \| 172. 31.0.103 \| t3. medium \| https : / /github.com/daws-76s/roboshop-docker
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    27e0137d85c0
    web : 1
    "/ docker-entrypoint...."
    3 seconds ago
    Up 2 seconds
    P/ : : :80->80/tcp
    web
    de98cecdc6f6
    catalogue : 1
    "docker-entrypoint . s..."
    10 minutes ago
    Up 10 minutes
    catalogue
    e421fled96al
    mongodb : 1
    "docker-entrypoint . s..."
    11 minutes ago
    Up 11 minutes
    mongodb

[^54]: ->
    G
    Not secure 3.239.203.108
    Stan's Robot Shop
    Search
    Login / Register
    EVTIM
    Welcome to Stan's Robot Shop
    Cart
    STAN
    Here you will find all of Stan's friends. Have a browse around and
    Empty
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    has been built using various technologies:
    . AngularJS (1.X)
    . Nginx
    . NodeJS
    . Java

[^55]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    27e0137d85co
    web : 1
    " / docker-entrypoint...."
    3 seconds ago
    Up 2 seconds
    P, : : :80->80/tcp
    web
    de98cecdc616
    catalogue : 1
    "docker-entrypoint. s..."
    10 minutes ago
    Up 10 minutes
    catalogue
    e421ficd96al
    mongodb : 1
    "docker-entrypoint . s..."
    11 minutes ago Up 11 minutes
    mongodb
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker exec -it 27e0137d85c0 bash
    root@27e0137d85co : /#

[^56]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker exe
    root@27e0137d85c0 : /# curl http: //catalogue : 8080/health
    { "app" : "OKK" , "mongo" : true } root@27e0137d85c0 : /#

[^57]: root@27e0137d85c0: /# curl localhost/api/catalouge/health
    <html>
    <head><title>404 Not Found</title></head>
    <body>
    <center><h1>404 Not Found</h1></center>
    <hr><center>nginx/1 . 25.3</center>
    </body>
    </html>
    root@27e0137d85co : /#

[^58]: root@27e0137d85c0: /# cd /etc/nginx/
    root@27e0137d85c0 : /etc/nginx# 1s
    conf.d default.d fastcgi params mime. types modules nginx. conf scgi_params uwsgi_params
    root@27e0137d85c0 : /etc/nginx# cat nginx. conf

[^59]: dependecies are there. .
    stop --> oneby one
    start --> one by one

[^60]: Docker Compose overview
    A Important
    Docker's documentation refers to and describes Compose V2 functionality.
    Effective July 2023, Compose V1 stopped receiving updates and is no longer in new Docker
    Desktop releases. Compose V2 has replaced it and is now integrated into all current Docker
    Desktop versions. For more information, see Migrate to Compose V2.
    Docker Compose is a tool for defining and running multi-container applications. It is the key to unlocking a
    streamlined and efficient development and deployment experience.
    Compose simplifies the control of your entire application stack, making it easy to manage services,
    networks, and volumes in a single, comprehensible YAML configuration file. Then, with a single command,
    you create and start all the services from your configuration file.

[^61]: Compose works in all environments; production, staging, development, testing, as well as Cl workflows. It
    also has commands for managing the whole lifecycle of your application:
    . Start, stop, and rebuild services
    View the status of running services
    . Stream the log output of running sewices
    . Run a one-off command on a service

[^62]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ curl -L https: //github. com/docker/compose/releases/dow
    nload/2. 24.5/docker-compose- uname -s - uname -m
    -o /usr/local/bin/docker-compose
    $ Total
    $ Received $ Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    0
    0
    0
    0
    0
    0
    0
    0 --: --:
    -- : -- :
    OWarning. Failed
    create
    the file /usr/local/bin/docker-compose: Permission
    Warning: denied
    100
    9
    100
    9
    0
    123
    --
    123
    curl :
    (23)
    Failed
    writing body
    (0
    != 9)

[^63]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ sudo chmod +x /usr/local/bin/docke

[^64]: List running compose projects
    pause
    Pause services
    port
    Print the public port for a port binding.
    ps
    List containers
    pull
    Pull service images
    push
    Push service images
    restart
    Restart service containers
    rm
    Removes stopped service containers
    run
    Run a one-off command on a service.
    scale
    Scale services
    start
    Start services
    stats
    Display a live stream of container (s) resource usage
    stop
    Stop services
    top
    Display the running processes
    unpause
    Unpause services

[^65]: it will create a netowrk, create volumes. attach network and volumes

[^66]: C
    github.com/instana/robot-shop/blob/master/docker-compose.yaml
    Files
    robot-shop / docker-compose.yaml D
    & master
    +
    steveww update all versions
    Q Go to file
    t
    Code
    Blame 172 lines (170 loc) . 3.67 KB
    search.html
    version: '3'
    N H
    shipping.html
    services :
    3
    mongodb :
    splash.html
    4
    build:
    Dockerfile
    5
    context: mongo
    image: ${REPO}/rs-mongodb : $ { TAG}
    default.conf.template
    networks :
    entrypoint.sh
    - robot - shop

[^67]: REPOS
    roboshop-docker > < docker-compose.yaml
    services :
    > dockerfiles
    6
    # docker run -d - -name mongodb --network=roboshop mongodb : 1
    > notes
    7
    mongodb :
    v roboshop-docker
    8
    image: mongodb : 1
    > catalogue
    9
    # networks :
    > mongodb
    10
    # - roboshop
    > web
    11
    12
    catalogue :
    docker-compose.y... U
    13
    image: catalogue : 1
    14
    # networks :
    15
    # - roboshop
    16
    depends_on :
    17
    - mongodb
    18
    19
    web :
    20
    image: web : 1
    21
    ports :
    22
    "80:80"
    23
    depends_on:
    24
    - catalogue
    25

[^68]: V REPOS
    roboshop-docker > < docker-compose.yaml
    > dockerfiles
    P
    networks :
    > notes
    2
    default:
    roboshop-docker
    B
    external: true
    4
    name: roboshop
    > catalogue
    5
    services :
    > mongodb
    6
    # docker run -d - -name mongodb - -network=roboshop mongodb : 1
    web
    7
    mongodb :
    docker-compose.... M
    8
    image: mongodb : 1
    9
    # networks :
    10
    # - roboshop
    11
    12
    catalogue :
    13
    image: catalogue : 1
    14
    # networks :
    15
    # - roboshop
    16
    depends_on :
    17
    mongodb
    18
    19
    web :
    20
    image: web: 1
    21
    ports :
    > OUTLINE
    22
    "80:80"
    23
    > TIMELINE
    depends_on:

[^69]: 3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker rm -f docker ps -a -q
    1c2117999663
    46f2f9aeab07
    de98cecdc6f6
    e421ficd96al

[^70]: 3. 239. 203.108 \| 172. 31. 0.103 \| t3. medium \| https : / /github. com/daws-7
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ git pull
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4) , done.
    remote: Compressing objects: 100% (3/3) , done.
    m

[^71]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and exter
    (+\] Running 3/3
    Container roboshop-docker-mongodb-1
    Started
    Container roboshop-docker-catalogue-1 Started
    Container roboshop-docker-web-1
    Started
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \] $

[^72]: 3. 239 . 203 . 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    19fcc2f91991
    web : 1
    " / docker-entrypoint...."
    52 seconds ago
    Up 50 sec
    P, :: :80->80/tcp
    roboshop-docker-web-1
    77elae0ca58b
    catalogue : 1
    "docker-entrypoint . s..."
    52 seconds ago
    Up 51 sec
    roboshop-docker-catalogue-1
    eb702fb8c5de
    mongodb : 1
    "docker-entrypoint. s..."
    52 seconds ago
    Up 51 sec
    roboshop-docker-mongodb-1

[^73]: C
    A Not secure 3.239.203.108
    Stan's Robot Shop
    Login / Register
    Welcome to Stan's Robot Shop
    Cart
    Here you will find all of Stan's friends. Have a browse around and
    Empty
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    . Artificial
    has been built using various technologies:
    Intelligence
    . Robot
    . AngularJS (1.X)
    Nginx
    NodeJS
    Java
    Python
    Golang
    PHP (Apache)
    . MongoDB
    Redis

[^74]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker compose down
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and external
    \[+\] Running 1/2
    Container roboshop-docker-web-1
    Removed
    Container roboshop-docker-catalogue-1 Stopping

[^75]: EXPLORER
    Dockerfile ... \\catalogue
    Dockerfile .. \\user U X
    Dock
    REPOS
    roboshop-docker > user > Dockerfile
    > dockerfiles
    H
    FROM node : 18
    > notes
    2
    EXPOSE 8080
    13
    v roboshop-docker
    WORKDIR /opt/server
    4
    ENV MONGO=true
    catalogue
    15
    COPY package. json /opt/server/
    Dockerfile
    6
    COPY server . js /opt/server/
    {} package.json
    7
    RUN npm install
    I
    JS server.js
    8
    CMD \["node", "server. js" \]
    > mongodb
    user
    Dockerfile
    U
    {} package.json
    U
    JS server.js
    U

[^76]: EXPLORER
    Dockerfile ...\\cart U
    JS server.js .. \\cart U X Dockerfile ... \\web
    doc
    V REPOS
    roboshop-docker > cart > JS server.js > \[\] cataloguePort
    > dockerfiles
    const redis = require(' redis' ) ;
    > notes
    const request = require ( ' request' ) ;
    3
    roboshop-docker
    const bodyParser = require( ' body-parser' ) ;
    14
    const express = require (' express' ) ;
    cart
    15
    const pino = require('pino' ) ;
    Dockerfile
    U
    6
    const expPino = require(' express-pino-logger' ) ;
    () package.json_
    U
    7
    / / Prometheus
    JS server.js
    U
    8
    const promClient = require( ' prom-client' ) ;
    > catalogue
    19
    const Registry = promClient . Registry;
    > mongodb
    10
    const register = new Registry( ) ;
    11
    const counter = new promClient . Counter({
    > user
    12
    name: 'items_added' ,
    >
    web
    13
    help: 'running count of items added to cart',
    docker-compose...
    M
    14
    registers: \[register\]
    15
    });
    16
    17
    18
    var redisConnected = false;
    19
    20
    var redisHost = process . env . REDIS_HOST \| \| 'redis'
    21
    r catalogueHost = process . env . CATALOGUE_HOST \| \| ' catalogue'
    > OUTLINE
    22
    var cataloguePort = process . env. CATALOGUE_PORT \| \|
    '8080
    23
    > TIMELINE

[^77]: Unpacking objects: 100% (10/10) , 5.67 KiB \| 2. 84 MiB/s, done.
    From https: //github. com/daws-76s/roboshop-docker
    7ed51f9. . 66d7705 main
    -> origin/main
    Updating 7ed51f9. . 66d7705
    Fast-forward
    cart/Dockerfile
    8
    + +
    cart/package . json
    -
    22
    +++++
    cart/server . js
    386 ++++++
    docker-compose . yaml
    2
    +
    user/Dockerfile
    8
    ++
    user/package . json
    21 +++++
    user/server . js
    \| 307 +++++++
    7 files changed, 754 insertions (+)
    create mode 100644 cart/Dockerfile
    create mode 100644 cart/package . json

[^78]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/user \]$ docker build -t user:1
    \[+\] Building 0.5s (8/9)
    \[internal\] load build definition from Dockerfile
    => transferring dockerfile: 1998
    \[internal\] load metadata for docker . io/library/node : 18
    \[internal\] load . dockerignore
    =>
    => transferring context: 2B
    (1/51
    FROM do
    /lib
    79
    192
    9
    dedid362 fa

[^79]: 3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https : / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/user \]$ cd . ./cart/
    3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/cart \]$ docker build -t cart:1 .
    \[+\] Building 0.8s (8/9)
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 1998
    =>
    \[internal\] load metadata for docker . io/library/node : 18

[^80]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/cart \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    cart
    1
    46d0933bce0d
    7 seconds ago
    1 . 18GB
    user
    T
    7f2ebc44dc84
    40 seconds ago
    1 . 17GB
    web
    1
    07824d803084
    34 minutes ago
    188MB
    <none>
    <none>
    515f4f5b3b55
    41 minutes ago
    188MB
    catalogue
    1
    980ba 9875c39
    About an hour ago
    1 . 17GB
    mongodb
    1
    9f14f1d4b471
    About an hour ago
    697MB
    nginx
    latest
    b690f5f0a2d5
    3 months ago
    187MB

[^81]: 25
    roboshop-docker
    26
    redis :
    > cart
    27
    > catalogue
    28
    user:
    > mongodb
    29
    image: user : 1
    > user
    30
    depdends_on:
    >
    web
    31
    - redis
    32
    - mongodb
    docker-compose.... M
    33
    34
    user:
    35
    image: cart : 1
    36
    depdends_on :
    37
    - redis
    38
    - catalogue
    39

[^82]: 5 . 259.
    05 . 106
    . medium
    \| https : / /github . com/ daws
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/cart \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (1/1) , done.

[^83]: \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and exte
    (+\] Running 9/9
    redis 8 layers \[! ! !!!!!:\]
    OB/OB
    Pulled
    c57ee5000d61 Already exists
    a378724be99b Pull complete
    5224cb0f59c4 Pull complete
    ef9d9b4bldb0 Pull complete
    234f81aa6553 Pull complete
    1clf1738e37a Pull complete
    4f4fb700ef54 Pull complete
    v a4eb7afb9a79 Pull complete
    \[+\] Running 4/6
    Container roboshop-docker-redis-1
    Started
    Container roboshop-docker-mongodb-1
    Started
    Container roboshop-docker-catalogue-1
    Started
    Container roboshop-docker-user-1
    Started
    Container roboshop-docker-web-1
    Starting
    Container roboshop-docker-cart-1
    Starting

[^84]: \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    f6d1c9afa0eb
    cart : 1
    "docker-entrypoint . s..."
    9 seconds ago
    Up 6 seconds
    roboshop-docker-cart-1
    cb620f0ba44c
    web : 1
    " / docker-entrypoint...."
    9 seconds ago
    Up 6 seconds
    : : :80->80/tcp
    roboshop-docker-web-1
    86610ae33431
    user : 1
    "docker-entrypoint . s..."
    9 seconds ago
    Up 7 seconds
    roboshop-docker-user-1
    Ocage 7bc2997
    catalogue : 1
    "docker-entrypoint . s..."
    9 seconds ago
    Up 7 seconds
    roboshop-docker-catalogue-1
    ae5d57991073
    mongodb : 1
    "docker-entrypoint. s..."
    10 seconds ago
    Up 8 seconds
    roboshop-docker-mongodb-1
    b2a3f6a703a3
    redis
    "docker-entrypoint. s..."
    10 seconds ago
    Up 8 seconds
    roboshop-docker-redis-1

[^85]: C
    A Not secure 3.239.203.108/login
    Stan's Robot Shop
    Login / Register
    Welcome to Stan's Robot Shop
    Cart
    Here you will find all of Stan's friends. Have a browse around and
    Empty
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    . Artificial
    has been built using various technologies:
    Intelligence
    . Robot
    AngularJS (1.X)
    Nginx
    NodeJS
    Java
    Python
    Golang
    PHP (Apache)
    MongoDB
    Redis

[^86]: V REPOS
    roboshop-docker > mysql > > Dockerfile
    > dockerfiles
    H
    FROM mysql :5.7
    2
    1
    > notes
    ENV MYSQL_ROOT_PASSWORD=RoboShop@1
    3
    MYSQL_DATABASE=cities \\
    roboshop-docker
    14
    MYSQL_USER=shipping \\
    > cart
    5
    MYSQL_PASSWORD=RoboShop@1
    > catalogue
    6
    COPY scripts/\* /docker-entrypoint-initdb. d/
    > mongodb
    v mysql
    scripts
    shipping.sql - U
    Dockerfile
    U
    > shipping

[^87]: X1 Carbon@DESKTOP-CGKCN7Q MINGW64 /c/devops/daws76s/repos/roboshop-docker (main)
    $ git add . ; git commit -m "docker"; git push origin main
    warning: in the working copy of 'mysql/scripts/shipping. sql', LF will be replaced by CRLF the next t

[^88]: \[ centos@ip-172-31-0-103 \~/roboshop-docker/mysql \]$ docker build -t mysql:1
    \[+\] Building 0.2s (1/2)
    =>
    (internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 2198
    =>
    \[internal\] load metadata for docker . io/library/mysql :5.7

[^89]: roboshop-docker
    32
    - redis
    > cart
    33
    - mongodb
    34
    > catalogue
    35
    cart :
    > mongodb
    36
    image: cart :1
    v mysql
    37
    depends_on :
    \~ scripts
    38
    - redis
    shipping.sql
    39
    - catalogue
    I
    Dockerfile
    40
    41
    > shipping
    mysql :
    42
    image: mysql :1
    > user
    43
    > web
    docker-compose.... M

[^90]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github . co
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ git pull
    Already up to date.

[^91]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/rob
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name
    \[+\] Running 6/7
    " Container roboshop-docker-mysql-1
    Starting
    Container roboshop-docker-mongodb-1
    Running
    Container roboshop-docker-catalogue-1
    Running
    Container roboshop-docker-web-1
    Running
    Container roboshop-docker-redis-1
    Running

[^92]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    1f95692fd2a8
    mysql :1
    "docker-entrypoint . s..."
    15 seconds ago
    Up 13 sec
    cp
    roboshop-docker-mysql-1
    4ecb0c981429
    web : 1
    " / docker-entrypoint...."
    9 minutes ago
    Up 9 minu
    P, : : :80->80/tcp
    roboshop-docker-web-1
    f6d1c9afa0eb
    cart : 1
    "docker-entrypoint. s..."
    11 minutes ago
    Up 11 min
    roboshop-docker-cart-1
    86610ae33431
    user : 1
    "docker-entrypoint . s..."
    11 minutes ago Up 11 min
    roboshop-docker-user-1
    Ocage 7bc2997
    catalogue : 1
    "docker-entrypoint. s..."
    11 minutes ago
    Up 11 min
    roboshop-docker-catalogue-1
    ae5d57991073
    mongodb : 1
    "docker-entrypoint. s.."
    11 minutes ago
    Up 11 min

[^93]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https : / /github. com/daws-76s/roboshop-do
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    NAMES
    1f95692fd2a8
    mysql : 1
    "docker-entrypoint. s..."
    37 seconds ago
    Up 36 second
    cp
    roboshop-docker-mysql-1
    4ecb0c981429
    web : 1
    " / docker-entrypoint...."
    9 minutes ago
    Up 9 minutes
    P, : : :80->80/tcp
    roboshop-docker-web-1
    f6d1c9afa0eb
    cart : 1
    "docker-entrypoint . s..."
    12 minutes ago
    Up 12 minute
    roboshop-docker-cart-1
    86610ae33431
    user : 1
    "docker-entrypoint . s..."
    12 minutes ago Up 12 minute
    roboshop-docker-user-1
    Ocage 7bc2997
    catalogue : 1
    "docker-entrypoint. s..."
    12 minutes ago Up 12 minute
    roboshop-docker-catalogue-!
    ae5d57991073
    mongodb : 1
    "docker-entrypoint . s..."
    12 minutes ago
    Up 12 minute
    roboshop-docker-mongodb-1
    b2a3f6a703a3
    redis
    "docker-entrypoint. s..."
    12 minutes ago Up 12 minute
    roboshop-docker-redis-1

[^94]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https : / /github. com/daws-76s/roboshop-docke
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker logs roboshop-docker-mysql-1/

[^95]: 2024-02-11T03 : 34 : 42 . 3888572 0 \[Note\] Server socket created on IP:
    2024-02-11T03: 34 : 42 . 3904027 0 \[Warning\] Insecure configuration for --pid-file:
    ' in the path is accessible to all OS users. Consider choosing a different dire
    2024-02-11T03 : 34 : 42 . 4041562 0 \[Note\] InnoDB: Buffer pool (s) load completed at 2
    2024-02-11TO3: 34: 42 . 4210522 0 \[Note\] Event Scheduler: Loaded 0 events
    2024-02-11T03 : 34 : 42 . 4214082 0 \[Note\] mysqld: ready for connections,
    Version: '5.7. 44' socket: ' /var/run/mysqld/mysqld. sock'
    port: 3306 MySQL Com
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$

[^96]: EXPLORER
    ..\\web
    docker-compose.yaml M X
    Docker
    REPOS
    roboshop-docker > > docker-compose.yaml
    > dockerfiles
    21
    web :
    notes
    22
    image: web : 1
    roboshop-docker
    23
    container_name: web
    24
    ports :
    > cart
    25
    "80:80"
    > catalogue
    26
    depends_on:
    > mongodb
    27
    - catalogue
    mysql
    28
    scripts
    29
    redis :
    shipping.sql
    30
    image: redis
    I
    31
    container_name: redis
    Dockerfile
    32
    > shipping
    33
    user :
    > user
    34
    image: user :1
    > web
    35
    depends_on:
    docker-compose.... M
    36
    - redis
    37
    mongodb

[^97]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https:/ /github. com/daws-76s/roboshop-doc
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and exter
    \[+\] Running 7/14
    :. Container roboshop-docker-redis-1
    Recreated
    :. Container roboshop-docker-mysql-1
    Recreated
    Container roboshop-docker-mongodb-1
    Recreated
    i Container roboshop-docker-catalogue-1 Recreated
    : Container roboshop-docker-user-1
    Recreated
    Container roboshop-docker-cart-1
    Recreated
    Container roboshop-docker-web-1
    Recreated
    Container mysql
    Started
    Container mongodb
    Started
    Container redis
    Started
    Container catalogue
    Started
    Container user
    Started
    Container web
    Started
    Container cart
    Started

[^98]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https : //github. com/daws-76s/ro
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    ST
    NAMES
    dbd37aa2d4a3
    cart : 1
    "docker-entrypoint. s..."
    19 seconds ago
    UF
    cart
    e239c78d4f03
    web : 1
    "/ docker-entrypoint...."
    19 seconds ago
    : : : 80->80/tcp
    web
    dge942f05d78
    user : 1
    "docker-entrypoint. s..."
    29 seconds ago
    user
    69fd5192919c
    catalogue : 1
    "docker-entrypoint. s..."
    29 seconds ago
    UF
    catalogue
    eb504e85c67e
    mysql : 1
    "docker-entrypoint. s..."
    30 seconds ago
    P
    mysql
    4b8eee32b811
    mongodb : 1
    "docker-entrypoint. s..."
    30 seconds ago
    UF
    mongodb
    724a78f21956
    redis
    "docker-entrypoint . s..."
    30 seconds ago
    Up
    redis

[^99]: multi stage builds
    maven jdk (heavy)
    jar file
    runtime
    no need of maven, no need of jak, need jre
    jdk = jre + developmet packages

[^100]: EXPLORER
    ...\\web
    docker-compose.yaml
    Dockerfile .. \\shipping U X
    Dockerfile ... \\mysql
    V REPOS
    roboshop-docker > shipping > > Dockerfile
    > dockerfiles
    10
    COPY pom. xml /opt/shipping/
    notes
    11
    RUN mvn dependency : resolve
    roboshop-docker
    12
    COPY src /opt/shipping/src/
    13
    > cart
    RUN mvn package
    14
    > catalogue
    15
    #
    > mongodb
    16
    # Run
    > mysql
    17
    #
    shipping \~
    18
    FROM openjak :8-jdk
    > src
    19
    20
    Dockerfile
    EXPOSE 8080
    U
    21
    pom.xml
    U
    22
    WORKDIR /opt/shipping
    > user
    23
    web
    24
    ENV CART ENDPOINT=cart : 8080
    docker-compose.yaml
    25
    ENV DB HOST=mysql
    I
    26
    27
    COPY --from=build /opt/shipping/target/shipping-1.0. jar shipping . jar
    28
    29
    CMD \[ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping. jar" \]
    30

[^101]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ git pull
    remote: Enumeratiog objects: 26, done.
    remote: Counting objects: 100% (26/26) , done.
    remote: Compressing objects: 100% (18/18), done.
    remote: Total 25 (delta 2) , reused 25 (delta 2), pack-reused 0
    Unpacking objects: 20% (5/25)

[^102]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: / /github. com/daws-76s/roboshop-dock
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/shipping \]$ docker build -t shipping:1 .
    \[+\] Building 0.2s (1/3)
    =>
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 493B
    => \[internal\] load metadata for docker . io/library/openjak : 8-jdk
    =>
    \[internal\] load metadata for docker . io/library/debian : 10

[^103]: docker-compose.... M
    48
    image: mysql :1
    49
    container_name: mysql
    50
    51
    shipping:
    52
    image: shipping : 1
    53
    container_name: shipping
    54
    depends_on :
    55
    - mysql
    56

[^104]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https:/ /github. com/daws-76s/roboshop-
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and ex
    \[+\] Running 8/8
    Container mongodb
    Running
    Container redis
    Running
    Container mysql
    Running
    Container user
    Running
    Container shipping
    Started
    Container catalogue
    Running
    Container cart
    Running
    Container web
    Running

[^105]: C
    A Not secure 3.239.203.108/shipping
    Stan's Robot Shop
    Login / Register
    Shipping information
    Cart
    Select country Netherlands
    Enter location
    Empty
    Calculate
    Australia
    Categories
    Austria
    Brasil
    . Artificial
    Bulgaria
    Intelligence
    Canada
    Czech Republic
    . Robot
    Denmark
    Finland
    France
    Germany
    Great Britain
    Siva
    Hungary
    India
    Italy
    Japan
    Netherlands
    Norway
    Portugal
    Romania

[^106]: EXPLORER
    docker-compose.yaml M X Dockerfile .. \\shipping
    Dockerfil
    REPOS
    roboshop-docker > < docker-compose.yaml
    > dockerfiles
    48
    image: mysql :1
    > notes
    49
    container_name: mysql
    roboshop-docker
    50
    >
    cart
    51
    shipping:
    > catalogue
    52
    image: shipping:1
    > mongodb
    53
    container_name: shipping
    54
    depends_on :
    > mysql
    55
    - mysql
    > payment
    56
    shipping
    57
    rabbitmq:
    >
    user
    58
    container_name: rabbitmq
    > web
    59
    image: rabbitmq
    I
    docker-compose.... M
    60
    environment:
    61
    RABBITMQ_DEFAULT_USER=roboshop
    62
    RABBITMQ_DEFAULT_PASS=roboshop123
    63

[^107]: EXPLORER
    . . .
    iml M
    Dockerfile ..\\payment U X
    rabbitmq.py U
    Docker
    REPOS
    roboshop-docker > payment > > Dockerfile
    > dockerfiles
    H
    FROM python : 3.9
    > notes
    2
    3
    EXPOSE 8080
    roboshop-docker
    14
    ENV AMQP_USER=roboshop \\
    > cart
    15
    AMQP_PASS=roboshop123
    > catalogue
    6
    USER root
    > mongodb
    7
    WORKDIR /app
    > mysql
    8
    COPY requirements . txt /app/
    payment -
    9
    RUN pip install -r requirements. txt_
    10
    Dockerfile -
    U
    COPY \* . py /app/
    11
    COPY payment. ini /app/
    = payment.ini
    U
    12
    #CMD \["python", "payment. py" \]
    payment.py
    U
    13
    CMD \["uwsgi", "--ini", "payment. ini" \]
    2
    rabbitmq.py
    U
    14
    requirements.txt -U
    > shipping
    > user

[^108]: 3. 239. 203.108 \| 172. 31.0.103 \| t3. medium \| https : //github. com/daws-76s
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ git pull
    remote: Enumeratiog objects: 15, done.
    remote: Counting objects: 100% (15/15) , done.
    remote: Compressing objects: 100% (8/8) , done.
    remote: Total 11 (delta 3) , reused 11 (delta 3) , pack-reused 0
    Unpacking objects: 72% (8/11)

[^109]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-docke
    \[ centos@ip-172-31-0-103 \~/roboshop-docker \]$ cd payment/
    3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-docke
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/payment \]$ docker build -t payment:1 .
    \[+\] Building 0.3s (2/2)
    =>
    \[internal\] load build definition from Dockerfile
    =>
    => transferring dockerfile: 313B
    =>
    \[internal\] load metadata for docker. io/library/python : 3.9

[^110]: 3. 239. 203. 108 \| 172. 31.0.103 \| t3. medium \| https: //github. com/daws-76s/roboshop-d
    \[ centos@ip-172-31-0-103 \~/roboshop-docker/web \]$ docker build -t web:1 .
    \[+\] Building 0.0s (0/1)

[^111]: 11 /3118400/1 Pull complete
    Oeaee8120age Pull complete
    aaf353801647 Pull complete
    3af77ecf0aa6 Pull complete
    662b8be8eleb Pull complete
    e707813f956c Pull complete
    8ff5f83dc2d0 Pull complete
    31513c655622 Pull complete
    (+\] Running 10/10
    Container rabbitma
    Started
    Container mongodb
    Running
    Container redis
    Running
    Container catalogue
    Running
    Container user
    Running
    Container mysql
    Running
    Container cart
    Running
    Container shipping
    Running
    Container payment
    Started

[^112]: C
    A Not secure 3.239.203.108/shipping
    Stan's Robot Shop
    Login / Register
    Shipping information
    Cart
    Select country Netherlands
    Enter location
    Empty
    Calculate
    Australia
    Categories
    Austria
    Brasil
    . Artificial
    Bulgaria
    Intelligence
    Canada
    Czech Republic
    . Robot
    Denmark
    Finland
    France
    Germany
    Great Britain
    Siva
    Hungary
    India
    Italy
    Japan
    Netherlands
    Norway
    Portugal
    Romania

[^113]: E
    daws-76s / shell-script
    Q Type to search
    <> Code O Issues 10 Pull requests Actions Projects ) Wiki @ Security \~ Insights & Settings
    al Files
    shell-script / 19-docker-install.sh
    & main
    +
    Q
    joindevopscloud jenkins
    Q Go to file
    Code
    Blame 65 lines (42 loc) . 1.32 KB
    Raw D + 0 -
    0 01-hello-world.sh
    0 02-variables.sh
    #! /bin/bash
    WNA
    0 03-variables.sh
    ID-$(id -u)
    4
    R-"le\[31m"
    04-variables.sh
    5
    G-"le\[32m"
    05-variables.sh
    6
    Y-"le\[33m"
    7
    N-"le\[Om"
    06-data-types.sh
    0 07-arrays.sh
    10
    TIMESTAMP-$(date +%F-XH-XM-xS)
    08-conditions.sh
    11
    LOGFILE-"/tmp/$0-$TIMESTAMP . log"
    12
    09-install-mysql.sh
    13
    echo "script stareted executing at STIMESTAMP" &> > $LOGFILE
    10-functions.sh
    14
    15 V
    VALIDATE(){
    0 11-logs.sh
    16
    if \[ $1 -ne 0 \]
    12-loops.sh
    17
    then
    18
    echo -e "$2 ... SR FAILED SN"
    13-install-packages.sh
    19
    exit 1
    20
    else
    \[ 14-without-exit-status.sh
    21
    echo -e "$2 ... $G SUCCESS SN"
    \[ 15-delete-old-logs.sh
    22
    fi

[^114]: 3.215.153.36
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ curl https: //raw . githubusercontent. com/daws-76s/shell-script/main/19-docker-install. sh \| sudo bash
    8 Total
    8 Received % Xferd Average Speed
    Time
    Time
    Time
    Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 1352 100 1352
    0
    0
    13520
    0
    -:
    13520

[^115]: 3. 215 . 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos(ip-172-31-3-23 \~ \]$ git clone https: //github. com/daws-76s/roboshop-docker . git
    Cloning into 'roboshop-docker' . .
    remote: Enumeratiog objects: 151, done.
    remote: Counting objects: 100% (151/151), done.
    remote: Compressing objects: 91% (112/122)

[^116]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ cd roboshop-docker/
    3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ 1s
    cart catalogue docker-compose. yaml mongodb mysql payment shipping user web
    3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos(ip-172-31-3-23 \~/roboshop-docker \]$ for i in mongodb mysql catalogue cart user shipping payment web ; do cd $i ; docker build
    -t $i:v1 . ; cd .. ; done
    \[+\] Building 0.3s (2/2)
    docker : default
    =>
    \[internal) load build definition from Dockerfile
    0. 0s
    => > transferring dockerfile: 88B
    0 . 0s
    \[internal\] load metadata for docker. 10/library/mongo: 5
    0, 3s

[^117]: 3. 215. 153.36 \| 172. 31.3.23 \| t3.medium \| https: //github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    web
    v1
    a41cb736524d
    8 seconds ago
    188MB
    payment
    v1
    14547af635c5
    15 seconds ago
    1 . 03GB
    shipping
    v1
    c8247503b9a8
    About a minute ago
    568MB
    user
    v1
    3dae078bbaca
    About a minute ago
    1 . 17GB
    cart
    v1
    1bc532491c7e
    2 minutes ago
    1 . 18GB
    catalogue
    7f1567098822
    2 minutes ago
    1 . 17GB
    mysql
    b42c9cc0 370d
    3 minutes ago
    566MB
    mongodb
    321938f93156
    4 minutes ago
    697MB

[^118]: 3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker network create roboshop
    edf04cc688a5286abb0d92a852280e6febb299975abaf3fc6be08301f604cla

[^119]: 3. 215. 153.36 \| 172. 31.3.23 \| t3.medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and external: true
    \[+\] Running 0/10
    Container rabbitma
    Starting
    Container mysql
    Starting
    Container redis
    Starting
    Container mongodb
    Starting
    Container shipping
    Created
    Container catalogue
    Created
    Container user
    Created
    Container cart
    Created
    Container payment
    Created
    Container web
    Created

[^120]: C
    A Not secure 3.215.153.36/payment
    Stan's Robot Shop
    Login / Register
    Review your order
    Cart
    Order placed aff18fdd-1f48-45ce-85e1-6fb521125d7a
    Empty
    Thank you for your order Continue shopping
    Categories
    . Artificial
    Intelligence
    .
    Robot

[^121]: 3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker compose down
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and external: true
    \[+\] Running 3/4
    Container web
    Removed
    Container shipping
    Removed
    :. Container payment
    Stopping
    Container mysql
    Removed

[^122]: ChatGPT 3.5 v
    You
    what are the best practice while working with docker
    ChatGPT
    Working with Docker efficiently and securely requires following best practices to ensure that your
    containers and the applications they run are stable, maintainable, and performant. Here are some
    back practices for working with Docker:
    1.
    Use Official Images
    Whenever possible, use official Docker images from the Docker Hub or other trusted
    repositories. Official images are regularly updated and maintained by the respective software
    vendors, ensuring security and reliability.
    2. Create Custom Dockerfiles:
    Avoid modifying official images directly. Instead, create custom Dockerfiles that inherit from
    official images and customize them to suit your application's specific requirements. This makes
    your setup more reproducible and maintainable.
    3. Keep Containers Small:
    Strive for minimalism in your containers. Only include the necessary dependencies and
    components. Smaller images reduce deployment time and save disk space.
    4. Use .dockerignore:
    Create a " . dockerignore ' file to exclude unnecessary files and directories from the build
    context, reducing the image size and speeding up the build process.
    5. Use Multi-Stage Builds:
    If your application requires build tools or dependencies during development but not in
    production, use multi-stage builds to create a smaller final image that only includes the
    necessary components.
    6. Update Dependencies:
    Regularly update the software and packages within your containers to address security

[^123]: 3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker.
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    web
    v1
    a41cb736524d
    5 minutes ago
    188MB
    payment
    v1
    14547af635c5
    5 minutes ago
    1 . 03GB
    shipping
    v1
    c8247503b9a8
    6 minutes ago
    568MB
    iser
    v1
    3dae078bbaca
    7 minutes ago
    1 . 17GB
    cart
    1bc532491c7e
    7 minutes ago
    1 . 18GB
    catalogue
    7f1567098822
    8 minutes ago
    1 . 17GB
    mysql
    v1
    b42c9cc0370d
    9 minutes ago
    566MB
    mongodb
    v1
    321938f93156
    9 minutes ago
    697MB
    rabbitma
    latest
    e80099828f6f
    3 days ago
    217MB
    redis
    latest
    d1397258b209
    5 weeks ago
    138MB

[^124]: v
    () daws-76s/roboshop-docker
    \* \| Instances \| EC2 \| us-east-1
    x @
    Stan's Robot Shop
    x \|G docker best practices - Google X
    node - Official Image \| Docker + X
    Docker Best Practices
    x
    +
    - C hub.docker.com/_/node/tags?page=1&name=18
    dockerhub
    Explore
    Repositories
    Organizations
    node
    X
    ?
    Explore / Official Images / node
    node@
    node @ Docker Official Image . $ 18+ . > 10K+
    docker pull node
    Node.js is a JavaScript-based platform for server-side and networking applications.
    Overview
    Tags
    Sort by
    Newest
    18
    T
    X
    TAG
    hydrogen-slim
    docker pull node :hydrogen-slim
    Last pushed 4 days ago by doljanky.
    DIGEST
    OS/ARCH
    VULNERABILITIES
    COMPRESSED SIZE
    460f3d811ff3
    linux/amd64
    0
    1
    0
    18
    67.11 MB

[^125]: TAG
    18,19.1-alpine3.19
    docker pull node : 18. 19. 1-alpine3..
    Last pushed 4 days ago by dejanky.
    DIGEST
    OS/ARCH
    VULNERABILITIES
    COMPRESSED SIZE
    affdf979bdBe
    linux/amd64
    0
    0
    43.87 MB
    affofd4c20bb
    linux/arm/v6
    O
    0
    0
    O
    42.34 MB
    a23d29bab59f
    linux/arm/v7
    O
    O
    0
    41.62 MB
    +3 more...

[^126]: 3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/robos
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    user
    v1
    a9187cdd9078
    14 seconds ago
    160MB
    cart
    v1
    b328b3c963de
    27 seconds ago
    165MB
    catalogue
    v1
    d060107fba5b
    41 seconds ago
    160MB
    web
    v1
    a41cb736524d
    8 minutes ago
    188MB
    payment
    v1
    14547af635c5
    9 minutes ago
    1 . 03GB
    shipping
    v1
    c8247503b9a8
    9 minutes ago
    568MB
    <none>
    <none>
    3dae078bbaca
    10 minutes ago
    1 . 17GB
    <none>
    <none>
    1bc532491c7e
    11 minutes ago
    1 . 18GB
    <none>
    <none>
    7f1567098822
    11 minutes ago
    1 . 17GB
    mysql
    v1
    b42c9cc0370d
    12 minutes ago
    56 6MB
    mongodb
    v1
    321938193156
    12 minutes ago
    697MB
    rabbitma
    latest
    e80099828f6f
    3 days ago
    217MB
    node
    18
    39e94893115b
    4 days ago
    1 . 09GB
    redis
    latest
    d1397258b209
    5 weeks ago
    138MB

[^127]: best practices
    1. use official images
    2. reduce image size by using bare minimum OS like alpine, disto, core os, etc.
    3. use multi stage builds I
    4. use docker volumes to persist the data
    5. use custom network to isolate containers from other projects

[^128]: Source code --> compile --> byte code (jar) --> run byte code
    JDK --> Java development kit
    JRE --> Java runtime environment
    JDK > JRE and JRE is subset of JDK
    JDK memory > JRE memory
    I

[^129]: REPOS
    roboshop-docker > shipping > Dockerfile > FROM
    #
    > learn-jenkins
    2
    # Build
    > notes
    13
    #
    > roboshop-ansible
    4
    FROM maven AS build
    > roboshop-ansible-roles
    5
    > roboshop-ansible-roles-tf
    16
    WORKDIR /opt/shipping
    roboshop-docker
    7
    8
    COPY pom. xml /opt/shipping/
    > cart
    19
    RUN mvn dependency : resolve
    > catalogue
    10
    COPY sec /opt/shipping/src/
    > mongodb
    11
    RUN mvn package
    > mysql
    12
    > payment
    13
    #
    shipping
    14
    # Run
    15
    #
    >
    src
    16
    FROM openjak:8-jdk
    Dockerfile
    17
    pom.xml
    18
    EXPOSE 8080
    > user
    19
    > web
    20
    WORKDIR /opt/shipping
    docker-compose.yaml
    21
    > roboshop-documentation
    22
    ENV CART_ENDPOINT=cart : 8080
    23
    ENV DB_HOST=mysql
    rohnchon-infra-dow
    24

[^130]: when you remove docker container, what happens to data?
    containers ephemeral/temporary. data by default will be deleted. .
    T

[^131]: \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker run -d -p 80:80 nginx
    Unable to find image 'nginx: latest' locally
    latest: Pulling from library/nginx
    elcaac4eb9d2: Already exists
    88f6f236f401: Already exists
    c3ea3344e711: Already exists
    cclbb4345a3a: Already exists
    da8fa4352481: Already exists
    c7f80e9cdab2: Already exists
    18a869624cb6: Already exists
    Digest: sha256: c26ae7472d624balfafd296e73cecc4f93f853088e6a9c13c0d52f6ca5865107
    Status: Downloaded newer image for nginx: latest
    57dbodd91e2f321a6978260991862cb644f82d2f98bcbb22fbad3c0c52570543
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    57dbcdd91e2f
    nginx
    "/ docker-entrypoint...."
    4 seconds ago
    Up 4 seconds
    0. 0.0.0:80->80/top, : : :80->80/tcp
    sad sammet
    3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$

[^132]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker exec -it 57dbcdd91e2f bash
    root@57dbcdd91e2f: /# cd /usr/share/nginx/html/
    root@57dbcdd91e2f: /usr/share/nginx/html# echo "Hello from Docker Volumes" > volume.html
    root@57dbcdd91e2f: /usr/share/nginx/html# \|

[^133]: F
    C
    Not secure 3.215.153.36/volume.htm\]\[
    Hello from Docker Volumes

[^134]: "GraphDriver": {
    "Data" : {
    "LowerDir": "/var/lib/docker/overlay2/add863ed5ac43d62d7a1209accda26108dd9d4353872616373510faab78b5ce-init/diff: /var/1
    ib/docker/overlay2/1f0d8eb2985e8f18e973641cd388a5b381363cbfe885af9db2d97bb54393fd/diff : /var/lib/docker/overlay2/dead8dc88bb377c7dlael
    abc773dae361025f3fd73889bc9a8bc63bf3aa4ad9/diff : /var/lib/docker/overlay2/89cedb61ca76048fa584bed38ff305eca81244a403e2d63a78d047242e19d
    19d/diff: /var/lib/docker/overlay2/eb9036509e93ce4ce735b5d486c173181338d9f147bac97c53db2072fc55240/diff :/var/lib/docker/overlay2/11026d
    a98393852a607913380c0c147373d39c64dedd646d4593efa56f198ae/diff: /var/lib/docker/overlay2/d7323b889e3c98eb08fc8e0a1679f3ead5c93c18a4fda
    8716f8db7b54110832/diff : /var/lib/docker/overlay2/9890b17e14054ce705b17fbece02d0c385d5d98411f60a5a5c0bd1208a03ba49/diff",
    "MergedDir": "/var/lib/docker/overlay2/add863ed5ac43d62d7a1209accda26108dd9d4353872616373510faab78b5ce/merged",
    "UpperDir": "/var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d4353872616373510faab78b5ce/diff"
    "WorkDir" : "/var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d4353872616373510faab78b5ce/work"

[^135]: \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    57dbcdd91e2f
    nginx
    "/docker-entrypoint...."
    About a minute ago
    Up About a minute
    0. 0.0. 0:80->80/top, : : :80->80/tcp
    sad samm
    et
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ sudo su
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ root@ip-172-31-3-23 /home/centos/roboshop-docker \]# cd /var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d435387261637351
    Ofaab 78b
    bash: cd: /var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d4353872616373510faab78b: No such file or directory
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ root@ip-172-31-3-23 /home/centos/roboshop-docker \]# cd /var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d435387261637351
    Ofaab 78b5ce
    3. 215 . 153.36 \| 172 . 31.3.23 \| t3. medium \| null
    \[ root@ip-172-31-3-23 /var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d4353872616373510faab78b5ce \]# find . -iname "volum
    e. html"
    /diff/usr/share/nginx/html/volume . html
    ./merged/usr/share/nginx/html/volume. html
    . 215. 153. 36 \| 172.31.
    . 23
    t3.medium

[^136]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ root@ip-172-31-3-23 \~ \]# docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    57dbcdd91e2f
    nginx
    " /docker-entrypoint..."
    2 minutes ago
    Up 2 minutes
    0.0.0.0:80->80/top, : : :80->80/tcp
    sad sammet
    3. 215 . 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ root@ip-172-31-3-23 \~ \]# docker rm -f 57dbcdd91e2f
    57dbcdd91e2f
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ rootdip-172-31-3-23 \~ \]# cd /var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d4353872616373510faab78b5ce
    bash: cd: /var/lib/docker/overlay2/add863ed5ac43d662d7a1209accda26108dd9d4353872616373510faab78b5ce: No such file or directory

[^137]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ cd
    3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ mkdir nginx-data
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ 1s
    nginx-data roboshop-docker
    3. 215 . 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ pwd
    / home/ centos
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ 1s -1
    total 0
    drwxrwxr-x 2 centos centos
    6 Feb 20 02:30 nginx-data
    drwxrwxr-x 11 centos centos 156 Feb 20 01:59 roboshop-docker
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos(ip-172-31-3-23 \~ \]$

[^138]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ docker run -d -p 80:80 -v /home/centos/nginx-data: /usr/share/nginx/html nginx
    5e95d1a266b70d1c91e8bc71a2ddd3a8f9d3ddd82114cc6a0f6a19dd66744456
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos(ip-172-31-3-23 \~ \]$

[^139]: 3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    5e95dla266b7
    nginx
    " /docker-entrypoint...."
    10 seconds ago
    Up 10 seconds
    0. 0. 0. 0:80->80/top, : : :80->80/tcp
    busy pasca.

[^140]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ docker exec -it 5e95dla266b7 bash
    root@ 5e95d1a266b7: /# cd /usr/share/nginx/html/
    root@5e95d1a266b7: /usr/share/nginx/html# echo "Hello Volumes" > volume.html
    root@ 5e95dla2667: /usr/share/nginx/html#

[^141]: () daws-763/roboshop-docker
    x Instances \| EC2 \| us-east-1
    X
    S
    3.215.153.36/volume.h
    C
    Not secure 3.215.153.36/volume.html
    Hello Volumes

[^142]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ docker rm -f 5e95dla266b7
    5e95d1a266b7

[^143]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ cd nginx-data/
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~/nginx-data \]$ 1s
    volume . html
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~/nginx-data \]$

[^144]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~ \]$ docker run -d -p 80:80 -v /home/centos/nginx-data: /usr/share/nginx/html nginx
    5e95d1a266b70d1c91e8bc71a2ddd3a8f9d3ddd82114cc6a0f6a19dd66744456
    3. 215 . 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos(ip-172-31-3-23 \~ \]$

[^145]: () daws-763/roboshop-docker
    x Instances \| EC2 \| us-east-1
    X
    S
    3.215.153.36/volume.h
    C
    Not secure 3.215.153.36/volume.html
    Hello Volumes

[^146]: 3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~/nginx-data \]$ docker volume
    Usage: docker volume COMMAND
    Manage volumes
    Commands :
    create
    Create a volume
    inspect
    Display detailed information on one or more volumes
    List volumes
    prune
    Remove unused local volumes
    rm
    Remove one or more volumes
    Run 'docker volume COMMAND --help' for more information on a command.
    3
    215 153
    36
    172

[^147]: 3. 215. 153.36 \| 172. 31.3.23 \| t3.medium \| null
    \[ centosdip-172-31-3-23 \~/nginx-data \]$ docker volume create nginx
    nginx
    3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos(ip-172-31-3-23 \~/nginx-data \]$

[^148]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~/nginx-data \]$ docker volume inspect nginx
    "CreatedAt": "2024-02-20T02 : 33: 22Z",
    "Driver": "local",
    "Labels": null,
    "Mountpoint": "/var/lib/docker/volumes/nginx/ data",
    "Name": "nginx"
    "Options": null,
    " Scope": "local"

[^149]: 3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~/nginx-data \]$ docker run -d -p 80:80 -v nginx: /usr/share/nginx/html nginx
    f62c0e8492464ee36fc98d435ce78c9ab7125d7eca2cf027f51747660c7f2f7e
    3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| null
    \[ centos@ip-172-31-3-23 \~/nginx-data \] $

[^150]: V REPOS
    roboshop-docker > < docker-compose.yaml > {} services > {} mongodb > \[ \] volumes > {} 0 > . typ
    > learn-jenkins
    8
    mysql :
    9
    rabbitmq:
    > notes
    10
    services :
    > roboshop-ansible
    11
    # docker run -d - -name mongodb - -network=roboshop mongodb : 1
    > roboshop-ansible-roles
    12
    mongodb :
    > roboshop-ansible-roles-tf
    13
    image: mongodb : v1
    roboshop-docker
    14
    container_name: mongodb
    > cart
    15
    volumes :
    16
    source: mongodb I
    > catalogue
    17
    target: /data/db
    > mongodb
    18
    type: volume
    > mysql
    19
    # networks:
    > payment
    20
    # - roboshop
    > shipping
    21
    > user
    22
    catalogue:
    23
    > web
    image: catalogue: v1
    24
    container_name: catalogue
    docker-compose.yaml
    M
    25
    # networks:
    > roboshop-documentation
    26
    # - roboshop
    > roboshop-infra-dev
    27
    depends_on:
    > roboshop-infra-prod
    28
    - mongodb
    roboshop-shared-library
    29

[^151]: How to use this image
    start a redis instance
    $ docker run --name some-redis -d redis
    start with persistent storage
    $ docker run --name some-redis -d redis redis-server --save 68 1 --loglevel warning
    There are several different persistence strategies to choose from. This one will save a snapshot of the DB every 60
    seconds if at least 1 write operation was performed (it will also lead to more logs, so the loglevel option may be
    desirable). If persistence is enabled, data is stored in the VOLUME /data , which can be used with --volumes-from
    some-volume-container or -v /docker/host/dir : /data (see docs.docker volumes).
    For more about Redis Persistence, see http://redis.io/topics/persistence.

[^152]: 3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and external: true
    \[+\] Running 10/10
    Container redis
    Running
    Container mongodb
    Running
    Container catalogue
    Running
    Container cart
    Running
    Container mysql
    Running
    Container shipping
    Running
    Container rabbitma
    Running
    Container user
    Running
    Container payment
    Running
    Container web
    Started

[^153]: C
    Not secure
    3.215.153.36/login
    Stan's Robot Shop
    Login / Register
    Cart
    Greetings siva
    Empty
    Email - siva@joindevops.com
    Categories
    . Artificial
    Order History
    Intelligence
    Order ID Items Total
    .
    Robot

[^154]: 7. Limit Privileges:
    Run containers with the principle of least privilege. Avoid running containers as the root user
    whenever possiblerand use user namespaces or non-root users for your applications.

[^155]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker run -d -p 8080:80 -v /: /test nginx
    d19065957f7d0e5ele010b58b4e52c967782a0ed874abe7d407d833067db50d1
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker exec -it d19065957 bash
    root@d19065957f7d: /# cd /test/
    root@d19065957f7d: /test# 1s -1
    total 20
    lrwxrwxrwx.
    1 root root
    7 Jun 22 2021 bin -> usr/bin
    dr-xr-xr-x.
    6 root root 4096 Feb 20 01:47 boot
    drwxr-xr-x
    16 root root 2620 Feb 20 01:46 dev
    drwxr-xr-x.
    93 root root 8192 Feb 20 01:51 etc
    drwxr-xr-x.
    3 root root
    20 Jan 16 13:13 home
    lrwxrwxrwx.
    1 root root
    7 Jun 22 2021 lib -> usr/lib
    lrwxrwxrwx.
    1 root root
    9 Jun 22
    2021 lib64 -> usr/lib64
    drwxr-xr-x.
    2 root root
    6 Jun 22 2021 media
    drwxr-xr-x.
    2 root root
    6 Jun 22 2021 mnt
    drwxr-xr-x.
    3 root root
    24 Feb 20 01:51 opt
    dr-xr-xr-x 153 root root
    0 Feb 20 01:46 proc
    dr-xr-x---.
    3 root root 181 Feb 20 02:29 root
    I
    drwxr-xr-x
    29 root root 940 Feb 20 01:56 run
    lrwxrwxrwx.
    1 root root
    8 Jun 22 2021 sbin -> usr/sbin
    drwxr-xr-x.
    2 root root
    6 Jun 22 2021 srv
    dr-xr-xr-x
    13 root root
    0 Feb 20 01:46 sys
    drwxrwxrwt.
    3 root root 137 Feb 20 02:42 tmp
    drwxr-xr-x.
    12 root root 144 Dec 11 04:51 usr
    drwxr-xr-x.
    20 root root 4096 Jan 16 13:12 var
    root@d19065957f7d: /test# cd

[^156]: XJ
    File Edit Selection View Go
    repos
    EXPLORER
    Dockerfile .. \\cart M X
    DocnormIC m catalogue
    Dockerfile .. \\user
    Dockerfile .. \\shipping
    V REPOS
    roboshop-docker > cart > Dockerfile > FROM
    FROM node : 18. 19. 1-alpine3. 19
    > learn-jenkins
    2
    EXPOSE 8080
    > notes
    3
    RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    8 11
    > roboshop-ansible
    4
    WORKDIR /opt/server
    > roboshop-ansible-roles
    5
    ENV MONGO=true
    > roboshop-ansible-roles-tf
    6
    RUN chown roboshop : roboshop /opt/server
    7
    roboshop-docker
    USER roboshop
    8
    COPY package. json /opt/server/
    cart
    19
    COPY server . js /opt/server/
    Dockerfile
    M
    10
    RUN npm install
    A
    {} package.json
    11
    CMD \["node", "server. js"\]
    JS server.js
    > catalogue

[^157]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ for i in mongodb mysql catalogue cart user shipping payment web ; do cd $i ; docke
    -t $i:vi . ; cd . . ; done
    \[+\] Building 0.2s (7/7) FINISHED
    docker :
    > \[internal\] load build definition from Dockerfile
    => transferring dockerfile: 88B
    (internal\] load metadata for docker. 10/library/mongo: 5
    (internal) load . dockerignore
    -> > transferring context: 28
    \[internal\] load build context
    > > transferring context: 618
    (1/2\] FROM docker . 10/library/mongo : 58sha256: 2c310a955{d670e3285901252a682ae6{be3937edbob20e7721b3370bb9334{
    CACHED (2/2\] COPY . . js /docker-entrypoint-initdb. d/
    exporting to image
    > exporting layers
    "> > writing image sha256: 3219381931560170910027ab8370094a58cBe2e5485be85602600c432584baa7
    => naming to docker . 10/library/mongodb : v1

[^158]: 3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker compose up -d
    WARN \[0000\] networks . default: external . name is deprecated. Please set name and external: true
    \[+\] Running 5/7
    Container mongodb
    Running
    Container rabbitma
    Running
    Container mysql
    Running
    Container catalogue
    Recreate
    Container shipping
    Running
    Container redis
    Running
    Container user
    Recreate

[^159]: 3. 215 . 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker exec -it cart bash
    OCI runtime exec failed: exec failed: unable to start container process: exec: "bash": executable file not found in $PATH: unknown
    3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker exec -it cart sh
    /opt/server $

[^160]: hub.docker.com/_fredis/tags
    reais
    docker pull redis
    Redis is an open source key-value store that functions as a data structure server.
    pers
    Overview
    Tags
    Sort by
    Newest
    Filter Tags
    Q
    TAG
    latest
    docker pull redis: latest
    Last pushed 4 days ago by dollanky
    High severity
    DIGEST
    OS/ARCH
    VULNERABILITIES
    COMPRESSED SIZE
    3ed176138cd
    linux/386
    2
    28
    11
    22
    C
    49.08 MB
    fe98b2d39d46
    linux/amd64
    2
    11
    22
    O
    49.01 MB
    002eaf750838
    linux/arm/v5
    2
    28
    11
    22
    0
    45.27 MB
    +5 more...

[^161]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker system prune
    WARNING! This will remove:
    all stopped containers
    all networks not used by at least one container
    all dangling images
    unused build cache
    Are you sure you want to continue? \[y/N\] y
    Deleted Images :
    deleted: sha256: 3dae078bbaca10c21f699c5097982069cc3b804b25687cfc9c9f03925542edf0
    deleted: sha256: c8247503b9a84ca6dec24f2e364366c62f73df915d41326abf2e50b8fec21128
    deleted: sha256: 14547af635c53280fa71b4a8a444ac604cd5526ec9d368b305cf61755141cb83
    deleted: sha256: 7f156709882244e25d06d7076f7d7cb538dbb75a0905ccb5638ccec18d642825
    deleted: sha256: a9187cdd9078235ae0df0aa0b378328c185b610ec9ec33ef8e137fb283146385
    deleted: sha256: d060107fba569279397c3e4b498c5af387c86a43afef43133462f70b0e99b6d4
    deleted: sha256: 1bc532491c7ela657e683cad7f22ee1459b42132d0941cc422885e43685163fa
    deleted: sha256: fce725da2aad412c891ae3293e636f34fd1c6a159530d19466c44ad24348fb87
    deleted: sha256: b328b3c963dec7fa380c4cbf6ef98c7c751f034ca3f9910ac9e8f346c14b17e2

[^162]: 0bo94p16azk8h9stkzb4zfza9
    i6ps04hbtbkre7b5gvd5kjprm
    Total reclaimed space: 637. 2MB

[^163]: docker architecture
    docker run nginx
    1. docker shell/ docker command send a request to docker deamon
    2. docker engine receives the request
    3. it will check whether image is available in local or not
    4. if available it will create container and show the response in client
    5. if not available, it will pul from docker central hub, keep it in local.
    6. create container and response to client

[^164]: Docker architecture
    Docker follows Client-Server architecture, which includes the three main components that are Docker Client, Docker Host, and Docker Registry.
    Client
    DOCKER HOST
    Registry
    docker build
    Docker daemon
    docker pull
    Containers
    Images
    docker run
    NGINX

[^165]: 1. Docker Client
    Docker client uses commands and REST APIs to communicate with the Docker Daemon (Server). When a client runs any docker command on the
    docker client terminal, the client terminal sends these docker commands to the Docker daemon. Docker daemon receives these commands from the
    docker client in the form of command and REST API's request.

[^166]: Note: Docker Client has an ability to communicate with more than one docker daemon.
    Docker Client uses Command Line Interface (CLI) to run the following commands -
    docker build
    docker pull
    docker run
    2. Docker Host
    Docker Host is used to provide an environment to execute and run applications. It contains the docker daemon, images, containers, networks, and
    storage.
    3. Docker Registry
    Docker Registry manages and stores the Docker images.

[^167]: roboshop-docker > user > Dockerfile > RUN
    1
    FROM node : 18. 19. 1-alpine3. 19
    2
    EXPOSE 8080
    I
    3
    RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    4
    WORKDIR /opt/server
    5
    ENV MONGO=true
    16
    RUN chown roboshop : roboshop /opt/server
    7
    USER roboshop
    8
    COPY package . json /opt/server/
    19
    COPY server . js /opt/server/
    10
    RUN npm install
    11
    CMD \["node", "server. js"\]

[^168]: 1. base image
    creates container out of first instruction, intermediate container
    2. runs second instruction in the container, creates image out of this
    3. creates container out of 2 instructions.
    4. runs the command in the intermediate container. creates image out of these 3
    FROM node : 18. 19. 1-alpine3.19 --> creates container-1 here
    runs EXPOSE 8080 in container-1 --> creates image-1 out of this container-1
    create container-2 out of image-1
    runs this command addgroup -S roboshop & & adduser -S roboshop -G roboshop in container-2 -->
    creates image-2 out of this conatiner-2
    creates container-3 out of this image-2
    RUNS

[^169]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker rmi -f docker images -a -q
    Untagged: user:v1
    Deleted: sha256:b035a6868f6094a8e6b48333d3c311464dc83908a74d79097873e3f97b2c147e
    Untagged: cart:v1
    Deleted: sha256: a1647452b5b2c60ea505bc67a839ba33dae3dd70a05bceed90e1530aad539518
    Untagged: catalogue:v1
    Deleted: sha256: dd7eef8dbca41b6ac0527f6be1b81ad7d999de837975e16369dc32dee916a020
    Untagged: payment: v1
    Deleted: sha256: Ofec7970178dobb36307c5fc43ddf68945aeb74cf33b1548eb5f18d4b731473d
    Untagged: shipping:v1
    Deleted: sha256: 40e758109ecab5963a5332199alfbdef9bbf37995585e94ad5f9f4706cf371c6
    Untagged: web:v1
    Deleted: sha256: a41cb736524ddcad41628e559coff9fd1le43292cc61de042ac5b8d751d88ea5
    Untagged: mysql :v1
    Deleted: sha256: b42c9cc0370d16432918a37067b9d61b32dbe947133864701d935b69d78b1328
    Untagged: mongodb : v1
    Deleted: sha256: 321938f93f560f7c9d0027ab8370c94a58c8e2e5485be856026c0c432584baa7
    Untagged: rabbitmq: latest
    Untagged: rabbitmq@sha256: 556d69518f4fb4d457645f1ba7b6bf74e0661c26cf9a6f538da6cca1572f1c28
    Deleted: sha256: e80099828f6f4ea9fa40bc7ef9370c7df3608fab>4aac6d05fde874e4abe4c654
    Deleted: sha256: 779de421c39f0338a07aaa370ad2ec5e80b77c2675a85609168b466f5025991
    Deleted: sha256: 97ade2ca56b39dd3b9078252cde1c4f2d09001c763f2a72594566d77b7d068bb
    Deleted: sha256: ceOf5d1c0ed80fabc7c6d0bf0db27cc97fb49005410795b41c7a7e831ec6a 702

[^170]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    nginx
    latest
    e4720093a3c1
    5 days ago
    187MB
    3. 215. 153. 36 \| 172. 31.3.23 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker \]$ cd cart/

[^171]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker build -t cart:v1
    \[+\] Building 0.3s (12/12) FINISHED
    \[internal\] load build definition from Dockerfile
    => transferring dockerfile: 3298
    \[internal\] load metadata for docker. 10/library/node: 18 . 19.1-alpine3. 19
    \[internal\] load . dockerignore
    > 'transferring context: 28
    \[1/7\] FROM docker . 10/library/node : 18. 19. 1-alpine3. 190sha256: ca9160b0466196380590c249d335a07
    \[internal\] load build context
    > transferring context: 11 . 94kB
    CACHED \[2/7\] RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    CACHED \[3/7\] WORKDIR /opt/server
    CACHED \[4/7\] RUN chown roboshop: roboshop /opt/server
    (5/71
    COPY

[^172]: 3. 215 . 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    cart
    v1
    7afd7cf90811
    11 seconds ago
    165MB
    3. 215 . 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    cart
    v1
    7afd7cf90811
    About a minute ago
    165MB
    3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker tag joindevops/cart:v1 .
    Error parsing reference: "." is not a valid repository/tag: invalid reference format
    3. 215. 153.36 \| 172. 31.3.23 \| t3.medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker tag cart:v1 joindevops/cart:v1
    3. 215 . 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$

[^173]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: //github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker login
    Log in with your Docker ID or email address to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https
    / /hub . docker . com/ to create one.
    You can log in with your password or a Personal Access Token (PAT) . Using a limited-scope PAT grants better security and is required fo
    r organizations using SSO. Learn more at https: / /docs . docker . com/go/access-tokens/
    Username: joindevops
    Password:
    WARNING! Your password will be stored unencrypted in /home/centos/ . docker/config . json.
    Configure a credential helper to remove this warning. See
    https: / /docs . docker . com/engine/reference/commandline/login/#credentials-store
    Login Succeeded

[^174]: 3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker push joindevops/cart:v1
    The push refers to repository \[docker . io/joindevops/cart\]
    e9c885a041fa: Pushing \[=
    \] 22. 53MB/33. 78MB
    6187f2762e68: Pushed
    991cc18f4d40: Pushed
    a7d7c901c9c5: Pushed
    acd174b252b6: Pushed
    62e7144f99dd: Pushing \[=
    >\] 12.29kB
    efdc30a9b9c0: Mounted from library/node
    a7ede14bfe13: Waiting
    d49996f6d982: Waiting

[^175]: roboshop-docker > user > Dockerfile > FROM
    1
    FROM node : 18. 19. 1-alpine3. 19
    2
    EXPOSE 8080
    13
    RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    4
    WORKDIR /opt/server
    5
    ENV MONGO=true
    16
    RUN chown roboshop : roboshop /opt/server
    7
    USER roboshop
    8
    COPY package . json /opt/server/
    9
    COPY server . js /opt/server/
    10
    RUN npm install
    11
    RUN echo Hello World
    12
    CMD \["node", "server. js"\]

[^176]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker build -t joindevops/cart:v1 .
    \[+\] Building 0.3s (13/13) FINISHED
    \[internal\] load build definition from Dockerfile
    transferring dockertile: 329B
    (internal\] load metadata for docker . 10/library/node: 18 . 19. 1-alpine3 . 19
    ( auth\] library/node: pull token for registry-1. docker. 10
    (internal\] load . dockerignore
    > transferring context: 2B
    \[1/7\] FROM docker. 10/ library/node: 18. 19. 1-alpine3. 190sha256: ca916cb045619638e5960c249d335207867ed50c429b507830ddalb
    (internal\] load build context
    > transferring context: 63B
    CACHED \[2/7\] RUN addgroup -S roboshop & adduser -S roboshop -G roboshop
    CACHED \[3/7\] WORKDIR /opt/server
    CACHED \[4/7\] RUN chown roboshop: roboshop /opt/server
    CACHED (5/7\] COPY package. json /opt/server/
    CACHED
    \[6/7\] COPY server. js /opt/server/
    CACHED \[7/7\] RUN nom install
    exporting to image
    => exporting layers
    ->
    -> writing image sha256: 7afd7of908114ca66b817546072085ed59098ba24fd6b20fe9868c5ec0a03177
    -> naming to docker . 10/joindevops/cart:v1
    3. 215. 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    centos@ip-172-31-3-23 \~/roboshop
    -docker /cart 1s

[^177]: 3. 215. 153.36 \| 172. 31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$ docker push joindevops/cart:v1
    The push refers to repository \[docker . io/joindevops/cart\]
    e9c885a041fa: Layer already exists
    6f87f2762e68: Layer already exists
    991cc18f4d40: Layer already exists
    a7d7c901c9c5: Layer already exists
    acd1 74b252b6: Layer already exists
    62e7144f99dd: Layer already exists
    efdc30a9b9c0: Layer already exists
    a7ede14bfe13: Layer already exists
    d49996f6d982: Layer already exists
    d4fc045c9e3a: Layer already exists
    v1: digest: sha256: cce00c0ce921d9a5ea82a3a18c5537cad11bc88e3f2af9007347a07160dbf917 size: 2407
    3. 215 . 153.36 \| 172.31.3.23 \| t3. medium \| https: / /github. com/daws-76s/roboshop-docker . git
    \[ centos@ip-172-31-3-23 \~/roboshop-docker/cart \]$

