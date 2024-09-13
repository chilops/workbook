---
title: 16Day_Shell Scripting
uuid: 8d658766-0f65-11ef-af7b-a6f126245c9e
version: 170
created: '2024-05-11T12:40:30+05:30'
tags:
  - shell
  - shellscripting
---

***Topics:***

 

1. *<mark style="background-color:#f8d616;">Delete old log files<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">IFS - Internal Field Separator<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Check Disk usage & drop an email<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Installing and configuring Gmail setup in centos 8 & sending alerts to gmail<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">delete old log files<!-- {"backgroundCycleColor":"25"} --></mark>*

\

\

# *<mark style="background-color:#f8914d;">**Delete old log files**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*1. we have a folder where we are storing log files*

*/tmp/shell-script-logs*

 

*2. delete log files more than 14 days, only .log extensions not another files*

 

*source-directory*

*search .log files and more than 14 days old*

*rm -rf*

 

*Launch an instance*

![e99ed13a-f333-41cc-8fe7-44c35c1cfcc4.png|887.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/e99ed13a-f333-41cc-8fe7-44c35c1cfcc4.png) [^1]

 

![e1343666-25c3-4988-8392-e8ccbc22b8b9.png|884.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/e1343666-25c3-4988-8392-e8ccbc22b8b9.png) [^2]

 

 

*Create a dir which is not present*

![67d8b995-cbf6-4681-bc79-80c93aae2676.png|827](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/67d8b995-cbf6-4681-bc79-80c93aae2676.png) [^3]

 

*Creating some log files with different dates*

*touch -d 20231201 user.log*

*touch -d 20240418 satya.log*

*touch -d 20240419 mitra.log*

*touch -d 20231202 user2.log*

*touch -d 20231202 user2.js*

*touch -d 20231202 cart.js*

*touch -d 20231202 shipping.java*

 

![e6bb5e11-3241-43ba-b4b5-83c8869527ae.png|875.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/e6bb5e11-3241-43ba-b4b5-83c8869527ae.png) [^4]

 

![a43298ee-0ed1-41ac-aac1-0ae890db69fd.png|875.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/a43298ee-0ed1-41ac-aac1-0ae890db69fd.png) [^5]

 

```
find . -type f -mtime +14     --> . represents current directory, f stands for files, +14 more than 14days
```

```
find . -type f -mtime +14   -name "*.log"
```

 

![2131d2f3-45ba-4069-8d10-bc89d5c6802d.png|900.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/2131d2f3-45ba-4069-8d10-bc89d5c6802d.png) [^6]

 

*while IFS= read -r line                    -->     while loop, IFS - Internal field separator, read line by line*

*do*

    *echo "Deleting file: $line"*

    *rm -rf $line*

*done <<< $FILES_TO_DELETE       -->     <<< is input for this while loop*

 

*Script to delete .log files of more than 14days*

![56829e6e-7543-4328-b4b8-b9cc392a4de7.png|726](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/56829e6e-7543-4328-b4b8-b9cc392a4de7.png) [^7]

 

 

```
git status
```

```
git add . ; git commit -m "added .log files deletion script"; git push origin main
```

```
git status
```

![7a2ba76c-8942-4ac2-82e6-ad647b1c132e.png|950.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/7a2ba76c-8942-4ac2-82e6-ad647b1c132e.png) [^8]

 

*#git clone* [*https://github.com/chilops/shellscripts.git*](https://github.com/chilops/shellscripts.git) 

```
cd shellscripts/
```

```
ls -l
```

![021164d9-3374-4663-9b8c-07dc11960f9a.png|856.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/021164d9-3374-4663-9b8c-07dc11960f9a.png) [^9]

 

 

```
sh 15.Delete-old-log.sh        --> deletes .log files which are more than 14days
```

![ef8e4ee1-2d60-4515-9033-200b18cd1788.png|885.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/ef8e4ee1-2d60-4515-9033-200b18cd1788.png) [^10]

 

\

# *<mark style="background-color:#f8914d;">**IFS - Internal Field Separator  -- in detail discussion by using /etc/passwd file**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

***Script***

![bf581ba2-ef29-47c3-98e9-046ec0057e1b.png|806](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/bf581ba2-ef29-47c3-98e9-046ec0057e1b.png) [^11]

 

```
git status
```

```
git add . ; git commit -m "IFS script"; git push origin main
```

```
git status
```

![fa6cf092-58ed-4fe4-9dac-8f987a86fed3.png|844](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/fa6cf092-58ed-4fe4-9dac-8f987a86fed3.png) [^12]

 

```
git pull
```

```
ls
```

```
sh 16.ifs.sh   
```

 

![12ab1ad4-a2bb-486e-bb65-f934a0bd7755.png|853.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/12ab1ad4-a2bb-486e-bb65-f934a0bd7755.png) [^13]

\

\

# *<mark style="background-color:#f8914d;">**Check Disk usage & drop an email**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*monitoring team --> servers, websites*

 

*servers are down/more memory --> alert DevOps Team*

 

*Hard Disk --> just beside our laptop*

*Google/Microsoft Drive --> they are in network, connecting through internet*

 

*Create a volume of 12gb from aws volumes & mount it to Linux machine*

![a79bc005-f171-41bb-a4c9-66a8de59ebe5.png|787.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/a79bc005-f171-41bb-a4c9-66a8de59ebe5.png) [^14]

```
df -hT
lsblk
sudo file -s /dev/xvdf
sudo lsblk -f
sudo mkfs -t xfs /dev/xvdf
sudo mkdir /data
sudo mount /dev/xvdf /data
```

 

![d5cf1997-ce1d-47d2-ad10-6d36d83bd690.png|762](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/d5cf1997-ce1d-47d2-ad10-6d36d83bd690.png) [^15]

 

![250655b3-9798-4428-849c-05b6229cbe2d.png|854](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/250655b3-9798-4428-849c-05b6229cbe2d.png) [^16]

 

![b109db47-0a5b-4aa0-aafb-481cadc9d38a.png|862](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/b109db47-0a5b-4aa0-aafb-481cadc9d38a.png) [^17]

 

![5f330b42-7781-4581-b95e-8d3c607c708b.png|875.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/5f330b42-7781-4581-b95e-8d3c607c708b.png) [^18]

 

![618c5178-8c79-439f-a2e0-0013a0bd7f39.png|736](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/618c5178-8c79-439f-a2e0-0013a0bd7f39.png) [^19]

 

![53857139-8292-4fa7-8cc4-009fb562c90b.png|715](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/53857139-8292-4fa7-8cc4-009fb562c90b.png) [^20]

 

 

```
df -hT | grep -v tmp              --> -v stands except that remaining info(reverse searching)
```

![27f1fdec-fa2d-4880-b815-271a50e192ff.png|637](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/27f1fdec-fa2d-4880-b815-271a50e192ff.png) [^21]

 

\

#  *<mark style="background-color:#f8914d;">**Installing and configuring Gmail setup in centos 8 :**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

```
sudo su -
```

```
 yum -y install postfix cyrus-sasl-plain mailx
```

 

*postfix --> Hit Gmail API*

*cyrus-sasl-plain --> authentication*

*mailx --> command to send email*

 

![f556aa09-bf82-44f3-821a-f4d3f77db2f8.png|836.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/f556aa09-bf82-44f3-821a-f4d3f77db2f8.png) [^22]

 

```
systemctl restart postfix
```

```
systemctl enable postfix
```

 

![e769897e-8cd5-4687-b7e9-af2efaa29d0c.png|820.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/e769897e-8cd5-4687-b7e9-af2efaa29d0c.png) [^23]

 

```
vim /etc/postfix/main.cf
```

![c763445b-d9f0-4cb3-be3a-8062221d95b1.png|732](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/c763445b-d9f0-4cb3-be3a-8062221d95b1.png) [^24]

 

***Shift+G   --> to go to last line & paste the below gmail config to setup gmail in our server.***

 

***Refer -***[*concepts/gmail.MD at master · daws-76s/concepts (github.com)*](https://github.com/daws-76s/concepts/blob/master/gmail.MD) 

 

```
relayhost = [smtp.gmail.com]:587
smtp_use_tls = yes
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_sasl_tls_security_options = noanonymous
```

 

![da62caa8-5806-4e30-a33e-1fd16c60eab6.png|712](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/da62caa8-5806-4e30-a33e-1fd16c60eab6.png) [^25]

 

 

*from_address --> who is sending*

 

*chilukuridevops@gmail.com --> from address*

*chilukurispace@gmail.com  --> to address*

 

 

*Create a 2 step verification & app password for a gmail chilukuridevops@gmail.com*

 

![e1e03483-ff33-4c8f-bd5a-91349b1a91a4.png|689.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/e1e03483-ff33-4c8f-bd5a-91349b1a91a4.png) [^26]

### ***fghpssphxwgzalmx***

\

*\[smtp.gmail.com\]:587 chilukuridevops:**fghpssphxwgzalmx***

###  

![c82fa5bc-d181-4a14-9c01-baa25f13e11a.png|761](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/c82fa5bc-d181-4a14-9c01-baa25f13e11a.png) [^27]

###  

![c82fa5bc-d181-4a14-9c01-baa25f13e11a.png|725](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/c82fa5bc-d181-4a14-9c01-baa25f13e11a.png) [^28]

###  

```
postmap /etc/postfix/sasl_passwd
```

![5d7d2c94-ab4e-44f0-9005-0226af7f3130.png|715](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/5d7d2c94-ab4e-44f0-9005-0226af7f3130.png) [^29]

*Testing an email if its working or not*

```
echo "This is a test mail & Date $(date)" | mail -s "AWS with DEVOPS Practice" chilukurispace@gmail.com     
```

 

![9d1e87a4-c3f6-4a54-bdfe-cfabe603cf4a.png|833.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/9d1e87a4-c3f6-4a54-bdfe-cfabe603cf4a.png) [^30]

 

*Mail setup done & working*

 

![5368db0d-a98e-4960-9313-256594c1908a.png|607](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/5368db0d-a98e-4960-9313-256594c1908a.png) [^31]

 

*Disk usage mail script*

![4b0046ba-2b59-4f0e-9b12-a565cb9e0b62.png|719](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/4b0046ba-2b59-4f0e-9b12-a565cb9e0b62.png) [^32]

 

```
git status
```

```
git add . ; git commit -m "disk usage script"; git push origin main
```

```
git status
```

 

![9ebf3b86-9571-4264-89f5-7e9400a18c90.png|799](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/9ebf3b86-9571-4264-89f5-7e9400a18c90.png) [^33]

 

```
git pull
```

```
sh 17.disk-usage.sh
```

![4ed823e1-3adf-403d-a2c9-978a3a9a4462.png|876.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/4ed823e1-3adf-403d-a2c9-978a3a9a4462.png) [^34]

 

 

*Mail received to chilukurispace@gmail.com*

![612e4b01-75e0-46eb-8e97-0c430fdefc89.png|685](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/612e4b01-75e0-46eb-8e97-0c430fdefc89.png) [^35]

 

 

*If we want proper formatting & template as below.*

 

![32a18802-9a19-46f8-aeb2-faa899b03863.png|352](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/32a18802-9a19-46f8-aeb2-faa899b03863.png) [^36]

 

\

*The above body is converted into html format and placed in template.html file* 

 

*We can convert by using following link  -->* [*Best HTML Viewer, HTML Beautifier, HTML Formatter and to Test / Preview HTML Output (codebeautify.org)*](https://codebeautify.org/htmlviewer) 

\

![7d810a8c-4549-4fa4-b663-ea97e8277d44.png|801.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/7d810a8c-4549-4fa4-b663-ea97e8277d44.png) [^37]

 

*Now create mail.sh script file*

![128b93e0-797d-4a31-a414-8fb8fd145d90.png|777.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/128b93e0-797d-4a31-a414-8fb8fd145d90.png) [^38]

 

 

```
git status
```

```
git add . ; git commit -m "disk usage script"; git push origin main
```

```
git status
```

 

![bb5a8054-7984-452e-97ff-77bf8aecd624.png|833](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/bb5a8054-7984-452e-97ff-77bf8aecd624.png) [^39]

 

```
git pull
```

```
sh 17.disk-usage.sh
```

![cf3f6373-496d-43a7-bb5f-b5914f17bd0f.png|796.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/cf3f6373-496d-43a7-bb5f-b5914f17bd0f.png) [^40]

 

![f4e72c32-5c9d-4287-b15a-8871bfd8a844.png|789.3333740234375](https://images.amplenote.com/8d658766-0f65-11ef-af7b-a6f126245c9e/f4e72c32-5c9d-4287-b15a-8871bfd8a844.png) [^41]

 

#  *<mark style="background-color:#f8914d;">**Delete old log files**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*---------------------*

*1. user has to provide source directory*

*2. action --> archieve/delete*

*3. if he selects archieve --> where is the destination directory*

*4. time --> optional, if he gives take it, otherwise 14 days default*

*5. memory --> optional. if he dont give dont consider, if he gives consider it...*

 

 

*old-logs.sh -s <source-dir> -a <archieve/delete> -d <destination-dir> -t <no-days> -m <memory-in-mb>*

 

*algorithm*

*---------------*

*-s, -a, -d --> check all these inputs, if he dont give tell him the usage....*

 

*source directory exists or not*

*destination directory exists or not*

 

*-a --> archive if he don't give destination dir throw error about destination-dir*

 

 

 

[^1]: Instances (1/1) Info
    C
    Connect
    Instance state
    Action
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    V
    Name _
    Instance ID
    Instance state
    4
    Instance type
    Status check
    Alarm status
    Av
    V
    shellscript
    i-0b6foe722e5ae7af7
    Pending
    t2.micro
    View alarms +
    US

[^2]: SuperPUTTY - 44.204.39.188
    File View Tools Help
    Protocol SSH
    Host 44.204.39.188
    Login
    Password
    Session
    chilops
    - O X
    Commands
    44.204.39.188
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 \~ \]$ \]

[^3]: 44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 \~ \]$ cd /tmp/shellscript-logs
    -bash: cd: /tmp/shellscript-logs: No such file or directory
    44 . 204 . 39.188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 \~ \]$ mkdir /tmp/shellscript-logs
    44 . 204. 39.188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 \~ \]$ cd /tmp/shellscript-logs
    44 . 204.39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 /tmp/shellscript-logs \]$ \[

[^4]: \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20231201 user .log
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ 1s
    user . log
    44 . 204 . 39. 188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20241804 satya. log
    touch: invalid date format '20241804'
    44 . 204 . 39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20240418 satya. log
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20240419 mitra. log
    44 . 204 . 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20231202 user2.log
    44 . 204. 39. 188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ 1s -1
    total 0
    -rw-rw-r-- 1 centos centos 0 Apr 19 00:00 mitra . log
    -rw-rw-r--
    1 centos centos 0 Apr 18 00:00 satya . log
    -rw-rw-r--
    1 centos centos 0 Dec 2 00:00 user2. log
    -rw-rw-r--
    1 centos centos 0 Dec 1 00:00 user . log
    44 . 204.39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ 4

[^5]: \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20231202 user2.js
    44 . 204 . 39. 188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20231202 cart. js
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 /tmp/shellscript-logs \]$ touch -d 20231202 shipping . java
    44 . 204.39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 /tmp/shellscript-logs \]$ 1s -1
    total 0
    rw-rw-r--
    1 centos centos 0 Dec 2 00:00 cart. js
    rw-rw-r-
    1 centos centos 0 Apr 19 00:00 mitra. log
    rw-rw-r--
    1 centos centos 0 Apr 18 00:00 satya . log
    rw-rw-r--
    1 centos centos 0 Dec 2 00:00 shipping . java
    rw-rw-r--
    1 centos centos 0 Dec 2 00:00 user2. js
    rw-rw-r--
    1 centos centos 0 Dec 2 00:00 user2. log
    rw-rw-r--
    1 centos centos 0 Dec 1 00:00 user . log
    44 . 204 . 39.188 \| 172. 31 . 94.56 \| t2.micro
    ITnu

[^6]: \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ find . -type f -mtime +14
    . /user . log
    . /user2 . log
    . /user2. js
    . / cart . js
    . / shipping . java
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ find . -type f -mtime +14 -name "\*.log"
    . /user . log
    . /user2 . log
    44 . 204. 39.188 \| 172. 31. 94.56 \| t2.micro \| null

[^7]: shellscripts > $ 15.Delete-old-log.sh
    1
    #! /bin/bash
    2
    3
    SOURCE_DIR="/tmp/shellscript-logs"
    14
    5
    R=" \\e\[31m"
    6
    G=" \\e\[32m"
    7
    Y=" \\e \[33m"
    8
    N="\\e\[Om"
    9
    10
    if \[ ! -d $SOURCE_DIR \] # ! denotes opposite
    11
    then
    12
    echo -e "$R Source directory: $SOURCE_DIR does not exists. $N"
    13
    fi
    14
    15
    FILES_TO_DELETE=$(find $SOURCE_DIR -type f -mtime +14 -name "\*.log")
    16
    17
    while IFS= read -r line
    18
    do
    19
    echo "Deleting file: $line"
    20
    rm -rf $line
    21
    done <<< $FILES_TO_DELETE

[^8]: PROBLEMS
    OUTPUT
    DEBUG CONSOLE
    TERMINAL
    PORTS
    > powers
    (use "git add <file>..." to include in what will be committed)
    15. Delete-old-log. sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\shellscripts> git add . ; git commit -m "added .log files deletion script"; git push origin main
    warning: in the working copy of '15. Delete-old-log. sh', LF will be replaced by CRLF the next time Git touches it
    \[main 2f6d664\] added . log files deletion script

[^9]: \[ centos@ip-172-31-94-56 \~ \]$ git clone https: //github. com/chilops/shellscripts.git
    Cloning into 'shellscripts'..
    remote: Enumeratiog objects: 73, done.
    remote: Counting objects: 100% (73/73), done.
    remote: Compressing objects: 100% (55/55), done.
    remote: Total 73 (delta 37), reused 53 (delta 17), pack-reused 0
    Receiving objects: 100% (73/73), 8.15 KiB \| 8. 15 MiB/s, done.
    Resolving deltas: 100% (37/37), done.
    44 . 204 . 39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 \~ \]$ 1s
    shellscripts
    44 . 204.39.188 \| 172. 31.94.56 \| t2.micro \| null
    centosdip-172-31-94-56 \~ \]$ cd shellscripts/
    44 . 204. 39.188 \| 172. 31.94.56 \| t2.micro \| https://github. com/chilops/shellscripts.git
    centosdip-172-31-94-56 \~/shellscripts \]$ 1s -1
    total 60
    -rw-rw-r--
    1 centos centos 63 Apr 22 06:05 01.hello-world. sh
    rw-rw-r-
    centos centos 228 Apr 22 06:05 02. variables. sh
    rw-rw-r--
    centos centos 57 Apr 22 06:05 03. variables.sh
    rw-rw-r--
    centos centos 225 Apr 22 06:05 04. variablesArgs. sh
    rw-rw-r-
    centos centos 325 Apr 22 06:05 05. variables.sh
    rw-rw-r--
    centos centos 182 Apr 22 06:05 06. datatypes. sh
    rw-rw-r--
    centos centos 183 Apr 22 06:05 07. arrays. sh
    rw-rw-r-
    centos centos 163 Apr 22 06:05 08 . conditions. sh
    rw-rw-r--
    centos centos 523 Apr 22 06:05 09. install-mysql. sh
    rw-rw-r--
    centos centos 562 Apr 22 06:05 10. functions. sh
    rw-rw-r-
    centos centos 690 Apr 22 06:05 11. logs. sh
    rw-rw-r--
    centos centos 51 Apr 22 06:05 12. loops. sh
    rw-rw-r--
    centos centos 994 Apr 22 06:05 13. install-packages. sh
    rw-rw-r-
    centos centos 137 Apr 22 06:05 14.without-exit-status. sh
    rw-rw-r--
    1
    centos centos 385 Apr 22 06:05 15. Delete-old-log. sh
    04. 39. 188
    172.
    31. 94 . 56

[^10]: 44 . 204.39.188 \| 172. 31.94.56 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-94-56 \~/shellscripts \]$ sh 15. Delete-old-log.sh
    Deleting file: /tmp/shellscript-logs/user . log
    Deleting file: /tmp/shellscript-logs/user2.log
    44 . 204. 39.188 \| 172. 31. 94.56 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centos@ip-172-31-94-56 \~/shellscripts \]$ cd /tmp/shellscript-logs/
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ centosdip-172-31-94-56 /tmp/shellscript-logs \]$ 1s -1
    total 0
    rw-rw-r--
    1 centos centos 0 Dec 2 00:00 cart. js
    rw-rw-r--
    1 centos centos 0 Apr 19 00:00 mitra. log
    -rw-rw-r--
    1 centos centos 0 Apr 18 00:00 satya . log
    -rw-rw-r-- 1 centos centos 0 Dec 2 00:00 shipping . java
    -rw-rw-r-- 1 centos centos 0 Dec 2 00:00 user2. js
    44 . 204.39. 188 \| 172. 31.94.56 \| t2.micro \| null
    \[ centos@ip-172-31-94-56 /tmp/shellscript-logs \]$\|

[^11]: shellscripts > $ 16.ifs.sh
    1
    #! /bin/bash
    2
    file=/etc/passwd
    3
    14
    R="\\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e \[33m"
    7
    N=" \\e\[Om"
    18
    9
    if \[ ! -f $file \] # ! denotes opposite
    10
    then
    11
    echo -e "$R Source directory: $file does not exists. $N"
    12
    fi
    13
    14
    while IFS=":" read -r username password user_id group_id user_fullname home_dir shell_path
    15
    do
    16
    echo "username: $username"
    17
    echo "user ID: $user_id"
    18
    echo "User Full name: $user_fullname"
    19
    done < $file

[^12]: (use "git add <file>..." to include in what will be committed)
    16. ifs . sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\shellscripts> git add . ; git commit -m "IFS script"; git push origin main
    warning: in the working copy of '16. ifs. sh', LF will be replaced by CRLF the next time Git touches it
    \[main 37320c8\] IFS script

[^13]: \[ centosdip-172-31-94-56 \~ \]$ cd shellscripts/
    44 . 204 .39. 188 \| 172. 31.94.56 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-94-56 \~/shellscripts \]$ git pull
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 1), reused 3 (delta 1) , pack-reused 0
    Unpacking objects: 100% (3/3), 504 bytes \| 504.00 KiB/s, done.
    From https: //github. com/chilops/shellscripts
    2f6d664. . 37320c8 main
    -> origin/main
    Updating 2f6d664. . 37320c8
    Fast-forward
    16. ifs . sh \| 19 +++4+++++++++++++4+
    1 file changed, 19 insertions (+)
    create mode 100644 16. ifs.sh
    44 . 204. 39. 188 \| 172. 31.94.56 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-94-56 \~/shellscripts \]$ 1s
    01. hello-world. sh 04. variablesArgs. sh
    07. arrays . sh
    10. functions. sh 13. install-packages. sh
    16. ifs. sh
    02. variables. sh
    05 . variables. sh
    08 . conditions . sh
    11. logs . sh
    14. without-exit-status . sh
    03. variables . sh
    06. datatypes . sh
    09. install-mysql. sh 12. loops. sh
    15. Delete-old-log. sh
    44 . 204. 39.188 \| 172. 31. 94.56 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-94-56 \~/shellscripts \]$ sh 16. ifs.sh
    username: root
    user ID: 0
    User Full name: root
    username: bin
    user ID: 1
    User Full name: bin
    username: daemon
    user ID: 2
    User Full name: daemon
    username: adm
    user ID:

[^14]: Volumes (1/2) Info
    C
    Actions V
    Create volume
    Q Search
    <
    1 >
    -
    Name
    4
    Volume ID
    4
    Type
    4
    Size
    A
    IOPS
    A
    Throughput
    4
    Snapshot
    4
    Created
    Availability Zo
    vol-Od3c31584613bc130
    gp2
    10 GiB
    100
    snap-Od6f961...
    2024/04/22 11:06 GMT +5:...
    us-east-1c
    V
    vol-058deb80b8f938132
    gp3
    12 GB
    3000
    125
    2024/04/22 12:23 GMT +5:...
    us-east-1c

[^15]: \[ centos@ip-172-31-16-230 \~/shell-script \]$ df -hT
    Filesystem
    Type
    Size Used Avail Use% Mounted on
    devtmpfs
    devtmpfs
    347M
    0
    347M
    0% / dev
    tmpfs
    tmpfs
    384M
    0
    384M
    0% /dev/shm
    tmpfs
    tmpfs
    384M
    416K
    384M
    18 /run
    tmpfs
    tmpfs
    384M
    0
    384M
    08 / sys/fs/cgroup
    /dev/xvdal
    xfs
    10G 2.8G
    7. 3G
    28% / -
    tmpfs
    tmpfs
    77M
    0
    77M
    0% /run/user/1000
    3. 89 . 253. 40 \| 172. 31.16.230 \| t2.micro \| https: / /github. com/daws-76s/shell-script. git
    \[ centos@ip-172-31-16-230 \~/shell-script \]$ 1sblk
    NAME
    MAJ : MIN RM SIZE RO TYPE MOUNTPOINT
    xvda
    202:0
    0
    10G
    0 disk
    Lxvdal 202:1
    0
    10G 0 part /
    xvdf
    202: 80
    0
    12G
    0 disk

[^16]: \[ centos@ip-172-31-16-230 \~/shell-script \]$ sudo file -s /dev/xvdf
    / dev/xvdf: data
    3. 89 . 253. 40 \| 172. 31. 16.230 \| t2.micro \| https: / /github. com/daws-76s/shell-script. git
    \[ centos@ip-172-31-16-230 \~/shell-script \]$ sudo Isblk -f
    NAME
    FSTYPE LABEL UUID
    MOUNTPOINT
    xvda
    Lxvdal xfs
    5b4b28dd-1441-4548-9dfa-df0a938ac273 /
    xvdf
    3. 89 . 253. 40 \| 172. 31. 16.230 \| t2.micro \| https: / /github. com/daws-76s/shell-script. git
    \[ centos@ip-172-31-16-230 \~/shell-script \]$

[^17]: \[ centos@ip-172-31-16-230 \~/shell-script \]$ sudo mkfs -t xfs /dev/xvdf
    meta-data=/dev/xvdf
    isize=512
    agcount=4, agsize=786432 blks
    sectsz=512
    attr=2, projid32bit=1
    crc=1
    finobt=1, sparse=1, rmapbt=0
    reflink=1
    bigtime=0 inobtcount=0
    data
    bsize=4096
    blocks=3145728, imaxpct=25
    =
    sunit=0
    swidth=0 blks
    naming
    =version 2
    bsize=4096
    ascii-ci=0, ftype=1
    log
    =internal log
    bsize=4096
    blocks=2560, version=2
    =
    sectsz=512
    sunit=0 blks, lazy-count=1
    realtime =none
    extsz=4096
    blocks=0, rtextents=0
    3. 89 . 253. 40 \| 172. 31.16.230 \| t2.micro \| https: / /github. com/daws-76s/shell-script.git
    \[ centosdip-172-31-16-230 \~/shell-script \]$ sudo mkdir /data

[^18]: \[ centos@ip-172-31-16-230 \~/shell-script \]$ cd /
    3. 89. 253. 40 \| 172. 31.16.230 \| t2.micro \| null
    \[ centos@ip-172-31-16-230 / \]$ 1s -1
    total 20
    lrwxrwxrwx .
    1 root root
    7 Jun 22 2021 bin -> usr/bin
    dr-xr-xr-x.
    6 root root 4096 Dec 18 01:56 boot
    drwxr-xr-x
    2 root root
    6 Dec 18 02:24 data
    drwxr-xr-x
    18 root root 2660 Dec 18 02:21 dev
    drwxr-xr-x.
    90 root root 8192 Dec 18 01:55 etc
    drwxr-xr-x.
    3 root root
    20 Jun 4 2023 home
    lrwxrwxrwx .
    1 root root
    7 Jun 22 2021 lib -> usr/lib
    lrwxrwxrwx .
    1 root root
    9 Jun 22
    2021 lib64
    -> usr/lib64
    drwxr-xr-x.
    2 root root
    6 Jun 22
    2021 media
    drwxr-xr-x.
    2 root root
    6 Jun 22
    2021 mnt
    drwxr-xr-x.
    2 root root
    6 Jun 22 2021 opt
    dr-xr-xr-x 102 root root
    0 Dec 18 01:55 proc
    dr-xr-x--
    3 root root 160 Jun 4 2023 root
    drwxr-xr-x
    25 root root
    820 Dec 18 01:55 run
    lrwxrwxrwx .
    1 root root
    8 Jun 22
    2021 sbin ->
    usr/sbin
    drwxr-xr-x.
    2 root root
    6 Jun 22
    2021 srv
    dr-xr-xr-x
    13 root root
    0 Dec 18 01:55 sys
    drwxrwxrwt.
    root root 125 Dec 18 02:16
    tmp
    drwxr-xr-x.
    13 root root 158 Mar 8 2023 usr
    drwxr-xr-x.
    20 root root 4096 Jun
    4
    2023 var
    3. 89. 253. 40 \| 172. 31. 16.230 \| t2.micro \| null
    \[ centos@ip-172-31-16-230 / \]$ cd
    3. 89. 253. 40 \| 172. 31.16.230 \| t2.micro \| null
    \[ centos@ip-172-31-16-230 \~ \]$

[^19]: 3. 89. 253. 40 \| 172. 31.16.230 \| t2.micro \| null
    \[ centos@ip-172-31-16-230 \~ \]$ sudo mount /dev/xvdf /data
    3. 89 . 253. 40 \| 172. 31.16.230 \| t2.micro \| null

[^20]: \[ centos@ip-172-31-16-230 \~ \]$ df -hT
    Filesystem
    Type
    Size Used Avail Use% Mounted on
    devtmpfs
    devtmpfs
    347M
    0
    347M
    0% /dev
    tmpfs
    tmpfs
    384M
    0
    384M
    0% / dev/shm
    tmpfs
    tmpfs
    384M
    416K
    384M
    18 /run
    tmpfs
    tmpfs
    384M
    0
    384M
    0% / sys/fs/cgroup
    /dev/xvdal
    xfs
    10G
    2.8G
    7. 3G
    28% /
    tmpfs
    tmpfs
    77M
    0
    77M
    0% /run/user/1000
    / dev/xvdf
    xfs
    12G
    118M
    12G
    1% / data
    3. 89 . 253. 40 \| 172. 31.16.230 \| t2.micro \| null

[^21]: \[ centos@ip-172-31-16-230 \~ \]$ df -hT \| grep -v tmp
    Filesystem
    Type
    Size Used Avail Use% Mounted on
    / dev/xvdal
    xfs
    10G
    2. 8G 7. 3G 28% /
    / dev/xvdf
    xfs
    12G 118M
    12G
    18 /data

[^22]: \[ centosdip-172-31-94-56 \~/shellscripts \]$ sudo su
    44 . 204 . 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]# yum -y install postfix cyrus-sasl-plain mailx
    Last metadata expiration check: 0:34:36 ago on Mon 22 Apr 2024 06:32:10 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Repos
    Installing :
    cyrus-sasl-plain
    x86 64
    2.1.27-6. e18 5
    based
    mailx
    x86 64
    12.5-29.e18
    based
    postfix
    x86 64
    2:3.5.8-7.e18
    based
    Installing dependencies:
    libicu
    x86 64
    60.3-2. e18 1
    based
    Transaction Summary
    Install 4 Packages

[^23]: root@ip-172-31-94-56 \~ \]#
    systemctl
    restart postfix
    44 . 204 . 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]# systemctl enable postfix
    Created symlink /etc/systemd/system/multi-user . target. wants/postfix. service - /usr/lib/systemd/system/postfix. service.
    14. 204 . 39. 188
    172.
    94 . 56

[^24]: 44 . 204. 39.188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]# vim /etc/postfix/main. cf

[^25]: smtp_tls_security_level = may
    meta directory = /etc/postfix
    shlib directory = /usr/lib64/postfix
    relayhost = \[smtp . gmail . com\] : 587
    smtp use tls = yes
    smtp_sasl_auth_enable =
    yes
    smtp_sasl_password maps = hash: /etc/postfix/sasl passwd
    smtp_sasl_security_options = noanonymous
    smtp sasl tls security options = noanonymous

[^26]: C
    @ https://myaccount.google.com/u/2/apppasswords?pli=1&rapt=AEjHL4NeeKSzq4Xj6xQaMmwq2NIHfNd5t6HVJVUAD6a_MJCx5qGpjOFaT-KmxR-CJmbe3A...
    A
    Google Account
    App passwords
    App passwords help you sign into your Google Account on older apps and
    services that don't support modern security standards.
    App passwords are
    that use modern se
    Generated app password
    you should check to
    Your app password for your device
    Learn more
    fghp ssph xwgz almx
    Your app passw
    shellscripts
    How to use it
    Go to the settings for your Google Account in the application or device you are
    To create a new al
    trying to set up. Replace your password with the 16-character password shown
    above.
    App name
    Just like your normal password, this app password grants complete access to
    your Google Account. You won't need to remember it, so don't write it down or
    share it with anyone.
    Done

[^27]: \[ rootdip-172-31-94-56 \~ \]# touch /etc/postfix/sasl_passwd
    44 . 204 . 39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ rootdip-172-31-94-56 \~ \]# vim /etc/postfix/sasl passwd
    44 . 204 . 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ rootdip-172-31-94-56 \~ \]# cat /etc/postfix/sasl_passwd
    \[ smtp . gmail. com\] : 587 chilukuridevops : fghpssphxwgzalmx
    44 . 204.39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]

[^28]: \[ rootdip-172-31-94-56 \~ \]# touch /etc/postfix/sasl_passwd
    44 . 204 . 39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ rootdip-172-31-94-56 \~ \]# vim /etc/postfix/sasl passwd
    44 . 204 . 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ rootdip-172-31-94-56 \~ \]# cat /etc/postfix/sasl_passwd
    \[ smtp . gmail. com\] : 587 chilukuridevops : fghpssphxwgzalmx
    44 . 204.39.188 \| 172. 31.94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]

[^29]: \[ rootdip-172-31-94-56 \~ \]# postmap /etc/postfix/sasl_passwd
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]# \|\]

[^30]: root@ip-172-31-94-56 \~ \]# echo "This is a test mail & Date $ (date) " \| mail -s "message" chilukurispace@gmail. com
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    \[ root@ip-172-31-94-56 \~ \]# echo "This is a test mail & Date $ (date)" \| mail -s "AWS with DEVOPS Practice" chilukurispace@g
    mail . com
    44 . 204. 39. 188 \| 172. 31. 94.56 \| t2.micro \| null
    root@ip-172-31-94-56 \~ \]# \[\]

[^31]: Ci
    O
    D
    ...
    AWS with DEVOPS Practice
    Inbox x
    root <chilukuridevops@gmail.com>
    to me
    This is a test mail & Date Mon Apr 22 07:41:08 UTC 2024
    Reply
    Forward

[^32]: shellscripts > $ 17.disk-usage.sh
    H
    #! /bin/bash
    2
    3
    DISK USAGE=$(df -hT \| grep -vE ' tmp \| File' )
    4
    DISK THRESHOLD=1
    5
    message= " "
    6
    while IFS= read line
    8
    do
    9
    usage=$(echo $line \| awk ' {print $6F}' \| cut -d % -f1)
    10
    partition=$(echo $line \| awk ' {print $1F}' )
    11
    if \[ $usage -ge $DISK_THRESHOLD \]
    12
    then
    13
    message+="High Disk Usage on $partition: $usage <br>"
    14
    fi
    15
    done <<< $DISK_USAGE
    16
    17
    echo -e "Message: $message"
    18
    19
    echo "$message" \| mail -s "High Disk Usage" chilukurispace@gmail. com
    20

[^33]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    17. disk-usage . sh
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevOps\\Repos \\shellscripts> git add . ; git commit -m "disk usage alert; git push origin main

[^34]: \[ centosdip-172-31-94-56 \~/shellscripts \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (1/1), done.
    Unpacking objects: 100% (3/3), 279 bytes \| 279.00 KiB/s, done.
    remote: Total 3 (delta 2), reused 3 (delta 2), pack-reused 0
    From https://github. com/chilops/shellscripts
    1331df6. . 2640053 main
    -> origin/main
    Updating 1331df6. . 2640053
    Fast-forward
    17 . disk-usage . sh \| 2 +-
    1 file changed, 1 insertion (+) , 1 deletion (-)
    44 . 204 . 39. 188 \| 172. 31. 94.56 \| t2.micro \| https: / /github.com/chilops/shellscripts.git
    \[ centos@ip-172-31-94-56 \~/shellscripts \]$ sh 17.disk-usage. sh
    Message: High Disk Usage on /dev/xvdal: 32
    High Disk Usage on /dev/xvdc: 1

[^35]: Cloud User <chilukuridevops@gmail.com>
    to me
    High Disk Usage on /dev/xvda1: 32\\nHigh Disk Usage on /dev/xvdc: 1\\n

[^36]: New Message
    2 X
    Recipients
    Subject
    Hello TO_TEAM,
    There is an ALERT_TYPE in the system. Please find the details below and take
    appropriate action.
    BODY
    Regards,
    Monitoring Team

[^37]: shellscripts > <> template.html > @ div
    KP>
    <strong>
    <span style="font-family: verdana, sans-serif; ">Hello TO_TEAM, </span>
    </strong>
    </p>
    <div>
    <strong>
    8
    <span style="font-family: verdana, sans-serif; ">&nbsp; </span>
    9
    </strong>
    10
    </div>
    11
    <div>
    12
    <strong>
    13
    <span style="font-family: verdana, sans-serif; ">There is an&nbsp; <span style="color: #ff0000; " >ALERT_TYPE</span>&nbsp; in the s
    14
    </strong>
    15
    </div>
    16
    <div>
    17
    (strong>
    18
    <span style="font-family: verdana, sans-serif; ">&nbsp; </span>
    19
    </strong>
    20
    </div>
    21
    <div>
    22
    <strong>
    23
    <span style="color: #ff0000; font-family: verdana, sans-serif; font-size: large; ">BODY</span>
    24
    </strong>
    25
    </div>
    26
    <div>
    27
    <strong>
    28
    <span style="font-family: verdana, sans-serif; ">&nbsp; </span>
    29
    </strong>
    30
    </div>
    31
    <div>
    32
    <strong>
    33
    <span style="font-family: verdana, sans-serif; ">Regards, </span>
    34
    </strong>
    35
    </div>
    36
    <div>
    37
    (strong>
    38
    <span style="font-family: verdana, sans-serif; ">Monitoring Team</span>
    39
    / strong>
    40
    </div>

[^38]: shellscripts > $ mail.sh
    1
    #! /bin/bash
    2
    3
    TO_TEAM=$1
    4
    ALERT_TYPE=$2
    15
    BODY=$3
    6
    ESCAPE_BODY=$(printf '%s \\n' "$BODY" \| sed -e 's/\[\]\\/$\*.^\[\]/\\\\&/g' );
    7
    TO_ADDRESS=$4
    8
    SUBJECT=$5
    9
    10
    FINAL_BODY=$ (sed -e "s/TO_TEAM/$TO_TEAM/g" -e "s/ALERT_TYPE/$ALERT_TYPE/g" -e "s/BODY/$ESCAPE_BODY/g" template . html)
    11
    12
    echo "$FINAL_BODY" \| mail -s "$(echo -e "$SUBJECT\\nContent-Type: text/html" )" "$TO_ADDRESS"

[^39]: PROBLEMS
    OUTPUT
    DEBUG CONSOLE
    TERMINAL
    PORTS
    template . html
    no changes added to commit (use "git add" and/or "git commit -a")
    PS E: \\AWSDevops \\Repos \\shellscripts> git add . ; git commit -m "disk usage alert"; git push origin main
    warning: in the working copy of '17. disk-usage. sh', LF will be replaced by CRLF the next time Git touches it
    warning: in the working copy of 'mail. sh', LF will be replaced by CRLF the next time Git touches it
    \[main ac05217\] disk usage alert

[^40]: \[ centos@ip-172-31-94-56 \~/shellscripts \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (1/1), done.
    remote: Total 3 (delta 2), reused 3 (delta 2), pack-reused 0
    Unpacking objects: 100% (3/3), 310 bytes \| 310.00 KiB/s, done.
    From https: //github. com/chilops/shellscripts
    ac05217. . 5d12082 main
    -> origin/main
    Updating ac05217. . 5d12082
    Fast-forward
    17. disk-usage . sh \| 4 ++--
    1 file changed, 2 insertions (+), 2 deletions (-)
    44 . 204. 39.188 \| 172. 31.94.56 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-94-56 \~/shellscripts \]$ sh 17.disk-usage. sh
    Message: High Disk Usage on /dev/xvdal: 32 <br>High Disk Usage on /dev/xvdc: 1 <br>

[^41]: ALERT High Disk Usage Inbox x
    Cloud User <chilukuridevops@gmail.com>
    2:02 PM (0 minutes ago)
    to me
    Hello Devops Team,
    There is an High Disk Usage in the system. Please find the details below and take appropriate action.
    High Disk Usage on / dev/xvda1: 32
    High Disk Usage on /dev/xvdc: 1
    Regards,
    Monitoring Team

