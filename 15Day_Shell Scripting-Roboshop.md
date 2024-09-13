---
title: 15Day_Shell Scripting-Roboshop
uuid: 63458fde-0f57-11ef-af7b-a6f126245c9e
version: 390
created: '2024-05-11T10:59:07+05:30'
tags:
  - shell
  - shellscripting
  - shellscript-roboshop
---

***Topics:  This Day15 session we can launch full website with shellscript***

 

1. *<mark style="background-color:#f8d616;">Creating AWS instances - user, cart, catalogue, web & redis. Along with mongodb(t3.small)<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Route53 record creation<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">MongoDB instance configure<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f8914d;">t3.small<!-- {"backgroundCycleColor":"24"} --></mark>*

1. *<mark style="background-color:#f8d616;">Catalogue instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Set -e --> to reduce validate commands in shell scripts<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Redis instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">User instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Cart instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Mysql instance configure<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f8914d;">t3.small<!-- {"backgroundCycleColor":"24"} --></mark>*

1. *<mark style="background-color:#f8d616;">Shipping instance configure<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f8914d;">t3.small<!-- {"backgroundCycleColor":"24"} --></mark>*

1. *<mark style="background-color:#f8d616;">Rabbitmq instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Payment instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Web instance configure<!-- {"backgroundCycleColor":"25"} --></mark>*

\

*<mark style="background-color:#f8914d;">**Creating AWS instances - user, cart, catalogue, web & redis Along with mongodb(t3.small):**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

![be059776-4c2f-4052-91f0-e0b2816aded9.png|863.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/be059776-4c2f-4052-91f0-e0b2816aded9.png) [^1]

 

![0fbce720-dc4d-46a8-9d76-0e92c9f3a7c2.png|875.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/0fbce720-dc4d-46a8-9d76-0e92c9f3a7c2.png) [^2]

 

 

*<mark style="background-color:#f8914d;">**Route53 record creation. WEB instance IP is public IP, remaining (cart, catalogue, mongodb, redis, user) are private IP's as below screenshot.**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

![597b3566-decc-4721-b630-9d78b6385187.png|899.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/597b3566-decc-4721-b630-9d78b6385187.png) [^3]

 

![06e3f661-c23b-4494-9459-a65c39922e3a.png|899.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/06e3f661-c23b-4494-9459-a65c39922e3a.png) [^4]

 

 

 

*<mark style="background-color:#f8914d;">**MongoDB instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Cloning a git repository to mongoDB instance*

![5c199b64-5488-4e09-b137-41ea910295a2.png|779.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/5c199b64-5488-4e09-b137-41ea910295a2.png) [^5]

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![39a2d302-d122-400f-a19e-af77798ccecb.png|822.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/39a2d302-d122-400f-a19e-af77798ccecb.png) [^6]

 

 

*Now installing required software's using shell scripts which we placed already*

```
sudo sh Mongodb.sh
```

![7368ee39-b949-4502-b1fa-f27b2912c3fc.png|823.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/7368ee39-b949-4502-b1fa-f27b2912c3fc.png) [^7]

 

*To check 27017 service is running or not (mongodb)*

```
netstat -lntp 
```

![e9c90585-1ab0-4ef5-b6b8-c5d920d1e3c7.png|869.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/e9c90585-1ab0-4ef5-b6b8-c5d920d1e3c7.png) [^8]

 

*To check logs*

```
sudo less /var/log/messages | grep -i mongodb
```

 

![6578defc-551c-47a4-8bff-4a03a4398560.png|815.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/6578defc-551c-47a4-8bff-4a03a4398560.png) [^9]

 

 

 *<mark style="background-color:#f8914d;">**Catalogue instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Cloning a git repository to catalogue instance*

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![2b609617-cf51-44d4-ac96-6903be744873.png|763.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/2b609617-cf51-44d4-ac96-6903be744873.png) [^10]

 

 

*Now installing required software's using shell scripts which we placed already*

```
sudo sh catalogue.sh
```

![29bab4db-c856-4369-86d3-e98cef1e3d70.png|733.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/29bab4db-c856-4369-86d3-e98cef1e3d70.png) [^11]

 

*To check logs if mongodb connected or not.*

```
sudo less /var/log/messages | grep -i mongodb
```

*Or*

```
sudo less /var/log/messages | grep -i catalogue
```

![02d071b2-8954-4f69-a525-4e8010676dc6.png|823.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/02d071b2-8954-4f69-a525-4e8010676dc6.png) [^12]

 

 

***Set -e --> By using set -e it stops script execution when a wrong command comes in, to reduce validate commands in shell scripts (without exit status)***

![1178eb90-5c69-4df2-9a42-689133b4b3a7.png|354](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1178eb90-5c69-4df2-9a42-689133b4b3a7.png) [^13]

 

```
cd shellscripts
```

```
git status
```

```
git add . ; git commit -m "added latest mongodb modifications"; git push origin main
```

```
git status
```

![3fba0bf0-8d8a-4fde-b1d8-946d8b7f2355.png|601](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/3fba0bf0-8d8a-4fde-b1d8-946d8b7f2355.png) [^14]

![3fba0bf0-8d8a-4fde-b1d8-946d8b7f2355.png|598](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/3fba0bf0-8d8a-4fde-b1d8-946d8b7f2355.png) [^15]

 

*Executing shellscript in /tmp folder in any instance*

 

```
cd /tmp/
```

*#git clone* [*https://github.com/chilops/shellscripts.git*](https://github.com/chilops/shellscripts.git) 

```
ls -l
```

```
cd shellscripts/
```

```
ls
```

![25f3f1a0-25a3-4892-a54b-83e79c138c73.png|849.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/25f3f1a0-25a3-4892-a54b-83e79c138c73.png) [^16]

 

```
sh 14.without-exit-status.sh    --> scripts automatically stops when a wrong command executes as below 
```

![b72cd690-a28d-4b58-b79d-14ac1c1b56b9.png|810.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/b72cd690-a28d-4b58-b79d-14ac1c1b56b9.png) [^17]

 

 

*<mark style="background-color:#f8914d;">**Redis instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Shellscript as below*

![7470d1bb-ddbb-4908-80ae-c59736c92716.png|696](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/7470d1bb-ddbb-4908-80ae-c59736c92716.png) [^18]

![7470d1bb-ddbb-4908-80ae-c59736c92716.png|681](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/7470d1bb-ddbb-4908-80ae-c59736c92716.png) [^19]

 

```
cd .\Robosho-shellscripts\
```

```
git status
```

```
git add . ; git commit -m "added latest redis modifications"; git push origin main
```

```
git status
```

![76e51f3f-0e0d-4022-a964-1c85d880d6ac.png|529](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/76e51f3f-0e0d-4022-a964-1c85d880d6ac.png) [^20]

 

![b8618402-3521-4a9f-9563-82ed4497fba9.png|484](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/b8618402-3521-4a9f-9563-82ed4497fba9.png) [^21]

 

*Now connect to Redis instance & clone git*

![1b155081-4356-4ba0-914c-51d2e5e74ba7.png|916.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1b155081-4356-4ba0-914c-51d2e5e74ba7.png) [^22]

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![8e30e4e8-df0d-49c7-8949-d079e87fbdc1.png|813.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/8e30e4e8-df0d-49c7-8949-d079e87fbdc1.png) [^23]

 

 

*Running redis shellscript to setup*

 

*Here it will run in the background since we used below line in the script*

```
sudo sh redis.sh            
```

```
tail -f /tmp/redis.sh-2024-04-18-06-44-43.log   --> to check background how its running use this command it will show in details
```

![](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/8de6ffe3-1d93-4062-9099-b2cb613d86ef.png) [^24]

 

![15d82fba-3575-4f52-aa5f-3fc879dfa518.png|999.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/15d82fba-3575-4f52-aa5f-3fc879dfa518.png) [^25]

 

![ea4fca0a-7dd4-4320-b0f9-3817db5a7e31.png|993.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/ea4fca0a-7dd4-4320-b0f9-3817db5a7e31.png) [^26]

 

```
netstat -lntp     --> to check if redis service 6379 is running or not 
```

![00454b11-3f66-4407-aeba-68413dc01947.png|984.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/00454b11-3f66-4407-aeba-68413dc01947.png) [^27]

 

 

*To check redis service & restart*

```
sudo systemctl restart redis
```

```
netstat -lntp  
```

```
sudo systemctl status redis
```

 

![d257ad1c-469f-4abb-86b6-ce05dbd48999.png|866.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/d257ad1c-469f-4abb-86b6-ce05dbd48999.png) [^28]

 

***User instance configure***

 

*Shellscript as below  - change below highlighted with hostname or IP's*

![1cc3936d-1997-47cb-ba26-7ac26527c614.png|833](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1cc3936d-1997-47cb-ba26-7ac26527c614.png) [^29]

![d23571c5-cdb6-46b3-8e4e-7d5220bb7bf5.png|858](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/d23571c5-cdb6-46b3-8e4e-7d5220bb7bf5.png) [^30]

![d23571c5-cdb6-46b3-8e4e-7d5220bb7bf5.png|881](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/d23571c5-cdb6-46b3-8e4e-7d5220bb7bf5.png) [^31]

![aa585260-7c89-4579-85ce-0ae920558e11.png|876](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/aa585260-7c89-4579-85ce-0ae920558e11.png) [^32]

 

*User.service file --> change below highlighted with hostname or IP's*

 

![b554b236-c5b4-4ba0-83cb-e0b0f30de989.png|963.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/b554b236-c5b4-4ba0-83cb-e0b0f30de989.png) [^33]

 

 

```
cd .\Robosho-shellscripts\
```

```
git status
```

```
git add . ; git commit -m "added latest user modifications"; git push origin main
```

```
git status
```

 

![b03c4a53-47c6-459b-a069-ef429fa159ad.png|556](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/b03c4a53-47c6-459b-a069-ef429fa159ad.png) [^34]

![b03c4a53-47c6-459b-a069-ef429fa159ad.png|552](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/b03c4a53-47c6-459b-a069-ef429fa159ad.png) [^35]

 

*Now connect to user instance*

![5830e4fa-fa68-4ddf-b0cd-1c58630eef30.png|811.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/5830e4fa-fa68-4ddf-b0cd-1c58630eef30.png) [^36]

 

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![d15909ab-025e-4e45-bb55-168a6193e85f.png|854.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/d15909ab-025e-4e45-bb55-168a6193e85f.png) [^37]

 

```
git pull   _ use if necessary
```

```
sudo sh user.sh     --> script execution & setup
```

 

![6e8c3949-7561-46a2-92ff-351f2cbf58c6.png|881.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/6e8c3949-7561-46a2-92ff-351f2cbf58c6.png) [^38]

 

*To check logs if mongodb connected & redis ready*

```
 sudo less /var/log/messages | grep -i mongodb
```

```
sudo less /var/log/messages | grep -i redis
```

![30f42084-1c5f-4145-bf0e-0e23272a670c.png|970.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/30f42084-1c5f-4145-bf0e-0e23272a670c.png) [^39]

 

![4182b938-c2c7-4b5f-b617-8866e6339a21.png|968.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/4182b938-c2c7-4b5f-b617-8866e6339a21.png) [^40]

 

 

 

*<mark style="background-color:#f8914d;">**Cart instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

![a86741fa-6ef4-43b8-aa47-22674a854628.png|820](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/a86741fa-6ef4-43b8-aa47-22674a854628.png) [^41]

*Cart script*

![042e47ab-dadd-43d2-bae8-b2a2ac2d8b0d.png|913](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/042e47ab-dadd-43d2-bae8-b2a2ac2d8b0d.png) [^42]

![cc3a7962-30a1-4060-80ed-092ef938a426.png|955](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/cc3a7962-30a1-4060-80ed-092ef938a426.png) [^43]

\

 

*Cart.service file - change below highlighted entries with FQDN or IP's*

![e1b227d3-43a4-439a-a88b-565632c0e168.png|945.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/e1b227d3-43a4-439a-a88b-565632c0e168.png) [^44]

 

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

 

![87382493-3a82-4f50-84f2-3be37e398e87.png|875.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/87382493-3a82-4f50-84f2-3be37e398e87.png) [^45]

 

 

*Connect to cart instance*

![bd021575-b97d-4a6d-8a1a-caa15cf8cadc.png|908.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/bd021575-b97d-4a6d-8a1a-caa15cf8cadc.png) [^46]

 

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

![be853fab-928b-4562-8086-46386f26d030.png|919.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/be853fab-928b-4562-8086-46386f26d030.png) [^47]

 

![95045c98-e1f8-4d41-a227-f544722166c8.png|920.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/95045c98-e1f8-4d41-a227-f544722166c8.png) [^48]

![95045c98-e1f8-4d41-a227-f544722166c8.png|918.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/95045c98-e1f8-4d41-a227-f544722166c8.png) [^49]

 

```
sudo sh cart.sh   --> cart script execution & setup
```

 

![95045c98-e1f8-4d41-a227-f544722166c8.png|997.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/95045c98-e1f8-4d41-a227-f544722166c8.png) [^50]

![95045c98-e1f8-4d41-a227-f544722166c8.png|998.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/95045c98-e1f8-4d41-a227-f544722166c8.png) [^51]

![0f15f159-64a4-496e-9027-1a5f161f98d6.png|995](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/0f15f159-64a4-496e-9027-1a5f161f98d6.png) [^52]

 

```
sudo less /var/log/messages | grep -i cart    --> to check logs if cart/redis running & ready
```

![cd3fb72b-206e-4a14-9356-18cb1d95306e.png|984.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/cd3fb72b-206e-4a14-9356-18cb1d95306e.png) [^53]

 

```
netstat -lntp
```

![020ddd8d-ed41-445d-9534-b165ed361598.png|925.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/020ddd8d-ed41-445d-9534-b165ed361598.png) [^54]

\

*<mark style="background-color:#f8914d;">**Web instance configure**:<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Web script*

![2503743e-6486-4fc0-ade9-07a91154c382.png|852](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/2503743e-6486-4fc0-ade9-07a91154c382.png) [^55]

![dfbe3420-7946-4e50-9b31-7ce93f6fa53c.png|887](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/dfbe3420-7946-4e50-9b31-7ce93f6fa53c.png) [^56]

 

*Roboshop.conf file for script   -- change with FQDN or IP's below highlighted*

![222c07f8-002b-4e2f-a5cb-6cfde937a77b.png|906.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/222c07f8-002b-4e2f-a5cb-6cfde937a77b.png) [^57]

 

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

![d288bc3a-1450-492e-afdb-462e03fc8a70.png|955.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/d288bc3a-1450-492e-afdb-462e03fc8a70.png) [^58]

 

*Connect to web instance*

 

![3f9d72d9-0621-44c7-a712-0c2684557d34.png|908](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/3f9d72d9-0621-44c7-a712-0c2684557d34.png) [^59]

 

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![a12f9471-6a18-4d26-ba0f-4bd39ae705aa.png|838.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/a12f9471-6a18-4d26-ba0f-4bd39ae705aa.png) [^60]

 

\

```
netstat -lntp    -->Before script execution
```

![16a1d257-db2e-4d54-87c7-0c2cb3d480e0.png|847](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/16a1d257-db2e-4d54-87c7-0c2cb3d480e0.png) [^61]

```
sudo sh web.sh   --> web script execution & setup
```

![0a7b5397-1d53-4deb-8c44-73f557172bc2.png|919.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/0a7b5397-1d53-4deb-8c44-73f557172bc2.png) [^62]

 

\

```
netstat -lntp    -->After script execution
```

![eb6b08b6-55de-40c5-96bd-7d881ec3f7a0.png|922.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/eb6b08b6-55de-40c5-96bd-7d881ec3f7a0.png) [^63]

 

 

```
sudo systemctl status nginx              --> nginx service check
```

```
sudo less /var/log/messages | grep -i nginx    --> nginx logs
```

 

![e3a7447e-2ce8-4fa0-9e69-75711adc321f.png|1009.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/e3a7447e-2ce8-4fa0-9e69-75711adc321f.png) [^64]

 

![ee01bc89-8c43-4f3b-9fcb-747ecf58592d.png|928.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/ee01bc89-8c43-4f3b-9fcb-747ecf58592d.png) [^65]

 

 

*Now website is ready & successful*

![9e3f20aa-dd14-4dbc-9293-037a512b8f4b.png|993.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/9e3f20aa-dd14-4dbc-9293-037a512b8f4b.png) [^66]

 

*<mark style="background-color:#f8914d;">**Mysql instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Creating MYSQL & Shipping t3.small instances*

![05cb1852-a8e3-40b7-be73-7125c5c98678.png|820](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/05cb1852-a8e3-40b7-be73-7125c5c98678.png) [^67]

 

![121b259d-ef6f-4feb-82b8-ee98cce8c9b7.png|898](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/121b259d-ef6f-4feb-82b8-ee98cce8c9b7.png) [^68]

 

 

*Creating route53 records for mysql & shipping*

![6dd212a1-f551-493d-b777-f345780629c3.png|892.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/6dd212a1-f551-493d-b777-f345780629c3.png) [^69]

 

![184a6cfc-390f-4b26-88f3-84ba0d69227d.png|924.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/184a6cfc-390f-4b26-88f3-84ba0d69227d.png) [^70]

 

***Mysql script***

![fec6d570-bb77-4bb2-8069-1fc7c3f754ff.png|727](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/fec6d570-bb77-4bb2-8069-1fc7c3f754ff.png) [^71]

![18df703b-5edd-4c23-a144-7805c0ef485a.png|646](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/18df703b-5edd-4c23-a144-7805c0ef485a.png) [^72]

 

*Mysql.repo*

![cb504ffe-f998-4176-8348-310d6caa55b6.png|803.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/cb504ffe-f998-4176-8348-310d6caa55b6.png) [^73]

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

![5b22f6c2-0e80-43b8-ac63-c52840e1bae2.png|609](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/5b22f6c2-0e80-43b8-ac63-c52840e1bae2.png) [^74]

 

![ef848837-9a98-4609-a3db-4324c4fdbab3.png|902.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/ef848837-9a98-4609-a3db-4324c4fdbab3.png) [^75]

 

*Connect to MYSQL instance*

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![5a0f6c99-871e-4aa0-9201-de8759032850.png|879.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/5a0f6c99-871e-4aa0-9201-de8759032850.png) [^76]

 

```
sudo sh mysql.sh
```

![6c7ae6af-3e0b-4e33-bece-dd9bc288b6d7.png|915.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/6c7ae6af-3e0b-4e33-bece-dd9bc288b6d7.png) [^77]

 

![9076a422-550a-437e-b8c6-96ecb068417f.png|889.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/9076a422-550a-437e-b8c6-96ecb068417f.png) [^78]

 

```
netstat -lntp
```

![09dec35a-6b2d-4856-a4b9-8ec71c6c83ae.png|914.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/09dec35a-6b2d-4856-a4b9-8ec71c6c83ae.png) [^79]

 

\

 *<mark style="background-color:#f8914d;">**Shipping instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Shipping script*

![f9b3df19-e479-4ca4-9df5-793e97f1acb0.png|851](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/f9b3df19-e479-4ca4-9df5-793e97f1acb0.png) [^80]

![b720b41c-95e6-4802-af6f-5f1f123171f5.png|993](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/b720b41c-95e6-4802-af6f-5f1f123171f5.png) [^81]

![4ebc5609-dce6-482c-a097-6daad4378848.png|992](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/4ebc5609-dce6-482c-a097-6daad4378848.png) [^82]

 

*Shipping.service file - update with FQDN or IP's*

![e9c9b372-afaf-44c0-b908-c5229b2cf9ca.png|895.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/e9c9b372-afaf-44c0-b908-c5229b2cf9ca.png) [^83]

 

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

 

![26dbd6b2-39fc-4bdc-927d-ab25200f2e87.png|919.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/26dbd6b2-39fc-4bdc-927d-ab25200f2e87.png) [^84]

 

*Now connect to shipping instance*

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![05fdfb0d-734b-4cd0-9e08-6ea886f6426e.png|895.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/05fdfb0d-734b-4cd0-9e08-6ea886f6426e.png) [^85]

 

```
sudo sh shipping.sh
```

![3037de3e-003f-425b-8ee6-415e3eaa3ce3.png|960.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/3037de3e-003f-425b-8ee6-415e3eaa3ce3.png) [^86]

 

```
netstat -lntp 
```

![bc444b79-de44-4568-893a-6c3883d73074.png|959.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/bc444b79-de44-4568-893a-6c3883d73074.png) [^87]

 

*<mark style="background-color:#f8914d;">**Rabbitmq instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Launch 2 instances -rabbitmq, payments*

 

![8142d971-06dd-4aed-8b1b-0516a917b05f.png|963.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/8142d971-06dd-4aed-8b1b-0516a917b05f.png) [^88]

 

![e88134ca-44f3-4dd8-89da-5c175aa860d5.png|919](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/e88134ca-44f3-4dd8-89da-5c175aa860d5.png) [^89]

 

 

*Create route53 records for rabbitmq, payments*

![f4587dff-b79a-43ca-b09c-2a338f17e2f2.png|908.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/f4587dff-b79a-43ca-b09c-2a338f17e2f2.png) [^90]

 

![2096e9af-ca8f-4e06-a686-9adc4a13abbf.png|899.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/2096e9af-ca8f-4e06-a686-9adc4a13abbf.png) [^91]

 

 

*Rabbitmq script*

![46c6e877-cdd3-4cdd-b045-4191b21d2818.png|852.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/46c6e877-cdd3-4cdd-b045-4191b21d2818.png) [^92]

![a4801288-3902-4fad-b336-bd6bed2d1e98.png|687](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/a4801288-3902-4fad-b336-bd6bed2d1e98.png) [^93]

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

![1f869c76-220d-4250-8563-d2bdfd68845e.png|813.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1f869c76-220d-4250-8563-d2bdfd68845e.png) [^94]

 

*Connect to rabbitmq instance*

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

![d95ba0d0-8103-427b-a375-8be9ecad7b00.png|918.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/d95ba0d0-8103-427b-a375-8be9ecad7b00.png) [^95]

 

```
sudo sh rabbitmq.sh
```

![4875dd94-99e6-4b4c-9b10-24f001826e50.png|921.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/4875dd94-99e6-4b4c-9b10-24f001826e50.png) [^96]

 

```
netstat -lntp
```

![de5c8280-ba94-4188-afca-c6928b78a106.png|922.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/de5c8280-ba94-4188-afca-c6928b78a106.png) [^97]

 

*<mark style="background-color:#f8914d;">**Payments instance configure**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Payments script*

![](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/31c21634-35af-4480-b69b-1e91bb9eaf54.png) [^98]

![](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/31c21634-35af-4480-b69b-1e91bb9eaf54.png) [^99]

 

*Payments.service file  --> update with FQDN or IP's*

![96afbd82-f979-4962-8e6a-a9e8da668c24.png|824](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/96afbd82-f979-4962-8e6a-a9e8da668c24.png) [^100]

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

![e070d35a-36ee-4125-85f8-7cb27b26c916.png|880.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/e070d35a-36ee-4125-85f8-7cb27b26c916.png) [^101]

 

*Connect to payment instance*

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

![39114796-9c98-45c0-ba64-abec48742bd9.png|844.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/39114796-9c98-45c0-ba64-abec48742bd9.png) [^102]

 

```
sudo sh payment.sh
```

![360e7035-8c33-44ac-85b6-6e6199af1ca8.png|980.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/360e7035-8c33-44ac-85b6-6e6199af1ca8.png) [^103]

 

 

 

*<mark style="background-color:#f8914d;">**Web instance configure**:<!-- {"backgroundCycleColor":"24"} --></mark>*

 

*Web script*

![ddcf22be-d457-46ab-b5f3-b9ea241ed639.png|832](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/ddcf22be-d457-46ab-b5f3-b9ea241ed639.png) [^104]

![1a53b285-6dcb-474a-85de-088a60d60c35.png|851](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1a53b285-6dcb-474a-85de-088a60d60c35.png) [^105]

 

 

*Roboshop.conf file for script   -- change with FQDN or IP's below highlighted*

 

![dc743cc5-638a-498d-bb94-c6c1b28164ef.png|874.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/dc743cc5-638a-498d-bb94-c6c1b28164ef.png) [^106]

 

 

```
git status
```

```
git add . ; git commit -m "added latest cart modifications"; git push origin main
```

```
git status
```

![64b0a39a-3526-4e43-8d7f-652543428b91.png|883.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/64b0a39a-3526-4e43-8d7f-652543428b91.png) [^107]

 

*Connect to web instance*

 

![fbb60fd8-3351-46bb-9ca8-f488dcaac6c0.png|931](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/fbb60fd8-3351-46bb-9ca8-f488dcaac6c0.png) [^108]

 

 

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

```
ls -l
```

```
cd Roboshop-shellscripts/
```

```
ls -l
```

 

![1e6a8509-28ca-42c4-895c-a9fe5f565b55.png|853.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1e6a8509-28ca-42c4-895c-a9fe5f565b55.png) [^109]

 

```
sudo sh web.sh   --> web script execution & setup
```

![1e7ed2d1-9079-42c2-9ab8-4482d9909588.png|841.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/1e7ed2d1-9079-42c2-9ab8-4482d9909588.png) [^110]

 

```
netstat -lntp    -->Before script execution
```

![00ab7215-4026-48ed-bc85-128fa5edbec0.png|846.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/00ab7215-4026-48ed-bc85-128fa5edbec0.png) [^111]

 

```
netstat -lntp    -->After script execution
```

![79005d48-ea57-4175-aff5-7fd311b7489c.png|834.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/79005d48-ea57-4175-aff5-7fd311b7489c.png) [^112]

 

 

```
sudo systemctl status nginx              --> nginx service check
```

```
sudo less /var/log/messages | grep -i nginx    --> nginx logs
```

 

![620d29dc-f871-4373-a848-db8614629f67.png|849.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/620d29dc-f871-4373-a848-db8614629f67.png) [^113]

 

![8eeaf3a0-660e-4afc-a8ab-3848a9458a98.png|840.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/8eeaf3a0-660e-4afc-a8ab-3848a9458a98.png) [^114]

 

 

*Now website is ready & successful*

![212aca31-c6ca-4ce5-b40d-d4fde0b7efbe.png|973.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/212aca31-c6ca-4ce5-b40d-d4fde0b7efbe.png) [^115]

 

![58e852dc-f006-4bc4-9815-36c60fe1aa11.png|969.3333740234375](https://images.amplenote.com/63458fde-0f57-11ef-af7b-a6f126245c9e/58e852dc-f006-4bc4-9815-36c60fe1aa11.png) [^116]

 

 

 

 

 

 

[^1]: Instances (5) Info
    C
    Connect
    Instance state
    Actions
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Instance state = running
    X
    Clear filters
    Name _
    4
    Instance ID
    Instance state
    4
    Instance type
    Status check
    web
    i-0egef75e92462b48e
    Running
    t2.micro
    Initializing
    catalogue
    i-0e86eed272bc3bcge
    Running
    t2.micro
    Initializing
    user
    i-Odaaacb0a2037e3b2
    Running
    t2.micro
    Initializing
    cart
    i-096d1c66b6daabae
    Running
    t2.micro
    Initializing
    redis
    i-0bbba44738f78794c
    Running
    t2.micro
    Initializing

[^2]: Q Find Instance by attribute or tag (case-sensitive)
    All states
    Instance state = running
    X
    Clear filters
    Name _
    4
    Instance ID
    Instance state
    4
    Instance type v Status check
    Alarm status
    Mongodb
    i-089f072963693772f
    Running
    t3.small
    Initializing
    View alarms +

[^3]: chowdarychilukuri.in was successfully updated.
    View status
    X
    Edit record
    X
    Route 53 propagates your changes to all of the Route 53 authoritative DNS servers
    within 60 seconds. Use "View status" button to check propagation status.
    Record name Info
    subdomain
    chowdarychilukuri.in
    Keep blank to create a record for the root domain.
    Records (8)
    DNSSEC signing
    Hosted zone tags (0)
    Record type Info
    A - Routes traffic to an IPv4 address and so...
    Records (1/8) Info
    Alias
    G
    Delete record
    Import zone file
    Create record
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    Value Info
    Q Filter records by property or value
    54.152.150.169
    Type
    Routing policy
    Alias
    <
    1
    Enter multiple values on separate lines.
    -
    Record name
    Type
    4
    Routin...
    4
    Differ...
    Alias
    TTL (seconds) Info
    V
    chowdarychilukuri.in
    A
    Simple
    No
    1
    1m
    1h
    1d
    Recommended values: 60 to 172800 (two days)
    0
    chowdarychilukuri.in
    NS
    Simple
    No
    Routing policy Info
    Simple routing
    O
    chowdarychilukuri.in
    SOA
    Simple
    No
    Cancel
    Save
    O
    cart.chowdarychilukuri.in
    A
    Simple
    No
    O
    catalogue.chowdarychilukuri.in
    A
    Simple
    No
    mongodb.chowdarychilukuri.in
    A
    Simple
    No

[^4]: Route 53
    X
    Hosted zone details
    Edit hosted zone
    Dashboard
    Records (8)
    DNSSEC signing
    Hosted zone tags (0)
    Hosted zones
    Health checks
    Records (1/8) Info
    C
    Delete record
    Import zone file
    Create record
    IP-based routing
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    CIDR collections
    Q Filter records by property or value
    Type
    Routing policy
    Alias
    <
    1
    Traffic flow
    Traffic policies
    Record name
    Type Routin... V Differ... V Alias
    A
    Value/Route traffic to
    V TTL (S...
    Policy records
    V
    chowdarychilukuri.in
    A
    Simple
    No
    54.152.150.169
    7
    Domains
    ns-59.awsdns-07.com.
    Registered domains
    ns-1889.awsdns-44.co.uk.
    0
    chowdarychilukuri.in
    NS
    Simple
    No
    172800
    Requests
    ns-1039.awsdns-01.org.
    ns-836.awsdns-40.net.
    Resolver
    O
    chowdarychilukuri.in
    SOA
    Simple
    No
    ns-59.awsdns-07.com. awsdn...
    900
    VPCs
    Inbound endpoints
    0
    cart.chowdarychilukuri.in
    A
    Simple
    No
    172.31.23.237
    Outbound endpoints
    O
    catalogue.chowdarychilukuri.in
    A
    Simple
    No
    172.31.16.218
    Rules
    O
    mongodb.chowdarychilukuri.in
    A
    Simple
    No
    172.31.22.44
    Query logging
    Outposts
    0
    redis.chowdarychilukuri.in
    A
    Simple
    No
    172.31.22.104
    user.chowdarychilukuri.in
    A
    Simple
    No
    172.31.16.218
    DNS Firew

[^5]: G
    https://github.com/chilops/Roboshop-shellscripts
    E
    chilops / Roboshop-shellscripts
    Q Type to search
    <> Code
    Issues
    87 Pull requests Actions
    Projects Wiki
    Security \~ Insights
    803 Settings
    Roboshop-shellscripts Public
    & Pin
    O Unwatch 1
    & main
    & 1 Branch 0 Tags
    Q Go to file
    t
    Add file
    <> Code
    Local
    Codespaces
    O
    Chowdarychilukuri added latest mongodb modifications
    D- Clone
    Mongodb.sh
    added new mongod
    HTTPS
    SSH
    GitHub CLI
    catalogue.service
    added latest mongo
    catalogue.sh
    https://github. com/chilops/Roboshop-shellscript
    added latest mongo
    Clone using the web URL.
    mongo.repo
    added mongodb ro
    Open with GitHub Desktop
    DO README
    Download ZIP

[^6]: \[ centos@ip-172-31-22-44 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts' .. .
    remote: Enumeratiog objects: 28, done.
    remote: Counting objects: 100% (28/28), done.
    remote: Compressing objects: 100% (21/21), done.
    remote: Total 28 (delta 11), reused 23 (delta 6), pack-reused 0
    Receiving objects: 100% (28/28), done.
    Resolving deltas: 100% (11/11), done.
    54 . 90 . 243.2 \| 172. 31.22. 44 \| t3. small \| null
    \[ centos@ip-172-31-22-44 \~ \]$ 1s -1
    total 0
    drwxrwxr-x 3 centos centos 99 Apr 18 05:27 Roboshop-shellscripts
    54 . 90. 243.2 \| 172. 31. 22. 44 \| t3. small \| null
    \[ centosdip-172-31-22-44 \~ \]$ cd Roboshop-shellscripts/
    54 . 90 .243.2 \| 172. 31. 22. 44 \| t3.small \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-22-44 \~/Roboshop-shellscripts \]$ 1s -1
    total 16
    -rw-rw-r--
    1 centos centos 265 Apr 18 05:27 catalogue . service
    -rw-rw-r--
    1 centos centos 2165 Apr 18 05:27 catalogue. sh
    -rw-rw-r--
    1 centos centos 1043 Apr 18 05:27 Mongodb. sh
    -rw-rw-r--
    1 centos centos 143 Apr 18 05:27 mongo . repo
    54 . 90. 243.2 \| 172. 31. 22. 44 \| t3. small \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-22-44 \~/Roboshop-shellscripts \]$ \[

[^7]: \[ centosdip-172-31-22-44 \~/Roboshop-shellscripts \]$ sudo sh Mongodb. sh
    You are root user
    Copied MongoDB Repo
    SUCCESS
    Installing MongoDB
    SUCCESS
    Enabling MongoDB
    SUCCESS
    Starting MongoDB
    SUCCESS
    Remote access to MongoDB
    . . .
    SUCCESS
    Restarting MongoDB
    SUCCESS
    54 . 90. 243.2 \| 172. 31.22. 44 \| t3. small \| https: //github.com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-22-44 \~/Roboshop-shellscripts \]$\[\]

[^8]: \[ centosdip-172-31-22-44 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    Ecp
    0 0. 0. 0. 0:27017
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    cp
    OOOOO
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    Ecp6
    0 : : :111
    : : :\*
    LISTEN
    Ecp6
    0 : : :22
    LISTEN

[^9]: \[ centosdip-172-31-22-44 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages
    \| grep
    -i mongodb
    Apr 18 05:32:21 ip-172-31-22-44 systemd \[1\]: Starting MongoDB Database Server. ..
    Apr 18 05:32:23 ip-172-31-22-44 systemd \[1\] : Started MongoDB Database Server.
    Apr 18 05:32:23 ip-172-31-22-44 systemd \[1\] : Stopping MongoDB Database Server. .
    Apr 18 05:32:23 ip-172-31-22-44 systemd \[1\]: Stopped MongoDB Database Server.
    Apr 18 05:32:23 ip-172-31-22-44 systemd \[1\]: Starting MongoDB Database Server. . .
    Apr 18 05:32:24 ip-172-31-22-44 systemd \[1\] : Started MongoDB Database Server.
    Apr 18 05:32:24 ip-172-31-22-44 dnf \[4825\] : MongoDB Repository
    27 kB/s \| 1.3 kB
    00: 00
    54 . 90. 243.2 \| 172. 31.22. 44 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-22-44 \~/Roboshop-shellscripts \]$ \|

[^10]: \[ centos@ip-172-31-16-218 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' .. .
    remote: Enumeratiog objects: 28, done.
    remote: Counting objects: 100% (28/28), done.
    remote: Compressing objects: 100% (21/21), done.
    remote: Total 28 (delta 11), reused 23 (delta 6), pack-reused 0
    Receiving objects: 100% (28/28), done.
    Resolving deltas: 100% (11/11), done.
    3. 88 . 176.75 \| 172. 31. 16.218 \| t2.micro \| null
    \[ centosdip-172-31-16-218 \~ \]$ 1s -1
    total 0
    drwxrwxr-x 3 centos centos 99 Apr 18 05:34 Roboshop-shellscripts
    3. 88. 176.75 \| 172. 31. 16.218 \| t2.micro \| null
    \[ centosdip-172-31-16-218 \~ \]$ cd Roboshop-shellscripts/
    3. 88. 176.75 \| 172. 31.16.218 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts . git
    \[ centosdip-172-31-16-218 \~/Roboshop-shellscripts \]$ 1s -1
    total 16
    rw-rw-r--
    1 centos centos 265 Apr 18 05:34 catalogue. service
    rw-rw-r--
    1 centos centos 2165 Apr 18 05:34 catalogue. sh
    rw-rw-r--
    1 centos centos 1043 Apr 18 05:34 Mongodb. sh
    rw-rw-r--
    1 centos centos 143 Apr 18 05:34 mongo . repo

[^11]: \[ centosdip-172-31-16-218 \~/Roboshop-shellscripts \]$ sudo sh catalogue. sh
    You are root user
    Disabling current NodeJS
    SUCCESS
    Enabling NodeJS : 18
    . .
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading catalogue application
    . . .
    SUCCESS
    unzipping catalogue . . .
    SUCCESS
    Installing dependencies
    SUCCESS
    Copying catalogue service file .. .
    SUCCESS
    catalogue daemon reload
    . . .
    SUCCESS
    Enable catalogue . . .
    SUCCESS
    Starting catalogue . . .
    SUCCESS
    copying mongodb repo
    SUCCESS
    Installing MongoDB client . ..
    SUCCESS
    Loading catalouge data into MongoDB
    . . .
    SUCCESS

[^12]: \[ centos@ip-172-31-16-218 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep -i catalogue
    Apr 18 05:35:41 ip-172-31-16-218 systemd \[1\] : Started Catalogue Service.
    Apr 18 05:35: 42 ip-172-31-16-218 catalogue \[7870\]: (node : 7870) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monito
    ring engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine, p
    ass option { useUnifiedTopology: true } to the MongoClient constructor.
    Apr 18 05:35:42 ip-172-31-16-218 catalogue \[7870\]: (Use node --trace-warnings
    to show where the warning was created)
    Apr 18 05:35:42 ip-172-31-16-218 catalogue \[7870\]: {"level": "info", "time" : 1713418542846, "pid": 7870, "hostname": "ip-172-31-16-
    218 . ec2 . internal", "msg": "Started on port 8080", "v":1}
    Apr 18 05:35:42 ip-172-31-16-218 catalogue \[7870\]: {"level":"info", "time" : 1713418542880, "pid" : 7870, "hostname": "ip-172-31-16-
    218. ec2. internal", "msg": "MongoDB
    connected", "v" : 1}

[^13]: shellscripts > $ 14.without-exit-status.sh
    6
    7
    touch example . txt
    8
    9
    echo "Before wrong command"
    10
    11
    Isfff
    12
    13
    echo "After wrong command"
    14
    15
    cd / tmp
    16
    17
    cd / home/centos

[^14]: PS E: \\AWSDevops\\Repos> cd . \\shellscripts\\
    PS E: \\AWSDevops \\Repos\\shellscripts> git status
    On branch main
    Your branch is up to date with 'origin/main' .
    Untracked files:
    (use "git add <file>..." to include in what will be committed)

[^15]: PS E: \\AWSDevops\\Repos> cd . \\shellscripts\\
    PS E: \\AWSDevops \\Repos\\shellscripts> git status
    On branch main
    Your branch is up to date with 'origin/main' .
    Untracked files:
    (use "git add <file>..." to include in what will be committed)

[^16]: \[ centosdip-172-31-22-44 \~/Roboshop-shellscripts \]$ cd /tmp/
    54 . 90 . 243.2 \| 172. 31. 22. 44 \| t3. small \| null
    \[ centosdip-172-31-22-44 /tmp \]$ git clone https: //github. com/chilops/shellscripts.git
    Cloning into 'shellscripts'..
    remote: Enumeratiog objects: 70, done.
    remote: Counting objects: 100% (70/70), done.
    remote: Compressing objects: 100% (52/52), done.
    remote: Total 70 (delta 36), reused 51 (delta 17), pack-reused 0
    Receiving objects: 100% (70/70), 7.66 KiB \| 7.66 MiB/s, done.
    Resolving deltas: 100% (36/36), done.
    54 . 90. 243.2 \| 172. 31.22. 44 \| t3. small \| null
    \[ centos@ip-172-31-22-44 /tmp \]$ 1s -1
    total 12
    -rw-r--r
    root
    root
    222 Apr 18 06:00 idle. out
    srwx-
    1
    mongod mongod
    0 Apr 18 05:32 mongodb-27017 . sock
    -rw-r
    1 root
    root
    3592 Apr 18 05:32 Mongodb. sh-2024-04-18-05-31-22. log
    drwxrwxr-x
    3 centos centos 4096 Apr 18 06:03 shellscripts
    drwx-
    3 root
    root
    17 Apr 18 05:11 systemd-private-fa64f96334914f1995ef7387bd9a2ff3-chronyd. service-ehMI8W
    54 . 90 . 243.2 \| 172. 31. 22. 44 \| t3. small \| null
    centosdip-172-31-22-44 /tmp \]$ cd shellscripts/
    54 . 90. 243.2 \| 172. 31.22. 44 \| t3. small \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-22-44 /tmp/shellscripts \]$ 1s
    01. hello-world. sh 04. variablesArgs.sh 07. arrays. sh
    10 . functions. sh 13. install-packages. sh
    02 . variables. sh
    05 . variables . sh
    08 . conditions . sh
    11 . logs. sh
    14. without-exit-status. sh
    03. variables. sh
    06. datatypes . sh
    09. install-mysql . sh
    12 . loops . sh
    54 . 90. 243.2 \| 172. 31.22. 44 \| t3. small \| https://github. com/chilops/shellscripts.git
    \[ centosdip-172-31-22-44 /tmp/shellscripts \]$ \[

[^17]: 54 . 90 . 243.2 \| 172. 31.22. 44 \| t3. small \| https: //github. com/chilops/shellscripts.git
    \[ centos@ip-172-31-22-44 /tmp/shellscripts \]$ sh 14. without-exit-status. sh
    total 56
    -rw-rw-r--
    1 centos centos 523 Apr 18 06:03 09. install-mysql. sh
    -rw-rw-r--
    1 centos centos 163 Apr 18 06:03 08. conditions. sh
    -rw-rw-r--
    1 centos centos 183 Apr 18 06:03 07.arrays. sh
    rw-rw-r--
    1 centos centos 182 Apr 18 06:03 06. datatypes. sh
    -rw-rw-r--
    1 centos centos 325 Apr 18 06:03 05. variables. sh
    -rw-rw-r--
    1 centos centos 225 Apr 18 06:03 04. variablesArgs. sh
    -rw-rw-r--
    1 centos centos 57 Apr 18 06:03 03. variables.sh
    -rw-rw-r--
    1 centos centos 228 Apr 18 06:03 02. variables.sh
    rw-rw-r--
    1 centos centos 63 Apr 18 06:03 01.hello-world.sh
    rw-rw-r--
    1 centos centos 137 Apr 18 06:03 14. without-exit-status. sh
    -rw-rw-r--
    1 centos centos 994 Apr 18 06:03 13. install-packages. sh
    -rw-rw-r--
    1 centos centos 51 Apr 18 06:03 12. loops. sh
    -rw-rw-r--
    1 centos centos 690 Apr 18 06:03 11. logs.sh
    rw-rw-r-- 1 centos centos 562 Apr 18 06:03 10. functions.sh
    Before wrong command
    14. without-exit-status. sh: line 11: Isfff: command not found
    54 . 90.243.2 \| 172. 31.22. 44 \| t3. small \| https: //github.com/chilops/shellscripts.git

[^18]: Robosho-shellscripts > $ redis.sh
    1
    #! /bin/bash
    N
    3
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e\[33m"
    7
    N=" \\e\[Om"
    8
    9
    TIMESTAMP=$ (date +%F-%H-%M-%s)
    10
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    11
    exec &>$LOGFILE
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE ( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 ...
    $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 ... $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    34
    dnf install https ://rpms . remirepo. net/enterprise/remi-release-8 . rpm -y
    35
    36
    VALIDATE $? "Installing Remi release"
    37
    38
    anf module enable redis : remi-6.2 -y
    39
    40
    VALIDATE $? "enabling redis"
    41
    42
    anf install redis -y
    43
    44
    VALIDATE $? "Installing Redis"

[^19]: Robosho-shellscripts > $ redis.sh
    1
    #! /bin/bash
    N
    3
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e\[33m"
    7
    N=" \\e\[Om"
    8
    9
    TIMESTAMP=$ (date +%F-%H-%M-%s)
    10
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    11
    exec &>$LOGFILE
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE ( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 ...
    $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 ... $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    34
    dnf install https ://rpms . remirepo. net/enterprise/remi-release-8 . rpm -y
    35
    36
    VALIDATE $? "Installing Remi release"
    37
    38
    anf module enable redis : remi-6.2 -y
    39
    40
    VALIDATE $? "enabling redis"
    41
    42
    anf install redis -y
    43
    44
    VALIDATE $? "Installing Redis"

[^20]: PS E: \\AWSDevops\\Repos> cd . \\Robosho-shellscripts\\
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git status
    On branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    redis . sh

[^21]: PS E: \\AWSDevops \\Repos\\Robosho-shellscripts> git status
    On branch main
    nothing to commit, working tree clean
    PS E: \\AWSDevOps\\Repos \\Robosho-shellscripts>

[^22]: SuperPUTTY - Redis
    File View Tools Help
    Protocol SSH
    Host 54.87.38.124
    Login
    Password
    Session
    chilops
    Commands
    MongoDB
    Catalogue
    user
    Redis
    54 . 87 . 38.124 \| 172. 31. 22.104 \| t2.micro \| null
    \[ centos@ip-172-31-22-104 \~ \]$ clear

[^23]: \[ centos@ip-172-31-22-104 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts' . . .
    remote: Enumeratiog objects: 33, done.
    remote: Counting objects: 100% (33/33), done.
    remote: Compressing objects: 100% (26/26), done.
    remote: Total 33 (delta 14), reused 25 (delta 6), pack-reused 0
    Receiving objects: 100% (33/33), 4.83 KiB \| 4.83 MiB/s, done.
    Resolving deltas: 100% (14/14), done.
    54. 87. 38. 124 \| 172.31.22.104 \| t2.micro \| null
    \[ centos@ip-172-31-22-104 \~ \]$ 1s
    Roboshop-shellscripts
    54 . 87. 38. 124 \| 172. 31. 22.104 \| t2.micro \| null
    \[ centosdip-172-31-22-104 \~ \]$ cd Roboshop-shellscripts/
    54 . 87. 38.124 \| 172. 31. 22.104 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-22-104 \~/Roboshop-shellscripts \]$ 1s -1
    total 28
    -rw-rw-r--
    1 centos centos 265 Apr 18 06:39 catalogue . service
    -rw-rw-r--
    1 centos centos 2165 Apr 18 06:39 catalogue. sh
    -rw-rw-r--
    1 centos centos 1043 Apr 18 06:39 Mongodb. sh
    -rw-rw-r--
    1 centos centos 143 Apr 18 06:39 mongo . repo
    -rw-rw-r--
    1 centos centos 1014 Apr 18 06:39 redis. sh
    -rw-rw-r--
    1 centos centos 300 Apr 18 06:39 user. service
    -rw-rw-r--
    1 centos centos 2002 Apr 18 06:39 user.sh

[^24]: LOGFILE="/tmp/$0-$TIMESTAMP . log"
    exec . &> $LOGFILE

[^25]: centos@ip-172-31-22-104 \~/Roboshop-shellscripts \]$ sudo sh redis. sh
    64 . 87 . 38.124 \| 172. 31.22.104 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git

[^26]: centos@ip-172-31-22-104 \~ \]$ tail -f /tmp/redis. sh-2024-04-18-06-44-43. log
    Installed:
    redis-6. 2. 14-1. e18 . remi . x86 64
    Complete!
    Installing Redis ..
    SUCCESS
    allowing remote connections . . .
    SUCCESS
    Created symlink /etc/systemd/system/multi-user . target . wants/redis. service - /usr/lib/systemd/system/redis. service.
    Enabled Redis ..
    SUCCESS
    Started Redis
    SUCCESS

[^27]: \[ centosdip-172-31-22-104 \~ \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Rec-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp
    0
    0 0. 0. 0. 0: 6379
    0.0.0.0:\*
    LISTEN
    tcp
    0
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : :22
    LISTEN
    tcp6
    0 : :1:6379
    LISTEN
    tcp6
    0 : : :111
    LISTEN
    54 . 87. 38. 124 \| 172. 31. 22. 104 \| t2.micro \| null
    \[ centos@ip-172-31-22-104 \~ \]$\]

[^28]: \[ centosdip-172-31-22-104 \~ \]$ sudo systemctl restart redis
    54. 87. 38.124 \| 172. 31.22.104 \| t2.micro \| null
    \[ centos@ip-172-31-22-104 \~ \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    cp
    O
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    Ecp
    0
    0 0. 0. 0. 0:6379
    0.0.0.0:\*
    LISTEN
    tcp
    O
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    cp6
    0
    0 :::22
    : : :\*
    LISTEN
    Ecp6
    0 : : 1: 6379
    LISTEN
    OO
    cp6
    0 : : :111
    LISTEN
    54. 87. 38. 124 \| 172. 31.22. 104 \| t2.micro \| null
    \[ centos@ip-172-31-22-104 \~ \]$ sudo systemctl status redis
    redis . service - Redis persistent key-value database
    Loaded: loaded (/usr/lib/systemd/system/redis . service; enabled; vendor preset: disabled)
    Drop-In: /etc/systemd/system/redis . service.d
    Llimit . conf
    Active: active (running) since Thu 2024-04-18 07:02:20 UTC; 47s ago
    Process: 16734 ExecStop=/usr/libexec/redis-shutdown (code=exited, status=0/SUCCESS)
    Main PID: 16748 (redis-server)

[^29]: Robosho-shellscripts > $ user.sh
    #! /bin/bash
    W
    ID=$(id -u)
    14
    R=" \\e\[31m"
    G=" \\e \[32m"
    Y=" \\e\[33m"
    N=" \\e\[Om"
    MONGDB_HOST=mongodb . chowdarychilukuri . in
    9
    10
    TIMESTAMP=$ (date +%F-%H: %M: %s)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 . .. $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo
    -e "$2 . . . $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    dnf module disable nodejs -y &> > $LOGFILE
    34
    35
    VALIDATE $? "Disabling current NodeJS"
    36
    37
    dnf module enable nodejs : 18 -y &> > $LOGFILE
    38
    39
    VALIDATE $? "Enabling NodeJS:18"
    40
    41
    dnf install nodejs -y &> > $LOGFILE
    42
    43
    VALIDATE $? "Installing NodeJS: 18"

[^30]: 44
    45
    id roboshop #if roboshop user
    does not exist, then it is failure
    46
    if \[ $? -ne 0 \]
    47
    then
    48
    useradd roboshop
    49
    VALIDATE $? "roboshop user creation"
    150
    else
    51
    echo -e "roboshop user already exist $Y SKIPPING $N"
    52
    fi
    53
    54
    mkdir -p /app
    55
    56
    VALIDATE $? "creating app directory"
    57
    58
    curl -o /tmp/user. zip https:// roboshop-builds . s3. amazonaws . com/user . zip &> > $LOGFILE
    59
    60
    VALIDATE $? "Downloading user application"
    61
    62
    cd / app
    63
    64
    unzip -o /tmp/user . zip &>> $LOGFILE
    65
    66
    VALIDATE $? "unzipping user"
    67
    68
    npm install &> > $LOGFILE
    69
    70
    VALIDATE $? "Installing dependencies"
    71
    72
    cp /home/ centos/ roboshop-shell/user. service /etc/systemd/system/user. service
    73
    74
    VALIDATE $? "Copying user service file"
    75
    76
    systemctl daemon-reload &> > $LOGFILE
    77
    78
    VALIDATE $? "user daemon reload"
    79
    80
    systemctl enable user &>> $LOGFILE
    81
    82
    VALIDATE $? "Enable user"
    83
    84
    systemctl start user &>> $LOGFILE
    85
    86
    VALIDATE $? "Starting user"

[^31]: 44
    45
    id roboshop #if roboshop user
    does not exist, then it is failure
    46
    if \[ $? -ne 0 \]
    47
    then
    48
    useradd roboshop
    49
    VALIDATE $? "roboshop user creation"
    150
    else
    51
    echo -e "roboshop user already exist $Y SKIPPING $N"
    52
    fi
    53
    54
    mkdir -p /app
    55
    56
    VALIDATE $? "creating app directory"
    57
    58
    curl -o /tmp/user. zip https:// roboshop-builds . s3. amazonaws . com/user . zip &> > $LOGFILE
    59
    60
    VALIDATE $? "Downloading user application"
    61
    62
    cd / app
    63
    64
    unzip -o /tmp/user . zip &>> $LOGFILE
    65
    66
    VALIDATE $? "unzipping user"
    67
    68
    npm install &> > $LOGFILE
    69
    70
    VALIDATE $? "Installing dependencies"
    71
    72
    cp /home/ centos/ roboshop-shell/user. service /etc/systemd/system/user. service
    73
    74
    VALIDATE $? "Copying user service file"
    75
    76
    systemctl daemon-reload &> > $LOGFILE
    77
    78
    VALIDATE $? "user daemon reload"
    79
    80
    systemctl enable user &>> $LOGFILE
    81
    82
    VALIDATE $? "Enable user"
    83
    84
    systemctl start user &>> $LOGFILE
    85
    86
    VALIDATE $? "Starting user"

[^32]: 87
    88
    cp /home/centos/roboshop-shell/mongo . repo /etc/yum. repos . d/mongo . repo
    89
    90
    VALIDATE $? "copying mongodb repo"
    91
    92
    dnf install mongodb-org-shell -y &>> $LOGFILE
    93
    94
    VALIDATE $? "Installing MongoDB client"
    95
    96
    mongo --host $MONGDB_HOST </app/schema/user . js &>> $LOGFILE
    97
    98
    VALIDATE $? "Loading user data into MongoDB"

[^33]: EXPLORER
    $ 12.loops.sh
    $ 11.logs.sh
    13.install-packages.sh
    $ mongodb.sh
    mongo.repo
    $
    cata
    REPOS
    Robosho-shellscripts > = user.service
    Robosho-shellscripts
    1
    \[Unit\]
    catalogue.service
    N
    Description = User Service
    3
    $ catalogue.sh
    \[Service\]
    4
    User=roboshop
    amongo.repo
    15
    Environment=MONGO=true
    $ mongodb.sh
    6
    Environment=REDIS_HOST=redis . chowdarychilukuri . in
    user.service
    U
    7
    Environment=MONGO_URL="mongodb : / /mongodb . chowdarychilukuri . in : 27017/users"
    $ user.sh
    U
    8
    ExecStart=/bin/node /app/server . js
    > shellscripts
    9
    SyslogIdentifier=user
    10
    11
    \[Install \]
    12
    WantedBy=multi-user . target

[^34]: PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git status
    On branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    redis . sh
    user . service
    user . sh

[^35]: PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git status
    On branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    redis . sh
    user . service
    user . sh

[^36]: SuperPUTTY - user
    File View Tools Help
    Protocol SSH
    Host 3.80.117.170
    Login
    Password
    Session chilops
    - O X
    Commands
    MongoDB Catalogue
    user
    3. 80 .117.170 \| 172. 31.21. 157 \| t2.micro \| null
    \[ centos@ip-172-31-21-157 \~ \]$ \]

[^37]: \[ centosdip-172-31-21-157 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts' ...
    remote: Enumeratiog objects: 36, done.
    remote: Counting objects: 100% (36/36), done.
    remote: Compressing objects: 100% (27/27), done.
    remote: Total 36 (delta 16), reused 28 (delta 8), pack-reused 0
    Receiving objects: 100% (36/36), 5.07 KiB \| 5.07 MiB/s, done.
    Resolving deltas: 100% (16/16), done.
    . 80. 117. 170 \| 172. 31. 21. 157 \| t2.micro \| null
    centos@ip-172-31-21-157 \~ \]$ 1s
    Roboshop-shellscripts
    80. 117. 170 \| 172. 31.21. 157 \| t2.micro \| null
    centosdip-172-31-21-157 \~ \]$ cd Roboshop-shellscripts/
    80. 117. 170 \| 172. 31. 21. 157 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts.git
    centosdip-172-31-21-157 \~/Roboshop-shellscripts \]$ 1s
    catalogue. service catalogue. sh Mongodb. sh mongo. repo redis.sh user. service user. sh
    3. 80. 117. 170 \| 172. 31. 21. 157 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git

[^38]: \[ centos@ip-172-31-21-157 \~/Roboshop-shellscripts \]$ sudo sh user. sh
    You are root user
    Disabling current NodeJS
    SUCCESS
    Enabling NodeJS : 18
    . . .
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    uid=1001 (roboshop) gid=1001 (roboshop) groups=1001 (roboshop)
    roboshop user already exist SKIPPING
    creating app directory .
    SUCCESS
    Downloading user application
    SUCCESS
    unzipping user . . .
    SUCCESS
    Installing dependencies . .
    SUCCESS
    Copying user service file ..
    SUCCESS
    user daemon reload ... SUCCESS
    Enable user . . .
    SUCCESS
    Starting user . .
    SUCCESS
    copying mongodb repo
    SUCCESS
    Installing MongoDB client . . .
    SUCCESS
    Loading user data into MongoDB
    . . .
    SUCCESS
    3. 80 . 117. 170 \| 172. 31. 21. 157 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-21-157 \~/Roboshop-shellscripts \]$ 0

[^39]: centos@ip-172-31-21-157 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep
    -i redis
    Apr 18 07:16:36 ip-172-31-21-157 user \[17383\]: {"level": "info", "time" : 1713424596265, "pid" : 17383, "hostname": "ip-172-31-21-157
    ec2 . internal",
    "msg": "Redis
    READY
    undefined"
    "v" :1}

[^40]: \[ centosdip-172-31-21-157 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep -i mongodb
    Apr 18 07:16:36 ip-172-31-21-157 user \[17383\]: (node: 17383) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monitorin
    g engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine, pass
    option { useUnifiedTopology: true } to the MongoClient constructor.
    Apr 18 07:16:36 ip-172-31-21-157 user \[17383\]: {"level": "info", "time" : 1713424596281, "pid" : 17383, "hostname" : "ip-172-31-21-157
    ec2 . internal", "msg": "MongoDB connected", "v" :1}
    3. 80. 117. 170 \| 172. 31. 21. 157 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-21-157 \~/Roboshop-shellscripts \]$ !

[^41]: 44
    45
    id roboshop #if roboshop user does not exist, then it is failure
    46
    if \[ $? -ne 0 \]
    47
    then
    48
    useradd roboshop
    49
    VALIDATE $? "roboshop user creation"
    50
    else
    51
    echo -e "roboshop user already exist $Y SKIPPING $N"
    52
    fi
    53
    54
    mkdir -p /app
    55
    56
    VALIDATE $? "creating app directory"
    57
    58
    curl -o /tmp/cart. zip https://roboshop-builds . s3 . amazonaws . com/cart . zip &> > $LOGFILE
    59
    60
    VALIDATE $? "Downloading cart application"
    61
    62
    cd / app
    63
    64
    unzip -o /tmp/cart. zip &>> $LOGFILE
    65
    66
    VALIDATE $? "unzipping cart"
    67
    68
    npm install &>> $LOGFILE
    69
    70
    VALIDATE $? "Installing dependencies"
    71
    72
    # use absolute, because cart. service exists there
    73
    cp / home/centos/roboshop-shell/cart. service /etc/systemd/system/cart. service &>> $LOGFILE
    74
    75
    VALIDATE $? "Copying cart service file"
    76
    77
    systemctl daemon-reload &> > $LOGFILE
    78
    79
    VALIDATE $? "cart daemon reload"
    80
    81
    systemctl enable cart &>> $LOGFILE
    82
    83
    VALIDATE $? "Enable cart"
    84
    85
    systemctl start cart &>> $LOGFILE

[^42]: Robosho-shellscripts > $ cart.sh
    #! /bin/bash
    W
    ID=$(id -u)
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e\[33m"
    N=" \\e\[Om"
    8
    9
    10
    TIMESTAMP=$ (date +%F-%H: %M: %S)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE() {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 .
    . . . $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 ... $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    dnf module disable nodejs -y &>> $LOGFILE
    34
    35
    VALIDATE $? "Disabling current NodeJS"
    36
    37
    dnf module enable nodejs: 18 -y &>> $LOGFILE
    38
    39
    VALIDATE $? "Enabling NodeJS:18"
    40
    41
    anf install nodejs -y &> > $LOGFILE
    42
    43
    VALIDATE $? "Installing NodeJS: 18"

[^43]: 44
    45
    id roboshop #if roboshop user does not exist, then it is failure
    46
    if \[ $? -ne 0 \]
    47
    then
    48
    useradd roboshop
    49
    VALIDATE $? "roboshop user creation"
    50
    else
    51
    echo -e "roboshop user already exist $Y SKIPPING $N"
    52
    fi
    53
    54
    mkdir -p /app
    55
    56
    VALIDATE $? "creating app directory"
    57
    58
    curl -o /tmp/cart. zip https://roboshop-builds . $3. amazonaws . com/cart. zip &> > $LOGFILE
    59
    60
    VALIDATE $? "Downloading cart application"
    61
    62
    cd / app
    63
    64
    unzip -o /tmp/cart. zip &>> $LOGFILE
    65
    66
    VALIDATE $? "unzipping cart"
    67
    68
    npm install &>> $LOGFILE
    69
    70
    VALIDATE $? "Installing dependencies"
    71
    72
    # use absolute, because cart . service exists there
    73
    cp /home/ centos/Roboshop-shellscripts/cart. service /etc/systemd/system/cart. service &>> $LOGFILE
    74
    75
    VALIDATE $? "Copying cart service file"
    76
    77
    systemctl daemon-reload &> > $LOGFILE
    78
    79
    VALIDATE $? "cart daemon reload"
    80
    81
    systemctl enable cart &> > $LOGFILE
    82
    83
    VALIDATE $? "Enable cart"
    84
    85
    systemctl start cart &> > $LOGFILE
    86
    87
    VALIDATE $? "Starting cart"

[^44]: REPOS
    Robosho-shellscripts > cart.service
    Robosho-shellscripts
    1
    \[Unit\]
    E cart.service
    U
    2
    Description = Cart Service
    3
    $ cart.sh
    \[Service\]
    14
    User=roboshop
    catalogue.service
    5
    Environment=REDIS_HOST=redis . chowdarychilukuri . in
    $ catalogue.sh
    6
    Environment=CATALOGUE_HOST=catalogue . chowdarychilukuri . in
    amongo.repo
    7
    Environment=CATALOGUE_PORT=8080
    $ mongodb.sh
    8
    ExecStart=/bin/node /app/server . js
    $ redis.sh
    19
    SyslogIdentifier=cart
    user.service
    10
    11
    \[Install \]
    $ user.sh
    12
    WantedBy=multi-user . target
    > shellscripts

[^45]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    cart . service
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest cart modifications"; git push origin main
    \[main dbdbe4e\] added latest cart modifications

[^46]: SuperPUTTY - Cart
    File View Tools Help
    Protocol SSH
    Host 54.162.212.131
    Login
    Password
    Session
    chilops
    - O X
    Commands
    MongoDB Catalogue
    user
    Redis
    Cart
    54 . 162 . 212.131 \| 172. 31.23.237 \| t2.micro \| null
    \[ centos@ip-172-31-23-237 \~ \]$

[^47]: MongoDB
    Catalogue
    user
    Redis
    Cart
    54 . 162. 212. 131 \| 172. 31.23.237 \| t2.micro \| null
    \[ centosdip-172-31-23-237 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' .. .
    remote: Enumeratiog objects: 45, done.
    remote: Counting objects: 100% (45/45), done.
    remote: Compressing objects: 100% (33/33), done.
    remote: Total 45 (delta 24), reused 32 (delta 11) , pack-reused 0
    Receiving objects: 100% (45/45), 5.80 KiB \| 5.80 MiB/s, done.
    Resolving deltas: 100% (24/24), done.
    54 . 162. 212. 131 \| 172. 31.23.237 \| t2.micro \| null
    \[ centosdip-172-31-23-237 \~ \]$ 1s
    Roboshop-shellscripts
    54 . 162. 212. 131 \| 172. 31.23.237 \| t2.micro \| null
    \[ centos@ip-172-31-23-237 \~ \]$ cd Roboshop-shellscripts/
    54 . 162 . 212. 131 \| 172.31.23.237 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-23-237 \~/Roboshop-shellscripts \]$ 1s
    cart. service cart.sh catalogue. service catalogue. sh Mongodb. sh mongo . repo redis.sh user. service user. sh
    54 . 162. 212.131 \| 172.31.23.237 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    centos@ip-172-31-23-237 \~/Roboshop-shellscripts \]$ \[

[^48]: \[ centosdip-172-31-23-237 \~/Roboshop-shellscripts \]$ sudo sh cart. sh
    You are root user
    Disabling current NodeJS
    SUCCESS
    Enabling NodeJS : 18
    . .
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading cart application
    . .
    SUCCESS
    unzipping cart . .
    SUCCESS
    Installing dependencies
    SUCCESS

[^49]: \[ centosdip-172-31-23-237 \~/Roboshop-shellscripts \]$ sudo sh cart. sh
    You are root user
    Disabling current NodeJS
    SUCCESS
    Enabling NodeJS : 18
    . .
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading cart application
    . .
    SUCCESS
    unzipping cart . .
    SUCCESS
    Installing dependencies
    SUCCESS

[^50]: \[ centosdip-172-31-23-237 \~/Roboshop-shellscripts \]$ sudo sh cart. sh
    You are root user
    Disabling current NodeJS
    SUCCESS
    Enabling NodeJS : 18
    . .
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading cart application
    . .
    SUCCESS
    unzipping cart . .
    SUCCESS
    Installing dependencies
    SUCCESS

[^51]: \[ centosdip-172-31-23-237 \~/Roboshop-shellscripts \]$ sudo sh cart. sh
    You are root user
    Disabling current NodeJS
    SUCCESS
    Enabling NodeJS : 18
    . .
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading cart application
    . .
    SUCCESS
    unzipping cart . .
    SUCCESS
    Installing dependencies
    SUCCESS

[^52]: Copying cart service file
    .
    SUCCESS
    cart daemon reload . . .
    SUCCESS
    Enable cart .
    SUCCESS
    Starting cart ...
    SUCCESS
    54 . 162. 212. 131 \| 172. 31.23.237 \| t2.micro \| https: //github.com/chil
    \[ centos@ip-172-31-23-237 \~/Roboshop-shellscripts \]$ \| \|

[^53]: \[ centosdip-172-31-23-237 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep -i cart
    Apr 18 07:37:27 ip-172-31-23-237 systemd \[1\] : Started Cart Service.
    Apr 18 07:37:28 ip-172-31-23-237 cart \[17264\]: {"level": "info", "time" : 1713425848859, "pid" : 17264, "hostname" : "ip-172-31-23-237
    ec2. internal", "msg": "Started on port 8080", "v":1}
    Apr 18 07:37:28 ip-172-31-23-237 cart \[17264\]: {"level": "info", "time" : 1713425848896, "pid" : 17264, "hostname" : "ip-172-31-23-237
    . ec2 . internal", "msg": "Redis READY undefined", "v":1}

[^54]: \[ centos@ip-172-31-23-237 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    O
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0
    0 0. 0. 0. 0:22
    0. 0.0.0:\*
    LISTEN
    tcp6
    0 :::111
    LISTEN
    tcp6
    0
    8080
    LISTEN
    tcp6
    0
    : : : 22
    LISTEN

[^55]: Robosho-shellscripts > $ web.sh
    1
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e \[33m"
    7
    N=" \\e \[Om"
    MONGDB_HOST=mongodb . daws76s . online
    9
    10
    TIMESTAMP=$ (date +%F-%H: %M: %S)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 ... $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo
    -e "$2 . . . $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    def install nginx -y &> > $LOGFILE
    34
    35
    VALIDATE $? "Installing nginx"
    36
    37
    systemctl enable nginx &>> $LOGFILE
    38
    39
    VALIDATE $? "Enable nginx"
    40
    41
    systemctl start nginx &>> $LOGFILE
    42
    43
    VALIDATE $? "Starting Nginx"

[^56]: 44
    45
    rm -rf /usr/share/nginx/html/\* &>> $LOGFILE
    46
    47
    VALIDATE $? "removed default website"
    48
    49
    curl -o /tmp/web. zip https: //roboshop-builds . s3. amazonaws . com/web . zip &> > $LOGFILE
    50
    51
    VALIDATE $? "Downloaded web application"
    52
    53
    cd /usr/share/nginx/html &>> $LOGFILE
    54
    55
    VALIDATE $? "moving to nginx html directory"
    56
    57
    unzip -o /tmp/web . zip &>> $LOGFILE
    58
    59
    VALIDATE $? "unzipping web"
    60
    61
    cp /home/centos//Roboshop-shellscripts/roboshop . conf /etc/nginx/default.d/roboshop. conf &> > $LOGFILE
    62
    63
    VALIDATE $? "copied roboshop reverse proxy config"
    64
    65
    systemctl restart nginx &> > $LOGFILE
    66
    67
    VALIDATE $? "restarted nginx"

[^57]: EXPLORER
    . . .
    mongodb.sh
    mongo.repo
    $ catalogue.sh
    $ user.sh
    $ redis.sh
    $ cart.sh
    cart.service
    REPOS
    Robosho-shellscripts > roboshop.conf
    Robosho-shellscripts
    1
    proxy_http_version 1.1;
    E cart.service
    N
    location /images/ {
    3
    $ cart.sh
    expires 5s;
    4
    catalogue.service
    root /usr/share/nginx/html;
    5
    try_files $uri /images/placeholder . jpg;
    $ catalogue.sh
    6
    }
    mongo.repo
    7
    location /api/catalogue/ { proxy_pass http: //catalogue . chowdarychilukuri . in: 8080/;
    $ mongodb.sh
    8
    location /api/user/ { proxy_pass http://user . chowdarychilukuri . in: 8080/; }
    $ redis.sh
    19
    location /api/cart/ { proxy_pass http://cart. chowdarychilukuri . in : 8080/;
    roboshop.conf
    U
    10
    location /api/shipping/ { proxy_pass http://localhost: 8080/; }
    11
    user.service
    location /api/payment/ { proxy_pass http: //localhost : 8080/; }
    12
    $ user.sh
    13
    location /health {
    $ web.sh
    U
    14
    stub_status on;
    > shellscripts
    15
    access_log off;
    16

[^58]: (use "git add <file>.
    ..." to include in what will be committed)
    roboshop . conf
    web . sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest web modifications"; git push origin main
    warning: in the working copy of 'web. sh', LF will be replaced by CRLF the next time Git touches it

[^59]: SuperPUTTY - Web
    File View Tools Help
    Protocol SSH
    Host 54.152.150.169
    Login
    Password
    Session
    chilops
    O X
    Commands
    MongoDB
    Catalogue
    user
    Redis
    Cart
    Web
    54 . 152 . 150. 169 \| 172. 31. 16.157 \| t2.micro \| null
    \[ centos@ip-172-31-16-157 \~ \]$ \[

[^60]: \[ centos@ip-172-31-16-157 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' ...
    remote: Enumeratiog objects: 52, done.
    remote: Counting objects: 100% (52/52), done.
    remote: Compressing objects: 100% (39/39), done.
    remote: Total 52 (delta 28), reused 36 (delta 12), pack-reused 0
    Receiving objects: 100% (52/52), 6.99 KiB \| 6.99 MiB/s, done.
    Resolving deltas: 100% (28/28), done.
    54 . 152. 150.169 \| 172. 31. 16. 157 \| t2.micro \| null
    \[ centosdip-172-31-16-157 \~ \]$ 1s
    Roboshop-shellscripts
    54 . 152 . 150.169 \| 172. 31. 16.157 \| t2.micro \| null
    \[ centos@ip-172-31-16-157 \~ \]$ cd Roboshop-shellscripts/
    54 . 152 . 150.169 \| 172. 31.16.157 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ 1s
    cart . service catalogue . service Mongodb. sh redis. sh
    user . service web. sh
    cart . sh
    catalogue . sh
    mongo . repo roboshop . conf
    user . sh

[^61]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0. 0.0.0:111
    0.0.0.0:\*
    LISTEN
    cp
    0 0.0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : :111
    : : :\*
    LISTEN
    cp6
    0 : : :22
    LISTEN

[^62]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ sudo sh web. sh
    You are root user
    Installing nginx
    SUCCESS
    Enable nginx
    SUCCESS
    Starting Nginx . .
    SUCCESS
    removed default website . ..
    SUCCESS
    Downloaded web application . . .
    SUCCESS
    moving to nginx html directory
    . . .
    SUCCESS
    unzipping web
    SUCCESS
    copied roboshop reverse proxy config . . .
    SUCCESS
    restarted nginx ...
    SUCCESS

[^63]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0. 0. 0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0. 0.0. 0:80
    0.0.0.0:\*
    LISTEN
    tcp
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    oooOOO
    tcp6
    0 :::111
    LISTEN
    tcp6
    0 :::80
    LISTEN
    tcp6
    0 : : :22
    LISTEN

[^64]: centosdip-172-31-16-15/ \~/Roboshop-shellscripts \]s sudo systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2024-04-18 07:57:12 UTC; 7min ago
    Process: 6726 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 6723 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 6721 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0/SUCCESS)

[^65]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep -i nginx
    Apr 18 07:57:09 ip-172-31-16-157 systemd \[1\]: nginx. service: Unit cannot be reloaded because it is inactive.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\]: Starting The nginx HTTP and reverse proxy server . ..
    Apr 18 07:57:11 ip-172-31-16-157 nginx \[6459\]: nginx: the configuration file /etc/nginx/nginx. conf syntax is ok
    Apr 18 07:57:11 ip-172-31-16-157 nginx \[6459\]: nginx: configuration file /etc/nginx/nginx. conf test is successful
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\]: nginx. service: Failed to parse PID from file /run/nginx.pid: Invalid argument
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\]: Started The nginx HTTP and reverse proxy server.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : Stopping The nginx HTTP and reverse proxy server. . .
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : nginx. service: Succeeded.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : Stopped The nginx HTTP and reverse proxy server.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : Starting The nginx HTTP and reverse proxy server. ..
    Apr 18 07:57:12 ip-172-31-16-157 nginx \[6723\]: nginx: the configuration file /etc/nginx/nginx. conf syntax is ok
    Apr 18 07:57:12 ip-172-31-16-157 nginx \[6723\]: nginx: configuration file /etc/nginx/nginx. conf test is successful
    Apr 18 07:57:12 ip-172-31-16-157 systemd \[1\] : nginx. service: Failed to parse PID from file /run/nginx. pid: Invalid argument
    Apr 18 07:57:12 ip-172-31-16-157 systemd \[1\] : Started The nginx HTTP and reverse proxy server.
    54 . 152 . 150.169 \| 172. 31 . 16.157
    t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git

[^66]: G
    Not secure \| chowdarychilukuri.in/product/STAN-1
    Al
    Stan's Robot Shop
    Search
    Login / Register
    Cart
    Stan
    STAN
    Empty
    Categories
    . Artificial
    Intelligence
    o HAL
    . Positronic
    Brain
    o Stan
    . Robot
    STAND
    . C3PO
    o Eve
    o K9
    o Kryten
    . Marvin
    . Mr Data
    . R2D2
    o Robbie
    o Stan
    Rating No votes yet. Vote now.
    APM guru
    Price E67.00 Quantity 1
    Add to cart

[^67]: Application and OS Images (Amazon Machine Image) Info
    Summary
    An AMI is a template that contains the software configuration (operating system, application server, and
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Number of instances Info
    below
    2
    Q devops-practice
    X
    When launching more than 1 instance, consider EC2 Auto
    Scaling
    AMI from catalog
    Recents
    Quick Start
    Software Image (AMI)
    Centos-8-DevOps-Practice
    ami-Of3c7d07486cad139
    Amazon Machine Image (AMI)
    Q
    Centos-8-DevOps-Practice
    Virtual server type (instance type)
    ami-Of3c7d07486cad139
    Browse more AMIs
    3.small
    Including AMIs from
    AWS, Marketplace and
    Firewall (security group)
    the Community
    Catalog
    Published
    Architecture
    Virtualization
    Root device type ENA Enabled
    SG_Allow_All
    Community
    2024-01-
    x86_64
    hvm
    ebs
    Yes
    Storage (volumes)
    AMIs
    16T13:22:50.00
    1 volume(s) - 10 GiB
    OZ
    Free tier: In your first year includes
    X
    750 hours of t2.micro (or t3.micro in
    the Regions in which t2.micro is
    unavailable) instance usage on free
    Instance type Info \| Get advice
    tier AMIs per month, 750 hours of
    public IPv4 address usage per
    month, 30 GiB of EBS storage, 2
    Instance type
    million 10s, 1 GB of snapshots, and
    t3.small
    100 GB of bandwidth to the
    Family: t3 2 VCPU 2 GiB Memory Current generation: true
    All generations
    internet.
    On-Demand SUSE base pricing: 0.0518 USD per Hour
    On-Demand Linux base pricing: 0.0208 USD per Hour
    On-Demand RHEL base pricing: 0.0808 USD per Hour
    Compare instance types
    On-Demand Windows base pricing: 0.0392 USD per Hour
    Additional costs apply for AMIs with pre-installed software
    Cancel
    Launch instance
    Review commands
    Key pair (login) Info
    You can use a key pair to securely connect to your instance. Ensure that you have access to the selected key pair
    before you launch the instance
    Key pair name - required
    KeysC
    Create new key pair
    Network settings Info
    Edit

[^68]: mysql
    i-0a2f245ef904f0646
    Running
    t3.small
    V
    shipping
    i-01df4a2b34501203e
    Running
    t3.small

[^69]: Route 53 > Hosted zones > chowdarychilukuri.in > Create record
    Create record Info
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
    Value Info
    172.31.24.78
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

[^70]: mysql.chowdarychilukuri.in
    A
    Simple
    No
    172.31.25.147
    redis.chowdarychilukuri.in
    A
    Simple
    No
    172.31.83.100
    O
    shipping.chowdarychilukuri.in
    A
    Simple
    No
    172.31.24.78
    1

[^71]: Robosho-shellscripts > $ mysql.sh
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e\[32m"
    6
    Y=" \\e\[33m"
    7
    N=" \\e\[Om"
    8
    MONGDB_HOST=mongodb . chowdarychilukuri . in
    9
    10
    TIMESTAMP=$ (date +%F-%H: %M: %s)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE ( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 .. . $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 ... $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    dnf module disable mysql -y &>> $LOGFILE
    34
    35
    VALIDATE $? "Disable current MySQL version"
    36
    37
    cp mysql . repo /etc/yum. repos . d/mysql . repo &> > $LOGFILE
    38
    39
    VALIDATE $? "Copied MySQ1 repo"
    40
    41
    dnf install mysql-community-server -y &>> $LOGFILE
    42
    43
    VALIDATE $? "Installing MySQL Server"

[^72]: 44
    45
    systemctl enable mysqld &>> $LOGFILE
    46
    47
    VALIDATE $? "Enabling MySQL Server"
    48
    49
    systemctl start mysqld &>> $LOGFILE
    50
    51
    VALIDATE $? "Starting MySQL Server"
    52
    53
    mysql_secure_installation --set-root-pass RoboShop@1 &> > $LOGFILE
    54
    55
    VALIDATE $? "Setting MySQL root password"

[^73]: EXPLORER
    . . .
    user.sh
    $ redis.sh
    X
    $ cart.sh
    cart.service
    $ web.sh
    $ mysql.sh U
    $ shippi
    REPOS
    Robosho-shellscripts > @ mysql.repo
    Robosho-shellscripts
    1
    \[mysql \]
    cart.service
    2
    name=MySQL 5.7 Community Server
    3
    $ cart.sh
    baseur1=http://repo. mysql . com/yum/mysql-5.7-community/e1/7/$basearch/
    4
    enabled=1
    catalogue.service
    5
    gpgcheck=0
    $ catalogue.sh
    amongo.repo
    $ mongodb.sh
    mysql.repo
    U
    $ mysql.sh
    U

[^74]: PS E: \\AWSDevops\\Repos> cd . \\Robosho-shellscripts\\
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git status
    On branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    mysql . repo
    mysql . sh

[^75]: mysql . repo
    mysql . sh
    shipping. service
    shipping. sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest web modifications"; git push origin main

[^76]: 54 . 90 . 200.232 \| 172. 31 . 25. 147 \| t3. small \| null
    \[ centosdip-172-31-25-147 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' .. .
    remote: Enumeratiog objects: 52, done.
    remote: Counting objects: 100% (52/52), done.
    remote: Compressing objects: 100% (39/39), done.
    remote: Total 52 (delta 28), reused 36 (delta 12), pack-reused 0
    Receiving objects: 100% (52/52), 6.99 KiB \| 2.33 MiB/s, done.
    Resolving deltas: 100% (28/28), done.
    54 . 90 . 200.232 \| 172. 31. 25. 147 \| t3. small \| null
    \[ centos@ip-172-31-25-147 \~ \]$ cd Roboshop-shellscripts/

[^77]: \[ centosdip-172-31-25-147 \~/Roboshop-shellscripts \]$ 1s
    cart . service
    catalogue . service
    Mongodb . sh
    mysql . repo
    redis. sh
    shipping . service
    user . service
    web . sh
    cart . sh
    catalogue . sh
    mongo . repo
    mysql . sh
    roboshop . conf
    shipping . sh
    user . sh
    54 . 90. 200.232 \| 172. 31.25. 147 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    centosdip-172-31-25-147 \~/Roboshop-shellscripts \]$ sudo sh mysql . shl\]

[^78]: \[ centosdip-172-31-25-147 \~/Roboshop-shellscripts \]$ sudo sh mysql. sh
    You are root user
    Disable current MySQL version
    SUCCESS
    Copied MySQ1 repo . .
    SUCCESS
    Installing MySQL Server . .
    SUCCESS
    Enabling MySQL Server . . .
    SUCCESS
    Starting MySQL Server . .
    SUCCESS
    Setting MySQL root password
    .
    SUCCESS
    54 . 90. 200.232 \| 172. 31. 25. 147 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts. git
    centos@ip-172-31-25-147 \~/Roboshop-shellscripts \]$ \|

[^79]: \[ centos@ip-172-31-25-147 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    O
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0
    0 0.0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    0 :: :3306
    LISTEN
    tcp6
    O
    : : :111
    LISTEN
    tcp6
    0
    : : : 22
    LISTEN

[^80]: Robosho-shellscripts > $ shipping.sh
    #! /bin/bash
    A WN
    ID=$(id -u)
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e \[33m"
    N=" \\e\[Om"
    8
    9
    TIMESTAMP=$ (date +%F-%H: %M: %s)
    10
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    11
    12
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    13
    14
    VALIDATE ( ) {
    15
    if \[ $1 -ne 0 \]
    16
    then
    17
    echo -e "$2
    . . . $R FAILED $N"
    18
    exit 1
    19
    else
    20
    echo -e "$2 .
    $G SUCCESS $N"
    21
    fi
    22
    23
    24
    if \[ $ID -ne 0 \]
    25
    then
    26
    echo -e "$R ERROR: : Please run this script with root access $N"
    27
    exit 1 # you can give other than 0
    28
    else
    29
    echo "You are root user"
    30
    fi # fi means reverse of if, indicating condition end
    31
    32
    dnf install maven -y &>> $LOGFILE
    33
    34
    id roboshop #if roboshop user does not exist, then it is failure
    35
    if \[ $? -ne 0 \]
    36
    then
    37
    useradd roboshop
    38
    VALIDATE $? "roboshop user creation"
    39
    else
    40
    echo -e "roboshop user already exist $Y SKIPPING $N"
    41
    fi
    42
    43
    mkdir -p / app

[^81]: 44
    45
    VALIDATE $? "creating app directory"
    46
    47
    curl -L -o /tmp/shipping. zip https://roboshop-builds . $3. amazonaws . com/shipping. zip &> > $LOGFILE
    48
    49
    VALIDATE $? "Downloading shipping"
    50
    51
    cd / app
    52
    53
    VALIDATE $? "moving to app directory"
    54
    55
    unzip -o /tmp/shipping . zip &>> $LOGFILE
    56
    57
    VALIDATE $? "unzipping shipping"
    58
    59
    mvn clean package &> > $LOGFILE
    60
    61
    VALIDATE $? "Installing dependencies"
    62
    63
    mv target/shipping-1.0. jar shipping . jar &> > $LOGFILE
    64
    65
    VALIDATE $? "renaming jar file"
    66
    67
    cp /home/ centos/Roboshop-shellscripts/shipping. service /etc/systemd/system/shipping. service &>> $LOGFILE
    68
    69
    VALIDATE $? "copying shipping service"
    70
    71
    systemctl daemon-reload &> > $LOGFILE
    72
    73
    VALIDATE $? "deamon reload"
    74
    75
    systemctl enable shipping &> > $LOGFILE
    76
    77
    VALIDATE $? "enable shipping"
    78
    79
    systemctl start shipping &>> $LOGFILE
    80
    81
    VALIDATE $? "start shipping"
    82
    83
    dnf install mysql -y &> > $LOGFILE
    84
    85
    VALIDATE $? "install MySQL client"
    86

[^82]: 87
    mysql -h mysql . chowdarychilukuri. in -uroot -pRoboShop@1 < /app/schema/shipping. sql &> > $LOGFILE
    88
    89
    VALIDATE $? "loading shipping data"
    90
    91
    systemctl restart shipping &> > $LOGFILE
    92
    93
    VALIDATE $? "restart shipping"

[^83]: EXPLORER
    . . .
    user.sh
    $ redis.sh
    $ cart.sh
    E cart.service
    $ web.sh
    $ mysql.sh
    REPOS
    Robosho-shellscripts > shipping.service
    Robosho-shellscripts
    H
    \[Unit \]
    cart.service
    2
    Description=Shipping Service
    3
    $ cart.sh
    4
    \[Service \]
    catalogue.service
    5
    User=roboshop
    $ catalogue.sh
    6
    Environment=CART_ENDPOINT=cart . chowdarychilukuri . in : 8080
    amongo.repo
    7
    Environment=DB_HOST=mysql . chowdarychilukuri . in
    $ mongodb.sh
    8
    ExecStart=/bin/java -jar /app/shipping . jar
    @mysql.repo
    SyslogIdentifier=shipping
    $ mysql.sh
    10
    11
    $ redis.sh
    \[Install \]
    12
    WantedBy=multi-user . target
    roboshop.conf
    shipping.service
    $ shipping.sh
    user.service
    $ user.sh
    $ web.sh
    > shellscripts

[^84]: mysql . repo
    mysql . sh
    shipping. service
    shipping. sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest web modifications"; git push origin main

[^85]: SuperPUTTY - shipping
    File View Tools Help
    Protocol SSH
    Host 54.89.126.246
    Login
    Password
    Session chilops
    Commands
    mongodb
    catalogue
    user
    redis
    cart
    web
    mysql shipping
    54 . 89. 126.246 \| 172. 31.24.78 \| t3. small \| null
    \[ centosdip-172-31-24-78 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' ...
    remote: Enumeratiog objects: 58, done.
    remote: Counting objects: 100% (58/58), done.
    remote: Compressing objects: 100% (44/44), done.
    remote: Total 58 (delta 31), reused 40 (delta 13), pack-reused 0
    Receiving objects: 100% (58/58), 8.30 KiB \| 2.77 MiB/s, done.
    Resolving deltas: 100% (31/31), done.
    54 . 89. 126.246 \| 172. 31.24.78 \| t3. small \| null
    \[ centosdip-172-31-24-78 \~ \]$ cd Roboshop-shellscripts/
    54. 89. 126.246 \| 172.31.24.78 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-24-78 \~/Roboshop-shellscripts \]$ 1s
    cart . service catalogue . service Mongodb.sh mysql . repo
    redis. sh
    shipping . service user . service web. sh
    cart . sh
    catalogue . sh
    mongo . repo mysql . sh
    roboshop . conf shipping . sh
    user . sh
    54. 89. 126.246 \| 172. 31.24.78 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-24-78 \~/Roboshop-shellscripts \]$

[^86]: \[ centos@ip-172-31-24-78 \~/Roboshop-shellscripts \]$ sudo sh shipping. sh
    You are root user
    id: 'roboshop' : no such user
    roboshop user creation
    .
    SUCCESS
    creating app directory . .
    SUCCESS
    Downloading shipping . . .
    SUCCESS
    moving to app directory .
    SUCCESS
    unzipping shipping . . .
    SUCCESS
    Installing dependencies
    SUCCESS
    renaming jar file ... SUCCESS
    copying shipping service
    ..
    SUCCESS
    deamon reload . . .
    SUCCESS
    enable shipping
    . . .
    SUCCESS
    start shipping.
    SUCCESS
    install MySQL client
    . . .
    SUCCESS
    loading shipping data
    .
    SUCCESS
    restart shipping . . .
    SUCCESS
    54 . 89. 126.246 \| 172. 31.24.78 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-24-78 \~/Roboshop-shellscripts 1$ \[

[^87]: centos@ip-172-31-24-78 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    cp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    cp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    cp6
    0 : : :111
    : : .\*
    LISTEN
    OOOO
    cp6
    0 : : : 8080
    LISTEN
    cp6
    0 : ::22
    LISTEN

[^88]: Q devops-practice
    X
    Summary
    AMI from catalog
    Recents
    Quick Start
    Number of instances Info
    Amazon Machine Image (AMI)
    Centos-8-DevOps-Practice
    Q
    2
    7d07486cad 139
    Browse more AMIs
    When launching more than 1 instance, consider EC2 Auto
    Scaling
    Including AMIs from
    AWS, Marketplace and
    the Community
    Software Image (AMI)
    Catalog
    Published
    Architecture
    Virtualization
    Root device type ENA Enabled
    Centos-8-DevOps-Practice
    ami-Of3c7d07486cad139
    Community
    2024-01-
    x86_64
    hvm
    ebs
    Yes
    AMIs
    16T13:22:50.00
    Virtual server type (instance type)
    OZ
    t2.micro
    Firewall (security group)
    SG_Allow_All
    Storage (volumes)
    Instance type Info \| Get advice
    1 volume(s) - 10 GiB
    Instance type
    Free tier: In your first year includes
    X
    t2.micro
    Free tier eligible
    750 hours of t2.micro (or t3.micro in
    Family: t2 1 vCPU 1 GiB Memory Current generation: true
    All generations
    the Regions in which t2.micro is
    On-Demand Windows base pricing: 0.0162 USD per Hour
    On-Demand SUSE base pricing: 0.0116 USD per Hour
    unavailable) instance usage on free
    On-Demand RHEL base pricing: 0.0716 USD per Hour
    Compare instance types
    tier AMIs per month, 750 hours of
    On-Demand Linux base pricing: 0.0116 USD per Hour
    public IPv4 address usage per
    Additional costs apply for AMIs with pre-installed software
    month, 30 GiB of EBS storage, 2
    million IOs, 1 GB of snapshots, and
    100 GB of bandwidth to the
    internet.
    Key pair (login) Info
    You can use a key pair to securely connect to your instance. Ensure that you have access to the selected key pair
    Cancel
    Launch instance
    before you launch the instance.
    Review commands
    Key pair name - required
    KeysC
    Create new key pair
    Network settings Info
    Edit
    Network Info

[^89]: rabitmq
    i-Of4d64877132287f5
    Running
    t2.micro
    V
    payments
    i-09353adccd5ae90cf
    Pending
    t2.micro

[^90]: Create record Info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    rabbitmq
    chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.92.11
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

[^91]: payments.chowdarychilukuri.in
    A
    Simple
    No
    172.31.89.237
    0
    rabbitmq.chowdarychilukuri.in
    A
    Simple
    No
    172.31.92.11

[^92]: Robosho-shellscripts > $ rabbitmq.sh
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R="\\e\[31m"
    UI
    G=" \\e \[32m"
    6
    Y=" \\e\[33m"
    N=" \\e\[Om"
    8
    MONGDB_HOST=mongodb . chowdarychilukuri . in
    9
    10
    TIMESTAMP=$ (date +%F-%%H: %M: %s)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 . . . $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2
    . . . $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    curl -s https://packagecloud. io/install/repositories/rabbitmq/erlang/script . rpm. sh \| bash &> > $LOGFILE
    34
    35
    VALIDATE $? "Downloading erlang script"
    36
    37
    curl -s https: //packagecloud . io/install/repositories/rabbitmq/rabbitmq-server/script. rpm. sh \| bash &> > $LOGFILE
    38
    39
    VALIDATE $? "Downloading rabbitmq script"
    40
    41
    dnf install rabbitmq-server -y &> > $LOGFILE
    42
    43
    VALIDATE $? "Installing RabbitMQ server"

[^93]: 44
    45
    systemctl enable rabbitmq-server &> > $LOGFILE
    46
    47
    VALIDATE $? "Enabling rabbitmq server"
    48
    49
    systemctl start rabbitmq-server &> > $LOGFILE
    50
    51
    VALIDATE $? "Starting rabbitmq server"
    52
    53
    rabbitmqctl add_user roboshop roboshop123 &> > $LOGFILE
    54
    55
    VALIDATE $? "creating user"
    56
    57
    rabbitmqctl set_permissions -p / roboshop
    \* 1I
    &> > $LOGFILE
    58
    59
    VALIDATE $? "setting permission"

[^94]: On branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    rabbitmq . sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest web modifications"; git push origin mainl

[^95]: \[ centosdip-172-31-92-11 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts'
    remote: Enumeratiog objects: 61, done.
    remote: Counting objects: 100% (61/61), done.
    remote: Compressing objects: 100% (47/47), done.
    remote: Total 61 (delta 33), reused 41 (delta 13), pack-reused 0
    Receiving objects: 100% (61/61), 8.85 KiB \| 2.95 MiB/s, done.
    Resolving deltas: 100% (33/33), done.
    35 . 172. 133.227 \| 172. 31. 92.11 \| t2.micro \| null
    centos@ip-172-31-92-11 \~ \]$ cd Roboshop-shellscripts/
    35. 172. 133.227 \| 172. 31. 92.11 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts. git
    \[ centos@ip-172-31-92-11 \~/Roboshop-shellscripts \]$ 1s
    cart . service catalogue . service Mongodb. sh mysql . repo rabbitmash roboshop. conf
    shipping . sh
    user . sh
    cart . sh
    catalogue . sh
    mongo . repo mysql . sh
    redis. sh
    shipping . service user . service
    web . sh
    35. 172. 133.227 \| 172. 31. 92.11 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    centos@ip-172-31-92-11 \~/Roboshop-shellscripts \]$ (

[^96]: \[ centos@ip-172-31-92-11 \~/Roboshop-shellscripts \]$ sudo sh rabbitmq. sh
    You are root user
    Downloading erlang script . . .
    SUCCESS
    Downloading rabbitmq script
    SUCCESS
    Installing RabbitMQ server .
    SUCCESS
    Enabling rabbitmq server
    SUCCESS
    Starting rabbitmq server .
    SUCCESS
    creating user
    SUCCESS
    setting permission . . .
    SUCCESS
    35. 172. 133.227 \| 172. 31.92.11 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-92-11 \~/Roboshop-shellscripts \]$ \[

[^97]: \[ centosdip-172-31-92-11 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0. 0. 0 . 0 :25672
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0. 0 . 0: 4369
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : : 5672
    : : :\*
    LISTEN
    Ecp6
    0
    : : :111
    LISTEN
    tcp6
    0 : : : 4369
    LISTEN
    Ecp6
    : : : 22
    LISTEN
    35. 172. 133.227 \| 172. 31. 92.11 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts. git
    centos@ip-172-31-92-11 \~/Roboshop-shellscripts \]$ \[\]

[^98]: Robosho-shellscripts > $ payment.sh
    1
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e \[33m"
    7
    N=" \\e \[Om"
    8
    MONGDB_HOST=mongodb . chowdarychilukuri . in
    9
    10
    TIMESTAMP=$(date +%F-%H: %M: %s)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 ... $
    $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 .
    . . . $G SUCCESS $N"
    22
    fi
    23
    }
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    dnf install python36 gcc python3-devel -y &> > $LOGFILE
    34
    35
    id roboshop #if roboshop user does not exist, then it is failure
    36
    if \[ $? -ne 0 \]
    37
    then
    38
    useradd roboshop
    39
    VALIDATE $? "roboshop user creation"
    40
    else
    41
    echo -e "roboshop user already exist $Y SKIPPING $N"
    42
    fi
    43
    44
    mkdir -p /app &> > $LOGFILE

[^99]: Robosho-shellscripts > $ payment.sh
    1
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e \[33m"
    7
    N=" \\e \[Om"
    8
    MONGDB_HOST=mongodb . chowdarychilukuri . in
    9
    10
    TIMESTAMP=$(date +%F-%H: %M: %s)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 ... $
    $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 .
    . . . $G SUCCESS $N"
    22
    fi
    23
    }
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    dnf install python36 gcc python3-devel -y &> > $LOGFILE
    34
    35
    id roboshop #if roboshop user does not exist, then it is failure
    36
    if \[ $? -ne 0 \]
    37
    then
    38
    useradd roboshop
    39
    VALIDATE $? "roboshop user creation"
    40
    else
    41
    echo -e "roboshop user already exist $Y SKIPPING $N"
    42
    fi
    43
    44
    mkdir -p /app &> > $LOGFILE

[^100]: EXPLORER
    = cart.service
    $ web.sh
    $ mysql.sh
    $ shipping.sh
    = shi
    REPOS
    Robosho-shellscripts > = payment.service
    Robosho-shellscripts
    1
    \[Unit \]
    cart.service
    2
    Description=Payment Service
    3
    $ cart.sh
    4
    \[Service\]
    catalogue.service
    5
    User=root
    $ catalogue.sh
    6
    WorkingDirectory=/app
    amongo.repo
    7
    Environment=CART_HOST=cart . chowdarychilukuri . in
    $ mongodb.sh
    8
    Environment=CART_PORT=8080
    @mysql.repo
    19
    Environment=USER_HOST=user . chowdarychilukuri . in
    $ mysql.sh
    10
    Environment=USER_PORT=8080
    11
    Environment=AMQP_HOST=rabbitmq . chowdarychilukuri . in
    = payment.service
    U
    12
    Environment=AMQP_USER=roboshop
    $ payment.sh
    U
    13
    Environment=AMQP_PASS=roboshop123
    $ rabbitmq.sh
    14
    $ redis.sh
    15
    ExecStart=/usr/local/bin/uwsgi --ini payment. ini
    roboshop.conf
    16
    ExecStop=/bin/kill -9 $MAINPID
    shipping.service
    17
    SyslogIdentifier=payment
    18
    $ shipping.sh
    19
    \[Install \]
    user.service
    20
    WantedBy=multi-user . target
    $ user.sh
    $ web.sh
    > shellscripts

[^101]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    payment . service
    payment . sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest web modifications"; git push origin mainl

[^102]: \[ centos@ip-172-31-89-237 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' . . .
    remote: Enumeratiog objects: 65, done.
    remote: Counting objects: 100% (65/65), done.
    remote: Compressing objects: 100% (50/50), done.
    remote: Total 65 (delta 35), reused 44 (delta 14), pack-reused 0
    Receiving objects: 100% (65/65), 9. 67 KiB \| 9. 67 MiB/s, done.
    Resolving deltas: 100% (35/35), done.
    54 . 209.3.232 \| 172. 31.89.237 \| t2.micro \| null
    \[ centos@ip-172-31-89-237 \~ \]$ cd Roboshop-shellscripts/
    54 . 209.3.232 \| 172. 31.89.237 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-89-237 \~/Roboshop-shellscripts \]$ 1s
    cart . service
    catalogue. sh mysql . repo
    payment . sh
    roboshop . conf
    user . service
    cart . sh
    Mongodb . sh
    mysql . sh
    rabbitmq . sh
    shipping . service
    user . sh
    catalogue . service mongo . repo
    payment. service redis. sh
    shipping . sh
    web. sh
    54. 209.3.232 \| 172. 31.89.237 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts. git
    \[ centosdip-172-31-89-237 \~/Roboshop-shellscripts \]$ 0

[^103]: \[ centosdip-172-31-89-237 \~/Roboshop-shellscripts \]$ sudo sh payment. sh
    You are root user
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading payment . . .
    SUCCESS
    unzipping payment . . .
    SUCCESS
    Installing Dependencies
    SUCCESS
    Copying payment service
    SUCCESS
    daemon reaload . . .
    SUCCESS
    Enable payment
    SUCCESS
    Start payment
    SUCCESS
    54. 209.3.232 \| 172. 31.89.237 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-89-237 \~/Roboshop-shellscripts \]$ !

[^104]: Robosho-shellscripts > $ web.sh
    1
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e \[33m"
    7
    N=" \\e \[Om"
    MONGDB_HOST=mongodb . daws76s . online
    9
    10
    TIMESTAMP=$ (date +%F-%H: %M: %S)
    11
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    12
    13
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    14
    15
    VALIDATE( ) {
    16
    if \[ $1 -ne 0 \]
    17
    then
    18
    echo -e "$2 ... $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo
    -e "$2 . . . $G SUCCESS $N"
    22
    fi
    23
    24
    25
    if \[ $ID -ne 0 \]
    26
    then
    27
    echo -e "$R ERROR: : Please run this script with root access $N"
    28
    exit 1 # you can give other than 0
    29
    else
    30
    echo "You are root user"
    31
    fi # fi means reverse of if, indicating condition end
    32
    33
    def install nginx -y &> > $LOGFILE
    34
    35
    VALIDATE $? "Installing nginx"
    36
    37
    systemctl enable nginx &>> $LOGFILE
    38
    39
    VALIDATE $? "Enable nginx"
    40
    41
    systemctl start nginx &>> $LOGFILE
    42
    43
    VALIDATE $? "Starting Nginx"

[^105]: 44
    45
    rm -rf /usr/share/nginx/html/\* &>> $LOGFILE
    46
    47
    VALIDATE $? "removed default website"
    48
    49
    curl -o /tmp/web. zip https: //roboshop-builds . s3. amazonaws . com/web . zip &> > $LOGFILE
    50
    51
    VALIDATE $? "Downloaded web application"
    52
    53
    cd /usr/share/nginx/html &>> $LOGFILE
    54
    55
    VALIDATE $? "moving to nginx html directory"
    56
    57
    unzip -o /tmp/web . zip &>> $LOGFILE
    58
    59
    VALIDATE $? "unzipping web"
    60
    61
    cp /home/centos//Roboshop-shellscripts/roboshop . conf /etc/nginx/default.d/roboshop. conf &> > $LOGFILE
    62
    63
    VALIDATE $? "copied roboshop reverse proxy config"
    64
    65
    systemctl restart nginx &> > $LOGFILE
    66
    67
    VALIDATE $? "restarted nginx"

[^106]: EXPLORER
    . . .
    .sh
    $ shipping.sh
    shipping.service
    $ rabbitmq.sh
    $ payment.sh
    = payment.service
    mysql.repo
    REPOS
    Robosho-shellscripts > @ roboshop.conf
    Robosho-shellscripts
    1
    proxy_http_version 1.1;
    cart.service
    2
    location /images/ {
    3
    $ cart.sh
    expires 5s;
    4
    catalogue.service
    root /usr/share/nginx/html;
    15
    try_files $uri /images/placeholder . jpg;
    $ catalogue.sh
    6
    }
    mongo.repo
    7
    location /api/catalogue/ { proxy_pass http://catalogue. chowdarychilukuri . in: 8080/;
    $ mongodb.sh
    8
    location /api/user/ { proxy_pass http://user . chowdarychilukuri . in: 8080/; }
    @ mysql.repo
    9
    location /api/cart/ { proxy_pass http://cart. chowdarychilukuri . in : 8080/; }
    $ mysql.sh
    location /api/shipping/ { proxy_pass http://shipping . chowdarychilukuri . in: 8080/;
    3
    11
    = payment.service
    location /api/payment/ { proxy_pass http://payment . chowdarychilukuri . in: 8080/;
    12
    $ payment.sh
    13
    location /health {
    $ rabbitmq.sh
    14
    stub_status on;
    redis.sh
    15
    access_log off;
    roboshop.conf
    16
    }
    shipping.service
    $ shipping.sh
    user.service
    $ user.sh
    $ web.sh
    > shellscripts

[^107]: (use "git add <file>.
    ..." to include in what will be committed)
    roboshop . conf
    web . sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest web modifications"; git push origin main
    warning: in the working copy of 'web. sh', LF will be replaced by CRLF the next time Git touches it

[^108]: SuperPUTTY - Web
    File View Tools Help
    Protocol SSH
    Host 54.152.150.169
    Login
    Password
    Session
    chilops
    O X
    Commands
    MongoDB
    Catalogue
    user
    Redis
    Cart
    Web
    54 . 152 . 150. 169 \| 172. 31. 16.157 \| t2.micro \| null
    \[ centos@ip-172-31-16-157 \~ \]$ \[

[^109]: \[ centos@ip-172-31-16-157 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' ...
    remote: Enumeratiog objects: 52, done.
    remote: Counting objects: 100% (52/52), done.
    remote: Compressing objects: 100% (39/39), done.
    remote: Total 52 (delta 28), reused 36 (delta 12), pack-reused 0
    Receiving objects: 100% (52/52), 6.99 KiB \| 6.99 MiB/s, done.
    Resolving deltas: 100% (28/28), done.
    54 . 152. 150.169 \| 172. 31. 16. 157 \| t2.micro \| null
    \[ centosdip-172-31-16-157 \~ \]$ 1s
    Roboshop-shellscripts
    54 . 152 . 150.169 \| 172. 31. 16.157 \| t2.micro \| null
    \[ centos@ip-172-31-16-157 \~ \]$ cd Roboshop-shellscripts/
    54 . 152 . 150.169 \| 172. 31.16.157 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ 1s
    cart . service catalogue . service Mongodb. sh redis. sh
    user . service web. sh
    cart . sh
    catalogue . sh
    mongo . repo roboshop . conf
    user . sh

[^110]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ sudo sh web. sh
    You are root user
    Installing nginx
    SUCCESS
    Enable nginx
    SUCCESS
    Starting Nginx . .
    SUCCESS
    removed default website . ..
    SUCCESS
    Downloaded web application . . .
    SUCCESS
    moving to nginx html directory
    . . .
    SUCCESS
    unzipping web
    SUCCESS
    copied roboshop reverse proxy config . . .
    SUCCESS
    restarted nginx ...
    SUCCESS

[^111]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0. 0.0.0:111
    0.0.0.0:\*
    LISTEN
    cp
    0 0.0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : :111
    : : :\*
    LISTEN
    cp6
    0 : : :22
    LISTEN

[^112]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0. 0. 0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0. 0.0. 0:80
    0.0.0.0:\*
    LISTEN
    tcp
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    oooOOO
    tcp6
    0 :::111
    LISTEN
    tcp6
    0 :::80
    LISTEN
    tcp6
    0 : : :22
    LISTEN

[^113]: centosdip-172-31-16-15/ \~/Roboshop-shellscripts \]s sudo systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2024-04-18 07:57:12 UTC; 7min ago
    Process: 6726 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 6723 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 6721 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0/SUCCESS)

[^114]: \[ centosdip-172-31-16-157 \~/Roboshop-shellscripts \]$ sudo less /var/log/messages \| grep -i nginx
    Apr 18 07:57:09 ip-172-31-16-157 systemd \[1\]: nginx. service: Unit cannot be reloaded because it is inactive.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\]: Starting The nginx HTTP and reverse proxy server . ..
    Apr 18 07:57:11 ip-172-31-16-157 nginx \[6459\]: nginx: the configuration file /etc/nginx/nginx. conf syntax is ok
    Apr 18 07:57:11 ip-172-31-16-157 nginx \[6459\]: nginx: configuration file /etc/nginx/nginx. conf test is successful
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\]: nginx. service: Failed to parse PID from file /run/nginx.pid: Invalid argument
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\]: Started The nginx HTTP and reverse proxy server.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : Stopping The nginx HTTP and reverse proxy server. . .
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : nginx. service: Succeeded.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : Stopped The nginx HTTP and reverse proxy server.
    Apr 18 07:57:11 ip-172-31-16-157 systemd \[1\] : Starting The nginx HTTP and reverse proxy server. ..
    Apr 18 07:57:12 ip-172-31-16-157 nginx \[6723\]: nginx: the configuration file /etc/nginx/nginx. conf syntax is ok
    Apr 18 07:57:12 ip-172-31-16-157 nginx \[6723\]: nginx: configuration file /etc/nginx/nginx. conf test is successful
    Apr 18 07:57:12 ip-172-31-16-157 systemd \[1\] : nginx. service: Failed to parse PID from file /run/nginx. pid: Invalid argument
    Apr 18 07:57:12 ip-172-31-16-157 systemd \[1\] : Started The nginx HTTP and reverse proxy server.
    54 . 152 . 150.169 \| 172. 31 . 16.157
    t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git

[^115]: G
    Not secure \| chowdarychilukuri.in/product/STAN-1
    Al
    Stan's Robot Shop
    Search
    Login / Register
    Cart
    Stan
    STAN
    Empty
    Categories
    . Artificial
    Intelligence
    o HAL
    . Positronic
    Brain
    o Stan
    . Robot
    STAND
    . C3PO
    o Eve
    o K9
    o Kryten
    . Marvin
    . Mr Data
    . R2D2
    o Robbie
    o Stan
    Rating No votes yet. Vote now.
    APM guru
    Price E67.00 Quantity 1
    Add to cart

[^116]: C
    Not secure \| chowdarychilukuri.in/payment
    P
    . . .
    Stan's Robot Shop
    Search
    Login / Register
    Review your order
    Cart
    Order placed 66ea2568-50bf-4b2d-87d4-283c59735569
    STAN
    Empty
    Thank you for your order Continue shopping
    Categories
    . Artificial
    Intelligence
    o HAL
    o Positronic
    Brain
    Stan
    . Robot
    chill

