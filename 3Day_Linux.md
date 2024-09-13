---
title: 3Day_Linux
uuid: 2a20131c-0e82-11ef-9be8-a6f126245c9e
version: 251
created: '2024-05-10T09:32:47+05:30'
tags:
  - linux
---

***Topics:***

1. *<mark style="background-color:#f3de6c;">Permissions -users, groups, others<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Chmod<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">User management<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Create/add new user- **useradd**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">set password - **passwd**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Enabling password authentication -    **PasswordAuthentication yes"** under **/etc/ssh/sshd_config**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Group creation - groupadd, getent , adding secondary group to user<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">User modification - **usermod**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Change ownership of a file - **chown**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Removing a user from group -**gpasswd**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Deleting a user - **userdel**   (if user leaving organization)<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Group deletion -**groupdel**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Process management --> **ps, ps -ef, Kill**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Package management - **Yum(install, remove a package)**<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Adding ssh private, public keys to new user & login new user with private key.<!-- {"backgroundCycleColor":"14"} --></mark>*

 

 

 

# *<mark style="background-color:#f8914d;">**Permissions:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*permissions*

*--------------*

*U - user    - Satya user is one who created the file/folder*

*G - group  - a team of people present in a group (Now satya is part of DevOps group)*

*O - others - some other person belongs to testing, development teams*

 

*R   - 4 - Read*

*W - 2 - Write*

*X  - 1 -Execute - used when you run shell scripts & commands*

 

*In Linux when you create user, a group with same name will be created*

*Satya--> user Satya and group with name Satya also created*

 

***Created to file1 to check permissions***

 

```
touch file1
```

```
ls -l
```

![5817c5b1-8df3-44e5-97aa-53df357d1b5d.png|461](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/5817c5b1-8df3-44e5-97aa-53df357d1b5d.png) [^1]

*Above file has below permissions*

*rw-        rw-       r--*

*user      group  others*

*u           g           o*

 

# *<mark style="background-color:#f8914d;">**Chmod:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
chmod u+x file1
```

```
chmod g+x file1
```

![](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/0185d503-b619-4b6b-928e-87d90575736b.png) [^2]

 

```
chmod g-rwx file1
```

```
chmod o-r file1
```

![](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/c74a305e-fdab-4ec6-80f4-914eeed7bab8.png) [^3]

 

```
 chmod ugo+rwx file1      --> Giving permissions at same time for user, group, others
```

```
 chmod ugo-rwx file1       --> Removing permissions at same time for user, group, others
```

```
 chmod ugo+rw file1    
```

![1e375135-bb29-4bcc-ade2-a3723c210779.png|564](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/1e375135-bb29-4bcc-ade2-a3723c210779.png) [^4]

 

 

*Changing permissions recursively for a folder so that inside file permissions also will change*

```
chmod g-w -R devops        --> -R stands recursively
```

 

![0d725e01-858c-4ab8-ada9-4d072ab7d715.png|519](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/0d725e01-858c-4ab8-ada9-4d072ab7d715.png) [^5]

 

![a401d136-5876-40e3-8c7a-bb6bb618a2f8.png|526](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/a401d136-5876-40e3-8c7a-bb6bb618a2f8.png) [^6]

 

```
chmod 740 example.txt
```

![c80b2987-0fa6-495c-aa3a-031d20a0f255.png|524](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/c80b2987-0fa6-495c-aa3a-031d20a0f255.png) [^7]

 

 

# *<mark style="background-color:#f8914d;">**User management: **<!-- {"backgroundCycleColor":"24"} --></mark><mark style="background-color:#f3de6c;">create user, set password, adding new user<!-- {"backgroundCycleColor":"14"} --></mark>*<!-- {"collapsed":true} -->

 

*Create user: ex: Sanjay joined in our team.*

\

***Syn:** useradd <user-name>   -when a user is created, automatically group is created with same username*

```
sudo useradd Sanjay     --> to create a new user(only root user can add user).
```

 

![d1ecd4be-318b-4883-a26e-27d8542f6da4.png|455](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/d1ecd4be-318b-4883-a26e-27d8542f6da4.png) [^8]

*Or*

```
useradd satya
```

```
passwd satya
```

 

![64937ace-1fc6-46e3-bd0f-92834f1285b6.png|753](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/64937ace-1fc6-46e3-bd0f-92834f1285b6.png) [^9]

 

```
cat /etc/passwd     --> to check users  -will have user entries
```

 

![fec61813-0b55-4482-a89c-2250a52c21a7.png|679](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/fec61813-0b55-4482-a89c-2250a52c21a7.png) [^10]

 

```
id satya      --> to check user id details
```

```
getent group     --> to check groups which are created
```

*Or*

```
getent group | grep -i satya
```

![](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/42a817d8-b37e-4991-97f6-1220e199e057.png) [^11]

 

 

# *<mark style="background-color:#f8914d;">**Enabling password authentication:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*If you want user to login using putty, we need to change below entries "PasswordAuthentication no" to "PasswordAuthentication yes" under **/etc/ssh/sshd_config***

 

```
Vim /etc/ssh/sshd_config     --> enable password authentication
```

 

![ca735e05-869b-4200-a86e-d93c373f73aa.png|788](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/ca735e05-869b-4200-a86e-d93c373f73aa.png) [^12]

 

![99267064-b7a9-4e87-af2a-7fbb45c83e6e.png|787](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/99267064-b7a9-4e87-af2a-7fbb45c83e6e.png) [^13]

 

```
sshd -t --> checks for syntax of the file if any errors in sshd_config file config it will show errors
```

```
systemctl restart sshd --> to restart sshd services
```

 

![b42b50b9-6d2f-40f8-9cdf-7511e2905619.png|571](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/b42b50b9-6d2f-40f8-9cdf-7511e2905619.png) [^14]

 

![](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/c3c02df6-2a9b-44bd-b53f-961b799d1e90.png)

 

*Now login into a new user which already created.*

```
 ssh satya@3.91.221.62
```

 

![5169600c-42ab-43f7-a834-b0e1dc9132bf.png|668](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/5169600c-42ab-43f7-a834-b0e1dc9132bf.png) [^15]

 

 

# *<mark style="background-color:#f8914d;">**Group creation:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Syn: groupadd <group-name>*

```
groupadd devops
```

```
getent group
```

*Or*

```
getent group | grep -I devops
```

![50094daf-d77a-4fbe-8fdd-8ca7209768c0.png|604](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/50094daf-d77a-4fbe-8fdd-8ca7209768c0.png) [^16]

 

# *<mark style="background-color:#f8914d;">**Assigning a new group(devops) to user satya**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*#every user will have a primary group and secondary group*

 

*Satya should be added to devops group*

*Syn**: usermod -g <group-name>  <user-name>     --> usermod commands***

```
usermod -g devops satya
```

```
id satya
```

![e5d265b3-3088-480e-a82a-7de214a9c85c.png|529](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/e5d265b3-3088-480e-a82a-7de214a9c85c.png) [^17]

 

***Login as user satya and create file/folder to check user & group***

```
id satya
```

```
touch file1
```

```
ls -l
```

```
mkdir folder1
```

```
ls -l
```

 

![a8495f7c-b516-43b8-82a6-9796a71781aa.png|638](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/a8495f7c-b516-43b8-82a6-9796a71781aa.png) [^18]

 

# *<mark style="background-color:#f8914d;">**chown command**:<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Syn: chown user:group <file-name>*

*Syn: chown user:group -R <folder-name>*

```
chown satya:devops file2
```

```
chown satya:devops -R folder1      --> recursively for a folder
```

 

![d209281c-10f7-463c-9574-6448cd477a7f.png|540](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/d209281c-10f7-463c-9574-6448cd477a7f.png) [^19]

 

*Adding secondary group to user satya*

```
groupadd prod
```

```
usermod -aG prod satya           --> G - for secondary group, g - for primary group, a - for appending.
```

 

![30fe227a-668b-4a98-b4aa-1f7282e30acf.png|560](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/30fe227a-668b-4a98-b4aa-1f7282e30acf.png) [^20]

 

# *<mark style="background-color:#f8914d;">**Removing a user from group**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

***Syn:** gpasswd -d <user-name> <group-name>   --> -d stands for delete*

```
gpasswd -d satya prod
```

![7a855de1-3c18-4410-b282-fa7557109521.png|562](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/7a855de1-3c18-4410-b282-fa7557109521.png) [^21]

 

 

# *<mark style="background-color:#f8914d;">**Group deletion:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
groupdel devops
```

![39f279cd-fef2-4964-a581-5c445ddfa0b7.png|686](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/39f279cd-fef2-4964-a581-5c445ddfa0b7.png) [^22]

 

# *<mark style="background-color:#f8914d;">**User deletion:**<!-- {"backgroundCycleColor":"24"} --></mark> user is leaving organization*<!-- {"collapsed":true} -->

\

*Syn: userdel <user-name> --> removes user from Linux*

```
userdel sanjay
```

 

![8aa3f760-48e3-4628-834f-1249e5efc178.png|583](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/8aa3f760-48e3-4628-834f-1249e5efc178.png) [^23]

 

 

 

# *<mark style="background-color:#f8914d;">**Process Management:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*whatever we do in linux --> a process id will be created and reported back*

 

```
ps
```

*Or*

```
ps -ef   --> to see all the processes in linux
```

![64814be2-6fda-4e48-ad71-90e12721d67e.png|859](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/64814be2-6fda-4e48-ad71-90e12721d67e.png) [^24]

 

 

*foreground process --> block terminal*

 

*background process --> runs in background*

 

*To kill a process*

```
kill <process id>
```

```
kill -9 <process id>     --> forcefully kills process (ex. When a police stops we will stop)
```

 

 

# *<mark style="background-color:#f8914d;">**Package management:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

***To install any package we should use only sudo access***

 

```
cd /etc/yum.repos.d/    --> centos will a have some extra urls
```

```
ls -l
```

```
cat amzn2-extras.repo
```

![6ae77b03-50cd-444a-b463-222443b921a1.png|588](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/6ae77b03-50cd-444a-b463-222443b921a1.png) [^25]

 

 

***Yum Install:** Is used to install packages -supports in RHEL ,centos, fedora, AWS Linux 2*

![e302a1fd-24c5-4ae2-b49d-0f0880b919c8.png|609](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/e302a1fd-24c5-4ae2-b49d-0f0880b919c8.png) [^26]

 

 

 

***#yum install <package-name>***

```
yum install git
```

 

![54d602ab-7069-4c7f-9252-598348694914.png|802](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/54d602ab-7069-4c7f-9252-598348694914.png) [^27]

 

 

```
yum list installed
```

```
yum list available
```

```
yum list available | wc -l
```

![f21e0db2-fcf8-4935-b69b-0ffa9d29d1e6.png|590](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/f21e0db2-fcf8-4935-b69b-0ffa9d29d1e6.png) [^28]

 

```
yum list available | grep -I mysql
```

![974894a7-77fc-40d8-8262-0e9c0a255fc9.png|629](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/974894a7-77fc-40d8-8262-0e9c0a255fc9.png) [^29]

 

*<mark style="background-color:#f8914d;">**To remove any package:**<!-- {"backgroundCycleColor":"24"} --></mark>*

 

```
yum remove <package-name> -y
```

```
yum remove git -y
```

![05ecbec8-70fd-43ca-b157-5f68d8fc733a.png|873.3333740234375](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/05ecbec8-70fd-43ca-b157-5f68d8fc733a.png) [^30]

 

 

# *<mark style="background-color:#f8914d;">**Adding ssh private, public keys to new user:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Madhu joined, how can you enable ssh access through private key*

1. *User Madhu created.*

1. *Give me your public key(ask Madhu), keep your private key securely.*

1. *Madhu will create a key* 


  ```
   ssh-keygen -t rsa -f madhu
  ```

![11a4b536-8b37-40c1-816f-07c6e0fc3d30.png|641](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/11a4b536-8b37-40c1-816f-07c6e0fc3d30.png) [^31]

 

*Public key*

```
cat madhu.pub
```

![a8a85efe-5667-4dd5-93c4-298edb4c365a.png|814.3333740234375](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/a8a85efe-5667-4dd5-93c4-298edb4c365a.png) [^32]

 

1. *Create .ssh file under /home/madhu*

![da5f1665-3adc-4ec3-b921-6f495b3c27b7.png|575](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/da5f1665-3adc-4ec3-b921-6f495b3c27b7.png) [^33]

 

*Change the permission to 700*

\

![a584d806-ac3d-4b08-b638-4b5e48f6efce.png|537](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/a584d806-ac3d-4b08-b638-4b5e48f6efce.png) [^34]

 

*Add public key under "authorized_keys"*

\

![fcd18b83-2230-452f-a57b-8fc5ea20f06f.png|522](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/fcd18b83-2230-452f-a57b-8fc5ea20f06f.png) [^35]

 

***Change the permissions** "authorized_keys"*

```
chmod 600 authorized_keys
```

```
ls -l
```

![2c0ae625-a6a7-4296-b2e4-3bfc5e7bc2a6.png|541](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/2c0ae625-a6a7-4296-b2e4-3bfc5e7bc2a6.png) [^36]

 

***Change the owner ship of .ssh file***

```
chown -R madhu:madhu .ssh
```

```
ls -la
```

![042d1838-6885-4cb0-af0e-d452c1935897.png|542](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/042d1838-6885-4cb0-af0e-d452c1935897.png) [^37]

 

 

***Now madhu can login with private key:***

***Syn**: ssh -i <keypair> user@3.91.221.62*

```
ssh -i madhu madhu@3.91.221.62
```

![cd502346-bd0c-487e-adec-99832c3d90c3.png|655](https://images.amplenote.com/2a20131c-0e82-11ef-9be8-a6f126245c9e/cd502346-bd0c-487e-adec-99832c3d90c3.png) [^38]

 

[^1]: Lecz-user(@1p-1/2-31-35-27 \~\]>
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    \[ec2-user@ip-172-31-35-27 \~\]$
    \[ec2-user@ip-172-31-35-27 \~\]$ touch file1
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\] $

[^2]: ec2-user@ip-172-31-35-27 \~\]$ chmod u+x file1
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    rwxrw-r-- 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$ chmod g+x file1
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    rwxrwxr-- 1 ec2-user ec2-user 0 Nov 30 10:13 file1

[^3]: \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rwxrwxr-- 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-userup-172-31-35-27 \~\]$ chmod g-rwx file1
    \[ec2-user@ip-172-31-35-27 \~\]$ chmod o-r file1
    \[ec2-user@ip-172-31-35-27 \~\] $
    \[ec2-user@ip-172-31-35-27 \~\]$
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rWx--
    1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$

[^4]: \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rwx---rwx 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$ chmod ugo+rwx file1
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rwxrwxrwx 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$ chmod ugo-rwx file1
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    - 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$

[^5]: \[ec2-user@ip-172-31-35-27 \~\]$ mkdir devops
    \[ec2-user@ip-172-31-35-27 \~\]$ cd devops/
    \[ec2-user@ip-172-31-35-27 devops\]$ touch example. txt
    \[ec2-user@ip-172-31-35-27 devops\]$ cd . .
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    drwxrwxr-x 2 ec2-user ec2-user 25 Nov 30 10:53 devops
    -rw-rw---- 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$ chmod g-w -R devops
    \[ec2-user@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    drwxr-xr-x 2 ec2-user ec2-user 25 Nov 30 10:53 devops
    -rw-rw---- 1 ec2-user ec2-user 0 Nov 30 10:13 file1
    \[ec2-user@ip-172-31-35-27 \~\]$

[^6]: \[ec2-user@ip-172-31-35-27 \~\]$ cd devops/
    \[ec2-user@ip-172-31-35-27 devops\]$ 1s -1
    total 0
    -rw-r--r-- 1 ec2-user ec2-user 0 Nov 30 10:53 example. txt
    \[ec2-user@ip-172-31-35-27 devops\] $

[^7]: \[ec2-user@ip-172-31-35-27 devops\]$ 1s -1
    total 0
    -rw-r--r-- 1 ec2-user ec2-user 0 Nov 30 10:53 example . txt
    Lecz-useramp-172-31-35-27 devops\]$ chmod 740 example . txt
    \[ec2-user@ip-172-31-35-27 devops\]$ 1s -1
    total 0
    -rwxr -
    - 1 ec2-user ec2-user 0 Nov 30 10:53 example. txt
    \[ec2-useramp-172-31-35-27 devops \] $

[^8]: \[ec2-user@ip-172-31-35-27 devops\]$ cd
    \[ec2-user@ip-172-31-35-27 \~\]$ pwd
    /home/ec2-user
    \[ec2-user@ip-172-31-35-27 \~\]$ useradd Sanjay
    bash: /usr/sbin/useradd: Permission denied
    \[ec2-user@ip-172-31-35-27 \~\]$ sudo useradd sanjay
    \[ec2-user@ip-172-31-35-27 \~\] $
    \[ec2-user@ip-172-31-35-27 \~\]$ sudo su
    \[root@ip-172-31-35-27 \~\]#

[^9]: \[ec2-user@ip-172-31-35-27 \~\]$ sudo su
    \[root@ip-172-31-35-27 ec2-user\]#
    \[root@ip-172-31-35-27 ec2-user\]#
    \[root@ip-172-31-35-27 ec2-user\]# useradd satya
    \[root@ip-172-31-35-27 ec2-user\]# passwd satya
    Changing password for user satya.
    New password:
    BAD PASSWORD: The password fails the dictionary check - it is too simplistic/systematic
    Retype new password:
    passwd: al1 authentication tokens updated successfully.
    \[root@ip-172-31-35-27 ec2-user\]#

[^10]: \[root@ip-172-31-35-27 ec2-user\]# cat /etc/passwd
    oot : x: 0:0: root: /root: /bin/bash
    pin : x:1:1:bin: /bin: /sbin/nologin
    daemon : x : 2 : 2 : daemon : /sbin : /sbin/nologin
    adm : x : 3 : 4 : adm: /var /adm: /sbin/nologin
    p: x:4:7: 1p:/var/spool/1pd: /sbin/nologin
    sync : x : 5:0:sync: /sbin : /bin/sync
    shutdown : x : 6:0: shutdown : /sbin: /sbin/shutdown
    alt :x:7 :0:halt: /sbin: /sbin/halt
    mail : x : 8: 12 :mai1: /var /spool/mail: /sbin/nologin
    operator : x: 11:0: operator : /root: /sbin/nologin
    games : x: 12 : 100: games : /usr /games : /sbin/nologin
    tp : x: 14:50: FTP User :/var/ftp: /sbin/nologin
    nobody : x : 99: 99 : Nobody : /: /sbin/nologin
    systemd-network : x : 192 : 192 :systemd Network Management: /: /sbin/nologin
    abus : x : 81:81: System message bus : /: /sbin/nologin
    "pc : x: 32: 32: Rpcbind Daemon : /var /lib/rpcbind: /sbin/nologin
    ibstoragemgmt : x : 999: 997 : daemon account for libstoragemgmt : /var /run/Ism: /sbin/nologin
    sshd : x: 74:74:Privilege-separated SSH: /var/empty/sshd: /sbin/nologin
    ngd : x : 998 : 996: Random Number Generator Daemon: /var /lib/rngd: /sbin/nologin
    chrony : x: 997: 995 : : /var /1ib/chrony: /sbin/nologin
    "pcuser : x: 29:29:RPC Service User: /var/lib/nfs: /sbin/nologin
    Ifsnobody : x : 65534 : 65534 : Anonymous NFS User : /var/lib/nfs : /sbin/nologin
    ec2-instance-connect : x: 996: 994: : /home/ec2-instance-connect : /sbin/nologin
    postfix : x: 89: 89: : /var /spool/postfix: /sbin/nologin
    Ecpdump : x : 72:72: : /:/sbin/nologin
    ac2-user : x : 1000: 1000:EC2 Default User : /home/ec2-user : /bin/bash
    sanjay : x: 1001 :1001:: /home/sanjay: /bin/bash (
    satya : x: 1002 : 1002: : /home/satya : /bin/bash
    root@ip-172-31-35-27 ec2-user\]#

[^11]: \[root@ip-172-31-35-27 ec2-user\]# id satya
    uid=1002 (satya) gid=1002 (satya) groups=1002 (satya)
    \[root@ip-172-31-35-27 ec2-user\]#
    \[root@ip-172-31-35-27 ec2-user\]# getent group \| grep -i satya
    satya : x : 1002:
    \[root@ip-172-31-35-27 ec2-user\]#

[^12]: #IgnoreUserknownHosts no
    # Don't read the user's \~/.rhosts and \~/.shosts files
    #IgnoreRhosts yes
    # To disable tunneled clear text passwords, change to no here!
    #PasswordAuthentication yes
    #PermitEmptyPasswords no
    PasswordAuthentication no

[^13]: #
    HostbasedAuthentication
    #IgnoreUserknownHosts no
    #
    Don't read the user's \~/. rhosts and \~/.shosts files
    #IgnoreRhosts yes
    To disable tunneled clear text
    passwords, change to no here!
    #PasswordAuthentication yes
    #PermitEmptyPasswords no
    PasswordAuthentication yes

[^14]: \[root@ip-172-31-35-27 ec2-user\]# vim /etc/ssh/sshd_config
    \[root@ip-172-31-35-27 ec2-user\]#
    \[root@ip-172-31-35-27 ec2-user\]#
    \[root@ip-172-31-35-27 ec2-user\]# systemct1 restart sshd
    \[root@ip-172-31-35-27
    A

[^15]: chowd@chowdary MINGW64
    $ ssh satya@3 . 91. 221. 62
    satya@3 . 91. 221.62's password:
    #_
    ####_
    Amazon Linux 2
    #####\\
    ###
    AL2 End of Life is 2025-06-30.
    #/
    1
    A newer version of Amazon Linux is available!
    Amazon Linux 2023, GA and supported until 2028-03-15.
    https ://aws . amazon . com/linux/amazon-linux-2023/
    \[satya@ip-172-31-35-27 \~\] $
    \[satyaQip-172-31-35-27 \~\]$ pwd
    /home /satya

[^16]: \[root@ip-172-31-35-27 ec2-user\]# groupadd devops
    \[root@ip-172-31-35-27 ec2-user\]# getend group \| grep -i devops
    bash: getend: command not found
    \[root@ip-172-31-35-27 ec2-user\]# getent group \| grep -i devops
    devops : x : 1003 :
    \[root@ip-172-31-35-27 ec2-user\]# \|

[^17]: \[root@ip-172-31-35-27 ec2-user\]# usermod -g devops satya
    \[root@ip-172-31-35-27 ec2-user\]# id satya
    uid=1002 (satya) gid=1003 (devops) groups=1003 (devops)
    \[root@ip-172-31-35-27 ec2-user\]#

[^18]: chowd@Chowdary MINGW64/
    $ ssh satya@3 . 91. 221. 62
    satya@3 . 91. 221. 62's password:
    Last login: Thu Nov 30 13:01:59 2023 from 106.206.67.1
    #
    ####_
    Amazon Linux 2
    #####
    ###
    AL2 End of Life is 2025-06-30.
    #
    A newer version of Amazon Linux is available!
    Amazon Linux 2023, GA and supported until 2028-03-15.
    https://aws . amazon . com/linux/amazon-linux-2023/
    \[satya@ip-172-31-35-27 \~\]$
    \[satya@ip-172-31-35-27 \~\]$
    \[satya@ip-172-31-35-27 \~\]$ pwd
    /home/satya
    \[satya@ip-172-31-35-27 \~\]$ id satya -
    uid=1002 (satya) gid=1003 (devops) groups=1003 (devops)
    \[satya@ip-172-31-35-27 \~\]$ touch file1-
    \[satya@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rw-r--r-- 1 satya devops 0 Nov 30 13:34 file1
    \[satya@ip-172-31-35-27 \~\]$ mkdir folder1
    \[satya@ip-172-31-35-27 \~\]$ 1s -1
    total 0
    -rw-r--r-- 1 satya devops 0 Nov 30 13:34 file1
    drwxr-xr-x 2 satya devops 6 Nov 30 13:34 folder1
    \[satya@ip-172-31-35-27 \~}$ \|

[^19]: \[root@ip-172-31-35-27 satya\]# touch file2 -
    \[root@ip-172-31-35-27 satya\]# 1s -1
    total 0
    -rw-r--r-- 1 satya devops 0 Nov 30 13:34 file1
    -rw-r--r-- 1 root root
    0 Nov 30 13:46 file2
    drwxr-xr-x 2 satya devops 6 Nov 30 13:34 folder1
    \[root@ip-172-31-35-27 satya\]# chmod satya: devops file2
    chmod: invalid mode: 'satya: devops'
    Try 'chmod --help' for more information.
    \[root@ip-172-31-35-27 satya\]# chown satya: devops file2
    \[root@ip-172-31-35-27 satya\]# 1s -1-
    total 0
    -rw-r--r-- 1 satya devops 0 Nov 30 13:34 file1
    -rw-r--r-- 1 satya devops 0 Nov 30 13:46 file2 -
    drwxr-xr-x 2 satya devops 6 Nov 30 13:34 folder1
    \[root@ip-172-31-35-27 satya\]#

[^20]: \[root@ip-172-31-35-27 satya\]# groupadd prod
    \[root@ip-172-31-35-27 satya\]# usermod -aG prod satya
    \[root@ip-172-31-35-27 satya\]# id satya
    uid=1002 (satya) gid=1003 (devops) groups=1003 (devops ) , 1004(prod)
    \[root@ip-172-31-35-27 satya\]#\|

[^21]: \[root@ip-172-31-35-27 satya\]# gpasswd -d satya prod
    Removing user satya from group prod
    \[root@ip-172-31-35-27 satya\]# id satya
    uid=1002 (satya) gid=1003 (devops) groups=1003 (devops)
    \[root@ip-172-31-35-27 satya\]#

[^22]: \[root@ip-172-31-35-27 satya\]# groupdel devops
    groupdel: cannot remove the primary group of user 'satya'
    \[root@ip-172-31-35-27 satya\]# userdel satya
    userdel: user satya is currently used by process 928
    \[root@ip-172-31-35-27 satya\]# userdel satya
    userdel: user satya is currently used by process 928
    \[root@ip-172-31-35-27 satya\]# cd . .
    \[root@ip-172-31-35-27 home\]# userdel satya
    userdel: user satya is currently used by process 928
    \[root@ip-172-31-35-27 home\]# cd . .
    \[root@ip-172-31-35-27 /\]# userdel satya
    userdel: user satya is currently used by process 928
    \[root@ip-172-31-35-27 /\]#
    \[root@ip-172-31-35-27 /\]# ps -ef \| grep 928
    satya
    928
    926
    0 13:01 ?
    00: 00:00 sshd: satya@pts/5
    satya
    929
    928
    0 13:01 pts /5
    00: 00:00 -bash
    oot
    1846
    1196
    0 14:14 pts /7
    00:00:00 grep --color=auto 928
    root@ip-172-31-35-27 /\]# ki11 -9 928
    \[root@ip-172-31-35-27 /\]# userdel satya
    userdel: group satya not removed because it is not the primary group of user satya.
    \[root@ip-172-31-35-27 /\]
    \[root@ip-172-31-35-27
    groupdel devops
    27

[^23]: CTP
    \[root@ip-172-31-35-27 satya\]# userdel sanjay
    \[root@ip-172-31-35-27 satya\]# cat /etc/passwd
    grep sanjay
    \[root@ip-172-31-35-27 satya\]# cat /etc/passwd
    grep satya
    satya : x: 1002:1003:: /home/satya: /bin/bash

[^24]: \[root@ip-172-31-35-27 /\]# groupdel devops
    \[root@ip-172-31-35-27 /\]#
    \[root@ip-172-31-35-27 /\]#
    \[root@ip-172-31-35-27 /\]#
    \[root@ip-172-31-35-27 /\]#
    \[root@ip-172-31-35-27 /\]# ps
    PID TTY
    TIME CMD
    1194 pts/7
    00: 00:00 sudo
    1195 pts/7
    00: 00:00 su
    1196 pts /7
    00: 00:00 bash
    1870 pts/7
    00: 00:00 ps
    \[root@ip-172-31-35-27 /\]#
    \[root@ip-172-31-35-27 /\]# ps -ef
    UID
    PID PPID
    C STIME TTY
    TIME CMD
    root
    0
    0 10:10 ?
    00: 00:02 /usr/lib/systemd/systemd --switched-root --system --deserialize 21
    root
    O
    0 10:10
    ?
    00: 00:00 \[kthreadd\]
    root
    Of WNH
    2
    0 10:10
    00:00:00 \[rcu_gp\]
    root
    0 10:10 ?
    00: 00:00 \[rcu_par_gp\]
    root
    2
    0 10 :10
    00: 00:00 \[kworker /0 : OH-ev\]
    root
    8
    0 10:10
    00: 00:00 \[mm_percpu_wq\]
    root
    9
    0 10:10
    00: 00:00 \[rcu_tasks_rude_\]
    root
    10
    NNNNN
    0
    10:10
    00:00:00 \[rcu_tasks_trace\]
    root
    11
    10:10
    00:00:00 \[ksoftirqd/0\]
    root
    12
    0
    10:10
    00 : 00: 00
    \[rcu_sched\]

[^25]: \[ec2-user@ip-172-31-35-27 \~\]$ sudo su
    ast login: Thu Nov 30 13:25:09 UTC 2023 on pts/7
    \[root@ip-172-31-35-27 \~\]#
    \[root@ip-172-31-35-27 \~\]# cd /etc/yum. repos . d/
    \[root@ip-172-31-35-27 yum. repos . d\]# 1s -1
    total 8
    rw-r--r-- 1 root root 1003 Sep 26 22:32 amzn2-core. repo
    rw-r--r-- 1 root root 2150 Nov 16 23:34 amzn2-extras . repo
    \[root@ip-172-31-35-27 yum. repos . d\] #

[^26]: RHEL repo
    amazon repo
    Our repo

[^27]: \[root@ip-172-31-35-27 yum . repos . d\]# yum install git
    oaded plugins: extras_suggestions, langpacks, priorities, update-motd
    amzn2-core
    Resolving Dependencies
    -> Running transaction check
    --> Package git. x86_64 0:2. 40.1-1. amzn2 . 0.1 will be installed
    -> Processing Dependency: git-core = 2. 40.1-1. amzn2. 0.1 for package: git-2. 40.1-1. amzn2 . 0. 1. x86_64
    Processing Dependency: git-core-doc = 2. 40.1-1. amzn2 .0.1 for package: git-2. 40.1-1. amzn2. 0. 1. x86_64
    Processing Dependency: per1-Git = 2.40.1-1. amzn2 . 0.1 for package: git-2. 40.1-1. amzn2 . 0.1. x86_64
    Processing Dependency: per1 (Git) for package: git-2. 40.1-1. amzn2 . 0. 1. x86_64
    Processing Dependency: per1 (Term: : Readkey) for package: git-2. 40.1-1. amzn2. 0.1.x86_64
    Running transaction check
    Package git-core. x86_64 0:2. 40.1-1. amzn2. 0.1 will be installed
    Package git-core-doc . noarch 0:2.40.1-1. amzn2. 0.1 will be installed
    Package per1-Git. noarch 0:2. 40.1-1. amzn2 . 0.1 will be installed
    Processing Dependency: per1(Error) for package: per1-Git-2. 40.1-1. amzn2. 0. 1. noarch
    Package per1-TermReadKey . x86_64 0:2.30-20. amzn2. 0.2 will be installed
    -> Running transaction check
    --> Package per1-Error . noarch 1:0.17020-2. amzn2 will be installed
    --> Finished Dependency Resolution
    Dependencies Resolved
    Package
    Arch
    Version
    Repositor
    Installing:
    git
    x86_64
    2 . 40. 1-1. amzn2 . 0. 1
    amzn2-cor
    Installing for dependencies:

[^28]: gT
    \[root@ip-172-31-35-27 yum. repos . d\]# yum list available \| wc -1
    8697
    \[root@ip-172-31-35-27 yum. repos . d\]#
    \[root@ip-172-31-35-27 yum. repos . d\]#

[^29]: \[root@ip-172-31-35-27 yum. repos . d\]# yum list available \| grep -I mysql
    apr-util-mysql . x86_64
    1. 6. 3-1. amzn2 . 0. 1
    amzn2-core
    dovecot-mysql. x86_64
    1:2. 2 . 36-6 . amzn2 . 1
    amzn2-core
    freeradius-mysql1. x86_64
    3 . 0. 26-1. amzn2 . 0. 1
    amzn2-core
    1ibdbi-dbd-mysql . x86_64
    0.8. 3-16 . amzn2 . 0. 1
    amzn2-core
    mysql-connector-java. noarch
    1:5.1.25-3. amzn2 . 0 .2
    amzn2-core
    mysql-connector-odbc . x86_64
    5 .2.5-8 . amzn2
    amzn2-core
    pcp-pmda-mysql. x86_64
    4.3.2-12 . amzn2 . 0. 1
    amzn2-core
    php-mysql . x86_64
    5 . 4.16-43 . amzn2
    amzn2-core
    php-mysqlnd . x86_64
    5 . 4. 16-46 . amzn2 . 0. 2
    amzn2-core
    qt-mysql . 1686
    1:4.8.5-15 . amzn2 . 0.6
    amzn2-core
    qt-mysql . x86_64
    1:4.8.5-15 . amzn2 . 0. 6
    amzn2-core
    qt5-qtbase-mysql . 1686
    5.9.2-3 . amzn2 . 0 . 12
    amzn2-core
    qt5-qtbase-mysql . x86_64
    5 . 9.2-3 . amzn2 . 0. 12
    amzn2-core
    redland-mysql. x86_64
    1.0. 16-6 . amzn2 . 0. 1
    amzn2-core
    rsys log-mysql . x86_64
    8. 24.0-57 . amzn2 . 2 . 0. 2
    amzn2-core
    \[root@ip-172-31-35-27 yum. repos . d\] #

[^30]: \[root@ip-172-31-35-27 yum . repos . d\]# yum remove git -y
    oaded plugins: extras_suggestions, langpacks, priorities, update-motd
    Resolving Dependencies
    -> Running transaction check
    --> Package git. x86_64 0:2. 40. 1-1. amzn2 . 0.1 will be erased
    Processing Dependency: git = 2.40.1-1. amzn2 . 0.1 for package: per1-Git-2. 40.1-1. amzn2 . 0. 1. noarch
    Running transaction check
    -> Package per1-Git. noarch 0:2. 40.1-1. amzn2 . 0.1 will be erased
    -> Finished Dependency Resolution
    amzn2-core/2/x86_64
    \| 3.6 KB 00: 00:00
    Dependencies Resolved
    Package
    Arch
    Version
    Repository
    Size
    Removing :
    git
    x86_64
    2. 40. 1-1. amzn2 . 0.1
    @amzn2-core
    85 k
    Removing for dependencies :
    per1-Git
    noarch
    2. 40. 1-1. amzn2 . 0. 1
    @amzn2-core
    65 k
    Transaction Summary
    Remove 1 Package (+1 Dependent package)
    Installed size: 150 k
    Down loading packages :
    Running transaction check
    Running transaction test
    Transaction test succeeded
    Running transaction
    Erasing
    per1-Git-2. 40. 1-1. amzn2 . 0. 1. noarch
    Erasing
    git-2. 40. 1-1. amzn2 . 0. 1. x86_64
    NHNH
    git-2 . 40. 1-1. amzn2 . 0. 1. x86_64
    NNNN
    Verifying
    Verifying
    : per1-Git-2. 40. 1-1. amzn2 . 0. 1. noarch
    Removed:
    git . x86_64 0:2. 40. 1-1. amzn2 . 0.1
    Dependency Removed:
    per1-Git . noarch 0:2. 40. 1-1. amzn2 . 0. 1
    Complete!
    \[root@ip-172-31-35-27 yum. repos . d\]# \|

[^31]: chowd@chowdary MINGW64
    $ cd /e/awsdevops /keys/
    chowd@Chowdary MINGW64 /e/awsdevops/keys
    $ ssh-keygen -t rsa -f madhu
    Generating public/private rsa key pair.
    Enter passphrase (empty for no passphrase) :
    Enter same passphrase again:
    Your identification has been saved in madhu
    Your public key has been saved in madhu . pub
    The key fingerprint is :
    SHA256 : 30RtNqt6g+eQ61YetT8xKfqSezctwhgyb+6nIxVvC/E chowd@chowdary
    The key's randomart image is:
    \[RSA 3072\]
    OO.
    S\* \*
    OO\*=Eo+
    OO . XO+
    +
    +0&. \*
    O+XBX. O +
    \[SHA256\]
    chowd@Chowdary MINGW64 /e/awsdevops /keys

[^32]: chowd@Chowdary MINGW64 /e/awsdevops/keys
    $ cat madhu . pub
    ssh-rsa AAAAB3NzaClyc2EAAAADAQABAAABgQDts YZYpMMfHD+\]tmeHQTo+n08N4Cynv76JUJ7 FG5nm4tRC6Bd2GEYWBZBXX32IVYLaD6FKpm+2Pu3DZ30025B1xMI5WHSNAMEgQ 3
    4jFX4TUA7p6F1CbS8f27 1whhhYdOHL8yUecp+jb2sPb1tgGbeOOI2mVIoNirvgNL /TPnxQTTSdn0kbgmdoSh+In2 JwvJwMY9QxQgb 56 j yBAoQ4KzJVHvOr 4YWL 6GSWSSae TON4x169
    MLXL 2 FWS4uBZS1D2ZBZeCIDAnUKzQQfuSRhxjMAiMuzDgAnxtG9eShooZgZxchWHcuD 1EJv7H5tcuz78qFY7 d6MgNKoGebyWcbosd+8b JRESKMFFnIjlrB843/Legn17021DcZg/2L
    ALNNySPOILTNWS ZVG1Qphfkq1Ucnv6N8X77/4kusv/gVTOpkzrOE40CEbLW5h 1ofAKBKbRd92Kr7IESY5316XfpVwcf61fEYI+KhF+pSSeJoBhM77wf2NsbBVHRPVoe0Q18RMASTS=
    chowd@chowdary
    chowd@chowdary MINGW64 /e/awsdevops/keys

[^33]: id=1001 (madhu) gid=1001 (madhu) groups=1001 (madhu)
    \[root@ip-172-31-35-27 yum . repos . d\]# cd /home/madhu/
    \[root@ip-172-31-35-27 madhu\]#
    \[root@ip-172-31-35-27 madhu\]#
    \[root@ip-172-31-35-27 madhu\] #
    \[root@ip-172-31-35-27 madhu\]#
    \[root@ip-172-31-35-27 madhu\] # 1s -1
    total 0
    \[root@ip-172-31-35-27 madhu\]# mkdir .ssh
    \[root@ip-172-31-35-27 madhu\] # 1s -1
    total 0
    \[root@ip-172-31-35-27 madhu\] # 1s -la
    total 12
    drwx --
    ---- 3 madhu madhu 74 Nov 30 15:21
    drwxr-xr-x 6 root root
    62 Nov 30 15:14
    .
    rw-r--r-- 1 madhu madhu
    18 Jul 15 2020 .bash_logout
    -rw-r--r-- 1 madhu madhu 193 Jul 15
    2020 .bash_profile
    -rw-r--r-- 1 madhu madhu 231 Ju1 15 2020 .bashrc
    drwxr-xr-x 2 root root
    6 Nov 30 15:21 .ssh
    \[root@ip-172-31-35-27 madhu\]#

[^34]: drwxr-xr-x 2 root root
    6 Nov 30 15:21 . ssh
    \[root@ip-172-31-35-27 madhu\]# chmod 700 .ssh <
    \[root@ip-172-31-35-27 madhu\] # 1s -la
    total 12
    drwx------ 3 madhu madhu 74 Nov 30 15:21
    drwxr-xr-x 6 root root
    62 Nov 30 15:14
    -rw-r--r-- 1 madhu madhu 18 Ju1 15 2020 .bash_logout
    -rw-r--r-- 1 madhu madhu 193 Ju1 15
    2020 . bash_profile
    -rw-r--r--
    1 madhu madhu 231 Ju1 15 2020 .bashrc
    drwx-
    2 root root
    6 Nov 30 15:21 . ssh
    \[rootGip-172-31-35-27 madhu\]#

[^35]: \[root@ip-172-31-35-27 madhu\]# cd .ssh/
    \[root@ip-172-31-35-27 . ssh\]# vim authorized_keys
    \[root@ip-172-31-35-27 . ssh\]#

[^36]: \[root@ip-172-31-35-27 .ssh\]# 1s -1
    total 4
    -rw-r--r-- 1 root root 569 Nov 30 15:25 authorized_keys
    \[root@ip-172-31-35-27 . ssh\]#
    \[root@ip-172-31-35-27 . ssh\]# chmod 600 authorized_keys
    \[root@ip-172-31-35-27 . ssh\]# 1s -1
    total 4
    -rw--
    - 1 root root 569 Nov 30 15:25 authorized_keys
    \[root@ip-172-31-35-27 .ssh\]#

[^37]: root@ip-172-31-35-27 madhu\]# 1s -1a
    total 12
    drwx - - ----
    3 madhu madhu 74 Nov 30 15:21
    drwxr-xr-x 6 root root
    62 Nov 30 15:14
    -rw-r--r-- 1 madhu madhu 18 Jul 15
    2020 .bash_logout
    rw-r--r-- 1 madhu madhu 193 Jul 15
    2020 . bash_profile
    rw-r--r-- 1 madhu madhu 231 Jul 15
    2020 .bashrc
    drwx-
    2 root root 29 Nov 30 15:25 .ssh
    \[root@ip-172-31-35-27 madhu\]#
    \[root@ip-172-31-35-27 madhu\]# chown -R madhu : madhu .ssh
    \[root@ip-172-31-35-27 madhu\]# 1s -1a
    total 12
    drwx------ 3 madhu madhu 74 Nov 30 15:21
    drwxr-xr-x 6 root root
    62 Nov 30 15:14
    rw-r--r-- 1 madhu madhu 18 Jul 15
    2020 . bash_logout
    rw-r--r-- 1 madhu madhu 193 Jul 15
    2020 . bash_profile
    rw-r--r-- 1 madhu madhu 231 Ju1 15 2020 .bashrc
    arwx
    2 madhu madhu, 29 Nov 30 15:25 .ssh
    \[root@ip-172-31-35-27 madhu\] #

[^38]: chowd@chowdary MINGW64 /e/awsdevops /keys
    $ ssh -i madhu madhu@3. 91. 221.62
    #_
    ####_
    Amazon Linux 2
    #####\\
    ###
    AL2 End of Life is 2025-06-30.
    #
    A newer version of Amazon Linux is available!
    Amazon Linux 2023, GA and supported until 2028-03-15.
    https ://aws . amazon . com/linux/amazon-linux-2023/
    \[madhuQip-172-31-35-27 \~\] $
    \[madhu@ip-172-31-35-27 \~\]$ pwd
    /home /madhu
    madhu@ip-172-31-35-27 \~1$ 1

