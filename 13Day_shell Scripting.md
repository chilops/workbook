---
title: 13Day_shell Scripting
uuid: ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07
version: 85
created: '2024-05-11T10:39:39+05:30'
tags:
  - shellscripting
  - shell
---

**Topics:**

1. <mark style="background-color:#f8d616;">Conditions (IF)<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Install MySQL through shell script<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Functions<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Redirections<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Colours in shell scripts<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Loops<!-- {"backgroundCycleColor":"25"} --></mark>

 

# <mark style="background-color:#f8914d;">**Conditions:**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![311a6068-c196-4217-819c-494be3d4c0a7.png|495](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/311a6068-c196-4217-819c-494be3d4c0a7.png) [^1]

 

**OR**

![9a1e336e-6832-446e-96d0-953dd2976c20.png|429](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/9a1e336e-6832-446e-96d0-953dd2976c20.png) [^2]

 

**-gt     -- greaterthan**

**-lt      -- lessthan**

**-ge    -- greaterthan or equalto**

**-le     -- lessthan or equalto**

![bc277d01-3ee1-4076-a1d2-08823f657d39.png|770](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/bc277d01-3ee1-4076-a1d2-08823f657d39.png) [^3]

 

```
Git push
```

```
Git pull
```

![2b60a467-be4d-4e0e-a90b-cbdb2d51471f.png|912.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/2b60a467-be4d-4e0e-a90b-cbdb2d51471f.png) [^4]

 

 

# **Install MySQL through shell script**<!-- {"collapsed":true} -->

\------------------------------

steps:

\-------------

1\. check user is root or not

2\. if root --> if id is not equal to 0, then it is not root user

 proceed

   if not root

 stop and say run with root access

3\. now install mysql

4\. check installed properly.

5\. if success

 then good

   not success

      show what is the error

 

 

**If root user then Id will be 0**

 

![9b71b602-b210-437e-adb3-55dadf25f7b2.png|490](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/9b71b602-b210-437e-adb3-55dadf25f7b2.png) [^5]

 

![0bfd8355-774d-4592-970e-d4bc8a1c8d2e.png|419](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/0bfd8355-774d-4592-970e-d4bc8a1c8d2e.png) [^6]

 

$? It tell previous command is success or fail.. If success then it shows 0, fails means 1,2,3 etc

![cca5d186-22bb-4ada-b05f-1c7afa5967aa.png|889.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/cca5d186-22bb-4ada-b05f-1c7afa5967aa.png)

 

![3acfce04-79cd-49e7-a54b-809879c3a9fc.png|882.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/3acfce04-79cd-49e7-a54b-809879c3a9fc.png)

 

```
Git push
```

```
Git pull
```

 

![36264600-1e09-47a7-90dc-99e3a5ef30ac.png|840.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/36264600-1e09-47a7-90dc-99e3a5ef30ac.png) [^7]

 

 

# <mark style="background-color:#f8914d;">**Functions **<!-- {"backgroundCycleColor":"24"} --></mark>--> code that is repeated again, you can keep in function and call it whenever you want....<!-- {"collapsed":true} -->

 

![0d6f5777-e2fc-4596-9895-6be9ab6cbe1f.png|701](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/0d6f5777-e2fc-4596-9895-6be9ab6cbe1f.png)

 

```
Git push
```

```
Git pull
```

 

![01fa0650-c6a3-4a40-8826-5c1af6aeb930.png|785.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/01fa0650-c6a3-4a40-8826-5c1af6aeb930.png)

 

 

# <mark style="background-color:#f8914d;">**Redirections**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

> --> redirection

 

Redirections

\---------------

command > temp.log --> by default success output only stores here

 

1 --> success

2 --> failure

& --> both success and failures store the output

 

> --> replace previous output

>> --> to append previous output

 

![d4ff8652-586c-48a9-8288-fb79fae998ca.png|875](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/d4ff8652-586c-48a9-8288-fb79fae998ca.png)

 

![58046a0e-ecfb-440b-a409-7ad4d4285b71.png|888](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/58046a0e-ecfb-440b-a409-7ad4d4285b71.png)

 

$? --> exit status of previous command

$0 --> you will get script name

$1

$2

$N  

$@    --> its for all arguments

$#    --> To know how many arguments passed

 

![539d5f46-2c5d-454d-b6d5-4269119f8119.png|542](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/539d5f46-2c5d-454d-b6d5-4269119f8119.png)

 

![7a8e0829-a08e-4bf3-af2f-fc3518340bb6.png|912.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/7a8e0829-a08e-4bf3-af2f-fc3518340bb6.png)

 

![047acd7f-f807-49a0-b2f7-a002e453cae9.png|904.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/047acd7f-f807-49a0-b2f7-a002e453cae9.png) [^8]

 

 

1. Logs.sh

![bb31ebfc-e679-4793-8bd2-45b344e43675.png|740](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/bb31ebfc-e679-4793-8bd2-45b344e43675.png)

 

 

```
git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

 

![8997abcb-c57b-4b5f-90c0-9d2e89428de6.png|835.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/8997abcb-c57b-4b5f-90c0-9d2e89428de6.png)

 

 

![cdd71b74-141e-4b46-8811-f5dc2d481b5e.png|827.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/cdd71b74-141e-4b46-8811-f5dc2d481b5e.png)

 

 

# **Colors in shell scripts:**<!-- {"collapsed":true} -->

 

RED -->        \\e\[31m

GREEN -->   \\e\[32m

YELLOW --> \\e\[33m

normal -->   \\e\[0m

 

```
echo -e "Hello Iam learning \e[31m Shell script"
```

 

![ff13ff46-3f56-41a2-ae9d-6ecd6ad30a06.png|730.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/ff13ff46-3f56-41a2-ae9d-6ecd6ad30a06.png) [^9]

 

 

```
echo -e "Hello Iam learning \e[31m Shell \e[0m script"
```

 

![da98f3dd-f70f-474b-b3ad-c14917a465b8.png|853.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/da98f3dd-f70f-474b-b3ad-c14917a465b8.png) [^10]

 

 

![5d48f779-de67-4291-b558-a16def6ef8ed.png|580](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/5d48f779-de67-4291-b558-a16def6ef8ed.png) [^11]

 

 

```
git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

 

![318885eb-75a8-4ece-bfdf-09d609ebeff0.png|738](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/318885eb-75a8-4ece-bfdf-09d609ebeff0.png) [^12]

 

To check how failure will be in same script 11.log.sh:

![540914a8-2371-4ea3-a65c-e6ffdb8916fb.png|471](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/540914a8-2371-4ea3-a65c-e6ffdb8916fb.png) [^13]

 

```
git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

![9dac13f3-2f0f-4c35-b159-3c1406c1c1c5.png|738.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/9dac13f3-2f0f-4c35-b159-3c1406c1c1c5.png) [^14]

 

 

# <mark style="background-color:#f8914d;">**Loops:**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![cd372444-f730-44a1-9ccd-f9fc5cf6e8ed.png|390](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/cd372444-f730-44a1-9ccd-f9fc5cf6e8ed.png) [^15]

 

```
git add . ; git commit -m "added 3rd script"; git push origin main
```

```
git pull
```

 

![b6c90373-d72f-45f4-b682-dd5e9b8ec812.png|755.3333740234375](https://images.amplenote.com/ab5d61fa-0f54-11ef-9e6a-2e40d90dfe07/b6c90373-d72f-45f4-b682-dd5e9b8ec812.png) [^16]

 

[^1]: if (expression) {
    statement if expression is true
    else{
    statement if expression is false

[^2]: if (expression) {
    statement if expression is true
    else if (expression) {
    statement if expression is true
    else if (expression) {
    else{
    statement if expression is false

[^3]: EXPLORER
    . . .
    plesArgs.sh
    $ 05.variables.sh
    $ 06.datatypes.sh
    $ 07.arrays.sh
    $ 08
    REPOS
    shellscripts > $ 08.conditions.sh
    shellscripts
    H
    #! /bin/bash
    $ 01.hello-world.sh
    2
    3
    NUMBER=$1
    $ 02.variables.sh
    4
    $ 03.variables.sh
    15
    if \[ $NUMBER -gt 100 \]
    $ 04.variablesArgs.sh
    16
    then
    $ 05.variables.sh
    7
    echo "Give number $NUMBER is greater than 100"
    $ 06.datatypes.sh
    8
    else
    $ 07.arrays.sh
    9
    echo "Give number $NUMBER is not greater than 100"
    $ 08.conditions.sh
    10
    fi

[^4]: \[ root@ip-172-31-93-10 /home/centos/shellscripts \]# sh 08. conditions. sh 40
    Give number 40 is not greater than 100
    3. 95. 189. 142 \| 172. 31.93.10 \| t2.micro \| https: //github. com/Chowdarychilukuri/shellscripts.git
    \[ root@ip-172-31-93-10 /home/centos/shellscripts \]# sh 08. conditions. sh 200
    Give number 200 is greater than 100

[^5]: \[ root@ip-172-31-21-222 \~ \]# id
    uid=0 (root) gid=0 (root) groups=0 (root)
    18 .206.213.13 \| 172. 31.21.222 \| t2.micro \| null
    \[ root@ip-172-31-21-222 \~ \]# id -u
    O
    18 . 206.213.13 \| 172. 31.21.222 \| t2.micro \| null
    \[ root@ip-172-31-21-222 \~ \]# id centos -u
    1000

[^6]: $? --> if success, it has 0
    if failure, not zero

[^7]: \[ root@ip-172-31-93-10 /home/centos/shellscripts \]# sh 09. install-mysql. sh
    You are root user
    Last metadata expiration check: 0:01:28 ago on Thu 14 Dec 2023 09:38:10 AM UTC.
    Package mysql-8. 0.26-1 . module e18 . 4. 0+915+de215114.x86 64 is already installed.
    Dependencies resolved.
    Nothing to do.
    Complete!
    Installing MySQL is SUCCESS
    Last metadata expiration check: 0:01:31 ago on Thu 14 Dec 2023 09:38:10 AM UTC.
    Package git-2. 39.3-1. e18. x86 64 is already installed.
    Dependencies resolved.
    Nothing to do.
    Complete!
    Installing GIT is SUCCESS

[^8]: 34. 229. 194.209 \| 172. 31.17.228 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-17-228 \~/shellscripts \]$ sudo sh 06. datatypes.sh 100 300 100
    Total is 400
    How many arguments passed: : 3
    All arguments passed: : 100 300 100
    Script name: : 06. datatypes . sh

[^9]: 34 . 229. 194.209 \| 172.31.17.228 \| t2.micro \| https: //github.com/chilops/shellscripts.git
    \[ centosdip-172-31-17-228 \~/shellscripts \]$ echo -e "Hello Iam learning \\e \[31m Shell script"
    Hello Iam learning Shell script

[^10]: \[ centosdip-172-31-17-228 \~/shellscripts \]$ echo -e "Hello Iam learning \\e \[31m Shell \\e \[0m script"
    Hello Iam learning
    Shell
    script

[^11]: shellscripts > $ 11.logs.sh
    #! /bin/bash
    2
    3
    ID=$(id -u)
    4
    TIMESTAMP=$ (date +%F-%H-%M-%s)
    5
    R=" \\e\[31m"
    6
    G=" \\e \[32m"
    7
    N=" \\e \[Om"
    8
    9
    LOGFILE="/tmp/$0-$TIMESTAMP . log"
    10
    11
    echo "Script started executing at $TIMESTAMP" &> > $LOGFILE
    12
    13
    VALIDATE ( ) {
    14
    if \[ $1 -ne 0 \]
    15
    then
    16
    echo -e "ERROR: : $2 . .. $R FAILED $N"
    17
    exit 1
    18
    else
    19
    echo -e "$2 . .. $G SUCCESS $N"
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
    yum install mysql -y &>> $LOGFILE
    32
    33
    VALIDATE $? "Installing MySQL"
    34
    35
    yum install git -y &>> $LOGFILE

[^12]: \[ centosdip-172-31-17-228 \~/shellscripts \]$ sudo sh 11. logs. sh
    You are root user
    Installing MySQL . .
    SUCCESS
    Installing GIT
    SUCCESS

[^13]: yum install myssql
    -y &> > $LOGFILE

[^14]: 34 . 229. 194.209 \| 172. 31.17.228 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centos@ip-172-31-17-228 \~/shellscripts \]$ sudo sh 11. logs. sh
    You are root user
    ERROR: : Installing MySQL
    . . .
    FAILED
    34 . 229. 194.209 \| 172.31. 17.228 \| t2.micro \| https: //github.com/chilops/shellscripts.git
    \[ centosdip-172-31-17-228 \~/shellscripts \]$ cat /tmp/
    11. logs. sh-2024-04-15-05: 41 : 49.log
    11 . logs. sh-2024-04-15-06:02:17.log
    11. logs. sh-2024-04-15-06-04-29.log
    11 . logs. sh-2024-04-15-06-07-01.log
    11 . logs. sh-2024-04-15-06-07-39.log
    11 . logs. sh-2024-04-15-06-08-49.log
    11 . logs. sh-2024-04-15-06:11: 46. log
    idle . out
    systemd-private-9ed90a62e85d4dd5a6fb100050d9ad4f-chronyd. service-VYqlwr/
    34 . 229. 194.209 \| 172. 31.17.228 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centosdip-172-31-17-228 \~/shellscripts \]$ cat /tmp/11.logs. sh-2024-04-15-06:11: 46.log
    Script started executing at 2024-04-15-06:11: 46
    Last metadata expiration check: 1:05:12 ago on Mon 15 Apr 2024 05:06:35 AM UTC.
    No match for argument: myssql
    Error: Unable to find a match: myssql

[^15]: shellscripts > $ 12.loops.sh
    1
    #! /bin/bash
    12
    3
    for i in {1. .19}
    14
    do
    5
    echo "$1"
    6
    done

[^16]: centosdip-172-31-17-228 \~/shellscripts \]$ sudo sh 12. loops. sh
    16
    18
    19
    34 . 229. 194.209 \| 172. 31. 17.228 \| t2.micro \| https: //github. com/chilops/shellscripts.git
    \[ centos@ip-172-31-17-228 \~/shellscripts \]$

