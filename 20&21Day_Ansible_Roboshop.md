---
title: 20&21Day_Ansible_Roboshop
uuid: 5fdfcca0-0f76-11ef-b475-a6f126245c9e
version: 349
created: '2024-05-11T14:40:55+05:30'
tags:
  - ansible-roboshop
  - ansible
---

**Topics:**

1. <mark style="background-color:#f8d616;">Creating instances using Roboshop-shell script ( for time being)<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Roboshop using Ansible<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Inventory<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">MongoDB install & configure<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Catalogue  install & configure<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Web  install & configure<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Reddis  install & configure<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">User install & configure -<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f9b68d;">Similar to catalogue<!-- {"backgroundCycleColor":"13"} --></mark>

1. <mark style="background-color:#f8d616;">Cart install & configure -<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f9b68d;">Similar to catalogue<!-- {"backgroundCycleColor":"13"} --></mark>

1. <mark style="background-color:#f8d616;">MySQL install & configure<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Shipping install & configure<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Payment install & configure -<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f9b68d;">rabbitMQ, Payment<!-- {"backgroundCycleColor":"13"} --></mark>

1. <mark style="background-color:#f8d616;">Roles  --> Functions (In Ansible we call them as Roles)<!-- {"backgroundCycleColor":"25"} --></mark>

\

# #sudo yum install ansible -y<!-- {"collapsed":true} -->

 

![01bab218-e9fc-4426-a736-b54f245ef0ae.png|748.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/01bab218-e9fc-4426-a736-b54f245ef0ae.png) [^1]

 

 

# <mark style="background-color:#f8914d;">**Creating instance using Roboshop-shell script ( for time being)**<!-- {"backgroundCycleColor":"24"} --></mark>:<!-- {"collapsed":true} -->

 

Give the role which already created to the instance

![be59740b-5a29-4450-8718-fa24801563da.png|762](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/be59740b-5a29-4450-8718-fa24801563da.png) [^2]

 

 

```
git clone https://github.com/chilops/Roboshop-shellscripts.git 
cd Roboshop-shellscripts/
ls
 
```

![bb1e2e71-5751-43d4-97d5-050fc3c9a59f.png|866.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/bb1e2e71-5751-43d4-97d5-050fc3c9a59f.png) [^3]

 

\-- Creating all instances at a time

```
sudo sh roboshop.sh    
```

 

![49536518-77e0-4471-a5d7-25f145c623d6.png|897.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/49536518-77e0-4471-a5d7-25f145c623d6.png) [^4]

 

![d7877389-6efc-476e-bbec-e1d6d5ed6e3e.png|821.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/d7877389-6efc-476e-bbec-e1d6d5ed6e3e.png) [^5]

 

Also Domain records created  - Now update web server record with public IP

 

![1cea1907-451a-4d96-95b4-1adde30dc1d0.png|705.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/1cea1907-451a-4d96-95b4-1adde30dc1d0.png) [^6]

 

 

Creating an roboshop-ansible folder

![14fdece6-bfdf-4ba1-9f26-9c2439823e53.png|392](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/14fdece6-bfdf-4ba1-9f26-9c2439823e53.png) [^7]

 

 

Creating a new repository (roboshop-ansible)

![349e7ffc-3686-4cef-8acb-903ca49e837f.png|947.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/349e7ffc-3686-4cef-8acb-903ca49e837f.png) [^8]

 

 

# <mark style="background-color:#f8914d;">**Initializing git**:<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

```
cd /e/awsdevops/Repos/roboshop-ansible/
git init
git remote add origin git@github.com:chilops/roboshop-ansible.git
 
```

![b4f72a5d-635c-491f-8788-fa64cf7f9f91.png|781](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/b4f72a5d-635c-491f-8788-fa64cf7f9f91.png) [^9]

 

 

 

# <mark style="background-color:#f8914d;">**Roboshop using Ansible**: - Inventory<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

Inventory.ini

![6164866d-c264-4141-b75f-e8712e88df46.png|385](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/6164866d-c264-4141-b75f-e8712e88df46.png) [^10]

 

 

# <mark style="background-color:#f8914d;">**MongoDB installation**:<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

```
Mongodb.repo
 
[mongodb-org-4.2]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
gpgcheck=0
enabled=1
```

 

![5b0025fe-eeb8-49a5-836b-78bc18081853.png|698](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/5b0025fe-eeb8-49a5-836b-78bc18081853.png) [^11]

 

 

YAML code - mongodb.yaml

![b31b4692-d96b-416f-ab37-ae029d24cec0.png|511](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/b31b4692-d96b-416f-ab37-ae029d24cec0.png) [^12]

 

 

```
git status
```

```
git status
```

```
git status
```

 

![2cfed1b1-b1e0-47c6-8256-0deeacdb62fa.png|733](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/2cfed1b1-b1e0-47c6-8256-0deeacdb62fa.png) [^13]

```
 
git clone https://github.com/chilops/roboshop-ansible.git 
ls
cd roboshop-ansible/
ls
```

![d72a3a55-0a12-4f8f-971e-5df235da562e.png|842.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/d72a3a55-0a12-4f8f-971e-5df235da562e.png) [^14]

 

 

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 mongodb.yaml
```

 

![f4c6627d-806a-4bcd-bbee-1226564accd2.png|835.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/f4c6627d-806a-4bcd-bbee-1226564accd2.png) [^15]

 

Login to mongodb server and check if mongodb is running or not.

```
netstat -lntp
```

 

![df508bda-e4f9-4628-94aa-f733dee21f22.png|910.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/df508bda-e4f9-4628-94aa-f733dee21f22.png) [^16]

 

 

 

# <mark style="background-color:#f8914d;">**Catalogue installation**:<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

Command module vs shell module:

command -- > won't respect target machine shell variables and environment, it is running the command from outside

shell -- > It is like you logged in inside target machine directly and running command & shell module is little slower

 

Catalogue.service file

![cb3d3d2c-1a49-4189-9074-bc0651ce33dd.png|757](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/cb3d3d2c-1a49-4189-9074-bc0651ce33dd.png) [^17]

 

YAML code: catalogue.yaml

![66872030-c500-4096-b30d-84baaeb37b5e.png|846](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/66872030-c500-4096-b30d-84baaeb37b5e.png) [^18]

![66872030-c500-4096-b30d-84baaeb37b5e.png|846](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/66872030-c500-4096-b30d-84baaeb37b5e.png) [^19]

 

 

```
git add . ; git commit -m "mongodb "; git push origin main
```

```
git add . ; git commit -m "mongodb "; git push origin main
```

```
git status
```

 

![6529f248-c002-45ae-bc05-d5421a07f21d.png|741](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/6529f248-c002-45ae-bc05-d5421a07f21d.png) [^20]

 

```
git pull
```

```
git pull
```

![d72f3214-2571-4dfa-a0f7-663db4cbfde1.png|863.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/d72f3214-2571-4dfa-a0f7-663db4cbfde1.png) [^21]

 

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 catalogue.yaml
```

![0b713bf2-fee4-4ab3-bbb1-c3cca15ec88f.png|947.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/0b713bf2-fee4-4ab3-bbb1-c3cca15ec88f.png) [^22]

![6f58a039-aea2-450f-b795-5cc0b415a866.png|945.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/6f58a039-aea2-450f-b795-5cc0b415a866.png) [^23]

 

Connect to catalogue instance and check logs if mongodb connected or not.

```
sudo less /var/log/messages | grep -i mongodb
```

Or

```
sudo less /var/log/messages | grep -i catalogue
```

![7ea5747b-efd6-495b-9413-1b21902c540c.png|854.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/7ea5747b-efd6-495b-9413-1b21902c540c.png) [^24]

 

 

To connect mongodb from catalogue server:   -- to understand see video from 52:00 after

```
mongo --host mongodb.chowdarychilukuri.in
```

 

![b082139d-6f3d-4a3b-a251-d77b865346eb.png|834.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/b082139d-6f3d-4a3b-a251-d77b865346eb.png) [^25]

 

 

To get the db name

```
cd /app
ls -l
cd schema/
cat catalogue.js
```

![89c47d6d-c306-469b-aa87-cc4187bbc950.png|920.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/89c47d6d-c306-469b-aa87-cc4187bbc950.png) [^26]

 

\--This is to check if products are there or not & its count will be zero before loading. 

```
mongo --host mongodb.chowdarychilukuri.in --quiet --eval 'db = db.getSiblingDB("catalogue") ; db.products.count () '       
```

 

![506d25d5-8f3a-4fde-a26b-4444880d4d61.png|1085.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/506d25d5-8f3a-4fde-a26b-4444880d4d61.png) [^27]

 

 

After loading

![7455ef31-10e2-4720-b497-406ba4e640de.png|971](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/7455ef31-10e2-4720-b497-406ba4e640de.png) [^28]

 

 

Now count is 11

![be7848f4-a5ba-445e-9ab3-9b567a2c789b.png|969.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/be7848f4-a5ba-445e-9ab3-9b567a2c789b.png) [^29]

 

 

# <mark style="background-color:#f8914d;">**Web Installation**:<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

YAML code : web

![76865197-a00c-4f5b-b2f4-84936223e1c8.png|802](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/76865197-a00c-4f5b-b2f4-84936223e1c8.png) [^30]

 

 

Roboshop.conf file

![28149e24-3a41-405a-a951-793418965dd7.png|1001](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/28149e24-3a41-405a-a951-793418965dd7.png) [^31]

 

```
git status
```

```
git add . ; git commit -m "mongodb "; git push origin main
```

```
git status
```

```
git status
```

```
git add . ; git commit -m "mongodb "; git push origin main
```

 

```
git pull
```

```
ls
```

![65f038bc-5121-4fc6-9c59-a05ed44d6f5e.png|927](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/65f038bc-5121-4fc6-9c59-a05ed44d6f5e.png) [^32]

 

```
ls
```

```
ls
```

![a761ff64-d74b-4f6c-a520-b76084c38e66.png|1009.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/a761ff64-d74b-4f6c-a520-b76084c38e66.png) [^33]

 

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 web.yaml
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 web.yaml
```

 

 

 --After script execution

```
netstat -lntp    
```

```
sudo less /var/log/messages | grep -i nginx    --> nginx logs
```

```
netstat -lntp    
```

 

 

```
sudo systemctl status nginx              --> nginx service check
```

```
sudo systemctl status nginx              --> nginx service check
```

![1452b213-854d-4e8e-ae46-24b304e91475.png|861.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/1452b213-854d-4e8e-ae46-24b304e91475.png) [^34]

 

 

![15606c03-420d-4bc9-8bcc-7e94dedc1cbc.png|947.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/15606c03-420d-4bc9-8bcc-7e94dedc1cbc.png) [^35]

 

 

# <mark style="background-color:#f8914d;">**Reddis  install & configure** :<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

```
git add . ; git commit -m "redis"; git push origin main
```

```
git status
```

Redis YAML code

![b71e1010-85d1-41f6-b647-f2bb2bd2a26c.png|742](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/b71e1010-85d1-41f6-b647-f2bb2bd2a26c.png) [^36]

 

 

```
git status
```

```
git status
```

```
git status
```

![e01fd2cf-0767-4415-8c9b-d43e75bfec76.png|793](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/e01fd2cf-0767-4415-8c9b-d43e75bfec76.png) [^37]

![e01fd2cf-0767-4415-8c9b-d43e75bfec76.png|793](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/e01fd2cf-0767-4415-8c9b-d43e75bfec76.png) [^38]

 

```
git pull
```

 

```
git pull
```

```
git pull
```

```
git pull
```

 

![796b628b-8905-478d-a39c-7df80e855bb9.png|899.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/796b628b-8905-478d-a39c-7df80e855bb9.png) [^39]

 

```
netstat -lntp    --> to check if redis is running or not
```

```
netstat -lntp    --> to check if redis is running or not
```

```
netstat -lntp    --> to check if redis is running or not
```

 

 

 

 

# <mark style="background-color:#f8914d;">**User install & configure**<!-- {"backgroundCycleColor":"24"} --></mark> - Similar to catalogue<!-- {"collapsed":true} -->

![e4bf3d23-8dfc-4844-8c5c-fca51bfb0b0f.png|827.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/e4bf3d23-8dfc-4844-8c5c-fca51bfb0b0f.png) [^40]

 

```
git add . ; git commit -m "user"; git push origin main
```

```
git add . ; git commit -m "user"; git push origin main
```

![e4bf3d23-8dfc-4844-8c5c-fca51bfb0b0f.png|827.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/e4bf3d23-8dfc-4844-8c5c-fca51bfb0b0f.png) [^41]

 

User.service file

```
git status
```

```
git status
```

```
git status
```

![f4ba9196-3e7d-4833-8169-bc574be6ad2f.png|776](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/f4ba9196-3e7d-4833-8169-bc574be6ad2f.png) [^42]

 

 

```
git status
```

```
git status
```

```
git status
```

```
git status
```

 

```
git pull
```

```
git pull
```

 

```
 sudo less /var/log/messages | grep -i redis
```

![6b6dfcab-b56b-4a3d-9883-09fe286f3a6a.png|895.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/6b6dfcab-b56b-4a3d-9883-09fe286f3a6a.png) [^43]

![6b6dfcab-b56b-4a3d-9883-09fe286f3a6a.png|895.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/6b6dfcab-b56b-4a3d-9883-09fe286f3a6a.png) [^44]

 

Connect to user instance & check

To check logs if mondb connected & redis ready

```
sudo less /var/log/messages | grep -i mongodb
```

```
sudo less /var/log/messages | grep -i mongodb
```

![32732097-75ea-4fdb-a0df-a7dd18c5891b.png|963.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/32732097-75ea-4fdb-a0df-a7dd18c5891b.png) [^45]

 

![dd9a6508-b3ee-4817-8382-990ea1d9cede.png|529](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/dd9a6508-b3ee-4817-8382-990ea1d9cede.png) [^46]

![dd9a6508-b3ee-4817-8382-990ea1d9cede.png|529](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/dd9a6508-b3ee-4817-8382-990ea1d9cede.png) [^47]

 

Checking if user application is working or not

![743b8372-a46f-4d1d-a1c4-46485f671853.png|749](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/743b8372-a46f-4d1d-a1c4-46485f671853.png) [^48]

![bcc7a0ee-ca0a-4ddc-8e77-afd223927ed6.png|593](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/bcc7a0ee-ca0a-4ddc-8e77-afd223927ed6.png) [^49]

 

 

# <mark style="background-color:#f8914d;">**Cart install & configure**<!-- {"backgroundCycleColor":"24"} --></mark> - Similar to catalogue<!-- {"collapsed":true} -->

 

Cart YAML code

![743b8372-a46f-4d1d-a1c4-46485f671853.png|852](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/743b8372-a46f-4d1d-a1c4-46485f671853.png) [^50]

```
git add . ; git commit -m "cart"; git push origin main
```

```
git status
```

![743b8372-a46f-4d1d-a1c4-46485f671853.png|852](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/743b8372-a46f-4d1d-a1c4-46485f671853.png) [^51]

![dd9a6508-b3ee-4817-8382-990ea1d9cede.png|537](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/dd9a6508-b3ee-4817-8382-990ea1d9cede.png) [^52]

 

Cart.service file

![bddd7043-94ba-4574-b75e-623835ea7084.png|572](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/bddd7043-94ba-4574-b75e-623835ea7084.png) [^53]

 

```
git status
```

![ad99892a-c145-4e17-9fd5-4af1ce8d7f17.png|870.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/ad99892a-c145-4e17-9fd5-4af1ce8d7f17.png) [^54]

![b8edefd7-22df-45ec-ae12-bb569e894ba6.png|868.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/b8edefd7-22df-45ec-ae12-bb569e894ba6.png) [^55]

 

```
git status
```

```
git status
```

```
git status
```

![0f918f8f-8f84-4b8b-a643-4135ad11291b.png|751](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/0f918f8f-8f84-4b8b-a643-4135ad11291b.png) [^56]

 

 

```
git pull
```

```
git pull
```

 

![ad99892a-c145-4e17-9fd5-4af1ce8d7f17.png|871.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/ad99892a-c145-4e17-9fd5-4af1ce8d7f17.png) [^57]

![ad99892a-c145-4e17-9fd5-4af1ce8d7f17.png|871.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/ad99892a-c145-4e17-9fd5-4af1ce8d7f17.png) [^58]

![b8edefd7-22df-45ec-ae12-bb569e894ba6.png|868.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/b8edefd7-22df-45ec-ae12-bb569e894ba6.png) [^59]

 

 

![80d6a9b4-c9ed-4f33-8430-50ab034cd1eb.png|778](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/80d6a9b4-c9ed-4f33-8430-50ab034cd1eb.png) [^60]

```
git add . ; git commit -m "mysql"; git push origin main
```

```
git status
```

 

 

 

# <mark style="background-color:#f8914d;">**MySQL install & configure**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

MySql YAML code

![6821d50c-efc8-4ad7-9fb3-26a04d9fa531.png|792](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/6821d50c-efc8-4ad7-9fb3-26a04d9fa531.png) [^61]

 

 

Mysql.repo file

![442ef28e-1940-400c-b208-6ccad9491fe4.png|732](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/442ef28e-1940-400c-b208-6ccad9491fe4.png) [^62]

 

```
git status
```

```
git status
```

```
git add . ; git commit -m "mysql"; git push origin main
```

![e28c0358-be05-4937-b9f0-c24f20ade96c.png|949.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/e28c0358-be05-4937-b9f0-c24f20ade96c.png) [^63]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 mysql.yaml
```

 

![a1d6f1c8-5d13-4453-9e4e-bddbb7ffa6d2.png|952.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/a1d6f1c8-5d13-4453-9e4e-bddbb7ffa6d2.png) [^64]

 

```
netstat -lntp
```

![78954a6e-b5ae-40b5-89ad-ab4a300bca4b.png|959.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/78954a6e-b5ae-40b5-89ad-ab4a300bca4b.png) [^65]

 

# <mark style="background-color:#f8914d;">**Shipping install & configure**:<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

To check if databases loaded or not…

```
sudo dnf install mysql -y     --> install to check mysql DB
```

 

\-- cmd to connect to mysql database from shipping instance

```
mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1    
```

![1da4bcf2-9a47-4b36-bec3-b609867aeb2d.png|857.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/1da4bcf2-9a47-4b36-bec3-b609867aeb2d.png) [^66]

 

```
show databases;    --> currently Databases is not showing
```

![dfa0e71c-84aa-44e5-a6c1-81c5b4fd1452.png|466](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/dfa0e71c-84aa-44e5-a6c1-81c5b4fd1452.png) [^67]

 

\--SQL query to check the count

```
 mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1 -e "SELECT COUNT(*) FROM INFORMATION_SCHEMA.SCHEMATA WHERE SCHEMA_NAME= 'mysql'"    
```

Or

```
 mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1 -sN -e "SELECT COUNT(*) FROM INFORMATION_SCHEMA.SCHEMATA WHERE SCHEMA_NAME= 'mysql'" 
```

![a756d400-f75b-4881-a435-2ee7f55b412e.png|1011.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/a756d400-f75b-4881-a435-2ee7f55b412e.png) [^68]

 

![4bdff10b-93a0-4c2e-aaa0-9cf759dfcd22.png|1019.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/4bdff10b-93a0-4c2e-aaa0-9cf759dfcd22.png) [^69]

 

 

Shipping YAML code:

![8d1d7187-5fdf-4e3c-b36d-427fbd03ff82.png|825](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/8d1d7187-5fdf-4e3c-b36d-427fbd03ff82.png) [^70]

![59c1223d-364c-4536-b17f-9dcb31b5372a.png|968.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/59c1223d-364c-4536-b17f-9dcb31b5372a.png) [^71]

![8d1d7187-5fdf-4e3c-b36d-427fbd03ff82.png|824](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/8d1d7187-5fdf-4e3c-b36d-427fbd03ff82.png) [^72]

 

Shipping.service file

![63a48cc2-1f3b-4cf3-ab80-7950cda8ac1a.png|580](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/63a48cc2-1f3b-4cf3-ab80-7950cda8ac1a.png) [^73]

 

 

```
git status
```

```
git add . ; git commit -m "shipping"; git push origin main
```

```
git status
```

![ce54fdae-218a-42d1-ac4b-44c25c02a983.png|742](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/ce54fdae-218a-42d1-ac4b-44c25c02a983.png) [^74]

 

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 shipping.yaml
```

![59c1223d-364c-4536-b17f-9dcb31b5372a.png|901.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/59c1223d-364c-4536-b17f-9dcb31b5372a.png) [^75]

![59c1223d-364c-4536-b17f-9dcb31b5372a.png|898.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/59c1223d-364c-4536-b17f-9dcb31b5372a.png) [^76]

 

On shipping instance

```
mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1    --> cmd to connect to mysql database from shipping instance
```

```
show databases;    --> now cities Database is showing
```

```
 mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1 -e "SELECT COUNT(*) FROM INFORMATION_SCHEMA.SCHEMATA WHERE SCHEMA_NAME= 'cities'"    --> SQL query to check the count
```

Or

```
mysql -h mysql.chowdarychilukuri.in -uroot -pRoboShop@1 -sN -e "SELECT COUNT(*) FROM INFORMATION_SCHEMA.SCHEMATA WHERE SCHEMA_NAME= 'cities'" 
```

 

![80f14f5f-b072-48c0-9628-5dc2fabdfc10.png|991.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/80f14f5f-b072-48c0-9628-5dc2fabdfc10.png) [^77]

 

![8a5a530a-4e7b-436c-ae59-502397f70a80.png|987.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/8a5a530a-4e7b-436c-ae59-502397f70a80.png) [^78]

 

![0e7d8d78-125f-4640-ad19-7145890777bd.png|860](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/0e7d8d78-125f-4640-ad19-7145890777bd.png) [^79]

 

![c2184d72-1e5e-4c3a-bd8e-16091fcf2f89.png|671](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/c2184d72-1e5e-4c3a-bd8e-16091fcf2f89.png) [^80]

 

 

# <mark style="background-color:#f8914d;">**Payment install & configure**<!-- {"backgroundCycleColor":"24"} --></mark>: <mark style="background-color:#f8d616;">rabbitMQ, payment<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"collapsed":true} -->

\

![f771f5d8-9bd0-4c17-8eea-4f0d896d3b40.png|932.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/f771f5d8-9bd0-4c17-8eea-4f0d896d3b40.png) [^81]

 

Rabbitmq YAML code

![ab901342-868f-4a61-ada5-db19d002edcd.png|1043.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/ab901342-868f-4a61-ada5-db19d002edcd.png) [^82]

 

 

```
git status
```

```
git add . ; git commit -m "shipping"; git push origin main
```

```
git status
```

 

![272960ea-1cdf-4c35-ae09-3d64da1dbbb0.png|817](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/272960ea-1cdf-4c35-ae09-3d64da1dbbb0.png) [^83]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 rabbitmq.yaml
```

![f771f5d8-9bd0-4c17-8eea-4f0d896d3b40.png|1013.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/f771f5d8-9bd0-4c17-8eea-4f0d896d3b40.png) [^84]

 

![f771f5d8-9bd0-4c17-8eea-4f0d896d3b40.png|1012.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/f771f5d8-9bd0-4c17-8eea-4f0d896d3b40.png) [^85]

![7024bb1a-f4e5-41ae-9f21-98f79ed45555.png|1015.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/7024bb1a-f4e5-41ae-9f21-98f79ed45555.png) [^86]

 

\

 

Payment YAML code

![93249c52-1b3b-4192-968b-02cf0d4aace6.png|715](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/93249c52-1b3b-4192-968b-02cf0d4aace6.png) [^87]

![d8862152-2040-496b-984b-5f29c1109f3c.png|464](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/d8862152-2040-496b-984b-5f29c1109f3c.png) [^88]

 

 

Payment.service

![56a26ae5-3821-41f2-876b-ae32f7e3e7f3.png|579](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/56a26ae5-3821-41f2-876b-ae32f7e3e7f3.png) [^89]

 

```
git status
```

```
git add . ; git commit -m "shipping"; git push origin main
```

```
git status
```

![3cf43c21-e52f-4156-9a70-5a745503c5cb.png|821](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/3cf43c21-e52f-4156-9a70-5a745503c5cb.png) [^90]

 

 

![a6a417d4-0765-4ebc-9b1b-c1d8b2bb25f8.png|931.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/a6a417d4-0765-4ebc-9b1b-c1d8b2bb25f8.png) [^91]

\

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 payment.yaml
```

 

![a6a417d4-0765-4ebc-9b1b-c1d8b2bb25f8.png|956.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/a6a417d4-0765-4ebc-9b1b-c1d8b2bb25f8.png) [^92]

![521459bc-3667-453e-84bb-cb3654bef5c4.png|957.3333740234375](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/521459bc-3667-453e-84bb-cb3654bef5c4.png) [^93]

 

![76360d2c-63b4-458b-8392-c509f6cbaade.png|949](https://images.amplenote.com/5fdfcca0-0f76-11ef-b475-a6f126245c9e/76360d2c-63b4-458b-8392-c509f6cbaade.png) [^94]

 

# <mark style="background-color:#f8914d;">**Roles  --> Functions (In Ansible we call them as Roles)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

DRY -- > don't repeat yourself  (to Avoid duplicates like same work doing multiple times creating directories etc)

 

In shellscripts, we created a function and kept code inside. whenever you want can call the function.

 

reduce duplicate code, and a central place to change.

[^1]: \[ centosdip-172-31-19-35 \~ \]$ sudo yum install ansible
    -y
    CentOS Stream 8 - AppStream
    57 MB/S
    28 MB
    00: 00
    CentOS Stream 8
    - BaseOS
    18 MB/S
    10 MB
    00: 00
    CentOS Stream 8 - Extras
    212 kB/s
    18 kB
    00: 00
    CentOS Stream 8 - Extras common packages
    34 kB/s
    1
    7. 7 kB
    00: 00
    Extra Packages for Enterprise Linux 8 - x86 64
    42 MB/s \|
    16 MB
    00: 00
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Size
    Installing:
    ansible
    noarch
    8. 3.0-1.e18
    epel
    41 M
    Installing dependencies:
    ansible-core
    x86 64
    2. 16.2-1.e18
    appstream
    4.1

[^2]: EC2 > Instances > i-0b9bbb46e9f9617d2 > Modify IAM role
    Modify IAM role info
    Attach an IAM role to your instance.
    Instance ID
    i-0b9bbb46e9f9617d2 (Ansible_server)
    IAM role
    Select an IAM role to attach to your instance or create a new role if you haven't created any. The role you select replaces any roles that are
    currently attached to your instance.
    EC2Roleforshellscripts
    C
    Create new IAM role \[
    Cancel
    Update IAM role

[^3]: \[ centosdip-172-31-19-35 \~ \]$ git clone https://github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts'...
    remote: Enumeratiog objects: 71, done.
    remote: Counting objects: 100% (71/71), done.
    remote: Compressing objects: 100% (55/55), done.
    remote: Total 71 (delta 37), reused 49 (delta 15), pack-reused 0
    Receiving objects: 100% (71/71), 10.98 KiB \| 3. 66 MiB/s, done.
    Resolving deltas: 100% (37/37), done.
    54 . 86.23.207 \| 172. 31. 19.35 \| t2.micro \| null
    \[ centosdip-172-31-19-35 \~ \]$ cd Roboshop-shellscripts/
    54 . 86.23.207 \| 172. 31. 19.35 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts .git
    \[ centos@ip-172-31-19-35 \~/Roboshop-shellscripts \]$ 1s
    cart . service
    catalogue . sh mysql . repo
    payment . sh
    roboshop . conf
    shipping . sh
    web . sh
    cart . sh
    Mongodb . sh
    mysql . sh
    rabbitmq . sh
    roboshop . sh
    user . service
    catalogue . service mongo . repo
    payment . service redis. sh
    shipping . service user . sh
    54 . 86.23.207 \| 172. 31.19.35 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-19-35 \~/Roboshop-shellscripts \]$ !

[^4]: \[ centos@ip-172-31-19-35 \~/Roboshop-shellscripts \]$ sudo sh roboshop. sh
    mongodb: 172. 31 . 29.116
    M
    "ChangeInfo" : {
    "Id": "/change/C04466802A516H4IWK55U",
    "Status": "PENDING"
    "SubmittedAt": "2024-05-03T05 : 00 : 32 . 168000+00:00",
    "Comment": "Creating a record set for cognito endpoint"
    redis: 172. 31. 21. 133
    "ChangeInfo" : {
    "Id": "/change/C0801010NMH90TSYDXO2",
    "Status": "PENDING",
    "SubmittedAt": "2024-05-03T05 : 00 : 35 . 461000+00:00",
    "Comment": "Creating a record set for cognito endpoint"
    mysql: 172 . 31 . 31.203
    "ChangeInfo" : {
    "Id": "/change/C04702323GM8BM1TXZJ4Q",
    "Status": "PENDING",
    "SubmittedAt": "2024-05-03T05 : 00 : 38 . 506000+00:00"
    "Comment": "Creating a record set for cognito endpoint"

[^5]: Instances (12) Info
    G
    Connect
    Instance state
    Actions
    4
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    O
    Name
    Instance ID
    Instance state
    V
    Instance type
    Status check
    catalogue
    i-0bge5d0801db2930e
    Running
    t2.micro
    Initializing
    mongodb
    i-05cb81ac412f55acf
    Running
    t3.small
    Initializing
    redis
    i-0582094a3620d1577
    Running
    t2.micro
    Initializing
    web
    i-0c3430f84a08b1bae
    Running
    t2.micro
    Initializing
    dispatch
    i-0d130ef671697e4a4
    Running
    t2.micro
    Initializing
    user
    i-069930d4df40d04f1
    Running
    t2.micro
    Initializing
    cart
    i-034216343e0Ofb27a
    Running
    t2.micro
    Initializing
    Ansible_server
    i-0b9bbb46e9f9617d2
    Running
    t2.micro
    2/2 checks passed
    payment
    i-06655eae55910b5fd
    Running
    t2.micro
    Initializing
    mysql
    i-02353ecc4f7bc8fea
    Running
    t3.small
    Initializing
    shipping
    i-053d5be6a69e98da9
    Running
    t3.small
    Initializing
    rabbitmq
    i-0a9fd87b4d4ad7e7f
    Running
    t2.micro
    Initializing

[^6]: Edit record
    X
    <
    1
    Record name Info
    subdomain
    chowdarychilukuri.in
    -
    Record name
    Type
    Routin...
    4
    Differ...
    Ali
    Keep blank to create a record for the root domain.
    Record type Info
    0
    chowdarychilukuri.in
    NS
    Simple
    No
    A - Routes traffic to an IPv4 address and so...
    . Alias
    chowdarychilukuri.in
    SOA
    Simple
    No
    Value Info
    0
    cart.chowdarychilukuri.in
    A
    Simple
    No
    54.227.85.183
    O
    catalogue.chowdarychilukuri.in
    A
    Simple
    No
    0
    dispatch.chowdarychilukuri.in
    A
    Simple
    No
    O
    mongodb.chowdarychilukuri.in
    A
    Simple
    No
    Enter multiple values on separate lines.
    TTL (seconds) Info
    mysql.chowdarychilukuri.in
    A
    Simple
    No
    7
    1m
    1h
    1d
    O
    payment.chowdarychilukuri.in
    A
    Simple
    No
    Recommended values: 60 to 172800 (two days)
    0
    rabbitmq.chowdarychilukuri.in
    A
    Simple
    No
    Routing policy Info
    O
    redis.chowdarychilukuri.in
    A
    Simple
    No
    Simple routing
    0
    shipping.chowdarychilukuri.in
    A
    Simple
    No
    Cancel
    Save
    O
    user.chowdarychilukuri.in
    A
    Simple
    No
    web.chowdarychilukuri.in
    A
    Simple
    No

[^7]: EXPLORER
    $ robo
    REPOS
    Robosh
    > Ansible
    1
    2
    > Concepts
    3
    > Robosho-shellscripts
    4
    v roboshop-ansible
    5
    > shellscripts
    16
    7

[^8]: E
    New repository
    Q Type to search
    +
    O
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    chilops
    roboshop-ansible
    roboshop-ansible is available.
    Great repository names are short and memorable. Need inspiration? How about urban-computing-machine ?
    Description (optional)
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    O
    Private
    You choose who can see and commit to this repository.

[^9]: "MINGW64:/c/devops/daws-76s/repos/roboshop-ansible
    user@AshDexter-T480 MINGW64 \~
    $ cd /c/devops/daws-76s/repos/roboshop-ansible/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/roboshop-ansible
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/roboshop-ansible/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos /roboshop-ansible (master)
    $ git remote add origin git@github.com: daws-76s/roboshop-ansible . git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s /repos /roboshop-ansible (master)

[^10]: $ roboshop.sh X inventory.ini X
    roboshop-ansible > # inventory.ini
    \[mongodb \]
    N
    mongodb . chowdarychilukuri . in
    13
    \[catalogue\]
    4
    catalogue . chowdarychilukuri . in
    5
    \[user \]
    6
    user . chowdarychilukuri . in
    7
    \[cart\]
    8
    cart . chowdarychilukuri . in
    19
    \[web \]
    10
    web . chowdarychilukuri . in
    11
    \[redis \]
    12
    redis . chowdarychilukuri . in
    13
    \[mysql \]
    14
    mysql . chowdarychilukuri . in
    15
    \[shipping \]
    16
    shipping . chowdarychilukuri . in
    17
    \[rabbitmq\]
    18
    rabbitmq . chowdarychilukuri . in
    19
    \[payment \]
    20
    payment . chowdarychilukuri . in

[^11]: roboshop-ansible > @ mongodb.repo
    1
    \[mongodb-org-4.2\]
    2
    name=MongoDB Repository
    3
    baseur1=https : //repo . mongodb . org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    4
    gpgcheck=0
    5
    enabled=1

[^12]: roboshop-ansible > ! mongodb.yaml
    name : mongodb
    N
    hosts: mongodb
    3
    become : yes
    4
    tasks :
    5
    name: Copy mongodb repo
    6
    ansible. builtin . copy :
    7
    src: mongodb . repo
    8
    dest: /etc/yum. repos . d/mongodb . repo
    9
    10
    - name: Install mongodb
    11
    ansible . builtin . package :
    12
    name : mongodb-org
    13
    state: present
    14
    15
    - name: start and enable mongodb
    16
    ansible . builtin . service:
    17
    name: mongod
    18
    state: started
    19
    enabled: yes
    20
    21
    name: allow remote conncections
    22
    ansible. builtin . replace:
    23
    path: /etc/mongod . conf
    24
    regexp: '127.0.0.1'
    25
    replace: '0.0.0.0'
    26
    27
    name: start and enable mongodb
    28
    ansible . builtin . service:
    29
    name : mongod
    30
    state: restarted

[^13]: (use "git add <file>..." to include in what will be committed)
    inventory . ini
    mongodb . repo
    mongodb . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevOps \\Repos \\roboshop-ansible> git add . ; git commit -m "mongodb "; git push origin main

[^14]: \[ centos@ip-172-31-19-35 \~ \]$ git clone https: //github. com/chilops/roboshop-ansible.git
    Cloning into ' roboshop-ansible'
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 5 (delta 0), reused 5 (delta 0), pack-reused 0
    Receiving objects: 100% (5/5), done.
    54 . 86. 23.207 \| 172. 31. 19.35 \| t2.micro \| null
    \[ centos@ip-172-31-19-35 \~ \]$ 1s
    roboshop-ansible Roboshop-shellscripts
    54. 86.23.207 \| 172. 31. 19.35 \| t2.micro \| null
    \[ centos@ip-172-31-19-35 \~ \]$ cd roboshop-ansible/
    54 . 86.23.207 \| 172. 31. 19.35 \| t2.micro \| https: / /github. com/chilops/roboshop-ansible.git
    \[ centosdip-172-31-19-35 \~/roboshop-ansible \]$ 1s
    inventory . ini mongodb . repo mongodb . yaml
    54 . 86. 23.207 \| 172. 31. 19.35 \| t2.micro \| https://github. com/chilops/roboshop-ansible. git
    \[ centosdip-172-31-19-35 \~/roboshop-ansible \]$

[^15]: \[ centosdip-172-31-19-35 \~/roboshop-ansible \]$ ansible-playbook -i inventory . ini -e ansible_user=centos -e ansible_password
    =Devops321 mongodb . yaml
    PLAY \[mongodb \]
    \* \* \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*
    ok: \[mongodb . chowdarychilukuri . in\]
    TASK \[Copy mongodb repo\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
    changed: \[mongodb . chowdarychilukuri . in\]
    TASK \[Install mongodb\] \* \* \* \*\*\*\*\*\*\*\*\*\* \*\* \* \*
    changed: \[mongodb . chowdarychilukuri . in\]
    TASK \[start and enable mongodb\] \* \* \* \* \* \* \*\*\* \*
    changed: \[mongodb . chowdarychilukuri . in\]
    TASK \[allow remote connections\] \*\*\*\*\*\*\*
    changed: \[mongodb . chowdarychilukuri . in\]
    TASK \[start and enable mongodb\]
    \* \* \* \* \* \* \* \*
    changed: \[mongodb . chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    mongodb . chowdarychilukuri . in : ok=6
    changed=5
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    54 . 86.23.207 \| 172. 31. 19.35 \| t2.micro \| https://github. com/chilops/roboshop-ansible. git
    centos@ip-172-31-19-35 \~/roboshop-ansible \]$ !

[^16]: Ansible
    Mongodb
    54 . 160. 247.26 \| 172. 31. 29. 116 \| t3. small \| null
    \[ centos@ip-172-31-29-116 \~ \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    O
    0 0. 0. 0. 0:27017
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    OOOO
    tcp6
    : : :111
    :: :
    LISTEN
    tcp6
    0 : : :22
    LISTEN
    54 . 160. 247.26 \| 172. 31. 29.116 \| t3. small \| null
    \[ centos@ip-172-31-29-116 \~ \]$ 1

[^17]: roboshop-ansible > catalogue.service
    \[Unit\]
    2
    Description = Catalogue Service
    3
    4
    \[Service\]
    15
    User=roboshop
    6
    Environment=MONGO=true
    7
    Environment=MONGO_URL="mongodb : / /mongodb . chowdarychilukuri . in: 27017/catalogue"
    8
    ExecStart=/bin/node /app/server. js
    9
    SyslogIdentifier=catalogue
    10
    11
    \[Install \]
    12
    WantedBy=multi-user . target

[^18]: roboshop-ansible > ! catalogue.yaml
    name: catalogue
    hosts: catalogue
    become: yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin . shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    9
    ansible. builtin . dnf:
    10
    name: nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible. builtin. file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible . builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download catalogue application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3. amazonaws . com/catalogue . zip
    30
    dest: /tmp
    31
    32
    name: extract catalogue application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/catalogue . zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chair: /app
    42
    43
    name: Copy catalogue service
    44
    ansible. builtin. copy :

[^19]: roboshop-ansible > ! catalogue.yaml
    name: catalogue
    hosts: catalogue
    become: yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin . shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    9
    ansible. builtin . dnf:
    10
    name: nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible. builtin. file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible . builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download catalogue application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3. amazonaws . com/catalogue . zip
    30
    dest: /tmp
    31
    32
    name: extract catalogue application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/catalogue . zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chair: /app
    42
    43
    name: Copy catalogue service
    44
    ansible. builtin. copy :

[^20]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    catalogue . service
    catalogue . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "catalogue"; git push origin main

[^21]: \[ centos@ip-172-31-19-35 \~/roboshop-ansible \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 4 (delta 0), reused 4 (delta 0), pack-reused 0
    Unpacking objects: 100% (4/4), 1.28 KiB \| 1.28 MiB/s, done.
    From https: / /github. com/chilops/roboshop-ansible
    5c79a28. . 495dba5 main
    -> origin/main
    Updating 5c79a28. . 495dba5
    Fast-forward
    catalogue . service \| 12 +++++4+
    catalogue . yaml
    1 80 ++4+++++++++
    2 files changed, 92 insertions (+)
    create mode 100644 catalogue. service
    create mode 100644 catalogue . yaml
    54 . 86.23.207 \| 172. 31. 19.35 \| t2.micro \| https: //github.com/chilops/roboshop-ansible. git
    \[ centos@ip-172-31-19-35 \~/roboshop-ansible \]$ 1s
    catalogue . service catalogue . yaml
    inventory . ini
    mongodb . repo mongodb . yaml

[^22]: \[ centosdip-172-31-19-35 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 catalogue . yaml
    PLAY \[catalogue\]
    \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\*\*
    ok: \[catalogue . chowdarychilukuri . in\]
    TASK \[disable old nodejs and enable nodejs\]
    \* \* \*
    changed: \[catalogue . chowdarychilukuri . in\]
    TASK \[Install nodejs\] \*\*\*\*\*\*\*\*\*\*\*\*\* \* \*\*\*\*\* \*
    changed: \[catalogue . chowdarychilukuri . in\]
    TASK \[create roboshop user\] \*\*\*\*\*\*
    changed: \[catalogue . chowdarychilukuri . in\]

[^23]: TASK \[start and enable catalogue\] \*\*\*\*\*\*\*\*
    changed: \[catalogue . chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \* \* \* \* \* \* \*
    catalogue . chowdarychilukuri . in : ok=16
    changed=13
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^24]: \[ centos@ip-172-31-18-234 \~ \]$ sudo less /var/log/messages \| grep -i mongodb
    May 3 07:08:14 ip-172-31-18-234 platform-python \[14035\]: ansible-ansible. legacy. stat Invoked with path=/etc/yum. repos. d/mon
    godb. repo follow=False get_checksum=True checksum_algorithm=shal get_mime=True get_attributes=True
    May 3 07:08:14 ip-172-31-18-234 platform-python \[14320\]: ansible-ansible. legacy. copy Invoked with src=/home/centos/ . ansible
    /tmp/ansible-tmp-1714720093 . 6756272-6050-273843159173077/source dest=/etc/yum. repos . d/mongodb. repo _original_basename=mongo
    db. repo follow=False checksum=69529feaae521c7bccla9585fb0824d5ff0f928d backup=False force=True unsafe_writes=False content=
    NOT LOGGING PARAMETER validate=None directory_mode=None remote_src=None local_follow=None mode=None owner=None group=None s
    euser=None serole=None selevel=None setype=None attributes=None
    May 3 07:08:15 ip-172-31-18-234 platform-python \[14720\]: ansible-ansible. legacy . dnf Invoked with name=\[ 'mongodb-org-shell' \]
    state=present allow_downgrade=False autoremove=False bugfix=False cacheonly=False disable_gpg_check=False disable_plugin=\[
    disablerepo=\[\] download_only=False enable_plugin=\[\] enablerepo=\[\] exclude=\[\] installroot=/ install_repoquery=True install
    weak_deps=True security=False skip_broken=False update_cache=False update_only=False validate_certs=True sslverify=True lo
    ck_timeout=30 allowerasing=False nobest=False use_backend=auto conf_file=None disable_excludes=None download_dir=None list=
    None releasever=None
    May 3 07:08:23 ip-172-31-18-234 platform-python \[17485\]: ansible-ansible. legacy. command Invoked with _raw_params=mongo --ho
    st mongodb . chowdarychilukuri . in --quiet --eval 'db = db. getSiblingDB ("catalogue") ; db. products. count () ' uses_shell=False e
    xpand_argument_vars=True stdin_add newline=True strip_empty_ends=True argv=None chdir=None executable=None creates=None rem
    oves=None stdin=None
    May 3 07:08:24 ip-172-31-18-234 platform-python \[17889\]: ansible-ansible. legacy. command Invoked with _raw_params=mongo --ho
    st mongodb . chowdarychilukuri . in < /app/schema/catalogue. js _uses_shell=False expand_argument_vars=True stdin_add newline=Tr
    ue strip_empty_ends=True argv=None chdir=None executable=None creates=None removes=None stdin=None
    May 3 07:08:26 ip-172-31-18-234 catalogue \[18756\]: (node: 18756) \[MONGODB DRIVER\] Warning: Current Server Discovery and Moni
    toring engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine,
    pass option { useUnifiedTopology: true } to the MongoClient constructor.
    May
    3 07:08:26 ip-172-31-18-234 catalogue \[18756\]: {"level": "info", "time" : 1714720106612, "pid" : 18756, "hostname": "ip-172-31-1
    8-234. ec2. internal", "msg" : "
    connected" "y";

[^25]: \[ root@ip-172-31-18-234 /app/schema \]#
    mongo --host mongodb . chowdarychilukuri . in
    MongoDB shell version v4 . 2.25
    connecting to: mongodb: / /mongodb . chowdarychilukuri . in: 27017/?compressors=disabled&gssapiServiceName=mongodb
    Implicit session: session { "id" : UUID ("871c0e13-5a42-435d-bl1b-7283f2114868") }
    MongoDB server version: 4.2.25
    Welcome to the MongoDB shell.
    For interactive help, type "help".
    For more comprehensive documentation, see
    https :/ /docs . mongodb . com/
    Questions? Try the MongoDB Developer Community Forums
    https: / /community . mongodb . com
    Server has startup warnings:
    2024-05-03T05 : 54: 13. 857+0000 I
    CONTROL
    \[initandlisten\]
    2024-05-03T05 : 54: 13. 857+0000 I
    CONTROL
    \[initandlisten\]
    \* \* WARNING: Access control is not enabled for the database.
    2024-05-03T05 : 54 : 13. 857+0000 I
    CONTROL
    \[initandlisten\]
    \* \*
    Read and write access to data and configuration is
    estricted.
    2024-05-03T05 : 54: 13. 857+0000 I
    CONTROL
    \[initandlisten\]
    2024-05-03T05 : 54: 13. 857+0000 I
    CONTROL
    \[initandlisten\]
    2024-05-03T05 : 54: 13.857+0000 I
    CONTROL
    \[initandlisten\]
    \*\* WARNING: /sys/kernel/mm/transparent_hugepage/enabled is 'a
    2024-05-03T05 : 54 : 13. 857+0000 I CONTROL
    \[initandlisten\]
    \* \*
    We suggest setting it to 'never'
    2024-05-03T05 : 54 : 13. 857+0000 I CONTROL
    \[initandlisten\]
    Enable MongoDB's free cloud-based monitoring service, which will then receive and display
    metrics about your deployment (disk utilization, CPU, operation statistics, etc) .
    The monitoring
    data
    will be
    available on
    a MongODB website with
    a unique URL accessible to you

[^26]: \[ root@ip-172-31-18-234 /app/schema \]# cat catalogue. js
    Products
    db =
    db . getSiblingDB ( ' catalogue' ) ;
    db . products . insertMany ( \[
    {sku: 'HAL-1', name: 'HAL', description: 'Sorry Dave, I cant do that', price: 2001, instock: 2, categories: \['Artific
    Intelligence' \]} ,
    {sku: 'PB-1', name: 'Positronic Brain', description: 'Highly advanced sentient processing unit with the laws of roboti
    burned in', price: 200, instock: 0, categories: \['Artificial Intelligence' \] },
    {sku: 'ROB-1', name: 'Robbie', description: 'Large mechanical workhorse, crude but effective. Comes in handy when you
    re lost in space', price: 1200, instock: 12, categories: \['Robot' \]},
    {sku: 'EVE-1' ,
    name: 'Eve', description: 'Extraterrestrial Vegetation Evaluator', price: 5000, instock: 10, categories
    \[ ' Robot' \] } ,
    {sku: 'C3P0' ,
    name: 'C3P0', description: 'Protocol android', price: 953, instock: 1, categories: \['Robot' \]},
    \[sku: 'R2D2'
    name :
    'R2D2 '
    description:
    'R2 maintenance robot and secret messenger.
    Help me Obi Wan',
    price :
    1024
    in

[^27]: rootdip-172-31-18-234 /app/schema \]# mongo --host mongodb . chowdarychilukuri
    . in
    quiet
    --eval 'db
    db . getSiblingDB ("cat
    logue") ;
    db . products . count
    ()
    1 1

[^28]: name: get the categories count
    ansible . builtin. command: mongo. - -host mongodb . daws76s . online --quiet --eval 'db = db.
    getSiblingDB("catalogue"); db. products . count( )'
    register: product_count
    name: print the count
    ansible. builtin . debug:
    msg: "product count: {{product_count}}"
    name: load catalogue data
    ansible. builtin. command: mongo - -host mongodb . daws76s . online </app/schema/catalogue . js

[^29]: TASK \[print the count\]
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \*
    ok :
    \[ catalogue . daws 76s . online\] => {
    "msg" : "product count: {'changed' : True, stdout': '1?'
    'stderr' : "' ,
    'rc' : 0, 'cmd' : \['mongo' , ' --host', 'mongodb . daws76s. online
    ' --quiet' ,
    ' --eval' , 'db = db. getSiblingDB (\\ "catalogue\\") ; db . products . count () ' \], 'start' : '2023-12-22 02: 43:58. 710474', 'end' : '2023
    12-22 02: 43 : 58 . 801290', 'delta' : '0:00:00 . 090816', 'msg'
    'stdout_lines' : \['11'\], 'stderr_lines' : \[\], 'failed': False}"

[^30]: roboshop-ansible > ! web.yaml
    name: install web component
    hosts: web
    become: yes
    4
    tasks :
    name: install nginx
    ansible . builtin. dnf :
    name : nginx
    8
    state: present
    9
    10
    name: remove html directory
    11
    ansible . builtin. file:
    12
    path: /usr/share/nginx/html
    13
    state: absent
    14
    15
    name: create html directory
    16
    ansible. builtin . file:
    17
    path: /usr/share/nginx/html
    18
    state: directory
    19
    20
    name : Download web app
    21
    ansible. builtin. get_url:
    22
    url: https://roboshop-builds . s3 . amazonaws . com/web . zip
    23
    dest: /tmp
    24
    25
    name: Extract application
    26
    ansible. builtin. unarchive:
    27
    src: /tmp/web . zip
    28
    dest: /usr/share/nginx/html
    29
    remote_src: yes
    30
    31
    name: copy roboshop configuration
    32
    ansible . builtin . copy :
    33
    src: roboshop . conf
    34
    dest: /etc/nginx/default. d/roboshop. conf
    35
    36
    name: start and enable nginx
    37
    ansible. builtin. service:
    38
    name : nginx
    39
    state: restarted
    40
    enabled: yes

[^31]: roboshop-ansible > @ roboshop.conf
    1
    proxy_http_version 1.1;
    N
    location /images/ {
    3
    expires 5s;
    4
    root /usr/share/nginx/html;
    5
    try_files $uri /images/placeholder . jpg;
    6
    17
    location /api/catalogue/ { proxy_pass http: //catalogue. chowdarychilukuri . in: 8080/; }
    8
    location /api/user/ { proxy_pass http://user . chowdarychilukuri . in : 8080/; }
    19
    location /api/cart/ { proxy_pass http://cart. chowdarychilukuri . in: 8080/;
    10
    location /api/shipping/ { proxy_pass http://shipping . chowdarychilukuri . in : 8080/;
    11
    location /api/payment/ { proxy_pass http://payment . chowdarychilukuri . in: 8080/;
    }
    12
    13
    location /health {
    14
    stub_status on;
    15
    access_log off;
    16

[^32]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    roboshop . conf
    web . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "web ansible"; git push origin main

[^33]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 4 (delta 1), reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4), 534 bytes \| 534.00 KiB/s, done.
    From https://github. com/chilops/roboshop-ansible
    495dba5. . 217daff main
    -> origin/main
    Updating 495dba5. . 217daff
    Fast-forward
    roboshop . conf \| 16 ++++++
    web . yaml
    0
    2 files changed, 16 insertions (+)
    create mode 100644 roboshop. conf
    create mode 100644 web. yaml
    54. 87.3.19 \| 172. 31.25.57 \| t2.micro \| https: //github. com/chilops/roboshop-ansible.git
    \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ 1s
    catalogue . service catalogue. yaml inventory. ini mongodb . repo mongodb . yaml roboshop. conf web. yaml

[^34]: 3. 90. 188. 101 \| 172. 31.27.2 \| t2.micro \| null
    centosdip-172-31-27-2 \~ \]$ sudo systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Sat 2024-05-04 05:43:51 UTC; 6min ago
    Process: 9591 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 9563 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    9562
    r /bir
    ited

[^35]: C
    Not secure chowdarychilukuri.in/product/PB-1
    Stan's Robot Shop
    Search
    Login / Register
    Cart
    Positronic Brain
    STAN
    Empty
    Categories
    . Artificial
    Intelligence
    o HAL
    . Positronic
    Brain
    Stan
    . Robot
    o C3PO
    01 10
    0100 0201
    o Eve
    1001 1090110
    K9
    0218100
    010d 001
    o Kryten
    1007
    o Marvin
    . Mr Data
    o R2D2
    Robbie
    o Stan
    Rating No votes yet. Vote now.
    Highly advanced sentient processing unit
    with the laws of robotics burned in
    Price E200.00 Out of stock
    too

[^36]: roboshop-ansible > ! redis.yaml
    1
    name: install redis component
    hosts: redis
    3
    become : yes
    4
    tasks :
    name: install remi release
    6
    ansible. builtin. dnf: # check pacakge will work not
    7
    name: https ://rpms . remirepo . net/enterprise/remi-release-8 . rpm
    18
    state: present
    9
    disable_gpg_check: true
    10
    11
    name: enable redis
    12
    ansible . builtin. command: anf module enable redis : remi-6.2 -y
    13
    14
    name: install redis
    15
    ansible . builtin . dnf :
    16
    name: redis
    17
    state: present
    18
    19
    name: allow remote connections
    20
    ansible . builtin . replace:
    21
    path: /etc/redis/redis . conf
    22
    regexp: '127.0.0.1'
    23
    replace: '0.0.0.0'
    24
    25
    name: start and enable redis
    26
    ansible . builtin. service:
    27
    name: redis
    28
    state: restarted
    29
    enabled: yes

[^37]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    redis . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "redis"; git push origin main/

[^38]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    redis . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "redis"; git push origin main/

[^39]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 redis . yaml
    PLAY \[install redis component\]
    \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\*\*\*\*
    ok: \[redis . chowdarychilukuri . in\]
    TASK \[install remi release\] \* \*\*\*\*\*\*\*\*\*
    changed: \[redis . chowdarychilukuri . in\]
    TASK \[enable redis\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
    changed: \[redis . chowdarychilukuri . in\]
    TASK \[install redis\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
    changed: \[redis . chowdarychilukuri . in\]
    TASK \[allow remote connections\] \* \*\*\*\*\* \*
    changed: \[redis . chowdarychilukuri . in\]
    TASK \[start and enable redis\] \*\*\*\*\*\*\*\*\*
    changed: \[redis . chowdarychilukuri . in\]
    PLAY RECAP
    \* \* \* \* \*
    redis. chowdarychilukuri . in : ok=6
    changed=5
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^40]: roboshop-ansible > ! user.yaml
    1
    name: user
    hosts: user
    become : yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin. shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    ansible. builtin. dnf :
    10
    name : nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible . builtin . file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible. builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download user application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3. amazonaws . com/user . zip
    30
    dest: /tmp
    31
    name: extract user application
    ansible. builtin. unarchive:
    34
    src: /tmp/user . zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chdir: /app
    42
    43
    name: Copy user service
    44
    ansible . builtin . copy :

[^41]: roboshop-ansible > ! user.yaml
    1
    name: user
    hosts: user
    become : yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin. shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    ansible. builtin. dnf :
    10
    name : nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible . builtin . file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible. builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download user application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3. amazonaws . com/user . zip
    30
    dest: /tmp
    31
    name: extract user application
    ansible. builtin. unarchive:
    34
    src: /tmp/user . zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chdir: /app
    42
    43
    name: Copy user service
    44
    ansible . builtin . copy :

[^42]: roboshop-ansible > = user.service
    \[Unit \]
    2
    Description = User Service
    3
    \[Service\]
    14
    User=roboshop
    5
    Environment=MONGO=true
    6
    Environment=REDIS_HOST=redis . chowdarychilukuri . in
    7
    Environment=MONGO_URL="mongodb : / /mongodb . chowdarychilukuri . in : 27017/users"
    18
    ExecStart=/bin/node /app/server . js
    9
    SyslogIdentifier=user
    10
    11
    \[Install \]
    12
    WantedBy=multi-user . target

[^43]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 user . yaml
    PLAY \[user\]
    \* \* \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*
    ok: \[user . chowdarychilukuri . in\]
    TASK \[disable old nodejs and enable nodejs\]
    \* \* \* \* \*
    changed:
    \[user . chowdarychilukuri . in\]

[^44]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 user . yaml
    PLAY \[user\]
    \* \* \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*
    ok: \[user . chowdarychilukuri . in\]
    TASK \[disable old nodejs and enable nodejs\]
    \* \* \* \* \*
    changed:
    \[user . chowdarychilukuri . in\]

[^45]: centos@ip-172-31-21-157 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep
    -i redis
    Apr 18 07:16:36 ip-172-31-21-157 user \[17383\]: {"level": "info", "time" : 1713424596265, "pid" : 17383, "hostname": "ip-172-31-21-157
    ec2 . internal",
    "msg": "Redis
    READY
    undefined"
    "v" :1}

[^46]: 46
    dest: /etc/systemd/system/cart . service
    47
    48
    name: deamon realod and start
    49
    ansible . builtin . systemd_service:
    50
    daemon_reload: true
    51
    52
    name: start and enable cart
    53
    ansible . builtin . service:
    54
    name: cart
    55
    state: restarted
    56
    enabled: yes

[^47]: 46
    dest: /etc/systemd/system/cart . service
    47
    48
    name: deamon realod and start
    49
    ansible . builtin . systemd_service:
    50
    daemon_reload: true
    51
    52
    name: start and enable cart
    53
    ansible . builtin . service:
    54
    name: cart
    55
    state: restarted
    56
    enabled: yes

[^48]: roboshop-ansible > ! cart.yaml
    name: cart
    hosts: cart
    become : yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin. shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    ansible . builtin. dnf :
    10
    name : nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible . builtin . file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible. builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download cart application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3 . amazonaws . com/cart . zip
    30
    dest: /tmp
    31
    32
    name: extract cart application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/cart. zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chair: / app
    42
    43
    name: Copy cart service
    44
    ansible . builtin . copy:

[^49]: C
    Not secure chowdarychilukuri.in/login
    Stan's Robot Shop
    Login / Register
    Cart
    Greetings chill
    Empty
    Categories
    Email - chill@gmail.com
    Order History
    Order ID Items Total
    chill

[^50]: roboshop-ansible > ! cart.yaml
    name: cart
    hosts: cart
    become : yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin. shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    ansible . builtin. dnf :
    10
    name : nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible . builtin . file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible. builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download cart application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3 . amazonaws . com/cart . zip
    30
    dest: /tmp
    31
    32
    name: extract cart application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/cart. zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chair: / app
    42
    43
    name: Copy cart service
    44
    ansible . builtin . copy:

[^51]: roboshop-ansible > ! cart.yaml
    name: cart
    hosts: cart
    become : yes
    tasks :
    name: disable old nodejs and enable nodejs
    ansible. builtin. shell: anf module disable nodejs -y ; anf module enable nodejs : 18 -y
    name: Install nodejs
    ansible . builtin. dnf :
    10
    name : nodejs
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible . builtin . file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible. builtin. file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download cart application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3 . amazonaws . com/cart . zip
    30
    dest: /tmp
    31
    32
    name: extract cart application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/cart. zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: Install dependencies
    39
    ansible. builtin. command: npm install
    40
    args :
    41
    chair: / app
    42
    43
    name: Copy cart service
    44
    ansible . builtin . copy:

[^52]: 46
    dest: /etc/systemd/system/cart . service
    47
    48
    name: deamon realod and start
    49
    ansible . builtin . systemd_service:
    50
    daemon_reload: true
    51
    52
    name: start and enable cart
    53
    ansible . builtin . service:
    54
    name: cart
    55
    state: restarted
    56
    enabled: yes

[^53]: roboshop-ansible > cart.service
    1
    \[Unit \]
    2
    Description = Cart Service
    3
    \[Service\]
    4
    User=roboshop
    5
    Environment=REDIS_HOST=redis . chowdarychilukuri . in
    16
    Environment=CATALOGUE_HOST=catalogue . chowdarychilukuri. in
    17
    Environment=CATALOGUE_PORT=8080
    8
    ExecStart=/bin/node /app/server . js
    9
    SyslogIdentifier=cart
    10
    11
    \[Install \]
    12
    WantedBy=multi-user . target

[^54]: \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password
    =Devops321 cart . yaml
    PLAY \[cart\]
    \* \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \*
    ok: \[cart . chowdarychilukuri . in\]
    TASK \[disable old nodejs and enable nodejs\]
    \* \* \* \*
    changed: \[cart . chowdarychilukuri . in\]
    TASK \[Install nodejs\] \*\*\*\*\*\*\*\*\*\*\* \*
    changed: \[cart . chowdarychilukuri . in\]
    TASK \[create roboshop user\] \* \* \* \*\*\*\*

[^55]: TASK \[deamon realod and start\]
    \* \*
    ok: \[cart . chowdarychilukuri . in\]
    TASK \[start and enable cart\] \*\*\*\*\*\*\*\*\*\*
    changed: \[cart . chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \*
    \* \* \* \* \*
    cart . chowdarychilukuri . in : ok=12
    changed=9
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^56]: cart . service
    cart . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\roboshop-ansible> git add . ; git commit -m "cart"; git push origin main
    \[main cdb3d9d\] cart

[^57]: \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password
    =Devops321 cart . yaml
    PLAY \[cart\]
    \* \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \*
    ok: \[cart . chowdarychilukuri . in\]
    TASK \[disable old nodejs and enable nodejs\]
    \* \* \* \*
    changed: \[cart . chowdarychilukuri . in\]
    TASK \[Install nodejs\] \*\*\*\*\*\*\*\*\*\*\* \*
    changed: \[cart . chowdarychilukuri . in\]
    TASK \[create roboshop user\] \* \* \* \*\*\*\*

[^58]: \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password
    =Devops321 cart . yaml
    PLAY \[cart\]
    \* \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \*
    ok: \[cart . chowdarychilukuri . in\]
    TASK \[disable old nodejs and enable nodejs\]
    \* \* \* \*
    changed: \[cart . chowdarychilukuri . in\]
    TASK \[Install nodejs\] \*\*\*\*\*\*\*\*\*\*\* \*
    changed: \[cart . chowdarychilukuri . in\]
    TASK \[create roboshop user\] \* \* \* \*\*\*\*

[^59]: TASK \[deamon realod and start\]
    \* \*
    ok: \[cart . chowdarychilukuri . in\]
    TASK \[start and enable cart\] \*\*\*\*\*\*\*\*\*\*
    changed: \[cart . chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \*
    \* \* \* \* \*
    cart . chowdarychilukuri . in : ok=12
    changed=9
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^60]: F
    C
    Not secure \| chowdarychilukuri.in/cart
    Stan's Robot Shop
    Login / Register
    Shopping cart for satyaa
    Cart
    QTY
    Name Sub Total
    4
    HAL
    E8004.00
    E8004.00
    Categories
    Inc Tax E1334.00
    . Artificial
    Total
    E8004.00
    Intelligence
    Checkout
    o HAL
    o Positronic
    Brain
    o Stan
    Robot
    satyaa

[^61]: Robosho-shellscripts > ! mysql.yaml
    1
    name: install mysql component
    2
    hosts: mysql
    3
    become : yes
    4
    tasks :
    5
    name: disable current version of mysql
    6
    ansible. builtin. command: dnf module disable mysql -y
    7
    8
    name: setup mysql5.7 repo
    9
    ansible . builtin . copy :
    10
    src: mysql . repo
    11
    dest: /etc/yum. repos . d/mysql . repo
    12
    13
    name: install mysql server
    14
    ansible. builtin . package:
    15
    name: mysql-community-server
    16
    state: present
    17
    18
    name: start and enable mysql
    19
    ansible. builtin . service:
    20
    name: mysqld
    21
    state: started
    22
    enabled: yes
    23
    24
    name: setup root password
    25
    ansible . builtin . command: mysql_secure_installation --set-root-pass RoboShop@1

[^62]: roboshop-ansible > @ mysql.repo
    H
    \[mysql \]
    12
    name=MySQL 5.7 Community Server
    3
    baseur1=http://repo. mysql . com/yum/mysql-5 .7-community/e1/7/$basearch/
    4
    enabled=1
    5
    gpgcheck=0

[^63]: mysql . repo
    mysql . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "mysql"; git push origin main

[^64]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 mysql . yaml
    PLAY \[install mysql component\]
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\* \*
    ok: \[mysql . chowdarychilukuri . in\]
    TASK \[disable current version of mysql\]
    \* \* \*
    changed: \[mysql . chowdarychilukuri . in\]
    TASK \[setup mysql5.7 repo\] \*\*\*\*\*\*\*\*\*\*\* \*#
    changed: \[mysql . chowdarychilukuri . in\]
    TASK \[install mysql server\] \*\*\*\*\*\*\*\*\*\*\*
    changed: \[mysql . chowdarychilukuri . in\]
    TASK \[start and enable mysql\] \* \*\*\*\*\*\*\*
    changed: \[mysql . chowdarychilukuri . in\]
    TASK \[setup root password\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*
    changed: \[mysql . chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \*
    mysql . chowdarychilukuri . in : ok=6
    changed=5
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    54. 87.3.19 \| 172.31.25.57 \| t2.micro \| https: //github. com/chilops/roboshop-ansible.git
    \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ \]

[^65]: \[ centos@ip-172-31-17-250 \~ \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0. 0.0.0:\*
    LISTEN
    it cp
    0 0. 0. 0 . 0:22
    0. 0.0.0:\*
    LISTEN
    tcp6
    OOOOO
    0 : : : 3306
    LISTEN
    tcp6
    0
    : : :111
    LISTEN
    tcp6
    : : : 22
    LISTEN

[^66]: \[ centosdip-172-31-18-99 \~ \]$ mysql -h mysql . chowdarychilukuri . in -uroot -pRoboShop@1
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    Welcome to the MySQL monitor. Commands end with ; or \\g.
    Your MySQL connection id is 5
    Server version: 5.7. 44 MySQL Community Server (GPL)
    Copyright (c) 2000, 2021, Oracle and/or its affiliates.
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners.

[^67]: mysql> show databases;
    Database
    +
    information schema
    mysql
    performance schema
    sys
    +
    4 rows in set (0.00 sec)
    mysql>

[^68]: \[ centosdip-172-31-18-99 \~ \]$ mysql -h mysql . chowdarychilukuri . in -uroot -pRoboShop@1 -e "SELECT COUNT (\*) FROM INFORMATION
    SCHEMA . SCHEMATA WHERE SCHEMA NAME= 'mysql'"
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    COUNT (\*)

[^69]: \[ centos@ip-172-31-18-99 \~ \]$ mysql -h mysql . chowdarychilukuri . in -uroot -pRoboShop@1 -SN -e "SELECT COUNT (\*) FROM INFORMA
    ION SCHEMA . SCHEMATA WHERE SCHEMA NAME= 'mysql' "
    mysql: \[Warning\] Using a password on the command line interface can be insecure.

[^70]: roboshop-ansible > ! shipping.yaml
    1
    name: install shipping component
    W N
    hosts: shipping
    4
    become: yes
    5
    vars :
    mysql_password: RoboShop@1
    tasks :
    8
    name: install maven
    9
    ansible . builtin . dnf:
    10
    name: maven
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible. builtin. file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible . builtin . file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download shipping application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3 . amazonaws . com/shipping. zip
    30
    dest: /tmp
    31
    32
    name: extract shipping application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/shipping. zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: install dependencies
    39
    ansible. builtin. command: mvn clean package
    40
    args :
    41
    chdir: /app
    42
    43
    name: rename jar file
    44
    ansible. builtin. command: mv target/shipping-1.0. jar shipping. jar

[^71]: \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password
    =Devops321 shipping . yaml
    PLAY \[install shipping component\]
    \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*
    ok: \[shipping . chowdarychilukuri . in\]
    TASK \[install maven\]
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    changed: \[shipping . chowdarychilukuri . in\]

[^72]: roboshop-ansible > ! shipping.yaml
    1
    name: install shipping component
    W N
    hosts: shipping
    4
    become: yes
    5
    vars :
    mysql_password: RoboShop@1
    tasks :
    8
    name: install maven
    9
    ansible . builtin . dnf:
    10
    name: maven
    11
    state: present
    12
    13
    name: create roboshop user
    14
    ansible . builtin . user :
    15
    name: roboshop
    16
    17
    name: Recursively remove app directory
    18
    ansible. builtin. file:
    19
    path: /app
    20
    state: absent
    21
    22
    name: create app directory
    23
    ansible . builtin . file:
    24
    path: /app
    25
    state: directory
    26
    27
    name: download shipping application
    28
    ansible. builtin. get_url:
    29
    url: https://roboshop-builds . s3 . amazonaws . com/shipping. zip
    30
    dest: /tmp
    31
    32
    name: extract shipping application
    33
    ansible. builtin . unarchive:
    34
    src: /tmp/shipping. zip
    35
    dest: /app
    36
    remote_src: yes
    37
    38
    name: install dependencies
    39
    ansible. builtin. command: mvn clean package
    40
    args :
    41
    chdir: /app
    42
    43
    name: rename jar file
    44
    ansible. builtin. command: mv target/shipping-1.0. jar shipping. jar

[^73]: roboshop-ansible > shipping.service
    \[Unit\]
    2
    Description=Shipping Service
    U
    4
    \[service\]
    15
    User=roboshop
    6
    Environment=CART_ENDPOINT=cart . chowdarychilukuri . in : 8080
    7
    Environment=DB_HOST=mysql . chowdarychilukuri . in
    8
    ExecStart=/bin/java -jar /app/shipping. jar
    9
    SyslogIdentifier=shipping
    10
    11
    \[Install \]
    12
    WantedBy=multi-user . target

[^74]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    shipping. service
    shipping. yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "shipping"; git push origin main

[^75]: \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password
    =Devops321 shipping . yaml
    PLAY \[install shipping component\]
    \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*
    ok: \[shipping . chowdarychilukuri . in\]
    TASK \[install maven\]
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    changed: \[shipping . chowdarychilukuri . in\]

[^76]: \[ centos@ip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password
    =Devops321 shipping . yaml
    PLAY \[install shipping component\]
    \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*
    ok: \[shipping . chowdarychilukuri . in\]
    TASK \[install maven\]
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    changed: \[shipping . chowdarychilukuri . in\]

[^77]: \[ centosdip-172-31-18-99 \~ \]$ mysql -h mysql . chowdarychilukuri . in -uroot -pRoboShop@1
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    Welcome to the MySQL monitor. Commands end with ; or \\g.
    Your MySQL connection id is 22
    Server version: 5.7. 44 MySQL Community Server (GPL)
    Copyright (c) 2000, 2021, Oracle and/or its affiliates.
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners.
    Type 'help; ' or ' \\h' for help. Type ' \\c' to clear the current input statement.
    mysql> show databases;
    Database
    information schema
    cities
    mysql
    performance schema
    sys
    5 rows in set (0.00 sec)

[^78]: centos@ip-172-31-18-99 \~ \]$ mysql -h mysql . chowdarychilukuri . in -uroot -pRoboShop@1 -e "SELECT COUNT (\*) FROM INFORMATION
    SCHEMA . SCHEMATA WHERE SCHEMA NAME= 'cities'"
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    COUNT (\*)
    52. 207 . 250. 124 \| 172. 31. 18. 99 \| t3. small \| null
    centos@ip-172-31-18-99 \~ \]$ \[

[^79]: Not secure \| chowdarychilukuri.in/shipping
    Stan's Robot Shop
    Login / Register
    Shipping information
    Cart
    Select country India
    (953.00
    Enter location Bangalore City
    Categories
    Calculate
    . Artificial
    Intelligence
    . Robot
    . C3PO
    o Eve
    o K9
    o Kryten
    o Marvin
    o Mr Data
    o R2D2
    O
    Robbie
    o Stan
    satayy

[^80]: Stan's Robot Shop
    Login / Register
    Review your order
    Cart
    QTY
    Name
    Sub Total
    (1414.75
    C3PO
    6953.00
    Categories
    1
    shipping to India Bangalore City 6461.75
    . Artificial
    Intelligence
    Inc Tax
    (235.79
    Robot
    Total
    (1414.75
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
    satayy

[^81]: 54 .87 .
    25 .
    https :
    ithub . com/ c
    Lops / roboshop-ansible . g1
    \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$
    ansible-playbook -i inventory . ini -e ansible_user=centos -e ansible_password
    =Devops321 rabbitmq . yaml
    PLAY \[install rabbitmq component\]
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok :
    \[rabbitmq . chowdarychilukuri . in\]
    TA

[^82]: roboshop-ansible > ! rabbitmq.yaml
    1
    name: install rabbitmq component
    2
    hosts: rabbitmq
    3
    become : yes
    14
    tasks :
    5
    name: configure yum erlang repos
    6
    ansible . builtin . shell: curl -s https://packagecloud. io/install/repositories/rabbitmq/erlang/script . rpm. sh \| bash
    7
    8
    name: configure yum rabbitmq repos
    9
    ansible . builtin. shell: curl -s https: //packagecloud . io/install/repositories/rabbitmq/rabbitmq-server/script . rpm. sh \| bash
    10
    11
    name: install rabbitmq server
    12
    ansible . builtin . dnf:
    13
    name: rabbitmq-server
    14
    state: present
    15
    16
    name: start and enable rabbitmq
    17
    ansible . builtin . service:
    18
    name: rabbitmq-server
    19
    state: restarted
    20
    enabled: yes
    21
    22
    name: create rabbitmq user
    23
    ansible. builtin. command: rabbitmqctl add_user roboshop roboshop123
    24
    25
    name: set permissions
    26
    ansible . builtin. command: rabbitmqctl set_permissions -p / roboshop

[^83]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    payment . yam1
    rabbitmq . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\roboshop-ansible> git add . ; git commit -m "rabbitmq & payment; git push origin main

[^84]: 54 .87 .
    25 .
    https :
    ithub . com/ c
    Lops / roboshop-ansible . g1
    \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$
    ansible-playbook -i inventory . ini -e ansible_user=centos -e ansible_password
    =Devops321 rabbitmq . yaml
    PLAY \[install rabbitmq component\]
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok :
    \[rabbitmq . chowdarychilukuri . in\]
    TA

[^85]: 54 .87 .
    25 .
    https :
    ithub . com/ c
    Lops / roboshop-ansible . g1
    \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$
    ansible-playbook -i inventory . ini -e ansible_user=centos -e ansible_password
    =Devops321 rabbitmq . yaml
    PLAY \[install rabbitmq component\]
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok :
    \[rabbitmq . chowdarychilukuri . in\]
    TA

[^86]: TASK \[set permissions\] \*\*\*
    changed: \[rabbitmq. chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    rabbitmq . chowdarychilukuri . in : ok=7
    changed=6
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^87]: roboshop-ansible > ! payment.yaml
    name: payment
    hosts: payment
    W
    become: yes
    tasks :
    5
    name: Install python packages
    6
    ansible . builtin . dnf :
    name: "{{item}}"
    8
    state: present
    9
    loop :
    10
    - python36
    11
    gcc
    12
    python3-devel
    13
    14
    name: create roboshop user
    15
    ansible . builtin . user :
    16
    name: roboshop
    17
    18
    name: Recursively remove app directory
    19
    ansible . builtin . file:
    20
    path: /app
    21
    state: absent
    22
    23
    name: create app directory
    24
    ansible . builtin . file:
    25
    path: /app
    26
    state: directory
    27
    28
    name: download payment application
    29
    ansible. builtin . get_url:
    30
    url: https://roboshop-builds . s3 . amazonaws . com/payment . zip
    31
    dest: /tmp
    32
    33
    name: extract payment application
    34
    ansible . builtin. unarchive:
    35
    src: /tmp/payment. zip
    36
    dest: /app
    37
    remote_src: yes
    38
    39
    name: Install dependencies
    40
    ansible. builtin. command: pip3.6 install -r requirements . txt
    41
    args :
    42
    chdir: / app
    43
    44
    name: Copy payment service

[^88]: 45
    ansible . builtin . copy :
    46
    src: payment . service
    47
    dest: /etc/systemd/system/payment . service
    48
    49
    name: deamon realod and start
    50
    ansible . builtin . systemd_service:
    51
    daemon_reload: true
    52
    53
    name: start and enable payment
    54
    ansible . builtin . service:
    55
    name: payment
    56
    state: restarted
    57
    enabled: yes

[^89]: roboshop-ansible > = payment.service
    1
    \[Unit\]
    2
    Description=Payment Service
    3
    4
    \[Service \]
    5
    User=root
    6
    WorkingDirectory=/ app
    7
    Environment=CART_HOST=cart . chowdarychilukuri . in
    8
    Environment=CART_PORT=8080
    9
    Environment=USER_HOST=user . chowdarychilukuri . in
    10
    Environment=USER_PORT=8080
    11
    Environment=AMQP_HOST=rabbitmq . chowdarychilukuri . in
    12
    Environment=AMQP_USER=roboshop
    13
    Environment=AMQP_PASS=roboshop123
    14
    15
    ExecStart=/usr/local/bin/uwsgi --ini payment. ini
    16
    ExecStop=/bin/kill -9 $MAINPID
    17
    SyslogIdentifier=payment
    18
    19
    \[Install \]
    20
    WantedBy=multi-user . target

[^90]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    payment . service
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\roboshop-ansible> git add . ; git commit -m "\[payment"; git push origin main

[^91]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 payment . yaml
    PLAY \[payment \] \* \* \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*
    ok: \[payment . chowdarychilukuri . in\]
    TASK \[Install python packages\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\* \*
    ok: \[payment . chowdarychilukuri . in\] => (item=python36)
    changed: \[payment . chowdarychilukuri . in\] => (item=gcc)
    changed: \[payment . chowdarychilukuri . in\] => (item=python3-devell

[^92]: \[ centosdip-172-31-25-57 \~/roboshop-ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible password
    =Devops321 payment . yaml
    PLAY \[payment \] \* \* \* \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*
    ok: \[payment . chowdarychilukuri . in\]
    TASK \[Install python packages\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\* \*
    ok: \[payment . chowdarychilukuri . in\] => (item=python36)
    changed: \[payment . chowdarychilukuri . in\] => (item=gcc)
    changed: \[payment . chowdarychilukuri . in\] => (item=python3-devell

[^93]: TASK \[start and enable payment\] \* \* \* \*\*
    changed: \[payment . chowdarychilukuri . in\]
    PLAY RECAP \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \*
    payment . chowdarychilukuri . in : ok=11
    changed=8
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^94]: Not secure \| chowdarychilukuri.in/payment
    Stan's Robot Shop
    Login / Register
    Review your order
    Cart
    Order placed 175eb4fd-18db-46d9-a3db-5ec6cc0e8b9a
    Empty
    Thank you for your order Continue shopping
    Categories
    . Artificial
    Intelligence
    HAL
    o Positronic
    Brain
    o Stan
    . Robot

