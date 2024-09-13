---
title: 22&23Day_Ansible
uuid: 2f97211e-0b62-11ef-9fa6-5658f55e0c13
version: 548
created: '2024-05-06T10:06:20+05:30'
tags:
  - ansible
---

<mark style="background-color:#f8d616;">**Topics:**<!-- {"backgroundCycleColor":"25"} --></mark>

1. *<mark style="background-color:#f8d616;">How to run in background and storing output<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Roles in Ansible<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *<mark style="background-color:#f8d616;">MongoDB setup<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *<mark style="background-color:#f8d616;">Catalogue setup<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">ansible.cfg usage<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"offset":2} -->

1. <mark style="background-color:#f8d616;">Tags concept in Ansible<!-- {"backgroundCycleColor":"25"} --></mark>

\

\

# *<mark style="background-color:#f8914d;">**How to run in background and storing output**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
nohup ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 mysql.yaml & >> /dev/null
```

```
tail -f nohup.out
```

\

![c2baceac-5c73-4265-8039-b32cd0dedbc7.png|989.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/c2baceac-5c73-4265-8039-b32cd0dedbc7.png)

\

\

# <mark style="background-color:#f8914d;">**Roles in Ansible**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

*Roles is like DRY(Don't Repeat Yourself) principle. It will have proper directory structure to keep our configuration, we can share roles with other users.*

\

*Roles let you automatically load related vars, files, tasks, handlers, and other Ansible artifacts based on a known file structure. After you group your content into roles,* 

*you can easily reuse them and share them with other users.*

\

![474a12ec-d0db-4fd2-9391-f00fb723445b.png|782](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/474a12ec-d0db-4fd2-9391-f00fb723445b.png)

\

\

*Creating Roles directories as below and copy inventory files:*

![9e603f11-31c8-4803-bd06-53fcfc926be7.png|838](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/9e603f11-31c8-4803-bd06-53fcfc926be7.png)

\

![416e7030-f89a-4596-b5ae-10ff5308f69c.png|927.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/416e7030-f89a-4596-b5ae-10ff5308f69c.png)

\

*Create main.yaml code*

\

![3b64510f-0a72-461b-a16b-bc43408ecac8.png|856](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/3b64510f-0a72-461b-a16b-bc43408ecac8.png)

\

# *<mark style="background-color:#f8914d;">**MongoDB setup**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*mail.yaml code under roles/mongodb/tasks*

\

![3c0365db-4e0c-4ebb-bff4-4311b077497a.png|683](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/3c0365db-4e0c-4ebb-bff4-4311b077497a.png)

\

*Creating a new repository:*

![9a79e62c-b535-40dc-8744-d617ddb2ee40.png|881.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/9a79e62c-b535-40dc-8744-d617ddb2ee40.png)

\

\

```
 git init
 git branch -M main
 git remote add origin git@github.com:chilops/roboshop-ansible-roles.git
 git add . ; git commit -m "roles"; git push origin main
```

\

![6a8f9ccc-0daa-476d-8884-0be59f9f4be6.png|914](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/6a8f9ccc-0daa-476d-8884-0be59f9f4be6.png)

\

*On Ansible server*

```
git clone  https://github.com/chilops/roboshop-ansible-roles.git
ls
cd roboshop-ansible-roles/
ls
```

![c7df4615-ed46-49f2-bec4-20957a8e3473.png|1069.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/c7df4615-ed46-49f2-bec4-20957a8e3473.png)

\

*Creating files folder & mongodb.repo data into it.*

![7ee6ee1b-4306-433a-86ee-4782962713e0.png|1064.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/7ee6ee1b-4306-433a-86ee-4782962713e0.png)

\

\

```
git status
```

```
git add . ; git commit -m "mongodb using roles"; git push origin main
```

```
git status
```

![89e4f5cc-b09e-4cb4-ab79-fbc099f389d2.png|911](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/89e4f5cc-b09e-4cb4-ab79-fbc099f389d2.png)

\

\

```
git pull
```

![e3d254bc-82db-4166-bfd8-dc1494836efd.png|974](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/e3d254bc-82db-4166-bfd8-dc1494836efd.png)

\

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 -e component=mongodb main.yaml
```

![81c0e82f-35a9-45ea-84ac-c2526ed58275.png|1115.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/81c0e82f-35a9-45ea-84ac-c2526ed58275.png)

\

\

# *<mark style="background-color:#f8914d;">**Catalogue setup**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*Now create folders **catalogue** under **files, tasks** as below*

![74528049-2a14-4c4b-8230-5c909211dd82.png|351](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/74528049-2a14-4c4b-8230-5c909211dd82.png) [^1]

\

*create a **common** folder which is used for common data*

*<mark>common also a role where you can keep common things between all the roles and call it whenever required</mark>*

\

![f4d9a45b-5a9f-481d-ba70-8002caf2051f.png|322](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/f4d9a45b-5a9f-481d-ba70-8002caf2051f.png)

\

*under **common** directory create **tasks** directory & under **main.yaml** file*

![2c0be329-ea0c-4bc3-b49e-c010e403862a.png|860](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/2c0be329-ea0c-4bc3-b49e-c010e403862a.png) [^2]

\

\

*Under common directory we created app-setup.yaml code   -- this is commonly used to create app folder & download data & unzip for catalogue etc.*

![f07848df-1ccc-43af-a60e-d0bb6182aefe.png|864.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/f07848df-1ccc-43af-a60e-d0bb6182aefe.png) [^3]

\

***catalogue is a role***

***common is a role***

*I want to call a task in common role in catalogue role.*

\

Under Catalogue task - main.yaml code -- whci calling app-setup from common role(folder)

![28fa74f2-d087-4e7a-9913-1a5a82036173.png|807](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/28fa74f2-d087-4e7a-9913-1a5a82036173.png)

\

```
git status
```

```
git add . ; git commit -m "catalogue roles"; git push origin main
```

```
git status
```

\

![f820f9ff-b792-4e90-8a18-820ebebe373f.png|838](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/f820f9ff-b792-4e90-8a18-820ebebe373f.png)

\

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 -e component=catalogue main.yaml
```

![2d2d69f6-35e6-4c03-a931-48e01b64c947.png|962.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/2d2d69f6-35e6-4c03-a931-48e01b64c947.png)

\

\

***Nodejs.yaml** code in common/tasks folder*  

![9ab69a48-0c49-491a-b468-4b0899d572c5.png|866.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/9ab69a48-0c49-491a-b468-4b0899d572c5.png)

\

*Updating **nodejs.yaml** code in **catalogue/tasks main.yaml** code as below*

![8886c94b-8677-498d-af6a-81df5e3bc1d1.png|878](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/8886c94b-8677-498d-af6a-81df5e3bc1d1.png)

\

\

*<mark style="background-color:#f8d616;">30.00 (Skipping this Ansible roles concept, but all to code updated in roboshop-ansible-roles)<!-- {"backgroundCycleColor":"25"} --></mark>*

\

*\*\*\* This -vvv will give you entire output with all errors*

```
ansible-playbook -vvv -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 -e component=catalogue main.yaml   
```

\

# *<mark style="background-color:#f8914d;">**ansible.cfg usage**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/3bae3d30-8bcc-4a98-b3c3-b4032177a8ad.png)

![e6fb8107-f45f-42d6-8a34-bccbe994798e.png|749](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/e6fb8107-f45f-42d6-8a34-bccbe994798e.png)

\

*Now we can use command without user name, password & inventory, since we placed details in ansible.cfg*

```
ansible-playbook -e component=mongodb main.yaml
```

![9ed7e05f-d846-4730-af1f-1b51ff937eba.png|933.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/9ed7e05f-d846-4730-af1f-1b51ff937eba.png)

\

<mark>Skipping most of the notes in day23, if needed refer session23.</mark>

\

# *<mark style="background-color:#f8914d;">**Tags concept in Ansible**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

tags.yaml code

![20c9468a-a0b6-4858-a28e-63b4dd80dfc3.png|517](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/20c9468a-a0b6-4858-a28e-63b4dd80dfc3.png) [^4]

\

```
git status
```

```
git add . ; git commit -m "catalogue roles"; git push origin main
```

```
git status
```

![cb811256-5df3-4e48-8f6b-fc6ace2a1e88.png|859](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/cb811256-5df3-4e48-8f6b-fc6ace2a1e88.png) [^5]

\

```
git pull
```

```
ansible-playbook -t devops 16.tags.yaml
```

or

```
ansible-playbook -t aws 16.tags.yaml
```

![1e9880e3-bec1-4457-9716-4211dfa3dcbf.png|1028.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/1e9880e3-bec1-4457-9716-4211dfa3dcbf.png)

\

![8a483ed0-fefd-476d-8588-d16a8eac65bf.png|1039.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/8a483ed0-fefd-476d-8588-d16a8eac65bf.png)

\

*<mark>when you want to stop the service, load new code, start the service when we get new releases. At that time we can use tags</mark>*

*Deployment.yaml code    -- which we can use -tags*

![7bbaac7d-6708-47a5-b9d8-9e5bbcd69e1f.png|914.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/7bbaac7d-6708-47a5-b9d8-9e5bbcd69e1f.png) [^6]

\

```
 ansible-playbook -e component=catalogue -t deployment main.yaml
```

![83956db2-ca1f-4b23-99cc-b2e14a12570b.png|959.3333740234375](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/83956db2-ca1f-4b23-99cc-b2e14a12570b.png) [^7]

\

*Now catalogue is running fine after new deployment*

![7dc866e1-b17b-4cea-80e8-d0af3073d773.png|908](https://images.amplenote.com/2f97211e-0b62-11ef-9fa6-5658f55e0c13/7dc866e1-b17b-4cea-80e8-d0af3073d773.png)

[^1]: v roboshop-ansible-roles
    v roles
    catalogue -
    V
    files
    v tasks
    mongodb
    > files
    > tasks

[^2]: EXPLORER
    $ roboshop.sh
    inventory.ini
    ! main.yaml .. \\mongodb\\.
    REPOS
    roboshop-ansible-roles > roles > common > tasks > ! main.yaml
    > Ansible
    1
    > Concepts
    > Robosho-shellscripts
    M
    > roboshop-ansible
    roboshop-ansible-roles
    v roles
    > catalogue
    v common \\ tasks
    ! main.yaml
    > mongodb
    E inventory.ini
    ! main.yaml
    > shellscripts

[^3]: EXPLORER
    $ roboshop.sh
    E inventory.ini
    ! main.yaml .. \\mongodb\\.
    ! main.yaml .. \\catalogue\\.
    REPOS
    roboshop-ansible-roles > roles > common > tasks > ! app-setup.yaml
    > Ansible
    - name: create roboshop user
    > Concepts
    2
    ansible . builtin . user :
    13
    > Robosho-shellscripts
    M
    name: roboshop
    4
    > roboshop-ansible
    15
    - name: Recursively remove app directory
    v roboshop-ansible-roles
    6
    ansible . builtin . file:
    roles
    7
    path: /app
    > catalogue
    8
    state: absent
    common \\ tasks
    9
    ! app-setup.yaml-
    10
    name: create app directory
    11
    ! main.yaml
    ansible . builtin. file:
    12
    path: /app
    > mongodb
    13
    state: directory
    inventory.ini
    14
    ! main.yaml
    15
    name: "download {{component}} application"
    > shellscripts
    16
    ansible . builtin . get_url:
    17
    url: "https://roboshop-builds . s3 . amazonaws . com/{{component} } . zip"
    18
    dest: /tmp
    19
    20
    - name: "extract {{component}} application"
    21
    ansible . builtin . unarchive:
    22
    src: "/tmp/{{component}} . zip"
    23
    dest: / app
    24
    remote_src: yes

[^4]: Ansible > ! 16.tags.yaml
    name: ping playbook
    2
    hosts: localhost
    3
    tasks :
    4
    -
    name: ping the server
    5
    ansible . builtin . ping:
    6
    7
    name: print message
    8
    ansible . builtin . debug :
    9
    msg: "Hello Devops"
    10
    tags :
    11
    - devops
    12
    13
    name: print message
    14
    ansible . builtin . debug :
    15
    msg: "Hello AWS"
    16
    tags :
    17
    -
    aws

[^5]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    16. tags . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "tags concept"; git push origin main

[^6]: REPOS
    roboshop-ansible-roles > roles > common > tasks > ! deployment.yaml
    Ansible
    1
    name: "stop {{component}}"
    > Concepts
    tags :
    W
    > New folder
    deployment
    14
    ansible . builtin. service:
    > Robosho-shellscripts
    M
    15
    name: "{{component}}"
    > roboshop-ansible
    6
    state: stopped
    roboshop-ansible-roles
    7
    group_vars
    8
    name: Recursively remove app directory
    ! all.yaml
    9
    tags :
    v roles
    10
    deployment
    11
    cart
    ansible . builtin. file:
    12
    path: /app
    files
    13
    state: absent
    cart.service
    14
    #force: yes
    tasks
    15
    #recurse: yes
    ! main.yaml
    16
    > templates
    17
    name: create app directory
    18
    catalogue
    tags :
    19
    deployment
    v tasks
    20
    ansible . builtin. file:
    ! main.yaml
    21
    path: /app
    > templates
    22
    state: directory
    common
    23
    > files
    24
    name: "download {{component}} application"
    tasks
    25
    tags :
    26
    app-setup.yaml
    deployment
    27
    ansible . builtin . get_url:
    deployment.yaml
    28
    url: "https://roboshop-builds . s3 . amazonaws . com/{{component} } . zip"
    go.yaml
    29
    dest: /tmp
    java.yaml
    30
    main.yaml
    31
    name: "extract {{component}} application"
    mongodb-setup.yaml
    32
    tags :
    33
    ! mysql-setup.yaml
    deployment
    34
    ansible. builtin . unarchive:
    nodejs.yaml
    35
    src: "/tmp/{{component}} . zip"
    python.yaml
    36
    dest: /app
    systemd.yaml
    37
    remote_src: yes
    > dispatch
    38
    > mongodb
    39
    name: Install dependencies
    40
    > mysql
    tags :
    41
    deployment
    > payment
    42
    ansible. builtin. command: npm install
    > OUTLINE
    43
    args :
    TIMELINE
    44
    chair : /app

[^7]: 54 . 90. 76.82 \| 172. 31.29. 141 \| t2.micro \| https: / /github. com/daws-76s/roboshop-ansible-roles . git
    \[ centos@ip-172-31-29-141 \~/roboshop-ansible-roles \]$ ansible-playbook -e component=catalogue -t deployment main. yaml
    PLAY \[install catalogue\] \*\*\*\*\*\*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*\*
    ok: \[catalogue . daws76s . online\]
    TASK \[common : stop catalogue\] \*\*\*\*\*\*\*\*
    \* \*
    ok: \[catalogue . daws 76s . online\]
    TASK \[common : Recursively remove app directory\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
    \* \* \* \*
    ok: \[catalogue . daws 76s . online\]
    TASK \[common : create app directory\]
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    changed: \[catalogue . daws76s . online\]
    TASK \[common : download catalogue application\]
    \* \* \* \* \* \* \* \* \* \*
    ok: \[catalogue . daws76s . online\]
    TASK \[common : extract catalogue application\]
    \* \* \* \* \*

