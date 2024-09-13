---
title: 7Day_Proj_Manual_Installation
uuid: 8381b170-0e8e-11ef-9be8-a6f126245c9e
version: 447
created: '2024-05-10T11:01:11+05:30'
tags:
  - roboshop-project
  - roboshop-project-manual
---

***Topics:***

1. *<mark style="background-color:#f8d616;">**Configure Roboshop manually**<!-- {"backgroundCycleColor":"25"} --></mark>*

 

 

# *<mark style="background-color:#f8914d;">**Configure Roboshop manually:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*We have 3 tiers*

1. *Frontend/Web tier*

1. *Application/API/Backend tier*

1. *Database tier*

1. *MongoDB - It's a NOSQL database i.e used for Bigdata*

1. *Redis - It's a cache database*

1. *MySQL - RDBMS database (tables & columns)*

1. *RABBIT MQ - It's a Queue kind of Database*

 

*Dependencies*

***NodeJS - NPM***

***Java   - Maven***

***Python - PIP***

 

*Database Applications are stateful(customer information etc like user name, password, address)   - if DB app's crashes restoration is harder*

*Application/backend or web/frontend are stateless (where database not required & user or customer data will not be stored here)  - if these app's crashes we can restore Fastly/easily*

 

 

*How faster we connect to database is more useful ( developer writes code to connect faster to DB)* 

*Ex- If Amazon/Flipkart user connected to then DB should fetch data faster else user may move to other applications like Myntra etc.. So that Amazon business gets down slowly).*

 

# *<mark style="background-color:#f8914d;">**CRUD over Database**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*--------------------------*

*Create - user*

*Read - read data*

*Update - update profile data*

*Delete - profile data delete*

![e7271016-aa73-4e49-aee6-caa36b3c5bdb.png|783](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e7271016-aa73-4e49-aee6-caa36b3c5bdb.png) [^1]

 

 

# *<mark style="background-color:#f8914d;">**Manual project Installation:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*<mark style="background-color:#f8d616;">**Web server**<!-- {"backgroundCycleColor":"25"} --></mark> **- t2.micro instance***

\

*Creating a firewall(Security group) - Before creating an Instance*

 

![a2b61b44-999d-401d-9cb7-5b1ebaab6637.png|822.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/a2b61b44-999d-401d-9cb7-5b1ebaab6637.png) [^2]

 

![6ace5029-b933-442f-b577-0b1c2196faf4.png|901.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/6ace5029-b933-442f-b577-0b1c2196faf4.png) [^3]

 

# *<mark style="background-color:#f8d616;">**Creating an WEB Instance:**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

*Creating a new servers to check how Nginx reverse proxy works.* 

*For this project we are using CentOS AMI for practice - Centos-8-DevOps-Practice*

*User - centos*

*Psw: #DevOps321#*

 

![7b33ca34-7ba7-4bf0-a77f-94867128df2b.png|851.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/7b33ca34-7ba7-4bf0-a77f-94867128df2b.png) [^4]

 

![6ec6b69c-5be9-410d-92bd-ee256c3bd6c8.png|829.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/6ec6b69c-5be9-410d-92bd-ee256c3bd6c8.png) [^5]

 

*No Keypair needed as we login directly using user/psw:*

 

![6aeeb161-cb0a-40a8-8d95-92333fde23f4.png|837.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/6aeeb161-cb0a-40a8-8d95-92333fde23f4.png) [^6]

 

***Now configure putty to use credentials:***

![fa72cf64-84cd-436c-ae73-a41ec3f47186.png|469](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/fa72cf64-84cd-436c-ae73-a41ec3f47186.png) [^7]

 

![abb5f0c6-9629-44ff-b2cd-352eeecb870a.png|478](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/abb5f0c6-9629-44ff-b2cd-352eeecb870a.png) [^8]

 

![e95b7e40-4082-459c-ada4-72e4a5c473af.png|648](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e95b7e40-4082-459c-ada4-72e4a5c473af.png) [^9]

 

*Now save it*

![e6ed6da6-3c92-4bb0-8132-aeb779e289f7.png|478](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e6ed6da6-3c92-4bb0-8132-aeb779e289f7.png) [^10]

 

*Now Login to web server using public IP address by superputty*

 

![9ac80a60-8df7-4cbb-b2a5-3be77854015e.png|829.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/9ac80a60-8df7-4cbb-b2a5-3be77854015e.png) [^11]

 

 

![42f3c187-7855-4dc8-a6b0-0f79b32f694f.png|906.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/42f3c187-7855-4dc8-a6b0-0f79b32f694f.png) [^12]

 

![d42ed3fe-a822-43d0-940c-4c02d3d0fc4f.png|840](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/d42ed3fe-a822-43d0-940c-4c02d3d0fc4f.png) [^13]

 

 

*Renaming Instance as WEB*

![24dd930c-b04c-4aec-be9a-3177a810a9e8.png|859](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/24dd930c-b04c-4aec-be9a-3177a810a9e8.png) [^14]

 

 

*We are using Nginx as Web server, webservers' is nothing but Http server's -- Nginx port - 80 (Nginx is a popular webserver)*

 

![f277eac1-555d-4c14-ac3f-ad4fab7fb4eb.png|769](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/f277eac1-555d-4c14-ac3f-ad4fab7fb4eb.png) [^15]

 

# ***Installing NGINX: on web server***<!-- {"collapsed":true} -->

 

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

 

![29338d25-8a24-436f-aa4f-909689112b54.png|987.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/29338d25-8a24-436f-aa4f-909689112b54.png) [^16]

 

 

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

 

![bffa7248-33b0-41aa-b38b-e1a99db73c56.png|898.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/bffa7248-33b0-41aa-b38b-e1a99db73c56.png) [^17]

 

![f5a85de5-a645-4544-8cd5-8c7f2a8b466e.png|896.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/f5a85de5-a645-4544-8cd5-8c7f2a8b466e.png) [^18]

 

```
netstat -lntp    --> to check ports opened or not
```

![5b3f4d70-a07a-4522-8aa7-25bedecb13ae.png|928.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/5b3f4d70-a07a-4522-8aa7-25bedecb13ae.png) [^19]

 

*Try to access the service once over the browser and ensure you get some default content.*

 

[*<mark style="background-color:#f3de6c;">http://<public-IP>:80<!-- {"backgroundCycleColor":"14"} --></mark>*](http://%3cpublic-IP%3e:80) 

*<mark style="background-color:#f3de6c;">http:3.85.61.63:80<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">Or<!-- {"backgroundCycleColor":"14"} --></mark>*

*<mark style="background-color:#f3de6c;">3.85.61.63<!-- {"backgroundCycleColor":"14"} --></mark>*

 

![67c4d119-14b7-4793-80cb-457f35eb688e.png|827.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/67c4d119-14b7-4793-80cb-457f35eb688e.png) [^20]

 

*/etc/nginx   --> n**ginx configuration files will be present here.***

 

```
cd /etc/nginx/
```

*--I**n this file all nginx config files will be present & it will have all details like where error logs will save, access logs, where html pages will be there.***  

***which port server is using ex:80 for nginx.***

```
vim nginx.conf   
```

 

![042da556-f58b-4a77-887e-e29d9ec0f9c3.png|869.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/042da556-f58b-4a77-887e-e29d9ec0f9c3.png) [^21]

 

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

![64205832-fadd-4209-be61-25dead45a6cb.png|800.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/64205832-fadd-4209-be61-25dead45a6cb.png) [^22]

 

![8303e767-5bb1-4865-bdf0-66097487489c.png|830.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/8303e767-5bb1-4865-bdf0-66097487489c.png) [^23]

 

 

*Now web page code is ready & built. Developer pushed/placed packages in one location(here in aws s3). Copy those code files to /usr/share/nginx/html/  (we are configuring manually this setup)*

*Download the frontend content*

 

*# curl -o /tmp/web.zip* [*https://roboshop-builds.s3.amazonaws.com/web.zip*](https://roboshop-builds.s3.amazonaws.com/web.zip) 

```
cd /tmp/
```

```
ls -l
```

 

![d9ebbe51-ea75-42ba-94ac-4eb953cdf019.png|931.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/d9ebbe51-ea75-42ba-94ac-4eb953cdf019.png) [^24]

 

![5fca7e91-461a-4461-9a2c-026f41ecf9d1.png|782.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/5fca7e91-461a-4461-9a2c-026f41ecf9d1.png) [^25]

 

 

*Extract the frontend content.*

```
cd /usr/share/nginx/html
```

```
unzip /tmp/web.zip
```

```
ls -l
```

![298bb15c-9f9e-4ea1-b549-836dcfab9b55.png|907.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/298bb15c-9f9e-4ea1-b549-836dcfab9b55.png) [^26]

![ae782e27-82ed-447c-9d5c-6bf346846c15.png|907](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/ae782e27-82ed-447c-9d5c-6bf346846c15.png) [^27]

 

 

*Try to access the nginx service once more over the browser and ensure you get roboshop content.*

![56f56f46-a074-47e8-bcbd-16b06c46ebfc.png|891.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/56f56f46-a074-47e8-bcbd-16b06c46ebfc.png) [^28]

 

# *<mark style="background-color:#f8914d;">**Create Nginx Reverse Proxy Configuration.**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

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

 

 

# *<mark style="background-color:#f8d616;">**Forward proxy**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

![d893dd0f-412e-45fd-b3fa-0ebb4fe0f9ec.png|697](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/d893dd0f-412e-45fd-b3fa-0ebb4fe0f9ec.png) [^29]

 

 

![579340aa-975c-4ad8-ad15-63c09f1dcf1d.png|678](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/579340aa-975c-4ad8-ad15-63c09f1dcf1d.png) [^30]

 

# *<mark style="background-color:#f8914d;">**Reverse proxy**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![080d0072-3394-4593-9e14-cdcbd37247a1.png|808.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/080d0072-3394-4593-9e14-cdcbd37247a1.png) [^31]

 

 

 

```
vim /etc/nginx/default.d/roboshop.conf
```

*Place below content in above roboshop.conf file*

*---------*

<mark>proxy_http_version 1.1;</mark>

<mark>location /images/ {</mark>

  <mark>expires 5s;</mark>

  <mark>root   /usr/share/nginx/html;</mark>

  <mark>try_files $uri /images/placeholder.jpg;</mark>

<mark>}</mark>

<mark>location /api/catalogue/ { proxy_pass</mark> [<mark>http://localhost:8080/</mark>](http://localhost:8080/)<mark>; }</mark>

<mark>location /api/user/ { proxy_pass</mark> [<mark>http://localhost:8080/</mark>](http://localhost:8080/)<mark>; }</mark>

<mark>location /api/cart/ { proxy_pass</mark> [<mark>http://localhost:8080/</mark>](http://localhost:8080/)<mark>; }</mark>

<mark>location /api/shipping/ { proxy_pass</mark> [<mark>http://localhost:8080/</mark>](http://localhost:8080/)<mark>; }</mark>

<mark>location /api/payment/ { proxy_pass</mark> [<mark>http://localhost:8080/</mark>](http://localhost:8080/)<mark>; }</mark>

 

<mark>location /health {</mark>

  <mark>stub_status on;</mark>

  <mark>access_log off;</mark>

<mark>}</mark>

*--------*

 

```
cat /etc/nginx/default.d/roboshop.conf
```

![f4159843-f60f-45df-b3e5-0442f20e89e7.png|779.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/f4159843-f60f-45df-b3e5-0442f20e89e7.png) [^32]

 

 

*Ensure you replace the localhost with the actual ip address of those component server. Word localhost is just used to avoid the failures on the Nginx Server.*

```
systemctl restart nginx
```

![445b79f6-b9fa-47bc-bb5c-9602d74336fa.png|758.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/445b79f6-b9fa-47bc-bb5c-9602d74336fa.png) [^33]

 

 

![647e13e8-9d8c-4d48-aa6a-ef8376bfb1f3.png|611.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/647e13e8-9d8c-4d48-aa6a-ef8376bfb1f3.png) [^34]

 

 

***Right click & click on inspect - select network***

![82bdfee1-27c2-486f-a0b8-1a8d23a0ac0a.png|793.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/82bdfee1-27c2-486f-a0b8-1a8d23a0ac0a.png) [^35]

 

![0b29f32b-b7c0-4d7b-9b6c-357d1e688532.png|549](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/0b29f32b-b7c0-4d7b-9b6c-357d1e688532.png) [^36]

 

# *<mark style="background-color:#f8d616;">HTTP status<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

*--------------------*

*2\*\* --> success*

*3\*\* --> redirect/temp --> images, gifs are redirected*

 

*failure responses*

*-----------------*

*400, 404, 403, 402*

 

*4\*\* --> client side error*

*5\*\* --> server side error --> purely project error (we need to check immediately)*

 

# *<mark style="background-color:#f8d616;">**Caching -> main purpose is load balancing & server anonymous**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

*--------------*

*Airtel --> 1000 users*

 

*1 user downloaded bahubali movie --> server from US*

*cache server --> bahubali movie*

 

*2nd user get from cache server --> more speed*

 

 

# *<mark style="background-color:#f8914d;">**Configuring MongoDB server:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

![e50cb04e-e9d4-489e-b431-bfacf9bbfb72.png|663.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e50cb04e-e9d4-489e-b431-bfacf9bbfb72.png) [^37]

 

 

***Since MongoDB is heavy uses DB we use T3.micro instance***

 

*Launch MongoDB instance: --> centos-8-DevOps-Practice (AMI)*

*Select t3.micro instance type -- _ it is chargeable so once used shutdown immediately*

![301b9247-57da-45df-bd58-2c138881ed7e.png|761.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/301b9247-57da-45df-bd58-2c138881ed7e.png) [^38]

 

***No Keypair needed, SG group allow all TCP protocols(all traffic)***

![b901e863-91eb-435c-abc2-628a2e9cb21b.png|821.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/b901e863-91eb-435c-abc2-628a2e9cb21b.png) [^39]

 

***Login with super putty by providing IP:***

***User -centos***

***Psw: #DevOps321#***

 

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

 

![b5dac903-b1d8-4b6a-82eb-5e44e5edf62f.png|848.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/b5dac903-b1d8-4b6a-82eb-5e44e5edf62f.png) [^40]

 

*<mark style="background-color:#f8d616;">Install MongoDB<!-- {"backgroundCycleColor":"25"} --></mark>*

```
dnf install mongodb-org -y
```

![dce9cfb6-c77a-4b2a-a117-7c170490f138.png|835.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/dce9cfb6-c77a-4b2a-a117-7c170490f138.png) [^41]

 

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

![5e10392c-41f8-4905-9cc8-b9adf29fcd64.png|651.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/5e10392c-41f8-4905-9cc8-b9adf29fcd64.png) [^42]

 

```
netstat -lntp    
```

![7b7e86a4-bf8a-48a2-b83a-a20cb5a776c0.png|869.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/7b7e86a4-bf8a-48a2-b83a-a20cb5a776c0.png) [^43]

 

 

*127.0.0.1 --> localhost (nothing but mongodb within the server only it will accept connections & it won't accept outside connections) - but here we need connection from App tier*

 

![803daa46-6b79-452d-9af5-7cdaf17bd3a4.png|789.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/803daa46-6b79-452d-9af5-7cdaf17bd3a4.png) [^44]

 

```
vim /etc/mongod.conf
```

![f51ccee2-00aa-483a-8cd6-927ab24793ae.png|692.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/f51ccee2-00aa-483a-8cd6-927ab24793ae.png) [^45]

 

```
systemctl restart mongod
```

```
netstat -lntp                            --> now App tier servers can communicate with mongo DB.
```

 

![92e49033-9b23-4475-9012-4db66771347a.png|744.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/92e49033-9b23-4475-9012-4db66771347a.png) [^46]

 

 

# *<mark style="background-color:#f8914d;">**Launching & configuring Catalogue server:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Launch Catalogue instance: --> centos-8-DevOps-Practice (AMI)*

*Select t2.micro instance type* 

 

 

![c5172e57-8998-4af2-bad8-8cf57569a633.png|784.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/c5172e57-8998-4af2-bad8-8cf57569a633.png) [^47]

 

![89973c4b-6854-43c6-b95b-dc1e916b58d7.png|756.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/89973c4b-6854-43c6-b95b-dc1e916b58d7.png) [^48]

 

![87f17d32-11ba-45c9-a3ae-3d2fa7fc45ba.png|836.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/87f17d32-11ba-45c9-a3ae-3d2fa7fc45ba.png) [^49]

 

***Connect to catalogue instance:***

 

![530a3fe1-f5c9-410b-885d-b8c0e54d5e55.png|768](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/530a3fe1-f5c9-410b-885d-b8c0e54d5e55.png) [^50]

 

```
sudo su -
```

```
dnf module disable nodejs -y
```

```
dnf module enable nodejs:18 -y
```

![006a8714-6028-4e76-944b-416bc2b498a7.png|877.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/006a8714-6028-4e76-944b-416bc2b498a7.png) [^51]

 

*Install NodeJS*

```
dnf install nodejs -y
```

![e54b1b32-61ea-418d-890c-9def21a244a7.png|861.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e54b1b32-61ea-418d-890c-9def21a244a7.png) [^52]

 

![8caa3656-b82b-4942-acde-908e3302898a.png|847.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/8caa3656-b82b-4942-acde-908e3302898a.png) [^53]

 

*Add application User*

*It’s a system user created for Roboshop application, we can use this user to run roboshop application without using root user.*

```
useradd roboshop  
```

![dc387914-5026-44e8-874a-35f81ae512cf.png|793.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/dc387914-5026-44e8-874a-35f81ae512cf.png) [^54]

 

![e25b6f7b-26ac-46a6-9bf4-9babaea09bcd.png|756](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e25b6f7b-26ac-46a6-9bf4-9babaea09bcd.png) [^55]

 

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

![d48eb527-24ee-4d01-8163-1a1ab5a8391a.png|613](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/d48eb527-24ee-4d01-8163-1a1ab5a8391a.png) [^56]

 

![0ae46651-f02b-417a-bc95-b95aefa3e26b.png|700](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/0ae46651-f02b-417a-bc95-b95aefa3e26b.png) [^57]

 

 

*Download the application code to created app directory.*

*#curl -o /tmp/catalogue.zip* [*https://roboshop-builds.s3.amazonaws.com/catalogue.zip*](https://roboshop-builds.s3.amazonaws.com/catalogue.zip) 

```
cd /tmp            --> catalogue files downloaded under /tmp
```

```
ls -l
```

 

![30f69526-4553-4f4e-9bb5-53a93f6f5c35.png|746.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/30f69526-4553-4f4e-9bb5-53a93f6f5c35.png) [^58]

 

*Unzip now*

```
cd /app
```

```
unzip /tmp/catalogue.zip
```

```
ls -l
```

 

![306b2fed-da54-454f-807f-c92929ba48e4.png|818](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/306b2fed-da54-454f-807f-c92929ba48e4.png) [^59]

 

```
cat package.json
```

![1b0dd07a-dee5-4bca-9a3e-02b269a41a21.png|816](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/1b0dd07a-dee5-4bca-9a3e-02b269a41a21.png) [^60]

 

![ca283cbc-4be1-4b74-b412-9c4a78187fb0.png|843.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/ca283cbc-4be1-4b74-b412-9c4a78187fb0.png) [^61]

```
npm install
```

```
ls -l
```

![6c920879-d15a-4509-88d3-f282f92565b4.png|879.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/6c920879-d15a-4509-88d3-f282f92565b4.png) [^62]

 

![faceddbf-c840-46ac-b4a7-1d4fd78c7147.png|879.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/faceddbf-c840-46ac-b4a7-1d4fd78c7147.png) [^63]

 

![05dc8d68-91ef-4978-8b07-d33c59c0a996.png|639](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/05dc8d68-91ef-4978-8b07-d33c59c0a996.png) [^64]

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

*+++++give MongoDB private address here++++*

 

 

![d745fd57-1f32-442a-bf47-e367dfe2bf28.png|700](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/d745fd57-1f32-442a-bf47-e367dfe2bf28.png) [^65]

 

![6cc3542c-60c8-4225-8538-d9b268bf8f6c.png|768.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/6cc3542c-60c8-4225-8538-d9b268bf8f6c.png) [^66]

 

*Daemon Load the service.*

```
systemctl daemon-reload
```

 

![886a3153-7417-41e4-b5fe-c5e4d67be1b3.png|672](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/886a3153-7417-41e4-b5fe-c5e4d67be1b3.png) [^67]

 

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

 

![90e2d699-896b-4d7d-b4ee-7fb287bfcd18.png|729.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/90e2d699-896b-4d7d-b4ee-7fb287bfcd18.png) [^68]

 

 

*Now login to **Web server and update the IP address for catalogue private IP**..*

```
vim /etc/nginx/default.d/roboshop.conf
```

```
cat /etc/nginx/default.d/roboshop.conf
```

```
systemctl restart nginx
```

![037b5073-8207-47ca-8a70-2f1a64bd979d.png|851.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/037b5073-8207-47ca-8a70-2f1a64bd979d.png) [^69]

 

![e777771a-4781-4b55-ad50-631b322d13fe.png|861.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e777771a-4781-4b55-ad50-631b322d13fe.png) [^70]

 

![2b6d1772-f2d7-4541-aec3-37e656c0661f.png|866.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/2b6d1772-f2d7-4541-aec3-37e656c0661f.png) [^71]

 

*It showing something is not modified*

 

[*http://54.197.5.96/api/catalogue/categories*](http://54.197.5.96/api/catalogue/categories) 

 

*304 --> not modified    --> I have installed mongo db but I haven't pushed data*

 

![f9264e26-a2eb-4a61-ae9e-0f260be05d86.png|833.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/f9264e26-a2eb-4a61-ae9e-0f260be05d86.png) [^72]

 

 

*Now we need push data to mongo DB  -- **Now perform changes in catalogue server***

![05d7a207-de23-4eb1-b282-fe8dfeec54f1.png|724](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/05d7a207-de23-4eb1-b282-fe8dfeec54f1.png) [^73]

 

![19312bcc-bc8f-4852-b43f-009d58410a13.png|861](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/19312bcc-bc8f-4852-b43f-009d58410a13.png) [^74]

 

```
vim /etc/yum.repos.d/mongo.repo 
```

*------------*

*<mark>\[mongodb-org-4.2\]</mark>*

*<mark>name=MongoDB Repository</mark>*

*<mark>baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/</mark>*

*<mark>gpgcheck=0</mark>*

*<mark>enabled=1</mark>*

*-------------*

 

```
cat /etc/yum.repos.d/mongo.repo
```

![e43a727c-4566-45df-9ce9-3b544e0d1a5d.png|849.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/e43a727c-4566-45df-9ce9-3b544e0d1a5d.png) [^75]

 

***Now installing a client package:***

```
dnf install mongodb-org-shell -y
```

![7eeb52d2-1a7a-4dc5-aea0-cbd52158cdc2.png|901.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/7eeb52d2-1a7a-4dc5-aea0-cbd52158cdc2.png) [^76]

 

```
cd /app
```

```
ls -l
```

```
cat schema/catalogue/js           --> we can see some default products here.
```

![daee2f1f-7bc3-483d-9711-4d96523c505a.png|812.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/daee2f1f-7bc3-483d-9711-4d96523c505a.png) [^77]

 

 

***Now loading schema***

 ***--172.31.39.106   this is mongo DB server private IP***

```
mongo --host 172.31.39.106 </app/schema/catalogue.js       
```

 

![522b012e-8262-4906-8e9f-9aaf6898134e.png|832.3333740234375](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/522b012e-8262-4906-8e9f-9aaf6898134e.png) [^78]

 

```
 systemctl restart catalogue
```

![7bacfe5d-93ad-47a2-8851-8205db95696b.png|802](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/7bacfe5d-93ad-47a2-8851-8205db95696b.png) [^79]

 

 

***Now check the webpage: now you will see the products in catalogue***

![99e1ed34-648b-4c69-8c3f-71c02f273d91.png|846](https://images.amplenote.com/8381b170-0e8e-11ef-9be8-a6f126245c9e/99e1ed34-648b-4c69-8c3f-71c02f273d91.png) [^80]

 

\

 

\

\

 

\

 

[^1]: Roboshop Architecture
    WEB TIER
    API TIER
    DB TIER
    CATALOGUE
    MONGODB
    CART
    WEB
    USER
    REDIS
    USER
    SHIPPING
    MYSQL
    PAYMENTS
    RABBIT MQ
    RATINGS

[^2]: Create security group info
    A security group acts as a virtual firewall for your instance to control inbound and outbound traffic. To create a new security group, complete the fields below.
    Basic details
    Security group name Info
    SG_Allow_All
    Name cannot be edited after creation.
    Description Info
    Allowing all firewalls
    VPC Info
    vpc-0817cae8968304c06
    Inbound rules Info
    Type Info
    Protocol Info
    Port range Info
    Source Info
    Description - optional Info
    All TCP
    TCP
    0 - 65535
    Anywh...
    Q
    Delete
    0.0.0.0/0 X
    Add rule
    A Rules with source of 0.0.0.0/0 or :/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only.
    X

[^3]: Security Groups (1/5) Info
    G
    Actions V
    Export security groups to CSV
    V
    Create security group
    Find resources by attribute or tag
    < 1 >
    -
    Name
    Security group ID
    4
    Security group name
    4
    VPC ID
    4
    Description
    V
    SG1_Allow-All
    sg-0d20035c3943d6a29
    SG1_Allow-All
    vpc-0817cae89b8304c06 \[2
    Allowing all traffic for a pra
    0
    Frontend_SG
    sg-020b9258c6db847af
    Frontend_SG
    vpc-0817 cae8968304c06 \[2
    This is frontend SG, which
    sg-029974043a4090491
    default
    vpc-0817 cae89b8304c06 \[2
    default VPC security group
    sg-0c9db47e9b4d484b6
    SG_Allow_All
    vpc-0817 cae89b8304c06 \[
    Allowing all firewalls
    sg-Ofa371a4689ab653a
    Backend_SG_payment
    vpc-0817 cae898304c06 \[2
    This SG is created for paym
    sg-Od20035c3943d6a29 - SG1_Allow-All
    Details
    Inbound rules
    Outbound rules
    Tags
    Inbound rules (1)
    C
    Manage tags
    Edit inbound rules
    Q Search
    <1 >
    0
    Name
    Security group rule... V IP version
    4
    Type
    Protocol
    4
    Port range
    4
    Source
    sgr-0a806f8e5553e8603
    IPV4
    All traffic
    All
    All
    0.0.0.0/0

[^4]: Name
    Web
    Add additional tags
    Summary
    Number of instances I
    Application and OS Images (Amazon Machine Image) Info
    1
    An AMI is a template that contains the software configuration (operating system, application server, and
    Software Image (AMI)
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Centos-8-DevOps-Practice
    below
    ami-03265a0778a880afb
    Q Centos-8-DevOps-Practice
    X
    Virtual server type (instance type)
    t2.micro
    AMI from catalog
    Quick Start
    Firewall (security group)
    New security group
    Amazon Machine Image (AMI)
    Q
    Storage (volumes)
    Centos-8-DevOps-Practice
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
    Review commands
    Instance type
    t2.micro
    Free tier eligible
    Family: t2 1 vCPU 1 GiB Memory Current generation: true
    All generations
    On-Demand Windows base pricing: 0.0162 USD per Hour
    On-Demand SUSE base pricing: 0.0116 USD per Hour

[^5]: Choose an Amazon Machine Image (AMI)
    An AMI is a template that contains the software configuration (operating system, application server, and applications)
    required to launch your instance. You can select an AMI provided by AWS, our user community, or the AWS Marketplace; or
    you can select one of your own AMIs.
    Selected AMI: Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type (ami-Ofa 1ca9559f1892ec) (Quickstart AMIs)
    Q Centos-8-DevOps-Practice
    X
    Quickstart AMIs (0)
    My AMIs (0)
    AWS Marketplace AMIs (4492)
    Community AMIs (1)
    Commonly used AMIs
    Created by me
    AWS & trusted third-party AMIs
    Published by anyone
    Refine results
    Centos-8-DevOps-Practice (1 filtered, 1 unfiltered)
    < 1
    Clear all filters
    Community AMIs
    Community AMIs contain all AMIs that are public, therefore anyone can publish an AMI and it will show in this catalog. This catalog can also contain paid products. When
    Operating system
    using community AMIs it is best practice to ensure you know and trust the publisher before launching an AMI.
    Linux/Unix
    Centos-8-DevOps-Practice
    O All Linux/Unix
    ami-03265a0778a880afb
    Amazon Linux
    CentOS
    Select
    OwnerAlias: - Platform: Cent OS Architecture: x86_64 Owner: 973714476881 Publish date: 2023-06-04 Root device type: ebs Virtualization: hvm
    O CentOS
    ENA enabled: Yes
    Debian
    Fedora
    Gentoo
    O macOS
    The following results for "Centos-8-DevOps-Practice" were found in other categories

[^6]: Key pair name - required
    Select
    X
    Create new key pair
    Number of instances
    Info
    Network settings Info
    Edit
    Software Image (AMI)
    Centos-8-DevOps-Practice
    ami-03265a0778a880afb
    Network Info
    Virtual server type (instance type)
    vpc-0817 cae8968304c06
    t2.micro
    Subnet Info
    No preference (Default subnet in any availability zone)
    Firewall (security group)
    SG_Allow_All
    Auto-assign public IP Info
    Enable
    Storage (volumes)
    1 volume(s) - 10 GiB
    Firewall (security groups) Info
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    Free tier: In your first year includes
    X
    Create security group
    Select existing security group
    750 hours of t2.micro (or t3.micro in
    the Regions in which t2.micro is
    Common security groups Info
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
    Cancel
    Launch instance
    Configure storage Info
    Advanced
    Review commands
    1x
    10
    GIB
    gp2
    Root volume (Not encrypted)

[^7]: S? PUTTY Configuration
    X
    Category:
    - Session
    Basic options for your PUTTY session
    L. Logging
    E- Tominal
    D' PUTTY Configuration
    X
    Keyb
    - Featu
    Category:
    E- Window
    . Session
    Basic options for your PUTTY session
    . Appe
    L. Logging
    Beha
    . Terminal
    Specify the destination you want to connect to
    Trans
    Keyboard
    Host Name (or IP address)
    Port
    - Seled
    Colou
    Bel
    22
    - Connectic
    Features
    Connection type:
    Rata
    . Window
    Appearance
    O SSH O Serial OOther: Telnet
    8-SSH
    Behaviour
    Serial
    Translation
    - Telne
    Load, save or delete a stored session
    Rlook
    + Selection
    Colours
    Saved Sessions
    SUP
    E. Connection
    CentOS-8
    Data
    Default Settings
    Load
    About
    Proxy
    DevOps
    . SSH
    Save
    Serial
    Telnet
    Delete
    Rlogin
    SUPDUP
    Close window on exit:
    O Always Never
    Only on clean exit
    About
    Open
    Cancel

[^8]: alon
    Configure the appearance of PUTTY's window
    Logginn
    ainal
    De PUTTY Configuration
    X
    Keybe
    Category:
    Feat
    B. Session
    Data to send to the server
    . Logging
    . Terminal
    Login details
    Trans
    Keyboard
    Auto-login username
    centos
    Bell
    When username is not specified:
    nect
    . Features
    Data
    -. Window
    Prompt Use system username (chowd)
    Proxy
    Appearance
    SSH
    Terminal details
    Behaviour
    Serial
    Translation
    xterm
    Telne
    Terminal-type string
    Rlogit
    +. Selection
    38400,38400
    SUP
    Colours
    Terminal speeds
    E. Connection
    Data -
    Environment variables
    Proxy
    out
    Variable
    Add
    .SSH
    Serial
    Value
    Remove
    Telnet
    Rlogin
    SUPDUP
    About
    Open
    Cancel

[^9]: PUTTY Configuration
    tegory:
    - Session
    Configure the appearance of PUTTY's window
    L. Logginn
    By PUTTY Configuration
    X
    s check
    Alarms
    Tominal
    - Keyb
    Category:
    No alar
    Font
    Session
    Configure the appearance of PUTTY's window
    . Logging
    No alar
    Font:
    Adjust the use of the cursor
    . Terminal
    Cour
    Keyboard
    Cursor appearance:
    No alar
    Cour
    Bell
    Block
    O Underline
    O Vertical line
    Fixe
    Features
    Cursor blinks
    No alar
    Luci
    . Window
    Luci
    Appearance-
    Font settings
    MS G
    Behaviour
    Font used in the terminal window
    NSin
    Translation
    + Selection
    Font: Courier New, 10-point
    Change..-
    Colours
    Allow
    . Connection
    Font
    X
    - Data
    Font qua
    Proxy
    Antial
    +. SSH
    O Clear
    Font:
    Font style:
    Size:
    Serial
    Adjust the
    Courier New
    Bold
    12
    Telnet
    Rlogin
    Courier New
    Regular
    10
    Hide
    SUPDUP
    Fixedsys
    Italic
    11
    Adjust the Lucida Console
    Bold
    12
    Show
    Lucida Sans Typewrit
    Bold Italic
    14
    Gap bety
    MS Gothic
    16
    OSunk
    NSimSun
    18
    SimSun-ExtB
    20
    About
    Terminal
    22
    Sample

[^10]: PUTTY Configuration
    X
    tegory:
    Session
    Basic options for your PUTTY session
    L. Logginn
    s che
    Tominal
    PUTTY Configuration
    X
    -Keyb
    Feat
    Category:
    Window
    . Session
    Basic options for your PUTTY session
    Appe
    . Logging
    Beha
    Specify the destination you want to connect to
    .Terminal
    . Tran
    Keyboard
    Host Name (or IP address)
    Port
    - Seled
    22
    - Color
    Bell
    Connectic
    Features
    . Window
    Connection type:
    - Data
    Proxy
    Appearance
    O SSH O Serial OOther: Telnet
    - SSH
    Behaviour
    Serial
    Translation
    Telne
    Load, save or delete a stored session
    - Rlogi
    +. Selection
    Saved Sessions
    SUP
    .Colours
    . Connection
    CentOS-8
    Data
    Default Settings
    Load
    About
    - Proxy
    CentOS-8
    . SSH
    DevOps
    Save
    Serial
    Telnet
    Delete
    Rlogin
    SUPDUP
    Close window on exit:
    O Always Never
    Only on clean exit
    About
    Open
    Cancel

[^11]: Instances (1/1) Info
    C
    Connect
    Instance state V
    Actions
    Launch instances
    V
    Q Find Instance by attribute or tag (case-sensitive)
    < 1
    V
    Name _
    V
    Instance ID
    Instance state
    4
    Instance type
    Status check
    Alarm status
    Availability Zone
    Pub
    Web
    i-079429b4326698901
    Running
    t2.micro
    2/2 checks passed No alarms +
    us-east-1d
    2c2
    Instance: i-079429b4326698901 (Web)
    X
    Details
    Security
    Networking
    Storage
    Status checks
    Monitoring
    Tags
    Public IPV4 address copi
    Instance summary Info
    ed
    Instance ID
    Private IPv4 addresses
    i-079429b4326698901 (Web)
    3.85.61.63 \|open address \[
    172.31.19.108
    IPv6 address
    Instance state
    Public IPV4 DNS
    Running
    ec2-3-85-61-63.compute-1.amazonaws.com \|open
    address \[

[^12]: SuperPUTTY
    File View Tools Help
    Protocol SSH
    Host 3.85.61.63
    Login
    Password
    Session CentOS-8
    O X
    Commands

[^13]: Protocol SSH
    Host 3.85.61.63
    Login
    Password
    Session CentOS-8
    - O X
    Commands
    3.85.61.63
    PUTTY Security Alert
    X
    The host key is not cached for this server:
    3.85.61.63 (port 22)
    You have no guarantee that the server is the computer you think it is.
    The server's sshed25519 key fingerprint is:
    ssh-ed25519 255 SHA256:+ESjZ/lifxqdN40haLogLdS3jMnIGUAcPMMGA8Sgkuc
    If you trust this host, press "Accept" to add the key to PUTTY's cache and cany on
    connecting.
    If you want to cany on connecting just once, without adding the key to the cache, press
    "Connect Once".
    If you do not trust this host. press "Cancel" to abandon the connection.
    More info...
    Accept
    Connect Once
    Cancel

[^14]: SuperPUTTY - WEB
    File View Tools Help
    Protocol SSH
    . Host 3.85.61.63
    Login
    Password
    Session CentOS-8
    .O X
    Commands
    WEB
    3. 85. 61.63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ centos(ip-172-31-19-108 \~ \]$

[^15]: 01-WEB
    . The Web/Frontend is the service in RoboShop to serve the web content over Nginx.
    . This will have the web page for the web application.
    . Developer has chosen Nginx as a web server and thus we will install Nginx Web Server.

[^16]: 3. 85. 61. 63 \| 172 . 31.19.108 \| t2.micro \| null
    \[ centos@ip-172-31-19-108 \~ \]$ sudo su -
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 \~ \]# anf install nginx -y
    Centos Stream 8 - AppStream
    54 MB/S \|
    34 MB
    00:00
    Centos Stream 8
    - BaseOS
    45 MB/S
    55 MB
    00 : 01

[^17]: \[ root@ip-172-31-19-108 \~ \]# systemctl enable nginx
    Created symlink /etc/systemd/system/multi-user . target. wants/nginx. service - /usr/lib/systemd/system/nginx
    service .
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 \~ \]# systemctl start nginx
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 \~ \]#

[^18]: 3. 85. 61. 63 \| 172 . 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 \~ \]# systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Wed 2023-12-06 06:28:33 UTC; 6min ago
    Process: 16355 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 16353 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 16352 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0 /SUCCESS)
    Main PID: 16357 (nginx)
    Tasks: 2 (limit: 4440)

[^19]: \[ root@ip-172-31-19-108 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    top
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:80
    0.0.0.0:\*
    LISTEN
    16357/nginx: master
    top
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    831/sshd
    OOOooo
    tcp6
    0 : : :111
    : ::\*
    LISTEN
    1/systemd
    tcp6
    0 :: :80
    LISTEN
    16357/nginx: master
    tcp6
    0 : : :22
    LISTEN
    831/sshd
    3. 85. 61. 63 \| 172. 31.19.108 \| t2.micro \| null

[^20]: D Instances \| EC2 \| us-east-1
    x notes/session-07.txt at master . X
    roboshop-documentation/01-w X DAWS-765 - YouTube
    X
    Test Page for the Nginx HTTP SE X
    +
    C
    Not secure 3.85.61.63
    Welcome to nginx on Red Hat Enterprise Linux!
    This page is used to test the proper operation of the nginx HTTP server after it has been installed. If you can read this page, it means that the web server installed at this site is working properly.
    Website Administrator
    This is the default index. html page that is distributed with nginx on Red Hat Enterprise Linux. It is located in /usr/ share/nginx/html.
    You should now put your content in a location of your choice and edit the root configuration directive in the nginx configuration file /etc/nginx/nginx. conf.
    For information on Red Hat Enterprise Linux, please visit the Red Hat, Inc. website. The documentation for Red Hat Enterprise Linux is available on the Red Hat, Inc. website.
    NGINX
    POWERED BY
    redhat.

[^21]: \[ root@ip-172-31-19-108 \~ \]# cd /etc/nginx/
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

[^22]: \[ root@ip-172-31-19-108 /etc/nginx \]# cd /usr/share/nginx/html/
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]#
    3. 85. 61. 63 \| 172. 31.19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# 1s -1
    total 24
    -rw-r--r-- 1 root root 3971 Dec 21 2021 404. html
    r-- 1 root root 4020 Dec 21
    2021 50x . html
    -rw-r--r-- 1 root root 4057 Dec 21
    2021 index. html
    -rw-r--r-- 1 root root 368 Dec 21
    2021 nginx-logo . png
    rw-
    -- 1 root root 4148 Dec 21
    2021 poweredby . png

[^23]: 3. 85 . 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ rootdip-172-31-19-108 /usr/share/nginx/html \]# rm -rf /usr/share/nginx/html/\*
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# 1s -1
    total 0

[^24]: 3. 85. 61. 63 \| 172. 31.19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# curl -o /tmp/web. zip https: //roboshop-builds . s3 . amazonaw
    s . com/web . zip
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
    8102k
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# cd /tmp/

[^25]: \[ root@ip-172-31-19-108 /tmp \]# 1s -1
    total 1108
    -rw-r--r--
    1 root root
    222 Dec 6 06:50 idle. out
    drwx----
    -
    3 root root
    17 Dec 6 06:05 systemd-private-e3bc5120
    ice-IIgQHx
    drwx--
    - - -
    3 root root
    17 Dec 6 06:28 systemd-private-e3bc5120
    e-nc8j ZD
    -rw-r--r-- 1 root root 1128410 Dec 6 06:57
    web . zip

[^26]: 3. 85. 61.63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /tmp \]# cd /usr/share/nginx/html/
    3. 85. 61. 63 \| 172. 31.19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# unzip /tmp/web . zip
    Archive: /tmp/web . zip
    inflating: cart. html
    creating: css/
    inflating: css/auto-complete . css
    inflating: css/style . css
    inflating: empty . html

[^27]: \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# 1s -1
    total 44
    -rw-r--r-- 1 root root 1335 Dec
    1 2022 cart.html
    drwxr-xr-x 2 root root
    48 Dec 2
    2022 css
    -rw-r--r-- 1 root root
    77 Dec 1
    2022 empty . html
    -rw-r--r-- 1 root root
    441 Dec
    1 2022 eum. html

[^28]: Instances \| EC2 \| us-east-1
    notes/session-07.txt at master . X (roboshop-documentation/01-w X
    DAWS-765 - YouTube
    X
    Stan's Robot Shop
    X
    +
    C
    A Not secure 3.85.61.63
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
    has been built using various technologies.
    AngularJS (1.x)
    .Nginx
    NodeJS
    Java
    Python
    Golang
    PHP (Apache)
    MongoDB

[^29]: HotStar US
    VPN
    O
    OC
    US
    India

[^30]: Intemet
    Cisco VPN
    Access Restriction
    Traffic monitoring
    Office Network

[^31]: App
    DB
    Load Balancer
    Web
    Client
    fb n/w

[^32]: \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# vim /etc/nginx/default.d/roboshop. conf
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]#
    3. 85. 61. 63 \| 172. 31. 19.108 \| t2.micro \| null
    \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# cat /etc/nginx/default.d/roboshop . conf
    proxy http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: //localhost: 8080/; }
    location /api/user/ { proxy_pass http: //localhost: 8080/;}
    location /api/cart/ { proxy_pass http: //localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: //localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access log off;

[^33]: \[ root@ip-172-31-19-108 /usr/share/nginx/html \]# systemctl restart nginx

[^34]: Stan's Robot Shop
    Search
    Login / Register
    Welcome to Stan's Robot Shop
    Cart
    STAN
    Here you will find all of Stan's friends. Have a browse around and
    Empty
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    has been built using various technologies.
    AngularJS (1.x)
    Nginx
    NodeJS
    Java
    Python
    Golang
    PHP (Apache)
    MongoDB
    Redis
    MySQL
    When deployed into an environment monitored by Instana, these
    technology stacks will be automatically detected and monitored
    all with minimum configuration. Every request will be traced end to
    end. Stan will keep an eye on all those metrics, events and traces
    and let you know what needs your attention.
    To find out more visit the Instana site.
    All the code is available on Github

[^35]: A Not secure 3.85.61.63
    AD Welcome
    Network X
    > >
    +
    @ 5 0 52
    503
    X
    Stan's Robot Shop
    Search
    0 0 - Q Preserve log Disable cache No throttling
    503
    Filter
    O Invert Hide data URLs O Hide extension URLs
    Login / Register
    All Doc JS Fetch/XHR CSS Font Img Media Manifest WS Wasm Other
    O Blocked response cookies
    O Blocked requests O 3rd-party requests
    Cart
    STAN
    200 ms
    400 ms
    600 ms
    800 ms
    1000 ms
    1200 ms
    Empty
    Categories
    Name
    Status Type Initiator
    Size Time F... Waterfall
    Welcome to Stan's Robot Shop
    E 3.85.61.63
    304
    do... Other
    18... 36...
    Here you will find all of Stan's friends. Have a browse around and
    < css?family=Orb...
    styl... (index):...
    OB 10...
    see who is here.
    style.css
    200
    styl... 3.85.61....
    OB Oms (...
    auto-complete... 200
    styl... 3.85.61....
    OB Oms (...
    This is a simple example microservices ecommerce application. It
    stan.png
    200
    png 3.85.61....
    OB Oms (...
    has been built using various technologies:
    < angular.js
    200
    scri... 3.85.61....
    OB Oms (...
    AngularJS (1.X)
    <>angular-route.js
    200
    scri... 3.85.61....
    OB Oms (...
    Nginx
    <> auto-complete.js 200
    scri... 3.85.61....
    OB Oms (...
    NodeJS
    <> controller.js
    200
    scri... 3.85.61....
    OB Oms (...
    -
    Java
    categories
    404
    xhr
    angular... 72... 23...
    Python
    uniqueid
    404
    xhr
    angular... 72... 23...
    Golang
    splash.html
    200
    xhr
    angular...
    OB 4 ms (...
    PHP (Apache)
    \* categories
    404
    xhr
    angular... 72... 43...
    MongoDB
    404
    xhr
    angular... 72...
    Redis
    x uniqueid
    MySQL
    instana_icon_s...
    200
    png
    Other
    OB 19 ... (...
    D graph.png
    200
    ong style.css
    OB Oms (...
    When deployed into an environment monitored by Instana, these
    technology stacks will be automatically detected and monitored,
    all with minimum configuration. Every request will be traced end to
    end. Stan will keep an eye on all those metrics, events and traces
    and let you know what needs your attention.
    To find out more visit the Instana site.

[^36]: Name
    X Headers Preview Response Initiator Timing
    3.85.61.63
    General
    x css? family=Orbitron
    Request URL:
    style.css
    http://3.85.61.63/api/catalogu
    e/categories
    auto-complete.css
    Request Method:
    GET
    stan.png
    Status Code:
    404 Not Found
    <> angular.js
    Remote Address:
    3.85.61.63:80
    <> angular-route.js
    Referrer Policy:
    strict-origin-when-cross-origi
    <> auto-complete.js
    n
    <> controller.js
    X
    categories
    Response Headers
    O Raw
    \* uniqueid
    Connection:
    keep-alive
    O splash.html
    Content-Length:
    571
    X
    categories
    Content-Type:
    text/html
    \* uniqueid
    Date:
    Wed, 06 Dec 2023
    instana_icon_square.png
    07:30:06 GMT
    I graph.png
    Server:
    nginx/1.14.1
    Request Headers
    Raw
    Accept:
    application/json, text/plain,
    \* /\*
    Accept-Encoding:
    gzip, deflate
    Accept-I anguage:
    en-US,en;q=0.9

[^37]: MongoDB
    . Developer has chosen the database MongoDB.
    . Hence, we are trying to install it up and configure it.
    NOTE: Versions of the DB Software you will get context from the developer, Meaning we need to check with developer. Developer has
    shared the version information as MongoDB-4.x

[^38]: MongoDB
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
    Q Devops-practice
    X
    Virtual server type (instance type)
    t3.micro
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
    T17:05:56.00
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
    t3.micro
    Family: t3 2 vCPU 1 GiB Memory Current generation: true
    . All generations
    On-Demand SUSE base pricing: 0.0104 USD per Hour
    On-Demand Linux base pricing: 0.0104 USD per Hour
    On-Demand RHEL base pricing: 0.0704 USD per Hour
    Compare instance types

[^39]: Key pair (login) Info
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
    t3.micro
    Network settings Info
    Edit
    Firewall (security group)
    SG_Allow_All
    Network Info
    vpc-0817 cae89b8304c06
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
    Firewall (security groups) Info
    unavailable) instance usage on free
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    tier AMIs per month, 30 GiB of EBS
    instance.
    storage, 2 million IOs, 1 GB of
    O Create security group
    snapshots, and 100 GB of bandwidth
    Select existing security group
    to the internet.
    Common security groups Info
    Select security groups
    C
    Compare security
    Cancel
    Launch instance
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    VPC: vpc-0817cae8968304c06
    Review commands
    Security groups that you add or remove here will be added to or removed from all your network interfaces.

[^40]: \[ centos@ip-172-31-39-106 \~ \]$ sudo su -
    54 . 209.226.184 \| 172. 31.39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]# vim /etc/yum. repos . d/mongo . repo
    54 . 209. 226.184 \| 172. 31. 39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]# cat /etc/yum. repos . d/mongo . repo
    \[mongodb-org-4 . 2\]
    name=MongODB Repository
    baseurl=https: / /repo . mongodb . org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    gpgcheck=0
    enabled=1
    54 . 209. 226.184 \| 172. 31. 39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]#

[^41]: \[ root@ip-172-31-39-106 \~ \]# dnf install mongodb-org -y
    Centos Stream 8 - AppStream
    28 MB/S \|
    34 MB
    00 : 01
    Centos Stream 8 - BaseOS
    29 MB/S
    55 MB
    00: 01
    Centos Stream 8 - Extras
    239 kB/s \|
    18 KB
    00: 00
    Centos Stream 8 - Extras common packages
    33 kB/s \| 6.9 kB
    00:00
    Extra Packages for Enterprise Linux 8 - x86 64
    16 MB/S \|
    16 MB
    00: 00
    MongoDB Repository
    447 KB/s \|
    41 KB
    00:00
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Si
    Installing:
    mongodb-org
    x86 64
    4. 2.24-1. e18
    mongodb-org-4 . 2
    11
    Installing dependencies:
    mongodb-org-mongos
    x86 64
    4.2.24-1. e18
    mongodb-org-4 .2
    11
    mongodb-org-server
    x86 64
    4.2.24-1. e18
    mongodb-org-4 .2
    20

[^42]: \[ root@ip-172-31-39-106 \~ \]# systemctl enable mongod
    54 . 209 . 226.184 \| 172.31. 39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]# systemctl start mongod
    54 . 209. 226. 184 \| 172. 31. 39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]# systemctl status mongod
    mongod . service - MongODB Database Server
    Loaded: loaded (/usr/lib/systemd/system/mongod. service; enabled; vendor preset: disabled)
    Active: active (running) since Wed 2023-12-06 16:38:48 UTC; 47s ago
    Docs: https : / /docs . mongodb . org/manual

[^43]: \[ root@ip-172-31-39-106 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 127 . 0. 0.1:27017
    0.0.0.0:\*
    LISTEN
    5129/mongod
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    815/sshd
    tcp6
    0 :: :111
    : ::\*
    LISTEN
    1/systemd
    tcp6
    0 :: :22
    LISTEN
    815/sshd
    54 . 209. 226.184 \| 172. 31.39.106 \| t3.micro \| null

[^44]: Usually MongoDB opens the port only to localhost(127.0.0.1), meaning this service can be accessed by the application that is hosted on this
    server only. However, we need to access this service to be accessed by another server(remote server), So we need to change the config
    accordingly.
    Update listen address from 127.0.0.1 to 0.0.0.0 in /etc/mongod.conf
    You can edit file by using

[^45]: #
    network interfaces
    net:
    port: 27017
    bindIp: 0.0.0.0 \| # Enter 0.0.0.0, :: to bind to all IPV4 and IPV6 addresses or, alternatively, use
    et. bindIpAll setting.

[^46]: 54 . 209. 226.184 \| 172. 31 . 39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]# systemctl restart mongod
    54 . 209 . 226. 184 \| 172. 31. 39.106 \| t3.micro \| null
    \[ root@ip-172-31-39-106 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0. 0. 0. 0:270172
    0.0.0.0:\*
    LISTEN
    5235/mongod
    tcp
    OOO
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    815/sshd
    tcp6
    0 :: :111
    :::
    LISTEN
    1/systemd
    top6
    0
    0 : : :22
    LISTEN
    815/sshd
    54 . 209 .226.184 \| 172. 31. 39.106 \| t3.micro \| null

[^47]: Catalogue
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
    On-Demand SUSE base pricing: 0.0116 USD per Hour
    Compare instance types

[^48]: Key pair name - required
    Software Image (AMI)
    Centos-8-DevOps-Practice
    Proceed without a key pair (Not recommended)
    Default value
    Create new key pair
    ami-03265a0778a880afb
    Virtual server type (instance type)
    t2.micro
    Network settings Info
    Edit
    Firewall (security group)
    SG_Allow_All
    Network
    Info
    vpc-0817 cae8968304c06
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
    Firewall (security groups) Info
    unavailable) instance usage on free
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    tier AMIs per month, 30 GiB of EBS
    instance.
    storage, 2 million IOs, 1 GB of
    snapshots, and 100 GB of bandwidth
    O Create security group
    O Select existing security group
    to the internet.
    Common security groups Info
    Select security groups
    C
    Compare security
    Cancel
    Launch instance
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    VPC: vpc-0817cae8968304c06
    Review commands
    Security groups that you add or remove here will be added to or removed from all your network interfaces.

[^49]: Catalogue
    Catalogue is a microservice that is responsible for serving the list of products that displays in roboshop application.
    Developer has chosen Nodels, Check with developer which version of NodeJS is needed. Developer has set a context that it can work with
    NodeJS > 18
    Install NodeJS, By default NodeJS 10 is available, We would like to enable 18 version and install list.

[^50]: Protocol SSH
    Host 35.172.201.219
    Login
    Password
    Session
    CentOS-8
    - O X
    Commands
    WEB
    MongoDB
    catalogue
    35 . 172 . 201.219 \| 172. 31. 28.155 \| t2.micro \| null
    \[ centos@ip-172-31-28-155 \~ \]$

[^51]: \[ root@ip-172-31-28-155 \~ \]# anf module disable nodejs -y
    Centos Stream 8 - AppStream
    21 MB/S \|
    34 MB
    00 : 01
    Centos Stream 8 - BaseOS
    18 MB/S
    55 MB
    00: 03
    Centos Stream 8 - Extras
    233 kB/s
    18 KB
    00: 00
    Centos Stream 8 - Extras common packages
    32 kB/s \| 6.9 kB
    00: 00
    Extra Packages for Enterprise Linux 8 - x86 64
    18 MB/S \|
    16 MB
    00: 00
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Size
    Disabling modules:
    nodejs
    Transaction Summary
    Complete!
    35 . 172 . 201. 219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 \~ \]# dnf module enable nodejs: 18 -y
    Last metadata expiration check: 0:00:20 ago on Wed 06 Dec 2023 05:02:06 PM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Size
    Enabling module streams:

[^52]: \[ root@ip-172-31-28-155 \~ \]# anf install nodejs -y
    Last metadata expiration check: 0:04:33 ago on Wed 06 Dec 2023 05:02:06 PM UTC.
    Dependencies resolved.
    Package
    Arch
    Version
    Repository
    Size
    Installing :
    nodejs
    x86 64
    1:18.9.1-1 . module e18 . 7. 0+1220+0be9752c
    appstream
    13 M
    Installing weak dependencies:
    nodejs-docs
    noarch
    1:18. 9. 1-1 . module e18 . 7. 0+1220+0be9752c
    appstream
    9.4 M
    nodejs-full-i18n
    x86 64
    1:18.9.1-1 . module e18 . 7. 0+1220+0be9752c
    appstream
    8.0 M
    nom
    x86 64
    1:8.19. 1-1. 18. 9. 1. 1 . module e18 . 7. 0+1220+0be9752c
    appstream
    2.0 M
    Transaction Summary
    Install 4 Packages
    Total download size: 33 M
    Installed size: 160 M

[^53]: Configure the application.
    Our application developed by the developer of our company and it is not having any RPM software just like other softwares. So we need to
    configure every step manually

[^54]: User roboshop is a function / daemon user to run the application. Apart from that we don't use this user to login to server.
    Also, username roboshop has been picked because it more suits to our project name.
    We keep application in one standard location. This is a usual practice that runs in the organization.

[^55]: \[ root@ip-172-31-28-155 \~ \]# useradd roboshop
    35 . 172 . 201.219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 \~ \]#

[^56]: \[ root@ip-172-31-28-155 \~ \]# mkdir /app

[^57]: \[ root@ip-172-31-28-155 \~ \]# cd /
    35 . 172 . 201. 219 \| 172.31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 / \]# 1s -1
    total 20
    drwxr-xr-x
    2 root root
    6 Dec 6 17:13 app
    lrwxrwxrwx .
    1 root root
    7 Jun 22 2021 bin -> usr/bin
    dr-xr-xr-x.
    6 root root 4096 Dec 6 16:57 boot
    drwxr-xr-x
    18 root root 2640 Dec
    6 16:56 dev

[^58]: \[ root@ip-172-31-28-155 / \]# curl -o /tmp/catalogue. zip https: //roboshop-builds . s3 . amazonaws . com/catalogu
    e . zip
    8 Total
    8 Received % Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    100 3097 100 3097
    0
    0
    46223
    0
    --
    46223
    35 . 172 . 201.219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 / \]# cd /tmp
    35 . 172 . 201. 219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /tmp \]# 1s -1
    total 8
    -rw-r--r--
    1 root root 3097 Dec 6 17:15 catalogue . zip
    -rw-r--r--
    1 root root 222 Dec 6 17:10 idle. out
    drwx-
    3 root root
    17 Dec 6 16:56 systemd-private-29af4780d6e54ee2b0007b0fa8d5b5c5-chronyd. service
    qs9Bhs

[^59]: \[ root@ip-172-31-28-155 /tmp \]# cd /app
    35. 172 . 201.219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# unzip /tmp/catalogue . zip
    Archive: /tmp/catalogue . zip
    inflating: package . json
    creating: schema/
    inflating: schema/catalogue . js
    inflating: server . js
    35 . 172 . 201 . 219 \| 172.31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# 1s -1
    total 12
    rw-r--r-- 1 root root 490 Dec 1 2022 package . json
    drwxr-xr-x 2 root root
    26 Dec 3 2022 schema
    rw-r--r-- 1 root root 5336 Mar 27
    2023 server . js

[^60]: \[ root@ip-172-31-28-155 /app \]# cat package . json
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

[^61]: Every application is developed by development team will have some common softwares that they use as libraries. This application also have the
    same way of defined dependencies in the application configuration.
    Lets download the dependencies.

[^62]: \[ root@ip-172-31-28-155 /app \]# npm install
    nom WARN deprecated express-pino-logger@4.0.0: use pino-http instead
    added 178 packages, and audited 179 packages in 17s

[^63]: \[ root@ip-172-31-28-155 /app \]# 1s -1
    total 152
    drwxr-xr-x 163 root root
    8192 Dec 6 17:25 node modules
    rw-r--r-
    1 root root
    490 Dec
    1 2022 package . json
    -rw-r--r-
    1 root root 127491 Dec
    6 17:25 package-lock . json
    drwxr-xr-x
    2 root root
    26 Dec
    3
    2022 schema
    -rw-r--r--
    1 root root
    5336 Mar 27 2023 server. js
    35 . 172 . 201.219 \| 172.31.28.155 \| t2.micro \| null

[^64]: We need to setup a new service in systemd so systemctl can manage this service
    Setup SystemD Catalogue Service

[^65]: web
    mongodb
    catalogue
    \[Unit\]
    Description = Catalogue Service
    \[Service\]
    User-roboshop
    Environment=MONGO=true
    Environment=MONGO URL="mongodb : / /172 . 31 . 39 . 110:27017/catalogue"
    ExecStart=/bin/node /app/server. js
    SyslogIdentifier=catalogue
    \[Install\]
    WantedBy=multi-user . target

[^66]: \[ rootdip-172-31-28-155 /app \]# vim /etc/systemd/system/catalogue . service
    35. 172 . 201.219 \| 172. 31. 28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# cat /etc/systemd/system/catalogue . service
    \[Unit\]
    Description = Catalogue Service
    \[Service\]
    User=roboshop
    Environment=MONGO=true
    Environment=MONGO URL="mongodb : / /172 . 31 . 39 . 106:27017/catalogue"
    ExecStart=/bin/node /app/server. js
    SyslogIdentifier=catalogue
    \[Install\]
    WantedBy=multi-user . target

[^67]: \[ root@ip-172-31-28-155 /app \]# systemctl daemon-reload
    35 . 172 . 201.219 \| 172.31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]#

[^68]: \[ root@ip-172-31-28-155 /app \]# systemctl enable catalogue
    Created symlink /etc/systemd/system/multi-user . target. wants/catalogue . service - /etc/systemd/syst
    ogue . service.
    35 . 172 . 201. 219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# systemctl start catalogue
    35 . 172 . 201.219 \| 172. 31. 28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# systemctl status catalogue
    catalogue . service - Catalogue Service
    Loaded: loaded (/etc/systemd/system/catalogue. service; enabled; vendor preset: disabled)
    Active: active (running) since Wed 2023-12-06 17:39:46 UTC; 8s ago
    Main PID: 5806 (node)

[^69]: proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root
    /usr/share/nginx/html ;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: //172 . 31 . 28 .155:8080/; }
    location /api/user/ { proxy_pass http: //localhost: 8080/; }
    location /api/cart/ { proxy_pass http: //localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: //localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access_log off;

[^70]: \[ root@ip-172-31-17-119 / \]# vim /etc/nginx/default.d/roboshop . conf
    52 . 90.237.1 \| 172. 31.17.119 \| t2.micro \| null
    \[ root@ip-172-31-17-119 / \]# cat /etc/nginx/default.d/roboshop . conf
    proxy_http_version 1.1;
    location /images/ {
    expires 5s;
    root /usr/share/nginx/html ;
    try files $uri /images/placeholder . jpg;
    location /api/catalogue/ { proxy_pass http: //172 . 31 . 28 . 155:8080/; }
    location /api/user/ { proxy_pass http: //localhost: 8080/; }
    location /api/cart/ { proxy_pass http: //localhost: 8080/; }
    location /api/shipping/ { proxy_pass http: //localhost: 8080/; }
    location /api/payment/ { proxy_pass http: //localhost: 8080/; }
    location /health {
    stub status on;
    access log off;

[^71]: \[ root@ip-172-31-17-119 / \]# systemctl restart nginx
    52 . 90.237.1 \| 172. 31. 17.119 \| t2.micro \| null
    \[ root@ip-172-31-17-119 / \]# systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx . service; enabled; vendor pre
    Active: active (running) since Wed 2023-12-06 17:50:59 UTC; 27s ago
    Process: 5954 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)

[^72]: C
    . . .
    Not secure \| 52.90.237.1
    A Welcome
    Network X
    +
    3 0 53
    503
    X
    Stan's Robot Shop
    Search
    1 0 - Q Preserve log Disable cache No throttling
    T
    503
    Filter
    O Invert O Hide data URLs O Hide extension URLs
    Login / Register
    All Doc JS Fetch/XHR CSS Font Img Media Manifest WS Wasm Other
    Blocked response cookies
    O Blocked requests
    O 3rd-party requests
    Cart
    STAN
    200 ms
    400 ms
    600 ms
    800 ms
    1000 ms
    1200 ms
    1400 ms
    1600 n
    Empty
    Categories
    Welcome to Stan's Robot Shop
    Name
    X
    Headers
    Preview
    Response
    Initiator Timing
    E 52.90.237.1
    General
    Here you will find all of Stan's friends. Have a browse around and
    & css?family=Orbitron
    Request URL:
    http://52.90.237.1/api/catalog
    see who is here.
    style.css
    ue/categories
    auto-complete.css
    This is a simple example microservices ecommerce application. It
    Request Method:
    GET
    has been built using various technologies.
    stan.png
    Status Code:
    304 Not Modified
    @ angular.js
    Remote Address:
    52.90.257.1:80
    AngularJS (1.x)
    angular-route.js
    Referrer Policy:
    strict-origin-when-cross-origi
    Nginx
    < auto-complete.js
    n
    NodeJS
    <> controller.js
    Java
    {} categories
    Response Headers
    O Raw
    Python
    uniqueid
    Access-Control-Allow-Origin:
    Golang
    O splash.html
    Connection:
    keep-alive
    PHP (Apache)
    instana_icon_square.png
    Date:
    Wed, 06 Dec 2023
    MongoDB
    Redis
    (categories
    17:52:49 GMT
    MySQL
    uniqueid
    Etag:
    W/"2-
    D graph.png
    19FW4VUO7kr8CvBIt4za
    When deployed into an environment monitored by Instana, these
    MCqXZOw"
    technology stacks will be automatically detected and monitored,
    Server:
    nginx/1.14.1
    all with minimum configuration. Every request will be traced end to
    Timing-Allow-Origin:
    Stan will keep a
    eve on all those

[^73]: Client
    MongoDB Server

[^74]: For the application to work fully functional we need to load schema to the Database.
    Schemas are usually part of application code and developer will provide them as part of development.
    We need to load the schema. To load schema we need to install mongodb client.
    To have it installed we can setup MongoDB repo and install mongodb-client

[^75]: 35 . 172 . 201 . 219 \| 172. 31.28.155 \| t2.micro \| null
    \[ rootdip-172-31-28-155 /app \]# vim /etc/yum. repos . d/mongo . repo
    35 . 172 . 201.219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# cat /etc/yum. repos . d/mongo . repo
    \[mongodb-org-4 . 2\]
    name=MongoDB Repository
    baseurl=https: //repo . mongodb . org/yum/redhat/$releasever/mongodb-org/4 .2/x86_64/
    gpgcheck=0
    enabled=1

[^76]: \[ root@ip-172-31-28-155 /app \]# anf install mongodb-org-shell -y
    MongODB Repository
    289 kB/s \| 41 kB
    00 : 0
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Installing:
    mongodb-org-shell
    x86 64
    4. 2.24-1. e18
    mongodb-org-4 . 2
    Transaction Summary
    Install 1 Package

[^77]: \[ root@ip-172-31-28-155 /app \]# 1s -1
    total 152
    drwxr-xr-x 163 root root
    8192 Dec 6 17:25 node modules
    -rw-r--r--
    1 root root
    490 Dec
    1 2022 package . json
    -rw-r--r--
    1 root root 127491 Dec
    6 17:25 package-lock . json
    drwxr-xr-x
    2 root root
    26 Dec 3 2022 schema
    -rw-r--r--
    1 root root
    5336 Mar 27 2023 server . js
    35 . 172 . 201. 219 \| 172. 31.28.155 \| t2.micro \| null
    \[ root@ip-172-31-28-155 /app \]# cat schema/catalogue . js
    / / Products
    db = db . getSiblingDB ( ' catalogue' ) ;
    db . products . insertMany ( \[
    {sku: 'HAL-1' , name: 'HAL' , description: 'Sorry Dave, I cant do that' , price: 2001, instock: 2,
    ories: \['Artificial Intelligence' \]} ,
    {sku: 'PB-1' , name: 'Positronic Brain' , description: 'Highly advanced sentient processing unit
    he laws of robotics burned in' , price: 200, instock: 0, categories: \['Artificial Intelligence' \]},
    {sku: 'ROB-1' , name: 'Robbie' , description: 'Large mechanical workhorse, crude but effective. C
    n handy when you are lost in space' , price: 1200, instock: 12, categories: \['Robot' \] },
    {sku: 'EVE-1' ,
    name: 'Eve' , description: 'Extraterrestrial Vegetation Evaluator' , price: 5000

[^78]: \[ rootip-172-31-28-155 /app \]# mongo --host 172.31.39.106 </app/schema/catalogue. js
    MongoDB shell version v4 .2.24
    connecting to: mongodb: //172 . 31 . 39. 106:27017/?compressors=disabled&gssapiServiceName=mongodb
    Implicit session: session { "id" : UUID ("0996ef33-0686-4578-8437-101felblob18") }
    MongoDB server version: 4.2.24
    catalogue
    2023-12-06T18: 12: 31. 238+0000 E QUERY
    \[js\] uncaught exception: BulkWriteError ({
    "writeErrors" : \[
    "index" : 0,
    "code" : 11000
    "errmsg" : "E11000 duplicate key error collection: catalogue. product
    1 dup key: { sku: \\"HAL-1\\" }",
    "op" :
    {
    " id" : ObjectId ("6570b98fce42a60b04bf3aef") ,
    "sku" : "HAL-1" ,
    "name" : "HAL"
    "description" : "Sorry Dave, I cant do that"

[^79]: \[ root@ip-172-31-28-155 / app
    \]# systemctl restart catalogue

[^80]: C
    Not secure \| 52.90.237.1/product/ROB-1
    Stan's Robot Shop
    Login / Register
    Cart
    Robbie
    Empty
    Categories
    . Artificial
    Intelligence
    o HAL
    o Positronic
    Brain
    o Stan
    . Robot
    o C3PO
    o Eve
    o K9
    o Kryten
    Marvin
    o Mr Data
    o R2D2
    o Robbie
    Stan
    Rating No votes yet. Vote now.

