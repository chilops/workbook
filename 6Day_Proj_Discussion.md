---
title: 6Day_Proj_Discussion
uuid: e78beeda-0e8c-11ef-9be8-a6f126245c9e
version: 131
created: '2024-05-10T10:49:40+05:30'
tags:
  - roboshop-project
---

***Topics:***

1. *<mark style="background-color:#f8d616;">Public & Private IP's<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Monolithic Vs Microservices<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Security Groups<!-- {"backgroundCycleColor":"25"} --></mark>*

\

# *<mark style="background-color:#f8914d;">**Public & Private IP:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

![4ebae68f-de2f-4a54-96c4-00aec51cbf21.png|582](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/4ebae68f-de2f-4a54-96c4-00aec51cbf21.png) [^1]

 

![5fb052a0-800d-47f0-8cce-aa037070bfda.png|769.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/5fb052a0-800d-47f0-8cce-aa037070bfda.png) [^2]

 

 

 

![a18aba95-6e9d-4107-8db6-49608b046b5b.png|817.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/a18aba95-6e9d-4107-8db6-49608b046b5b.png) [^3]

 

![16ffa7d5-5dda-469a-b477-e7f998a653bb.png|679](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/16ffa7d5-5dda-469a-b477-e7f998a653bb.png) [^4]

 

 

 

# *<mark style="background-color:#f8914d;">**Monolithic Vs Microservices:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

![81949ccf-cc4d-47a7-9fd7-18228c282947.png|651](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/81949ccf-cc4d-47a7-9fd7-18228c282947.png) [^5]

 

![56e7fdda-923a-4302-a292-ed488c6e4ace.png|758.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/56e7fdda-923a-4302-a292-ed488c6e4ace.png) [^6]

 

![e5868ea0-6f85-4cd1-8a29-701fc08de3ef.png|483](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/e5868ea0-6f85-4cd1-8a29-701fc08de3ef.png) [^7]

 

 

*After 2016 backend server got issues due to heavy usage started **in application like fb, whatsup, banking apps etc(due to data got cheaper by JIO)***

 

![7dc807eb-d623-4f54-b725-3777861e13e3.png|847.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/7dc807eb-d623-4f54-b725-3777861e13e3.png) [^8]

 

 

*<mark style="background-color:#f3de6c;">**To come over from above issue, Now they came with below solution which is also known as microservices(not complete)**<!-- {"backgroundCycleColor":"14"} --></mark>*

 

*When any changes needed in code, then we can change code in only products or etc.*

 

*Maintenance is easy.*

*Language can be anything like python, java etc for build code.*

*Individual deployments*

*Servers resources can be used as per requirement (amazon great india festival or Big billion day sales)*

 

*User can be - java*

*Product - nodejs*

*Payment - python language*

 

![cbabf2fb-9534-46d2-aa47-c512d7b761ff.png|646](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/cbabf2fb-9534-46d2-aa47-c512d7b761ff.png) [^9]

 

***Auto scaling is very easy***

 

![fbd56b02-1fbf-46c8-b019-0959ee05ddea.png|768](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/fbd56b02-1fbf-46c8-b019-0959ee05ddea.png) [^10]

 

 

# *<mark style="background-color:#f8914d;">**Security Groups: **<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![c5d522ff-647a-4927-ab0d-ae6d9d4ab3ab.png|792.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/c5d522ff-647a-4927-ab0d-ae6d9d4ab3ab.png) [^11]

 

 

***Creating a security groups: (nothing but firewalls)***

![cda5ab71-28fa-4a56-afa8-e6ffbf55ab1d.png|458](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/cda5ab71-28fa-4a56-afa8-e6ffbf55ab1d.png) [^12]

 

 

***Now we are going to test communication backend payment server only to frontend server***

***(We are testing this because we don’t need our backend server communicate to outside world)***

 

![f9ba7056-0799-4b1f-88bd-80a8e443240f.png|845.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/f9ba7056-0799-4b1f-88bd-80a8e443240f.png) [^13]

 

 

 

 

***Http - port 80 I am using this because I am testing with Nginx server (As its for frontend server it can give anywhere) .***

***SSH - port 22 - using to login to that server. SSH should be local (my personal laptop or company IP range).***

 

![7aafefac-17d3-4006-9da9-e5122e88b72f.png|795.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/7aafefac-17d3-4006-9da9-e5122e88b72f.png) [^14]

 

 

***Create an instance by assigning new frontend_SG***

![44417058-386b-4a29-b5f5-d76a4df57d2e.png|792.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/44417058-386b-4a29-b5f5-d76a4df57d2e.png) [^15]

 

*<mark style="background-color:#f8914d;">**Installing Nginx on frontend server:**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

```
sudo amazon-linux-extras install nginx1
```

```
sudo systemctl start nginx
```

![984bfe86-f587-43ad-856f-9d8cd46ef07b.png|869.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/984bfe86-f587-43ad-856f-9d8cd46ef07b.png) [^16]

 

```
sudo systemctl start nginx
```

```
systemctl status nginx
```

 

![6e270305-105e-4041-b918-4742dad39721.png|847.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/6e270305-105e-4041-b918-4742dad39721.png) [^17]

 

![27d469e7-c15e-42fb-af9f-be4a3dccd05a.png|847.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/27d469e7-c15e-42fb-af9f-be4a3dccd05a.png) [^18]

 

 

\

***Now creating a security group for backend server: (No inbound rules given for now will add later).***

 

![bd9a20a8-37d2-4ec3-b7e4-8e9c26a62f8a.png|745.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/bd9a20a8-37d2-4ec3-b7e4-8e9c26a62f8a.png) [^19]

 

 

***Create backend server which is used for payments(select security group -backend_SG_payments)***

 

![4a348fcc-9cec-49f4-97ea-5e969b7805bb.png|752.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/4a348fcc-9cec-49f4-97ea-5e969b7805bb.png) [^20]

 

 

***Updating Backend_SG_payments security group: only SSH port enabling:***

 

![350880a2-7e84-44bb-a2ae-29bb28195f33.png|771.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/350880a2-7e84-44bb-a2ae-29bb28195f33.png) [^21]

 

![964afc15-f514-4b78-afe5-ce9f2ae829c5.png|776.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/964afc15-f514-4b78-afe5-ce9f2ae829c5.png) [^22]

 

 

***Connect to backend payment server using SSH***

![90f95d08-b2cc-4dfa-a8b2-f23018dc7ce4.png|735](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/90f95d08-b2cc-4dfa-a8b2-f23018dc7ce4.png) [^23]

 

![bc4b6cd0-0510-496b-80cb-7e397f027d3a.png|356](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/bc4b6cd0-0510-496b-80cb-7e397f027d3a.png) [^24]

 

***Telnet <destination IP> portno***

```
telnet 3.100.33.103 8080
```

```
netstat -lntp
```

 

 

***To test here - think backend app is working with port 80.***

\

```
sudo amazon-linux-extras install nginx1     --> installing nginx server in backend application payment server.
```

```
sudo systemctl start nginx
```

```
systemctl status nginx
```

 

![23aa8327-bc9c-44e2-9d05-3910fc8807b9.png|852.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/23aa8327-bc9c-44e2-9d05-3910fc8807b9.png) [^25]

 

***Now update backend SG payment group with tcp port 80***

![c638c6b0-b723-4ab1-8411-9d5663a283eb.png|885.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/c638c6b0-b723-4ab1-8411-9d5663a283eb.png) [^26]

 

```
netstat -lntp      --> in backend server
```

***Telnet <destination IP> portno***

```
telnet 3.100.33.103 80    --> in frontend server
```

 

![026ea12d-5c11-4adb-b95a-2ae4a57bc2cd.png|773.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/026ea12d-5c11-4adb-b95a-2ae4a57bc2cd.png) [^27]

 

![3f954790-2f37-4e40-86bb-bd489e22409a.png|771](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/3f954790-2f37-4e40-86bb-bd489e22409a.png) [^28]

 

 

***Now I want only backend server should communicate only with frontend server***

***Select only frontend SG in backendSG***

![4e8064f7-02ce-411e-b86e-7e9ceea5b4ec.png|691.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/4e8064f7-02ce-411e-b86e-7e9ceea5b4ec.png) [^29]

 

 

![9e1a9bc3-7347-4dbe-9eb5-b8519f4afe9e.png|688.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/9e1a9bc3-7347-4dbe-9eb5-b8519f4afe9e.png) [^30]

 

***Now it won't communicate to outside world & it will only communicate with frontend server only.***

![08cb8aa9-df40-4f54-af67-265341038eea.png|745.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/08cb8aa9-df40-4f54-af67-265341038eea.png) [^31]

 

![3ccf5287-3d74-4e2a-91d9-66072fb1c593.png|658](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/3ccf5287-3d74-4e2a-91d9-66072fb1c593.png) [^32]

 

 

***Now its communicated with only frontend server (only with private IP)***

![c8cbdef6-bce7-4c08-a879-454227f00c57.png|683.3333740234375](https://images.amplenote.com/e78beeda-0e8c-11ef-9be8-a6f126245c9e/c8cbdef6-bce7-4c08-a879-454227f00c57.png) [^33]

[^1]: 192 . 168.1.3 --> IP
    192. 168 .29.160 --> My private IP
    192 . 168 . 29.1 -->
    Modem
    2power32 -->
    NAT --> Network Address Translation
    My Home pulbic IP: 49. 43. 243. 168
    with in the network private IP
    latency: time to respond --> slow
    security :
    cost: data charges

[^2]: . . .
    ISP
    Public
    Private
    AirTel
    -

[^3]: Submarine Cable Map
    The Submarine Cable Map is a free and regularly updated
    Arctic Ocean
    Arctic Ocean
    Arctic Ocean
    resource from TeleGeography.
    Sponsored by
    AQUACOMMS
    Q Search by cable, landing, country, year ...
    Greenland
    Submarine Cables
    Russia
    Russia
    2Africa
    ACS Alaska-Oregon Network (AKORN)
    Mongolia
    Mongolia
    Aden-Djibouti
    North
    United States
    North
    China
    Pacific
    Alland
    Pacific
    astan
    Ocean
    Adria-1
    AEC-1
    Africa-1
    Africa Coast to Europe (ACE)
    Indian
    South
    South
    Ocean
    South
    Airraq
    Pacific
    Atlantic
    Pacific
    Ocean
    Ocean
    Ocean
    Alaska United East (AU-East)
    Alaska United Southeast (AU-SE)
    Alaska United Turnagain Arm (AUTA)
    Southern
    Ocean
    Alaska United West (AU-West)
    Win a Free Wall Map
    Southern
    Southern
    Ocean
    Ocean
    ALBA-1

[^4]: DNS --> Domain name system
    amazon . us --> IP address
    not in our home network
    not in jio network
    exchange point --> TATA, Airtel,
    cables --> go to us
    us

[^5]: Frontend Server
    Backend Server
    DB Server
    KIOSK

[^6]: Monolithic vs Microservices
    2012 TCS
    enterprise archive file --> this in only file of entire project
    Servlets --> DB connect data
    JSPS --> UI
    I
    small change is also a big release
    - - ----
    - - ------
    change management team
    they will do document --> client --> approve
    DEV --> QA --> UAT --> PROD

[^7]: FrontEnd --> Backend
    HTML, JS, AngularJS
    Java
    2 files
    frontend
    backend
    maintainance easy

[^8]: Backend
    - - - - -
    1 file --> user, cart, products, payment, order, dispatch
    50 members
    products related code need to be changed. ...
    2 weeks
    - - -
    a change in product display
    a change in payment display
    a single failure also --> total failure
    java/. net

[^9]: User
    Products
    Frontend Server
    payment

[^10]: User
    User
    User
    Java
    Products
    Products
    Products
    Products
    Frontend Server
    NodeJS
    payment
    payment
    Python

[^11]: User
    User
    User
    Java
    Products
    Frontend Server
    Products
    Products
    Products
    Web
    Android
    ios
    NodeJS
    payment
    payment
    Python

[^12]: Frontend Server
    Web
    User
    Android
    IOS

[^13]: Security Groups (2) Info
    C
    Actions
    Export security groups to CSV
    Create security group
    Q Find resources by attribute or tag
    < 1
    O
    Name
    Security group ID
    Security group name
    VPC ID
    Description
    SG1_Allow-All
    sg-Od20035c3943d6a29
    SG1_Allow-All
    vpc-0817cae89b8304c06 \[
    Allowing all traffic for a pract
    sg-029974043a4090491
    default
    vpc-0817 cae8968304c06 \[
    default VPC security group

[^14]: Security group name Info
    Frontend_SG
    Name canno
    d after creation.
    Description Info
    This is frontend SG, which can allow public servers or users
    VPC Info
    vpc-0817cae89b8304c06
    Inbound rules Info
    Type Info
    Protocol Info
    Port range Info
    Source Info
    Description - optional Info
    HTTP
    TCP
    80
    Anywh...
    Q
    Delete
    0.0.0.0/0 X
    SSH
    TCP
    22
    My IP
    Q
    Delete
    106.51.167.88/32 X
    Add rule

[^15]: Instances (1/1) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    V
    Q Find Instance by attribute or tag (case-sensitive)
    1 >
    V
    Name _
    Instance ID
    Instance state
    4
    Instance type
    Status check
    Alarm status
    Availability Zone
    4
    Public IPV4 DNS
    V
    Frontend_Server
    i-080da800598fb3aa7
    Running
    t2.micro
    Initializing
    No alarms
    +
    us-east-1a
    ec2-54-91-14-16
    E
    Instance: i-080da800598fb3aa7 (Frontend_Server)
    X
    Details
    Security
    Networking
    Storage
    Status checks
    Monitoring
    Tags
    Security details
    IAM Role
    Owner ID
    Launch time
    7 158724841371
    Mon Dec 04 2023 18:06:09 GMT+0530 (India Standard Time)
    Security groups
    sg-020b9258c6db847af (Frontend_SG)
    Inbound rules
    Q Filter rules
    Name
    Security group rule ID
    Port range
    Protocol
    Source
    Security groups
    sgr-032733f91 10786a76
    80
    TCP
    0.0.0.0/0
    Frontend_SG Z
    sgr-03e017f4da6dacbf0
    22
    TCP
    106.51.167.88/32
    Frontend_SG \[
    Outbound rules
    Q Filter rules
    1
    >

[^16]: \[ec2-user@ip-172-31-44-18 \~\]$ sudo amazon-linux-extras install nginxl
    Installing nginx
    Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
    Cleaning repos: amzn2-core amzn2extra-docker amzn2extra-kernel-5.10 amzn2extra-nginx1
    17 metadata files removed
    6 sqlite files removed
    0 metadata files removed
    Loaded plugins: extras suggestions, langpacks, priorities, update-motd
    amzn2-core
    3.6 KB 00:00:00
    amzn2extra-docker
    2.9 KB
    00: 00:00
    amzn2extra-kernel-5. 10
    3.0 KB
    00 : 00:00
    amzn2extra-nginx1
    2.9 KB
    00: 00: 00
    (1/9) : amzn2-core/2/x86_64/group_gz
    2. 7 kB
    00: 00:00
    (2/9) : amzn2-core/2/x86 64/updateinfo
    742 KB
    00 : 00: 00

[^17]: \[ec2-user@ip-172-31-44-18 \~\]$ sudo systemctl start nginx
    \[ec2-user@ip-172-31-44-18 \~\]$ systemctl status nginz
    Unit nginz . service could not be found.
    \[ec2-user@ip-172-31-44-18 \~\]$ sudo systemctl start nginx
    \[ec2-user@ip-172-31-44-18 \~\]$ systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: active (running) since Mon 2023-12-04 12:47:31 UTC; 19s ago
    Process: 3472 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 3468 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 3467 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0 /SUCCESS)
    Main PID: 3474 (nginx)
    CGroup: /system . slice/nginx . service
    -3474 nginx: master process /usr/sbin/nginx
    3475 nginx: worker process
    Dec 04 12:47:31 ip-172-31-44-18. ec2. internal systemd\[1\] : Starting The nginx HTTP and reverse proxy s
    Dec 04 12:47:31 ip-172-31-44-18. ec2. internal nginx \[3468\]: nginx: the configuration file /etc/nginx/n
    Dec 04 12:47:31 ip-172-31-44-18. ec2. internal nginx \[3468\]: nginx: configuration file /etc/nginx/nginx.
    Dec 04 12:47:31 ip-172-31-44-18. ec2. internal systemd \[1\] : Started The nginx HTTP and reverse proxy se
    Hint: Some lines were ellipsized, use -1 to show in full.
    \[ec2-user@ip-172-31-44-18 \~\]$

[^18]: daws-76s/notes
    X
    Instances \| EC2 \| us-east-1
    X
    Welcome to nginx!
    X
    G
    Not secure 54.91.14.162
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^19]: Create security group info
    A security group acts as a virtual firewall for your instance to control inbound and outbound traffic. To create a new security group, complete the fields below.
    Basic details
    Security group name Info
    Backend_SG_payment
    Name cannot be edited after creation.
    Description Info
    This SG is created for payments, public is not allowed to connect directly
    VPC Info
    vpc-0817cae8968304c06
    Inbound rules Info
    This security group has no inbound rules.
    Add rule
    Outbound rules Info
    Type Info
    Protocol Info
    Port range Info
    Destination Info
    Description - optional Info
    All traffic
    Custom
    Delete

[^20]: Instances (1/2) Info
    G
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    < 1 >
    -
    Name _
    4
    Instance ID
    Instance state
    A
    Instance type
    4
    Status check
    Alarm status
    Availability Zone
    Publi
    BackendServer_payments
    i-098cab9e06524622a
    Pending
    t2.micro
    Initializing
    No alarms +
    us-east-1a
    ec2-3
    Frontend_Server
    i-080da800598fb3aa7
    Running
    Q Q
    t2.micro
    2/2 checks passed No alarms +
    us-east-1a
    ec2-5
    Instance: i-098cab9e06524622a (BackendServer_payments)
    X
    Details
    Security
    Networking
    Storage
    Status checks
    Monitoring
    Tags
    Security details
    IAM Role
    Owner ID
    Launch time
    7 158724841371
    Mon Dec 04 2023 18:26:50 GMT+0530 (India Standard Time)
    Security groups
    sg-Ofa371a4b89ab653a (Backend_SG_payment)
    Inbound rules
    O Filter rules
    < 1
    >
    Name
    Security group rule ID
    Port range
    Protocol
    Source
    Security groups
    No rules to display
    Outbound rules

[^21]: EC2 > Security Groups > sg-Ofa371a4b89ab653a - Backend_SG_payment > Edit inbound rules
    Edit inbound rules info
    Inbound rules control the incoming traffic that's allowed to reach the instance.
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info
    Port range Info
    Source Info
    Description - optional Info
    SSH
    TCP
    22
    My IP
    Q
    Delete
    106.51.167.88/32 X
    Add rule
    Cancel
    Preview changes
    Save rules

[^22]: Instances (1/2) Info
    C
    Connect
    Instance state
    Actions V
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    < 1
    Name _
    4
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Alarm status
    Availability Zone
    4
    Publi
    BackendServer_payments
    i-098cab9e06524622a
    Running
    t2.micro
    2/2 checks passed No alarms
    +
    us-east-1a
    ec2-3
    O
    Frontend_Server
    i-080da800598fb3aa7
    Running
    Q Q
    t2.micro
    2/2 checks passed No alarms
    +
    us-east-1a
    ec2-5
    Instance: i-098cab9e06524622a (BackendServer_payments)
    X
    Details
    Security
    Networking
    Storage
    Status checks
    Monitoring
    Tags
    Security details
    IAM Role
    Owner ID
    Launch time
    7 158724841371
    Mon Dec 04 2023 18:26:50 GMT+0530 (India Standard Time)
    Security groups
    sg-Ofa371a4b89ab653a (Backend_SG_payment)
    Inbound rules
    Q Filter rules
    < 1
    Name
    Security group rule ID
    Port range
    Protocol
    Source
    Security groups
    sgr-049f45bf0Of487039
    22
    TCP
    106.51.167.88/32
    Backend_SG_payment \[
    Outbound rules
    Q Filter rules

[^23]: Commands
    54.91.14.162
    3.81.36.97
    \[ec2-user@ip-172-31-36-0 \~\] $
    \[ec2-user@ip-172-31-36-0 \~\]$

[^24]: Security groups
    frontend apps --> 80
    backend apps --> 8080

[^25]: \[ec2-user@ip-172-31-36-0 \~\]$ sudo amazon-linux-extras install nginx1
    Installing nginx
    Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
    Cleaning repos: amzn2-core amzn2extra-docker amzn2extra-kernel-5.10 amzn2extra-nginx1
    17 metadata files removed
    6 sqlite files removed
    0 metadata files removed
    Loaded plugins: extras suggestions, langpacks, priorities, update-motd
    amzn2-core
    \| 3.6 KB
    00 : 00: 00
    amzn2extra-docker
    2.9 KB
    00: 00: 00
    amzn2extra-kernel-5 .10
    3.0 kB
    00: 00: 00
    amzn2extra-nginx1
    2.9 KB
    00 : 00: 00
    (1/9) :
    re/2/x86 64
    .7 KB
    00 : 00 : 00

[^26]: EC2 > Security Groups > sg-Ofa3714b89ab653a - Backend_SG_payment > Edit inbound rules
    Edit inbound rules info
    Inbound rules control the incoming traffic that's allowed to reach the instance.
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info
    Port range Info
    Source Info
    Description - optional Info
    sgr-049f45bf0Of487039
    SSH
    TCP
    22
    Custom
    Q
    Delete
    106.51.167.88/32 X
    Custom TCP
    TC
    80
    Anywh...
    Q
    Delete
    0.0.0.0/0 X
    Add rule
    A Rules with source of 0.0.0.0/0 or :/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only.
    X
    Cancel
    Preview changes
    Save rules

[^27]: \[ec2-user@ip-172-31-36-0 \~\]$ netstat -Intp
    (No info could be read for "-p": geteuid ()=1000 but you should be root.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0. 0.0.0:22
    0.0.0.0:\*
    LISTEN
    tcp
    0 127 . 0 . 0.1:25
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0. 0:80
    0 . 0.0.0:\*
    LISTEN
    tcp6
    0 :::22
    : : :\*
    LISTEN
    tcp6
    0 :: :111
    : ::\*
    LISTEN
    tcp6
    0 : : :80
    LISTEN
    \[ec2-user@ip-172-31-36-0 \~\] $
    \[ec2-user@ip-172-31-36-0 \~\] $

[^28]: \[ec2-user@ip-172-31-44-18 \~\]$ telnet 3. 81.36.97 80
    Trying 3. 81.36.97. .
    Connected to 3. 81.36.97
    Escape character is '^\]'
    ^CConnection closed by foreign host.
    \[ec2-user@ip-172-31-44-18 \~1$

[^29]: EC2 > Security Groups > sg-Ofa371a4b89ab653a - Backend_SG_payment > Edit inbound rules
    Edit inbound rules info
    Inbound rules control the incoming traffic that's allowed to reach the instance.
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info
    Port range Info
    Source Info
    Description - optional Info
    sgr-049f45bf0Of487039
    SSH
    TCP
    22
    Custom
    Q sg-020b9258c6db847af X
    Delete
    106.51.167.88/32 X
    Custom TCP
    TCP
    80
    Custom
    Q sg-020b9258c6db847af X
    Delete
    sg-020b9258c6db847af X
    Add rule
    Cancel
    Preview changes
    Save rules

[^30]: EC2 > Security Groups > sg-Ofa371a4689ab653a - Backend_SG_payment
    sg-Ofa371a4b89ab653a - Backend_SG_payment
    Actions
    Details
    Security group name
    Security group ID
    Description
    VPC ID
    Backend_SG_payment
    sg-Ofa371a4689ab653a
    This SG is created for payments,
    vpc-0817cae89b8304c06 \[
    public is not allowed to connect directly
    Owner
    Inbound rules count
    Outbound rules count
    158724841371
    2 Permission entries
    1 Permission entry
    Inbound rules
    Outbound rules
    Tags
    Inbound rules (2)
    C
    Manage tags
    Edit inbound rules
    Q Search
    <
    ile...
    V
    IP version
    v Type
    4
    Protocol
    4
    Port range
    V
    Source
    4
    Descriptio
    f5deec
    HTTP
    TCP
    80
    sg-020b9258c6db847af / Frontend_SG
    187039
    IPV4
    SSH
    TCP
    22
    106.51.167.88/32

[^31]: daws-76s/notes
    X Instances \| EC2 \| us-east-1
    x Welcome to nginx!
    X
    3.81.36.97
    X
    +
    X
    3.81.36.97
    Hmmm... can't reach this page
    3.81.36.97 took too long to respond
    Try:
    . Search the web for 3 81 36 97
    . Checking the connection

[^32]: Frontend Server
    Web
    User
    Android
    IOS
    80
    Frontend Server
    Web
    Android
    ios

[^33]: \[ec2-user@ip-172-31-44-18 \~\]$ telnet 172.31.36.0 80
    Trying 172. 31.36.0. ..
    Connected to 172 . 31 . 36.0.
    Escape character is "^j'.
    ^CConnection closed by foreign host.
    \[ec2-user@ip-172-31-44-18 \~1$

