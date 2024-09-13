---
title: 14Day_Shell Scripting
uuid: f0a73d34-0f55-11ef-af7b-a6f126245c9e
version: 173
created: '2024-05-11T10:48:45+05:30'
tags:
  - shell
  - shellscripting
---

***Topics:***

 

1. *<mark style="background-color:#f8d616;">Using loops install any no of packages<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Echo $?  -- To check the exit status success/failure<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Packages installation using shellscripts<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Roboshop-shellscripts<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">MongoDB with shellscripts<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">SED Editor - streamline editor<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">MongoDB full script & execution<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Catalogue full script & execution<!-- {"backgroundCycleColor":"25"} --></mark>*

\

 

# *<mark style="background-color:#f8914d;">**Using loops install any no of packages**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*sh 13-install-packages.sh git mysql gcc postfix net-tools*

 

*$# --> no of arguments (Total count)*

*$@ --> all arguments*

 

 

*1. check root user or not*

*2. if root user*

*check package is already installed or not*

*if installed skip it and tell user, already installed*

*if not installe, install it*

*validate it*

*if not root user*

*throw the error*

 

![caee46ec-1969-45a0-a2ed-f985b2438c1a.png|598](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/caee46ec-1969-45a0-a2ed-f985b2438c1a.png) [^1]

 

```
git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

 

![c0dfd64d-0252-4dff-87b5-68a92be62a20.png|917.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/c0dfd64d-0252-4dff-87b5-68a92be62a20.png) [^2]

 

 

# *<mark style="background-color:#f8914d;">**Echo $?**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Exit status 0 - successful/installed*

*Exit status 1 - not successful/not installed*

 

*$? --> exit status of previous command*

*$0 --> you will get script name*

*$1*

*$2*

*$N*  

*$@    --> its for all arguments*

*$#    --> To know how many arguments passed*

 

 

*-ne --> not equal to*

 

![bf8458fd-205e-4d4c-b094-773acabafd5e.png|874](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/bf8458fd-205e-4d4c-b094-773acabafd5e.png) [^3]

 

 

# *<mark style="background-color:#f8914d;">**Packages installation using shellscripts**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![91bc2d3c-a711-404b-a665-0db4d1adb951.png|664](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/91bc2d3c-a711-404b-a665-0db4d1adb951.png) [^4]

![](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/5132d63e-0ce5-4d9f-b263-0b8bfb50afaf.png)

 

```
 git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

 

*# <mark style="background-color:#f8914d;">sh 13.install-packages.sh git mysql postfix net-tools<!-- {"backgroundCycleColor":"24"} --></mark>*

![ee679f2a-90c8-4e5a-ac67-303ba05fe730.png|936.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/ee679f2a-90c8-4e5a-ac67-303ba05fe730.png) [^5]

 

 

 

# *<mark style="background-color:#f8914d;">**Roboshop-shellscripts**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

 

*Create new folder in laptop & github with "roboshop-shellscripts"*

![dd0ac374-d6b5-40b8-947c-1c547b4e2d9d.png|728.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/dd0ac374-d6b5-40b8-947c-1c547b4e2d9d.png) [^6]

 

 

![f762de90-822e-405e-a241-f5e309408e77.png|837.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/f762de90-822e-405e-a241-f5e309408e77.png) [^7]

 

*Now initialize git in local(laptop) with below commands:*

 

![9f96d84c-33bd-48f8-836c-63172ea9756c.png|668](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/9f96d84c-33bd-48f8-836c-63172ea9756c.png) [^8]

 

 

# *<mark style="background-color:#f8914d;">**MongoDB with shellscripts**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*Now launch an instance with t3.medium /t3.small instances*

![a706fe09-3a58-4512-baeb-a11ca5cdbe31.png|813](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/a706fe09-3a58-4512-baeb-a11ca5cdbe31.png) [^9]

 

 

![80c5ef87-2f05-4ab6-932c-1214d3804b0f.png|691](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/80c5ef87-2f05-4ab6-932c-1214d3804b0f.png) [^10]

 

*Now git add as below*

 

```
git add . ; git commit -m "added mongodb roboshop shellscripts"; git push origin main
```

 

![0afbd3f8-5b5b-49b0-9e33-bf3d4167157f.png|726](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/0afbd3f8-5b5b-49b0-9e33-bf3d4167157f.png) [^11]

 

 

*Now we can check on github central repository*

 

![3574f396-8a13-47bb-88c0-c148920a5e2b.png|716.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/3574f396-8a13-47bb-88c0-c148920a5e2b.png) [^12]

 

 

*Connect to MongoDB instance:*

 

![e8a984eb-a8fb-4e83-81f3-9f236804955e.png|754.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/e8a984eb-a8fb-4e83-81f3-9f236804955e.png) [^13]

 

*Now clone the git roboshop-shellscripts:*

*#git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git) 

 

![c560d18d-cb6a-4c37-8530-3f51e7f5964e.png|807.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/c560d18d-cb6a-4c37-8530-3f51e7f5964e.png) [^14]

 

![d21fd563-d000-4993-a0d1-c76f4de23398.png|872.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/d21fd563-d000-4993-a0d1-c76f4de23398.png) [^15]

 

 

# *SED Editor - streamline editor --> it is useful when you write any scripts & modifies file in background without opening. It’s a temporary editor*<!-- {"collapsed":true} -->

 

*Creation of new lines*

*#sed -e '1 a message' <file name>   --> syntax (-e -- enable, 1 -- first line, a -- appends)*

 

```
sed -e '1 a I am learning shell script' passwd    --> temporary change with  -e
```

```
sed -i '1 a I am learning shell script' passwd     --> permanant change with  -I
```

```
sed -e '1 i I am learning shell script' passwd    --> it modifies 1st line before line
```

 

![80c116ed-b225-4ca3-abc4-c86338fb936e.png|666](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/80c116ed-b225-4ca3-abc4-c86338fb936e.png) [^16]

 

 

*<mark style="background-color:#f8d616;">Lines updating:<!-- {"backgroundCycleColor":"25"} --></mark>*

 

![b225abed-7418-4657-902d-ee702ede1562.png|793.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/b225abed-7418-4657-902d-ee702ede1562.png) [^17]

 

```
sed -e 's/sbin/SBIN/' passwd     --> changing all small sbin to SBIN
```

![](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/eec0ebc2-c052-49c7-910c-dc3c0310d887.png) [^18]

 

![43bc84ab-e811-475c-a990-0b0f74106cfa.png|776](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/43bc84ab-e811-475c-a990-0b0f74106cfa.png) [^19]

 

 

```
sed -i 's/sbin/SBIN/g' passwd    --> it changes all sbin to SBIN in all lines & all words(g - globally, I - permanent change)
```

 

![c537fd8c-1a29-485d-b23c-7b56fd27c96c.png|773](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/c537fd8c-1a29-485d-b23c-7b56fd27c96c.png) [^20]

 

![d8810797-183b-45d3-a482-25fdde3d1bf5.png|760](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/d8810797-183b-45d3-a482-25fdde3d1bf5.png) [^21]

 

 

 

*<mark style="background-color:#f8d616;">Deleting a line<!-- {"backgroundCycleColor":"25"} --></mark>*

```
sed -e '1d' passwd    --> to delete 1st line
```

![cb320f7f-0d2e-44a3-b746-a5e8cc71f0f0.png|688](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/cb320f7f-0d2e-44a3-b746-a5e8cc71f0f0.png) [^22]

 

*Deleting a particular word*

```
sed -e '/learning/ d' passwd    --> d --denotes deletion of a word
```

![f58178c9-c669-487c-b84c-cee10b5a3c44.png|780](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/f58178c9-c669-487c-b84c-cee10b5a3c44.png) [^23]

 

 

# *MongoDB full script & execution*<!-- {"collapsed":true} -->

![046ca235-48b4-4294-a207-36b6ef110f0c.png|652](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/046ca235-48b4-4294-a207-36b6ef110f0c.png) [^24]

![9d9d2da9-aaee-4e8d-87c0-4e2d7c4b771e.png|604](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/9d9d2da9-aaee-4e8d-87c0-4e2d7c4b771e.png) [^25]

 

*Mongodb.repo file*

![c3621ccc-1070-4801-98c0-4e96250f929b.png|757.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/c3621ccc-1070-4801-98c0-4e96250f929b.png) [^26]

 

```
git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

 

```
sudo sh Mongodb.sh
```

 

![476241f6-3572-4e5d-b023-c7547caeee8d.png|646.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/476241f6-3572-4e5d-b023-c7547caeee8d.png) [^27]

 

```
netstat -lntp    --> shows mongodb is running
```

 

![6a8da933-e0da-4ac7-bd6f-64694193b306.png|852.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/6a8da933-e0da-4ac7-bd6f-64694193b306.png) [^28]

 

 

# *<mark style="background-color:#f8914d;">Catalogue full script & execution<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Below is the script*

![42819584-6c5f-4e67-8fa5-aff71aa55517.png|685](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/42819584-6c5f-4e67-8fa5-aff71aa55517.png) [^29]

![ca543f2a-4de8-4602-bed7-4514ae1cdb57.png|901](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/ca543f2a-4de8-4602-bed7-4514ae1cdb57.png) [^30]

![50fb7383-4009-48f5-99bf-c1bb1fe80c00.png|655](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/50fb7383-4009-48f5-99bf-c1bb1fe80c00.png) [^31]

 

*Catalogue.service file*

![b59d0e63-1327-4a84-9bea-3213ec561c22.png|766.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/b59d0e63-1327-4a84-9bea-3213ec561c22.png) [^32]

 

 

*Now launch a t2.micro instance for Catalogue.*

 

![4f996a49-cea5-4adc-883e-5025053cad5f.png|696](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/4f996a49-cea5-4adc-883e-5025053cad5f.png) [^33]

 

 

*Create a record in Route53 for mongodb as below*

 

![2a7b7979-b54f-465d-ab97-bf935fa38474.png|801.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/2a7b7979-b54f-465d-ab97-bf935fa38474.png) [^34]

 

 

*$ git clone* [*https://github.com/chilops/Roboshop-shellscripts.git*](https://github.com/chilops/Roboshop-shellscripts.git)           *--> at catalogue instance*

 

```
git add . ; git commit -m "added 3rd script"; git push origin main         --> at source(laptop)
```

```
git pull                                                                                                               --> at catalogue instance
```

 

![c905a95a-d852-4cb9-9495-a921f7581787.png|844.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/c905a95a-d852-4cb9-9495-a921f7581787.png) [^35]

 

![f01f2e22-d6ba-45cc-a0cb-b05a3bfab6e1.png|840.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/f01f2e22-d6ba-45cc-a0cb-b05a3bfab6e1.png) [^36]

 

![f39c4530-bb6b-40cd-96ea-cf3a117e1b48.png|845.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/f39c4530-bb6b-40cd-96ea-cf3a117e1b48.png) [^37]

 

 

```
sudo sh catalogue.sh     --> Installing catalogue related everything.
```

 

![fd9b13d6-d3a3-475d-b5cb-0c2578251392.png|910.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/fd9b13d6-d3a3-475d-b5cb-0c2578251392.png) [^38]

 

```
netstat -lntp
```

![ac857a8d-0812-4521-bf10-414ef4f2306c.png|906.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/ac857a8d-0812-4521-bf10-414ef4f2306c.png) [^39]

 

```
sudo su -
```

```
less /var/log/messages | grep -i mongodb  --> to check if mongodb connected or not
```

 

![85fe80aa-7ff8-471a-9f13-f1936629f25c.png|914.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/85fe80aa-7ff8-471a-9f13-f1936629f25c.png) [^40]

 

![e5994454-e3ae-42f7-b8e3-6ebe4c5a05b4.png|913.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/e5994454-e3ae-42f7-b8e3-6ebe4c5a05b4.png) [^41]

 

 

*Some testing(stopping catalogue service & restart the process)*

 

```
sudo systemctl stop catalogue
```

```
netstat -lntp
```

```
sudo sh catalogue.sh
```

```
netstat -lntp
```

 

![16a78db0-0187-4338-9a67-00315a490957.png|782.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/16a78db0-0187-4338-9a67-00315a490957.png) [^42]

 

![8ad5ba4e-4fce-41f5-ba07-970ec3d13316.png|781.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/8ad5ba4e-4fce-41f5-ba07-970ec3d13316.png) [^43]

 

```
less /var/log/messages | grep -i mongodb   --> to check logs if mongodb connected or not
```

![3375a7f8-efd4-41a2-b685-2cffde655b1e.png|858.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/3375a7f8-efd4-41a2-b685-2cffde655b1e.png) [^44]

 

*To validate if nodejs18 package installed or not.*

```
sudo su -
```

```
dnf list installed nodejs
```

![c79c9210-a941-4f95-b3b8-c82d8d44dd3a.png|835.3333740234375](https://images.amplenote.com/f0a73d34-0f55-11ef-af7b-a6f126245c9e/c79c9210-a941-4f95-b3b8-c82d8d44dd3a.png) [^45]

 

*<mark style="background-color:#f3de6c;">Now all looks good in MongoDB<!-- {"backgroundCycleColor":"14"} --></mark>*

[^1]: #! /bin/bash
    2
    3
    ID=$(id -u)
    4
    R=" \\e \[31m"
    5
    G=" \\e \[32m"
    6
    N=" \\e\[Om"
    7
    8
    if \[ $ID -ne 0 \]
    9
    then
    10
    echo -e "$R ERROR: : Please run this script with root access $N"
    11
    exit 1 # you can give other than 0
    12
    else
    13
    echo -e "$G You are root user $N"
    14
    fi # fi means reverse of if, indicating condition end
    15
    16
    echo "All arguments passed: $@"

[^2]: \[ root@ip-172-31-29-85 \~/shellscripts \]# git pull
    Already up to date.
    34 . 229. 77. 108 \| 172. 31.29.85 \| t2.micro \| https: / /github. com/chilops/shellscripts.git
    \[ rootdip-172-31-29-85 \~/shellscripts \]# sh 13. install-packages. sh git mysql postfix
    You are root user
    All arguments passed: git mysql postfix
    34 . 229. 77. 108 \| 172. 31.29.85 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ root@ip-172-31-29-85 \~/shellscripts \]#\|

[^3]: 18. 206.213.13 \| 172. 31.21.222 \| t2.micro \| https: / /github.com/daws-76s/shell-script. git
    \[ centosdip-172-31-21-222 \~/shell-script \]$ yum list installed git
    Installed Packages
    git . x86 64
    2. 39.3-1. e18
    18 . 206.213.13 \| 172.31.21.222 \| t2.micro \| https: / /github. com/daws-76s/shell-script.git
    \[ centosdip-172-31-21-222 \~/shell-script \]$ echo $?
    O
    18 . 206.213.13 \| 172.31.21.222 \| t2.micro \| https: / /github.com/daws-76s/shell-script. git
    \[ centos@ip-172-31-21-222 \~/shell-script \]$ yum list installed postfix
    Error: No matching Packages to list
    18. 206.213.13 \| 172. 31.21.222 \| t2.micro \| https: / /github. com/daws-76s/shell-script. git
    \[ centos@ip-172-31-21-222 \~/shell-script \]$ echo $?
    1
    18. 206.213.13 \| 172. 31.21.222 \| t2.micro \| https: / /github. com/daws-76s/shell-script. git
    \[ centos@ip-172-31-21-222 \~/shell-script \]$

[^4]: shellscripts > $ 13.install-packages.sh
    #! /bin/bash
    3
    ID=$(id -u)
    14
    R=" \\e\[31m"
    5
    G=" \\e \[32m"
    6
    Y=" \\e\[33m"
    7
    N="\\e\[Om"
    8
    9
    TIMESTAMP=$ (date +%F-%H: %M: %s)
    10
    LOGFILE=" /tmp/$0-$TIMESTAMP . log"
    11
    12
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    13
    14
    VALIDATE() {
    15
    if \[ $1 -ne 0 \]
    16
    then
    17
    echo -e "$2 ... $R FAILED $N"
    18
    else
    19
    echo -e "$2 ... $G SUCCESS $N"
    20
    fi
    21
    22
    23
    if \[ $ID -ne 0 \]
    24
    then
    25
    echo -e "$R ERROR: : Please run this script with root access $N"
    26
    exit 1 # you can give other than 0
    27
    else
    28
    echo -e "$G You are root user $N"
    29
    fi # fi means reverse of if, indicating condition end
    30
    31
    #echo "All arguments passed: $@"
    32
    # git mysql postfix net-tools
    33
    # package=git for first time
    34
    35
    for package in $@
    36
    do
    37
    yum list installed $package &> > $LOGFILE #check installed or not
    38
    if \[ $? -ne 0 \] #if not installed
    39
    then
    40
    yum install $package -y &>> $LOGFILE # install the package
    41
    VALIDATE $? "Installation of $package" # validate
    42
    else
    43
    echo -e "$package is already installed ... $Y SKIPPING $N"
    44
    fi

[^5]: \[ rootdip-172-31-29-85 \~/shellscripts \]# git pull
    Already up to date.
    34. 229. 77. 108 \| 172. 31.29.85 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ root@ip-172-31-29-85 \~/shellscripts \]# sh 13. install-packages. sh git mysql postfix net-tools
    You are root user
    git is already installed ...
    SKIPPING
    Installation of mysql
    SUCCESS
    Installation of postfix .
    SUCCESS
    net-tools is already installed . ..
    SKIPPING
    34 . 229. 77. 108 \| 172. 31.29.85 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ root@ip-172-31-29-85 \~/shellscripts \]# _

[^6]: XJ
    File Edit Selection View Go Run Terminal Help
    Repos
    EXPLORER
    $ 12.loops.sh
    $ 11.logs.sh
    $ 13.install-packages.sh x
    REPOS
    shellscripts > $ 13.install-packages.sh
    Robosho-shellscripts
    6
    Y=" \\e \[33m"
    7
    N=" \\e\[Om"
    shellscripts
    8
    $ 01.hello-world.sh
    9
    TIMESTAMP=$(date +%F-%H: %M: %S)
    $ 02.variables.sh
    10
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    $ 03.variables.sh
    11

[^7]: Roboshop-shellscripts Public
    & Pin
    Unwatch 1
    Fork 0
    Star 0
    Set up GitHub Copilot
    Add collaborators to this repository
    Use GitHub's Al pair programmer to autocomplete suggestions as you code.
    Search for people using their GitHub username or email address.
    Get started with GitHub Copilot
    Invite collaborators
    Quick setup - if you've done this kind of thing before
    Set up in Desktop
    or
    HTTPS
    SSH
    https://github. com/chilops/Roboshop-shellscripts.git
    Get started by creating a new file or uploading an existing file. We recommend every repository include a README, LICENSE, and .gitignore.

[^8]: chowd@chowdary MINGW64 /
    $ cd /e/awsdevops /Repos /Robosho-shellscripts/
    chowd@chowdary MINGW64 /e/awsdevops /Repos /Robosho-shellscripts (main)
    $ git init
    Initialized empty Git repository in E: /AWSDevops/Repos /Robosho-shellscripts/.git
    chowd@Chowdary MINGW64 /e/awsdevops /Repos /Robosho-shellscripts (main)
    $ git branch -M main
    chowd@chowdary MINGW64 /e/awsdevops/Repos /Robosho-shellscripts (main)
    $ git remote add origin https: //github.com/chilops/Roboshop-shellscripts . git
    chowd@Chowdary MINGW64 /e/awsdevops/Repos/Robosho-shellscripts (main)

[^9]: Name
    MongoDB
    Add additional tags
    Summary
    Number of instances Info
    Application and OS Images (Amazon Machine Image) Info
    1
    An AMI is a template that contains the software configuration (operating system, application server, and
    Software Image (AMI)
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    Centos-8-DevOps-Practice
    below
    ami-Of3c7d07486cad139
    Q devops-practice
    X
    Virtual server type (instance type)
    +3.smal
    AMI from catalog
    Recents
    Quick Start
    Firewall (security group)
    SG_Allow_All
    Amazon Machine Image (AMI)
    Q
    Storage (volumes)
    Centos-8-DevOps-Practice
    1 volume(s) - 10 GiB
    ami-Of3c7d07486cad139
    Browse more AMIs
    Including AMIs from
    AWS, Marketplace and
    X
    the Community
    Free tier: In your first year includes
    Catalog
    Published
    Architecture
    Virtualization
    Root device type ENA Enabled
    750 hours of t2.micro (or t3.micro in
    the Regions in which t2.micro is
    Community
    2024-01-
    x86_64
    hvm
    ebs
    Yes
    unavailable) instance usage on free
    AMIs
    16T13:22:50.00
    tier AMIs per month, 750 hours of
    OZ
    public IPv4 address usage per
    month, 30 GiB of EBS storage, 2
    million IOs, 1 GB of snapshots, and
    100 GB of bandwidth to the
    internet.
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    t3.smal
    Review commands
    Family: t3
    2 GiB Memory Current generation: true
    All generations
    On-Demand SUSE base pricing: 0.0518 USD per Hour
    On-Demand Linux base pricing: 0.0208 USD per Hour
    On-Demand RHEL base pricing: 0.0808 USD per Hour
    Compare instance types
    On-Demand Windows base pricing: 0.0392 USD per Hour
    Additional costs apply for AMIs with pre-installed software
    Key pair (login) Info
    You can use a key pair to securely connect to your instance. Ensure that you have access to the selected key pair
    before you launch the instance.
    Key pair name - required
    KeysC
    Create new key pair

[^10]: roboshop-shell > $ mongodb.sh
    14
    VALIDATE ( ) {
    15
    if \[ $1 -ne 0 \]
    16
    then
    17
    echo -e "$2 ... $R FAILED $N"
    18
    else
    19
    echo -e "$2 ... $G SUCCESS $N"
    20
    fi
    21
    22
    23
    if \[ $ID -ne 0 \]
    24
    then
    25
    echo -e "$R ERROR: : Please run this script with root access $N"
    26
    exit 1 # you can give other than 0
    27
    else
    28
    echo "You are root user"
    29
    fi # fi means reverse of if, indicating condition end
    30
    31
    cp mongo . repo /etc/yum . repos . d/mongo . repo &> > $LOGFILE
    32
    33
    VALIDATE $? "Copied MongoDB Repo"
    34

[^11]: chowd@Chowdary MINGW64 /e/awsdevops/Repos/Robosho-shellscripts (main)
    $ git add . ; git commit -m "added mongodb roboshop shellscripts"; git push origin main
    \[main (root-commit) 4ce7b3e\] added mongodb roboshop shellscripts
    2 files changed, 5 insertions (+)
    create mode 100644 Mongodb . sh
    create mode 100644 mongo . repo
    Enumeratiog objects: 4, done.
    Counting objects: 100% (4/4), done.
    Delta compression using up to 12 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (4/4), 400 bytes \| 400.00 KiB/s, done.
    Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
    To https://github.com/chilops/Roboshop-shellscripts . git
    \*
    \[new branch\]
    main -> main
    chowd@chowdary MINGW64 /e/awsdevops /Repos /Robosho-shellscripts (main)

[^12]: Files
    Roboshop-shellscripts / Mongodb.sh \[
    & main
    Q
    O
    Chowdarychilukuri added new modifications
    Q Go to file
    t
    Code
    Blame 22 lines (18 loc) . 345 Bytes
    Raw
    Mongodb.sh
    #! /bin/bash
    mongo.repo
    W N
    ID=$(id -u)
    R="\\e\[31m"
    5
    G="\\e\[32m"
    6
    Y="le\[33m"
    N="\\e\[om"
    00
    9
    TIMESTAMP=$ (date +%%F-%%H-%%M-%s)
    10
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    11
    12
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    13
    14
    V
    VALIDATE ( ) {
    15
    if \[ $1 -ne 0 \]
    16
    then
    17
    echo -e "$2 . .. $R FAILED $N"
    18
    exit 1
    19
    else
    20
    echo -e "$2 ... $G SUCCESS $N"
    21
    fi
    22

[^13]: SuperPUTTY - 3.84.181.230
    File
    Help
    Protocol SSH
    Host 3.84.181.230
    Login
    Password
    Session chilops
    Commands
    34.229.77.108 3.84.181.230
    Disclaimer :
    This image is designed for only for the lab purpose
    of learning Devops and not recommended at all to use
    in production or any company environments.
    This image is customized and it is having some of
    the default softwares which will help the student
    to start the practice without any issues.
    \*\*Note\*\*: This server is going to shutdown automatically
    in case if it is idle for 60 mins to save
    the cost in AWS.
    Customized Commands available in this Image:
    1.
    labauto
    2 .
    disable-auto-shutdown / enable-auto-shutdown
    3.
    set-hostname
    Last login: Tue Jan 16 13:13:26 2024 from 4. 213.0.213
    3. 84 . 181.230 \| 172. 31.23.78 \| t3. small \| null
    centos@ip-172-31-23-78 \~ \]$
    3. 84 . 181.230 \| 172. 31.23.78 \| t3. small \| null
    centos@ip-172-31-23-78 \~ \]$
    3. 84 . 181. 230 \| 172. 31.23. 78 \| t3. small \| null

[^14]: 3. 84 . 181.230 \| 172. 31.23. 78 \| t3. small \| null
    \[ centosdip-172-31-23-78 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts. git
    Cloning into 'Roboshop-shellscripts' . . .
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (6/6), done.
    remote: Total 7 (delta 0), reused 7 (delta 0), pack-reused 0
    Receiving objects: 100% (7/7), done.
    3. 84. 181.230 \| 172. 31. 23. 78 \| t3. small \| null
    \[ centosdip-172-31-23-78 \~ \]$ cd Roboshop-shellscripts/
    3. 84 . 181.230 \| 172. 31.23.78 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-23-78 \~/Roboshop-shellscripts \]$ 1s -1
    total 8
    -rw-rw-r-- 1 centos centos 345 Apr 16 06:55 Mongodb. sh
    -rw-rw-r--
    1 centos centos 143 Apr 16 06:55 mongo . repo
    3. 84. 181. 230 \| 172. 31.23.78 \| t3. small \| https: //github.com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-23-78 \~/Roboshop-shellscripts \]$ \[\]

[^15]: 52 . 55 . 201.39 \| 172. 31.38.203 \| t3. small \| https: / /github. com/daws-76s/roboshop-shell . git
    \[ centos@ip-172-31-38-203 \~/roboshop-shell \]$ 1s -1
    total 8
    rw-rw-r-- 1 centos centos 642 Dec 14 02:20 mongodb . sh
    -rw-rw-r-- 1 centos centos 142 Dec 14 02:20 mongo . repo
    52 . 55 . 201.39 \| 172. 31.38.203 \| t3. small \| https: / /github. com/daws-76s/roboshop-shell . git
    \[ centos@ip-172-31-38-203 \~/roboshop-shell \]$ sh mongodb . sh
    ERROR: : Please run this script with root access
    52. 55. 201.39 \| 172. 31.38.203 \| t3. small \| https: / /github. com/daws-76s/roboshop-shell . git
    \[ centos@ip-172-31-38-203 \~/roboshop-shell \]$ sudo sh mongodb . sh
    You are root user
    Copied MongoDB Repo
    SUCCESS
    52 . 55 . 201. 39 \| 172. 31. 38.203 \| t3. small \| https: / /github. com/daws-76s/roboshop-shell . git
    \[ centos@ip-172-31-38-203 \~/roboshop-shell \] $

[^16]: 52 . 55 . 201.39 \| 172. 31.38.203 \| t3. small \| null
    \[ centos@ip-172-31-38-203 \~ \]$ Ised -e '1 a I am learning Shell script' passwd
    root : x: 0:0: root: /root: /bin/bash
    I am learning Shell script -
    bin : x: 1:1 :bin: /bin: /sbin/nologin
    daemon : x : 2 : 2 : daemon: /sbin: /sbin/nologin
    adm : x : 3: 4 : adm: /var/adm: /sbin/nologin
    1p: x: 4:7: 1p: /var/spool/1pd: /sbin/nologin
    sync : x : 5:0 : sync: /sbin: /bin/sync
    shutdown : x : 6:0: shutdown: /sbin: /sbin/shutdown
    halt : x: 7:0:halt: /sbin: /sbin/halt
    mail : x : 8: 12 :mail: /var/spool/mail: /sbin/nologin
    operator : x: 11 : 0: operator: /root: /sbin/nologin
    games : x : 12 : 100 : games : /usr/games: /sbin/nologin

[^17]: sed -e 's/word-to-find/word-to-replace/' --> by default first occurence in every lines
    sed -e
    's/word-to-find/word-to-replace/g'

[^18]: 52 . 55 . 201.39 \| 172. 31.38.203 \| t3. small \| null
    \[ centos@ip-172-31-38-203 \~ \]$ sed -e 's/sbin/SBIN/
    passwd

[^19]: root : x: 0:0: root : /root: /bin/bash
    bin : x: 1:1 :bin: /bin: /SBIN/nologin
    I am learning Shell script
    daemon : x : 2 : 2 : daemon: /SBIN: /sbin/nologin
    adm : x : 3 : 4 : adm: /var/adm: /SBIN/nologin
    1p: x: 4:7: 1p: /var/spool/1pd: /SBIN/nologin
    sync : x : 5:0 : sync : /SBIN: /bin/sync
    shutdown : x : 6: 0 : shutdown: /SBIN: /sbin/shutdown
    halt: x: 7:0:halt: /SBIN: /sbin/halt
    mail : x: 8:12 :mail: /var/spool/mail: /SBIN/nologin
    operator : x: 11:0: operator: /root: /SBIN/nologin
    games : x : 12 : 100 : games : /usr/games : /SBIN/nologin
    ftp : x: 14:50 : FTP User: /var/ftp: /SBIN/nologin
    nobody : x : 65534 : 65534 : Kernel Overflow User: / : /SBIN/nologin
    dbus : x : 81 : 81 : System message bus : / : /SBIN/nologin
    systemd-coredump : x : 999: 997: systemd Core Dumper: /: /SBIN/nologin
    systemd-resolve : x: 193: 193 : systemd Resolver: /: /SBIN/nologin
    tss : x: 59: 59: Account used for TPM access: /dev/null: /SBIN/nologin
    polkitd: x: 998: 996: User for polkitd: /: /SBIN/nologin
    unbound: x : 997: 994 : Unbound DNS resolver: /etc/unbound: /SBIN/nologin
    rpc : x : 32: 32 : Rpcbind Daemon: /var/lib/rpcbind: /SBIN/nologin
    sssd : x : 996: 993: User for sssd: / : /SBIN/nologin
    setroubleshoot : x: 995 : 992: : /var/lib/setroubleshoot: /SBIN/nologin
    rpcuser : x : 29:29:RPC Service User: /var/lib/nfs: /SBIN/nologin
    cockpit-ws : x: 994: 991: User for cockpit web service: /nonexisting: /SBIN/nologin
    cockpit-wsinstance : x: 993: 990: User for cockpit-ws instances: /nonexisting: /SBIN/nologin
    chrony : x : 992 : 989: : /var/lib/chrony : /SBIN/nologin
    sshd : x : 74: 74: Privilege-separated SSH: /var/empty/sshd: /SBIN/nologin
    centos : x : 1000: 1000 : Cloud User: /home/centos: /bin/bash

[^20]: \[ centos@ip-172-31-38-203 \~ \]$ sed -i 's/sbin/SBIN/g' passwd

[^21]: root : x: 0:0: root: /root: /bin/bash
    bin: x: 1: 1 :bin: /bin: /SBIN/nologin
    I am learning Shell script
    daemon : x : 2: 2 : daemon : /SBIN: /SBIN/nologin
    adm : x : 3 : 4: adm: /var/adm: /SBIN/nologin
    1p: x: 4:7: 1p: /var/spool/1pd: /SBIN/nologin
    sync : x : 5:0 : sync : /SBIN: /bin/sync
    shutdown : x : 6: 0 : shutdown: /SBIN: /SBIN/shutdown
    halt : x: 7:0: halt: /SBIN: /SBIN/halt
    mail : x : 8: 12 : maj1: /var/spool/mail: /SBIN/nologin
    operator : x: 11:0: operator: /root : /SBIN/nologin
    games : x : 12 : 100: games : /usr/games : /SBIN/nologin
    ftp : x : 14: 50 : FTP User: /var/ftp: /SBIN/nologin
    nobody : x : 65534 : 65534 : Kernel Overflow User: /: /SBIN/nologin
    dbus : x : 81 : 81 : System message bus : /: /SBIN/nologin
    systemd-coredump : x: 999: 997 : systemd Core Dumper: /: /SBIN/nologin
    systemd-resolve : x: 193: 193: systemd Resolver: /: /SBIN/nologin
    tss : x : 59: 59: Account used for TPM access: /dev/null: /SBIN/nologin
    polkitd: x: 998: 996: User for polkitd: /: /SBIN/nologin
    unbound : x : 997: 994 : Unbound DNS resolver: /etc/unbound: /SBIN/nologin
    rpc : x : 32: 32 : Rpcbind Daemon: /var/lib/rpcbind: /SBIN/nologin
    sssd : x : 996: 993 : User for sssd: / : /SBIN/nologin
    setroubleshoot : x: 995 : 992: : /var/lib/setroubleshoot: /SBIN/nologin
    rpcuser : x: 29: 29:RPC Service User: /var/lib/nfs: /SBIN/nologin
    cockpit-ws : x: 994: 991: User for cockpit web service: /nonexisting: /SBIN/nologin
    cockpit-wsinstance : x: 993: 990: User for cockpit-ws instances: /nonexisting: /SBIN/nologin
    chrony : x : 992 : 989: : /var/lib/chrony: /SBIN/nologin
    sshd: x : 74: 74: Privilege-separated SSH: /var/empty/sshd: /SBIN/nologin
    centos : x : 1000: 1000 : Cloud User: /home/centos: /bin/bash

[^22]: \[ centosdip-172-31-38-203 \~ \]$ sed -e '1d' passwd
    bin : x: 1:1 :bin: /bin: /SBIN/nologin
    I am learning Shell script
    daemon : x : 2 : 2 : daemon : /SBIN: /SBIN/nologin
    adm : x : 3: 4 : adm: /var/adm: /SBIN/nologin
    1p :x: 4:7: 1p: /var/spool/1pd: /SBIN/nologin
    sync : x : 5: 0 : sync: /SBIN: /bin/sync
    shutdown : x : 6: 0: shutdown: /SBIN: /SBIN/shutdown
    halt: x: 7:0:halt: /SBIN: /SBIN/halt
    mail : x : 8 :12 : mail: /var/spool/mail: /SBIN/nologin
    operator : x: 11:0: operator: /root: /SBIN/nologin
    games : x : 12 : 100 : games: /usr/games: /SBIN/nologin

[^23]: \[ centos@ip-172-31-38-203 \~ \]$ sed -e '/learning/ d' passwd
    root : x: 0:0: root: /root: /bin/bash
    bin : x: 1:1:bin: /bin: /SBIN/nologin
    daemon : x : 2 : 2 : daemon: /SBIN: /SBIN/nologin
    adm: x : 3 : 4 : adm: /var/adm I/SBIN/nologin
    1p:x: 4:7: 1p: /var/spool/1pd: /SBIN/nologin
    sync : x : 5:0: sync : /SBIN: /bin/sync
    shutdown : x : 6:0: shutdown: /SBIN: /SBIN/shutdown
    halt : x: 7:0: halt: /SBIN: /SBIN/halt
    mail : x : 8:12 :mail: /var/spool/mail: /SBIN/nologin
    operator : x : 11: 0 : operator: /root: /SBIN/nologin
    games : x : 12 : 100 : games : /usr/games : /SBIN/nologin
    ftp : x: 14: 50 : FTP User: /var/ftp: /SBIN/nologin
    nobody : x : 65534 : 65534 : Kernel Overflow User: /: /SBIN/nologin
    dbus : x : 81 : 81 : System message bus: / : /SBIN/nologin
    systemd-coredump : x : 999: 997: systemd Core Dumper: /: /SBIN/nologin

[^24]: Robosho-shellscripts > $ Mongodb.sh
    1
    #! /bin/bash
    W N
    ID=$(id -u)
    4
    R=" \\e\[31m"
    15
    G=" \\e \[32m"
    6
    Y=" \\e\[33m"
    7
    N=" \\e\[Om"
    TIMESTAMP=$(date +%F-%H-%M-%S)
    10
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    11
    12
    echo "script stareted executing at $TIMESTAMP" &> > $LOGFILE
    13
    14
    VALIDATE( ) {
    15
    if \[ $1 -ne 0 \]
    16
    then
    17
    echo -e "$2 . .. $R FAILED $N"
    18
    exit 1
    19
    else
    20
    echo -e "$2 . .. $G SUCCESS $N"
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
    cp mongo . repo /etc/yum. repos . d/mongo . repo &> > $LOGFILE
    33
    34
    VALIDATE $? "Copied MongoDB Repo"
    35
    36
    dnf install mongodb-org -y &> > $LOGFILE
    37
    38
    VALIDATE $? "Installing MongoDB"
    39
    40
    systemctl enable mongod &> > $LOGFILE
    41
    42
    VALIDATE $? "Enabling MongoDB"
    43
    44
    systemctl start mongod &> > $LOGFILE

[^25]: 45
    46
    VALIDATE $? "Starting MongoDB"
    47
    48
    sed -i 's/127.0.0.1/0.0.0.0/g' /etc/mongod . conf &>> $LOGFILE
    49
    50
    VALIDATE $? "Remote access to MongoDB"
    51
    52
    systemctl restart mongod &>> $LOGFILE
    53
    54
    VALIDATE $? "Restarting MongoDB"

[^26]: REPOS
    Robosho-shellscripts > @ mongo.repo
    Robosho-shellscripts
    1
    \[ mongodb-org-4.2\]
    amongo.repo
    2
    name=MongoDB Repository
    $ Mongodb.sh
    3
    baseur1=https: / /repo. mongodb . org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    4
    gpgcheck=0
    shellscripts
    5
    enabled=1
    $ 01.hello-world.sh
    6

[^27]: \[ centos@ip-172-31-23-78 \~/Roboshop-shellscripts \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5), done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
    Unpacking objects: 100% (3/3), 783 bytes \| 783.00 KiB/s, done.
    From https://github. com/chilops/Roboshop-shellscripts
    a7526a2. . 9e9baab main
    -> origin/main
    Updating a7526a2. . 9e9baab
    Fast-forward
    Mongodb . sh \| 34 +++++++++++4
    1 file changed, 33 insertions (+) , 1 deletion(-)
    3. 84. 181.230 \| 172. 31.23.78 \| t3. small \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-23-78 \~/Roboshop-shellscripts \]$ sudo sh Mongodb. sh
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
    3. 84. 181.230 \| 172. 31.23.78 \| t3. small \| https: / /github.com/chilops/Roboshop-shellscripts. git
    \[ centos@ip-172-31-23-78 \~/Roboshop-shellscripts \]$ \[\]

[^28]: 3. 84. 181.230 \| 172. 31.23.78 \| t3. small \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centos@ip-172-31-23-78 \~/Roboshop-shellscripts \]$ netstat -Intp
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
    tcp
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp
    OOOOO
    0 0.0.0.0:27017
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : :111
    : ::\*
    LISTEN
    tcp6
    0
    : : : 22
    LISTEN

[^29]: Robosho-shellscripts > $ catalogue.sh
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
    MONGDB_HOST=mongodb . chowdarychilukuri . in
    9
    10
    TIMESTAMP=$ (date +%F-%H: %M:%s)
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
    echo -e "$2 ... $R FAILED $N"
    19
    exit 1
    20
    else
    21
    echo -e "$2 . .. $G SUCCESS $N"
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
    dnf module enable nodejs : 18 -y &>> $LOGFILE
    38
    39
    VALIDATE $? "Enabling NodeJS: 18"
    40
    41
    dnf install nodejs -y &>> $LOGFILE
    42
    43
    VALIDATE $? "Installing NodeJS: 18"

[^30]: 44
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
    curl -o /tmp/catalogue. zip https://roboshop-builds . s3. amazonaws . com/catalogue. zip &> > $LOGFILE
    59
    60
    VALIDATE $? "Downloading catalogue application"
    61
    62
    cd / app
    63
    64
    unzip -o /tmp/catalogue. zip &>> $LOGFILE
    65
    66
    VALIDATE $? "unzipping catalogue"
    67
    68
    npm install &>> $LOGFILE
    69
    70
    VALIDATE $? "Installing dependencies"
    71
    72
    # use absolute, because catalogue . service exists there
    73
    cp /home/centos/Roboshop-shellscripts/catalogue . service /etc/systemd/system/catalogue . service &>> $LOGFILE
    74
    75
    VALIDATE $? "Copying catalogue service file"
    76
    77
    systemctl daemon-reload &> > $LOGFILE
    78
    79
    VALIDATE $? "catalogue daemon reload"
    80
    81
    systemctl enable catalogue &>> $LOGFILE
    82
    83
    VALIDATE $? "Enable catalogue"
    84
    85
    systemctl start catalogue &> > $LOGFILE
    86

[^31]: 87
    VALIDATE $? "Starting catalogue"
    88
    89
    cp / home/centos/Roboshop-shellscripts/mongo . repo /etc/yum. repos .d/mongo . repo
    90
    91
    VALIDATE $? "copying mongodb repo"
    92
    93
    dnf install mongodb-org-shell -y &> > $LOGFILE
    94
    95
    VALIDATE $? "Installing MongoDB client"
    96
    97
    mongo --host $MONGDB_HOST </app/schema/catalogue . js &> > $LOGFILE
    98
    99
    VALIDATE $? "Loading catalouge data into MongoDB"
    100

[^32]: REPOS
    Robosho-shellscripts > catalogue.service
    Robosho-shellscripts
    1
    \[Unit \]
    catalogue.service
    N
    Description = Catalogue Service
    3
    $ catalogue.sh
    4
    \[Service\]
    amongo.repo
    5
    User=roboshop
    $ mongodb.sh
    6
    Environment=MONGO=true
    > shellscripts
    7
    Environment=MONGO_URL="mongodb : / /mongodb . chowdarychilukuri . in: 27017/catalogue"
    8
    ExecStart=/bin/node /app/server . js
    9
    SyslogIdentifier=catalogue
    10
    11
    \[Install \]
    12
    WantedBy=multi-user . target

[^33]: Name
    Summary
    Catalogue
    Add additional tags
    Number of instances Info
    Application and OS Images (Amazon Machine Image) Info
    Software Image (AMI)
    An AMI is a template that contains the software configuration (operating system, application server, and
    Centos-8-DevOps-Practice
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    ami-Of3c7d07486cad139
    below
    Virtual server type (instance type)
    Q devops-practice
    X
    t2.micro
    Firewall (security group)
    AMI from catalog
    Recents
    Quick Start
    SG_Allow_ALL
    Storage (volumes)
    Amazon Machine Image (AMI)
    Centos-8-DevOps-Practice
    Q
    1 volume(s) - 10 GiB
    ami-Of3c7d07486cad139
    Browse more AMIs
    Including AMIs from
    Free tier: In your first year includes
    X
    wS, Marketplace and
    the Community
    750 hours of t2.micro (or t3.micro in
    Catalog
    Published
    Architecture
    Virtualization
    Root device type ENA Enabled
    the Regions in which t2.micro is
    Community
    2024-01
    <86_64
    pbs
    Yes
    unavailable) instance usage on free
    AMIs
    16T13:22:50.00
    tier AMIs per month, 750 hours of
    20
    public IPV4 address usage per
    month, 30 GIB of EBS storage, 2
    million IOs, 1 GB of snapshots, and
    100 GB of bandwidth to the
    internet
    Instance type Info \| Get advice
    Cancel
    Launch instance
    Instance type
    Review commands
    t2.micro
    Free tier eligible
    Family. t2 1 VCPU 1 GIB Memory Current generation: true
    All generations
    On-Demand Windows base pricing: 0.0162 USD per Hour
    On-Demand SUSE base pricing: 0.0116 USD per Hour
    On-Demand RHEL base pricing: 0.0716 USD per Hour
    Compare instance types
    On-Demand Linux base pricing: 0.0116 USD per Hour
    Additional costs apply for AMIs with pre-installed software
    Key pair (login) Info
    You can use a key pair to securely connect to your instance. Ensure that you have access to the selected key pair
    before you launch the instance.
    Key pair name - required
    Keyso
    Create new key pair
    Network settings Info
    Edit
    Network Info
    vpc-0817cae8968304c06
    Subnet Info
    No preference (Default subnet in any availability zone)
    Auto-assign public IP Info
    Enable
    Additional charges apply when outside of free tier allowance
    Firewall (security groups) \|Info
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    create security group
    Select existing security group

[^34]: Route 53 > Hosted zones > chowdarychilukuri.in > Create record
    Create record Info
    Quick create record
    Switch to wizard
    Record 1
    Delete
    Record name Info
    Record type Info
    mongodb
    .chowdarychilukuri.in
    A - Routes traffic to an IPv4 address and some AWS resources
    Keep blank to create a record for the root domain.
    . Alias
    Value Info
    172.31.22.209
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

[^35]: PS E: \\AWSDevops \\Repos \\Robosho-shellscripts> git add . ; git commit -m "added latest mongodb modifications"; git push origin main
    warning: in the working copy of 'catalogue. sh', LF will be replaced by CRLF the next time Git touches it
    \[main 903818c\] added latest mongodb modifications
    2 files changed, 111 insertions(+)
    create mode 100644 catalogue . service

[^36]: 100.27.27.232 \| 172. 31. 91.221 \| t2.micro \| null
    \[ centos@ip-172-31-91-221 \~ \]$ git clone https://github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts' .. .
    remote: Enumeratiog objects: 14, done.
    remote: Counting objects: 100% (14/14), done.
    remote: Compressing objects: 100% (13/13), done.
    remote: Total 14 (delta 2), reused 12 (delta 0), pack-reused 0
    Receiving objects: 100% (14/14), done.
    Resolving deltas: 100% (2/2), done.
    100 .27.27.232 \| 172. 31. 91.221 \| t2.micro \| null
    \[ centos@ip-172-31-91-221 \~ \]$ 1s -1
    total 0
    drwxrwxr-x 3 centos centos 99 Apr 17 04:58 Roboshop-shellscripts
    100.27.27.232 \| 172. 31.91.221 \| t2.micro \| null
    a1
    221

[^37]: \[ centos@ip-172-31-91-221 \~ \]$ cd Roboshop-shellscripts/
    100 . 27.27.232 \| 172. 31.91.221 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-91-221 \~/Roboshop-shellscripts \]$ 1s -1
    total 16
    rw-rw-r
    1
    centos centos 265 Apr 17 04:58 catalogue . service
    -rw-rw-r-
    centos centos 2140 Apr 17 04:58 catalogue.sh
    rw-rw-r-
    1 centos centos 1043 Apr 17 04:58 Mongodb. sh
    rw-rw-r--
    1
    centos centos 143 Apr 17 04:58 mongo . repo

[^38]: 3. 82 . 110.190 \| 172. 31. 85.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ sudo sh catalogue. sh
    You are root user
    Disabling current NodeJS
    . . .
    SUCCESS
    Enabling NodeJS : 18
    SUCCESS
    Installing NodeJS : 18 .
    SUCCESS
    id: 'roboshop' : no such user
    roboshop user creation
    SUCCESS
    creating app directory
    SUCCESS
    Downloading catalogue application
    SUCCESS
    unzipping catalogue . . .
    SUCCESS
    Installing dependencies . ..
    SUCCESS
    Copying catalogue service file . . .
    SUCCESS
    catalogue daemon reload . . .
    SUCCESS
    Enable catalogue . . .
    SUCCESS
    Starting catalogue . . .
    SUCCESS
    copying mongodb repo . . .
    SUCCESS
    Installing MongoDB client . . .
    SUCCESS
    Loading catalouge data into MongoDB
    . . .
    SUCCESS
    3. 82 . 110.190 \| 172. 31.85.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    72.
    LL

[^39]: \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ netstat -Intp
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
    0 0.0.0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : :111
    :::
    LISTEN
    tcp6
    0 : : : 8080
    LISTEN
    tcp6
    0 : : :22
    LISTEN

[^40]: 3. 82. 110. 190 \| 172. 31.85.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ sudo su -
    Last login: Wed Apr 17 06:46:11 UTC 2024 on pts/0
    3. 82. 110.190 \| 172. 31. 85.170 \| t2.micro \| null
    root@ip-172-31-85-170 \~ \]#

[^41]: root@ip-172-31-85-170 \~ \]# less /var/log/messages \| grep -i mongodb
    Apr 17 06:42:09 ip-172-31-85-170 catalogue \[5534\]: (node: 5534) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monito
    ing engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine, p
    ass option { useUnifiedTopology: true } to the MongoClient constructor.
    Apr 17 06:42:09 ip-172-31-85-170 catalogue \[5534\]: {"level": "info", "time" : 1713336129839, "pid" : 5534, "hostname": "ip-172-31-85-
    170. ec2. internal", "msg" : "MongoDB
    connected" , "v" :1}
    Apr 17 06:49:32 ip-172-31-85-170 dnf \[5900\] : MongoDB Repository
    20 kB/s \| 1.3 kB
    00: 00
    82
    190
    85.

[^42]: centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ sudo systemctl stop catalogue
    3. 82. 110.190 \| 172. 31. 85.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$
    3. 82. 110. 190 \| 172. 31. 85. 170 \| t2.micro \| https: / /github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    Ecp
    0
    0 0. 0.0.0:111
    0.0.0.0:\*
    LISTEN
    Ecp
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    OOO
    0 : : :111
    LISTEN
    tcp6
    0 : : :22
    LISTEN
    3. 82. 110. 190 \| 172. 31. 85.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ sudo sh catalogue. sh
    You are root user
    Disabling current NodeJS . ..
    SUCCESS
    Enabling NodeJS : 18 ...
    SUCCESS
    Installing NodeJS : 18
    SUCCESS
    uid=1001 (roboshop) gid=1001 (roboshop) groups=1001 (roboshop)
    roboshop user already exist SKIPPING
    creating app directory . . .
    SUCCESS
    Downloading catalogue application . .
    SUCCESS
    unzipping catalogue .. . SUCCESS
    Installing dependencies . .
    SUCCESS
    Copying catalogue service file . . .
    SUCCESS
    catalogue daemon reload . . . SUCCESS
    Enable catalogue . .
    SUCCESS
    Starting catalogue . . .
    SUCCESS
    copying mongodb repo . . .
    SUCCESS
    Installing MongoDB client . ..
    SUCCESS
    Loading catalouge data into MongoDB . . .
    SUCCESS

[^43]: copying mongodb repo
    SUCCESS
    Installing MongoDB client . . .
    SUCCESS
    Loading catalouge data into MongoDB . . .
    SUCCESS
    3. 82. 110.190 \| 172. 31. 85.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts. git
    \[ centosdip-172-31-85-170 \~/Roboshop-shellscripts \]$ netstat -Intp
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
    it cp
    0 0.0.0. 0:22
    0.0.0.0:\*
    LISTEN
    OO
    tcp6
    0 :::111
    : : :\*
    LISTEN
    tcp6
    0 : : : 8080
    LISTEN
    tcp6
    0 : : :22
    LISTEN
    3. 82. 110.190 \| 172. 31. 85.170 \| t2.micro \| https: //github.com/chilops/Roboshop-shellscripts.git
    centos@ip-172-31-85-170 \~/Roboshop-shellscripts 1$ 0

[^44]: \[ root@ip-172-31-85-170 \~ \]# less /var/log/messages \| grep -i mongodb
    Apr 17 06:42:09 ip-172-31-85-170 catalogue \[5534\]: (node : 5534) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monit
    ring engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine,
    ass option { useUnifiedTopology: true } to the MongoClient constructor.
    Apr 17 06:42:09 ip-172-31-85-170 catalogue \[5534\]: {"level": "info", "time" : 1713336129839, "pid" : 5534, "hostname" : "ip-172-31-85
    170. ec2. internal", "msg" : "MongoDB connected", "v" :1}
    Apr 17 06:49:32 ip-172-31-85-170 dnf \[5900\] : MongoDB Repository
    20 kB/s \| 1.3 kB
    00:00
    Apr 17 07:07:00 ip-172-31-85-170 catalogue \[6321\]: (node: 6321) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monit
    ring engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine,
    ass option { useUnifiedTopology: true } to the MongoClient constructor.
    Apr 17 07:07:00 ip-172-31-85-170 catalogue \[6321\]: {"level": "info", "time" : 1713337620371, "pid" : 6321, "hostname" : "ip-172-31-85
    170. ec2 . internal", "msg" : "MongoDB
    connected", "v": 1}

[^45]: 3 . 82 . 110.190 \| 172. 31. 85. 170 \| t2.micro \| null
    \[ rootdip-172-31-85-170 \~ \]# anf list installed nodejs
    Installed Packages
    nodejs . x86_64
    1: 18. 9.1-1. module e18. 7. 0+1220+0be9752c
    @appstre

