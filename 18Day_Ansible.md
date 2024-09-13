---
title: 18Day_Ansible
uuid: 5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07
version: 164
created: '2024-05-11T13:07:45+05:30'
tags:
  - ansible
---

**Topics:**

1. <mark style="background-color:#f8d616;">Shell disadvantages<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Ansible - configuration Management tool<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">idempotance<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Ansible installation<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Modules<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Playbooks<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Inventory<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">XML, JSON, YAML<!-- {"backgroundCycleColor":"25"} --></mark>

\

# <mark style="background-color:#f8914d;">**shell disadvantages**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

1\. shell script will not work in all linux distros.

2\. scalability --> difficult to manage more no of servers

3\. error handling and validations, need to manual

4\. readability issues

5\. shell will only work for linux, will not work with external systems

\

\

# <mark style="background-color:#f8914d;">**Ansible -**<!-- {"backgroundCycleColor":"24"} --></mark>  <mark style="background-color:#fff;">**Its a configuration Management tool**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

 

**Ex** - Configure your laptop - when you buy a new laptop we need to setup many things like - installing new software's, anti-virus etc..

 

To make server ready for application deployment is called configuring server

 

Ansible is an open-source automation tool used for

- Configuration management

- Application deployment

\]1. stop the server

2\. remove old code

3\. download new code

4\. restart server

- Cloud provisioning and orchestration(But not recommended)

**What is configuration?**

Before deploying the application we need to make the server ready. For example

- Installing packages

- Installing Programming languages

- Installing build tools.

- Installing Application Runtime.

- Creation of users, folders, etc.

- Setting permissions.

- Creation of systemctl services.

 

As a DevOps engineer we need to do this effectively. Basically CRUD over the server.

Creation of configuration --> should be fast and accurate

Update the configuration --> any changes in configuration should be rolled out asap.

Delete the configuration --> delete the configuration if not required.

Read the configuration --> it is easy to read the configuration of server through ansible playbooks.

**Disadvantages of shell**

- Does your shell script can work with all distributions? because command may change based on distribution.

- Suppose on big billion day we have 1000 servers. How can we configure servers?

- Is shell scripting effective for error handling?

- Is shell scripting easy to understand and read?

- How to manage sensitive information in shell scripts?

- How to integrate shell script with external systems like AWS, Azure, etc.

**Ansible Features**

- Platform independent  -- a single code can be used in different OS's - RHEL, centos, ubuntu etc

- Scalable    - Ansible can manage 1000+ servers at a time, which Shellscripts can't do.

- Idempotence

- Error Handling

- Readable and maintainable

- Vault   - for password management etc

- Rich modules

- Agent less -

 

# <mark style="background-color:#f8914d;">Idempotence<!-- {"backgroundCycleColor":"24"} --></mark> - <mark style="background-color:#f8d616;">even you run your program infinite times, it should not create any damage<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"collapsed":true} -->

 

<mark style="background-color:#f8d616;">providing same result irrespective of no.of executions is called idempotence<!-- {"backgroundCycleColor":"25"} --></mark>

 

useradd ramesh

1\. it will create multiple ramesh users --> bad (shellscripts)

2\. it will try to create user, but got error and program exit --> no (shellscripts)

 

ansible --> if not exist it will create, if exist it will ignore --> yes

 

 

Ex:

Created 2 aws servers, 1- config server, 2 - node

 

![21a07ea3-d950-4712-9dd4-8d80ba73b582.png|731](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/21a07ea3-d950-4712-9dd4-8d80ba73b582.png) [^1]

 

![25764229-1245-454f-98ee-98fe112e05d7.png|687](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/25764229-1245-454f-98ee-98fe112e05d7.png) [^2]

 

Syn: sshpass -p "passsword ssh username@pubilcIPnode     

\-- Now we connected to node directly from configuration server

```
sshpass -p "DevOps321" ssh centos@54.235.14.240   
```

 

![a2e5a127-c220-4d21-8b42-4fcb5cf21f73.png|775](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/a2e5a127-c220-4d21-8b42-4fcb5cf21f73.png) [^3]

 

 -- The file hello.txt created on node

```c
sshpass -p "DevOps321" ssh centos@54.235.14.240 -C "echo Hello > /tmp.hello.txt"     
```

![c353e12d-51ec-47bc-b487-b70a5a5e3a6e.png|932.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/c353e12d-51ec-47bc-b487-b70a5a5e3a6e.png) [^4]

 

On a node file presents

![2dba47f6-304b-4a42-8a7f-26cf41a9f0dd.png|953.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/2dba47f6-304b-4a42-8a7f-26cf41a9f0dd.png) [^5]

 

 

Ansible Architecture:

![](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/bb81ccc1-19d3-43a8-aa28-31c47f8c4143.jpg) [^6]

 

**PUSH:**

1. Unlike pull there is no need of agent installation.

1. Whenever there is a change in configuration, server can push to the nodes directly.

1. Ansible uses SSH authentication to connect to the servers.

 

 

Delhi -- > Hyderabad -- > today  sent

 

Delhi -- > HYD DTDC

 

You going to HYD DTDC every day and ask for courier   --PULL concept

2nd day

3rd day

4th day

5th day -- > got courier

 

<mark style="background-color:#f8d616;">**Disadvantages**:<!-- {"backgroundCycleColor":"25"} --></mark>

traffic increases

fuel consumption

resources waste

time waste

 

 

HYD DTDC -- > deliver to home  --PUSH concept

\

# <mark style="background-color:#f8914d;">**Ansible installation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

```
sudo yum install ansible -y
```

![7c30df50-b322-4aeb-a10b-a99fcaf71ccd.png|791.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/7c30df50-b322-4aeb-a10b-a99fcaf71ccd.png) [^7]

 

Connecting to node from server:

Syn: ansible -I <node public IP>, all -e ansible_user=<username> ansible_password=<node psw> -m ping

 

\-- We are able to ping node from a server.

```
ansible -i 54.235.14.240, all -e ansible_user=centos -e ansible_password=DevOps321 -m ping    
```

 

![709a8f41-8228-4216-a070-34a12af8ac4e.png|849.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/709a8f41-8228-4216-a070-34a12af8ac4e.png) [^8]

 

 

Linux --> everything is called as command

ansible --> module/collection

 

To Install Nginx Module:

\-- become --> makes as root user, -m -- is a module

```
ansible -i 54.163.18.10, all -e ansible_user=centos -e ansible_password=DevOps321 --become -m yum -a "name=nginx state=present"              
```

 

![ee379754-8ce1-4ec9-a8b1-db910218de77.png|1076.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/ee379754-8ce1-4ec9-a8b1-db910218de77.png) [^9]

 

Its already installed means it shows in green color:

![f383a6bd-4e77-443c-af08-0c02147fdcfe.png|941.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/f383a6bd-4e77-443c-af08-0c02147fdcfe.png) [^10]

 

 

To start Nginx service

```
ansible -i 54.163.18.10, all -e ansible_user=centos -e ansible_password=DevOps321 --become -m service -a "name=nginx state=started"
```

![70120833-a4f9-491d-b0f5-0b6774da6385.png|819.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/70120833-a4f9-491d-b0f5-0b6774da6385.png) [^11]

 

\-To stop the service

```
ansible -i 54.163.18.10, all -e ansible_user=centos -e ansible_password=DevOps321 --become -m service -a "name=nginx state=stopped"    -
```

 --To restart

```
ansible -i 54.163.18.10, all -e ansible_user=centos -e ansible_password=DevOps321 --become -m service -a "name=nginx state=restarted"  
```

 

 

Now on node side Nginx service is running

![359c2151-b5b2-42ac-9b8d-665ba043fd6d.png|988.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/359c2151-b5b2-42ac-9b8d-665ba043fd6d.png) [^12]

 

![b0f8f791-4a41-47e6-b9cc-5860ff1c64bd.png|927.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/b0f8f791-4a41-47e6-b9cc-5860ff1c64bd.png) [^13]

 

 

# one by one module --> success/fail<!-- {"collapsed":true} -->

 

keep all modules/commands in a file

keep some validations, conditions, loops, variables

now run the file

 

Playbook --> a file of modules/collections

YAML --> yet another markup language

 

 

 

DTO --> data transfer object

\--------------------------------------

# XML --> Extensive Markup Language  (2008 older usage)<!-- {"collapsed":true} -->

 

<User>

<Email>info@joindevops.com</Email>

<Password>admin123</Password>

</User>

 

# JSON --> Java script object notation<!-- {"collapsed":true} -->

\----------------------------

 

{

"Emai": "info@joindevops.com",

"Password":"admin123"

}

 

# YAML<!-- {"collapsed":true} -->

\----------------------------

email: "info@joindevops.com"

password: "admin123"

 

YAML

![4849682b-9962-4751-b42c-4543d489fb35.png|730](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/4849682b-9962-4751-b42c-4543d489fb35.png) [^14]

 

 

# Ansible playbooks:<!-- {"collapsed":true} -->

Create a repo:

![8c962f2b-6dc7-4aac-a062-a6a09bd473c1.png|739.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/8c962f2b-6dc7-4aac-a062-a6a09bd473c1.png) [^15]

 

 

 

![a3d0273a-3e21-4038-b2ec-e7d7f6589f50.png|920.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/a3d0273a-3e21-4038-b2ec-e7d7f6589f50.png) [^16]

 

![76bb3e54-ee6a-4b06-a322-ba82ab8e5917.png|681](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/76bb3e54-ee6a-4b06-a322-ba82ab8e5917.png) [^17]

 

 

Ansible inventory file

![4aab937f-10d7-472b-b4c0-c98289afc1db.png|818.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/4aab937f-10d7-472b-b4c0-c98289afc1db.png) [^18]

 

```
git clone https://github. com/daws-76s/ansible.git
[ centos@ip-172-31-28-85 ~ ]$ cd ansible/
1s -1
ansible -i inventory web -- list-hosts
ansible -i inventory cart -- list-hosts
ansible -i inventory roboshop -- list-hosts
```

![fec90529-bd12-4e0f-a4bf-5c92a39629d8.png|845](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/fec90529-bd12-4e0f-a4bf-5c92a39629d8.png) [^19]

 

```
ansible -i inventory ungrouped -- list-hosts
```

![e2ec37c9-7f3a-44c6-94be-8e669d80d5dc.png|806](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/e2ec37c9-7f3a-44c6-94be-8e669d80d5dc.png) [^20]

 

```
ansible -i inventory all -- list-hosts
```

![5524920d-c2ef-48a4-8f73-fddbf2a8924a.png|847](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/5524920d-c2ef-48a4-8f73-fddbf2a8924a.png) [^21]

 

 

 

 

Ping playbook

![f2a924cb-f7f5-4c0e-8b51-db16b5e36b4b.png|708](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/f2a924cb-f7f5-4c0e-8b51-db16b5e36b4b.png) [^22]

```
 
git status
git add . ; git commit -m "playbook1"; git push origin main
git status
```

![c0738467-0ce2-483f-a1e6-08050afefead.png|825](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/c0738467-0ce2-483f-a1e6-08050afefead.png) [^23]

 

```
git clone https://github.com/chilops/Ansible.git 
1s
cd Ansible/
1s
 
```

![ae8c7e49-a160-42ef-b904-8e1bed1fe28e.png|909.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/ae8c7e49-a160-42ef-b904-8e1bed1fe28e.png) [^24]

 

 

 -- pinging web instance

```
ansible-playbook -i inventory.ini -e ansible_user=centos -- become -e ansible password=Devops321 1.pingplaybook. Yaml                      
```

 

![544bd21e-ce85-4359-a5e8-37685ed867ce.png|914.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/544bd21e-ce85-4359-a5e8-37685ed867ce.png) [^25]

 

 

 

Nginx install playbook

![10245d38-433e-4deb-98c6-b739e8adee71.png|457](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/10245d38-433e-4deb-98c6-b739e8adee71.png) [^26]

 

```
git status
git add . ; git commit -m "playbook2"; git push origin main
git status
```

 

![5f65ffb5-8128-482e-853f-c6304fdbc3d4.png|880](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/5f65ffb5-8128-482e-853f-c6304fdbc3d4.png) [^27]

 

```
-- Installing ngnix on web instanceansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 2.nginx.yaml      
```

![77455c57-086f-4df3-b1f9-c7b37172a6e1.png|929.3333740234375](https://images.amplenote.com/5c1aa2aa-0f69-11ef-9e6a-2e40d90dfe07/77455c57-086f-4df3-b1f9-c7b37172a6e1.png) [^28]

[^1]: Instances (1/2) Info
    C
    Connect
    Instance state
    Q Find Instance by attribute or tag (case-sensitive)
    -
    Name _
    4
    Instance ID
    Instance state
    Instance type
    Status check
    Alarm
    V
    server
    X
    i-02bbe4a7dd2c1d802
    Pending Q Q
    t2.micro
    No ala
    node
    i-Oac9cc0017549e 1f4
    Pending Q Q
    t2.micro
    No alar

[^2]: SuperPUTTY - server
    File View Tools Help
    Protocol SSH
    \* Host 54.235.14.240
    Login
    Password
    Session centos-8
    .OX
    Commands
    server
    node
    3. 89. 162.97 \| 172. 31.28.85 \| t2.micro \| null
    \[ centos@ip-172-31-28-85 \~ \]$

[^3]: server
    node
    3. 89. 162.97 \| 172. 31.28.85 \| t2.micro \| null
    \[ centos@ip-172-31-28-85 \~ \]$ sshpass -p "Devops321" ssh centos@54 . 235 . 14. 240
    Warning: Permanently added '54.235.14.240' (ECDSA) to the list of known hosts.

[^4]: SuperPUTTY - server
    File View Tools Help
    Protocol SSH
    Host 54.235.14.240
    Login
    Password
    Session centos-8
    . Ox
    Commands
    . 0\*95
    server
    node
    3. 89. 162.97 \| 172 . 31.28.85 \| t2.micro \| null
    \[ centos@ip-172-31-28-85 \~ \]$ sshpass -p "Devops321" ssh centos@54. 235.14.240 -C "echo Hello > /tmp/hello. txt"
    Warning: Permanently added '54. 235.14.240' (ECDSA) to the list of known hosts.
    3. 89. 162.97 \| 172. 31 .28.85 \| t2.micro \| null
    \[ centos@ip-172-31-28-85 \~ \]$

[^5]: server node
    54 . 235. 14.240 \| 172 . 31 .20.140 \| t2.micro \| null
    \[ centos@ip-172-31-20-140 /tmp \]$ 1s -1
    total 4
    -rw-rw-r--
    1 centos centos 6 Dec 20 02:06 hello. txt
    drwx-
    3 root
    root
    17 Dec 20 02:05 systemd-private-6ac9fecc002d4d12be0alle8c6065ca0-chronyd. service-InEBIx
    -rw-r--
    1 centos centos 0 Jun 4 2023 terraform 6722844.sh
    54 . 235. 14. 240 \| 172 . 31.20.140 \| t2.micro \| null
    \[ centos@ip-172-31-20-140 /tmp \]$ cat hello. txt
    Hello
    54 . 235. 14.240 \| 172. 31 . 20.140 \| t2.micro \| null
    \[ centos@ip-172-31-20-140 /tmp \] $

[^6]: PUSH ARCHITECTURE
    NODE-1
    Configuration
    NODE-2
    server
    NODE-3

[^7]: 3. 89. 162 .97 \| 172. 31.28.85 \| t2.micro \| null
    \[ centos@ip-172-31-28-85 \~ \]$ sudo yum install ansible -y
    Centos Stream 8 - AppStream
    26 MB/S \| 35 MB
    00 : 01

[^8]: \[ centos@ip-172-31-28-85 \~ \]$ ansible -i 54. 235. 14.240, all -e ansible user=centos -e ansible_password=Devops321 -m ping
    54 . 235 . 14 . 240 \| SUCCESS =>
    "ansible_facts": {
    "discovered interpreter_python": "/usr/libexec/platform-python"
    "changed" : false,
    "ping": "pong"

[^9]: \[ centos@ip-172-31-21-76 \~ \]$ ansible -i 54. 163.18.10, all -e ansible_user=centos -e ansible_password=Devops321 --become
    -m
    yum -a "name=nginx state=present"
    54 . 163 . 18. 10 \| CHANGED => {
    "ansible facts": {
    "discovered_interpreter_python": "/usr/libexec/platform-python"
    "changed": true,
    "msg" : ""
    "rc": 0,
    "results": \[
    "Installed: nginx-1:1.14.1-9. module_e18 . 0. 0+1060+3ab382d3.x86 64"
    "Installed: nginx-all-modules-1:1. 14.1-9. module_e18 . 0. 0+1060+3ab382d3. noarch",
    "Installed: libXpm-3. 5.12-11.e18.x86_64",
    "Installed: gd-2. 2.5-7. e18.x86_64",
    "Installed: nginx-filesystem-1: 1. 14.1-9.module_e18 . 0. 0+1060+3ab382d3. noarch",
    "Installed: libwebp-1. 0.0-9.e18.x86 64",
    "Installed: libtiff-4.0.9-31. e18.x86 64"
    "Installed: nginx-mod-http-image-filter-1: 1. 14.1-9. module_e18 . 0. 0+1060+3ab382d3.x86 64",
    "Installed: jbigkit-libs-2.1-14.e18.x86 64"

[^10]: \[ centos@ip-172-31-21-76 \~ \]$ ansible -i 54. 163.18.10, all -e ansible user=centos -e ansible_password=Devops321 --become
    -m
    yum -a "name=nginx state=present"
    54 . 163. 18. 10 \| SUCCESS =>
    "ansible facts": {
    "discovered_interpreter_python": "/usr/libexec/platform-python"
    "changed": false,
    "msg": "Nothing to do",
    "rc" : 0,
    "results": \[\]
    54 . 227. 54.185 \| 172. 31.21.76 \| t2.micro \| null
    \[ centos@ip-172-31-21-76 \~ \]$\]

[^11]: \[ centos@ip-172-31-21-76 \~ \]$ ansible -i 54. 163.18.10, all -e ansible_user=centos -e ansible_password=Devops321 --become
    -n
    service -a "name=nginx state=started"
    54 . 163. 18.10 \| CHANGED =>
    "ansible facts": {
    "discovered_interpreter_python": "/usr/libexec/platform-python"
    "changed": true,
    "name": "nginx",
    "state": "started",
    "status" :
    "ActiveEnterTimestampMonotonic": "(",
    "ActiveExitTimestampMonotonic": "(",
    "ActiveState": "inactive",
    "After": "remote-fs. target system. slice systemd-journald. socket sysinit. target basic. target network. target tmp.mour

[^12]: Server
    Node
    centos@ip-172-31-17-156 \~ \]$ systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; disabled; vendor preset: disabled)
    Active: active (running) since Mon 2024-04-29 05:08:49 UTC; 2min 10s ago
    Process: 7555 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 7553 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)
    Process: 7552 ExecStartPre=/usr/bin/rm -f /run/nginx.pid (code=exited, status=0/SUCCESS)
    Main PID: 7557 (nginx)
    Tasks: 2 (limit: 4398)
    Memory : 3. 6M
    CGroup: /system. slice/nginx. service
    7557 nginx: master process /usr/sbin/nginx

[^13]: Search
    Q
    v M Inbox (3,268) - info@joinc x \| \| Instances \| EC2 \| us-east-1 x \| () concepts/ansible.MD at x \| draw.io
    x A ansible.builtin.package m x \| G anisibe adhoc command : x \| <> Install and configure Ngir X
    Test Page for the Nginx H X
    +
    X
    A Not secure 54.235.14.240
    Welcome to nginx on Red Hat Enterprise Linux!
    This page is used to test the proper operation of the nginx HTTP server after it has been installed. If you can read this page, it means that the web server installed at this site is working properly.
    Website Administrator
    This is the default index.html page that is distributed with nginx on Red Hat Enterprise Linux. It is located in /usr/share/nginx/html.
    You should now put your content in a location of your choice and edit the root configuration directive in the nginx configuration file /etc/nginx/nginx. conf.
    For information on Red Hat Enterprise Linux, please visit the Red Hat, Inc. website. The documentation for Red Hat Enterprise Linux is available on the Red Hat, Inc. website.
    NGINX
    POWERED BY
    redhat.

[^14]: Concepts > ! person.yaml
    1
    name: sivakumar
    2
    dob: "2023-09-09"
    3
    address :
    4
    address-line1: vivek street
    15
    address- line2: sanath nagar
    16
    city : HYD
    17
    email: info@joindevops .com
    8
    9
    - name: ramesh
    10
    dob: "2022-09-08"
    11
    address :
    12
    address-line1: vivek street1
    13
    address-line2: sanath nagar1
    14
    city : HYD1
    15
    address-line1: vivek street2
    16
    address-line2: sanath nagar2
    17
    city : HYD2
    18
    email: info@joindevops . com

[^15]: G
    & https://github.com/new
    New repository
    Q Type to search
    +
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    chilops
    Ansible
    Ansible is available.
    Great repository names are short and memorable. Need inspiration? How about supreme-enigma ?
    Description (optional)
    Public
    Anyone on the internet can see this repository. You choose who can commit.

[^16]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/ansible
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/ansible/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/ansible (master)
    $ git remote add origin git@github.com:daws-76s/ansible .git

[^17]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/ansible (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/ansible (main)
    $

[^18]: EXPLORER
    . .
    person.xml U
    {} person.json 1, U
    ! person.yaml U
    = 01-playbook.yaml
    = inventory
    V REPOS
    ansible > = inventory
    > github
    1
    192 . 187. 56.20
    ansible
    2
    192. 187 . 56.30
    3
    = 01-playbook.yaml
    4
    \[web \]
    inventory
    15
    192. 187 . 56.3
    > concepts
    6
    192. 187 .56.4
    > notes
    7
    > roboshop-documentation
    8
    \[catalogue\]
    > roboshop-shell
    9
    192. 187 . 56.5
    > shell-script
    10
    192.187 . 56.6
    11
    > weekly-interview-questions
    12
    \[cart \]
    13
    192. 187 .56.7
    14
    192. 187 . 56.8
    15
    16
    \[ roboshop : children \]
    17
    web
    18
    cart
    19
    catalogue

[^19]: server
    node
    \[ centosdip-172-31-28-85 \~ \]$ cd ansible/
    3. 89. 162.97 \| 172. 31.28.85 \| t2.micro \| https: / /github. com/daws-76s/ansible. git
    \[ centos@ip-172-31-28-85 \~/ansible \]$ 1s -1
    total 8
    rw-rw-r--
    1 centos centos 92 Dec 20 03:06 01-playbook. yaml
    rw-rw-r--
    1 centos centos 173 Dec 20 03:06 inventory
    3. 89. 162.97 \| 172. 31.28.85 \| t2.micro \| https: / /github. com/daws-76s/ansible. git
    \[ centosdip-172-31-28-85 \~/ansible \]$ ansible -i inventory web --list-hosts
    hosts (2) :
    192 . 187 . 56.3
    192 . 187 .56.4
    3. 89. 162.97 \| 172. 31.28.85 \| t2.micro \| https: / /github. com/daws-76s/ansible. git
    \[ centos@ip-172-31-28-85 \~/ansible \]$ ansible -i inventory cart --list-hosts
    hosts (2) :
    192 . 187 . 56.7
    192 . 187 . 56.8
    3. 89. 162.97 \| 172. 31. 28.85 \| t2. micro \| https: / /github . com/daws-76s/ansible.git
    \[ centos@ip-172-31-28-85 \~/ansible \]$ ansible -i inventory roboshop --list-hosts
    hosts (6) :
    192 . 187 . 56.3
    192 . 187 . 56 .4
    192 . 187 . 56.7
    192 . 187 . 56.8
    192 . 187 . 56.5
    192 . 187 . 56.6
    3. 89. 162.97 \| 172. 31.28.85 \| t2. micro \| https: / /github. com/daws-76s/ansible. git
    tosdip-172-31-28-85 \~/ansible 1s

[^20]: \[ centosdip-172-31-28-85 \~/ansible \]$ ansible -i inventory ungrouped --list-hosts
    hosts (2) :
    192 . 187 . 56.20
    192 . 187. 56.30

[^21]: \[ centosdip-172-31-28-85 \~/ansible \]$ ansible -i inventory all --list-hosts
    hosts (8) :
    192 . 187 . 56.20
    192 . 187 . 56.30
    192 . 187 .56.3
    192 . 187 . 56.4
    192 . 187 .56.7
    192 . 187 . 56.8
    192 . 187 . 56.5
    192 . 187 . 56.6
    3. 89. 162.97 \| 172. 31.28.85 \| t2. micro \| https: / /github. com/daws-76s/ansible.git
    \[ centos(ip-172-31-28-85 \~/ansible \]$

[^22]: REPOS
    Ansible > ! 1.pingplaybook.yaml
    Ansible
    T
    name: ping playbook
    ! 1.pingplaybook.yaml
    2
    hosts: web
    3
    tasks :
    E inventory.ini
    4
    name: ping the server
    > Concepts
    5
    ansible. builtin . ping:
    > Robosho-shellscripts
    shellscripts
    $ 01.hello-world.sh

[^23]: 1. pingplaybook . yam1
    inventory . ini
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevOps\\Repos \\Ansible> git add . ; git commit -m "playbook1"; git push origin main
    \[main ( root-commit) 66a6bf9\] playbook1

[^24]: \[ centos@ip-172-31-21-76 \~ \]$ git clone https: //github. com/chilops/Ansible.git
    Cloning into 'Ansible'.
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4), done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 4 (delta 0), reused 4 (delta 0), pack-reused 0
    Receiving objects: 100% (4/4), done.
    54 . 227. 54. 185 \| 172. 31.21.76 \| t2.micro \| null
    \[ centosdip-172-31-21-76 \~ \]$ 1s
    Ansible
    54 . 227. 54. 185 \| 172. 31.21.76 \| t2.micro \| null
    \[ centos@ip-172-31-21-76 \~ \]$ cd Ansible/
    54 . 227. 54.185 \| 172. 31.21.76 \| t2.micro \| https: / /github. com/chilops/Ansible.git
    \[ centosdip-172-31-21-76 \~/Ansible \]$ 1s
    1 . pingplaybook . yaml inventory . ini
    54 . 227. 54. 185 \| 172. 31.21.76 \| t2.micro \| https: //github. com/chilops/Ansible. git
    \[ centos@ip-172-31-21-76 \~/Ansible \]$ \[

[^25]: \[ centosdip-172-31-21-76 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos --become -e ansible password
    =Devops321 1. pingplaybook . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[ping playbook\]
    \* \* \* \*
    TASK \[Gathering Facts\]
    ok: \[54 . 163 . 18 . 10\]
    TASK \[ping the server\]
    ok: \[54 . 163 . 18.10\]
    PLAY RECAP \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    54 . 163 . 18 . 10
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    54. 227. 54.185 \| 172. 31.21.76 \| t2.micro \| https: //github.com/chilops/Ansible.git

[^26]: Ansible > ! 2.nginx.yaml
    name: install and run nginx
    12
    hosts: web
    3
    become: yes #it will get root access
    14
    tasks :
    5
    name: install nginx package
    6
    ansible . builtin . package :
    name: nginx
    8
    state: present
    9
    name: run nginx
    10
    ansible . builtin . service:
    name: nginx
    12
    state: started

[^27]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    2. nginx . yam1
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevOps \\Repos \\Ansible> git add . ; git commit -m "playbook2"; git push origin main

[^28]: centos@ip-172-31-21-76 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops3
    2 . nginx . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[install and run nginx\]
    \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok :
    \[54 . 163 . 18. 10\]
    TASK \[install nginx package\]
    \* \* \*
    ok :
    \[54 . 163 . 18 .10\]
    TASK \[run nginx\]
    \* \*
    ok: \[54 . 163 . 18 . 10\]
    PLAY RECAP
    \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    54 . 163 . 18 . 10
    : ok=3
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    54. 227. 54.185 \| 172.31.21.76 \| t2.micro \| https: //github. com/chilops/Ansible.git
    os@ip-172-31-21-76 \~
    /Ansible
    n

