---
title: 9&10Day_Full_Manual_Installation_project
uuid: 98b39b84-0e94-11ef-841c-a6f126245c9e
version: 808
created: '2024-05-10T11:44:44+05:30'
tags:
  - roboshop-project-manual
  - roboshop-project
---

***Topics:***

1. *<mark style="background-color:#f8d616;">**Complete manual installation**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**MongoDB**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**MySQL**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Shipping**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Web server**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Catalogue**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Redis**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**User**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Cart**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**RabbitMQ**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Payment**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Dispatch**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Creating DNS A records for required instances**<!-- {"backgroundCycleColor":"25"} --></mark>*

 

\

# Few Details<!-- {"collapsed":true} -->

![96a3305e-2b9b-416e-a523-3a22eb18ab4f.png|411](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/96a3305e-2b9b-416e-a523-3a22eb18ab4f.png) [^1]

 

 

![1de5ffc7-a234-4dad-af1f-1d944d3a006a.png|523](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1de5ffc7-a234-4dad-af1f-1d944d3a006a.png) [^2]

 

***Npm, maven, pip, nuget are build tools.***

![a8bb2d83-aecc-4ec4-8994-c1c6ed803419.png|718.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a8bb2d83-aecc-4ec4-8994-c1c6ed803419.png) [^3]

 

 

 

# *<mark style="background-color:#f8914d;">**Complete Manual project installation:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

***Possibility of errors:***

 

![99d9f305-78a5-4419-8b50-86565130935b.png|758.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/99d9f305-78a5-4419-8b50-86565130935b.png) [^4]

 

 

*<mark style="background-color:#bbe077;">**MongoDB - t3.medium instance or t3.small instance**<!-- {"backgroundCycleColor":"15"} --></mark>*

*<mark style="background-color:#bbe077;">**MySQL - t3.medium instance**<!-- {"backgroundCycleColor":"15"} --></mark>*

*<mark style="background-color:#bbe077;">**Shipping - t3.medium instance**<!-- {"backgroundCycleColor":"15"} --></mark>*

 

*<mark style="background-color:#f3de6c;">**Web server - t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**Catalogue -t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**Redis - t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**User - t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**Cart - t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**RabbitMQ -t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**Payment - t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">**Dispatch - t2.micro instance**<!-- {"backgroundCycleColor":"14"} --></mark>*

 

\

# *<mark style="background-color:#f8914d;">**Launching 5 Instances**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

![e3bd73df-e60f-48e0-871b-d79490ef711a.png|821.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e3bd73df-e60f-48e0-871b-d79490ef711a.png) [^5]

 

 

![065dc107-4efa-4649-9c30-19a2260661d3.png|823.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/065dc107-4efa-4649-9c30-19a2260661d3.png) [^6]

 

 

 

***Rename the instances as below***

![d575e081-90dd-4f5a-a146-5c033e05ff6d.png|757.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d575e081-90dd-4f5a-a146-5c033e05ff6d.png) [^7]

 

***Now launching MongoDB server with t3.medium***

![df47ff9e-6759-4f9e-8c5c-fdbd0b99ae42.png|741.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/df47ff9e-6759-4f9e-8c5c-fdbd0b99ae42.png) [^8]

 

![d3249fe6-b691-4476-828a-b32ce0f0ab66.png|707.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d3249fe6-b691-4476-828a-b32ce0f0ab66.png) [^9]

 

 

![8a01af54-410d-45b8-80d1-754bdb8de885.png|691.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8a01af54-410d-45b8-80d1-754bdb8de885.png) [^10]

 

 

*<mark style="background-color:#bbe077;">**As a best practice configure in such a way MongoDB ->Catalogue -> WEB -> REDIS -> USER**<!-- {"backgroundCycleColor":"15"} --></mark>*

 

 

# *<mark style="background-color:#f8914d;">**Now configuring MongoDB Module**:<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

***MongoDB configure***

![4a2f9b13-4bda-4715-9898-d7bbc724c7b6.png|739.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4a2f9b13-4bda-4715-9898-d7bbc724c7b6.png) [^11]

```
sudo su -
```

 

*Setup the MongoDB repo file*

 

```
vim /etc/yum.repos.d/mongo.repo
```

 

*--------*

*<mark>\[mongodb-org-4.2\]</mark>*

*<mark>name=MongoDB Repository</mark>*

*<mark>baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/</mark>*

*<mark>gpgcheck=0</mark>*

*<mark>enabled=1</mark>*

*------------*

```
cat /etc/yum.repos.d/mongo.repo
```

 

![ab8bcdaf-ee5d-4087-81b4-377e523b2b0e.png|805.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ab8bcdaf-ee5d-4087-81b4-377e523b2b0e.png) [^12]

 

*Install MongoDB*

```
dnf install mongodb-org -y
```

![ff78b49f-a985-40cc-922a-deec0d4d64fb.png|765.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ff78b49f-a985-40cc-922a-deec0d4d64fb.png) [^13]

 

 

*Start & Enable MongoDB Service*

```
systemctl enable mongod
```

```
systemctl start mongod
```

```
systemctl status mongod
```

 

![5770e499-edbe-4af5-9fd8-3e362ca02968.png|833.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5770e499-edbe-4af5-9fd8-3e362ca02968.png) [^14]

 

```
netstat -lntp
```

![09760227-76f8-41c0-90ad-a3217cea135e.png|735.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/09760227-76f8-41c0-90ad-a3217cea135e.png) [^15]

 

*127.0.0.1 --> localhost (nothing but mongodb within the server only it will accept connections & it won't accept outside connections) - but here we need connection from App tier, so now we are giving remote access*

![607b84a5-7520-4361-924a-f749be1c7d69.png|696.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/607b84a5-7520-4361-924a-f749be1c7d69.png) [^16]

 

```
vim /etc/mongod.conf
```

 

![8b361618-7531-4ff1-87ed-16b886ebbb66.png|806.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8b361618-7531-4ff1-87ed-16b886ebbb66.png) [^17]

 

```
systemctl restart mongod
```

```
netstat -lntp                            --> now App tier servers can communicate with mongo DB(remote connection).
```

 

![e0b58098-8010-490f-94a2-87e63c8b2e70.png|772.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e0b58098-8010-490f-94a2-87e63c8b2e70.png) [^18]

 

***Till now MongoDB is good***

 

 

# *<mark style="background-color:#f8914d;">**Creating A record for MongoDB, catalogue, web, cart, mysql, redis, shipping, user in AWS Route53  -- copy private IP & goto route 53**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

***Creating Catalogue record***

![82b548da-af41-4893-89af-ec9cad303ca0.png|845.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/82b548da-af41-4893-89af-ec9cad303ca0.png) [^19]

 

![e52fd955-f8ba-42d0-a478-3be17a4b8815.png|852.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e52fd955-f8ba-42d0-a478-3be17a4b8815.png) [^20]

 

![52add193-ab23-472f-881e-a761ced43103.png|862.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/52add193-ab23-472f-881e-a761ced43103.png) [^21]

 

 

![aabd47b8-1f0a-4430-bd09-f4587583b9bd.png|667.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/aabd47b8-1f0a-4430-bd09-f4587583b9bd.png) [^22]

 

 

***Creating Catalogue A record***

 

![3f3e1f52-ff03-4201-8f09-82901a5eaf8a.png|840.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/3f3e1f52-ff03-4201-8f09-82901a5eaf8a.png) [^23]

 

 

 

***Creating Web A record  - with public IP & record name should be empty***

![f68eb661-378c-4a35-b0a1-002e7b1d51ab.png|797.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/f68eb661-378c-4a35-b0a1-002e7b1d51ab.png) [^24]

 

***Creating REDIS A record***

![a25dd10a-2d89-447c-87c2-6c2b2cd8f932.png|797.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a25dd10a-2d89-447c-87c2-6c2b2cd8f932.png) [^25]

 

***Creating REDIS A record***

![3bb6bdfb-bc05-42ea-b686-82cf1b985f17.png|729.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/3bb6bdfb-bc05-42ea-b686-82cf1b985f17.png) [^26]

 

***Creating CART A record***

![cb50ce86-028f-40bd-b480-776529cccb45.png|789.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/cb50ce86-028f-40bd-b480-776529cccb45.png) [^27]

 

***Creating MYSQL   A record***

![7d5ae288-8f8f-484f-803c-a09d7c9a33fc.png|725.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7d5ae288-8f8f-484f-803c-a09d7c9a33fc.png) [^28]

 

***Creating SHIPPING A record***

![7e62d3bb-e533-445e-88a8-c121c08c36b6.png|803.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7e62d3bb-e533-445e-88a8-c121c08c36b6.png) [^29]

 

***Creating RABBITMQ A record***

 

![4fc8f025-b000-42ec-b6f9-baf339767a47.png|825.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4fc8f025-b000-42ec-b6f9-baf339767a47.png) [^30]

 

 

***Creating PAYMENT A record***

![30ffb329-64cc-4c04-b4bc-d7a7153c0e11.png|794.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/30ffb329-64cc-4c04-b4bc-d7a7153c0e11.png) [^31]

 

![b58f0c35-cb17-4e69-9bcf-d4f7aa8200cf.png|817.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/b58f0c35-cb17-4e69-9bcf-d4f7aa8200cf.png) [^32]

 

 

 

# *<mark style="background-color:#f8914d;">**Now configuring CATALOGUE Module:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![19803a1f-039d-4cbd-92e1-9e2da5ee8e0f.png|779.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/19803a1f-039d-4cbd-92e1-9e2da5ee8e0f.png) [^33]

 

```
sudo su -
```

```
dnf module disable nodejs -y
```

```
dnf module enable nodejs:18 -y
```

 

![057e39b3-4902-475b-a69a-2907a14e4abd.png|819.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/057e39b3-4902-475b-a69a-2907a14e4abd.png) [^34]

 

![9d9c3b06-dc3b-445c-8770-7a1088cad0ca.png|797.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/9d9c3b06-dc3b-445c-8770-7a1088cad0ca.png) [^35]

*Install NodeJS*

```
dnf install nodejs -y
```

 

![51438925-bc8c-42e3-82b1-239d58504d69.png|753.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/51438925-bc8c-42e3-82b1-239d58504d69.png) [^36]

 

![282a2461-db1d-4d7d-a54c-8b272fbd92fc.png|830.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/282a2461-db1d-4d7d-a54c-8b272fbd92fc.png) [^37]

![ab1fdfbd-4256-4696-b4ab-0ed926219417.png|849.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ab1fdfbd-4256-4696-b4ab-0ed926219417.png) [^38]

 

*Add application User --it’s a system user created for roboshop application, we can use this user to run roboshop application without using root user*

```
useradd roboshop      
```

 

![44a73777-de34-4948-a86c-6934631cfc85.png|723](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/44a73777-de34-4948-a86c-6934631cfc85.png) [^39]

 

*Lets setup an app directory.*

```
mkdir /app
```

```
cd /
```

```
ls -l
```

![0efa89ba-f5c0-4a28-870c-60ecc6e4c76c.png|700](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0efa89ba-f5c0-4a28-870c-60ecc6e4c76c.png) [^40]

 

![4335ca02-30ae-4ac2-bd8c-fee251c7eded.png|826.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4335ca02-30ae-4ac2-bd8c-fee251c7eded.png) [^41]

 

 

*Download the application code to created app directory.*

 

*#curl -o /tmp/catalogue.zip* [*https://roboshop-builds.s3.amazonaws.com/catalogue.zip*](https://roboshop-builds.s3.amazonaws.com/catalogue.zip) 

*#cd /tmp            --> catalogue files downloaded under /tmp*

*#ls -l*

 

![72540554-648a-461d-8f49-660790c9d834.png|883.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/72540554-648a-461d-8f49-660790c9d834.png) [^42]

 

*Unzip now*

```
cd /app
```

```
ls -l
```

```
unzip /tmp/catalogue.zip
```

```
ls -l
```

![bbbcdd35-8c00-4ae6-a35c-af33015f8eb4.png|677](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/bbbcdd35-8c00-4ae6-a35c-af33015f8eb4.png) [^43]

 

```
cat package.json
```

![d380fae5-727c-4972-b6ad-02f3a31433e3.png|787](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d380fae5-727c-4972-b6ad-02f3a31433e3.png) [^44]

 

![7344dc90-421e-45d6-913e-52a8d09de355.png|727.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7344dc90-421e-45d6-913e-52a8d09de355.png) [^45]

```
npm install
```

```
ls -l
```

![fe8cea1e-2660-4fd6-9915-ba19280e520a.png|907.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/fe8cea1e-2660-4fd6-9915-ba19280e520a.png) [^46]

 

![557e0d0f-3a67-476a-b136-659365d1dadd.png|905](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/557e0d0f-3a67-476a-b136-659365d1dadd.png) [^47]

 

![f559a114-3f38-40c9-86fc-1cf9a2389b65.png|612](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/f559a114-3f38-40c9-86fc-1cf9a2389b65.png) [^48]

 

*we are creating service called catalogue.service*

```
vim /etc/systemd/system/catalogue.service 
```

*------------*

*<mark>\[Unit\]</mark>*

*<mark>Description = Catalogue Service</mark>*

 

*<mark>\[Service\]</mark>*

*<mark>User=roboshop</mark>*

*<mark>Environment=MONGO=true</mark>*

*<mark>Environment=MONGO_URL="mongodb://<MONGODB-SERVER-IPADDRESS>:27017/catalogue"</mark>*             

*<mark>ExecStart=/bin/node /app/server.js</mark>*

*<mark>SyslogIdentifier=catalogue</mark>*

 

*<mark>\[Install\]</mark>*

*<mark>WantedBy=multi-user.target</mark>*

*--------------*

 

*+++++give MongoDB private address here++++ or give A record which is created in route53 -- here in this case given as **mongodb.chowdarychilukuri.in***

 

![2f9da8e0-a424-41ca-a72a-06e04ec72aa4.png|829.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/2f9da8e0-a424-41ca-a72a-06e04ec72aa4.png) [^49]

 

***#mongodb.chowdarychilukuri.in***

![213a0417-8f6a-4834-b3bc-d8711fc98510.png|817](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/213a0417-8f6a-4834-b3bc-d8711fc98510.png) [^50]

 

*Daemon Load the service.*

```
systemctl daemon-reload
```

![15197efb-1a7d-449a-888c-13349e08cb00.png|767](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/15197efb-1a7d-449a-888c-13349e08cb00.png) [^51]

 

*Start the service.*

```
systemctl enable catalogue
```

```
systemctl start catalogue
```

```
systemctl status catalogue
```

 

![c544e366-ef21-4ab2-bdea-37e431ea48e1.png|799.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c544e366-ef21-4ab2-bdea-37e431ea48e1.png) [^52]

 

![d21bc5e7-d1c1-4e2e-b220-9bdcc88b39c2.png|859.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d21bc5e7-d1c1-4e2e-b220-9bdcc88b39c2.png) [^53]

 

![be037f20-524a-40a2-b9e8-14ea3e7b6d21.png|674](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/be037f20-524a-40a2-b9e8-14ea3e7b6d21.png) [^54]

\

```
vim /etc/yum.repos.d/mongo.repo
```

*-------------*

*<mark>\[mongodb-org-4.2\]</mark>*

*<mark>name=MongoDB Repository</mark>*

*<mark>baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/</mark>*

*<mark>gpgcheck=0</mark>*

*<mark>enabled=1</mark>*

*-------------*

```
cat vim /etc/yum.repos.d/mongo.repo
```

 

![c4ec48cc-5cd6-41bc-a5cc-9a1f5678033e.png|724.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c4ec48cc-5cd6-41bc-a5cc-9a1f5678033e.png) [^55]

 

***Now installing a client package:***

```
dnf install mongodb-org-shell -y
```

![7e196fc6-c91d-42f2-a8c4-5647cbd47daa.png|770.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7e196fc6-c91d-42f2-a8c4-5647cbd47daa.png) [^56]

 

 

***Syn:** mongo --host MONGODB-SERVER-IPADDRESS </app/schema/catalogue.js              **-> 172.31.39.106/domain name  this is mongo DB server private IP***

```
mongo --host mongodb.chowdarychilukuri.in </app/schema/catalogue.js
```

 

![7f3d737d-1c12-4369-bb12-23cc26cd15f8.png|759.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7f3d737d-1c12-4369-bb12-23cc26cd15f8.png) [^57]

 

```
systemctl restart catalogue
```

```
systemctl status catalogue
```

```
netstat -lntp                --> port 8080 application is running
```

![7590e9d5-dc2b-422e-b132-b6d3ab792c64.png|931.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7590e9d5-dc2b-422e-b132-b6d3ab792c64.png) [^58]

 

![35a1d9b4-6cb9-42df-a540-0854047a2a3f.png|905.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/35a1d9b4-6cb9-42df-a540-0854047a2a3f.png) [^59]

 

*Now checking logs*

```
tail -f         -->will give running logs
```

*Or*

```
less /var/log/messages    --> these 2 commands is not working for me….
```

 

 

# *<mark style="background-color:#f8914d;">**Now configuring WEB Module**:<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*We are using Nginx as Web server, webservers' is nothing but Http server's -- Nginx port - 80 (Nginx is a popular webserver)*

![a125ae92-0e90-4348-9d2b-e1c3e7df1d48.png|582](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a125ae92-0e90-4348-9d2b-e1c3e7df1d48.png) [^60]

*<mark style="background-color:#f8d616;">**Installing NGINX: on web server**<!-- {"backgroundCycleColor":"25"} --></mark>*

 

*dnf Vs yum   --> not much difference, Yum consumes more memory. Redhat is bringing dnf as default package installer in future versions of RHEL.*

*-----------*

*centos 7 = yum is default package*

*centos 8/9 = dnf is default package manager*

 

```
sudo su -
```

```
dnf install nginx -y
```

 

![4c05b269-9645-43fa-9a6e-b90644643484.png|853.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4c05b269-9645-43fa-9a6e-b90644643484.png) [^61]

 

***Start & Enable Nginx service***

```
systemctl enable nginx
```

```
systemctl start nginx
```

```
systemctl status nginx
```

![abb86d85-4feb-44a7-9c1e-5bf105598186.png|778.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/abb86d85-4feb-44a7-9c1e-5bf105598186.png) [^62]

 

 

```
netstat -lntp    --> to check ports opened or not
```

![dd06561d-6ed1-4442-a27a-22f293588854.png|897.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/dd06561d-6ed1-4442-a27a-22f293588854.png) [^63]

 

 

[*<mark>http://<public-IP>:80</mark>*](http://%3cpublic-IP%3e:80) 

*<mark>http:3.85.61.63:80</mark>*

*<mark>Or</mark>*

*<mark>3.85.61.63</mark>*

*<mark>Or</mark>*

*<mark>chowdarychilukuri.in</mark>*

 

 

![8b59ae3b-93b3-4200-949d-d5c07f4d9d40.png|805.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8b59ae3b-93b3-4200-949d-d5c07f4d9d40.png) [^64]

 

*/etc/nginx   --> n**ginx configuration files will be present here.***

 

```
cd /etc/nginx/
```

*I**n this file all nginx config files will be present & it will have all details like where error logs will save, access logs, where html pages will be there.  which port server is using ex:80 for nginx.***

```
vim nginx.conf 
```

\

![b568e1de-591c-432e-b91f-99ec3b5b56f4.png|813.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/b568e1de-591c-432e-b91f-99ec3b5b56f4.png) [^65]

 

 

***Remove the default content that web server is serving.***

```
cd /usr/share/nginx/html/
```

```
ls -l
```

```
rm -rf /usr/share/nginx/html/*
```

```
ls -l
```

![a7a6ebf6-5b1a-4d64-92f2-01b94f3dfe12.png|855.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a7a6ebf6-5b1a-4d64-92f2-01b94f3dfe12.png) [^66]

 

*Now web page code is ready & built. Developer pushed/placed packages in one location(here in aws s3). Copy those code files to /usr/share/nginx/html/  (we are configuring manually this setup)*

*Download the frontend content*

 

*#curl -o /tmp/web.zip* [*https://roboshop-builds.s3.amazonaws.com/web.zip*](https://roboshop-builds.s3.amazonaws.com/web.zip) 

```
cd /tmp/
```

```
ls -l
```

 

![c04869ef-eaf9-4126-83a3-3b29cf1e23ce.png|798.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c04869ef-eaf9-4126-83a3-3b29cf1e23ce.png) [^67]

 

*Extract the frontend content.*

```
cd /usr/share/nginx/html
```

```
ls -l
```

```
unzip /tmp/web.zip
```

```
ls -l
```

![1ff41e72-375d-407a-a157-d1fe71ac8a1a.png|725](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1ff41e72-375d-407a-a157-d1fe71ac8a1a.png) [^68]

 

![a89386b8-0848-47c1-b23d-c0528c368855.png|769.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a89386b8-0848-47c1-b23d-c0528c368855.png) [^69]

 

![daa10e5c-13fb-48de-bcb5-ce93e9c13034.png|823](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/daa10e5c-13fb-48de-bcb5-ce93e9c13034.png) [^70]

 

![f99b1b09-0a9a-4b30-97d9-d755b8ced852.png|825.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/f99b1b09-0a9a-4b30-97d9-d755b8ced852.png) [^71]

 

 

# *<mark style="background-color:#f8d616;">**Create Nginx Reverse Proxy Configuration.**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

\

*Forward proxy vs reverse proxy*

*-------------------------------*

*VPN --> virtual private network*

 

*Servers are not aware of clients are behind VPN*

*anonymous access --> hiding our identity*

 

*forward proxies can't understand real clients*

 

*security --> companies can impose restrictions not to use particular sites, file upload and to monitor use internet behaviour*

 

*clients are aware of proxy, servers are not aware*

 

*reverse proxy*

*-------------------------------*

*clients are not aware of server side*

*apps use reverse proxy to secure their code*

*load balancing*

 

 

***Forward proxy***

![9f1e7adb-4630-4358-aeae-a7e6e39b7a87.png|635](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/9f1e7adb-4630-4358-aeae-a7e6e39b7a87.png) [^72]

 

 

![633f665c-a92a-43f5-95a0-02e231daf5e7.png|628](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/633f665c-a92a-43f5-95a0-02e231daf5e7.png) [^73]

 

![faa44a7c-6b0f-407c-abdd-f2438f270798.png|765.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/faa44a7c-6b0f-407c-abdd-f2438f270798.png) [^74]

 

```
vim /etc/nginx/default.d/roboshop.conf
```

*Place below content in above roboshop.conf file*

*---------*

*<mark>proxy_http_version 1.1;</mark>*

*<mark>location /images/ {</mark>*

  *<mark>expires 5s;</mark>*

  *<mark>root   /usr/share/nginx/html;</mark>*

  *<mark>try_files $uri /images/placeholder.jpg;</mark>*

*<mark>}</mark>*

*<mark>location /api/catalogue/ { proxy_pass</mark>* [*<mark>http://localhost:8080/</mark>*](http://localhost:8080/)*<mark>; }</mark>*

*<mark>location /api/user/ { proxy_pass</mark>* [*<mark>http://localhost:8080/</mark>*](http://localhost:8080/)*<mark>; }</mark>*

*<mark>location /api/cart/ { proxy_pass</mark>* [*<mark>http://localhost:8080/</mark>*](http://localhost:8080/)*<mark>; }</mark>*

*<mark>location /api/shipping/ { proxy_pass</mark>* [*<mark>http://localhost:8080/</mark>*](http://localhost:8080/)*<mark>; }</mark>*

*<mark>location /api/payment/ { proxy_pass</mark>* [*<mark>http://localhost:8080/</mark>*](http://localhost:8080/)*<mark>; }</mark>*

 

*<mark>location /health {</mark>*

  *<mark>stub_status on;</mark>*

  *<mark>access_log off;</mark>*

*<mark>}</mark>*

*--------*

```
cat /etc/nginx/default.d/roboshop.conf
```

 

![66893fbf-8d59-41bb-b853-658743c47804.png|844.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/66893fbf-8d59-41bb-b853-658743c47804.png) [^75]

 

![2d825e1a-6b92-4420-a351-d7c807b18ba2.png|835.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/2d825e1a-6b92-4420-a351-d7c807b18ba2.png) [^76]

 

*Ensure you replace the localhost with the actual ip address/domain of those component server. Word localhost is just used to avoid the failures on the Nginx Server.*

```
 systemctl restart nginx
```

```
systemctl status nginx
```

 

![cfdf4d76-cf12-4dea-8825-43d0002bc23b.png|782.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/cfdf4d76-cf12-4dea-8825-43d0002bc23b.png) [^77]

 

![16e243de-2fae-4f6d-98e5-7eb07bfafc5d.png|771.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/16e243de-2fae-4f6d-98e5-7eb07bfafc5d.png) [^78]

 

 

 

# *<mark style="background-color:#f8914d;">**Now configuring REDIS Module**:<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*Redis is a cache server, its mainly used for speed. If any request comes it first searches in redis cache & if not found it will connect to DB & stores that data in redis cache for further use aswell.*

 

![e1d6c522-f8f9-4e98-baac-e45f0165d5a7.png|420](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e1d6c522-f8f9-4e98-baac-e45f0165d5a7.png) [^79]

 

![5577a498-5ac5-45d0-8ea6-e29485e65749.png|797](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5577a498-5ac5-45d0-8ea6-e29485e65749.png) [^80]

```
sudo su -
```

*# dnf install* [*https://rpms.remirepo.net/enterprise/remi-release-8.rpm*](https://rpms.remirepo.net/enterprise/remi-release-8.rpm) *-y           -->here  installing package from url*

 

![1079ee5d-b68c-4776-a93a-04c757f644a3.png|845.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1079ee5d-b68c-4776-a93a-04c757f644a3.png) [^81]

 

 

*Enable Redis 6.2 from package streams.*

```
dnf module enable redis:remi-6.2 -y
```

 

![1c6b1f44-5dd0-4d7d-bd04-efb0a5f6755e.png|765.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1c6b1f44-5dd0-4d7d-bd04-efb0a5f6755e.png) [^82]

 

*Install REDIS*

```
dnf install redis -y
```

 

![664a8445-cf52-4a54-bcd3-7a38a1ed3b42.png|809.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/664a8445-cf52-4a54-bcd3-7a38a1ed3b42.png) [^83]

 

![94f4e0d1-c668-4cec-8add-868109f49d32.png|819.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/94f4e0d1-c668-4cec-8add-868109f49d32.png) [^84]

```
vim /etc/redis.conf
```

```
cat /etc/redis.conf
```

![d4baf22e-4dd6-4b7b-917a-bd06494911b4.png|772.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d4baf22e-4dd6-4b7b-917a-bd06494911b4.png) [^85]

 

 

 

*Start & Enable Redis Service*

```
systemctl enable redis
```

```
systemctl start redis
```

```
systemctl status redis
```

![586e5688-39c3-4abe-aa5e-5aef5367d5fb.png|953.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/586e5688-39c3-4abe-aa5e-5aef5367d5fb.png) [^86]

 

```
netstat -lntp
```

![d8e3caa4-b298-47c8-8070-810fb375be53.png|861.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d8e3caa4-b298-47c8-8070-810fb375be53.png) [^87]

 

 

 

 

# *<mark style="background-color:#f8914d;">**Now configuring USER Module**:<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*User Application is dependent on MongoDB & Redis*

![e99d6340-9a00-403a-a8ad-32dd3accf7a1.png|805.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e99d6340-9a00-403a-a8ad-32dd3accf7a1.png) [^88]

 

```
sudo su -
```

```
dnf module disable nodejs -y
```

```
dnf module enable nodejs:18 -y
```

![f2737135-96a7-4bef-889b-02f76c9b03ba.png|793.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/f2737135-96a7-4bef-889b-02f76c9b03ba.png) [^89]

 

*Install NodeJS*

```
 dnf install nodejs -y
```

![0008f066-89f4-4c53-a9e2-d3b4ba133d07.png|837.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0008f066-89f4-4c53-a9e2-d3b4ba133d07.png) [^90]

 

*Configure the application.*

*Add application User*

```
useradd roboshop
```

![7a36a6a1-52c1-4bf7-8da2-3d53bfd209a5.png|811](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7a36a6a1-52c1-4bf7-8da2-3d53bfd209a5.png) [^91]

 

*Lets setup an app directory.*

```
mkdir /app
```

![c0df7f8a-d924-4962-85c6-723bec3701e6.png|604](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c0df7f8a-d924-4962-85c6-723bec3701e6.png) [^92]

 

*Download the application code to created app directory.*

```
cd /app
```

*#curl -L -o /tmp/user.zip* [*https://roboshop-builds.s3.amazonaws.com/user.zip*](https://roboshop-builds.s3.amazonaws.com/user.zip) 

```
ls -l
```

 

![792131c2-7d09-4e94-ab67-2f022f0581be.png|843.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/792131c2-7d09-4e94-ab67-2f022f0581be.png) [^93]

 

![431e1a1c-55fc-41ee-8d28-b6c5610d2df3.png|835](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/431e1a1c-55fc-41ee-8d28-b6c5610d2df3.png) [^94]

 

 

 

*NPM install:*

![e863a50a-f252-40cb-81d0-f016d099105e.png|816.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e863a50a-f252-40cb-81d0-f016d099105e.png) [^95]

 

```
cd /app
```

```
/npm install
```

![19bb83bb-6a68-438d-a4c0-094c8506a3b6.png|847.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/19bb83bb-6a68-438d-a4c0-094c8506a3b6.png) [^96]

 

 

![0cfa9a8b-58d0-4cf4-a913-1134ab782241.png|492](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0cfa9a8b-58d0-4cf4-a913-1134ab782241.png) [^97]

```
vim /etc/systemd/system/user.service
```

*----*

*<mark>\[Unit\]</mark>*

*<mark>Description = User Service</mark>*

*<mark>\[Service\]</mark>*

*<mark>User=roboshop</mark>*

*<mark>Environment=MONGO=true</mark>*

*<mark>Environment=REDIS_HOST=<REDIS-SERVER-IP></mark>*

*<mark>Environment=MONGO_URL="mongodb://<MONGODB-SERVER-IP-ADDRESS>:27017/users"</mark>*

*<mark>ExecStart=/bin/node /app/server.js</mark>*

*<mark>SyslogIdentifier=user</mark>*

 

*<mark>\[Install\]</mark>*

*<mark>WantedBy=multi-user.target</mark>*

 

*----------*

```
cat /etc/systemd/system/user.service
```

![889a44b0-5dad-4c01-84c9-005c0dd894e1.png|849.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/889a44b0-5dad-4c01-84c9-005c0dd894e1.png) [^98]

 

 

*Load the service.*

```
systemctl daemon-reload
```

```
systemctl enable user
```

```
systemctl start user
```

```
systemctl status user
```

![8301ee57-4ad7-413c-96f5-f7ec5f42302e.png|821.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8301ee57-4ad7-413c-96f5-f7ec5f42302e.png) [^99]

 

![877dbc39-c67e-4e97-aa84-db8ea79536af.png|819.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/877dbc39-c67e-4e97-aa84-db8ea79536af.png) [^100]

 

![fc0cccd8-4a00-4abd-8638-7cea54d899a2.png|817](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/fc0cccd8-4a00-4abd-8638-7cea54d899a2.png) [^101]

```
vim /etc/yum.repos.d/mongo.repo
```

*-------*

*<mark>\[mongodb-org-4.2\]</mark>*

*<mark>name=MongoDB Repository</mark>*

*<mark>baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/</mark>*

*<mark>gpgcheck=0</mark>*

*<mark>enabled=1</mark>*

*-------*

```
cat /etc/yum.repos.d/mongo.repo
```

 

![e94fc6dd-506b-40ae-bbe2-7ec7a5d06d18.png|802.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e94fc6dd-506b-40ae-bbe2-7ec7a5d06d18.png) [^102]

 

```
dnf install mongodb-org-shell -y
```

![e417cabf-d0d4-40e5-a2da-58944fabad45.png|786.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e417cabf-d0d4-40e5-a2da-58944fabad45.png) [^103]

 

*To see default users*

```
cat /app/schema/user.js
```

![4aa577c6-3a53-4c5a-ab34-9458dde3f582.png|786.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4aa577c6-3a53-4c5a-ab34-9458dde3f582.png) [^104]

 

 

***Syn**:  mongo --host MONGODB-SERVER-IPADDRESS </app/schema/user.js*

 

```
mongo --host mongodb.chowdarychilukuri.in </app/schema/user.js             --> users are created
```

 

![db7ae545-9b00-4845-a3c1-bee005ac84e4.png|885.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/db7ae545-9b00-4845-a3c1-bee005ac84e4.png) [^105]

 

 

*Now login to WEB server: to added A record of user (user.chowdarychilukuri.in)*

```
vim /etc/nginx/default.d/roboshop.conf
```

```
cat /etc/nginx/default.d/roboshop.conf
```

 

![d7cd3f29-f2d9-4a80-badd-18f477234736.png|826.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d7cd3f29-f2d9-4a80-badd-18f477234736.png) [^106]

 

![bc106cf9-7f4a-46ee-b24c-a300a095738c.png|819.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/bc106cf9-7f4a-46ee-b24c-a300a095738c.png) [^107]

 

 

*Restart NGNIX service*

```
systemctl restart nginx
```

```
systemctl status nginx
```

![155e2eb4-cbf9-4b55-afa2-ecd98b65fc5e.png|789.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/155e2eb4-cbf9-4b55-afa2-ecd98b65fc5e.png) [^108]

 

 

***Now try to login with below users in web application: as users are existed***

 

***Users present/loaded in USER Application***

 

![7bb5eaae-8654-4f94-bf61-2f9abf086976.png|870](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7bb5eaae-8654-4f94-bf61-2f9abf086976.png) [^109]

 

![ae5a3b3d-e797-4200-af55-a2607eb63156.png|614](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ae5a3b3d-e797-4200-af55-a2607eb63156.png) [^110]

 

 

![477663c4-4a25-45d5-a4f1-e7153a2a5107.png|587](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/477663c4-4a25-45d5-a4f1-e7153a2a5107.png) [^111]

 

 

*Registering a new user:*

![6e80df32-b012-41d7-acd9-c54cf2beec9f.png|683](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/6e80df32-b012-41d7-acd9-c54cf2beec9f.png) [^112]

 

![cd541a21-c58e-4ac2-91f1-cc3653aa6868.png|703](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/cd541a21-c58e-4ac2-91f1-cc3653aa6868.png) [^113]

 

# *<mark style="background-color:#f8914d;">**Now configuring CART Module**:<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Cart Application is dependent on Catalogue & Redis*

![c8fecb41-367e-4801-b161-1cf57c3db5a5.png|805.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c8fecb41-367e-4801-b161-1cf57c3db5a5.png) [^114]

```
sudo su -
```

```
dnf module disable nodejs -y
```

```
dnf module enable nodejs:18 -y
```

![382f7ff3-cc4c-4b0c-bdfc-f42e67611ea4.png|815.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/382f7ff3-cc4c-4b0c-bdfc-f42e67611ea4.png) [^115]

 

 

*Install NodeJS*

```
dnf install nodejs -y
```

![87ffebf0-52e9-40e9-be10-6395b5af263e.png|787.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/87ffebf0-52e9-40e9-be10-6395b5af263e.png) [^116]

 

*Configure the application.*

*Add application User*

 

```
useradd roboshop
```

![2a102ae3-ceb2-4fdc-adcd-b2dde46dd139.png|660](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/2a102ae3-ceb2-4fdc-adcd-b2dde46dd139.png) [^117]

 

*Lets setup an app directory.*

```
mkdir /app 
```

![be5551ae-2995-48c3-949f-f0e26169183d.png|559](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/be5551ae-2995-48c3-949f-f0e26169183d.png) [^118]

 

*Download the application code to created app directory.*

 

*#curl -L -o /tmp/cart.zip* [*https://roboshop-builds.s3.amazonaws.com/cart.zip*](https://roboshop-builds.s3.amazonaws.com/cart.zip) 

```
cd /app
```

```
ls -l
```

```
unzip /tmp/cart.zip
```

```
ls -l
```

 

![2f2c84e9-a8e0-4fee-b750-f6aec8ffb6d7.png|781.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/2f2c84e9-a8e0-4fee-b750-f6aec8ffb6d7.png) [^119]

 

 

![cfe1b3d5-7157-4994-b003-0d44a8f709a0.png|815.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/cfe1b3d5-7157-4994-b003-0d44a8f709a0.png) [^120]

 

```
cd /app
```

```
npm install
```

![354d109f-8b21-41ff-a7ef-3ed6197f44ee.png|921.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/354d109f-8b21-41ff-a7ef-3ed6197f44ee.png) [^121]

 

 

![04216397-0088-4b1b-ba73-ce5415bcc938.png|674](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/04216397-0088-4b1b-ba73-ce5415bcc938.png) [^122]

 

```
vim /etc/systemd/system/cart.service
```

*-----------------*

*<mark>\[Unit\]</mark>*

*<mark>Description = Cart Service</mark>*

*<mark>\[Service\]</mark>*

*<mark>User=roboshop</mark>*

*<mark>Environment=REDIS_HOST=redis.chowdarychilukuri.in</mark>*

*<mark>Environment=CATALOGUE_HOST=catalogue.chowdarychilukuri.in</mark>*

*<mark>Environment=CATALOGUE_PORT=8080</mark>*

*<mark>ExecStart=/bin/node /app/server.js</mark>*

*<mark>SyslogIdentifier=cart</mark>*

 

*<mark>\[Install\]</mark>*

*<mark>WantedBy=multi-user.target</mark>*

*-------------*

```
cat /etc/systemd/system/cart.service
```

![2de8559f-c212-4c19-94e2-90d5ff92e229.png|793.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/2de8559f-c212-4c19-94e2-90d5ff92e229.png) [^123]

 

*Load the service.*

```
systemctl daemon-reload
```

```
systemctl enable cart
```

```
systemctl start cart
```

![0995e980-bb26-4b7e-bb24-60e95d2bed6d.png|823.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0995e980-bb26-4b7e-bb24-60e95d2bed6d.png) [^124]

 

*Now login to WEB server: to added A record of cart(cart.chowdarychilukuri.in)*

```
vim /etc/nginx/default.d/roboshop.conf
```

```
cat /etc/nginx/default.d/roboshop.conf
```

 

![412147d2-08c5-46cf-9514-a22ea658388f.png|722.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/412147d2-08c5-46cf-9514-a22ea658388f.png) [^125]

 

 

*Now restart NGNIX service*

```
systemctl restart nginx
```

```
systemctl status nginx
```

![1f2c4135-1e9e-4901-a1e6-46811c334b29.png|707.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1f2c4135-1e9e-4901-a1e6-46811c334b29.png) [^126]

 

*Now try to added products to cart:*

![e3cfc272-335b-4d2a-b5e1-bc9af099c950.png|679](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e3cfc272-335b-4d2a-b5e1-bc9af099c950.png) [^127]

 

 

 

***Now Launching MYSQL instance:***

![265c931c-435e-469d-9a2f-4a56002e2e90.png|685.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/265c931c-435e-469d-9a2f-4a56002e2e90.png) [^128]

 

 

![dd7f5ebe-54c1-4711-b44a-33179a8dffc7.png|765.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/dd7f5ebe-54c1-4711-b44a-33179a8dffc7.png) [^129]

 

 

![10cdb26f-67d7-4385-bd96-e9d9e5c50728.png|777.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/10cdb26f-67d7-4385-bd96-e9d9e5c50728.png) [^130]

 

```
sudo su
```

```
dnf module disable mysql -y
```

 

![7a4e241d-10c2-476c-9d71-caf86a99d0dd.png|826.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7a4e241d-10c2-476c-9d71-caf86a99d0dd.png) [^131]

 

```
vim /etc/yum.repos.d/mysql.repo
```

*-----------*

*<mark>\[mysql\]</mark>*

*<mark>name=MySQL 5.7 Community Server</mark>*

*<mark>baseurl=http://repo.mysql.com/yum/mysql-5.7-community/el/7/$basearch/</mark>*

*<mark>enabled=1</mark>*

*<mark>gpgcheck=0</mark>*

*-------*

```
cat /etc/yum.repos.d/mysql.repo
```

![1a7312f5-1ab4-454c-b81e-c6f03b0c80d1.png|863.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1a7312f5-1ab4-454c-b81e-c6f03b0c80d1.png) [^132]

 

 

*Install MySQL Server*

```
dnf install mysql-community-server -y
```

![e659cdd0-e18c-4e85-bed3-a3c13f9b496e.png|839.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/e659cdd0-e18c-4e85-bed3-a3c13f9b496e.png) [^133]

 

 

*Start MySQL Service*

```
systemctl enable mysqld
```

```
systemctl start mysqld
```

![5bff207a-5aea-44d9-8ad0-96a3f7e7f5ae.png|732](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5bff207a-5aea-44d9-8ad0-96a3f7e7f5ae.png) [^134]

 

![9571a0de-ce01-40e2-af8f-6779aeb5f3c7.png|733.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/9571a0de-ce01-40e2-af8f-6779aeb5f3c7.png) [^135]

 

```
mysql_secure_installation --set-root-pass RoboShop@1
```

![8959971a-13b0-4783-be1d-619b47100549.png|800.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8959971a-13b0-4783-be1d-619b47100549.png) [^136]

 

```
netstat -lntp
```

 

![44115be8-413a-4988-9ffe-fe51a2cf855a.png|811.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/44115be8-413a-4988-9ffe-fe51a2cf855a.png) [^137]

 

 

*To check if connections are good*

```
mysql -uroot -pRoboShop@1
```

```
exit
```

![cd983fa4-9e17-4625-802b-a6e6e5e0c0cd.png|825.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/cd983fa4-9e17-4625-802b-a6e6e5e0c0cd.png) [^138]

 

 

***Shipping Application launch & configure:***

 

 

![0346ff8f-c800-46f7-b69b-c6a61f5c2070.png|834.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0346ff8f-c800-46f7-b69b-c6a61f5c2070.png) [^139]

 

![3e8c8062-3f9b-4d5f-8ad6-feaf16bc19ba.png|768.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/3e8c8062-3f9b-4d5f-8ad6-feaf16bc19ba.png) [^140]

 

![62354a6e-6106-49d7-aa2e-decb3d0c0d99.png|779](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/62354a6e-6106-49d7-aa2e-decb3d0c0d99.png) [^141]

 

![6da264b6-8d6e-493e-95bf-f7d95c1dd79a.png|766.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/6da264b6-8d6e-493e-95bf-f7d95c1dd79a.png) [^142]

 

```
sudo su -
```

```
dnf install maven -y
```

 

![ae8a2aba-6910-4180-93b3-5e90409216e3.png|638.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ae8a2aba-6910-4180-93b3-5e90409216e3.png) [^143]

 

![b456dff6-7bd5-4194-8da2-56a3346afe21.png|252](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/b456dff6-7bd5-4194-8da2-56a3346afe21.png) [^144]

 

```
useradd roboshop
```

 

*Lets setup an app directory.*

 

```
mkdir /app
```

 

![fc03852c-4421-49b0-8481-523fdd0e4731.png|779](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/fc03852c-4421-49b0-8481-523fdd0e4731.png) [^145]

 

 

*Download the application code to created app directory.*

*#curl -L -o /tmp/shipping.zip* [*https://roboshop-builds.s3.amazonaws.com/shipping.zip*](https://roboshop-builds.s3.amazonaws.com/shipping.zip) 

```
cd /app
```

```
ls -l
```

```
unzip /tmp/shipping.zip
```

```
ls -l
```

 

![825034ec-4e4c-4790-ae12-92c4f8d263dc.png|930.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/825034ec-4e4c-4790-ae12-92c4f8d263dc.png) [^146]

 

![7b25e4ae-7c63-43eb-a554-5d051e984ba5.png|904.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7b25e4ae-7c63-43eb-a554-5d051e984ba5.png) [^147]

 

```
cd /app
```

```
mvn clean package
```

![31a66c46-c92f-433f-b61c-9935ab22e473.png|693](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/31a66c46-c92f-433f-b61c-9935ab22e473.png) [^148]

 

```
ls -l
```

```
cd target/
```

```
ls -l
```

![05dd7a47-c2a0-48b3-b21d-e2dfac4b25ef.png|750](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/05dd7a47-c2a0-48b3-b21d-e2dfac4b25ef.png) [^149]

 

![bf3aa5da-bfad-4f9c-a255-45131b8802fc.png|713.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/bf3aa5da-bfad-4f9c-a255-45131b8802fc.png) [^150]

 

```
cd /app
```

```
mv target/shipping-1.0.jar shipping.jar        --renaming & moving to /app folder
```

![0ad7225d-748d-4db9-bead-af9b048d912b.png|956.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0ad7225d-748d-4db9-bead-af9b048d912b.png) [^151]

 

![4902d2c0-ec94-48b2-9029-a1c084905579.png|890.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4902d2c0-ec94-48b2-9029-a1c084905579.png) [^152]

 

```
vim /etc/systemd/system/shipping.service
```

*------*

*<mark>\[Unit\]</mark>*

*<mark>Description=Shipping Service</mark>*

 

*<mark>\[Service\]</mark>*

*<mark>User=roboshop</mark>*

*<mark>Environment=CART_ENDPOINT=<CART-SERVER-IPADDRESS>:8080</mark>*

*<mark>Environment=DB_HOST=<MYSQL-SERVER-IPADDRESS></mark>*

*<mark>ExecStart=/bin/java -jar /app/shipping.jar</mark>*

*<mark>SyslogIdentifier=shipping</mark>*

 

*<mark>\[Install\]</mark>*

*<mark>WantedBy=multi-user.target</mark>*

 

*---------*

![39e6cc53-2cb4-4bcd-b24f-470a4b624aac.png|764](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/39e6cc53-2cb4-4bcd-b24f-470a4b624aac.png) [^153]

 

 

*We are loading countries, cities information . To check countries information*

```
ls -l
```

```
cd schema/
```

```
ls -l
```

```
less shipping.sql                --> this file will have huge data, like countries & cities etc
```

 

![c1c712fa-000c-4854-a3a6-ca7b7de6dabd.png|646](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c1c712fa-000c-4854-a3a6-ca7b7de6dabd.png) [^154]

 

*Load the service.*

```
systemctl daemon-reload
```

![57178a4e-bb1a-4719-a544-1f0ff032eafb.png|689](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/57178a4e-bb1a-4719-a544-1f0ff032eafb.png) [^155]

 

*Start the service.*

```
systemctl enable shipping
```

```
systemctl start shipping
```

![ee1278d1-b87f-4bf4-957c-052db0a76d85.png|736.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ee1278d1-b87f-4bf4-957c-052db0a76d85.png) [^156]

 

![abb441fc-18b1-4ea6-98ea-5f9df7f9d009.png|481](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/abb441fc-18b1-4ea6-98ea-5f9df7f9d009.png) [^157]

```
dnf install mysql -y
```

![5cc0ab34-e269-4259-b234-32ccdec444eb.png|806.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5cc0ab34-e269-4259-b234-32ccdec444eb.png) [^158]

 

 

*Load Schema  (means loading the data)*

***Syn:** mysql -h <MYSQL-SERVER-IPADDRESS> -uroot -pRoboShop@1 < /app/schema/shipping.sql*        --> this command takes sometime

```
mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1 < /app/schema/shipping.sql          
```

 

 

![a711c3fa-aa1c-4ec0-acd1-708a111dc471.png|994.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a711c3fa-aa1c-4ec0-acd1-708a111dc471.png) [^159]

 

![97c82377-bb26-425a-8743-b3b2ad0d62cd.png|946.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/97c82377-bb26-425a-8743-b3b2ad0d62cd.png) [^160]

```
systemctl restart shipping
```

![39c8e484-9b3c-43d5-b828-def04a7afcbf.png|822](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/39c8e484-9b3c-43d5-b828-def04a7afcbf.png) [^161]

 

```
netstat -lntp
```

![1baa0dbf-e7ea-48e7-b3a9-7cb78cc752a0.png|818.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1baa0dbf-e7ea-48e7-b3a9-7cb78cc752a0.png) [^162]

 

 

***To validate mqsql databases login to MYSQL application server DB and give a try below commands:***

```
mysql -uroot -pRoboShop@1
```

```
show databases;
```

```
use cities
```

```
show tables;
```

![0f3905c9-3e72-421e-8d6c-04395025cdee.png|818.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0f3905c9-3e72-421e-8d6c-04395025cdee.png) [^163]

 

![4ac26028-63b9-4d1f-ae59-9890d47dfef5.png|757.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4ac26028-63b9-4d1f-ae59-9890d47dfef5.png) [^164]

 

 

*Now login to **WEB Application server** and update the below entries:*

 

```
vim /etc/nginx/default.d/roboshop.conf
```

```
cat /etc/nginx/default.d/roboshop.conf
```

```
systemctl restart nginx
```

![2fadfa6a-fe22-44eb-86be-37def95e06ca.png|839.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/2fadfa6a-fe22-44eb-86be-37def95e06ca.png) [^165]

 

![b36d41ab-769a-4f0a-80c5-7920c2bb3d15.png|821.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/b36d41ab-769a-4f0a-80c5-7920c2bb3d15.png) [^166]

 

![59298f67-381a-4f40-981b-a67833a0e927.png|788.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/59298f67-381a-4f40-981b-a67833a0e927.png) [^167]

 

 

*It worked till shipping address*

 

![0755cedf-95c7-4d0b-b886-a62cfe8d52a7.png|668](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/0755cedf-95c7-4d0b-b886-a62cfe8d52a7.png) [^168]

\

\

# <mark style="background-color:#f8914d;">**Launching & configuring RabitMQ server**:<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

 

![fb8c8b65-7cd2-4e63-aa5b-6cfe8baea1bb.png|804.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/fb8c8b65-7cd2-4e63-aa5b-6cfe8baea1bb.png) [^169]

 

![db3709cb-ed5d-47cc-8ead-4deb59d976d5.png|836.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/db3709cb-ed5d-47cc-8ead-4deb59d976d5.png) [^170]

 

 

RabbitMQ is a ASYNC communication:

 

![8dc6c89f-88e9-4040-9d01-719dc3c2f6c0.png|747](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8dc6c89f-88e9-4040-9d01-719dc3c2f6c0.png) [^171]

 

![46a9b441-65dd-4259-bea3-197ab20118ba.png|860.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/46a9b441-65dd-4259-bea3-197ab20118ba.png) [^172]

 

![19e77eb2-1faf-4207-adda-891597c5ae65.png|809.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/19e77eb2-1faf-4207-adda-891597c5ae65.png) [^173]

 

```
sudo su -
```

\#curl -s [https://packagecloud.io/install/repositories/rabbitmq/erlang/script.rpm.sh](https://packagecloud.io/install/repositories/rabbitmq/erlang/script.rpm.sh) \| bash

 

![1d8761cf-084a-4b05-a1bb-4f8df6b6c72f.png|911.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1d8761cf-084a-4b05-a1bb-4f8df6b6c72f.png) [^174]

 

 

Configure YUM Repos for RabbitMQ.

\#curl -s [https://packagecloud.io/install/repositories/rabbitmq/rabbitmq-server/script.rpm.sh](https://packagecloud.io/install/repositories/rabbitmq/rabbitmq-server/script.rpm.sh) \| bash

![b9a0856f-1987-4a52-a283-7e9f22c1b40e.png|844.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/b9a0856f-1987-4a52-a283-7e9f22c1b40e.png) [^175]

 

 

Install RabbitMQ

```
dnf install rabbitmq-server -y
```

 

![54ca1112-31b2-4764-8608-36dcd3770a93.png|831.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/54ca1112-31b2-4764-8608-36dcd3770a93.png) [^176]

 

Start RabbitMQ Service

```
systemctl enable rabbitmq-server
```

```
systemctl start rabbitmq-server
```

```
systemctl status rabbitmq-server
```

 

![3372004a-51c9-4d7c-8d54-a181f38405a2.png|818.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/3372004a-51c9-4d7c-8d54-a181f38405a2.png) [^177]

 

![1204b6bb-54b5-402c-8b6e-84db3cb206b8.png|751.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1204b6bb-54b5-402c-8b6e-84db3cb206b8.png) [^178]

 

```
rabbitmqctl add_user roboshop roboshop123
```

```
rabbitmqctl set_permissions -p / roboshop ".*" ".*" ".*"
```

 

![7887685a-6a84-4de8-9a94-bc72d4b4d65c.png|735.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/7887685a-6a84-4de8-9a94-bc72d4b4d65c.png) [^179]

 

 

# <mark style="background-color:#f8914d;">**Launching & configuring PAYMENT server**:<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

 

![b96dfbd8-f6db-4173-9048-79ceecf2a3d8.png|705.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/b96dfbd8-f6db-4173-9048-79ceecf2a3d8.png) [^180]

 

![cac37d75-fcc1-463f-876f-1fce4de93e88.png|714.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/cac37d75-fcc1-463f-876f-1fce4de93e88.png) [^181]

 

 

```
sudo su -
```

```
dnf install python36 gcc python3-devel -y
```

 

![3f40ce0e-7fe2-4f69-9879-288121087cca.png|852.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/3f40ce0e-7fe2-4f69-9879-288121087cca.png) [^182]

 

Configure the application.

Add application User

Lets setup an app directory.

Download the application code to created app directory.

 

```
useradd roboshop
```

```
mkdir /app
```

\#curl -L -o /tmp/payment.zip [https://roboshop-builds.s3.amazonaws.com/payment.zip](https://roboshop-builds.s3.amazonaws.com/payment.zip) 

```
cd /app
```

```
ls -l
```

```
unzip /tmp/payment.zip
```

```
ls -l
```

![6ab44e90-ff9a-446e-be7a-87fd26a6bc39.png|910.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/6ab44e90-ff9a-446e-be7a-87fd26a6bc39.png) [^183]

 

![013ae6b0-f834-49a4-bba4-0bd54ba6f961.png|894.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/013ae6b0-f834-49a4-bba4-0bd54ba6f961.png) [^184]

 

```
cd /app
```

```
pip3.6 install -r requirements.txt
```

![febf2713-9bfe-4ad6-ab7d-337f18e7fcbd.png|998.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/febf2713-9bfe-4ad6-ab7d-337f18e7fcbd.png) [^185]

 

Requirements.txt file is dependency files to python.. These will download when we use above pip command

```
cat requirements.txt
```

![62edf373-7fa5-4d34-ad2d-99dee9cc7df5.png|793](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/62edf373-7fa5-4d34-ad2d-99dee9cc7df5.png) [^186]

 

![066378ea-2280-43fb-b6b3-1610d7e935d8.png|607](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/066378ea-2280-43fb-b6b3-1610d7e935d8.png) [^187]

```
vim /etc/systemd/system/payment.service
```

\-------------

<mark>\[Unit\]</mark>

<mark>Description=Payment Service</mark>

 

<mark>\[Service\]</mark>

<mark>User=root</mark>

<mark>WorkingDirectory=/app</mark>

<mark>Environment=CART_HOST=<CART-SERVER-IPADDRESS></mark>

<mark>Environment=CART_PORT=8080</mark>

<mark>Environment=USER_HOST=<USER-SERVER-IPADDRESS></mark>

<mark>Environment=USER_PORT=8080</mark>

<mark>Environment=AMQP_HOST=<RABBITMQ-SERVER-IPADDRESS></mark>

<mark>Environment=AMQP_USER=roboshop</mark>

<mark>Environment=AMQP_PASS=roboshop123</mark>

 

<mark>ExecStart=/usr/local/bin/uwsgi --ini payment.ini</mark>

<mark>ExecStop=/bin/kill -9 $MAINPID</mark>

<mark>SyslogIdentifier=payment</mark>

 

<mark>\[Install\]</mark>

<mark>WantedBy=multi-user.target</mark>

\-----------

```
cat  /etc/systemd/system/payment.service
```

![5f423764-33cd-42a7-9bad-8e143bd66dff.png|860](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5f423764-33cd-42a7-9bad-8e143bd66dff.png) [^188]

 

![c2dc3c65-553e-48e7-977b-1af895b15667.png|860.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c2dc3c65-553e-48e7-977b-1af895b15667.png) [^189]

 

 

Load the service.

```
systemctl daemon-reload
```

 

Start the service.

```
systemctl enable payment
```

```
systemctl start payment
```

```
systemctl status payment
```

```
netstat -lntp
```

 

![f5484a85-0234-4191-846f-cd4d27f94a1f.png|780.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/f5484a85-0234-4191-846f-cd4d27f94a1f.png) [^190]

 

![d13a3024-b68a-474e-861e-b74ae636cfa3.png|852.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d13a3024-b68a-474e-861e-b74ae636cfa3.png) [^191]

 

 

 

**Now login WEB server to change roboshop.conf**

```
vim /etc/nginx/default.d/roboshop.conf
```

```
systemctl restart nginx
```

![01edda18-93ba-41e6-9064-4c18b0da535b.png|769.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/01edda18-93ba-41e6-9064-4c18b0da535b.png) [^192]

 

 

Payment completed & order is successful

![ee6a63a2-d2bb-43b2-a553-5a683530c2b0.png|859.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/ee6a63a2-d2bb-43b2-a553-5a683530c2b0.png) [^193]

 

 

# <mark style="background-color:#f8914d;">**Launching & configuring DISPATCH server**:<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

 

![a2981887-69fe-4113-a9a0-67c6bf690187.png|792.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/a2981887-69fe-4113-a9a0-67c6bf690187.png) [^194]

 

 

![9f8e8688-5dae-4667-b97c-d8c99821e3f6.png|744.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/9f8e8688-5dae-4667-b97c-d8c99821e3f6.png) [^195]

 

![3916f238-5794-40ac-8b8c-0bd09de01663.png|689.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/3916f238-5794-40ac-8b8c-0bd09de01663.png) [^196]

 

 

![1739b008-4552-4469-8c64-6a567248693e.png|906.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/1739b008-4552-4469-8c64-6a567248693e.png) [^197]

 

![5ed3676c-9316-4fed-ba62-1519eb36b1a4.png|293](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5ed3676c-9316-4fed-ba62-1519eb36b1a4.png) [^198]

```
useradd roboshop
```

```
mkdir /app
```

![f3abd38b-5344-4f36-a812-d0b96e11cddd.png|694](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/f3abd38b-5344-4f36-a812-d0b96e11cddd.png) [^199]

 

Download the application code to created app directory.

\#curl -L -o /tmp/dispatch.zip [https://roboshop-builds.s3.amazonaws.com/dispatch.zip](https://roboshop-builds.s3.amazonaws.com/dispatch.zip) 

```
cd /app
```

```
unzip /tmp/dispatch.zip
```

```
ls -l
```

![5ec6b3fe-9851-49ab-8fe5-1f07d4b2b5ae.png|820.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/5ec6b3fe-9851-49ab-8fe5-1f07d4b2b5ae.png) [^200]

 

![d01a51c3-296a-4b51-80a7-234ddb4ac959.png|862.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/d01a51c3-296a-4b51-80a7-234ddb4ac959.png) [^201]

```
cd /app
```

```
go mod init dispatch
```

```
go get
```

```
go build
```

 

![c0491b5c-3885-4dea-838f-3eb2bffc31af.png|822.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/c0491b5c-3885-4dea-838f-3eb2bffc31af.png) [^202]

 

![4a0d68be-2046-473b-8292-10ce186fd07a.png|628](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/4a0d68be-2046-473b-8292-10ce186fd07a.png) [^203]

 

```
vim /etc/systemd/system/dispatch.service
```

\----------

<mark>\[Unit\]</mark>

<mark>Description = Dispatch Service</mark>

<mark>\[Service\]</mark>

<mark>User=roboshop</mark>

<mark>Environment=AMQP_HOST=RABBITMQ-IP</mark>

<mark>Environment=AMQP_USER=roboshop</mark>

<mark>Environment=AMQP_PASS=roboshop123</mark>

<mark>ExecStart=/app/dispatch</mark>

<mark>SyslogIdentifier=dispatch</mark>

 

<mark>\[Install\]</mark>

<mark>WantedBy=multi-user.target</mark>

\--------

```
cat /etc/systemd/system/dispatch.service
```

 

 

![9ba57dae-3b54-475f-ad18-c63c61733c19.png|729](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/9ba57dae-3b54-475f-ad18-c63c61733c19.png) [^204]

 

Load the service.

Start the service.

```
systemctl daemon-reload
```

```
systemctl enable dispatch
```

```
systemctl start dispatch
```

```
systemctl status dispatch
```

 

![8affbebd-ea60-4edf-b4c2-273683cd82ae.png|845.3333740234375](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/8affbebd-ea60-4edf-b4c2-273683cd82ae.png) [^205]

 

```
tail -f /var/log/messages
```

![281ba6d5-243f-467c-b4c0-4b95a1b48bcb.png|694](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/281ba6d5-243f-467c-b4c0-4b95a1b48bcb.png) [^206]

 

 ![23c2dc7f-c921-4d74-8ff9-b5d65343ac09.png|626](https://images.amplenote.com/98b39b84-0e94-11ef-841c-a6f126245c9e/23c2dc7f-c921-4d74-8ff9-b5d65343ac09.png) [^207]

[^1]: Project configuration
    create a server
    installed programming language
    downloaded code/application
    created directories, users I
    installed dependencies
    start application

[^2]: How to install application in Linux
    - -
    We should have server
    nodejs, .net, java, python, php, go, etc.
    install that programming language
    creating a directory
    creating a seperate user for that application
    downloading the application
    H

[^3]: downloading the application
    install dependencies
    nodejs --> npm
    java --> mvn
    python --> pip
    . net --> nuget
    H
    we are giving how to run in /etc/systemd/system/application. service
    systemctl start application
    systemctl enable application

[^4]: errors
    web --> roboshop. conf catalogue IP
    catalogue --> is running or not
    data loaded to mongodb or not
    catalogue. service mongodb IP is good or not
    mongodb --> remote 0.0.0.0 allowed or not
    firewalls

[^5]: web
    Add additional tags
    Summary
    Number of instances
    Info
    Application and OS Images (Amazon Machine Image) Info
    5
    When launching more than 1 instance, consider EC2 Auto
    An AMI is a template that contains the software configuration (operating system, application server, and
    Scaling
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    below
    Software Image (AMI)
    Centos-8-DevOps-Practice
    devops-practice
    X
    ami-03265a0778a880afb
    Virtual server type (instance type)
    AMI from catalog
    Quick Start
    t2.micro
    Firewall (security group)
    Amazon Machine Image (AMI)
    Q
    New security group
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Browse more AMIs
    Storage (volumes)
    Including AMIs from
    AWS, Marketplace and
    1 volume(s) - 10 GiB
    the Community
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    Free tier: In your first year includes
    X
    AMIs
    04T17:05:56.00
    750 hours of t2.micro (or t3.micro in
    OZ
    the Regions in which t2.micro is
    unavailable) instance usage on free
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Instance type
    Cancel
    Launch instance
    t2.micro
    Free tier eligible
    Review commands
    Family: t2 1 vCPU 1 GiB Memory Current generation: true
    All generations
    On-Demand Windows base pricing: 0.0162 USD per Hour
    On-Demand SUSE base pricing: 0.0116 USD per Hour

[^6]: Key pair name - required
    Proceed without a key pair (Not recommended)
    Default value
    C
    Create new key pair
    Number of instances Info
    5
    When launching more than 1 instance, consider EC2 Auto
    Network settings Info
    Edit
    Scaling
    Software Image (AMI)
    Network Info
    Centos-8-DevOps-Practice
    vpc-0817 cae8968304c06
    ami-03265a0778a880afb
    Subnet Info
    Virtual server type (instance type)
    No preference (Default subnet in any availability zone)
    t2.micro
    Auto-assign public IP Info
    Firewall (security group)
    Enable
    SG_Allow_ALL
    Firewall (security groups) Info
    Storage (volumes)
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    1 volume(s) - 10 GiB
    instance.
    Create security group
    Select existing security group
    @ Free tier: In your first year includes
    X
    Common security groups Info
    750 hours of t2.micro (or t3.micro in
    Select security groups
    the Regions in which t2.micro is
    G
    Compare security
    unavailable) instance usage on free
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    tier AMIs per month, 30 GiB of EBS
    VPC: vpc-0817cae89b8304c06
    storage, 2 million IOs, 1 GB of
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    snapshots, and 100 GB of bandwidth
    to the internet.
    Configure storage Info
    Advanced
    Cancel
    Launch instance
    1x
    10
    GIB
    gp2
    Root volume (Not encrypted)
    Review commands

[^7]: Instances (5) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    V
    Find Instance by attribute or tag (case-sensitive)
    < 1 >
    O
    Name _
    A
    Instance ID
    Instance state
    A
    Instance type
    Status check
    Alarm status
    Availability Zone
    4
    Publi
    web
    i-0bae41554bd71cd6d
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    ec2-5
    O
    catalogues
    i-ObOcd17285071ef10
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    ec2-3
    0
    Redis
    i-Obd6534a7c9de7631
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    ec2-5
    0
    user
    i-OdcOf1e9cd2639541
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    ec2-5
    cart
    i-07531202fda935fb4
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    ec2-5
    Select an instance
    X

[^8]: MongoDB
    Add additional tags
    Summary
    Number of instances Info
    Application and OS Images (Amazon Machine Image) Info
    An AMI is a template that contains the software configuration (operating system, application server, and
    Software Image (AMI)
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Centos-8-DevOps-Practice
    below
    ami-03265a0778a880afb
    Q devops-practice
    X
    Virtual server type (instance type)
    t3.medium
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Storage (volumes)
    Centos-8-DevOps-Practice
    1 volume(s) - 10 GiB
    ami-03265a0778a880afb
    Browse more AMIs
    Including AMIs from
    AWS, Marketplace and
    the Community
    Free tier: In your first year includes
    X
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    750 hours of t2.micro (or t3.micro in
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    the Regions in which t2.micro is
    AMIs
    04T17:05:56.00
    unavailable) instance usage on free
    OZ
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Review commands
    Instance type
    13.medium
    Family: t3 2 vCPU 4 GiB Memory Current generation: true
    All generations
    On-Demand SUSE base pricing: 0.0979 USD per Hour
    On-Demand Windows base pricing: 0.06 USD per Hour
    Compare instance types

[^9]: Key pair name - required
    1
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    Software Image (AMI)
    Centos-8-DevOps-Practice
    Network settings Info
    Edit
    ami-03265a0778a880afb
    Virtual server type (instance type)
    Network Info
    t3.medium
    vpc-0817 cae8968304c06
    Firewall (security group)
    Subnet Info
    SG_Allow_All
    No preference (Default subnet in any availability zone)
    Storage (volumes)
    Auto-assign public IP Info
    1 volume(s) - 10 GiB
    Enable
    Firewall (security groups) Info
    Free tier: In your first year includes
    X
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    750 hours of t2.micro (or t3.micro in
    instance.
    the Regions in which t2.micro is
    Create security group
    O Select existing security group
    unavailable) instance usage on free
    tier AMIs per month, 30 GiB of EBS
    Common security groups Info
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    Select security groups
    Compare security
    to the internet.
    SG_Allow_All sg-Oc9db47e9b4d484b6 X
    group rules
    VPC: vpc-0817cae8968304c06
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    Cancel
    Launch instance
    Review commands
    Configure storage Info
    Advanced

[^10]: Instances (6) Info
    G
    Connect
    Instance state
    Actions V
    Launch instances
    Find Instance by attribute or tag (case-sensitive)
    <
    >
    Name _
    Instance ID
    Instance state
    V
    Instance type
    V
    Status check
    Alarm status
    Availability Zone
    Publi
    web
    i-0bae41554bd71cd6d
    Running
    t2.micro
    2/2 checks passed View alarms +
    us-east-1d
    ec2-5
    catalogues
    i-0bOcd 17285071ef10
    Running
    t2.micro
    2/2 checks passed View alarms +
    us-east-1d
    ec2-3
    Redis
    i-Obd6534a7c9de7631
    Running
    t2.micro
    2/2 checks passed View alarms +
    us-east-1d
    ec2-5
    user
    i-0dcOf1e9cd2639541
    Running
    t2.micro
    2/2 checks passed View alarms +
    us-east-1d
    ec2-5
    cart
    i-07531202fda935fb4
    Running
    t2.micro
    2/2 checks passed View alarms +
    us-east-1d
    ec2-5
    MongoDB
    i-0b483ecc3f5d05960
    Running
    t3.medium
    Initializing
    View alarms +
    us-east-1a
    ec2-5

[^11]: MongoDB
    . Developer has chosen the database MongoDB.
    . Hence, we are trying to install it up and configure it.
    NOTE: Versions of the DB Software you will get context from the developer, Meaning we need to check with developer. Developer has
    shared the version information as MongoDB-4.x

[^12]: \[ centos@ip-172-31-40-148 \~ \]$ sudo su
    54 . 86. 43.111 \| 172. 31. 40.148 \| t3.medium \| null
    \[ root@ip-172-31-40-148 \~ \]# vim /etc/yum. repos . d/mongo . repo
    54 . 86. 43.111 \| 172. 31. 40.148 \| t3.medium \| null
    \[ root@ip-172-31-40-148 \~ \]# cat /etc/yum. repos . d/mongo . repo
    \[mongodb-org-4 . 2\]
    name=MongoDB Repository
    baseurl=https : / /repo . mongodb. org/yum/redhat/$releasever/mongodb-org/4 .2/x86_64/
    gpgcheck=0
    enabled=1

[^13]: \[ root@ip-172-31-40-148 \~ \]# dnf install mongodb-org -y
    Centos Stream 8 - AppStream
    46 MB/S
    I
    34 MB
    00:00
    Centos Stream 8 -
    BaseOS
    47 MB/S
    55 MB
    00 : 01
    Centos Stream 8
    Extras
    81 kB/s
    18 KB
    00: 00
    Centos Stream 8
    Extras common packages
    88 kB/s \|
    6.9 KB
    00:00
    Extra Packages for Enterprise Linux 8 - x86 64
    42 MB/s
    I
    16 MB
    00:00

[^14]: \[ root@ip-172-31-40-148 \~ \]# systemctl enable mongod
    54 . 86. 43.111 \| 172. 31. 40.148 \| t3. medium \| null
    \[ root@ip-172-31-40-148 \~ \]# systemctl start mongod
    54 . 86. 43.111 \| 172 . 31. 40.148 \| t3.medium \| null
    \[ root@ip-172-31-40-148 \~ \]# systemctl status mongod
    mongod . service - MongoDB Database Server
    Loaded: loaded (/usr/lib/systemd/system/mongod. service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 11:14:09 UTC; 7s ago
    Docs: https : / /docs . mongodb . org/manual
    Process: 5224 ExecStart=/usr/bin/mongod $OPTIONS (code=exited, status=0/SUCCESS)
    Process: 5223 ExecStartPre=/usr/bin/chmod 0755 /var/run/mongodb (code=exited, status=0/SUCCE

[^15]: \[ root@ip-172-31-40-148 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 127 . 0 . 0. 1:27017 -
    0.0.0.0:\*
    LISTEN
    5227/mongod -
    tcp
    0
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    812/sshd
    tcp6
    0 :::111
    LISTEN
    OO
    1/systemd
    top6
    : : :22
    LISTEN
    812/sshd

[^16]: Usually MongoDB opens the port only to localhost(127.0.0.1), meaning this service can be accessed by the application that is hosted on this
    server only. However, we need to access this service to be accessed by another server(remote server), So we need to change the config
    accordingly.
    Update listen address from 127.0.0.1 to 0.0.0.0 in /etc/mongod.conf
    You can edit file by using

[^17]: # network interfaces
    net:
    port: 27017
    bindIp: 0.0.0.0 # Enter 0.0.0.0, :: to bind to all IPV4 and IPV6 addresses or, alternatively, use the n
    et. bindIpAll setting.

[^18]: \[ root@ip-172-31-40-148 \~ \]# systemctl restart mongod
    54 . 86. 43.111 \| 172 . 31 . 40.148 \| t3.medium \| null
    \[ root@ip-172-31-40-148 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    top
    O
    0 0.0.0.0:27017
    0.0.0.0:\*
    LISTEN
    5296/mongod
    top
    0
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0. 0.0.0:22
    0.0.0.0:\*
    LISTEN
    812/sshd
    tcp6
    0 : : :111
    LISTEN
    1/systemd
    tcp6
    0 : : :22
    LISTEN
    812/sshd

[^19]: MongoDB
    i-0b483ecc3f5d05960
    Running
    t3.medium
    Initializing
    View alarms +
    us-east- 1a
    ec2-5
    Instance: i-0b483ecc3f5d05960 (MongoDB)
    X
    Details
    Status and alarms New
    Monitoring
    Security
    Networking
    Storage
    Tags
    Private IPV4 address cop
    Instance summary Info
    ied
    Instance ID
    Public IPv4 address
    7 i-0b483ecc3f5d05960 (MongoDB)
    54.86.43.111 \|open address \[
    172.31.40.148
    IPv6 address
    Instance state
    Public IPV4 DNS

[^20]: Route 53
    X
    Route 53 > Dashboard
    Route 53 Dashboard Info
    Dashboard
    Hosted zones
    Health checks
    DNS management
    Traffic management
    Availability monitoring
    Domain registration
    A visual tool that lets you easily create
    Health checks monitor your applications
    A domain is the name, such
    IP-based routing
    1
    policies for multiple endpoints in
    and web resources, and direct DNS
    example.com, that your users
    CIDR collections
    Hosted zone
    complex configurations.
    queries to healthy resources.
    access your application.
    Create policy
    Create health check
    Register domain
    Traffic flow
    Traffic policies

[^21]: Route 53 > Hosted zones
    Hosted zones (1)
    C
    View details
    Edit
    Delete
    Create hosted zone
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    Q Filter records by property or value
    <
    1 >
    Hosted zone name
    v Type
    Created by
    4
    Record count
    Description
    Hosted zon...
    chowdarychilukuri.in
    Public
    Route 53
    3
    ZO208414XXQ...

[^22]: Create record Info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    mongodb
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.40.148
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    1
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^23]: Create record Info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    catalogue
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.17.148
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    7
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^24]: Create record Info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    subdomain
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    52.90.166.6
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    1
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^25]: Create record info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    redis
    .chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.20.245
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    7
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^26]: Create record Info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    user
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.31.184
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    7
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^27]: Create record info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    cart
    .chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.21.202
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    7
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^28]: Create record info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name
    Info
    Record type Info
    mysql
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.40.170
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    7
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^29]: Create record info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    shipping
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value In
    172.31.47.239
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^30]: Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    rabbitmq
    .chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    Alias
    Value Info
    172.31.20.90
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    7
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^31]: Create record info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    payment
    .chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.31.198
    Enter multiple values on separate lines.
    TTL (seconds) Info
    Routing policy Info
    1
    1m
    1h
    1d
    Simple routing
    Recommended values: 60 to 172800 (two days)
    Add another record
    Cancel
    Create records

[^32]: Records (12) Info
    C
    Delete record
    Import zone file
    Create record
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    O Filter records by property or value
    Type
    Routing policy
    Alias
    1
    >
    Record name
    Type
    Routin...
    Differ... > Alias
    Value/Route traffic to
    TTL (S...
    Health ...
    chowdarychilukuri.in
    A
    Simple
    No
    3.95.60.91
    cart.chowdarychilukuri.in
    A
    Simple
    No
    172.31.21.202
    catalogue.chowdarychilukuri.in
    A
    Simple
    No
    172.31.17.148
    mongodb.chowdarychilukuri.in
    A
    Simple
    No
    172.31.39.248
    mysql.chowdarychilukuri.in
    A
    Simple
    No
    172.31.39.87
    payment.chowdarychilukuri.in
    A
    Simple
    No
    172.31.31.198
    rabbitmq.chowdarychilukuri.in
    A
    Simple
    No
    172.31.20.90
    redis.chowdarychilukuri.in
    A
    Simple
    No
    172.31.20.245
    shipping.chowdarychilukuri.in
    A
    Simple
    No
    172.31.47.162
    user.chowdarychilukuri.in
    A
    Simple
    No
    172.31.31.184

[^33]: Catalogue
    Catalogue is a microservice that is responsible for serving the list of products that displays in roboshop application.
    Developer has chosen Nodels, Check with developer which version of NodeJS is needed. Developer has set a context that it can work with
    NodeJS > 18
    Install NodeJS, By default NodeJS 10 is available, We would like to enable 18 version and install list.

[^34]: \[ root@ip-172-31-17-148 \~ \]# anf module disable nodejs -y
    Last metadata expiration check: 0:54:03 ago on Thu 07 Dec 2023 10:52:55 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Disabling modules:
    nodejs
    Transaction Summary
    Complete!
    3. 92. 56.19 \| 172. 31.17.148 \| t2.micro \| null
    \[ rootdip-172-31-17-148 \~ \]# anf module enable nodejs: 18 -y
    Last metadata expiration check: 0:54:20 ago on Thu 07 Dec 2023 10:52:55 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Enabling module streams:

[^35]: Configure the application.
    Our application developed by the developer of our company and it is not having any RPM software just like other softwares. So we need to
    configure every step manually

[^36]: \[ root@ip-172-31-17-148 \~ \]# anf install nodejs -y
    Last metadata expiration check: 0:57:03 ago on Thu 07 Dec 2023 10:52:55 AM UTC.
    Dependencies resolved.
    Package
    Arch
    Version
    R
    Installing:
    nodejs
    x86 64
    1:18.9.1-1 . module e18 . 7. 0+1220+0be9752c
    a
    Installing weak dependencies:
    nodejs-docs
    noarch
    1:18.9.1-1 . module e18 . 7. 0+1220+0be9752c
    a
    nodejs-full-i18n
    x86 64
    1 :18.9.1-1 . module e18 . 7. 0+1220+0be9752c
    a
    nom
    x86 64
    1:8.19. 1-1. 18. 9. 1. 1. module e18 . 7. 0+1220+0be9752c
    a
    Transaction Summary
    Install 4 Packages

[^37]: Configure the application.
    Our application developed by the developer of our company and it is not having any RPM software just like other softwares. So we need to
    configure every step manually

[^38]: User roboshop is a function / daemon user to run the application. Apart from that we don't use this user to login to server.
    Also, username roboshop has been picked because it more suits to our project name.
    We keep application in one standard location. This is a usual practice that runs in the organization.

[^39]: \[ root@ip-172-31-17-148 \~ \]# useradd roboshop
    3. 92. 56.19 \| 172.31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 \~ 1#

[^40]: 3. 92 . 56.19 \| 172. 31.17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 \~ \]# mkdir /app

[^41]: \[ root@ip-172-31-17-148 \~ \]# cd /
    3. 92. 56.19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 / \]# ls -1
    total 20
    drwxr-xr-x
    2 root root
    6 Dec 7 11:52 app
    lrwxrwxrwx .
    1 root root
    7 Jun 22 2021 bin
    -> usr/bin
    dr-xr-xr-x.
    6 root root 4096 Dec
    7 10:38 boot
    drwxr-xr-x
    18 root root 2640 Dec 7 10:38 dev
    drwxr-xr-x.
    90 root root 8192 Dec
    7 11:51 etc
    drwxr-xr-x.
    4 root root
    36 Dec
    7 11:51 home
    lrwxrwxrwx.
    1 root root
    7 Jun 22 2021 lib -> usr/lib
    1
    +
    r
    9 Jun
    2021 1ib64
    usr /lib64

[^42]: \[ root@ip-172-31-17-148 / \]# curl -o /tmp/catalogue. zip https: //roboshop-builds . s3. amazonaws . com/catalog
    e . zip
    8 Total
    % Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 3097 100 3097
    0
    0 41293
    0
    41293
    3. 92 . 56.19 \| 172. 31.17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 / \]# cd /tmp
    3. 92 . 56.19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /tmp \]# 1s -1
    total 8
    -rw-r--r--
    1 root root 3097 Dec 7 11:55 catalogue . zip
    -rw-r--r--
    1 root root 222 Dec 7 11:50 idle. out
    drwx-
    3 root root
    17 Dec 7 10:38 systemd-private-a07c2c7b2dd1429580a5cf2c5f06f7e7-chronyd. service
    KNe 7Hu

[^43]: \[ root@ip-172-31-17-148 /tmp \]# cd /app
    3. 92 . 56. 19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# 1s -1
    total 0
    3. 92. 56.19 \| 172. 31.17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# unzip /tmp/catalogue . zip
    Archive: /tmp/catalogue . zip
    inflating: package . json
    creating: schema/
    inflating: schema/catalogue . js
    inflating: server . js
    3. 92. 56.19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# 1s -1
    total 12
    r--
    root root 490 Dec
    2022 package . json
    drwxr-xr-x 2 root root
    26 Dec
    3
    2022 schema
    -rw-r--r-- 1 root root 5336 Mar 27 2023 server. js

[^44]: \[ root@ip-172-31-28-155 /app \]# cat package . json
    "name": "catalogue",
    "version": "1.0.0"
    "description": "product catalogue REST API"
    "main": "server. js",
    "scripts": {
    "test": "echo \\"Error: no test specified\\" & & exit 1"
    "author": "SteveW"
    "license": "Apache-2 . 0"
    "dependencies": {
    "body-parser": "^1.18.1
    "express" : "^4.15.4"
    "mongodb" : "^3.5.3"
    "pino": "^5.10.8",
    "express-pino-logger" : "^4.0.0"
    "pino-pretty": "^2.5. 0"
    "@instana/collector": "^1.98.1"

[^45]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies.

[^46]: \[ root@ip-172-31-17-148 /app \]# npm install
    nom WARN deprecated express-pino-logger@4.0.0: use pino-http instead
    added 178 packages, and audited 179 packages in 14s
    13 packages are looking for funding
    run npm fund for details
    4 moderate severity vulnerabilities

[^47]: \[ root@ip-172-31-17-148 /app \]# 1s -1
    total 152
    drwxr-xr-x 163 root root
    8192 Dec 7 11:59 node modules
    -rw-r--r--
    1 root root
    490 Dec
    1 2022 package . json
    rw-r--r--
    1 root root 127491 Dec
    7 11:59 package-lock . json
    drwxr-xr-x
    2 root root
    26 Dec
    3 2022 schema
    -rw-r--r--
    1 root root
    5336 Mar 27 2023 server . js

[^48]: We need to setup a new service in systemd so systemctl can manage this service
    Setup SystemD Catalogue Service

[^49]: \[ rootdip-172-31-17-148 /app \]# vim /etc/systemd/system/catalogue . service
    3. 92 . 56. 19 \| 172. 31.17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# cat /etc/systemd/system/catalogue . service
    \[Unit\]
    Description = Catalogue Service
    \[Service\]
    User=roboshop
    Environment=MONGO=true
    Environment=MONGO URL="mongodb: / /mongodb . chowdarychilukuri . in : 27017/catalogue"
    ExecStart=/bin/node /app/server . js
    SyslogIdentifier=catalogue
    \[Install \]
    WantedBy=multi-user . target

[^50]: \[ root@ip-172-31-25-200 /app \]# nslookup mongodb . joindevops . online
    Server :
    172 . 31 . 0.2
    Address :
    172 . 31 . 0. 2#53
    Non-authoritative answer:
    Name :
    mongodb . joindevops . online
    Address: 172 . 31 . 41 . 42
    54 . 226. 50.14 \| 172.31.25.200 \| t2.micro \| null
    \[ root@ip-172-31-25-200 /app \]#

[^51]: \[ root@ip-172-31-17-148 /app \]# systemctl daemon-reload

[^52]: \[ rootdip-172-31-17-148 /app \]# systemctl enable catalogue
    Created symlink /etc/systemd/system/multi-user . target. wants/catalogue . service - /etc/systemd/system/catal
    ogue . service.
    3. 92 . 56. 19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ rootdip-172-31-17-148 /app \]# systemctl start catalogue
    3. 92. 56.19 \| 172. 31. 17. 148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# systemctl status catalogue
    catalogue . service - Catalogue Service
    Loaded: loaded (/etc/systemd/system/catalogue . service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 12:07:10 UTC; 9s ago
    Main PID: 17059 (node)
    Tasks: 11 (limit: 4440)

[^53]: . For the application to work fully functional we need to load schema to the Database.
    . Schemas are usually part of application code and developer will provide them as part of development.
    We need to load the schema. To load schema we need to install mongodb client.
    To have it installed we can setup MongoDB repo and install mongodb-client

[^54]: Client
    MongoDB Server

[^55]: \[ root@ip-172-31-17-148 /app \]# vim /etc/yum. repos . d/mongo . repo
    3. 92. 56. 19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# cat /etc/yum. repos . d/mongo . repo
    \[mongodb-org-4 . 2\]
    name=MongoDB Repository
    baseurl=https : / /repo . mongodb . org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    gpgcheck=0
    enabled=1

[^56]: \[ root@ip-172-31-17-148 /app \]# dnf install mongodb-org-shell -y
    MongoDB Repository
    394 kB/s \| 42 kB
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Installing :
    mongodb-org-shell
    x86 64
    4.2.25-1. e18
    mongodb-org-4 . 2
    Transaction Summary
    Install 1 Package

[^57]: \[ root@ip-172-31-17-148 /app \]# mongo --host mongodb . chowdarychilukuri . in </app/schema/catalogue . js
    MongoDB shell version v4 .2.25
    connecting to: mongodb: / /mongodb . chowdarychilukuri . in: 27017/?compressors=disabled&gssapiServiceName=mong
    db
    Implicit session: session { "id" : UUID ("57385e9b-6ac2-4d63-a6c6-94059ec2247c") }
    MongoDB server version: 4.2.25
    catalogue
    {
    "acknowledged" : true,
    "insertedIds" : \[
    ObjectId("6571b89fcf503a6b87069bc4") ,
    ObjectId ("6571b89fcf503a6b87069bc5") ,
    ObjectId ("6571b89fcf503a6b87069bc6") ,
    ObjectId ("6571b89fcf503a6b87069bc7") ,
    ObjectId ("6571b89fcf503a6b87069bc8") ,
    ObjectId ("6571b89fcf503a6b87069bc9") ,
    ObjectId ("6571b89fcf503a6b87069bca") ,
    ObjectId ("6571b89fcf503a6b87069bcb") ,
    ObjectId ("6571b89fcf503a6b87069bcc") ,
    ObjectId ("6571b89fcf503a6b87069bcd") ,
    ObjectId ("6571b89fcf503a6b87069bce")
    "createdCollectionAutomatically"
    false

[^58]: \[ root@ip-172-31-17-148 /app \]# systemctl restart catalogue
    3. 92. 56.19 \| 172. 31. 17.148 \| t2.micro \| null
    \[ root@ip-172-31-17-148 /app \]# systemctl status catalogue
    catalogue . service - Catalogue Service
    Loaded: loaded (/etc/systemd/system/catalogue . service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 12:26:10 UTC; 2s ago
    Main PID: 17515 (node)
    Tasks: 11 (limit: 4440)
    Memory : 32.2M
    CGroup: /system . slice/catalogue . service
    L17515 /bin/node /app/server .js
    Dec 07 12:26:10 ip-172-31-17-148. ec2. internal systemd \[1\]: catalogue . service: Succeeded.
    Dec 07 12:26:10 ip-172-31-17-148.ec2. internal systemd \[1\]: Stopped Catalogue Service.
    Dec 07 12:26:10 ip-172-31-17-148. ec2 . internal systemd \[1\]: Started Catalogue Service.

[^59]: \[ root@ip-172-31-17-148 /app \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    845/sshd
    tcp6
    Ooooo
    0 :: :111
    LISTEN
    1/systemd
    tcp6
    0 : : : 8080
    LISTEN
    17515/node
    tcp6
    0 : : :22
    LISTEN
    845/sshd

[^60]: 01-WEB
    . The Web/Frontend is the service in RoboShop to serve the web content over Nginx.
    . This will have the web page for the web application.
    . Developer has chosen Nginx as a web server and thus we will install Nginx Web Server.

[^61]: \[ centos@ip-172-31-17-49 \~ \]$ sudo su
    52 . 90. 166.6 \| 172. 31.17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 \~ \]# anf install nginx -y
    Last metadata expiration check: 0:55:18 ago on Thu 07 Dec 2023 11:39:37 AM UTC.
    Dependencies resolved.
    Package
    Arch
    Version
    Repository
    Si
    Installing:
    nginx
    x86 64
    1:1. 14.1-9. module e18 . 0. 0+1060+3ab382d3
    appstream
    570
    Installing dependencies:
    dejavu-fonts-common
    noarch
    2. 35-7.e18
    baseos
    74
    dejavu-sans-fonts
    noarch
    2.35-7. e18
    baseos
    1 . 6
    fontconfig
    x86 64
    2. 13.1-4.e18
    baseos
    274

[^62]: \[ root@ip-172-31-17-49 \~ \]# systemctl enable nginx
    Created symlink /etc/systemd/system/multi-user . target. wants/nginx. service - /usr/lib/systemd/system/ngi
    . service.
    52 . 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 \~ \]# systemctl start nginx
    52. 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[
    root@ip-172-31-17-49 \~ \]# systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx . service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 12:35:56 UTC; 10s ago
    Process: 16697 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 16693 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)

[^63]: \[ root@ip-172-31-17-49 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID /Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0 :80
    0.0.0.0:\*
    LISTEN
    16699/nginx: master
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    833/sshd
    OOOooo
    tcp6
    0 : : :111
    : : .\*
    LISTEN
    1/systemd
    tcp6
    : : :80
    LISTEN
    16699/nginx: master
    tcp6
    0
    : : :22
    LISTEN
    833/sshd

[^64]: Not secure chowdarychilukuri.in
    Al
    Welcome to nginx on Red Hat Enterprise Linux!
    This page is used to test the proper operation of the nginx HTTP server after it has been installed. If you can read this page, it means that the web server installed at this site is working properly.
    Website Administrator
    This is the default index. html page that is distributed with nginx on Red Hat Enterprise Linux. It is located in /usr/share/nginx/html.
    You should now put your content in a location of your choice and edit the root configuration directive in the nginx configuration file /etc/nginx/nginx. conf.
    For information on Red Hat Enterprise Linux, please visit the Red Hat, Inc. website. The documentation for Red Hat Enterprise Linux is available on the Red Hat, Inc. website.
    NGINX
    POWERED BY
    redhat.

[^65]: \[ root@ip-172-31-19-108 \~ \]# cd /etc/nginx/
    3. 85. 61. 63 \| 172. 31.19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /etc/nginx \]# vim nginx. conf
    For more information on configuration, see:
    \*
    Official English Documentation: http: //nginx.org/en/docs/
    \* Official Russian Documentation: http: //nginx. org/ru/docs/
    user nginx;
    worker processes auto;
    error log /var/log/nginx/error .log;
    pid /run/nginx .pid;
    # Load dynamic modules. See /usr/share/doc/nginx/README . dynamic.
    include /usr/share/nginx/modules/\* . conf ;

[^66]: \[ root@ip-172-31-17-49 \~ \]# cd /usr/share/nginx/html/
    52 . 90 . 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# 1s -1
    total 24
    -rw-r--r--
    1 root root 3971 Dec 21 2021 404.html
    -rw-r--r-- 1 root root 4020 Dec 21 2021 50x.html
    -rw-r--r-- 1 root root 4057 Dec 21
    2021 index . html
    -rw-r--r-- 1 root root 368 Dec 21
    2021 nginx-logo . png
    -rw-r--r-- 1 root root 4148 Dec 21 2021 poweredby . png
    52 . 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# rm -rf /usr/share/nginx/html/\*
    52 . 90 . 166.6 \| 172 . 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# 1s -1
    total 0
    52 . 90 .166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# \|

[^67]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# curl -o /tmp/web. zip https: //roboshop-builds . s3 . amazonaws
    com/web . zip
    8 Total
    8 Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 1101k 100 1101k
    0
    0
    8102k
    0
    -- : --:-
    - : -- : -
    -- : -- : --
    8102k
    52 . 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# cd /tmp/
    52 . 90 . 166.6 \| 172. 31.17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /tmp \]# 1s -1
    total 1108
    -rw-r--r--
    1 root root
    223 Dec 7 12:40 idle . out
    drwx--
    3 root root
    17 Dec
    7 10:38 systemd-private-0a29767b9437498689c97bc82c62663c-chronyd. serv
    ice-ejlTIJ
    drwx-
    3 root root
    17 Dec 7 12:35 systemd-private-0a29767b9437498689c97bc82c62663c-nginx . servic
    e-1VTBV1
    -rw-r--r-- 1 root root 1128410 Dec 7 12:42 web . zip
    52 . 90. 166.6 \| 172. 31.17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /tmp \]#

[^68]: \[ root@ip-172-31-17-49 /tmp \]# cd /usr/share/nginx/html
    52 . 90 . 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# 1s -1
    total 0

[^69]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# unzip /tmp/web . zip
    Archive: /tmp/web . zip
    inflating: cart. html
    creating: css/
    inflating: css/auto-complete . css
    inflating: css/style . css
    inflating: empty . html
    inflating: eum. html
    creating: images/
    inflating: images/PB-1 . jpg
    inflating: images/EVE-1. ipg

[^70]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# ls -1
    total 44
    -rw-r--r-- 1 root root 1335 Dec
    1 2022 cart. html
    drwxr-xr-x 2 root root
    48 Dec
    2
    2022 css
    -rw-r--r-- 1 root root
    77 Dec
    1 2022 empty . html
    -rw-r--r-- 1 root root 441 Dec
    1
    2022 eum. html
    drwxr-xr-x 2 root root 4096 Dec
    2
    2022 images
    -rw-r--r-- 1 root root 2542 Dec
    1
    2022 index. html
    drwxr-xr-x 2 root root
    51 Dec
    2
    2022 js
    -rw-r--r-- 1 root root 2169 Dec
    1
    2022 login . html
    drwxr-xr-x 2 root root
    70 Dec
    2
    2022 media
    -rw-r--r-- 1 root root 1328 Dec
    1
    2022 payment . html
    rw-r
    --r-- 1 root root 1371 Dec 1
    2022 product. html
    -rw-r--r-- 1 root root 559 Dec
    1 2022 search. html
    rw-
    r-- 1 root root 843 Dec
    1 2022 shipping . html
    -rw-r--r-- 1 root root 1182 Dec 1 2022 splash. html

[^71]: C
    Not secure chowdarychilukuri.in
    Stan's Robot Shop
    Search
    Login / Register
    Welcome to Stan's Robot Shop
    Cart
    STAN
    Empty
    Here you will find all of Stan's friends. Have a browse around and
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    has been built using various technologies:
    AngularJS (1.x)
    Nginx
    NodeJS
    Java
    Python
    Golang
    PHP (Apache)
    : MongoDB

[^72]: HotStar US
    VPN
    O
    OC
    US
    India

[^73]: Intemet
    Cisco VPN
    Access Restriction
    Traffic monitoring
    Office Network

[^74]: App
    DB
    Load Balancer
    Web
    Client
    fb n/w

[^75]: MongoDB catalogue WEB
    proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html;
    try_files $uri /images/placeholder . jpg;
    F
    location /api/catalogue/ { proxy_pass http://catalogue. chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http://localhost: 8080/; }
    location /api/cart/ { proxy_pass http://localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: //localhost: 8080/; }
    location /api/payment/ { proxy_pass http://localhost: 8080/; }
    location /health {
    stub status on;
    access_log off;

[^76]: \[ rootdip-172-31-17-49 /usr/share/nginx/html \]# cat /etc/nginx/default.d/roboshop. conf
    proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html;
    try_files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: //catalogue. chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http: / /localhost: 8080/; }
    location /api/cart/ { proxy_pass http: //localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: / /localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access_log off;

[^77]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# systemctl restart nginx
    52 . 90.166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 12:57:01 UTC; 9s ago
    Process: 16905 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 16902 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process :
    16901 ExecStartPre=/usr/bin/rm -f /run/nginx. pid (code=exited, status=0/SUCCESS)

[^78]: C
    Not secure \| chowdarychilukuri.in/product/HHGTTG
    Stan's Robot Shop
    Search
    Login / Register
    Cart
    Marvin
    STAN
    Empty
    Categories
    . Artificial
    Intelligence
    o HAL
    Positronic
    Brain
    Stan
    . Robot
    o C3PO
    Eve
    K9
    o Kryten
    o Marvin
    Mr Data
    R2D2
    o Robbie
    o Stan
    Rating No votes yet. Vote now.
    Marvin, your paranoid android. Brain the
    size of a planet
    Price E42.00 Quantity 1
    Add to cart

[^79]: apps --> redis
    -->
    DB

[^80]: Redis is used for in-memory data storage(Caching) and allows users to access the data of database over API.
    Redis is offering the repo file as a rpm. Lets install it

[^81]: 52 . 201 . 230.153 \| 172.31.20.245 \| t2.micro \| null
    \[ centos(ip-172-31-20-245 \~ \]$ sudo su -
    52 . 201 . 230.153 \| 172. 31.20.245 \| t2.micro \| null
    \[ root@ip-172-31-20-245 \~ \]# anf install https: / /rpms . remirepo . net/enterprise/remi-release-8.rpm -y
    Last metadata expiration check: 1:34:51 ago on Thu 07 Dec 2023 11:39:25 AM UTC.
    remi-release-8 . rom
    67 kB/s \| 32 kB
    00:00
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Si
    Installing :
    remi-release
    noarch
    8.8-1. e18. remi
    @commandline
    32

[^82]: \[ root@ip-172-31-20-245 \~ \]# dnf module enable redis : remi-6.2 -y
    Remi's Modular repository for Enterprise Linux 8 - x86 64
    971 B/s \| 833 B
    00: 00
    Remi's Modular repository for Enterprise Linux 8 - x86 64
    3.0 MB/s \| 3.1 KB
    00: 00
    Importing GPG key 0x5F11735A:
    Userid
    "Remi's RPM repository <remi@remirepo.net>"
    Fingerprint: 6838 FEA7 231F 87F5 2B9C A9D8 5550 9759 5F11 735A
    From
    /etc/pki/rpm-gpg/RPM-GPG-KEY-remi . e18

[^83]: \[ root@ip-172-31-20-245 \~ \]# dnf install redis -y
    Last metadata expiration check: 0:00:48 ago on Thu 07 Dec 2023 01:19:09 PM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Installing:
    redis
    x86 64
    6. 2. 14-1. e18 . remi
    remi-modular
    Transaction Summary
    Install 1 Package
    Total download size: 1.2 M
    Installed size: 4.3 M

[^84]: Usually Redis opens the port only to localhost(127.0.0.1), meaning this service can be accessed by the application that is hosted on this server
    only. However, we need to access this service to be accessed by another server, So we need to change the config accordingly.
    Update listen address from 127.0.0.1 to 0.0.0.0 in /etc/redis.conf & /etc/redis/redis.conf

[^85]: MongoDB catalogue WEB REDIS
    #
    addresses that does not correspond to any network interfece. Addresses that
    are already in use will always fail, and unsupported protocols will always BE
    silently skipped.
    #
    Examples :
    bind 192. 168.1. 100 10 .0 .0.1
    # listens on two specific IPV4 addresses
    bind 0.0.0.0 : :1
    # listens on loopback IPV4 and IPV6
    #
    bind \* -: : \*
    # like the default, all available interfaces
    #
    \~\~\~ WARNING \~\~\~ If the computer running Redis is directly exposed to the
    internet, binding to all the interfaces is dangerous and will expose the
    instance to everybody on the internet. So by default we uncomment the
    following bind directive, that will force Redis to listen only on the
    IPv4 and IPv6 (if available) loopback interface addresses (this means Redis
    will only be able to accept client connections from the same host that it is
    running on) .
    #
    IF YOU ARE SURE YOU WANT YOUR INSTANCE TO LISTEN TO ALL THE INTERFACES
    JUST COMMENT OUT THE FOLLOWING LINE.
    NN
    bind 0.0.0.0
    -: :1
    Protected mode is a layer of security protection, in order to avoid that

[^86]: \[ root@ip-172-31-20-245 \~ \]# systemctl enable redis
    Created symlink /etc/systemd/system/multi-user . target. wants/redis. service - /usr/lib/systemd/system/red
    . service .
    52 . 201 . 230. 153 \| 172. 31.20.245 \| t2.micro \| null
    \[ root@ip-172-31-20-245 \~ \]# systemctl start redis
    52 . 201 .230.153 \| 172. 31.20.245 \| t2.micro \| null
    \[ root@ip-172-31-20-245 \~ \]# systemctl status redis
    redis . service - Redis persistent key-value database
    Loaded: loaded (/usr/lib/systemd/system/redis . service; enabled; vendor preset: disabled)
    Drop-In: /etc/systemd/system/redis . service.d
    Llimit. conf
    Active: active (running) since Thu 2023-12-07 13:26:58 UTC; 6s ago
    Main PID: 16951 (redis-server)
    Status: "Ready to accept connections"

[^87]: \[ root@ip-172-31-20-245 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0: 6379
    0.0.0.0:\*
    LISTEN
    17059/redis-server
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    834/sshd
    OOOOOO
    tcp6
    0 : :1:6379
    :::
    LISTEN
    17059/redis-server
    tcp6
    0 :: :111
    LISTEN
    1/systemd
    tcp6
    0 : : :22
    LISTEN
    834/sshd

[^88]: User
    User is a microservice that is responsible for User Logins and Registrations Service in RobotShop e-commerce portal.
    Developer has chosen Nodels, Check with developer which version of NodeJS is needed. Developer has set a context that it can work with
    NodeJS > 18
    Install NodeJS, By default NodeJS 10 is available, We would like to enable 18 version and install list.
    you can list modules by using anf module list

[^89]: \[ centosip-172-31-31-184 \~ \]$ sudo su
    54 . 204 . 51.210 \| 172. 31. 31.184 \| t2.micro \| null
    \[ rootdip-172-31-31-184 \~ \]# dnf module disable nodejs -y
    Last metadata expiration check: 2:47:46 ago on Thu 07 Dec 2023 10:54:05 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Disabling modules:
    nodejs
    Transaction Summary
    Complete!
    54 . 204 . 51.210 \| 172. 31. 31.184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 \~ \]# anf module enable nodejs:18 -y
    Last metadata expiration check: 2:47:58 ago on Thu 07 Dec 2023 10:54:05 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository

[^90]: \[ root@ip-172-31-31-184 \~ \]# anf install nodejs -y
    Last metadata expiration check: 2:49:23 ago on Thu 07 Dec 2023 10:54:05 AM UTC.
    Dependencies resolved.
    Package
    Arch
    Version
    Installing :
    nodejs
    x86 64
    1:18 .9.1-1 . module e18 . 7. 0+1220+0be9752c
    Installing weak dependencies:
    nodejs-docs
    noarch
    1:18.9.1-1. module e18 . 7. 0+1220+0be9752c
    nodejs-full-i18n
    x86 64
    1:18 .9.1-1 . module e18 . 7. 0+1220+0be9752c
    nom
    x86 64
    1:8.19. 1-1. 18. 9.1.1. module e18 . 7. 0+1220+0be9752c

[^91]: \[ root@ip-172-31-31-184 \~ \]# useradd roboshop

[^92]: 54 . 204 . 51.210 \| 172. 31. 31.184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 \~ \]# mkdir /app

[^93]: \[ root@ip-172-31-31-184 \~ \]# mkdir /app
    54 . 204. 51.210 \| 172. 31. 31. 184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 \~ \]# curl -L -o /tmp/user . zip https: //roboshop-builds . s3 . amazonaws . com/user . zip
    8 Total
    8 Received & Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100
    3150 100 3150
    0
    0
    34615
    0
    34615
    54 . 204 . 51. 210 \| 172. 31. 31. 184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 \~ \]# cd /app
    54 . 204 . 51.210 \| 172. 31. 31. 184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 /app \]# unzip /tmp/user . zip
    Archive: /tmp/user . zip
    inflating: package . json
    creating: schema/
    inflating: schema/user . js
    inflating: server . js

[^94]: \[ root@ip-172-31-31-184 /app \]# 1s -1
    total 16
    -rw-r--r-- 1 root root 497 Dec 1 2022 package . json
    drwxr-xr-x 2 root root
    21 Dec 3 2022 schema
    -rw-r--r-- 1 root root 9152 Mar 27 2023 server. js

[^95]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies.

[^96]: \[ root@ip-172-31-31-184 /app \]# cd /app
    54 . 204 .51.210 \| 172 . 31. 31.184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 /app \]# npm install
    ) : idealTree: semver :
    sill fetch manifest is-bluebird@^1 . 0.2

[^97]: We need to setup a new service in systemd so systemctl can manage this service
    Setup SystemD User Service

[^98]: \[Unit\]
    Description = User Service
    \[Service\]
    User=roboshop
    Environment=MONGO=true
    Environment=REDIS HOST=redis . chowdarychilukuri . in
    Environment-MONGO URL="mongodb : / /mongodb . chowdarychilukuri . in : 27017/users"
    ExecStart=/bin/node /app/server. js
    SyslogIdentifier=user
    \[Install \]
    WantedBy-multi-user . target

[^99]: \[ root@ip-172-31-31-184 /app \]# systemctl daemon-reload
    54 . 204 . 51. 210 \| 172. 31. 31. 184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 /app \]# systemctl enable user
    Created symlink /etc/systemd/system/multi-user . target. wants/user . service - /etc/systemd/system/us
    ce.
    54 . 204 . 51.210 \| 172. 31. 31. 184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 /app \]# systemctl start user

[^100]: \[ root@ip-172-31-31-184 /app \]# systemctl status user
    user . service - User Service
    Loaded: loaded (/etc/systemd/system/user . service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 13:56:41 UTC; 55s ago
    Main PID: 17462 (node)
    Tasks: 11 (limit: 4440)
    Memory: 34. 2M
    CGroup: /system. slice/user . service
    L17462 /bin/node /app/server . js

[^101]: For the application to work fully functional we need to load schema to the Database. Then
    NOTE: Schemas are usually part of application code and developer will provide them as part of development.
    We need to load the schema. To load schema we need to install mongodb client.
    To have it installed we can setup MongoDB repo and install mongodb-client

[^102]: \[ rootdip-172-31-31-184 /app \]# vim /etc/yum. repos . d/mongo . repo
    54 . 204 . 51.210 \| 172 . 31. 31. 184 \| t2.micro \| null
    \[ root@ip-172-31-31-184 /app \]# cat /etc/yum. repos .d/mongo . repo
    \[mongodb-org-4 . 2\]
    name=MongODB Repository
    baseurl=https : / /repo . mongodb . org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    gpgcheck=0
    enabled=1

[^103]: \[ root@ip-172-31-31-184 /app \]# dnf install mongodb-org-shell -y
    MongODB Repository
    312 kB/s \| 42 kB
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Installing :
    mongodb-org-shell
    x86 64
    4.2.25-1. e18
    mongodb-org-4 . 2
    Transaction Summary
    Install 1 Package

[^104]: \[ rootdip-172-31-31-184 /app \]# cat /app/schema/user . js
    1/
    Products
    db = db . getSiblingDB ( ' users' ) ;
    db . users . insertMany ( \[
    {name: 'user', password: 'password', email: 'user@me.com' } ,
    {name: 'stan', password: 'bigbrain' , email: 'standinstana. com' },
    {name: 'partner-57', password: 'worktogether', email: 'howdy@partner . com'}
    1) ;
    // unique index on the name
    db . users . createIndex (
    {name : 1} ,
    {unique: true}

[^105]: \[ root@ip-172-31-31-184 /app \]# mongo --host mongodb . chowdarychilukuri . in </app/schema/user . js
    MongoDB shell version v4 .2.25
    connecting to: mongodb: / /mongodb . chowdarychilukuri . in: 27017/?compressors=disabled&gssapiServiceName
    db
    Implicit session: session { "id" : UUID ("02d74479-40e8-4fdb-b103-cb173cb4e9a4") }
    MongoDB server version: 4.2.25
    users
    {
    "acknowledged" : true,
    "insertedIds" : \[
    ObjectId ("6571d14cc30206d100908555") ,
    ObjectId ("6571d14cc30206d100908556") ,
    ObjectId ("6571d14cc30206d100908557")
    "createdCollectionAutomatically" : false,
    "numIndexesBefore" : 1,
    "numIndexesAfter" : 2,
    "ok" : 1
    bye

[^106]: MongoDB catalogue WEB REDIS USER
    proxy_http_version 1.1;
    location /images/ {
    expires 5s ;
    root
    /usr/share/nginx/html ;
    try_files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http:/ /catalogue. chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http: / /user chowdarychilukuri . in: 8080/; }
    location /api/cart/ { proxy_pass http: //localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: / /localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access log off;

[^107]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# vim /etc/nginx/default.d/roboshop. conf
    52 . 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# cat /etc/nginx/default.d/roboshop . conf
    proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: / /catalogue. chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http: //user . chowdarychilukuri . in: 8080/; }
    location /api/cart/ { proxy_pass http: //localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: //localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access log off;

[^108]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# systemctl restart nginx
    52 . 90 .166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx . service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 14:15:11 UTC; 14s ago
    Process: 17304 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    7302
    + Pre
    -Just/sbin/nai
    ited
    0 / STIC

[^109]: \[ root@ip-172-31-31-169 /app \]# cat /app/schema/user . js
    Products
    db = db . getSiblingDB ( ' users' ) ;
    db . users . insertMany ( \[
    (name: 'user', password: 'password' , email: 'user@me. com' ) ,
    {name: 'stan' , password: 'bigbrain', email: 'standinstana. com'),
    {name: 'partner-57', password: 'worktogether' , email: 'howdy@partner . com' }

[^110]: F
    C
    A Not secure \| chowdarychilukuri.in/login
    Stan's Robot Shop
    Login / Register
    Cart
    Empty
    Name
    user
    Categories
    Password
    .......
    . Artificial
    Login
    Intelligence
    . Robot
    Name
    user
    Email
    Password
    ........
    Confirm Password
    Register

[^111]: C
    A
    Not secure \|chowdarychilukuri.in/login
    Stan's Robot Shop
    Login / Register
    Cart
    Greetings user
    Empty
    Email - user@me.com
    Categories
    . Artificial
    Order History
    Intelligence
    Order ID Items Total
    . Robot

[^112]: Not secure \| chowdarychilukuri.in/login
    Stan's Robot Shop
    Login / Register
    Cart
    Empty
    Name
    satyachilukuri
    Categories
    Password
    .........
    . Artificial
    Login
    Intelligence
    . Robot
    Name
    satyachilukuri
    Email
    chowdaryspace@outlook.co
    Password
    .........
    Confirm Password
    .........
    Register
    anonymous-6

[^113]: Not secure \| chowdarychilukuri.in/login
    Stan's Robot Shop
    Login / Register
    Cart
    Greetings satyachilukuri
    Empty
    Categories
    Email - chowdaryspace@outlook.com
    . Artificial
    Order History
    Intelligence
    Order ID Items Total
    . Robot
    satyachilukuri

[^114]: Cart is a microservice that is responsible for Cart Service in RobotShop e-commerce portal.
    Developer has chosen Nodels, Check with developer which version of NodeJS is needed. Developer has set a context that it can work with
    NodeJS > 18
    Install NodeJS, By default NodeJS 10 is available, We would like to enable 18 version and install list.
    you can list modules by using anf module list

[^115]: \[ centosip-172-31-21-202 \~ \]$ sudo su
    -
    54 . 174 . 93.4 \| 172. 31. 21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 \~ \]# anf module disable nodejs -y
    Last metadata expiration check: 3:14:47 ago on Thu 07 Dec 2023 11:25:25 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Disabling modules:
    nodejs
    Transaction Summary
    Complete!
    54 . 174. 93.4 \| 172. 31.21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 \~ \]# anf module enable nodejs : 18 -y
    Last metadata expiration check: 3:15:13 ago on Thu 07 Dec 2023 11:25:25 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository

[^116]: \[ root@ip-172-31-21-202 \~ \]# dnf install nodejs -y
    Last metadata expiration check: 3:16:14 ago on Thu 07 Dec 2023 11:25:25 AM UTC.
    Dependencies resolved.
    Package
    Arch
    Version
    Installing:
    nodejs
    x86 64
    1: 18.9. 1-1 . module e18 . 7. 0+1220+0be9752c
    Installing weak dependencies :
    nodejs-docs
    noarch
    1:18.9. 1-1 . module e18 . 7. 0+1220+0be9752c
    nodejs-full-i18n
    x86 64
    1:18 .9.1-1 . module e18 . 7. 0+1220+0be9752c
    nom
    x86 64
    1:8. 19. 1-1 . 18.9. 1. 1. module e18 . 7. 0+1220+0be9752c
    Transaction Summary

[^117]: \[ root@ip-172-31-21-202 \~ \]# useradd roboshop
    51 171 93
    179 31 21 202

[^118]: \[ root@ip-172-31-21-202 \~ \]# mkdir /app

[^119]: \[ root@ip-172-31-21-202 \~ \]# curl -L -o /tmp/cart. zip https: //roboshop-builds . s3 . amazonaws . com/cart . zip
    8 Total
    % Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 3109 100 3109
    0
    28263
    0
    28263
    54 . 174. 93.4 \| 172. 31.21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 \~ \]# cd /app
    54 . 174 . 93.4 \| 172. 31. 21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]# 1s -1
    total 0
    54 . 174.93.4 \| 172. 31.21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]# unzip /tmp/cart . zip
    Archive: /tmp/cart . zip
    inflating: package . json
    inflating: server . js
    54 . 174 . 93.4 \| 172. 31. 21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]# 1s -1
    total 16
    rw-r--r-- 1 root root
    530 Dec 1 2022 package . json
    -rw-r--r--
    1 root root 11324 Dec
    1
    2022 server . js

[^120]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies.

[^121]: \[ root@ip-172-31-21-202 /app \]# cd /app
    54 . 174. 93.4 \| 172. 31.21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]# npm install
    ) : idealTree: app: timing idealTree: #root Completed in 1981ms

[^122]: We need to setup a new service in systemd so systemctl can manage this service
    Setup SystemD Cart Service

[^123]: \[ root@ip-172-31-21-202 /app \]# vim /etc/systemd/system/cart. service
    54 . 174 . 93.4 \| 172.31.21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]#
    54 . 174 . 93.4 \| 172. 31.21.202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]# cat /etc/systemd/system/cart. service
    \[Unit\]
    Description = Cart Service
    \[Service\]
    User=roboshop
    Environment=REDIS HOST=redis . chowdarychilukuri . in
    Environment=CATALOGUE HOST=catalogue . chowdarychilukuri . in
    Environment=CATALOGUE PORT=8080
    ExecStart=/bin/node /app/server . js
    SyslogIdentifier=cart
    \[Install \]
    WantedBy=multi-user . target

[^124]: \[ root@ip-172-31-21-202 /app \]# systemctl daemon-reload
    54 . 174 . 93.4 \| 172. 31. 21. 202 \| t2.micro \| null
    \[ root@ip-172-31-21-202 /app \]# systemctl enable cart
    Created symlink /etc/systemd/system/multi-user . target. wants/cart. service - /etc/systemd/system/cart. servi
    ce .
    54 . 174. 93.4 \| 172. 31.21.202 \| t2.micro \| null
    \[ rootdip-172-31-21-202 /app \]# systemctl start cart

[^125]: proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html ;
    try_files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: / /catalogue . chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http: //user . chowdarychilukuri . in: 8080/; }
    location /api/cart/ { proxy_pass http: / /cart. chowdarychilukuri . in: 8080/; }
    location /api/shipping/ { proxy_pass http: //localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access_log off;

[^126]: \[ rootdip-172-31-17-49 /usr/share/nginx/html \]# systemctl restart nginx
    52 . 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2023-12-07 14:58:29 UTC; 3s ago
    Process: 17461 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 17458 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0 /SUCCESS)

[^127]: G
    Not secure \| chowdarychilukuri.in/cart
    Stan's Robot Shop
    Login / Register
    Shopping cart for anonymous-14
    Cart
    QTY
    Name Sub Total
    1
    Stan
    E67.00
    E67.00
    Categories
    Inc Tax
    E11.17
    . Artificial
    Total
    E67.00
    Intelligence
    Checkout
    Robot
    o C3PO
    o Eve
    o K9
    o Kryten
    Marvin
    o Mr Data
    o R2D2
    o Robbie
    o Stan
    anonymous-14

[^128]: MYSQL
    Add additional tags
    Summary
    Number of instances Info
    Application and OS Images (Amazon Machine Image) Info
    1
    An AMI is a template that contains the software configuration (operating system, application server, and
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Software Image (AMI)
    below
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    devops-practice
    X
    Virtual server type (instance type)
    t3.medium
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Centos-8-Devops-Practice
    Storage (volumes)
    ami-03265a0778a880afb
    Browse more AMIs
    1 volume(s) - 10 GiB
    Including AMIs from
    AWS, Marketplace and
    the Community
    Free tier: In your first year includes
    X
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    750 hours of t2.micro (or t3.micro in
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    the Regions in which t2.micro is
    AMIs
    04T17:05:56.00
    unavailable) instance usage on free
    OZ
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    Review commands
    +3.medium
    Family: t3 2 vCPU 4 GiB Memory Current generation: true
    All generations

[^129]: Key pair (login) Info
    Number of instances Info
    You can use a key pair to securely connect to your instance. Ensure that you have access to the selected key pair
    7
    before you launch the instance.
    Key pair name - required
    Software Image (AMI)
    Centos-8-DevOps-Practice
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    ami-03265a0778a880afb
    Virtual server type (instance type)
    t3.medium
    Network settings Info
    Edit
    Firewall (security group)
    SG_Allow_All
    Network Info
    vpc-0817cae8968304c06
    Storage (volumes)
    1 volume(s) - 10 GiB
    Subnet Info
    No preference (Default subnet in any availability zone)
    Free tier: In your first year includes
    X
    Auto-assign public IP Info
    750 hours of t2.micro (or t3.micro in
    Enable
    the Regions in which t2.micro is
    unavailable) instance usage on free
    Firewall (security groups) Info
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    tier AMIs per month, 30 GiB of EBS
    instance.
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    Create security group
    Select existing security group
    to the internet.
    Common security groups Info
    Select security groups
    C
    Compare security
    Cancel
    Launch instance
    SG_Allow_All 'sg-0c9db47e9b4d484b6 X
    group rules
    VPC: vpc-0817cae8968304c06
    Review commands
    Security groups that you add or remove here will be added to or removed from all your network interfaces.

[^130]: MySQL
    Developer has chosen the database MySQL. Hence, we are trying to install it up and configure it.
    CentOS-8 Comes with MySQL 8 Version by default, However our application needs MySQL 5.7. So lets disable MySQL 8 version.

[^131]: \[ centos@ip-172-31-40-170 \~ \]$ sudo su -
    54 . 80. 163.5 \| 172. 31. 40.170 \| t3.medium \| null
    \[ root@ip-172-31-40-170 \~ \]# anf module disable mysql -y
    Centos Stream 8 - AppStream
    63 MB/S
    Centos Stream 8 - BaseOS
    29 MB/s
    Centos Stream 8
    -
    Extras
    237 kB/s
    Centos Stream 8 - Extras common packages
    30 kB/s
    I
    Extra Packages for Enterprise Linux 8 - x86 64
    21 MB/S \|
    Dependencies resolved.

[^132]: \[ root@ip-172-31-40-170 \~ \]# vim /etc/yum. repos . d/mysql . repo
    54 . 80.163.5 \| 172 . 31 . 40.170 \| t3.medium \| null
    \[ root@ip-172-31-40-170 \~ \]# cat /etc/yum. repos . d/mysql . repo
    \[mysql \]
    name=MySQL 5. 7 Community Server
    baseurl=http: //repo.mysql . com/yum/mysql-5. 7-community/el/7/$basearch/
    enabled=1
    gpgcheck=0

[^133]: \[ root@ip-172-31-40-170 \~ \]# anf install mysql-community-server -y
    MySQL 5.7 Community Server
    13 M
    Last metadata expiration check: 0:00:02 ago on Thu 07 Dec 2023 03:42:09 PM UTC
    Dependencies resolved.
    Package
    Architecture
    Version
    Installing:
    mysql-community-server
    x86 64
    5. 7 . 44-1. e17
    Installing dependencies :
    libaio
    x86 64
    0. 3. 112-1.e18

[^134]: \[ root@ip-172-31-40-170 \~ \]# systemctl enable mysqld
    54 . 80.163.5 \| 172 . 31. 40.170 \| t3.medium \| null
    \[ root@ip-172-31-40-170 \~ \]# systemctl start mysqld

[^135]: Next, We need to change the default root password in order to start using the database service. Use password RoboShop@1 or any other as
    per your choice.

[^136]: \[ root@ip-172-31-40-170 \~ \]# mysql secure installation
    --set-root-pass RoboShop@1

[^137]: \[ root@ip-172-31-40-170 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID /Program name
    top
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    817/sshd
    tcp6
    OOOOO
    0
    :::3306
    LISTEN
    5338/mysqld
    tcp6
    0
    : ::111
    LISTEN
    1/systemd
    tcp6
    0
    : : :22
    LISTEN
    817/sshd

[^138]: \[ root@ip-172-31-40-170 \~ \]# mysql -uroot -pRoboShop@1
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    Welcome to the MySQL monitor. Commands end with ; or g.
    Your MySQL connection id is 5
    Server version: 5.7.44 MySQL Community Server (GPL)
    Copyright (c) 2000, 2023, Oracle and/or its affiliates.
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners .
    Type 'help; ' or ' \\h' for help. Type ' \\c' to clear the current input statement.
    mysql> exit
    Bye
    54 . 80. 163.5 \| 172. 31. 40.170 \| t3.medium \| null
    \[ root@ip-172-31-40-170 \~ 1# \[\]

[^139]: Shipping
    Add additional tags
    Summary
    Number of instances
    Info
    Application and OS Images (Amazon Machine Image) Info
    An AMI is a template that contains the software configuration (operating system, application server, and
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Software Image (AMI)
    below
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Q devops-practice
    X
    Virtual server type (instance type)
    t3.medium
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Centos-8-Devops-Practice
    Storage (volumes)
    ami-03265a0778a880afb
    Browse more AMIs
    1 volume(s) - 10 GiB
    Including AMIs from
    AWS, Marketplace and
    the Community
    @ Free tier: In your first year includes
    X
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    750 hours of t2.micro (or t3.micro in
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    the Regions in which t2.micro is
    AMIs
    04T17:05:56.00
    unavailable) instance usage on free
    OZ
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    Review commands
    t3.medium
    Family: t3 2 vCPU 4 GiB Memory Current generation: true
    All generations
    On-Demand SUSE base pricing: 0.0979 USD per Hour
    On-Demand Windows base pricing: 0.06 USD per Hour

[^140]: Summary
    Key pair name - required
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    Number of instances Info
    Network settings Info
    Edit
    Software Image (AMI)
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Network Info
    vpc-0817 cae8968304c06
    Virtual server type (instance type)
    t3.medium
    Subnet Info
    No preference (Default subnet in any availability zone)
    Firewall (security group)
    SG_Allow_All
    Auto-assign public IP Info
    Enable
    Storage (volumes)
    Firewall (security groups) Info
    1 volume(s) - 10 GiB
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    Free tier: In your first year includes
    X
    Create security group
    Select existing security group
    750 hours of t2.micro (or t3.micro in
    Common security groups Info
    the Regions in which t2.micro is
    unavailable) instance usage on free
    Select security groups
    tier AMIs per month, 30 GiB of EBS
    G
    Compare security
    storage, 2 million IOs, 1 GB of
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    snapshots, and 100 GB of bandwidth
    VPC: vpc-0817cae8968304c06
    to the internet.
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    Configure storage Info
    Advanced
    Cancel
    Launch instance
    Review commands

[^141]: maven --> automatically maven will install java
    npm install = mvn clean package = it will give a jar file
    java --> compile --> bytecode (. jar file)
    python=nodejs = no need of compile = no bytecode

[^142]: Shipping
    Shipping service is responsible for finding the distance of the package to be shipped and calculate the price based on that.
    Shipping service is written in Java, Hence we need to install Java.
    Maven is a Java Packaging software, Hence we are going to install maven, This indeed takes care of java installation.

[^143]: \[ centos@ip-172-31-47-239 \~ \]$ sudo su
    -
    54 . 165. 59. 178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 \~ \]# dnf install maven -y
    Centos Stream 8 - AppStream
    58 MB/S \| 34 MB
    Centos Stream 8 - BaseOS
    28 MB/S \|
    55 MB
    Centos Stream 8 - Extras
    1.9 kB/s \|
    18 KB
    CentOS Stream 8 - Extras common packages
    459 B/s \| 6.9 kB
    Extra Packages for Enterprise Linux 8 - x86 64
    14 MB/S \| 16 MB
    Dependencies resolved.
    Package
    Arch
    Version
    Repo
    Installing:

[^144]: Configure the application.
    Add application User

[^145]: \[ root@ip-172-31-47-239 \~ \]# useradd roboshop
    54 . 165 . 59.178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 \~ \]# mkdir /app

[^146]: \[ root@ip-172-31-47-239 \~ \]# curl -L -o /tmp/shipping . zip https: / /roboshop-builds . s3 . amazonaws . com/shipp
    ng . zip
    8 Total
    % Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 15.5M 100 15.5M
    0
    0 57. 4M
    0 --
    57 . 4M
    54 . 165 . 59.178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 \~ \]# cd /app
    54 . 165. 59. 178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app \]# unzip /tmp/shipping . zip
    Archive: /tmp/shipping . zip
    inflating: pom. xml

[^147]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies & build the application

[^148]: \[ root@ip-172-31-47-239 /app \]# mvn clean package

[^149]: \[ root@ip-172-31-47-239 /app \]# 1s -1
    total 4
    -rw-r--r-- 1 root root 2173 Dec 1 2022 pom. xml
    drwxr-xr-x 2 root root
    26 Dec 26
    2022 schema
    drwxr-xr-x 3 root root
    18 Dec 2
    2022 src
    drwxr-xr-x 6 root root
    145 Dec 7 16:07 target

[^150]: \[ root@ip-172-31-47-239 /app \]# cd target/
    54 . 165 . 59. 178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app/target \]# 1s -1
    total 40532
    drwxr-xr-x 3 root root
    47 Dec 7 16:07 classes
    drwxr-xr-x 3 root root
    25 Dec 7 16:07 generated-sources
    drwxr-xr-x 2 root root
    28 Dec
    7 16:07 maven-archiver
    drwxr-xr-x 3 root root
    35 Dec
    7 16:07 maven-status
    rw
    -- 1 root root 41486670 Dec
    7 16:07 shipping-1 . 0 . jar
    -rw-r--r-- 1 root root
    16322 Dec 7 16:07 shipping-1 . 0. jar . original

[^151]: \[ root@ip-172-31-47-239 /app/target \]# cd /app
    54 . 165. 59.178 \| 172.31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app \]# mv target/shipping-1.0. jar shipping. jar

[^152]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies & build the application

[^153]: \[Unit\]
    Description=Shipping Service
    \[Service\]
    User=roboshop
    Environment=CART ENDPOINT=cart . chowdarychilukuri . in : 8080
    Environment=DB HOST=mysql . chowdarychilukuri . in
    ExecStart=/bin/java -jar /app/shipping . jar
    SyslogIdentifier=shipping
    \[Install\]
    WantedBy-multi-user . target

[^154]: \[ root@ip-172-31-37-113 /app \]# 1s -1
    total 40520
    -rw-r--r-- 1 root root
    2173 Dec 1 2022 pom . xml
    drwxr-xr-x 2 root root
    26 Dec 26 2022 schema
    -rw-r--r-- 1 root root 41486670 Dec 7 02:50 shipping . jar
    drwxr-xr-x 3 root root
    18 Dec 2 2022 src
    drwxr-xr-x 6 root root
    121 Dec 7 02:51 target
    54 . 80 . 193. 157 \| 172. 31. 37. 113 \| t3. medium \| null
    \[ root@ip-172-31-37-113 /app \]# cd schema/
    54 . 80. 193. 157 \| 172. 31.37. 113 \| t3. medium \| null
    \[ root@ip-172-31-37-113 /app/schema \]# 1s -1
    total 63068
    -rw-r--r-- 1 root root 64581517 Dec 26 2022 shipping. sql
    54 . 80 . 193. 157 \| 172. 31. 37.113 \| t3. medium \| null
    \[ root@ip-172-31-37-113 /app/schema \]# less shipping . sql

[^155]: \[ root@ip-172-31-47-239 /app \]# systemctl daemon-reload

[^156]: \[ rootdip-172-31-47-239 /app \]# systemctl enable shipping
    Created symlink /etc/systemd/system/multi-user . target. wants/shipping . service - /etc/systemd/system/shippi
    ng . service .
    54 . 165 . 59. 178 \| 172 . 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app \]# systemctl start shipping
    54 . 165 . 59. 178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app \]#

[^157]: For this application to work fully functional we need to load schema to the Database.
    We need to load the schema. To load schema we need to install mysql client.
    To have it installed we can use

[^158]: \[ rootdip-172-31-47-239 /app \]# anf install mysql -y
    Last metadata expiration check: 0:04:21 ago on Thu 07 Dec 2023 04:23:57 PM UTC.
    Dependencies resolved.
    Package
    Arch
    Version
    Installing:
    mysql
    x86 64
    8. 0.26-1 . module e18 . 4. 0+915+de215114
    Installing dependencies:
    mariadb-connector-c-config
    noarch
    3. 1. 11-2. e18 3

[^159]: \[ root@ip-172-31-47-239 /app \]# mysql -h mysql . chowdarychilukuri . in -uroot -pRoboShop@1 < /app/schema/shi
    pping . sql
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    54 . 165 .59.178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app \]#

[^160]: This service needs a restart because it is dependent on schema, After loading schema only it will work as expected, Hence we are restarting this
    service. This

[^161]: \[ root@ip-172-31-47-239 /app \]# systemctl restart shipping
    54 . 165 . 59.178 \| 172. 31. 47.239 \| t3.medium \| null
    \[ root@ip-172-31-47-239 /app \]#\]

[^162]: \[ root@ip-172-31-47-239 /app \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID /Program name
    top
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0 . 0.0.0:\*
    LISTEN
    825/sshd
    tcp6
    0 :::111
    : : \*
    LISTEN
    1/systemd
    tcp6
    0
    :: : 8080
    LISTEN
    6230/java
    tcp6
    0
    : : : 22
    LISTEN
    825/sshd

[^163]: MongoDB
    catalogue WEB REDIS USER CART \| MYSQL Shipping
    54 . 80. 163.5 \| 172. 31. 40.170 \| t3. medium \| null
    \[ root@ip-172-31-40-170 \~ \]# mysql -uroot -pRoboShop@1
    mysql: \[Warning\] Using a password on the command line interface can be insecure
    Welcome to the MySQL monitor. Commands end with ; or g.
    Your MySQL connection id is 46
    Server version: 5.7.44 MySQL Community Server (GPL)
    Copyright (c) 2000, 2023, Oracle and/or its affiliates.
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners .
    Type 'help; ' or ' \\h' for help. Type ' \\c' to clear the current input statement.
    mysql> show databases;
    \| Database
    information schema
    cities
    mysql
    performance schema
    sys
    5 rows in set (0.00 sec)

[^164]: mysql> use cities
    Reading table information for completion of table and column names
    You can turn off this feature to get a quicker startup with -A
    Database changed
    mysql> use cities;
    Database changed
    mysql> show tables;
    +
    \| Tables in cities \|
    +
    +
    cities
    codes
    +
    2 rows in set (0.00 sec)

[^165]: MongoDB catalogue
    WEB
    REDIS
    USER
    CART MYSQL Shipping
    proxy_http_version 1.1;
    location /images/ {
    expires 5s ;
    root
    /usr/share/nginx/html ;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: / /catalogue. chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http://user . chowdarychilukuri . in: 8080/; }
    location /api/cart/ { proxy_pass http: / /cart. chowdarychilukuri . in: 8080/; }
    location /api/shipping/ { proxy_pass http: //shipping. chowdarychilukuri . in: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access_log off;

[^166]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# vim /etc/nginx/default.d/roboshop. conf
    52 . 90. 166.6 \| 172. 31. 17. 49 \| t2.micro \| null
    \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# cat /etc/nginx/default.d/roboshop . conf
    proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html ;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: / /catalogue. chowdarychilukuri . in: 8080/; }
    location /api/user/ { proxy_pass http: //user . chowdarychilukuri . in : 8080/; }
    location /api/cart/ { proxy_pass http: //cart. chowdarychilukuri . in: 8080/; }
    location /api/shipping/ { proxy_pass http: //shipping . chowdarychilukuri . in: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access log off;

[^167]: \[ root@ip-172-31-17-49 /usr/share/nginx/html \]# systemctl restart nginx

[^168]: G
    Not secure \| chowdarychilukuri.in/payment
    Stan's Robot Shop
    Login / Register
    Review your order
    Cart
    QTY
    Name
    Sub Total
    6595.10
    2
    Stan
    (134.00
    Categories
    1
    shipping to India Tanuku E461.10
    . Artificial
    Intelligence
    Inc Tax
    699. 18
    .
    Robot
    Total
    (595.10
    o C3PO
    Pay Now
    o Eve
    o K9
    o Kryten
    o Marvin
    o Mr Data
    o R2D2
    o Robbie
    o Stan
    satyachilukuri

[^169]: rabitmq
    Add additional tags
    Summary
    Number of instances Info
    Application and OS Images (Amazon Machine Image) Info
    An AMI is a template that contains the software configuration (operating system, application server, and
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Software Image (AMI)
    below
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    devops-practice
    X
    Virtual server type (instance type)
    t2.micro
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Centos-8-DevOps-Practice
    Storage (volumes)
    ami-03265a0778a880afb
    Browse more AMIs
    1 volume(s) - 10 GiB
    Including AMIs from
    AWS, Marketplace and
    the Community
    Free tier: In your first year includes
    X
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    750 hours of t2.micro (or t3.micro in
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    the Regions in which t2.micro is
    AMIs
    04T17:05:56.00
    unavailable) instance usage on free
    OZ
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    Review commands
    t2.micro
    Free tier eligible
    Family: t2 1 vCPU 1 GiB Memory Current generation: true
    All generations
    On-Demand Windows base pricing: 0.0162 USD per Hour

[^170]: Summary
    Key pair name - required
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    Number of instances Info
    1
    Network settings Info
    Edit
    Software Image (AMI)
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Network Info
    vpc-0817 cae8968304c06
    Virtual server type (instance type)
    t2.micro
    Subnet Info
    No preference (Default subnet in any availability zone)
    Firewall (security group)
    SG_Allow_All
    Auto-assign public IP Info
    Enable
    Storage (volumes)
    Firewall (security groups) Info
    1 volume(s) - 10 GiB
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    Free tier: In your first year includes
    X
    O Create security group
    Select existing security group
    750 hours of t2.micro (or t3.micro in
    the Regions in which t2.micro is
    Common security groups Info
    unavailable) instance usage on free
    Select security groups
    tier AMIs per month, 30 GiB of EBS
    C
    Compare security
    storage, 2 million IOs, 1 GB of
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    snapshots, and 100 GB of bandwidth
    VPC: vpc-0817cae8968304c06
    to the internet.
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    Configure storage Info
    Advanced
    Cancel
    Launch instance
    Review commands
    1x
    10
    GiB
    gpz
    Root volume (Not encrypted)

[^171]: RabbitMQ --> Messaging Queue Database
    synchronous --> asynchronous
    http/s --> synchronous
    server should be always up and running. ..
    400/500

[^172]: asynchronous
    - - -
    client --> messaging broker --> server
    sivakumar --> ramesh
    there will be a queue for ramesh
    sivakumar --> ramesh queue
    ramesh whatsapp --> subscribed to ramesh queue
    if online --> message wil be delivered
    when ramesh gets online --> ramesh whatsapp --> ramesh queue
    payment --> rabbitmq --> dispatch
    dispatch is subscribed to rabbitma

[^173]: RabbitMQ
    RabbitMQ is a messaging Queue which is used by some components of the applications.
    Configure YUM Repos from the script provided by vendor.

[^174]: \[ root@ip-172-31-20-90 \~ \]# curl -s https: //packagecloud. io/install/repositories/rabbitmq/erlang/script.r
    pm. sh \| bash
    Detected operating system as centos/8.
    Checking for curl. ..
    Detected curl. . .
    Downloading repository file: https: //packagecloud. io/install/repositories/rabbitmq/erlang/config_file . rep
    o?os=centos&dist=8&source=script

[^175]: \[ root@ip-172-31-20-90 \~ \]# curl -s https: //packagecloud. io/install/repositories/rabbitmq/rabbitmq-server
    /script . rpm. sh \| bash
    Detected operating system as centos/8.
    Checking for curl. .
    Detected curl. ..
    Downloading repository file: https: //packagecloud. io/install/repositories/rabbitmq/rabbitmq-server/config
    file. repo?os=centos&dist=8&source=script
    done.
    Installing pygpgme to verify GPG signatures . . .
    rabbitmq rabbitmq-server-source
    671 B/s \| 819 B
    00: 01
    rabbitmq rabbitmq-server-source
    13 kB/s \| 3.9 kB
    00: 00

[^176]: \[ root@ip-172-31-20-90 \~ \]# anf install rabbitmq-server -y
    Last metadata expiration check: 0:00:39 ago on Fri 08 Dec 2023 03:04:32 PM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Size
    Installing:
    rabbitmq-server
    noarch
    3. 12 . 10-1. e18
    rabbitmq rabbitmq-server
    17 M
    Installing dependencies:
    erlang
    x86 64
    26.1.2-1. e18
    rabbitmq erlang
    21 M
    Transaction Summary
    Install 2 Packages

[^177]: \[ root@ip-172-31-20-90 \~ \]# systemctl enable rabbitmq-server
    Created symlink /etc/systemd/system/multi-user . target. wants/rabbitmq-server . service - /usr/lib/systemd/
    stem/rabbitmq-server . service.
    54 . 172 . 199.58 \| 172. 31.20.90 \| t2.micro \| null
    \[ root@ip-172-31-20-90 \~ \]# systemctl start rabbitmq-server
    54 . 172 . 199.58 \| 172. 31.20.90 \| t2.micro \| null
    \[ root@ip-172-31-20-90 \~ \]# systemctl status rabbitmq-server
    rabbitmq-server . service - RabbitMQ broker
    Loaded: loaded (/usr/lib/systemd/system/rabbitmq-server . service; enabled; vendor preset: disabled)
    Active: active (running) since Fri 2023-12-08 15:06:14 UTC; 9s ago
    Main PID: 16697 (beam . smp)
    Tasks: 23 (limit: 4440)

[^178]: RabbitMQ comes with a default username / password as guest/guest. But this user cannot be used to connect. Hence, we need to create one
    user for the application.

[^179]: \[ root@ip-172-31-20-90 \~ \]# rabbitmqctl add_user roboshop roboshop123
    Adding user "roboshop"
    Done. Don't forget to grant the user permissions to some virtual hosts! See 'rabbitmqctl help set permiss
    ions' to learn more.
    54 . 172 . 199.58 \| 172.31.20.90 \| t2.micro \| null
    \[ root@ip-172-31-20-90 \~ \]# rabbitmqctl set permissions -p / roboshop " . \*" I \*ll ll
    \* 1I
    Setting permissions for user "roboshop" in vhost "/"
    54 . 172. 199.58 \| 172.31.20.90 \| t2.micro \| null
    \[ root@ip-172-31-20-90 \~ \]#

[^180]: Payment
    Add additional tags
    Summary
    Number of instances
    Info
    Application and OS Images (Amazon Machine Image) Info
    1
    An AMI is a template that contains the software configuration (operating system, application server, and
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Software Image (AMI)
    below
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Q devops-practice
    X
    Virtual server type (instance type)
    t2.micro
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Centos-8-DevOps-Practice
    Storage (volumes)
    ami-03265a0778a880afb
    Browse more AMIs
    1 volume(s) - 10 GiB
    Including AMIs from
    AWS, Marketplace and
    the Community
    Free tier: In your first year includes
    X
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    750 hours of t2.micro (or t3.micro in
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    the Regions in which t2.micro is
    AMIs
    04T17:05:56.00
    unavailable) instance usage on free
    OZ
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    Review commands
    t2.micro
    Free tier eligible
    Family: t2
    1 VCPU 1 GiB Memory Current generation: true
    All generations
    On-Demand Windows base pricing: 0.0162 USD per Hour

[^181]: Summary
    Key pair name - required
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    Number of instances
    Info
    Network settings Info
    Edit
    Software Image (AMI)
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Network Info
    vpc-0817 cae8968304c06
    Virtual server type (instance type)
    t2.micro
    Subnet Info
    No preference (Default subnet in any availability zone)
    Firewall (security group)
    SG_Allow_All
    Auto-assign public IP Info
    Enable
    Storage (volumes)
    Firewall (security groups) Info
    1 volume(s) - 10 GiB
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    Free tier: In your first year includes
    X
    O Create security group
    Select existing security group
    750 hours of t2.micro (or t3.micro in
    Common security groups Info
    the Regions in which t2.micro is
    unavailable) instance usage on free
    Select security groups
    tier AMIs per month, 30 GiB of EBS
    Compare security
    storage, 2 million IOs, 1 GB of
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    snapshots, and 100 GB of bandwidth
    VPC: vpc-0817cae8968304c06
    to the internet.
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    Configure storage Info
    Advanced
    Cancel
    Launch instance
    Review commands
    1x
    10
    GIB
    gp2
    Root volume (Not encrypted)

[^182]: 34 . 229. 14. 43 \| 172 . 31. 31.198 \| t2.micro \| null
    \[ centos@ip-172-31-31-198 \~ \]$ sudo su
    34 . 229. 14. 43 \| 172. 31. 31. 198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 \~ \]# anf install python36 gcc python3-devel -y
    Centos Stream 8 - AppStream
    27 MB/S \| 34 MB
    00 :01

[^183]: \[ root@ip-172-31-31-198 \~ \]# useradd roboshop
    34 . 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 \~ \]# mkdir /app
    34 . 229. 14.43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 \~ \]# curl -L -o /tmp/payment. zip https: //roboshop-builds . s3 . amazonaws
    diz .
    8 Total
    % Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left
    Speed
    100 3518 100 3518
    0
    0 37031
    0
    - -
    37031
    34 . 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 \~ \]# cd /app
    34 . 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ rootdip-172-31-31-198 /app \]# 1s -1
    total 0
    34 . 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# unzip /tmp/payment . zip
    Archive: /tmp/payment . zip
    inflating: payment . ini
    inflating: payment . py
    inflating: rabbitmq . py
    inflating: requirements . txt

[^184]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies.

[^185]: \[ root@ip-172-31-31-198 /app \]# cd /app
    34. 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# pip3.6 install -r requirements . txt
    WARNING: Running pip install with root privileges is generally not a good idea. Try
    r instead.
    Collecting uwsgi (from -r requirements . txt (line 1) )
    Downloading https: //files . pythonhosted. org/packages/79/73/b5def500729e134d1cb8dfc
    60c6532d40edaed/uwsgi-2 . 0.23. tar . gz (810kB)
    100%
    \| 819kB 1. 5MB/s
    Collecting Flask (from -r requirements. txt (line 2) )

[^186]: 34 . 229. 14. 43 \| 172. 31.31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# 1s -1
    total 20
    -rw-r--r-- 1 root root 176 Dec 26 2022 payment.ini
    -rw-r--r-- 1 root root 6085 Dec 1 2022 payment.py
    -rw
    -r-- 1 root root 2005 Dec
    1 2022 rabbitmq . py
    -rw-r--r-- 1 root root
    64 Dec
    2022 requirements . txt
    34 . 229. 14. 43 \| 172. 31. 31. 198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# cat requirements . txt
    uwsgi
    Flask
    requests
    pika
    prometheus client
    opentracing
    instana

[^187]: We need to setup a new service in systemd so systemctl can manage this service
    Setup SystemD Payment Service

[^188]: \[Unit\]
    Description=Payment Service
    \[Service\]
    User=root
    WorkingDirectory=/ app
    Environment=CART HOST=cart . chowdarychilukuri . in
    Environment-CART PORT=8080
    Environment=USER HOST=user . chowdarychilukuri .in
    Environment=USER PORT=8080
    Environment-AMQP HOST=rabbitmq . chowdarychilukuri . in
    Environment=AMQP USER=roboshop
    Environment=AMQP PASS=roboshop123
    ExecStart=/usr/local/bin/uwsgi --ini payment. ini
    ExecStop=/bin/kill -9 $MAINPID
    SyslogIdentifier=payment
    \[Install\]
    WantedBy-multi-user . target

[^189]: \[ rootip-172-31-31-198 /app \]# vim /etc/systemd/system/payment . service
    34 . 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# cat /etc/systemd/system/payment . service
    \[Unit\]
    Description=Payment Service
    \[Service\]
    User=root
    WorkingDirectory=/ app
    Environment=CART HOST=cart . chowdarychilukuri . in
    Environment=CART PORT=8080
    Environment=USER HOST=user . chowdarychilukuri . in
    Environment=USER PORT=8080
    Environment=AMQP HOST=rabbitmq . chowdarychilukuri . in
    Environment=AMQP_USER=roboshop
    Environment=AMOP PASS=roboshop123
    ExecStart=/usr/local/bin/uwsgi --ini payment.ini
    ExecStop=/bin/kill -9 $MAINPID
    SyslogIdentifier=payment
    \[Install\]
    WantedBy=multi-user . target

[^190]: \[ root@ip-172-31-31-198 /app \]# systemctl daemon-reload
    34 . 229. 14.43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# systemctl enable payment
    Created symlink /etc/systemd/system/multi-user . target. wants/payment . service - /etc/systemd/sy
    . service.
    34 . 229. 14. 43 \| 172. 31. 31.198 \| t2.micro \| null
    \[ root@ip-172-31-31-198 /app \]# systemctl start payment
    34 . 229. 14. 43 \| 172. 31. 31. 198 \| t2.micro \| null
    \[ rootdip-172-31-31-198 /app \]# systemctl status payment
    payment . service - Payment Service
    Loaded: loaded (/etc/systemd/system/payment . service; enabled; vendor preset: disabled)
    Active: active (running) since Fri 2023-12-08 15:44:02 UTC; 7s ago
    Main PID: 5870 (uwsgi)
    Tasks: 3 (limit: 4440)

[^191]: \[ root@ip-172-31-31-198 /app \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0. 0 . 0: 8080
    0.0.0.0:\*
    LISTEN
    5870/uwsgi
    tcp
    OOOOO
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    826/sshd
    tcp6
    0 :: :111
    : ::\*
    LISTEN
    1/systemd
    tcp6
    0 :: :22
    LISTEN
    826/sshd

[^192]: proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root
    /usr/share/nginx/html ;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: / /catalogue. chowdarychilukuri . in: 8080/;
    location /api/user/ { proxy_pass http: //user . chowdarychilukuri .in: 8080/; }
    location /api/cart/ { proxy_pass http://cart. chowdarychilukuri . in: 8080/; }
    location /api/shipping/ { proxy_pass http: //shipping. chowdarychilukuri . in: 8080/; }
    location /api/payment/ { proxy_pass http://payment. chowdarychilukuri . in: 8080/; }
    location /health {
    stub status on;
    access_log off;

[^193]: C
    Not secure \| chowdarychilukuri.in/payment
    Stan's Robot Shop
    Search
    Login / Register
    Review your order
    Cart
    Order placed ae49fccd-1fcb-4897-a988-8eec73c64f8c
    STAN
    Empty
    Thank you for your order Continue shopping
    Categories
    . Artificial
    Intelligence
    . Robot
    o C3PO
    o Eve
    o K9
    o Kryten
    o Marvin
    o Mr Data
    o R2D2
    o Robbie
    o Stan
    chill

[^194]: Dispatch
    Add additional tags
    Summary
    Number of instances
    Info
    Application and OS Images (Amazon Machine Image) Info
    An AMI is a template that contains the software configuration (operating system, application server, and
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Software Image (AMI)
    below
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    O devops-practice
    X
    Virtual server type (instance type)
    t2.micro
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Centos-8-DevOps-Practice
    Storage (volumes)
    ami-03265a0778a880afb
    Browse more AMIs
    1 volume(s) - 10 GiB
    Including AMIs from
    AWS, Marketplace and
    the Community
    Free tier: In your first year includes
    X
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    750 hours of t2.micro (or t3.micro in
    Community
    2023-06-
    x86_64
    hvm
    ebs
    Yes
    the Regions in which t2.micro is
    AMIs
    04T17:05:56.00
    unavailable) instance usage on free
    oz
    tier AMIs per month, 30 GiB of EBS
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    to the internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    Review commands
    t2.micro
    Free tier eligible
    Family: t2 1 VCPU 1 GiB Memory Current generation: true
    All generations
    On-Demand Windows base pricing: 0.0162 USD per Hour

[^195]: Key pair name - required
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    Number of instances Info
    Network settings Info
    Edit
    Software Image (AMI)
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Network Info
    vpc-0817 cae8968304c06
    Virtual server type (instance type)
    t2.micro
    Subnet
    Info
    No preference (Default subnet in any availability zone)
    Firewall (security group)
    SG_Allow_All
    Auto-assign public IP Info
    Enable
    Storage (volumes)
    Firewall (security groups) Info
    1 volume(s) - 10 GiB
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    @ Free tier: In your first year includes
    X
    Create security group
    Select existing security group
    750 hours of t2.micro (or t3.micro in
    the Regions in which t2.micro is
    Common security groups Info
    unavailable) instance usage on free
    Select security groups
    tier AMIs per month, 30 GiB of EBS
    C
    Compare security
    storage, 2 million IOs, 1 GB of
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    snapshots, and 100 GB of bandwidth
    VPC: vpc-0817cae8968304c06
    to the internet.
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    Configure storage Info
    Advanced
    Cancel
    Launch instance
    Review commands
    1x
    10
    GIB
    gp2
    Root volume (Not encrypted)

[^196]: Dispatch
    Dispatch is the service which dispatches the product after purchase. It is written in Golang, So wanted to install Golang.
    Install Golang

[^197]: \[ centos@ip-172-31-18-112 \~ \]$ sudo su
    34. 228 . 69.214 \| 172. 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 \~ \]# anf install golang -y
    Centos Stream 8 - AppStream
    28 MB/S \|
    34 MB
    00 : 01
    Centos Stream 8 - BaseOS
    23 MB/S
    55 MB
    00: 02

[^198]: Configure the application.
    Add application User

[^199]: \[ root@ip-172-31-18-112 \~ \]# useradd roboshop
    34 . 228. 69.214 \| 172. 31.18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 \~ \]# mkdir /app

[^200]: \[ root@ip-172-31-18-112 \~ \]# curl -L -o /tmp/dispatch . zip https: //roboshop-builds . s3 . amazonaws . com/dis
    ch . zip
    8 Total
    8 Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 2070 100 2070
    O
    0 27600
    0
    27972
    34 . 228. 69.214 \| 172. 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 \~ \]# cd /app
    34 . 228 . 69.214 \| 172. 31.18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# unzip /tmp/dispatch. zip
    Archive: /tmp/dispatch . zip
    inflating: main. go
    34. 228. 69. 214 \| 172. 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# 1s -1
    total 8
    -rw-r--r-- 1 root root 5228 Dec 1 2022 main . go

[^201]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies & build the software.

[^202]: \[ root@ip-172-31-18-112 /app \]# cd /app
    34. 228. 69.214 \| 172 . 31. 18.112 \| t2.micro \| null
    \[ rootdip-172-31-18-112 /app \]# go mod init dispatch
    go: creating new go.mod: module dispatch
    go: to add module requirements and sums:
    go mod tidy
    34 . 228 . 69. 214 \| 172 . 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# go get
    go: downloading github. com/opentracing/opentracing-go v1 .2.0
    go: downloading github. com/streadway/amqp v1 . 1.0
    go: module github . com/streadway/amqp is deprecated: Consider using the github. com/rabbitmq/amqp091-go pa
    kage instead.
    go: added github. com/opentracing/opentracing-go v1 .2.0
    go: added github. com/streadway/amqp v1 .1.0
    34 . 228 . 69.214 \| 172 . 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# go build

[^203]: We need to setup a new service in systemd so systemctl can manage this service
    Setup SystemD Dispatch Service

[^204]: \[Unit\]
    Description = Dispatch Service
    \[Service\]
    User=roboshop
    Environment=AMQP HOST=172 . 31 .20 .90
    Environment=AMQP USER=roboshop
    Environment=AMQP PASS=roboshop123
    ExecStart=/app/dispatch
    SyslogIdentifier=dispatch
    \[Install\]
    WantedBy-multi-user . target
    N

[^205]: \[ root@ip-172-31-18-112 /app \]# systemctl daemon-reload
    34 . 228 . 69.214 \| 172. 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# systemctl enable dispatch
    Created symlink /etc/systemd/system/multi-user . target. wants/dispatch. service - /etc/systemd/system
    ch . service.
    34. 228 . 69.214 \| 172. 31. 18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# systemctl start dispatch
    34 . 228 . 69.214 \| 172. 31.18.112 \| t2.micro \| null
    \[ root@ip-172-31-18-112 /app \]# systemctl status dispatch
    dispatch . service - Dispatch Service
    Loaded: loaded (/etc/systemd/system/dispatch. service; enabled; vendor preset: disabled)
    Active: active (running) since Fri 2023-12-08 16:14:09 UTC; 6s ago
    Main
    PID .
    9628 (dispatch)

[^206]: 2.micro \| null
    \[ rootlip-172-31-18-112 /app \]# tail -f /var/log/messages
    Dec 8 16:14:09 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:14:09 Connecting to amap: / /roboshop: robosh
    op1230172. 31.20. 90:5672/
    Dec 8 16:14:09 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:14:09 Waiting for messages
    Dec 8 16:14:09 ip-172-31-18-112 rsyslogd \[838\]: imjournal: journal files changed, reloading. .. \[v8.2102.
    0-13.e18 try https://www.rsyslog. com/e/0 \]
    Dec 8 16:14:09 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:14:09 Rabbit MQ ready true
    Dec 8 16:15:56 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:15:56 Order {"orderid": "dbffbd53-c7a6-4ff
    6-bbf8-bcc848a83344", "user": "anonymous-2", "cart": {"total": 2410.2, "tax": 401. 6999999999998, "items" :
    \[{"qty": 1, "sku" : "HAL-1", "name": "HAL", "price": 2001, "subtotal": 2001), {"qty" : 1, "sku": "SHIP",
    name": "shipping to India Banamau", "price": 409.2, "subtotal": 409.2)\]}}
    Dec 8 16:15:56 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:15:56 Headers map \[X-INSTANA-L: 1 X-INSTANA-
    S : ef903d0966c8e517 X-INSTANA-T : 5ed61b5be5c899b5 traceparent: 00-00000000000000005ed61b5be5c89965-3235200a8
    42f8eda-01 tracestate : in=5ed61b5be5c89965 ; 3235a00a842f8eda\]
    Dec 8 16:15:56 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:15:56 order dbffbd53-c7a6-4ff6-bbf8-bcc848
    a83344
    Dec 8 16:15:56 ip-172-31-18-112 dispatch \[9628\] : 2023/12/08 16:15:56 opentracing: SpanContext not found i
    n Extract carrier

[^207]: Deployment
    -
    developer will update the code
    he will push to some location as zip
    download new code
    stop the server --> stop catalogue
    remove old code
    unzip new code
    restart the server
    6hours --> testing

