---
title: 4Day_Linux
uuid: 956743c8-0e84-11ef-9be8-a6f126245c9e
version: 240
created: '2024-05-10T09:50:06+05:30'
tags:
  - linux
---

***Topics:***

1. *<mark style="background-color:#f8d616;">Service Management - **0 to 65535 ports**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8914d;">**Installing nginx to check port is communicating or not.**<!-- {"backgroundCycleColor":"24"} --></mark>*

1. *<mark style="background-color:#f8d616;">Network Management  - **netstat**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Troubleshooting process - **top, df -hT (FS usage), free (to check ram usage)**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">How to give access to Linux user<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">User creating & group creation & adding users to groups<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">3 Tier Architecture<!-- {"backgroundCycleColor":"25"} --></mark>*

 

 

 

 

# *<mark style="background-color:#f8914d;">**Service Management: **<!-- {"backgroundCycleColor":"24"} --></mark> 0 to 65535 ports available.*<!-- {"collapsed":true} -->

![33de7e0c-c67d-4d0a-86cb-f8adf2f32297.png|640](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/33de7e0c-c67d-4d0a-86cb-f8adf2f32297.png) [^1]

 

 

*ssh -i <private-key> ec2-user@IP*

 

*ssh port no - 22*

 

*http: 80*

*https: 443*

*mysql: 3306*

*SMTP: 25*

*FTP:*

 

![09abdf84-a6c6-4256-a1e2-34966ffa9b22.png|273](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/09abdf84-a6c6-4256-a1e2-34966ffa9b22.png)

 

*<mark style="background-color:#f3de6c;">**Popular protocols**<!-- {"backgroundCycleColor":"14"} --></mark>*

![6735c4d6-c0a2-46c8-ab5d-4fae43b7d6f0.png|690](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/6735c4d6-c0a2-46c8-ab5d-4fae43b7d6f0.png) [^2]

 *To check if ssh service is running or not.. If it running only then SSH will work.*

```
ps -ef | grep -i ssh     
```

![cfe5e5dc-e676-4384-8683-c4c89b937cad.png|672](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/cfe5e5dc-e676-4384-8683-c4c89b937cad.png) [^3]

 

[*https://facebook.com:443*](https://facebook.com:443)    *--> request will go to Facebook ip address, then it will search if https process is running or not.. If it runs then only we will get login page else it show down/error.*

 

*request reach IP address*

 

*https--> 443*

*\*system will check anything is running ssh process with port no 22*

*\*now authentication will be checked*

 

# *<mark style="background-color:#f8914d;">**Installing nginx to check port is communicating or not.**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
sudo amazon-linux-extras install nginx1 -y
```

![7162318a-cfd1-4e08-8ce6-7050b23d8176.png|812.3333740234375](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/7162318a-cfd1-4e08-8ce6-7050b23d8176.png) [^4]

 

*service --> offering service  -- it should be running.*

*nginx1 --> it should be running, it’s a http protocol & it will use port 80*

 

```
sudo systemctl start nginx   --> nginx will start run
```

```
systemctl status nginx
```

*Or*

```
ps -ef | grep -I nginx
```

![79cdc8dc-5622-4beb-9039-77ac36f5b938.png|767.3333740234375](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/79cdc8dc-5622-4beb-9039-77ac36f5b938.png) [^5]

 

![523700af-3e34-42f8-b1a5-e88cf8309ab0.png|769](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/523700af-3e34-42f8-b1a5-e88cf8309ab0.png) [^6]

 

[*http://54.224.185.251:80*](http://54.224.185.251:80) 

 

![41e2c62a-50c5-48d5-93d5-84b0b7108ef6.png|769.3333740234375](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/41e2c62a-50c5-48d5-93d5-84b0b7108ef6.png) [^7]

 

```
sudo systemctl stop nginx   --> nginx will stop run
```

```
systemctl status nginx
```

*Or*

```
ps -ef | grep -I nginx
```

 

![70dcb4d2-63bf-4c32-be9e-56b7ecdc1581.png|867.3333740234375](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/70dcb4d2-63bf-4c32-be9e-56b7ecdc1581.png) [^8]

 

 

*Now check if website is running or not… it wont run since nginx(port 80) stopped running.*

 

![91e2f601-c94d-4792-888f-8535441ce14b.png|829](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/91e2f601-c94d-4792-888f-8535441ce14b.png) [^9]

 

 

```
systemctl enable nginx --> if services are enabled, after restart automatically services will run
```

```
systemctl disable nginx
```

 

 

# *<mark style="background-color:#f8914d;">**Network Management -**<!-- {"backgroundCycleColor":"24"} --></mark><mark style="background-color:#f8d616;">**netstat**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 *Network statistics -To check if netstat is installed or not*

```
netstat 
```

 

![db503838-43f2-43f3-acc4-a4dce1f139f5.png|750](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/db503838-43f2-43f3-acc4-a4dce1f139f5.png) [^10]

 

```
netstat -lntp
```

![048d844e-570f-44e6-8308-c9ae99309708.png|830](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/048d844e-570f-44e6-8308-c9ae99309708.png) [^11]

 

*Stopping Nginx protocol to check netstat command*

```
sudo systemctl stop nginx
```

```
netstat -lntp
```

```
sudo netstat -lntp
```

![c1ab9de0-069f-465a-ad43-3b1096f6ae11.png|813](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/c1ab9de0-069f-465a-ad43-3b1096f6ae11.png) [^12]

 

 

# *<mark style="background-color:#f8914d;">**Troubleshooting process --> if system is hung**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*system resources*

*cpu memory --> check mem usage*

*HD full --> df -hT*

*RAm full --> free*

*process is running or not --> ps -ef \| grep nginx*

*port opened or not --> netstat -lntp*

*systemctl status <service> -->  systemctl status ngnix*

*firewall is opened or not*

 

```
top
```

 

![09674f8f-daea-401f-b9bb-f5eea00a3c51.png|650](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/09674f8f-daea-401f-b9bb-f5eea00a3c51.png) [^13]

 

```
df -hT
```

 

![b985e8a8-d84f-496e-b73b-161a7a7dd671.png|547](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/b985e8a8-d84f-496e-b73b-161a7a7dd671.png) [^14]

 

```
free    -- to check RAM usage
```

```
free -m
```

![a2d7aef3-1f76-45b6-ae83-9ecbd89ebbee.png|736](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/a2d7aef3-1f76-45b6-ae83-9ecbd89ebbee.png) [^15]

 

 

# *<mark style="background-color:#f8914d;">**How to give access to Linux user -**<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#f3de6c;">User creating & group creation & adding users to groups<!-- {"backgroundCycleColor":"14"} --></mark>*<!-- {"collapsed":true} -->

*Linux Admin --> full access to linux*

*DevOps Admin --> limited sudo access*

 

*Sanjay--> Linuxadmin, add him to wheel group or give admin group full access*

*Satya--> devops*

 

*User creating & group creation & adding users to groups*

```
sudo su
```

```
groupadd Linuxteam
```

```
groupadd devops
```

 

```
useradd satya
```

```
useradd sanjay 
```

```
usermod -g devops satya
```

```
id satya
```

 

```
id
```

```
useradd sanjay
```

```
id sanjay
```

```
usermod -g Linuxteam sanjay
```

```
id sanjay
```

 

![a6336799-f42c-40e9-9aa7-dd47f0590491.png|595](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/a6336799-f42c-40e9-9aa7-dd47f0590491.png) [^16]

 

 

*If I want to give **sudo** access to **Linuxadmin** --> to give sudo access there will be a file '/etc/sudoers'  - Don't open this command with VIM. For safe open with **visudo***

 

 

*Sanjay--> Linuxadmin, add him to **wheel** group or give admin group full access*

```
visudo
```

![](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/11055e13-fa49-49e8-b697-b27864b63413.png)

 

![ef1d2d8c-9a4c-4c26-8501-47374ec17cc1.png|793](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/ef1d2d8c-9a4c-4c26-8501-47374ec17cc1.png) [^17]

 

*After adding*

![e5dcd238-ee5e-43bf-b7a8-d4ae38c17573.png|774](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/e5dcd238-ee5e-43bf-b7a8-d4ae38c17573.png) [^18]

 

***Changing the authentication as yes***

![52c742cc-f798-4039-987a-1bfacfdacbd5.png|610](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/52c742cc-f798-4039-987a-1bfacfdacbd5.png) [^19]

 

***Before***

![303bd999-debf-4a9f-8df8-7e308d571c41.png|582](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/303bd999-debf-4a9f-8df8-7e308d571c41.png) [^20]

 

***After***

![cc95ed54-14eb-4836-8952-405ae946654d.png|585](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/cc95ed54-14eb-4836-8952-405ae946654d.png) [^21]

 

***After making changes in sshd file, restart the services***

 

```
systemctl restart sshd
```

![215c51fe-72cd-476f-a067-277ac937ec26.png|588](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/215c51fe-72cd-476f-a067-277ac937ec26.png) [^22]

 

 

***Now changing the password for both users***

```
passwd satya
```

```
passwd sanjay
```

![a6073047-0673-48ef-a5dd-eca8e89d12da.png|735](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/a6073047-0673-48ef-a5dd-eca8e89d12da.png) [^23]

 

 

***Login to sanjay to check if he is root user or not.. Since we gave him root access***

![4f18fcbf-99ca-4c76-9ba2-84795653de1a.png|721](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/4f18fcbf-99ca-4c76-9ba2-84795653de1a.png) [^24]

 

***If he is root user he can install git else no…***

```
sudo yum install git -y
```

![4048e035-310b-4ce0-96b9-a10be80ebfa4.png|892](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/4048e035-310b-4ce0-96b9-a10be80ebfa4.png) [^25]

 

 

***To give limited access to user satya (part of devops team)***

 

*DevOps Admin --> limited sudo access*

*yum, systemctl*

 

```
visudo
```

```
%devops  ALL=(ALL)   /usr/bin/yum,/usr/bin/systemctl
```

![3308e5f7-9f3a-441b-aa52-bf85440de0a8.png|652](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/3308e5f7-9f3a-441b-aa52-bf85440de0a8.png) [^26]

 

***Now trying to install git using yum & checking systemctl***

```
sudo yum install git -y
```

 

![84a92e8e-8487-4640-a034-be74fa5d5973.png|759.3333740234375](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/84a92e8e-8487-4640-a034-be74fa5d5973.png) [^27]

 

```
sudo systemctl stop nginx
```

```
systemctl status nginx
```

```
sudo systemctl stop nginx
```

```
systemctl status nginx
```

![dea142e5-7de2-4f94-8878-7c18b11f1cf9.png|814](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/dea142e5-7de2-4f94-8878-7c18b11f1cf9.png) [^28]

 

![8f7aa053-2388-41a3-9699-cfb63efdf4a1.png|814](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/8f7aa053-2388-41a3-9699-cfb63efdf4a1.png) [^29]

 

***Since you have limited access so you cant perform all admin commands***

```
sudo useradd madhu
```

![0408b027-6a39-48bf-a330-d686f6505b3d.png|905](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/0408b027-6a39-48bf-a330-d686f6505b3d.png) [^30]

 

 

***Other way to give permissions to users under** /etc/sudoers.d/devops**, since every time opening visudo is not safe & right practice.***

 

*#vim /etc/sudoers.d/devops      --> here in devops place we can add other file as linuxadmin, testingteam, etc.. So that we don’t get errors and we can delete when we want to delete devops file etc…*

```
%devops  ALL=(ALL)   /usr/bin/yum,/usr/bin/systemctl
```

 

![91231198-0bfa-44da-9051-9a86f68e1387.png|482](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/91231198-0bfa-44da-9051-9a86f68e1387.png) [^31]

 

***Now login to user satya(devops team/group) now check if you have permissions to install yum, systemctl***

```
sudo useradd madhu
```

```
sudo systemctl start nginx
```

```
systemctl status nginx
```

```
sudo systemctl stop nginx
```

```
systemctl status nginx
```

```
sudo systemctl restart nginx
```

 

![0e3cae46-53f7-41e2-bade-ac98b766bd46.png|853](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/0e3cae46-53f7-41e2-bade-ac98b766bd46.png) [^32]

 

 

***Now if you want to delete permissions to devops group then simply delete/comment the file devops under** /etc/sudoers.d/devops*

```
cd /etc/sudoers.d
```

```
ls -l
```

```
rm -rf devops
```

```
ls -l
```

 

![facaa126-4cb6-4445-906c-ec7bb832e6cf.png|525](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/facaa126-4cb6-4445-906c-ec7bb832e6cf.png) [^33]

 

![7c92f1f8-f299-4182-a795-5ccc10951a87.png|579](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/7c92f1f8-f299-4182-a795-5ccc10951a87.png) [^34]

 

 

 

# *<mark style="background-color:#f8914d;">**3 Tier Architecture**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

***Web applications** - Google sheets, docs, Ms office, bank applications*

*Ex. It's like a hotel, go n eat food.*

 

*<mark style="background-color:#f3de6c;">**Hotel Business**<!-- {"backgroundCycleColor":"14"} --></mark>*

*more people, more food, more money, more quality*

 

*RAW Items --> Cook --> We are serving*

 

*1. cook/cashier/manage customers --> roadside*

 

*10 persons we are able to serve*

 

*2. no proper cooking, we lose money --> hotel*

 

*1 employee --> cook*

*owner -> manage customers, token, money collection*

 

*20 persons can be managed*

 

*3. Restaurent*

 

*Captain --> customers receive*

*Waiter --> takes order*

*Chef --> cook*

*Raw Items*

 

 

*<mark style="background-color:#f8d616;">**1 server**<!-- {"backgroundCycleColor":"25"} --></mark>*

*DB table format --> users cant understand*

*Web application -->*

*fields --> enter username, enter password  -->insert data into DB*

 

 

***New way** --> Web applications will have Front End, Backend*

***Frontend** - HTML, Javascript(JS), Angular JS, ReactJS*

***Backend** - Java/.NET/Python/NodeJS*

*-----------*

 

***Old way** --> frontend+backend --> single application  (few years back frontend , backend are combined so more issue)*

*queue management --> is tough*

*security --> customers can easily copy your recipe*

*if DB and application in single server*

 

***3 Tier Architecture***

![a425a0f1-f7fd-40fa-a32f-3712cf17ef2f.png|768](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/a425a0f1-f7fd-40fa-a32f-3712cf17ef2f.png) [^35]

 

 

![98478979-3435-49ee-a868-5a6c83f762db.png|741](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/98478979-3435-49ee-a868-5a6c83f762db.png) [^36]

 

 

![9e6a25cb-2e53-4500-8796-caecf726b1b8.png|743](https://images.amplenote.com/956743c8-0e84-11ef-9be8-a6f126245c9e/9e6a25cb-2e53-4500-8796-caecf726b1b8.png) [^37]

[^1]: Delhi --> Hyd
    To address
    D. No: 123, 2nd floor
    Tirumala apartment
    hitech city
    Hyderabad
    600082
    Shipping is in Hyd
    - - -
    HYD central Shipping Hub
    Hitech City Regional HUb --> area
    Hitech City Regional HUb --> Apartment
    D . NO :

[^2]: Port No
    Port
    Protocol
    21
    FTP
    TCP
    22
    SSH
    TCP
    23
    TELNET
    TCP
    25
    SMTP
    TCP
    53
    DNS
    TCP, UDP
    67,68
    DHCP
    UDP
    80
    HTTP
    TCP
    110
    POP3
    TCP
    111
    Portmapper
    TCP, UDP
    123
    NTP
    UDP
    137
    NetBIOS
    TCP, UDP
    143
    IMAP
    TCP, UDP
    161, 162
    SNMP
    UDP
    443
    HTTPS
    TCP

[^3]: Lecz-user@1p-1/ 2-31-37-1/ 1 \~Id
    \[ec2-user@ip-172-31-37-171 \~\]$ ps -ef \| grep -i ssh
    root
    3219
    1 0 10:38 ?
    00: 00:00 /usr/sbin/sshd -D
    root
    3388
    3219
    0 11:18 ?
    00:00:00 sshd: ec2-user \[priv\]
    ec2-user
    3422
    3388
    0 11:18 ?
    00: 00:00 sshd: ec2-user@pts/0
    ec2-user
    3448
    3423
    0 11:19 pts/0
    00:00:00 grep --color=auto -i ssh
    \[ec2-user@ip-172-31-37-171 \~\]$

[^4]: \[ec2-user@ip-172-31-37-171 \~\]$ sudo amazon-linux-extras install nginx1 -y
    Installing nginx
    Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
    Cleaning repos: amzn2-core amzn2extra-docker amzn2extra-kernel-5 . 10 amzn2extra-nginx1
    metadata files removed
    sqlite files removed
    0 metadata files removed
    oaded plugins: extras_suggestions, langpacks, priorities, update-motd
    amzn2-core
    3.6 KB
    00: 00: 00
    amzn2extra-docker
    2.9 KB
    00: 00:00
    amzn2extra-kernel-5 . 10
    3.0 KB
    00 : 00: 00
    amzn2extra-nginx1
    2.9 KB
    00: 00:00
    (1/9): amzn2-core/2/x86_64/updateinfo
    742 KB
    00 : 00: 00
    (2/9): amzn2-core/2/x86_64/group_gz
    2.7
    00 : 00: 00
    (3/9): amzn2extra-docker/2/x86_64/updateinfo
    13 KB
    00 : 00:00
    (4/9) : amzn2extra-nginx1/2/x86_64/updateinfo
    3.0 KB
    00 : 00:00
    (5/9): amzn2extra-nginx1/2/x86_64/primary_db
    55 KB
    00 : 00:00
    (6/9): amzn2extra-docker/2/x86_64/primary_db
    104 KB
    00: 00: 00
    (7/9): amzn2extra-kernel-5 . 10/2/x86_64/updateinfo
    42 KB
    00 : 00:00
    8/9): amzn2extra-kernel-5 . 10/2/x86_64/primary_db
    21 MB
    00 : 00:00
    (9/9): amzn2-core/2/x86_64/primary_db
    68 MB
    00 : 00: 00
    Resolving Dependencies
    Running transaction check
    Package nginx. x86_64 1:1.22.1-1. amzn2 . 0.3 will be installed
    Processing Dependency: nginx-core = 1:1.22. 1-1. amzn2. 0. 3 for package: 1:nginx-1. 22.1-1. amzn2 . 0. 3.x86_64

[^5]: ec2-user@ip-172-31-37-171 \~\]$ sudo systemctl start nginx
    ec2-user@ip-172-31-37-171 \~\]$ systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: active (running) since Fri 2023-12-01 11:31:52 UTC; 1min 24s ago
    Process: 3592 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 3588 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 3587 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0/SUCCESS)
    Main PID: 3594 (nginx)
    CGroup :
    /system. slice/nginx. service
    -3594 nginx: master process /usr/sbin/nginx
    -3595 nginx: worker process
    Dec 01 11:31:52 ip-172-31-37-171. ec2. internal systemd\[1\]: Starting The nginx HTTP and reverse proxy server . . .
    Dec 01 11:31:52 ip-172-31-37-171. ec2. internal nginx \[3588\]: nginx: the configuration file /etc/nginx/nginx. conf syntax is ok
    Dec 01 11:31:52 ip-172-31-37-171. ec2. internal nginx \[3588\]: nginx: configuration file /etc/nginx/nginx. conf test is successful
    ec 01 11:31:52 ip-172-31-37-171. ec2. internal systemd\[1\]: Started The nginx HTTP and reverse proxy server.
    ec2-
    serain-
    -172-31-37-171 \~1$

[^6]: Lecz-userdip-1/ 2-51-37 -1/1 \~13
    \[ec2-user@ip-172-31-37-171 \~\]$ ps -ef \| grep -I nginx
    root
    3594
    1 0 11:31 ?
    00: 00:00 nginx: master process /usr/sbin/nginx
    nginx
    3595
    3594
    0 11:31 ?
    00:00:00 nginx: worker process
    ec2-user 32387 3423
    0 11:34 pts/0
    00:00:00 grep --color=auto -I nginx
    \[ec2-user@ip-172-31-37-171 \~\]$

[^7]: notes/session-04.txt at master . d X
    Instances \| EC2 \| us-east-1
    X
    Welcome to nginx!
    X
    +
    G
    A
    Not secure
    54.224.185.251
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^8]: ecz-user@1p-1
    \[ec2-user@ip-172-31-37-171 \~\]$ sudo systemctl stop nginx -
    \[ec2-user@ip-172-31-37-171 \~\] $
    \[ec2-user@ip-172-31-37-171 \~\]$ systemctl status nginx
    nginx. service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: inactive (dead)
    Dec 01 11:31:52 ip-172-31-37-171. ec2. internal systemd\[1\]: Starting The nginx HTTP and reverse proxy server . . .
    Dec 01 11:31:52 ip-172-31-37-171. ec2. internal nginx\[3588\]: nginx: the configuration file /etc/nginx/nginx. conf syntax is ok
    Dec 01 11:31:52 ip-172-31-37-171. ec2. internal nginx \[3588\]: nginx: configuration file /etc/nginx/nginx. conf test is successful
    Dec 01 11:31:52 ip-172-31-37-171.ec2. internal systemd\[1\] : Started The nginx HTTP and reverse proxy server.
    Dec 01 11:38:33 ip-172-31-37-171. ec2. internal systemd\[1\]: Stopping The nginx HTTP and reverse proxy server . .
    Dec 01 11:38:33 ip-172-31-37-171. ec2. internal systemd\[1\] :
    Stopped The nginx HTTP and reverse proxy server.

[^9]: notes/session-04.txt at master . d X
    Instances \| EC2 \| us-east-1
    X
    54.224.185.251
    X
    C
    i
    54.224.185.251
    Hmmm... can't reach this page
    54.224.185.251 refused to connect.
    Try:
    . Search the web for 54 224 185 251
    . Checking the connection
    . Checking the proxy and the firewall

[^10]: \[ec2-user@ip-172-31-37-171 \~\]$ netstat
    Active Internet connections (w/o servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    tcp
    236 ip-172-31-37-171. ec:ssh broadband . actcorp : 13260 ESTABLISHED
    Active UNIX domain sockets (w/o servers)
    Proto RefCnt Flags
    Type
    State
    I-Node
    Path
    unix
    3
    DGRAM
    11563
    /run/systemd/notify
    unix
    DGRAM
    11564
    /run/systemd/cgroups-agent
    unix
    5
    DGRAM
    11570
    / run/systemd/journal/socket
    unix
    2
    DGRAM
    16426
    / run/chrony/chronyd . sock
    unix
    16
    DGRAM
    11571
    /dev/log
    unix
    DGRAM
    13152
    /run/systemd/shutdownd
    un1x
    STREAM
    CONNECTED
    17970
    unix
    DGRAM
    18024
    WWW NW N
    unix
    STREAM
    CONNECTED
    17960
    unix
    STREAM
    CONNECTED
    17964
    unix
    STREAM
    CONNECTED
    17951

[^11]: \[ec2-user@ip-172-31-37-171 \~\]$ netstat -Intp
    (No info could be read for "-p": geteuid()=1000 but you should be root.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:80
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    tcp
    oooOOO
    0 127 . 0.0.1:25
    0.0.0.0:\*
    LISTEN
    tcp6
    :::111
    LISTEN
    tcp6
    : 80
    LISTEN
    OO
    tcp6
    : : :22
    LISTEN
    \[ec2-user@ip-172-31-37-171

[^12]: \[ec2-user@ip-172-31-37-171 \~\]$ netstat -Intp
    (No info could be read for
    "-p": geteuid()=1000 but you should be root. )
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:80
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    tcp
    0 127 . 0. 0. 1:25
    0.0.0.0:\*
    LISTEN
    tcp6
    : : :111
    LISTEN
    tcp6
    0 : : :80
    LISTEN
    tcp6
    0 : : :22
    LISTEN
    \[ec2-user@ip-172-31-37-171 \~\]$ sudo systemctl stop nginx
    \[ec2-user@ip-172-31-37-171 \~\] $
    \[ec2-user@ip-172-31-37-171 \~\]$ netstat -Intp
    (No info could be read for "-p": geteuid()=1000 but you should be root.)
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
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    tcp
    0 127 . 0. 0. 1:25
    0.0.0.0:\*
    LISTEN
    tcp6
    OOO
    0 :: :111
    LISTEN
    tcp6
    0 : : :22
    LISTEN
    \[ec2-user@ip-172-31-37-171 \~\]$

[^13]: \[ec2-user@ip-172-31-37-171 \~\]$ top
    top - 11:56:12 up 1:17, 1 user,
    load average: 0.00, 0.00, 0.00
    Tasks: 92 total,
    1 running, 50 sleeping,
    0 stopped, 0 zombie
    %Cpu (s): 0.0 us
    0.0 sy ,
    0.0 ni , 100.0 id,
    0.0 wa, 0.0 hi, 0.0 si, 0.0 st
    KiB Mem :
    975588 total ,
    207828 free,
    84576 used,
    683184 buff /cache
    KiB Swap :
    0 total,
    0 free,
    0 used.
    743956 avail Mem
    PID USER
    PR NI
    VIRT
    RES
    SHR S %CPU %MEM
    TIME+ COMMAND
    1
    root
    20
    123620
    5580
    3960 S 0.0 0.6
    0: 02 . 32 systemd
    2
    root
    20
    0
    O
    S
    0.0 0.0
    0:00.00 kthreadd
    3 root
    0 -20
    I
    0.0 0.0
    0: 00.00 rcu_gp
    4 root
    0 -20
    OI
    0.0 0.0
    0:00.00 rcu_par_gp
    6 root
    -20
    0
    T
    0.0 0.0
    0:00.00 kworker/0: OH-ev
    8 root
    0 -20
    0.0 0.0
    0:00.00 mm_percpu_wq
    9 root
    20
    S
    0.0
    0.0
    0:00.00 rcu_tasks_rude_
    10 root
    20
    S
    0.0 0.0
    0: 00. 00 rcu_tasks_trace
    11 root
    20
    S
    0.0 0.0
    0:00. 08 ksoftirad/0
    12 root
    20
    booooooo
    0.0 0.0
    0: 00. 12 rcu_sched
    13 root
    rt
    S
    0.0 0.0
    0:00. 02 migration/0
    15 root
    20
    S
    0.0 0.0
    0: 00.00 cpuhp/0
    17 root
    20
    S
    0.0 0.0
    0:00.00 kdevtmpfs
    18 root
    I
    0.0 0.0
    0:00.00 netns
    21 root
    20
    0
    V
    0.0 0.0
    0:00. 01 kauditd

[^14]: \[ec2-user@ip-172-31-37-171 \~\]$ of -hT
    Filesystem
    Type
    Size
    Used Avail Use% Mounted on
    devtmpfs
    devtmpfs
    468M
    O
    468M
    0% /dev
    tmpfs
    tmpfs
    477M
    O
    477M
    0% /dev/shm
    Empfs
    tmpfs
    477M
    464K
    476M
    1% /run
    tmpfs
    tmpfs
    477M
    O
    477M
    0% /sys /fs /cgroup
    /dev/xvdal
    xfs
    8 . OG
    1.7G
    6.4G
    21% /
    tmpfs
    tmpfs
    96M
    96M
    0% /run/user/0
    OO
    Empfs
    tmpfs
    96M
    96M
    0% /run/user /1000
    ec2-user@ip-172-31-37-171 \~\]$

[^15]: \[ec2-user@ip-172-31-37-171 \~\]$ free
    total
    used
    free
    shared buff/cache
    available
    Mem:
    975588
    84524
    207820
    464
    683244
    743992
    Swap :
    O
    0
    O
    \[ec2-user@ip-172-31-37-171 \~\] $
    \[ec2-user@ip-172-31-37-171 \~\]$ free -m
    total
    used
    free
    shared buff /cache
    available
    Mem :
    952
    82
    202
    0
    667
    726
    Swap :
    0
    0
    O
    \[ec2-user@ip-172-31-37-171 \~\]$

[^16]: \[ec2-user@ip-172-31-37-171 \~\]$ sudo su_
    \[root@ip-172-31-37-171 ec2-user\]#
    \[root@ip-172-31-37-171 ec2-user\]# groupadd Linuxteam
    \[root@ip-172-31-37-171 ec2-user\]# groupadd devops-
    \[root@ip-172-31-37-171 ec2-user\]#
    \[root@ip-172-31-37-171 ec2-user\]# useradd satya
    \[root@ip-172-31-37-171 ec2-user\]# useradd sanjay
    \[root@ip-172-31-37-171 ec2-user\]#
    \[root@ip-172-31-37-171 ec2-user\]# usermod -g devops satya
    \[root@ip-172-31-37-171 ec2-user\]# id satya -
    uid=1001(satya) gid=1002 (devops) groups=1002 (devops)
    \[root@ip-172-31-37-171 ec2-user\]#
    \[root@ip-172-31-37-171 ec2-user\]# id
    uid=0(root) gid=0(root) groups=0(root)
    \[root@ip-172-31-37-171 ec2-user\]# useradd sanjay
    useradd: user 'sanjay' already exists
    \[root@ip-172-31-37-171 ec2-user\]# id sanjay
    uid=1002 (sanjay) gid=1004 (sanjay) groups=1004(sanjay)
    \[root@ip-172-31-37-171 ec2-user\]# usermod -g linuxteam sanjay
    usermod: group 'linuxteam' does not exist
    \[root@ip-172-31-37-171 ec2-user\]# usermod -g Linuxteam sanjay_
    \[root@ip-172-31-37-171 ec2-user\]#
    \[root@ip-172-31-37-171 ec2-user\]# id sanjay
    uid=1002 (sanjay) gid=1001(Linuxteam) groups=1001(Linuxteam)
    \[root@ip-172-31-37-171 ec2-user\]# \|

[^17]: #F
    #
    The COMMANDS section may have other options added to it.
    #
    # Allow root to run any commands anywhere
    oot
    ALL=(ALL)
    ALL
    # Allows members of the 'sys' group to run networking, software,
    service management apps and more.
    %sys ALL = NETWORKING, SOFTWARE, SERVICES, STORAGE, DELEGATING, PROCESSES, LOCATE, DRIVERS
    ## Allows people in group wheel to run all commands
    6wheel ALL=(ALL)
    ALL
    #
    Same thing without a password
    %wheel
    ALL=(ALL)
    NOPASSWD : ALL

[^18]: ## Allow root to run any commands anywhere
    root
    ALL=(ALL)
    ALL
    ## Allows members of the 'sys' group to run networking, software,
    ## service management apps and more.
    #
    %sys ALL = NETWORKING, SOFTWARE, SERVICES, STORAGE, DELEGATING, PROCESSES, LOCATE, DRIVERS
    ## Allows people in group wheel to run all commands
    %wheel ALL=(ALL)
    ALL
    %Linuxteam ALL=(ALL)
    ALL

[^19]: \[root@ip-172-31-37-171 ec2-user\]# vi /etc/ssh/sshd_config

[^20]: # To disable tunneled clear text passwords, change to no here!
    #PasswordAuthentication yes
    #PermitEmptyPasswords no
    PasswordAuthentication no

[^21]: # To disable tunneled clear text passwords, change to no here!
    #PasswordAuthentication yes
    #PermitEmptyPasswords no
    PasswordAuthentication yes

[^22]: \[root@ip-172-31-37-171 ec2-user\]# systemct1 restart sshd
    \[root@ip-172-31-37-171 ec2-user\]#

[^23]: IP
    \[root@ip-172-31-37-171 ec2-user\]# passwd satya
    Changing password for user satya.
    New password:
    BAD PASSWORD: The password fails the dictionary check - it is too simplistic/systematic
    Retype new password:
    passwd: al1 authentication tokens updated successfully.
    \[root@ip-172-31-37-171 ec2-user\]#
    \[root@ip-172-31-37-171 ec2-user\]# passwd sanjay
    changing password for user sanjay.
    New password:
    BAD PASSWORD: The password fails the dictionary check - it is too simplistic/systematic
    Retype new password:
    passwd: al1 authentication tokens updated successfully.
    \[root@ip-172-31-37-171 ec2-user\]# \|

[^24]: chowd@chowdary MINGW64
    $ cd /e/awsdevops /keys /
    chowd@chowdary MINGW64 /e/awsdevops /keys
    chowd@chowdary MINGW64 /e/awsdevops /keys
    $ ssh sanjay@54 . 224 . 185 . 251
    sanjay@54 . 224 . 185 . 251's password:
    #
    ####.
    Amazon Linux 2
    # # ##;
    ###
    AL2 End of Life is 2025-06-30.
    #/
    V\~
    A newer version of Amazon Linux is available!
    Amazon Linux 2023, GA and supported until 2028-03-15.
    https ://aws . amazon . com/linux/amazon-linux-2023/
    \[sanjay@ip-172-31-37-171 \~\] $
    \[sanjay@ip-172-31-37-171 \~\]$
    in.
    175.
    31-37-171

[^25]: sanjay@ip-172-31-37-171 \~\]$ sudo yum install git -y
    sudo\] password for sanjay:
    oaded plugins: extras_suggestions, langpacks, priorities, update-motd
    amzn2-core
    ackage git-2. 40.1-1. amzn2 . 0.1.x86_64 already installed and latest version
    Nothing to do
    sanjay@ip-172-31-37-171 \~\]$
    sanjay@ip-172-31-37-171 \~\] $

[^26]: ## Allow root to run any commands anywhere
    root
    ALL=(ALL)
    ALL
    ## Allows members of the 'sys' group to run networking, software,
    ## service management apps and more.
    #
    %sys ALL = NETWORKING, SOFTWARE, SERVICES, STORAGE, DELEGATING, PROCESSES,
    ## Allows people in group wheel to run al1 commands
    %wheel ALL=(ALL)
    ALL
    %Linuxteam ALL=(ALL)
    ALL
    %devops ALL=(ALL) /usr/bin/yum, /usr/bin/systemct1
    ## Same thing without a password
    #
    %wheel
    ALL=(ALL)
    NOPASSWD : ALL

[^27]: \[satya@ip-172-31-37-171 \~\]$ sudo yum install git -y
    We trust you have received the usual lecture from the local System
    Administrator. It usually boils down to these three things:
    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.
    \[sudo\] password for satya:
    Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
    amzn2-core
    \| 3.6 k
    Resolving Dependencies
    > Running transaction check
    > Package git. x86_64 0:2. 40. 1-1. amzn2 . 0.1 will be installed
    Processing Dependency: git-core = 2. 40.1-1. amzn2. 0.1 for package: git-2. 40.1-1. amzn2 . 0.1.x86_64
    Processing Dependency: git-core-doc = 2.40.1-1. amzn2 .0.1 for package: git-2. 40.1-1. amzn2 .0.1. x86_64
    Processing Dependency: per1-Git = 2. 40.1-1. amzn2 . 0.1 for package: git-2. 40.1-1. amzn2 . 0. 1. x86_64
    Processing Dependency: per1(Git) for package: git-2. 40.1-1. amzn2 . 0.1. x86_64
    Processing Dependency: per1(Term: : Readkey) for package: git-2. 40.1-1. amzn2. 0.1.x86_64
    Running transaction check
    Package git-core. x86_64 0:2. 40. 1-1. amzn2 . 0.1 will be installed
    Package git-core-doc . noarch 0:2. 40.1-1. amzn2 . 0.1 will be installed
    Package per1-Git. noarch 0:2.40.1-1. amzn2 . 0.1 will be installed
    Processing Dependency: per1(Error) for package: per1-Git-2. 40.1-1. amzn2 . 0. 1. noarch
    > Package per1-TermReadKey . x86_64 0:2. 30-20. amzn2 . 0.2 will be installed
    Running transaction check
    Package per1-Error . noarch 1:0.17020-2. amzn2 will be installed

[^28]: \[satya@ip-172-31-37-171 \~\]$ sudo systemctl stop nginx
    \[satya@ip-172-31-37-171 \~\]$ systemctl status nginx
    nginx. service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: inactive (dead)

[^29]: \[satya@ip-172-31-37-171 \~\]$ sudo systemctl start nginx
    \[satya@ip-172-31-37-171 \~\]$ systemctl status nginx
    nginx. service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: active (running) since Fri 2023-12-01 13:25:38 UTC; 6s ago
    Process: 652 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 647 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 646 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0/SUCCESS)
    Main PID: 654 (nginx)
    CGroup: /system.slice/nginx. service
    -654 nginx: master process /usr/sbin/nginx
    655 nginx: worker process

[^30]: \[satya@ip-172-31-37-171 \~\]$ sudo useradd madhu
    Sorry, user satya is not allowed to execute
    "/sbin/useradd madhu' as root on ip-172-31-37-171. ec2. internal.
    \[satya@ip-172-31-37-171 \~\] $
    \[satya@ip-172-31-37-171 \~\] $

[^31]: yodevops
    ALL =(ALL)
    /usr /bin/yum, /usr/bin/systemct1

[^32]: \[satya@ip-172-31-37-171 \~\]$ sudo useradd madhu
    \[sudo\] password for satya:
    Sorry, user satya is not allowed to execute ' /sbin/useradd madhu' as root on ip-172-31-37-171.ec2. internal.
    \[satya@ip-172-31-37-171 \~\] $
    \[satya@ip-172-31-37-171 \~\]$ sudo systemctl start nginx
    \[sudo\] password for satya:
    \[satya@ip-172-31-37-171 \~\]$ systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: active (running) since Fri 2023-12-01 13:25:38 UTC; 13min ago
    Process: 652 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 647 ExecStartPre=/usr /sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 646 ExecStartPre=/usr/bin/rm -f /run/nginx. pid (code=exited, status=0/SUCCESS)
    Main PID: 654 (nginx)
    CGroup: /system . slice/nginx. service
    654 nginx: master process /usr/sbin/nginx
    655 nginx: worker process
    Warning: Journal has been rotated since unit was started. Log output is incomplete or unavailable.
    \[satya@ip-172-31-37-171 \~\]$ sudo systemctl stop nginx
    \[satya@ip-172-31-37-171 \~\]$ systemctl status nginx
    nginx. service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: inactive (dead)
    tvadip-172-31-37-171

[^33]: \[root@ip-172-31-37-171 ec2-user\]# cd /etc/sudoers.d-
    \[root@ip-172-31-37-171 sudoers . d\]# 1s -1 -
    total 8
    -r--r-
    1 root root 139 Dec 1 10:38 90-cloud-init-users
    -rw-r--r-- 1 root root 54 Dec 1 13:36 devops
    \[root@ip-172-31-37-171 sudoers . d\]#
    \[root@ip-172-31-37-171 sudoers . d\]# rm -rf devops-
    \[root@ip-172-31-37-171 sudoers . d\]# 1s -1
    total 4
    1 root root 139 Dec 1 10:38 90-cloud-init-users
    otai
    172-31-37-7
    -171
    udoe
    I

[^34]: User Privilege Lines
    The fourth line, which dictates the root user's sudo privileges, is different from the preceding lines
    Let's take a look at what the different fields mean:
    root ALL-(ALL: ALL) ALL The first field indicates the username that the rule will apply to
    (root).
    foot
    ALL
    (ALL:ALL) ALL
    The first "ALL" indicates that this rule applies to all hosts.
    root ALL=( ALL : ALL) ALL This "ALL" indicates that the root user can run commands as all
    users.
    . root ALL-(ALL: ALL ) ALL This "ALL" indicates that the root user can run commands as all
    groups.
    . root ALL-(ALL: ALL) ALL The last "ALL" indicates these rules apply to all commands.
    This means that our root user can run any command using sudo , as long as they provide their
    password.

[^35]: Frontend
    Backend
    DB
    Application
    Application
    Server
    C
    Load
    Balancer
    DB
    Server
    Frontend
    Backend
    Application
    Application
    RAW Data
    RAW Items
    Serveds
    Apache
    HTML
    Middleware
    MSSQL
    Nginx
    JS
    My SQL
    IIS
    ReactJS
    Jboss
    .Java
    Tomcat
    NOSQL
    Angular JS
    .NET
    Elastic Search
    NodeJS
    Weblogic
    Web Sphere
    Python
    Redi
    code

[^36]: Roboshop Architecture
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

[^37]: WEB TIER:
    . Usually web tier is the one which has frontend technologies like HTML, CSS, Java Script (React/Angular/Node).
    . We use web server to deploy these kind of applications.
    . Earlier Apache Server was popular, Now Nginx is the most popular web server.
    APP TIER:
    . APP/API Tier is the one which has backend technologies like Java, .NET, Python, Go, Php, etc.
    . Earlier Backend technologies had servers like tomcat, Jboss, IIS, etc.
    . Now all backend technologies are coming up with in built servers.
    . Usually API tier should not opened through internet, it should be only accessible through web tier.
    DB TIER:
    . Storage of the applications will be here like user data, products, orders data, etc.
    . We can use RDBMS like MySQL, MSSQL, Postgress, etc for row and column based data.
    . We can use NoSQL databases like MongoDB for storing the product information.
    . We can use Cache servers like Redis to access the data with lightening speed.
    . We can use MQ Servers like RabbitMQ, ActiveMQ, Kafka, etc for asynchronous communication.

