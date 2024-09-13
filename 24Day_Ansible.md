---
title: 24Day_Ansible
uuid: 1f222abc-0cf8-11ef-9bc9-2e40d90dfe07
version: 548
created: '2024-05-08T10:32:07+05:30'
tags:
  - ansible
---

<mark style="background-color:#f8d616;">**Topics:**<!-- {"backgroundCycleColor":"25"} --></mark>

1. *<mark style="background-color:#f8d616;">Ansible Vault (passwords)<!-- {"backgroundCycleColor":"25"} --></mark>*

1. <mark style="background-color:#f8d616;">Dynamic Inventory<!-- {"backgroundCycleColor":"25"} --></mark>

\

\

# *<mark style="background-color:#f8914d;">**Ansible Vault (passwords)**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*It's a storage of secrets,*

\

***encoding** - > A proper pattern to encode the text*

*ex:*

*asaiavaa -- > siva*

*adaeavaoapas -- > devops*

\

***encryption with password** -- > AES256 (mathematic algorithm) - Highly secured*

*ex:*

*dfkgfagjg;gjgg -- > devops*

*u4392854194586174598yhf -- > devops*

\

*<mark style="background-color:#f3de6c;">To check how vault works launching instances:<!-- {"backgroundCycleColor":"14"} --></mark>*

\

*Assign the IAM role before launching instances*

![775b1445-69f7-4083-97f1-30d2602bb8dc.png|835](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/775b1445-69f7-4083-97f1-30d2602bb8dc.png) [^1]

```
git clone https://github.com/chilops/Roboshop-shellscripts.git
```

```
cd Roboshop-shellscripts/
```

```
ls
```

```
sudo sh roboshop.sh
```

![919ad05e-da37-4131-b13c-e1e753eb941c.png|887.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/919ad05e-da37-4131-b13c-e1e753eb941c.png) [^2]

![4faf911d-ec8a-4556-a1de-ee49c2c526ef.png|886.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/4faf911d-ec8a-4556-a1de-ee49c2c526ef.png) [^3]

\

*Created Vault directory under Ansible, also copied 1.pingplaybook.yaml to vault directory.*

\

![2f382991-6494-4262-86f2-bdb505edb5d2.png|896](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/2f382991-6494-4262-86f2-bdb505edb5d2.png) [^4]

\

*<mark style="background-color:#f3de6c;">how to create ansible vault<!-- {"backgroundCycleColor":"14"} --></mark>*

*ansible-vault create /path/some-name.yaml*

\

*create group_vars directory under valut:*

![](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/6a40b9eb-834f-4d96-9503-eaad73af8530.png) [^5]

\

*Web instance variables under inventory file. from here pingplaybook.yaml will call the web variables*

![8239d286-24b4-432f-bc31-5ae6e9d5bbfd.png|775](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/8239d286-24b4-432f-bc31-5ae6e9d5bbfd.png) [^6]

\

![e97f9d95-43b8-49a8-96db-ae4775e32662.png|660](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/e97f9d95-43b8-49a8-96db-ae4775e32662.png) [^7]

```
git status
```

```c
git add . ; git commit -m "valut concept"; git push origin main
```

```
git status
```

![55a58671-7974-4276-94ca-18508d78c2d6.png|850](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/55a58671-7974-4276-94ca-18508d78c2d6.png) [^8]

\

```
git clone https://github.com/chilops/Ansible.git
```

```
ls
cd Ansible/
ls
```

\

![3fdcabf9-90e6-4eb0-9ead-59932bd28f71.png|872.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/3fdcabf9-90e6-4eb0-9ead-59932bd28f71.png) [^9]

\

```
git pull
```

```
 ls
 cd vault/
 ls -l
```

\

![2b2e1a14-2268-412f-9337-7bb1d42c4bb9.png|847.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/2b2e1a14-2268-412f-9337-7bb1d42c4bb9.png) [^10]

\

```
ls -l
mkdir group_vars
```

```
ansible-vault create group_vars/web.yaml
```

\

![d82a9e85-670c-458b-a4c0-ec2f22d69ebc.png|876.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/d82a9e85-670c-458b-a4c0-ec2f22d69ebc.png) [^11]

*After giving new password, it will open a vault file then give below entries(user name & password of web instance)*

![d5e4d5b2-30f5-4ec3-b19c-5b847b224f4a.png|609](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/d5e4d5b2-30f5-4ec3-b19c-5b847b224f4a.png) [^12]

\

*Its encrypted now*

```
cat group_vars/web.yaml
```

![6e3a35d6-3d3d-4b4c-9ed3-49590de6e449.png|879.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/6e3a35d6-3d3d-4b4c-9ed3-49590de6e449.png) [^13]

\

To edit vault:

```
ansible-vault edit group_vars/web.yaml
```

![d5e4d5b2-30f5-4ec3-b19c-5b847b224f4a.png|496](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/d5e4d5b2-30f5-4ec3-b19c-5b847b224f4a.png) [^14]

\

*Create a inventory.ini file and add web instance details FQDN or IP:*

![49af7e0a-9b7b-432a-8d2e-d3eac82420c7.png|696](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/49af7e0a-9b7b-432a-8d2e-d3eac82420c7.png) [^15]

\

*Also ansible.cfg file should be created under* 

![41e95ef2-68f2-4533-a415-953b0fcdda7a.png|714](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/41e95ef2-68f2-4533-a415-953b0fcdda7a.png) [^16]

\

```
git status
```

```
git add . ; git commit -m "valut concept"; git push origin main
```

```
git status
```

```
git pull
```

![c6360d9f-a72e-4b8c-8269-3149abc3c5fe.png|731](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/c6360d9f-a72e-4b8c-8269-3149abc3c5fe.png) [^17]

![a592577d-e03b-4920-894a-5c3c7455c174.png|814](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/a592577d-e03b-4920-894a-5c3c7455c174.png) [^18]

\

*Now no password required.. only we need to enter vault password*

```
ansible-playbook 1.pingplaybook.yaml
```

![1ccf0eb9-a413-445d-9964-26ff960e22ba.png|812.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/1ccf0eb9-a413-445d-9964-26ff960e22ba.png) [^19]

\

\

*If you disable now use vault password as below command*

\

![920c1d10-106d-46ac-8a4f-59cb46666035.png|789](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/920c1d10-106d-46ac-8a4f-59cb46666035.png) [^20]

\

```
ansible-playbook 1.pingplaybook.yaml --ask-vault-pass
```

![8016d468-c0e8-4a1d-87e9-168a603f3256.png|817.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/8016d468-c0e8-4a1d-87e9-168a603f3256.png) [^21]

\

\

\

# <mark style="background-color:#f8914d;">**Dynamic Inventory**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

![d2c52be6-f010-47ac-bdd9-150cd0183864.png|807](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/d2c52be6-f010-47ac-bdd9-150cd0183864.png) [^22]

\

*10 servers are running now -- > because of traffic*

*I need to run ansible playbook against these servers*

*Ansible -- > AWS -- > To fetch ip address of the servers dynamically*

*Fetch instances with name **web** in **us-east-1***

\

***Installing plugin on ansible server (plug & play) -***if ansible have plugin to connect aws ec2, we can fetch ip addresses

```
ansible-galaxy collection install amazon.aws
```

![23283d9b-b9d3-4141-8e4c-34deab276081.png|973.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/23283d9b-b9d3-4141-8e4c-34deab276081.png) [^23]

\

*To get python version*

```
ansible --version
```

![d5875291-53ca-4a2f-891b-370dde1e64b3.png|935.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/d5875291-53ca-4a2f-891b-370dde1e64b3.png) [^24]

\

```
python
sudo yum list | grep pip
```

![546c231c-ef6f-49a7-8dcd-35e3b86c67e1.png|911](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/546c231c-ef6f-49a7-8dcd-35e3b86c67e1.png) [^25]

![a3ed7ae4-549f-44ad-95fb-3f1060708724.png|910.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/a3ed7ae4-549f-44ad-95fb-3f1060708724.png) [^26]

\

```
sudo yum install python3.11-pip.noarch -y
```

![841475ee-a61e-46df-bbf9-7a1aee179dcb.png|948](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/841475ee-a61e-46df-bbf9-7a1aee179dcb.png) [^27]

\

![c5b6a736-bfaf-431a-b967-ba83e53ee8cc.png|927](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/c5b6a736-bfaf-431a-b967-ba83e53ee8cc.png) [^28]

\

\

```
pip3.11 install boto3 botocore
```

![41891434-4b15-42ea-8b46-7193dc82f8d7.png|928](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/41891434-4b15-42ea-8b46-7193dc82f8d7.png) [^29]

\

```
vim web.aws_ec2.yaml
```

![65d81976-6675-4dde-afb5-773c468559e9.png|699](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/65d81976-6675-4dde-afb5-773c468559e9.png) [^30]

\

```
plugin: amazon.aws.aws_ec2
regions:
 - us-east-1
filters:
        tag:Name: 
        - web
```

![70b18dab-876a-4a6f-9caa-b4d82d9fd174.png|445](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/70b18dab-876a-4a6f-9caa-b4d82d9fd174.png) [^31]

\

*It fetches web instance IP*

```
ansible-inventory -i web.aws_ec2.yaml --list
```

\

![f754fb7a-d9d3-4cf8-ba73-e77040613874.png|609](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/f754fb7a-d9d3-4cf8-ba73-e77040613874.png) [^32]

\

*Now connecting to ec2 instance **Dynamically** using web.aws_ec2.yaml*

```
ansible aws_ec2 -i web.aws_ec2.yaml -e ansible_user=centos -e ansible_password=DevOps321 -m ping
```

![57d0ef48-b7c8-45f9-b10a-fa1e6ae45486.png|857.3333740234375](https://images.amplenote.com/1f222abc-0cf8-11ef-9bc9-2e40d90dfe07/57d0ef48-b7c8-45f9-b10a-fa1e6ae45486.png) [^33]

\

[^1]: EC2 > Instances > i-088fb01eb26742f86 > Modify IAM role
    Modify IAM role Info
    Attach an IAM role to your instance.
    Instance ID
    i-088fb01eb26742f86 (ansible server)
    IAM role
    Select an IAM role to attach to your instance or create a new role if you haven't created any. The role you select replaces any roles that are
    currently attached to your instance.
    EC2Roleforshellscripts
    C
    Create new IAM role \[
    Cancel
    Update IAM role

[^2]: 54 . 167. 124.229 \| 172. 31.21. 170 \| t2.micro \| null
    \[ centosdip-172-31-21-170 \~ \]$ git clone https: //github. com/chilops/Roboshop-shellscripts.git
    Cloning into 'Roboshop-shellscripts' . . .
    remote: Enumeratiog objects: 78, done.
    remote: Counting objects: 100% (78/78), done.
    remote: Compressing objects: 100% (60/60), done.
    remote: Total 78 (delta 41), reused 54 (delta 17), pack-reused 0
    Receiving objects: 100% (78/78), 11. 69 KiB \| 3.90 MiB/s, done.
    Resolving deltas: 100% (41/41), done.
    54 . 167. 124.229 \| 172. 31.21.170 \| t2.micro \| null
    \[ centosdip-172-31-21-170 \~ \]$ 1s
    Roboshop-shellscripts
    54 . 167 . 124.229 \| 172. 31.21.170 \| t2.micro \| null
    \[ centos@ip-172-31-21-170 \~ \]$ cd Roboshop-shellscripts/
    54 . 167 . 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts . git
    \[ centosdip-172-31-21-170 \~/Roboshop-shellscripts \]$ 1s
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
    catalogue . service
    mongo . repo
    payment . service redis. sh
    shipping . service
    user . sh
    54 . 167 . 124.229 \| 172.31.21.170 \| t2.micro \| https: //github. com/chilops/Roboshop-shellscripts.git
    \[ centosdip-172-31-21-170 \~/Roboshop-shellscripts \]$ sudo sh roboshop. shy

[^3]: \[ centosdip-172-31-21-170 \~/Roboshop-shellscripts \]$ sudo sh roboshop. sh
    mongodb: 172. 31 . 29.231
    "ChangeInfo" : {
    "Id": "/change/C026924325GCA8BK8RUCU",
    "Status": "PENDING"
    "SubmittedAt": "2024-05-08T05 : 15 : 18 . 723000+00:00",
    "Comment": "Creating a record set for cognito endpoint"
    redis: 172. 31. 25.8
    "ChangeInfo": {
    "Id": "/change/C06819201MO5LG4C2XKVK",
    "Status": "PENDING"
    "SubmittedAt": "2024-05-08T05 : 15 : 21 . 703000+00:00",
    "Comment": "Creating a record set for cognito endpoint"

[^4]: V REPOS
    Ansible > vault > ! 1.pingplaybook.yaml
    Ansible
    1
    name: ping playbook
    v vault
    hosts: web
    3
    ! 1.pingplaybook.yaml -
    U
    tasks :
    4
    ! 1.pingplaybook.yam/ -
    name: ping the server
    5
    ansible . builtin . ping:
    ! 2.nginx.yaml
    ! 3.multi-play.yaml
    ! 4.variables.yaml

[^5]: EXPLORER
    REPOS
    Ansible
    v vault
    > group_vars

[^6]: EXPLORER
    . . .
    mmon\\...
    app-setup.yaml
    ! main.yaml roboshop-ansible-roles
    ! variables-
    REPOS
    Ansible > = inventory.ini
    Ansible
    7
    \[localhost: vars \]
    vault
    8
    Course="Devops From inventory"
    > group_vars
    9
    Trainer="Sivakumar"
    ! 1.pingplaybook.yaml
    U
    10
    Duration="110HRS"
    ! 1.pingplaybook.yaml
    11
    PERSON="Siva from inventory"
    ! 2.nginx.yaml
    12
    WISHES="Morning from inventory"
    13
    ! 3.multi-play.yaml
    14
    \[web \]
    ! 4.variables.yaml
    15
    54. 235 . 14. 240
    ! 5.variables_task.yaml
    16
    ! 6.variables_from_files.yaml
    17
    \[web: vars \]
    ! 7.vars_prompt.yaml
    18
    Course="Devops . From inventory"
    ! 8.vars_inventory.yaml
    19
    Trainer="Sivakumar"
    20
    ! 9.vars_from_args.yaml
    Duration="110HRS"
    21
    PERSON="Siva from inventory"
    10.vars_preferences.yaml
    22
    WISHES="Morning from inventory"
    11.data_types.yaml
    23
    12.conditions.yaml
    24
    \[catalogue \]
    13.loops.yaml
    25
    192. 187 .56.5
    14.loops_package.yaml
    26
    192 . 187 . 56.6
    ! 15.loops_packages.yaml
    27
    28
    \[cart \]
    ! 16.tags.yaml
    29
    192. 187 . 56.7
    inventory.ini
    30
    192 . 187 .56.8

[^7]: REPOS
    Ansible > vault > ! 1.pingplaybook.yaml
    Ansible
    1
    name: ping playbook
    vault
    2
    hosts: web
    3
    tasks :
    > group_vars
    4
    name: ping the server
    ! 1.pingplaybook.yaml
    U
    5
    ansible. builtin . ping:
    ! 1.pingplaybook.yaml
    ! 2.nginx.yaml
    3 multi-play va

[^8]: On branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    vault/
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "vault concept"; git push origin main

[^9]: \[ centos@ip-172-31-21-170 \~ \]$ git clone https://github. com/chilops/Ansible. git
    Cloning into 'Ansible'..
    remote: Enumeratiog objects: 74, done.
    remote: Counting objects: 100% (74/74), done.
    remote: Compressing objects: 100% (62/62), done.
    remote: Total 74 (delta 33), reused 52 (delta 11), pack-reused 0
    Receiving objects: 100% (74/74), 8.84 KiB \| 2.95 MiB/s, done.
    Resolving deltas: 100% (33/33), done.
    54. 167. 124.229 \| 172. 31.21.170 \| t2.micro \| null
    \[ centos@ip-172-31-21-170 \~ \]$ 1s
    Ansible Roboshop-shellscripts
    54 . 167 . 124.229 \| 172. 31.21.170 \| t2.micro \| null
    \[ centosdip-172-31-21-170 \~ \]$ cd Ansible/
    54 . 167 . 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centosdip-172-31-21-170 \~/Ansible \]$ 1s
    10. vars_preferences . yaml
    14 . loops_package . yaml
    2 . nginx . yaml
    6. variables_from files. yaml inventory . ini
    11 . data_types . yaml
    15. loops_packages . yaml
    3. multi-play . yaml
    7. vars_prompt . yaml
    variables . yaml
    12 . conditions . yaml
    16. tags . yaml
    4 . variables . yaml
    8 . vars inventory . yaml
    13. loops . yaml
    1. pingplaybook . yaml
    5. variables_task. yaml
    9. vars_from args . yaml
    54 . 167. 124. 229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-21-170 \~/Ansible \]$ \[

[^10]: centos@ip-172-31-21-170 \~/Ansible \]$ 1s
    10. vars_preferences . yaml
    14 . loops_package . yaml
    2 . nginx . yaml
    6. variables_from files. yaml
    inventory . ini
    11 . data_types . yaml
    15 . loops_packages . yaml
    3. multi-play . yaml
    7. vars prompt . yaml
    variables . yaml
    12 . conditions . yaml
    16. tags . yaml
    4 . variables . yaml
    8. vars_inventory . yaml
    vault
    13 . loops . yaml
    1. pingplaybook. yaml
    5. variables_task. yaml
    9. vars_from args . yaml
    54 . 167. 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Ansible.git
    centosdip-172-31-21-170 \~/Ansible \]$ cd vault/
    54 . 167. 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github.com/chilops/Ansible.git
    \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$ 1s -1
    total 4
    -rw-rw-r-- 1 centos centos 95 May 8 05:36 1. pingplaybook. yaml

[^11]: \[ centosdip-172-31-21-170 \~/Ansible/vault \]$ 1s -1
    total 4
    -rw-rw-r-- 1 centos centos 95 May 8 05:36 1. pingplaybook. yaml
    54. 167. 124.229 \| 172. 31.21. 170 \| t2.micro \| https: //github.com/chilops/Ansible.git
    \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$ 1s -al
    total 8
    drwxrwxr-x 2 centos centos
    33 May
    8 05: 36
    drwxrwxr-x 4 centos centos 4096 May
    8 05:36
    -rw-rw-r-- 1 centos centos
    95 May
    8 05: 36 1. pingplaybook. yaml
    54 . 167. 124.229 \| 172. 31. 21. 170 \| t2.micro \| https: //github. com/chilops/Ansible. git
    \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$ mkdir group_vars
    54 . 167. 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$ ansible-vault create group_vars/web . yaml
    New Vault password:
    Confirm New Vault password:

[^12]: ansible user: centos
    ansible passoword: Devops3210\]

[^13]: \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$ cat group_vars/web . yaml
    SANSIBLE VAULT ; 1 . 1 ; AES256
    37623166303234653433383763323535333437626263613935613233343135313166633231663061
    3231323039663861353265346136656234363135326334380a376630373163343336356133353664
    66613233383131316534623630396661613731343834393466336561373664323330613461306565
    3833323430313664300a316361316639313366386362343065636465363131666466343764653632
    62323164326365623232306336323838373362633837646238383034353664656336333262356438
    31363135333235316531646665323663616430303432313038613665346430643135336231346439
    363965383463356131383131363634303832
    54. 167. 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$

[^14]: ansible user: centos
    ansible passoword: Devops3210\]

[^15]: REPOS
    Ansible > vault > = inventory.ini
    Ansible
    \[web \]
    NH
    v vault
    chowdarychilukuri . in
    13
    > group_vars
    ! 1.pingplaybook.yaml
    E inventory.ini
    U

[^16]: V
    REPOS
    Ansible > vault > @ ansible.cfg
    Ansible
    H
    \[defaults \]
    vault
    2
    inventory=inventory . ini
    3
    ask_vault_pass=True
    > group_vars
    4
    ! 1.pingplaybook.yaml
    ansible.cfg

[^17]: on branch main
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    vault/inventory . ini
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\Ansible> git add . ; git commit -m "vault inv; git push origin main

[^18]: \[ centosdip-172-31-21-170 \~/Ansible/vault \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 4 (delta 1), reused 4 (delta 1), pack-reused 0
    Unpacking objects: 100% (4/4), 371 bytes \| 371.00 KiB/s, done.
    From https: //github. com/chilops/Ansible
    db6bfdb. . be947eb main
    -> origin/main
    Updating db6bfdb. . be947eb
    Fast-forward
    vault/inventory . ini \| 2 ++
    1 file changed, 2 insertions (+)
    create mode 100644 vault/inventory. ini

[^19]: \[ centosdip-172-31-21-170 \~/Ansible/vault \]$ ansible-playbook 1. pingplaybook. yaml
    Vault password:
    PLAY \[ping playbook\] \* \* \*\*\*\*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*
    ok: \[web . chowdarychilukuri . in\]
    TASK \[ping the server\] \*\*\*\*\*\*\*\*\*\*\*
    ok: \[web. chowdarychilukuri . in\]
    PLAY RECAP \* \* \*
    web . chowdarychilukuri . in : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    54 . 167 . 124.229 \| 172. 31.21.170 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-21-170 \~/Ansible/vault \]$ /

[^20]: V
    REPOS
    Ansible > vault > ansible.cfg
    Ansible
    H
    \[defaults \]
    v vault
    12
    inventory=inventory . ini
    3
    #ask_vault_pass=True -
    > group_vars
    4
    ! 1.pingplaybook.yaml
    ansible.cfg

[^21]: \[ centos@ip-172-31-22-137 \~/ansible/vault \]$ ansible-playbook 01-playbook. yaml --ask-vault-pass
    Vault password:
    PLAY \[ping playbook\]
    \* \* \*
    TASK \[Gathering Facts\] \*\*\*\*
    ok: \[web . daws 76s . online\]
    TASK \[ping the server\]
    \* \* \* \* \* \*
    ok: \[web . daws 76s . online\]
    PLAY RECAP
    \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \*
    web . daws 76s . online
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    18 . 215. 157. 145 \| 172.31.22.137 \| t2.micro \| https: / /github. com/daws-76s/ansible. git
    \[ centos@ip-172-31-22-137 \~/ansible/vault \]$

[^22]: we have servers, domains
    we had on premise servers, apps are deployed manually
    we used shell script to configure
    2016 --> internet usage, digital revolution
    2010/2012 --> EU, US
    autoscaling of servers highly required
    we are using ansible to configure
    - if you have more servers dynamically

[^23]: \[ centos@ip-172-31-22-137 \~ \]$ ansible-galaxy collection install amazon. aws
    Starting galaxy collection install process
    Nothing to do. All requested collections are already installed. If you want to reinstall them, consider using '--force
    18 . 215. 157. 145 \| 172.31.22.137 \| t2.micro \| null
    centos@ip-172-31-22-137 \~ \]$

[^24]: \[ centos@ip-172-31-22-137 \~ \]$ ansible --version
    ansible \[core 2.16.1\]
    config file = /etc/ansible/ansible.cfg
    configured module search path = \[' /home/centos/ . ansible/plugins/modules' , ' /usr/share/ansible/plugins/modules' \]
    ansible python module location = /usr/lib/python3.11/site-packages/ansible
    ansible collection location = /home/centos/ . ansible/collections: /usr/share/ansible/collections
    executable location = /usr/bin/ansible
    python version = 3.11.5 (main, Oct 25 2023, 14:45:39) \[GCC 8.5.0 20210514 (Red Hat 8.5.0-21) \] (/usr/bin/python3 .11)
    jinja version = 3.1.2
    libyaml = True
    18. 215. 157. 145 \| 172.31.22.137 \| t2.micro \| null

[^25]: \[ centosdip-172-31-22-137 \~ \]$ python
    python2
    python2 . 7
    python3
    python3.11 python3 . 6
    python3 . 6m
    I
    18 . 215. 157. 145 \| 172. 31.22.137 \| t2.micro \| null
    \[ centos@ip-172-31-22-137 \~ \]$ sudo yum list \| grep pip

[^26]: python3-pip . noarch
    9.0.3-23. e18
    stream
    python3-pip-wheel . noarch
    9.0.3-23. e18
    eos
    python3 . 11-pip . noarch
    22 . 3.1-4.e18
    stream
    python38-pip . noarch
    19.3.1-7. module e18+640+ebf3d03c
    stream
    python38-pip-wheel . noarch
    19.3.1-7. module e18+640+ebf3d03c

[^27]: \[ centos@ip-172-31-22-137 \~ \]$ sudo yum install python3.11-pip. noarch -y
    Last metadata expiration check: 0:31:38 ago on Fri 29 Dec 2023 02:05:04 AM UTC.

[^28]: boto and botocore --> aws python modules
    I
    ansible uses boto and botocore in background to connect aws

[^29]: \[ centos@ip-172-31-22-137 \~ \]$ pip3.11 install boto3 botocore
    Defaulting to user installation because normal site-packages is not writeable
    Collecting boto3
    Downloading boto3-1. 34.10-py3-none-any . wh1 (139 kB)
    139.3/139.3 kB 21.8 MB/s eta 0:00:00
    Collecting botocore
    Downloading botocore-1. 34.10-py3-none-any . whl (11.9 MB)
    11 . 9/11.9 MB 62.0 MB/s eta 0:00:00
    Collecting jmespath<2 .0.0,>=0.7.1
    Downloading jmespath-1.0.1-py3-none-any . wh1 (20 kB)
    Collecting s3transfer<0. 11.0,>=0.10.0
    Downloading s3transfer-0 .10.0-py3-none-any . wh1 (82 kB)
    82.1/82.1 kB 16.2 MB/s eta 0:00:00
    Collecting python-dateutil<3. 0.0,>=2.1
    Downloading python_dateutil-2.8.2-py2. py3-none-any . wh1 (247 kB)
    247. 7/247.7 KB 22.3 MB/s eta 0:00:00
    Collecting urllib3<2.1,>=1. 25.4
    Downloading urllib3-2.0.7-py3-none-any . wh1 (124 KB)
    124 . 2/124.2 kB 22.0 MB/s eta 0:00:00
    Collecting six>=1.5
    Downloading six-1.16.0-py2. py3-none-any . wh1 (11 kB)
    Installing collected packages: urllib3, six, jmespath, python-dateutil, botocore, s3transfer,

[^30]: \[ centos@ip-172-31-22-137 \~ \]$ vim web. aws ec2. yaml

[^31]: 18.215.157.145
    plugin: amazon. aws . aws ec2
    regions :
    - us-east-1
    filters :
    tag : Name :
    web

[^32]: "all": {
    "children": \[
    "ungrouped",
    "aws ec2"
    "aws ec2": {
    "hosts": \[
    "ec2-54-160-147-23 . compute-1 . amazonaws . com"

[^33]: \[ centosdip-172-31-22-137 \~ \]$ ansible aws ec2 -i web. aws ec2. yaml -e ansible user=centos -e ansible_password=Devops321 -m ping
    ec2-18-212-212-162. compute-1 . amazonaws . com \| SUCCESS =>
    "ansible_facts": {
    "discovered_interpreter_python": "/usr/libexec/platform-python"
    "changed" : false,
    "ping": "pong"
    ec2-54-172-172-40. compute-1 . amazonaws . com \| SUCCESS => {
    "ansible facts": {
    "discovered_interpreter_python": "/usr/libexec/platform-python"
    "changed": false,
    "ping": "pong"
    18 . 215 . 157. 145 \| 172. 31.22.137 \| t2. micro \| null

