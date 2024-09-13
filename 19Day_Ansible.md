---
title: 19Day_Ansible
uuid: 093c26a8-0f6e-11ef-b475-a6f126245c9e
version: 286
created: '2024-05-11T13:41:14+05:30'
tags:
  - ansible
---

***Topics:***

1. *<mark style="background-color:#f8d616;">How playbook works<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Play level variables<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Task level variables<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables from files<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables from prompt<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables from Inventory<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables from Arguments<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables 1st preferences - from different locations -inventory, cmd, files, args<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Data Types<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Conditions<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Loops  - this can be used when we are trying to installing multiple packages etc..<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Installing packages using loops<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Advanced loops - Installing & uninstalling packages<!-- {"backgroundCycleColor":"25"} --></mark>*

\

# *<mark style="background-color:#f8914d;">**How playbook works: Multi-playbooks**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*YAML code:*

![c5a166a0-a81a-47ef-bd24-50e79b2ea1d2.png|610](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/c5a166a0-a81a-47ef-bd24-50e79b2ea1d2.png) [^1]

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

\

![7f30d9dc-8371-4efa-8fff-9eda312208df.png|736](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/7f30d9dc-8371-4efa-8fff-9eda312208df.png) [^2]

 

*--Ansible software install on ansible server* 

```
sudo yum install ansible -y   
```

![ebef84e1-0d2c-49d6-857f-0a3f1d782432.png|857.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/ebef84e1-0d2c-49d6-857f-0a3f1d782432.png) [^3]

 

```
git clone https://github.com/chilops/Ansible.git 
ls
cd Ansible/
ls
 
```

![b3fb496e-46a5-453a-996b-b6aff6b90abe.png|855.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/b3fb496e-46a5-453a-996b-b6aff6b90abe.png) [^4]

 

 

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 3.multi-play.yaml
```

![01ad6446-8da5-4327-afc2-cd2f46bcc9a5.png|930.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/01ad6446-8da5-4327-afc2-cd2f46bcc9a5.png) [^5]

 

 

 

# ***variables***<!-- {"collapsed":true} -->

*--------------------*

*DRY --> don't repeat yourself*

 

*variables we keep aside from the code, so that code will not be disturbed when we are doing changes.*

 

*variable holds a value, you can use it anywhere.*

 

# ***Play level variables***<!-- {"collapsed":true} -->

*YAML code:*

![e0e83f6d-ee52-4103-9f56-1effeea14538.png|891](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/e0e83f6d-ee52-4103-9f56-1effeea14538.png) [^6]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![72853562-3d33-444d-96f2-09b3fc60feeb.png|726](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/72853562-3d33-444d-96f2-09b3fc60feeb.png) [^7]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 4.variables.yaml
```

 

![e1cdfb94-32f1-4075-8fbe-acd12209c4f2.png|872.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/e1cdfb94-32f1-4075-8fbe-acd12209c4f2.png) [^8]

 

  

# ***Task level variables***<!-- {"collapsed":true} -->

 

*YAML code:*

![73487bc5-491d-47df-8173-ec6496ee2d8f.png|822](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/73487bc5-491d-47df-8173-ec6496ee2d8f.png) [^9]

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![ca1a9832-396c-4c76-ba4c-de34a1bc1add.png|799](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/ca1a9832-396c-4c76-ba4c-de34a1bc1add.png) [^10]

 

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 5.variables_task.yaml
```

 

![fab4e7b5-39d6-43ec-8e10-7eb64ce6adc3.png|947.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/fab4e7b5-39d6-43ec-8e10-7eb64ce6adc3.png) [^11]

 

 

 

# *<mark style="background-color:#f8d616;">**Variables from files:**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

***YAML code***

![4fc5f48b-17d0-42fb-8c57-f053a3d014c3.png|794](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/4fc5f48b-17d0-42fb-8c57-f053a3d014c3.png) [^12]

 

***Variables file:***

![b215a045-fc83-4362-8d5f-494d0a0c2981.png|361](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/b215a045-fc83-4362-8d5f-494d0a0c2981.png) [^13]

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

![90db2423-5c10-4b97-b20e-0d450a721c05.png|814](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/90db2423-5c10-4b97-b20e-0d450a721c05.png) [^14]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 6.variables_from_files.yaml
```

 

![5cfcf111-3454-457f-b18c-f8502b36c7b5.png|945.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/5cfcf111-3454-457f-b18c-f8502b36c7b5.png) [^15]

 

 

 

# *<mark style="background-color:#f8d616;">**Variables from prompt**:<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

***YAML code***

![d9bcdfd7-4e49-42a6-b3fd-791ed4d453a4.png|610](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/d9bcdfd7-4e49-42a6-b3fd-791ed4d453a4.png) [^16]

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

![30b52517-4747-4c6c-b837-624fbef89b09.png|717](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/30b52517-4747-4c6c-b837-624fbef89b09.png) [^17]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 7.vars_prompt.yaml
```

 

![fe986547-4f98-4c14-848f-56a1e44ea8a2.png|947.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/fe986547-4f98-4c14-848f-56a1e44ea8a2.png) [^18]

 

 

 

# *<mark style="background-color:#f8d616;">**Variables from Inventory**:<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

*YAML code*

![7aff7df8-20b2-473f-b0c2-b72ddf76f861.png|852](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/7aff7df8-20b2-473f-b0c2-b72ddf76f861.png) [^19]

 

*Inventory.ini update*

![69019091-accc-4e48-a990-ea4a62259f0a.png|731](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/69019091-accc-4e48-a990-ea4a62259f0a.png) [^20]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

![0282539d-9cb5-4473-a77c-a3353fc21cf0.png|808](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/0282539d-9cb5-4473-a77c-a3353fc21cf0.png) [^21]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 8.vars_inventory.yaml
```

 

![9297e972-d9dd-4a5e-a060-8000ef2edea1.png|955.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/9297e972-d9dd-4a5e-a060-8000ef2edea1.png) [^22]

 

 

# *<mark style="background-color:#f8d616;">**Variables from Arguments**:<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

*YAML code:*

![07fe6223-10dd-479d-adf8-8859bc9939e9.png|536](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/07fe6223-10dd-479d-adf8-8859bc9939e9.png) [^23]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

![e64864bd-2bd5-4e77-b0b7-b88d90f3fcfa.png|858](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/e64864bd-2bd5-4e77-b0b7-b88d90f3fcfa.png) [^24]

 

```
git pull
```

```
 ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 -e "PERSON=satya" -e "WISHES=morning" 9.vars_from_args.yaml
```

 

![0542e50b-b0ba-48e1-bc84-ab685cf6da77.png|972.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/0542e50b-b0ba-48e1-bc84-ab685cf6da77.png) [^25]

 

 

 

# *<mark style="background-color:#f8d616;">**Variables 1st preferences - from different locations -inventory, cmd, files, args**:<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

*YAML code:*

![79720636-1cc8-446d-9ab5-53b047e77abe.png|648](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/79720636-1cc8-446d-9ab5-53b047e77abe.png) [^26]

 

*Updated in invetory, files, args etc:*

![ce34bd92-d81d-4ce7-ab12-2282da184463.png|483](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/ce34bd92-d81d-4ce7-ab12-2282da184463.png) [^27]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![cf01c381-0ac6-47c0-881b-2a46c251e2c0.png|889](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/cf01c381-0ac6-47c0-881b-2a46c251e2c0.png) [^28]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 -e "PERSON=satyafromcmd" -e "WISHES=morningfromcmd" 10.vars_preferences.yaml
```

 

![6e7a0041-f400-4a73-92e4-5224d3ce682d.png|961.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/6e7a0041-f400-4a73-92e4-5224d3ce682d.png) [^29]

 

*Or*

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 10.vars_preferences.yaml
```

![911b1831-10ec-48e2-a2f5-b8b5376ead14.png|1019.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/911b1831-10ec-48e2-a2f5-b8b5376ead14.png) [^30]

\

\

# *<mark style="background-color:#f8914d;">**Data Types**:<!-- {"backgroundCycleColor":"24"} --></mark> not much preference in scripting - shell, ansible etc*<!-- {"collapsed":true} -->

 

*list*

*map*

*boolean*

*key, value*

 

 

*YAML code*

![5d0ec9bc-c30b-4718-9cc2-9e399ed86ed2.png|703](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/5d0ec9bc-c30b-4718-9cc2-9e399ed86ed2.png) [^31]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![6ce0d687-f52f-447c-a7cc-399f2d671055.png|795](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/6ce0d687-f52f-447c-a7cc-399f2d671055.png) [^32]

 

```
git pull
```

![fe144007-8fed-4376-a331-457998071e58.png|876.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/fe144007-8fed-4376-a331-457998071e58.png) [^33]

 

 

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 11.data_types.yaml
```

![40859457-8c72-4b08-aa8c-1b8bda3c200b.png|903.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/40859457-8c72-4b08-aa8c-1b8bda3c200b.png) [^34]

 

 

 

 

# *<mark style="background-color:#f8914d;">**Conditions**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*id roboshop*

*if not exist we created, if exist we skipped*

 

*YAML code*

![3397d512-a099-4569-9f57-b46c596db9cf.png|712](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/3397d512-a099-4569-9f57-b46c596db9cf.png) [^35]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![57e69047-0b16-49b8-b6c4-62471c656b1b.png|802](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/57e69047-0b16-49b8-b6c4-62471c656b1b.png) [^36]

 

\

```
git pull
```

*-- Now user will create if not exist*

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 12.conditions.yaml     
```

 

![e3b0ab0d-cbd9-4019-905b-79b0a6a3a5e2.png|920.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/e3b0ab0d-cbd9-4019-905b-79b0a6a3a5e2.png) [^37]

 

 *-- Now user creations skips since its already exists*

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 12.conditions.yaml     
```

 

![21381fcf-e0ec-49a0-91aa-3630b80fb03f.png|961.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/21381fcf-e0ec-49a0-91aa-3630b80fb03f.png) [^38]

 

*check if user created or not*

```
id roboshop 
```

![ca9f7b88-d8ef-4574-aa61-84d910801005.png|774.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/ca9f7b88-d8ef-4574-aa61-84d910801005.png) [^39]

 

 

 

# *<mark style="background-color:#f8914d;">**Loops** :   <!-- {"backgroundCycleColor":"24"} --></mark><mark style="background-color:#f8d616;">this can be used when we are trying to installing multiple packages etc..<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

 

*YAML code*

![cc1c8ce2-db33-415e-907d-b236038b7607.png|642](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/cc1c8ce2-db33-415e-907d-b236038b7607.png) [^40]

 

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

![2362e35c-949d-42d1-b264-a34e5c16749b.png|714](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/2362e35c-949d-42d1-b264-a34e5c16749b.png) [^41]

 

```
git pull
```

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 13.loops.yaml
```

 

![196d9dde-1593-4769-a44b-e064161caafd.png|819.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/196d9dde-1593-4769-a44b-e064161caafd.png) [^42]

 

 

# ***Installing packages using loops:***<!-- {"collapsed":true} -->

 

*YAML Code*

![](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/7e2d1518-5d4b-41be-973f-c9f2980e3a75.png) [^43]

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![af32573d-2efb-464f-b964-53d7e475ede4.png|899.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/af32573d-2efb-464f-b964-53d7e475ede4.png) [^44]

 

```
git pull
```

 *-- Installing packages*

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 14.loops_package.yaml   
```

 

![e9425553-0d35-4d2a-ba0f-58f2730aa63f.png|929.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/e9425553-0d35-4d2a-ba0f-58f2730aa63f.png) [^45]

 

 

# *<mark style="background-color:#f8914d;">**Advanced loops - Installing & uninstalling packages**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*YAML Code:*

![b4a59989-b662-43e4-b6f4-705d4ae8627b.png|605](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/b4a59989-b662-43e4-b6f4-705d4ae8627b.png) [^46]

 

```
git status
```

```
git add . ; git commit -m "multiplay"; git push origin main
```

```
git status
```

 

![e5d6a2c8-832d-4459-b07d-083552c5a5e5.png|817](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/e5d6a2c8-832d-4459-b07d-083552c5a5e5.png) [^47]

 

 

```
git pull
```

*--To install & uninstall packages at same time.*

```
ansible-playbook -i inventory.ini -e ansible_user=centos -e ansible_password=DevOps321 15.loops_packages.yaml     
```

 

![7ced5c59-733e-4abf-967e-526b056f96b4.png|877.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/7ced5c59-733e-4abf-967e-526b056f96b4.png) [^48]

 

*--To check if nginx package installed or not*

```
systemctl status nginx 
```

 

![f4681250-1f7f-4330-828c-e334ef4da511.png|800.3333740234375](https://images.amplenote.com/093c26a8-0f6e-11ef-b475-a6f126245c9e/f4681250-1f7f-4330-828c-e334ef4da511.png) [^49]

 

[^1]: Ansible > ! 3.multi-play.yaml
    # playbook is a list of Plays
    12
    name: PLAY-1
    3
    hosts: localhost
    4
    tasks :
    5
    name: PLAY-1 and TASK-1
    6
    ansible . builtin . debug :
    7
    msg: "Hello from PLAY-1 and TASK-1"
    8
    9
    -
    name: PLAY-2
    10
    hosts: localhost
    11
    tasks :
    12
    name: PLAY-2 and TASK-2
    13
    ansible . builtin . debug :
    14
    msg: "Hello from PLAY-2 and TASK-2"

[^2]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    3. multi-play . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "multiplay"; git push origin main

[^3]: \[ centos@ip-172-31-31-85 \~ \]$ sudo yum install ansible -y
    CentOS Stream 8 - AppStream
    41 MB/S
    28 MB
    00: 00
    CentOS Stream 8
    - BaseOS
    39 MB/S
    10 MB
    00: 00
    CentOS Stream 8 -
    Extras
    28 kB/s
    18 kB
    00: 00
    CentOS Stream 8 - Extras common packages
    84 kB/s
    7. 7 kB
    00: 00
    Extra Packages for Enterprise Linux 8 - x86 64
    45 MB/S \|
    16 MB
    00:00
    Dependencies resolved.
    Package
    Architecture
    Version
    Repository
    Size
    Installing :
    ansible
    noarch
    8.3.0-1.e18
    epel
    41 M
    Installing dependencies:
    ansible-core
    x86 64
    2. 16.2-1.e18
    appstream
    4.1 M
    mpdecimal
    x86 64
    2.5.1-3.e18
    appstream
    93 k
    python3. 11
    x86 64
    3. 11. 7-1. e18
    appstream
    30 k
    python3. 11-cffi
    x86 64
    1. 15. 1-1. e18
    appstream
    305 k

[^4]: \[ centosdip-172-31-31-85 \~ \]$ git clone https: //github. com/chilops/Ansible.git
    Cloning into 'Ansible' ...
    remote: Enumeratiog objects: 13, done.
    remote: Counting objects: 100% (13/13), done.
    remote: Compressing objects: 100% (12/12), done.
    remote: Total 13 (delta 2), reused 12 (delta 1), pack-reused 0
    Receiving objects: 100% (13/13), done.
    Resolving deltas: 100% (2/2), done.
    18. 212. 216.0 \| 172. 31. 31.85 \| t2.micro \| null
    \[ centos@ip-172-31-31-85 \~ \]$
    18 . 212. 216.0 \| 172. 31. 31.85 \| t2.micro \| null
    \[ centos@ip-172-31-31-85 \~ \]$ 1s
    Ansible
    18 . 212.216.0 \| 172.31. 31.85 \| t2.micro \| null
    \[ centos@ip-172-31-31-85 \~ \]$ cd Ansible/
    18 . 212.216.0 \| 172. 31. 31.85 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-31-85 \~/Ansible \]$ 1s
    1. pingplaybook. yaml 2.nginx. yaml 3.multi-play . yaml inventory . ini
    18 . 212.216.0 \| 172. 31. 31.85 \| t2.micro \| https: //github. com/chilops/Ansible.git

[^5]: \[ centos@ip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    3. multi-play . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[PLAY-1 \]
    TASK \[Gathering Facts\]
    \* \* \*
    ok: \[localhost\]
    TASK \[PLAY-1 and TASK-1 \]
    \* \* \* \* \*
    ok: \[localhost\] => {
    "msg": "Hello from PLAY-1 and TASK-1"
    PLAY \[PLAY-2\]
    \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok: \[localhost\]
    TASK \[PLAY-2 and TASK-2\]
    \* \* \* \* \* \*
    ok :
    \[localhost\] => {
    "msg": "Hello from PLAY-2 and TASK-2"
    PLAY RECAP
    \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    localhost
    : ok=4
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^6]: Ansible > ! 4.variables.yaml
    1
    # PLAY level variables
    2
    name: variables from PLAY level
    3
    hosts: localhost
    4
    vars :
    5
    Course: "Devops"
    16
    Trainer: "Sivakumar"
    7
    Duration: "110HRS"
    8
    tasks :
    9
    -
    name: check variables
    10
    ansible . builtin . debug :
    11
    msg: "Hi, I am learning {{Course}}, Trainer is {{Trainer}}, Duration is {{Duration}}"
    12
    13

[^7]: (use "git add <file>..." to include in what will be committed)
    4. variables . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "simple variables"; git push origin main

[^8]: centos@ip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    4 . variables . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\]
    \* \* \* \* \* \* \*
    TASK \[Gathering Facts\]
    \*
    ok:
    \[localhost \]
    TASK \[check variables\]
    \* \* \* \*
    ok :
    \[localhost\] => {
    "msg": "Hi, I am learning Devops, Trainer is Sivakumar, Duration is 110HRS"
    PLAY RECAP
    \* \* \*
    \* \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    18. 212.216.0 \| 172.31.31.85 \| t2.micro_\| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-31-85 \~/Ansible \]$ \[

[^9]: Ansible > ! 5.variables_task.yaml
    # TASK level variables
    2
    name: variables from PLAY level
    3
    hosts: localhost
    4
    vars :
    5
    Course: "Devops"
    6
    Trainer: "Sivakumar"
    7
    Duration: "110HRS"
    18
    tasks :
    9
    name: check variables
    10
    vars: #task level
    11
    Course: "Devops with AWS"
    12
    ansible. builtin . debug :
    13
    msg: "Hi, I am learning {{Course}}, Trainer is {{Trainer}}, Duration is {{Duration}}"

[^10]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    5. variables_task. yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\Ansible> git add . ; git commit -m "simple variables"; git push origin main
    \[main e8ee8c7\] simple variables

[^11]: centosdip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops3.
    5. variables_task. yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\]
    \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \*
    ok: \[localhost\]
    TASK \[check variables\]
    ok: \[localhost\] => {
    "msg": "Hi, I am learning Devops with AWS, Trainer is Sivakumar, Duration is 110HRS"
    PLAY RECAP \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    18 . 212.216.0 \| 172. 31. 31.85 \| t2.micro_\| https: //github. com/chilops/Ansible.git
    centosdip-172-31-31-85 \~/Ansible 1$ \|\|

[^12]: Ansible > ! 6.variables_from_files.yaml
    name: variables from PLAY level
    2
    hosts: localhost
    3
    vars_files:
    14
    variables . yaml
    15
    tasks :
    6
    name: check variables
    ansible . builtin . debug:
    8
    msg: "Hi, I am learning {{Course}}, Trainer is {{Trainer}}, Duration is {{Duration}}"

[^13]: Ansible > ! variables.yaml
    1
    Course: "Devops with AWS 2024"
    Trainer: "Sivakumar"
    13
    Duration: "110HRS"
    4
    15
    #
    PERSON: "Siva from FILE"
    6
    # WISHES: "Morning from FILE"

[^14]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    6. variables_from_files . yaml
    variables . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos\\Ansible> git add . ; git commit -m "simple variables"; git push origin main/

[^15]: centos@ip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    1 6. variables from files. yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\]
    TASK \[Gathering Facts\]
    ok: \[localhost\]
    TASK \[check variables\]
    \* \* \* \* \*
    ok: \[localhost\] => {
    "msg": "Hi, I am learning Devops with AWS 2024, Trainer is Sivakumar, Duration is 110HRS"
    PLAY RECAP \* \*
    \* \* \* \* \*
    \* \* \* \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    18 . 212. 216.0 \| 172.31.31.85 \| t2.micro_\| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-31-85 \~/Ansible \]$ /

[^16]: Ansible > ! 7.vars_prompt.yaml
    -
    name: variables from prompt
    2
    hosts: localhost
    3
    vars_prompt:
    name : USERNAME
    15
    prompt: Please enter your username
    6
    private: false # user can see what they are entering
    name : PASSWORD
    8
    prompt: Please enter your password
    9
    private: true # user can't see what they are entering
    10
    tasks :
    11
    name: print and check the values
    12
    ansible . builtin . debug :
    13
    msg: "username is: {{USERNAME}}, Password is: {{PASSWORD}}"

[^17]: (use "git add <file>..." to include in what will be committed)
    7. vars_prompt . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\Ansible> git add . ; git commit -m "simple variables"; git push origin main
    \[main 8f2acaa\] simple variables

[^18]: centosdip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    7. vars_prompt . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    Please enter your username: satya
    Please enter your password:
    PLAY \[variables from prompt\]
    \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \* \*
    ok: \[localhost\]
    TASK \[print and check the values\]
    \* \* \* \* \*
    ok: \[localhost\] => {
    "msg": "username is: satya, Password is: admin123"
    PLAY RECAP \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    18. 212.216.0 \| 172.31. 31.85 \| t2.micro_\| https://github. com/chilops/Ansible.git
    centos@ip-172-31-31-85 \~/Ansible 1$ \[\]

[^19]: Ansible > ! 8.vars_inventory.yaml
    name: variables from PLAY level
    hosts: localhost
    3
    tasks :
    4
    name: check variables
    15
    ansible. builtin . debug:
    6
    msg: "Hi, I am learning {{Course}}, Trainer is {{Trainer}}, Duration is {{Duration}}"

[^20]: Ansible > = inventory.ini
    192 . 187 . 56.20
    2
    192 . 187 . 56.30
    3
    4
    \[localhost \]
    5
    localhost
    6
    7
    \[localhost: vars \]
    8
    Course="Devops . From inventory"
    9
    Trainer="Sivakumar"
    10
    Duration="110HRS"
    11
    12
    13
    \[web \]
    14
    54. 163 . 18.10
    15
    16
    \[catalogue \]
    17
    192 . 187 . 56.5
    18
    192. 187 . 56.6
    19
    20
    \[cart \]
    21
    192. 187 .56.7
    22
    192. 187 .56.8
    23
    24
    \[roboshop : children \]
    25
    web
    26
    cart
    27
    catalogue

[^21]: (use "git add <file>. . ."
    to include in what will be committed)
    8. vars_inventory . yaml
    no changes added to commit (use "git add" and/or "git commit -a")
    PS E: \\AWSDevops\\Repos \\Ansible> git add . ; git commit -m "simple variables"; git push origin main

[^22]: centosdip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    8. vars_inventory . yaml
    WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\]
    \* \* \* \* \*
    TASK \[Gathering Facts\]
    k: \[localhost\]
    ASK \[check variables\]
    \* \* \* \* \* \* \* \* \* \* \* \* \*
    k :
    \[localhost\] => {
    "msg": "Hi, I am learning Devops From inventory, Trainer is Sivakumar, Duration is 110HRS"
    PLAY RECAP \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    ocalhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    8. 212. 216.0 \| 172. 31.31.85 \| t2.micro \| https: //github. com/chilops/Ansible.git
    centos@ip-172-31-31-85 \~/Ansible 1$ \[\]

[^23]: Ansible > ! 9.vars_from_args.yaml
    1
    name: variables from PLAY level
    2
    hosts: localhost
    2
    tasks :
    4
    name: check variables
    5
    ansible . builtin . debug :
    6
    msg: "Hello {{PERSON}}, Good {{WISHES}}"

[^24]: 9. vars_from_args . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops\\Repos \\Ansible> git add . ; git commit -m "simple variables"; git push origin main
    \[main 4debc37\] simple variables

[^25]: centosdip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    -e "PERSON=satya" -e "WISHES=morning" 9.vars_from_args . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\]
    \* \* \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \*
    ok: \[localhost\]
    TASK \[check variables\]
    \* \* \* \* \* \* \* \*
    ok: \[localhost\] => {
    "msg": "Hello satya, Good morning"
    PLAY RECAP
    \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \*
    \* \* \* \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    18 . 212. 216.0 \| 172. 31.31.85 \| t2.micro_\| https: //github.com/chilops/Ansible.git
    centos@ip-172-31-31-85 \~/Ansible \]$\[\]

[^26]: Ansible > ! 10.vars_preferences.yaml
    1
    name: variables from PLAY level
    hosts: localhost
    3
    vars_files:
    4
    variables . yaml
    15
    vars_prompt:
    6
    name : PERSON
    7
    prompt: Please enter your name
    8
    private: false # user can see what they are entering
    9
    name : WISHES
    10
    prompt: Please enter your Wishes
    11
    private: false # user can't see what they are entering
    12
    vars :
    13
    PERSON: "Siva from PLAY"
    14
    WISHES: "Morning from PLAY"
    15
    tasks :
    16
    name: check variables
    17
    vars :
    18
    PERSON: "Siva from TASK"
    19
    WISHES: "Morning from TASK"
    20
    ansible . builtin . debug :
    21
    msg: "Hello {{PERSON}}, Good {{WISHES}}"
    22
    23
    #1. CMD
    24
    #2. task
    25
    #3. File
    26
    #4. prompt
    27
    #5. play
    28
    #6. inventory
    29
    #7. roles

[^27]: Ansible > = inventory.ini
    192 . 187 . 56.20
    2
    192 . 187 .56.30
    3
    4
    \[localhost \]
    15
    localhost
    16
    17
    \[localhost : vars \]
    8
    Course="Devops From inventory"
    9
    Trainer="Sivakumar"
    10
    Duration="110HRS"
    11
    PERSON="Siva . from inventory"
    12
    WISHES="Morning from inventory"
    13

[^28]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    10. vars_preferences . yam1
    no changes added to commit (use "git add" and/or "git commit -a")
    PS E: \\AWSDevops\\Repos \\Ansible> git add . ; git commit -m "simple variables"; git push origin main/

[^29]: \[ centos@ip-172-31-34-233 \~/ansible \]$ ansible-playbook -i inventory . ini -e ansible_user=centos -e ansible_password=Devops321 -e "PERSO
    N=SivafromCMD" -e "WISHES=MorningfromCMD" 10-vars-preference . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\] \*\*\*\*\*\*\*\*\*\*\*\*\*
    TASK \[Gathering Facts\] \*\*\*\*\*\*\*\*
    ok: \[localhost\]
    TASK \[check variables\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
    ok: \[localhost\] =>
    "msg": "Hello SivafromCMD, Good MorningfromCMD"
    PLAY RECAP \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^30]: centos@ip-172-31-31-85 \~/Ansible \]$ ansible-playbook -i inventory . ini -e ansible user=centos -e ansible password=Devops32
    10. vars_preferences . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[variables from PLAY level\]
    \* \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \*
    ok: \[localhost\]
    TASK \[check variables\]
    \* \* \* \*
    ok: \[localhost\] => {
    "msg": "Hello Siva from inventory, Good Morning from inventory"
    PLAY RECAP
    \* \* \* \* \* \*
    \* \* \* \* \* \* \*
    \* \* \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    18. 212.216.0 \| 172. 31.31.85 \| t2.micro \| https: //github. com/chilops/Ansible.git
    centos@ip-172-31-31-85 \~/Ansible 1$ \[\]

[^31]: Ansible > ! 11.data_types.yaml
    1
    name: checking data types
    hosts: localhost
    3
    vars :
    4
    NAME: Sivakumar # key value
    5
    Skills: #Skills is a list type
    6
    Devops
    Shell
    8
    ANsible
    9
    Linux
    10
    Experience: # Experience is map type. It contains key value pairs
    11
    Devops : 7
    12
    AWS : 6
    13
    Docker : 4
    14
    Trainer: true # boolean
    15
    tasks :
    16
    - name: print key value pair
    17
    ansible. builtin . debug :
    18
    msg: "name: {{NAME}}"
    19
    20
    name: print list
    21
    ansible . builtin . debug :
    22
    msg: "Skills: {{Skills}}"
    23
    24
    - name: print map
    25
    ansible . builtin . debug :
    26
    msg: "Experience: {{Experience}}"
    27
    28
    name: print boolean
    29
    ansible . builtin. debug :
    30
    msg: "is he Trainer: {{Trainer}}"

[^32]: Untracked files:
    (use "git add <file>..." to include in what will be committed)
    11. data_types . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevOps\\Repos \\Ansible> git add . ; git commit -m "data types"; git push origin main
    \[main Sfdec671
    data

[^33]: \[ centosdip-172-31-29-30 \~ \]$ cd Ansible/
    34 . 224. 39. 129 \| 172.31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-29-30 \~/Ansible \]$ 1s
    10 . vars_preferences . yaml
    2. nginx . yaml
    5. variables task. yaml
    8. vars inventory . yaml variables . yaml
    11 . data_types . yaml
    3. multi-play . yaml
    6. variables_from_files. yaml
    9. vars_from_args . yaml
    1 . pingplaybook . yaml
    4 . variables . yaml
    7. vars_prompt . yaml
    inventory . ini

[^34]: centosdip-172-31-29-30 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    1 11 . data_types . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[checking data types\]
    \* \*
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok: \[localhost\]
    TASK \[print key value pair\]
    \* \* \* \* \* \* \* \* \* \*
    ok: \[localhost\] => {
    "msg": "name: Sivakumar"
    TASK \[print list\] \* \*\*\*\*\*\*\* \*
    ok: \[localhost\] => {
    "msg": "Skills: \['Devops', 'Shell', 'ANsible', 'Linux' \]"
    TASK \[print map\] \* \*\* \*\*
    ok: \[localhost\] => {
    "msg": "Experience: {'Devops' : 7, 'AWS' : 6, 'Docker' : 4}"
    TASK \[print boolean\]
    \* \* \* \* \* \* \* \* \* \*
    ok :
    \[localhost\] => {
    "msg": "is he Trainer: True"
    PLAY RECAP \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    localhost
    : ok=5
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    34. 224. 39. 129 \| 172.31.29.30 \| t2.micro \| https: //github.com/chilops/Ansible.git
    centos@ip-172-31-29-30 \~/Ansible \]$ \[\]

[^35]: Ansible > ! 12.conditions.yaml
    1
    name: conditions
    2
    hosts: localhost
    3
    become: yes
    4
    tasks :
    5
    name: check roboshop user exists or not
    6
    ansible . builtin . command: id roboshop
    7
    register: user #user is a variable name
    8
    ignore_errors: true # ansilbe will not exit even it got error
    9
    10
    name: print variable value
    11
    ansible . builtin . debug :
    12
    msg: "User output is: {{user}}"
    13
    14
    name: print exit status or return code
    15
    ansible . builtin . debug:
    16
    msg: "status is: {{user.rc}}"
    17
    18
    name: create user
    19
    ansible . builtin . user :
    20
    name: roboshop
    21
    when: user. rc != 0 #condition

[^36]: (use "git add <file>..." to include in what will be committed)
    12. conditions . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "conditions"; git push origin main
    \[main 92fle17\] conditions
    1 file changed, 21 insertions (+)

[^37]: \[ centos@ip-172-31-29-30 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    1 12 . conditions . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[conditions\]
    \* \* \* \* \* \* \* \*
    TASK \[Gathering Facts\] \* \*\*\*\*\*\*\*\*
    ok: \[localhost\]
    TASK \[check roboshop user exists or not\] \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* \* \*\*\* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    fatal: \[localhost\] : FAILED! => {"changed": true, "cmd": \["id", "roboshop"\], "delta": "0:00:00. 005913", "end": "2024-05-02 0
    6:05 : 49. 794195", "msg": "non-zero return code", "rc": 1, "start": "2024-05-02 06:05: 49. 788282", "stderr": "id: 'roboshop' :
    no such user", "stderr_lines": \["id: 'roboshop' : no such user"\], "stdout": "", "stdout_lines": \[\]}
    . . . ignoring
    TASK \[print variable value\]
    \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \*
    ok: \[localhost\] => {
    "msg": "User output is: {'changed': True, 'stdout' :
    'stderr' : 'id: 'roboshop' : no such user', 'rc': 1, 'cmd': \['id'
    'roboshop' \], 'start': '2024-05-02 06: 05: 49. 788282', 'end': '2024-05-02 06: 05: 49. 794195', 'delta' : '0:00:00.005913',
    'fail
    ed': True, 'msg': 'non-zero return code', 'stdout_lines': \[\], 'stderr_lines': \['id: 'roboshop' : no such user' \]}"
    TASK \[print exit status or return code\]
    ok :
    \[localhost\] =>
    "msg": "status is: 1"
    TASK \[create user\] \*\*\*\*\*
    changed: \[localhost\]
    PLAY RECAP \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    localhost
    : ok=5
    changed=2
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=1
    34 . 224. 39. 129 \| 172.31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-29-30 \~/Ansible \]$ \]

[^38]: centosdip-172-31-29-30 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    12 . conditions . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[conditions\] \* \*\*\*\*
    TASK \[Gathering Facts\]
    k: \[localhost\]
    TASK \[check roboshop user exists or not\]
    \* \* \* \* \* \* \* \* \* \* \* \* \*
    changed: \[localhost\]
    TASK \[print variable value\] \*\*\*\*\*\*
    ok :
    \[localhost\] => {
    "msg": "User output is: {'changed': True, 'stdout': 'uid=1001 (roboshop) gid=1001 (roboshop) groups=1001 (roboshop) ', 'sto
    err' :
    'rc': 0, 'cmd': \['id', 'roboshop'\], 'start': '2024-05-02 06:08 : 01. 845645', 'end': '2024-05-02 06:08 : 01.851580'
    delta' : '0: 00 : 00 . 005935', 'msg' : "',
    'stdout_lines': \['uid=1001 (roboshop) gid=1001 (roboshop) groups=1001 (roboshop) '\], 'stde
    rr_lines': \[\], 'failed': False}"
    TASK \[print exit status or return code\]
    ok: \[localhost\] => {
    "msg": "status is: 0"
    TASK \[create user\] \*\*\*\*
    skipping: \[localhost\]
    PLAY RECAP \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    localhost
    : ok=4
    changed=1
    unreachable=0
    failed=0
    skipped=1
    rescued=0
    ignored=0
    34. 224. 39. 129 \| 172. 31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-29-30 \~/Ansible \]$ 0

[^39]: \[ centos@ip-172-31-29-30 \~/Ansible \]$ id roboshop
    uid=1001 (roboshop) gid=1001 (roboshop) groups=1001 (roboshop)
    34 . 224. 39. 129 \| 172.31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-29-30 \~/Ansible \]$ \[

[^40]: Ansible > ! 13.loops.yaml
    -
    name: loops
    2
    hosts: localhost
    13
    tasks :
    4
    name: print persons
    ansible . builtin . debug :
    msg: "Hello {{item}}" # item is a default keyword
    loop :
    18
    -
    Ramesh
    9
    -
    Suresh
    10
    Robert
    11
    -
    Raheem

[^41]: (use "git add <file>..." to include in what will be committed)
    12. conditions . yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevOps\\Repos \\Ansible> git add . ; git commit -m "conditions"; git push origin main
    \[main 92f1e17\] conditions

[^42]: centos@ip-172-31-29-30 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    1 13. loops . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[loops\]
    \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \*
    ok: \[localhost\]
    TASK \[print persons\]
    \* \* \* \* \* \* \*
    ok: \[localhost\] => (item=Ramesh) => {
    "msg": "Hello Ramesh"
    ok: \[localhost\] => (item=Suresh) => {
    "msg": "Hello Suresh"
    ok: \[localhost\] => (item=Robert) => {
    "msg": "Hello Robert"
    ok: \[localhost\] => (item=Raheem) => {
    "msg": "Hello Raheem"
    PLAY RECAP
    \* \*
    \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \*
    \* \* \* \*
    localhost
    : ok=2
    changed=0
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    34 . 224. 39. 129 \| 172. 31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centos@ip-172-31-29-30 \~/Ansible \]$ \[\]

[^43]: Ansible > ! 14.loops_package.yaml
    -
    name: loops
    2
    hosts: localhost
    3
    become: yes
    4
    tasks :
    5
    name: print persons
    6
    ansible . builtin . package:
    name: "{{item}}"
    8
    state: present # item is a default keyword
    loop :
    10
    -
    git
    11
    -
    mysql
    12
    -
    postfix

[^44]: (use
    "git add <file>.
    to include in what will be committed)
    14. loops_package. yaml
    nothing added to commit but untracked files present (use "git add" to track)
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "loops install packages"; git push origin main

[^45]: centos@ip-172-31-29-30 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    14 . loops_package . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[loops \]
    \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \*
    ok: \[localhost\]
    TASK \[print persons\]
    \* \* \* \* \* \* \* \*
    ok: \[localhost\] => (item=git)
    changed: \[localhost\] => (item=mysql) /\~
    changed: \[localhost\]
    => (item=postfix)
    PLAY RECAP
    \* \* \*
    localhost
    : ok=2
    changed=1
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0
    34 . 224. 39. 129 \| 172. 31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    centos@ip-172-31-29-30 \~/Ansible \]$ \[

[^46]: Ansible > ! 15.loops_packages.yaml
    1
    name: loops
    2
    hosts: localhost
    3
    become: yes
    4
    tasks :
    15
    name: install or uninstall packages
    6
    ansible . builtin . package :
    name: "{{item . name}}"
    8
    state: "{{item. state}}" # item is a default keyword
    9
    loop :
    10
    -
    {name: 'git', state: 'present' } # item
    11
    -
    {name: 'mysql', state: 'absent' }
    12
    -
    {name: 'postfix', state: 'absent' }
    13
    -
    {name: 'nginx', state: 'present' }

[^47]: (use "git add <file>..." to include in what will be committed)
    15. loops_packages . yaml
    no changes added to commit (use "git add" and/or "git commit -a")
    PS E: \\AWSDevops \\Repos \\Ansible> git add . ; git commit -m "loops install & uninstall packages"; git push origin main

[^48]: centos@ip-172-31-29-30 \~/Ansible \]$ ansible-playbook -i inventory. ini -e ansible_user=centos -e ansible_password=Devops32
    15. loops_packages . yaml
    \[WARNING\] : Found both group and host with same name: localhost
    PLAY \[loops\]
    \* \* \* \* \* \* \* \*
    TASK \[Gathering Facts\]
    \* \* \* \* \*
    ok: \[localhost\]
    TASK \[install or uninstall packages\]
    \* \* \* \* \* \* \* \* \* \*
    ok: \[localhost\] => (item={ 'name' : 'git', 'state': 'present'} )
    changed: \[localhost\] => (item={ 'name': 'mysql', 'state': 'absent'} )
    changed: \[localhost\]
    =>
    (item={ 'name' : 'postfix', 'state': 'absent' })
    changed: \[localhost\] =>
    (item={ 'name' : 'nginx' ,
    'state' : 'present' } )
    PLAY RECAP
    \* \* \*
    \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \* \*
    \* \* \* \* \* \* \* \* \*
    \* \* \* \*
    localhost
    : ok=2
    changed=1
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^49]: 34 . 224 . 39. 129 \| 172.31.29.30 \| t2.micro \| https: //github. com/chilops/Ansible.git
    \[ centosdip-172-31-29-30 \~/Ansible \]$ systemctl status nginx
    nginx . service - The nginx HTTP and reverse proxy server
    Loaded: loaded (/usr/lib/systemd/system/nginx. service; enabled; vendor preset: disabled)
    Active: active (running) since Thu 2024-05-02 06:37:55 UTC; 3s ago
    Process: 11971 ExecStart=/usr/sbin/nginx (code=exited, status=0/SUCCESS)
    Process: 11969 ExecStartPre=/usr/sbin/nginx -t (code=exited, status=0/SUCCESS)

