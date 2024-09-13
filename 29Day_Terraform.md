---
title: 29Day_Terraform
uuid: f63d379e-1d79-11ef-a7bb-2e97089a9920
version: 1099
created: '2024-05-29T10:41:52+05:30'
tags:
  - vpc-in-aws
  - cidr
  - aws
  - vpc
  - terraform
---

***Topics:***

1. *<mark style="background-color:#f8d616;">Modules development - Important topic<!-- {"backgroundCycleColor":"25"} --></mark>*

1. <mark style="background-color:#f3de6c;">VPC - Virtual private cloud<!-- {"backgroundCycleColor":"14"} --></mark>

1. <mark style="background-color:#f8d616;">CIDR -<!-- {"backgroundCycleColor":"25"} --></mark><mark style="background-color:#f8914d;">**classless interdomain routing**<!-- {"backgroundCycleColor":"24"} --></mark>

\

\

\

# *<mark style="background-color:#f8914d;">**Modules** development **- Important topic (its like a functions concept)**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

DRY - Don't repeat yourself.

**code re-use** -- no need to write infra for every project from the scratch.

\

**Modules are of two types.**

1. **Customized modules** - For specific organization/company (cloud central team or cloud owners or cloud managed teams - these team will develop/write the code & they use it for their organization)<!-- {"indent":1} -->

    1. **Open source modules -** Already pre-defined.

\

<mark style="background-color:#f3de6c;">**Customized modules:**<!-- {"backgroundCycleColor":"14"} --></mark>

Create below two folders and add .gitignore file

![](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/5395a5ed-8161-4d12-b19d-a5a79dd0e54f.png) [^1]

\

<mark style="background-color:#f3de6c;">Terraform level naming best practices<!-- {"backgroundCycleColor":"14"} --></mark>

![0cb6ae2f-cf17-4a27-99bf-147c2c8e0c01.png|726](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/0cb6ae2f-cf17-4a27-99bf-147c2c8e0c01.png) [^2]

![8153dc4c-0ec7-4f6a-8211-7df6d97d5599.png|630](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/8153dc4c-0ec7-4f6a-8211-7df6d97d5599.png) [^3]

\

<mark style="background-color:#f3de6c;">ec2.tf code<!-- {"backgroundCycleColor":"14"} --></mark>

![ce752384-19f5-4332-8a5e-3c22d7008c0b.png|770](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/ce752384-19f5-4332-8a5e-3c22d7008c0b.png) [^4]

\

variables.tf code

![35b4e6ec-fa8f-4148-a1d5-5a879d1aaf5e.png|768](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/35b4e6ec-fa8f-4148-a1d5-5a879d1aaf5e.png) [^5]

\

Now above files which are under **ec2** folder we can consider as modules(data), By using this code we can create multiple environments(dev, prod, uat etc) without writing extra code. As an example now creating one more folder called **roboshop-ec2** and use modules from **ec2** folder.

\

<mark style="background-color:#f3de6c;">create roboshop-ec2 folder<!-- {"backgroundCycleColor":"14"} --></mark> 

ec2.tf code 

![48a2d381-a2bd-44eb-87b2-428575a73d81.png|746](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/48a2d381-a2bd-44eb-87b2-428575a73d81.png) [^6]

\

<mark style="background-color:#f3de6c;">provider.tf file always should be present in user projects but not in modules.<!-- {"backgroundCycleColor":"14"} --></mark>

providers.tf code

![a57f69ad-3ff1-4385-acfd-d2955ea16027.png|761.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/a57f69ad-3ff1-4385-acfd-d2955ea16027.png) [^7]

\

also add .gitignore file (this is useful to push to github)

![1c1b003a-3fa5-4530-abc0-10e6f7d2cedc.png|831](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/1c1b003a-3fa5-4530-abc0-10e6f7d2cedc.png) [^8]

\

```
terraform init
```

![b2879931-a27d-4dca-b75c-f8f5b6855c55.png|697](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/b2879931-a27d-4dca-b75c-f8f5b6855c55.png) [^9]

\

```
terraform plan
```

![7b262410-7798-45c4-8034-f22741421306.png|660](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/7b262410-7798-45c4-8034-f22741421306.png) [^10]

\

Now if you want to pass variables to specify t3.micro instead of t2.micro from the current module. so update code as below in ec2.tf code (it will override which is present in ec2 folder code).

\

ec2.tf code update

![dd9d9f25-20e1-4a20-889f-a3eb53a90edf.png|736](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/dd9d9f25-20e1-4a20-889f-a3eb53a90edf.png) [^11]

\

outputs.tf code

![03dd8981-720b-43d5-a4c0-18b2a6dc821b.png|801](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/03dd8981-720b-43d5-a4c0-18b2a6dc821b.png) [^12]

\

```
terraform plan
```

![702134d9-d122-43e5-9b48-80018074f5dc.png|687](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/702134d9-d122-43e5-9b48-80018074f5dc.png) [^13]

\

or we can use different way.. create variables.tf file

\

variables.tf code

![77f867b2-3bda-4904-93cd-9be1e7b04cef.png|747](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/77f867b2-3bda-4904-93cd-9be1e7b04cef.png) [^14]

\

updated ec2.tf code

![7fab92a0-e014-41b6-b9a2-07af5563d503.png|724](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/7fab92a0-e014-41b6-b9a2-07af5563d503.png) [^15]

\

```
terraform plan
```

\

![40be1215-77b4-4f88-9b15-2733e77709d6.png|639](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/40be1215-77b4-4f88-9b15-2733e77709d6.png) [^16]

\

1\. **module developer** -- Who develops modules

2\. **module user**          -- Who consumes modules

\

\

outputs.tf code in roboshop-ec2

![c4ff3c59-0eb8-44a2-92b5-83bf11ad6d60.png|737](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/c4ff3c59-0eb8-44a2-92b5-83bf11ad6d60.png) [^17]

\

```
terraform plan
```

![79a9ffe7-fe1c-494e-94e7-e6fbe036e547.png|749](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/79a9ffe7-fe1c-494e-94e7-e6fbe036e547.png) [^18]

\

```
terraform apply -auto-approve
```

![93b60081-09a8-4925-ba14-806f369f3d55.png|902](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/93b60081-09a8-4925-ba14-806f369f3d55.png) [^19]

\

![12cc74da-a426-4f7b-9eee-ae58c30ebec2.png|907.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/12cc74da-a426-4f7b-9eee-ae58c30ebec2.png) [^20]

\

```
terraform destroy -auto-approve
```

![5beda3dc-5ccc-49f1-9bff-14822f0519f2.png|938](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/5beda3dc-5ccc-49f1-9bff-14822f0519f2.png) [^21]

\

# <mark style="background-color:#f8914d;">**VPC - Virtual private cloud -**<!-- {"backgroundCycleColor":"24"} --></mark> Its an Isolated network within AWS<!-- {"collapsed":true} -->

\

![3213a741-25d1-42ff-9677-f6206567115a.png|384](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/3213a741-25d1-42ff-9677-f6206567115a.png) [^22]

\

![474eb676-fb4b-4036-8685-88d1489101f1.png|756](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/474eb676-fb4b-4036-8685-88d1489101f1.png) [^23]

\

\

Arch -- Entry point = Internet gateway

Roads -- Routes 

\

![bb777bee-cb38-41e2-ac14-e24d20db55e0.png|799](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/bb777bee-cb38-41e2-ac14-e24d20db55e0.png) [^24]

**private & public subnets:**

Public affairs     -- Direct access  (web servers)

Minister offices  -- No direct access (shipping, payment servers)

PM office           -- No direct access (DB servers)

\

![c2c05fa8-4b50-434f-bd89-1bc418f5c597.png|782](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/c2c05fa8-4b50-434f-bd89-1bc418f5c597.png) [^25]

\

**Route tables --  routes**

Public route table       --   routes --  attach with public subnets

Private route table      --   routes --  attach with private subnets

Database route table  --   routes --  attach with database subnets

\

\

# <mark style="background-color:#f8914d;">**CIDR - classless interdomain routing**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

IPV4 --  192.168.1.1 --  32 bits = 4 octets  --  each octet 8bits

\

0 1 2 3 4 5 6 7 8 9 --- 10 numbers (decimals)

only 0,1 --  2 numbers (Binary)

\

**Decimal to Binary conversion**

7 6 5 4 3 2 1 0

\-   -  -  -  -  -  -  -    =8 bits in one octet.

\

1st -- 2^0 = 1

2nd -- 2^1 = 2

3rd -- 2^2 = 4

                = 8

                = 16

                = 32

                = 64 

8th -- 2^7 = 128

\

**1+2+4+8+16+32+64+128 = 255**

\

**192.168.1.1** 

\

192             168           1               1

11000000\.10101000.00000001.00000001

\

below calculation is for 168

2^7 = 128

2^5 = 32

2^3 = 8

\

![a17b79c6-b342-4bf5-a5fc-c3bc0f0a0f7d.png|703](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/a17b79c6-b342-4bf5-a5fc-c3bc0f0a0f7d.png) [^26]

\

![](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/a1a65fa9-5b02-4ea4-aa67-2b35a04a6d86.png) [^27]

we can create 4 billion(403 crores) of IP address we can use for create networks/servers

\

2^16 = 65536 IP addresses to create servers

![a884ca8d-8e96-4156-bae8-d9801dcad63e.png|875.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/a884ca8d-8e96-4156-bae8-d9801dcad63e.png) [^28]

\

\

<mark style="background-color:#f3de6c;">**NAT -- Network address translation**<!-- {"backgroundCycleColor":"14"} --></mark>

\

Ex: home internet trying to communicate with Gmail or Facebook etc

![ffc149f1-a99b-48ec-b8c6-c3400fcee2be.png|776](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/ffc149f1-a99b-48ec-b8c6-c3400fcee2be.png) [^29]

\

<mark style="background-color:#f3de6c;">**Subnetting:**<!-- {"backgroundCycleColor":"14"} --></mark>

\

![5a22f65d-b465-4d3c-bedb-74efec32c85e.png|586](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/5a22f65d-b465-4d3c-bedb-74efec32c85e.png) [^30]

\

**10.0.0.0/16** --  2^16 IP's are possible

\

Subnets which i want to create as below.

Public subnet

Private subnet

Database subnet

\

**Subnet1 - public subnet** 

**10.0.1.0/24** --  2^8 = 256 IP are possible   (<mark style="background-color:#f3de6c;">**Note: 24 bits I am leaving for network and only remaining 8 bits i am using for servers/hosts IP assigning**<!-- {"backgroundCycleColor":"14"} --></mark>)

10\.0.1.0

10\.0.1.1

10\.0.1.2

.

.

10\.0.1.255

\-- -------------

\

**Subnet2 - private subnet** 

**10.0.2.0/24** --  2^8 = 256 IP are possible

10\.0.2.0

10\.0.2.1

10\.0.2.2

.

.

10\.0.2.255

\-- -------------

\

**Subnet3 - database subnet** 

**10.0.3.0/24** --  2^8 = 256 IP are possible

10\.0.3.0

10\.0.3.1

10\.0.3.2

.

.

10\.0.3.255

\-- -------------

**10.0.1.0/20** --  20 bits for network, 2^12 = 4096 servers/hosts you can configure and assign IP's

**10.0.1.0/32 -- 10.0.1.0 In this case only one server/host we can use for IP and remaining all use only for network.**

\

\

# <mark style="background-color:#f8914d;">**VPC  -- manual creation in AWS**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![30347f6d-bb0f-4187-88d8-dc8a89723d98.png|371](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/30347f6d-bb0f-4187-88d8-dc8a89723d98.png) [^31]

\

![a2f733e9-7b76-44fc-9fc2-a63279896c2c.png|609](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/a2f733e9-7b76-44fc-9fc2-a63279896c2c.png) [^32]

\

<mark style="background-color:#f3de6c;">**AWS pre-defined minimum & Maximum range of CIDR**<!-- {"backgroundCycleColor":"14"} --></mark>  **-- <mark style="background-color:#f3de6c;">16 to 28<!-- {"backgroundCycleColor":"14"} --></mark>**

\

10\.0.0.0/28 --  28 bits are for network, 4 bits are for hosts - 2^4 = 16 servers     --Minimum 

10\.0.0.0/16 -- 16 bits are for network, 16 bits are for hosts - 2^16 =65L hosts/servers --Maximum

\

![311f02ff-1216-4dff-b8d3-3ff6bdca5864.png|676](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/311f02ff-1216-4dff-b8d3-3ff6bdca5864.png) [^33]

\

![aa1f904c-8304-499b-918d-5a5d259124c2.png|715.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/aa1f904c-8304-499b-918d-5a5d259124c2.png) [^34]

\

<mark style="background-color:#f3de6c;">**Subnets creation:**<!-- {"backgroundCycleColor":"14"} --></mark>

\

**Subnet1 - public subnet**

![42816c6c-3e75-402f-803a-1a9ca7a51e1d.png|737](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/42816c6c-3e75-402f-803a-1a9ca7a51e1d.png) [^35]

![70ddc7b5-9edd-43f6-aa18-f22fbee93f04.png|823](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/70ddc7b5-9edd-43f6-aa18-f22fbee93f04.png) [^36]

\

![be9f377b-42e4-4952-b041-df9ad5444ade.png|859.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/be9f377b-42e4-4952-b041-df9ad5444ade.png) [^37]

\

\

**Subnet2 - private subnet**

![856967e8-709a-465d-aa5f-ee1c9fcfe5e1.png|874.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/856967e8-709a-465d-aa5f-ee1c9fcfe5e1.png) [^38]

\

\

**Subnet2 - Database subnet**

![b08c8769-3394-4ba7-8761-d69f53583abb.png|1031.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/b08c8769-3394-4ba7-8761-d69f53583abb.png) [^39]

\

\

\

<mark style="background-color:#f3de6c;">**Creating a Route table:**<!-- {"backgroundCycleColor":"14"} --></mark>

\

**Public route table creation**

\

![2d39b8a2-531c-43c5-a262-b14b09017a23.png|997](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/2d39b8a2-531c-43c5-a262-b14b09017a23.png) [^40]

![dc083a83-bfa5-48eb-847d-53c5322eeb3b.png|975.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/dc083a83-bfa5-48eb-847d-53c5322eeb3b.png) [^41]

\

**Private route table creation**

![0e9cf4b7-f56c-4676-9bf2-654756097547.png|959.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/0e9cf4b7-f56c-4676-9bf2-654756097547.png) [^42]

\

**Database route table creation**

![a2eded03-3529-4871-b53e-12a37e16b2aa.png|979.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/a2eded03-3529-4871-b53e-12a37e16b2aa.png) [^43]

\

\

<mark style="background-color:#f8d616;">**Internet gateway creation:**<!-- {"backgroundCycleColor":"25"} --></mark>

\

![e41a2c59-38b1-4eef-af38-0145f4a22fca.png|803](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/e41a2c59-38b1-4eef-af38-0145f4a22fca.png) [^44]

![2bc8c2ba-5df6-4e83-9eab-5c00f9af8e9a.png|929.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/2bc8c2ba-5df6-4e83-9eab-5c00f9af8e9a.png) [^45]

\

Attach IG to VPC:

![16e40dfa-6d78-46de-8377-e90a63c77616.png|1038.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/16e40dfa-6d78-46de-8377-e90a63c77616.png) [^46]

![ea230c4f-d91a-4f1b-93be-3ad380f1d9fc.png|1032.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/ea230c4f-d91a-4f1b-93be-3ad380f1d9fc.png) [^47]

![4785a532-4453-48ba-bec7-926401e92cf0.png|1031.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/4785a532-4453-48ba-bec7-926401e92cf0.png) [^48]

\

Till now we done below creations and attachments

![4be7702f-1b99-4446-8b6f-3dad1c7f87a1.png|465](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/4be7702f-1b99-4446-8b6f-3dad1c7f87a1.png) [^49]

\

<mark style="background-color:#f8d616;">**Now association route tables to Subnets**<!-- {"backgroundCycleColor":"25"} --></mark>

\

<mark>1st public subnet associating with public route table</mark>

![0a879f60-18dc-457d-825a-8cc0b0653ba4.png|1123.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/0a879f60-18dc-457d-825a-8cc0b0653ba4.png) [^50]

![98985f76-5da8-4b89-a8e2-9239cf3ad0cc.png|1075.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/98985f76-5da8-4b89-a8e2-9239cf3ad0cc.png) [^51]

\

![26b041e5-d8b3-42db-906d-6014d24e3693.png|1061.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/26b041e5-d8b3-42db-906d-6014d24e3693.png) [^52]

\

\

<mark>2nd private subnet associating with private route table</mark>

![4404b967-13a6-45c9-8ff6-c8d4d4c5c7df.png|1066.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/4404b967-13a6-45c9-8ff6-c8d4d4c5c7df.png) [^53]

\

\

<mark>3rd database subnet associating with private route table</mark>

![22c25417-4cf5-4317-a17c-9056dc94b3e6.png|1010.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/22c25417-4cf5-4317-a17c-9056dc94b3e6.png) [^54]

\

\

\

<mark style="background-color:#f8d616;">**Now assigning internet gateway to public route table.. (This will help to communication outside world)**<!-- {"backgroundCycleColor":"25"} --></mark>

\

![e7acde54-baf5-41e9-98fc-9848fe704989.png|1039.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/e7acde54-baf5-41e9-98fc-9848fe704989.png) [^55]

![23c33bc3-0df5-402f-8c50-489df0251a71.png|1097.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/23c33bc3-0df5-402f-8c50-489df0251a71.png) [^56]

\

![691ce8af-6808-4471-8a2d-faedb23f5092.png|1097.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/691ce8af-6808-4471-8a2d-faedb23f5092.png) [^57]

\

\

or we can check in subnets

![5f03f64a-d67b-41c8-8c8f-f73faa9487c4.png|1118.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/5f03f64a-d67b-41c8-8c8f-f73faa9487c4.png) [^58]

\

\

<mark style="background-color:#f8d616;">**Enabling pubic IP for public subnet (its not required for private subnet)**<!-- {"backgroundCycleColor":"25"} --></mark>

![3b2962a7-c9cb-4744-914f-bec6583c8242.png|1100.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/3b2962a7-c9cb-4744-914f-bec6583c8242.png) [^59]

\

![ed0666b4-b1e8-44bd-be58-483d19762854.png|1010.3333740234375](https://images.amplenote.com/f63d379e-1d79-11ef-a7bb-2e97089a9920/ed0666b4-b1e8-44bd-be58-483d19762854.png) [^60]

\

\

# <mark style="background-color:#f8914d;">**Regions and AZS**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

ap-south-1  - Region

\

AZ's   -- Create your environment in minimum 2 Availability Zones (AZ's)

ap-south-1a -- > West Mumbai --  tsunami chances high   ( 1 public subnet, 1 private subnet, 1 DB subnet, 1 web server, 1 app server, 1 DB server etc)

ap-south-1b -- > East Mumbai --  far from sea                    ( same above environment we can create here if we have budget & for security/natural calamities etc)

ap-south-1c -- > south

[^1]: terraform-modules
    > ec2 -
    gitignore
    U

[^2]: Naming conventions
    General conventions
    There should be no reason to not follow at least these conventions :)
    i
    Beware that actual cloud resources often have restrictions in allowed names. Some resources,
    for example, can't contain dashes, some must be camel-cased. The conventions in this book
    refer to Terraform names themselves.
    1. Use _ (underscore) instead of - (dash) everywhere (in resource names, data source names,
    variable names, outputs, etc).
    2. Prefer to use lowercase letters and numbers (even though UTF-8 is supported).

[^3]: Resource and data source arguments
    1. Do not repeat resource type in resource name (not partially, nor completely):
    \`resource "aws_route_table"
    "public" {}'
    A
    \`resource "aws_route_table" "public_route_table" {}'
    \`resource "aws_route_table" "public_aws_route_table" {}'

[^4]: REPOS
    terraform-modules > ec2 > ec2.tf > % resource "aws_instance" "module"
    > Ansible
    H
    resource "aws_instance" "module" {
    Concepts
    ami = var . ami
    13
    Ansible.MD
    M
    instance_type = var . instance_type
    4
    tags = var . tags
    image-1.png
    5
    image.png
    {} person.json
    M
    person.xml
    ! person.yaml
    notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-modules
    v ec2
    ec2.tf
    U

[^5]: V REPOS
    terraform-modules > ec2 > variables.tf > < variable "tags"
    > Ansible
    1
    variable "ami" {
    Concepts
    default = "ami-Of3c7d07486cad139"
    3
    Ansible.MD
    M
    type = string
    4
    image-1.png
    15
    image.png
    6
    variable "instance_type" {
    {} person.json
    M
    7
    default = "t2.micro"
    person.xml
    8
    type = string
    ! person.yaml
    9
    10
    > notes
    11
    variable "tags" {
    > Robosho-shellscripts
    M
    12
    default = {}
    > roboshop-ansible
    13
    type = map
    > roboshop-ansible-roles
    14
    > shellscripts
    > terraform
    terraform-modules
    v ec2
    ec2.tf
    U
    variables.tf
    U

[^6]: V REPOS
    terraform-modules > roboshop-ec2 > \\ ec2.tf > ...
    > Ansible
    1
    module "roboshop_ec2" {
    Concepts
    2
    source = " . ./ec2"
    3
    Ansible.MD
    M
    14
    image-1.png
    image.png
    6
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    10
    > notes
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    terraform-modules
    17
    > ec2
    18
    19
    v roboshop-ec2
    20
    .terraform
    21
    E.terraform.lock.hcl
    U
    22
    ec2.tf
    U
    23
    provider.tf
    U
    24
    25
    .gitignore
    U
    26

[^7]: EXPLORER
    . .
    provider.tf .\\roboshop-ec2 U X ec2.tf .. \\roboshop-ec2 U .
    provider.tf terraform-provisioners
    REPOS
    terraform-modules > roboshop-ec2 > provider.tf > ...
    > Ansible
    1
    terraform {
    Concepts
    2
    required_providers {
    3
    Ansible.MD
    M
    aws = {
    4
    source = "hashicorp/aws"
    image-1.png
    5
    version = "5.49.0" #AWS provider version, not terraform version
    image.png
    6
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    > notes
    10
    provider "aws" {
    11
    > Robosho-shellscripts
    region = "us-east-1"
    M
    12
    }
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    terraform-modules
    > ec2
    roboshop-ec2
    .terraform
    E.terraform.lock.hcl
    U
    ec2.tf
    U
    provider.tf
    U

[^8]: terraform-modules > @ .gitignore
    # Local . terraform directories
    N
    \*\*/ . terraform/\*
    3
    4
    # . tfstate files
    5
    \* . tfstate
    6
    \* . tfstate.\*
    7
    8
    # Crash log files
    9
    crash . log
    10
    crash. \* . log
    11
    12
    # Exclude all . tfvars files, which are likely to contain sensitive data, such as
    13
    # password, private keys, and other secrets. These should not be part of version
    14
    # control as they are data points which are potentially sensitive and subject
    15
    # to change depending on the environment.
    16
    \*. tfvars
    17
    \* . tfvars . json
    18
    19
    # Ignore override files as they are usually used to override resources locally and so
    20
    # are not checked in
    21
    override. tf
    22
    override. tf . json
    23
    \*_override. tf
    24
    \*_override. tf . json
    25
    26
    # Include override files you do wish to add to version control using negated pattern
    27
    # !example_override. tf
    28
    29
    # Include tfplan files to ignore the plan output of command: terraform plan -out=tfplan
    30
    # example: \*tfplan\*
    31
    32
    # Ignore CLI configuration files
    33
    . terraformrc
    34
    terraform. rc

[^9]: chowd@chowdary MINGW64 /e/AWSDevops/Repos (main)
    $ cd terraform-modules/
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos /terraform-modules (main)
    $ cd roboshop-ec2/
    chowd@chowdary MINGW64 /e/AWSDevops /Repos/terraform-modules /roboshop-ec2 (main)
    $ terraform init
    Initializing the backend. . .
    Initializing provider plugins . . .
    Finding hashicorp/aws versions matching "5.49.0"...
    Installing hashicorp/aws v5 . 49.0. ..
    Installed hashicorp/aws v5. 49.0 (signed by Hashicorp)
    Terraform has created a lock file . terraform. lock.hc1 to record the provider
    selections it made above. Include this file in your version control repository
    so that Terraform can guarantee to make the same selections by default when
    you run "terraform init" in the future.
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. Al1 Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    chowd@chowdary MINGW64 /e/AWSDevops/Repos/terraform-modules /roboshop-ec2 (main)

[^10]: chowd@Chowdary MINGW64 /e/AWSDevops/Repos/terraform-modules/roboshop-ec2 (main)
    terraform plan
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # module . roboshop_ec2 . aws_instance . module will be created
    resource "aws_instance" "module" {
    am7
    = "ami -Of 3c7 d07486cad139"
    arn
    = (known after apply)
    associate_public_ip_address
    = (known after apply)
    availability_zone
    = (known after apply)
    cpu_core_count
    = (known after apply)
    cpu_threads_per_core
    = (known after apply)
    disable_api_stop
    = (known after apply)
    disable_api_termination
    = (known after apply)
    ebs_optimized
    = (known after apply)
    get_password_data
    false
    host_id
    = (known after apply)
    host_resource_group_arn
    = (known after apply)
    i am_instance_profile
    (known after apply)
    id
    (known after apply)
    instance_initiated_shutdown_behavior
    (known after apply)
    instance_lifecycle
    (known after apply)
    instance_state
    (known after apply)
    instance_type
    "t2 . micro"
    ipv6_address_count
    =
    (known after apply)
    ipv6_addresses
    E
    (known after apply)
    key_name
    =
    (known after apply)
    monitoring
    (known after apply)
    outpost_arn
    =
    (known after apply)
    password_data
    = (known after apply)
    placement_group
    = (known after apply)
    placement_partition_number
    (known after apply)
    primary_network_interface_id
    =
    (known after apply)
    private_dns
    = (known after apply)
    private_ip
    = (known after apply)
    public_dns
    = (known after apply)
    public_ip
    =
    (known after apply)
    secondary_private_ips
    =
    (known after apply)
    security_groups
    = (known after apply)
    source_dest_check
    true
    spot_instance_request_id
    (known after apply)
    subnet_id
    (known after apply)
    tags_all
    = (known after apply)
    tenancy
    = (known after apply)
    user_data
    = (known after apply)
    user_data_base64
    =
    (known after apply)
    + user_data_replace_on_change
    = false
    vpc_security_group_ids
    (known after apply)
    Plan: 1 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    chowd@chowdary MINGW64 /e/AWSDevops /Repos/terraform-modules/roboshop-ec2 (main)

[^11]: V REPOS
    terraform-modules > roboshop-ec2 > ec2.tf > ...
    > Ansible
    1
    module "roboshop_ec2" {
    Concepts
    2
    source = " . ./ec2"
    3
    Ansible.MD
    M
    instance_type = "t3.medium"
    image-1.png
    5
    image.png
    6
    {} person.json
    M
    17
    person.xml
    8
    person.yaml
    9
    10
    notes
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    v terraform-modules
    17
    18
    > ec2
    19
    roboshop-ec2
    20
    > .terraform
    21
    E .terraform.lock.hcl
    U
    22
    ec2.tf
    U
    23
    provider.tf
    U
    24
    U
    25
    .gitignore
    26

[^12]: EXPLORER
    . . .
    hore terraform
    .gitignore terraform-multi-env
    .gitignore terraform-provisioners
    REPOS
    terraform-modules > ec2 > outputs.of > 4 output "instance_id"
    > Ansible
    output "public_ip" {
    Concepts
    2
    value = aws_instance . module. public_ip
    3
    Ansible.MD
    M
    4
    image-1.png
    15
    output "private_ip" {
    image.png
    16
    value = aws_instance . module . private_ip
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    output "instance_id" {
    > notes
    10
    value = aws_instance . module. id
    11
    }
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    terraform-modules
    v ec2
    ec2.tf
    U
    outputs.tf
    U
    readme.MD
    U
    variables.tf
    U
    roboshop-ec2
    > .terraform
    E.terraform.lock.hcl
    U

[^13]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos /terraform-modules /roboshop-ec2 (main)
    terraform plan
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols :
    create
    Terraform will perform the following actions :
    # module . roboshop_ec2 . aws_instance . module will be created
    resource "aws_instance" "module" {
    ami
    "ami-Of 3c7d07486cad139"
    arn
    (known after apply)
    associate_public_ip_address
    (known after apply)
    availability_zone
    = (known after apply)
    cpu_core_count
    = (known after apply)
    cpu_threads_per_core
    = (known after apply)
    disable_api_stop
    = (known after apply)
    disable_api_termination
    = (known after apply)
    ebs_optimized
    = (known after apply)
    get_password_data
    = false
    host_id
    (known after apply)
    host_resource_group_arn
    = (known after apply)
    i am_instance_profile
    = (known after apply)
    id
    = (known after apply)
    instance_initiated_shutdown_behavior
    = (known after apply)
    instance_lifecycle
    (known after apply)
    instance_state
    (known after
    apply)
    instance_type
    "t3 . medium"
    ipv6_address_count
    = (known after apply)
    ipv6_addresses
    = (known after apply)
    key_name
    = (known after apply)
    monitoring
    = (known after apply)
    outpost_arn
    (known after apply)
    password_data
    = (known after apply)
    placement_group
    = (known after apply)
    placement_partition_number
    = (known after apply)
    primary_network_interface_id
    = (known after apply)
    private_dns
    (known after apply)
    private_ip
    = (known after apply)
    public_dns
    = (known after apply)
    public_ip
    = (known after apply)
    secondary_private_ips
    = (known after apply)
    security_groups
    = (known after apply)
    source_dest_check
    = true
    spot_instance_request_id
    = (known after apply)
    subnet_id
    = (known after apply)
    tags_al1
    = (known after apply)
    tenancy
    = (known after apply)
    + user_data
    (known after apply)
    user_data_base64
    = (known after apply)
    + user_data_replace_on_change
    = false
    vpc_security_group_ids
    (known after apply)
    Plan: 1 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply"
    now.

[^14]: REPOS
    terraform-modules > roboshop-ec2 > variables.of > < variable "tagssssss"
    > Ansible
    1
    variable "instance_typeeeeee" {
    Concepts
    2
    default = "t3.medium"
    3
    Ansible.MD
    M
    14
    image-1.png
    5
    variable "tagssssss" {
    image.png
    16
    default = {
    {} person.json
    M
    7
    Name = "roboshop"
    person.xml
    18
    terraform = "true"
    person.yaml
    9
    environment = "dev"
    10
    notes
    11
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-modules
    v ec2
    ec2.tf
    U
    variables.tf
    U
    roboshop-ec2
    > .terraform
    E .terraform.lock.hcl
    U
    ec2.tf
    U
    provider.tf
    U
    variables.tf
    U

[^15]: V REPOS
    terraform-modules > roboshop-ec2 > ec2.tf > ...
    > Ansible
    H
    module "roboshop_ec2" {
    Concepts
    2
    source = " . ./ec2"
    3
    Ansible.MD
    M
    instance_type = var . instance_typeeeeee
    14
    tags = var . tagssssss
    image-1.png
    15
    image.png
    16
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    > notes
    10
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    v terraform-modules
    17
    18
    v ec2
    O
    19
    ec2.tf
    U
    20
    variables.tf
    U
    21
    roboshop-ec2
    22
    > .terraform
    23
    E .terraform.lock.hcl
    U
    24
    ec2.tf
    U
    25
    26

[^16]: chowd@Chowdary MINGW64 /e/AWSDevops/Repos/terraform-modules /roboshop-ec2 (main)
    $ terraform plan
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols:
    create
    Terraform will perform the following actions :
    # module . roboshop_ec2. aws_instance . module will be created
    resource "aws_instance" "module" {
    ami
    "ami -Of 3c7 d07486cad139"
    arn
    = (known after apply)
    associate_public_ip_address
    (known after apply)
    availability_zone
    (known after apply)
    cpu_core_count
    (known after apply)
    cpu_threads_per_core
    (known after apply)
    disable_api_stop
    (known after apply)
    disable_api_termination
    =
    (known after apply)
    ebs_optimized
    (known after apply)
    get_password_data
    = false
    host_id
    (known after apply)
    host_resource_group_arn
    (known after apply)
    1 am_instance_profile
    =
    (known after apply)
    id
    (known after apply)
    instance_initiated_shutdown_behavior
    E
    (known after apply)
    instance_lifecycle
    (known after apply)
    instance_state
    (known after apply)
    instance_type
    "t3. medium"
    ipv6_address_count
    (known after apply)
    ipv6_addresses
    (known after apply)
    key_name
    (known after apply)
    monitoring
    (known after apply)
    outpost_arn
    (known after apply)
    password_data
    E
    (known after apply)
    placement_group
    (known after apply)
    placement_partition_number
    (known after apply)
    primary_network_interface_id
    (known after
    apply)
    private_dns
    (known after apply)
    private_ip
    (known after apply)
    public_dns
    =
    (known after apply)
    public_ip
    =
    (known after apply)
    secondary_private_ips
    E
    (known after apply)
    security_groups
    (known after apply)
    source_dest_check
    true
    spot_instance_request_id
    (known after apply)
    subnet_id
    (known after apply)
    +
    tags
    "Name"
    E
    "roboshop"
    "environment"
    =
    "dev"
    "terraform"
    = "true"
    }
    tags_al1
    "Name"
    "roboshop"
    "environment"
    =
    "dev"
    "terraform'
    = "true"
    tenancy
    = (known after apply)
    +
    user_data
    (known after apply)
    user_data_base64
    (known after apply)
    +
    user_data_replace_on_change
    = false
    vpc_security_group_ids
    (known after apply)
    Plan: 1 to add, 0 to change, 0 to destroy.

[^17]: REPOS
    terraform-modules > roboshop-ec2 > outputs.of > < output "private"
    > Ansible
    1
    output "public" {
    N
    Concepts
    value = module . roboshop_ec2. public_ip
    3
    Ansible.MD
    M
    4
    image-1.png
    5
    output "private" {
    image.png
    6
    value = module . roboshop_ec2 . private_ip
    {} person.json
    M
    7
    person.xml
    ! person.yaml
    > notes
    O
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-modules
    > ec2
    v roboshop-ec2
    > .terraform
    E.terraform.lock.hcl
    U
    ec2.tf
    U
    outputs.tf
    U
    provider.tf
    U
    variables.tf
    U
    .gitignore
    U

[^18]: source_dest_check
    =
    true
    spot_instance_request_id
    E
    (known after apply)
    +
    subnet_id
    (known after apply)
    +
    tags
    +
    "Name"
    "roboshop"
    +
    "environment"
    E
    "dev"
    +
    "terraform"
    =
    "true"
    +
    tags_a17
    "Name"
    "roboshop"
    +
    "environment"
    E
    "dev"
    +
    "terraform"
    "true"
    +
    tenancy
    = (known after apply)
    +
    user_data
    E
    (known after apply)
    user_data_base64
    = (known after apply)
    +
    user_data_replace_on_change
    E
    false
    +
    vpc_security_group_ids
    E
    (known after apply)
    Plan: 1 to add, 0 to change, 0 to destroy.
    Changes to Outputs :
    + private = (known after apply)
    public = (known after apply)
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    chowd@chowdary MINGW64 /e/AWSDevops /Repos /terraform-modules /roboshop-ec2 (main)

[^19]: subnet_id
    (known after apply)
    tags
    "Name"
    E
    "roboshop"
    +
    "environment"
    "dev"
    +
    "terraform"
    "true"
    +
    tags_al1
    =
    "Name"
    "roboshop"
    "environment"
    "dev"
    +
    "terraform"
    =
    "true"
    }
    tenancy
    =
    (known after apply)
    user_data
    =
    (known after apply)
    user_data_base64
    =
    (known after apply)
    user_data_replace_on_change
    = false
    vpc_security_group_ids
    (known after apply)
    Plan: 1 to add, 0 to change, 0 to destroy.
    Changes to Outputs:
    private = (known after apply)
    + public = (known after apply)
    module . roboshop_ec2 . aws_instance . module: Creating. . .
    module . roboshop_ec2 . aws_instance . module: Stil1 creating. .. \[10s elapsed\]
    module . roboshop_ec2 . aws_instance . module: Creation complete after 17s \[id=i-0c4d007c3e250804f\]
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
    Outputs :
    private = "172. 31.40.74"
    public = "35 . 174. 10.83"
    chowd@Chowdary MINGW64 /e/AWSDevops/Repos /terraform-modules /roboshop-ec2 (main)
    $

[^20]: aws
    Search
    (?)
    Services
    Q
    \[Alt+S\]
    A
    N. Virginia
    chowda
    EC2
    Route 53
    OF IAM
    CO VPC
    $3
    DynamoDB
    Instances (1/1) Info
    Connect
    Instance state
    Actions
    Launch instances
    4
    EC2 Dashboard
    X
    1
    EC2 Global View
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    <
    Events
    Name _
    Instance ID
    Instance state
    Instance type
    Status check
    Alarm status
    Availability
    Console-to-Code Preview
    roboshop
    i-0c4d007c3e250804f
    Running
    Q Q
    t3.medium
    Initializing
    View alarms +
    us-east-1a
    Instances

[^21]: Plan: 0 to add, 0 to change, 1 to destroy.
    Changes to Outputs:
    private = "172. 31. 40.74" -> null
    - public = "35 . 174. 10.83" -> null
    module . roboshop_ec2 . aws_instance . module: Destroying. .. \[id=i-0c4d007c3e250804f\]
    module . roboshop_ec2. aws_instance . module: Still destroying... \[id=i-0c4d007c3e250804f, 10s elapsed\]
    module . roboshop_ec2. aws_instance . module: Still destroying. . .
    \[id=i-0c4d007 c3e250804f, 20s elapsed\]
    module . roboshop_ec2. aws_instance . module: Still destroying. .
    \[id=i-0c4d007c3e250804f , 30s elapsed\]
    module . roboshop_ec2 . aws_instance . module: Still destroying. . .
    \[id=i-0c4d007c3e250804f, 40s elapsed\]

[^22]: physical space
    AC
    power backup
    network connections
    security gaurds
    network field engineer
    linux admin team

[^23]: Village --> VPC
    - -- -------------
    streets --> admin, proper organisation and maintaince
    I
    subnets -->
    HR department
    Databases
    Fianance

[^24]: Roads
    Public Affairs
    Ministers
    PMO
    Secure roads
    private roads
    Arch
    X
    private roads
    Secure roads
    Public Affairs
    Ministers
    PMO
    Roads

[^25]: Public Subnets
    Private Subnets
    Database Servers
    Public Subnets
    Private Subnets
    Database Servers

[^26]: 15. 197 .142.173 --> facebook IP
    home network --> facebook network --> particular server
    IP = Network + Server IP

[^27]: 2 to the Power of 32 is equal to 4294967296.

[^28]: 10.0.0.0/16 --> first 16 bits are for network, next 16 bits are for servers
    10 .0.0.1
    10 .0.0.2
    10 .0.0.3
    10 .0.0.3
    = 212
    0
    0
    1
    0
    1
    - = 213
    0
    0 0
    10
    OH
    10
    01 1
    I
    0 0
    1
    0
    1
    O
    111

[^29]: 49.43.240.14
    192.168.29.1
    192.168.29.3
    ISP
    192.168.29.2
    IPv4 address
    192.168.29.4

[^30]: 549906 --> village pin code
    street --> street 1
    home number --> 1-12 --> street 1 and house 12

[^31]: Amazon Virtual Private Cloud is a commercial cloud
    computing service that provides a virtual private cloud,
    by provisioning a logically isolated section of Amazon
    Web Services Cloud. Enterprise customers can
    access the Amazon Elastic Compute Cloud over an
    IPsec based virtual private network. Wikipedia

[^32]: private ip address range
    X U a Q
    Q All
    Images
    D Videos
    Books
    News
    : More
    Tools
    Q Class a
    Q Class B
    Q Class C
    Private IPv4 addresses
    RFC 1918 name
    IP address range
    Host ID size
    24-bit block
    10.0.0.0 - 10.255.255.255
    24 bits
    20-bit block
    172.16.0.0 - 172.31.255.255
    20 bits
    16-bit block
    192.168.0.0 - 192.168.255.255
    16 bits

[^33]: VPC > Your VPCs > Create VPC
    Create VPC Info
    A VPC is an isolated portion of the AWS Cloud populated by AWS objects, such as Amazon EC2 instances.
    VPC settings
    Resources to create Info
    Create only the VPC resource or the VPC and other networking resources.
    VPC only
    O VPC and more
    Name tag - optional
    Creates a tag with a key of 'Name' and a value that you specify.
    IPV4 CIDR block Info
    IPV4 CIDR manual input
    O IPAM-allocated IPV4 CIDR block
    IPV4 CIDR
    10.0.0.0/16
    CIDR block size must be between /16 and /28.
    IPV6 CIDR block Info
    No IPV6 CIDR block
    IPAM-allocated IPV6 CIDR block
    Amazon-provided IPV6 CIDR block
    O IPV6 CIDR owned by me
    Tenancy Info
    Default

[^34]: VPC > Your VPCs > vpc-02df05c586d93a701
    vpc-02df05c586d93a701 / roboshop-vpc
    Actions V
    Details Info
    VPC ID
    State
    DNS hostnames
    DNS resolution
    vpc-02df05c586d93a701
    Available
    Disabled
    Enabled
    Tenancy
    DHCP option set
    Main route table
    Main network ACL
    Default
    dopt-069994658cab2e8d2
    rtb-Oba4b60a44a44c720
    acl-0612b5efd93a0a 197
    Default VPC
    IPV4 CIDR
    IPV6 pool
    IPV6 CIDR (Network border group)
    No
    10.0.0.0/16
    Network Address Usage metrics
    Route 53 Resolver DNS Firewall rule
    Owner ID
    Disabled
    groups
    158724841371
    Resource map
    CIDRS
    Flow logs
    Tags
    Integrations

[^35]: Create subnet Info
    VPC
    VPC ID
    Create subnets in this VPC.
    vpc-02df05c586d93a701 (roboshop-vpc)
    Associated VPC CIDRs
    IPV4 CIDRS
    10.0.0.0/16
    Subnet settings
    Specify the CIDR blocks and Availability Zone for the subnet.
    Subnet 1 of 1
    Subnet name
    Create a tag with a key of 'Name' and a value that you specify.
    public-subnet
    The name can be up to 256 characters long.
    Availability Zone Info
    Choose the zone in which your subnet will reside, or let Amazon choose one for you.
    US East (N. Virginia) / us-east-1a
    IPV4 VPC CIDR block Info

[^36]: Subnet 1 of 1
    Subnet name
    Create a tag with a key of 'Name' and a value that you specify.
    public-subnet
    The name can be up to 256 characters long.
    Availability Zone Info
    Choose the zone in which your subnet will reside, or let Amazon choose one for you.
    US East (N. Virginia) / us-east-1a
    IPV4 VPC CIDR block Info
    Choose the VPC's IPV4 CIDR block for the subnet. The subnet's IPV4 CIDR must lie within this block.
    10.0.0.0/16
    IPv4 subnet CIDR block
    10.0.1.0/24
    256 IPS
    <
    >
    Tags - optional
    Key
    Value - optional
    Q Name
    X
    Q public-subnet
    X
    Remove
    Add new tag
    You can add 49 more tags.
    Remove
    Add new subnet
    Cancel
    Create subnet

[^37]: Subnets (1) Info
    C
    Actions
    Create subnet
    Q Find resources by attribute or tag
    Subnet ID : subnet-057f6c30051b578c6
    X
    Clear filters
    <
    1
    Name
    4
    Subnet ID
    4
    State
    4
    VPC
    IPV4 CIDR
    public-subnet
    subnet-057f6c300516578c6
    Available
    vpc-02df05c586d93a701 \| robo...
    10.0.1.0/24

[^38]: Subnets (8) Info
    G
    Actions
    Create subnet
    Q Find resources by attribute or tag
    < 1 >
    Name
    4
    Subnet ID
    4
    State
    V
    VPC
    V
    IPV4 CIDR
    subnet-097674cb818e57cda
    Available
    vpc-0817 cae8968304c06
    172.31.0.0/20
    subnet-Oc02fa3b6c12f822a
    Available
    vpc-0817cae8968304c06
    172.31.32.0/20
    subnet-06765624369d64fe6
    Available
    vpc-0817cae8968304c06
    172.31.80.0/20
    subnet-0873e3231bac49c20
    Available
    vpc-0817 cae8968304c06
    172.31.64.0/20
    subnet-076650bcf0b486323
    Available
    vpc-0817cae8968304c06
    172.31.16.0/20
    -
    subnet-Od3fb05110e2dge48
    Available
    vpc-0817cae89b8304c06
    172.31.48.0/20
    public-subnet
    subnet-057f6c30051b578c6
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.1.0/24
    private subnet-
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24

[^39]: O
    public-subnet
    subnet-057f6c300516578c6
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.1.0/24
    private subnet
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24
    V
    database-subnet
    subnet-08bfd9e9711377709
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.3.0/24

[^40]: VPC > Route tables > Create route table
    Create route table Info
    A route table specifies how packets are forwarded between the subnets within your VPC, the internet, and your VPN
    connection.
    Route table settings
    Name - optional
    Create a tag with a key of 'Name' and a value that you specify.
    public-route-roboshop
    VPC
    The VPC to use for this route table.
    vpc-02df05c586d93a701 (roboshop-vpc)
    Tags
    A tag is a label that you assign to an AWS resource. Each tag consists of a key and an optional value. You can use tags to search and filter
    your resources or track your AWS costs.
    Key
    Value - optional
    Q Name
    X
    Q public-route-roboshop
    X
    Remove
    Add new tag
    You can add 49 more tags.
    Cancel
    Create route table

[^41]: Route tables (3) Info
    G
    Actions
    Create route table
    Find resources by attribute or tag
    <
    1
    Name
    4
    Route table ID
    Explicit subnet associ...
    Edge associations
    Main
    4
    VPC
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817 cae896830
    rtb-Oba4b60a44a44c720
    Yes
    vpc-02df05c586d93
    public-route-roboshop
    rtb-06d5ab6e646 161452
    No
    vpc-02df05c586d93

[^42]: Route tables (4) Info
    G
    Actions
    Create route table
    Q Find resources by attribute or tag
    < 1 >
    Name
    4
    Route table ID
    4
    Explicit subnet associ...
    Edge associations
    Main
    V
    VPC
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817 cae89683
    rtb-Oba4b60a44a44c720
    Yes
    vpc-02df05c586d9
    public-route-roboshop
    rtb-06d5ab6e64b 161452
    No
    vpc-02df05c586d9:
    private-route-roboshop
    rtb-0819136c9076c97d1
    No
    vpc-02df05c586d9

[^43]: Route tables (1/5) Info
    C
    Actions
    Create route table
    A
    Q Find resources by attribute or tag
    <
    1 >
    -
    Name
    4
    Route table ID
    Explicit subnet associ... V Edge associations
    Main
    4
    VPC
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817 cae896830
    rtb-Oba4b60a44a44c720
    Yes
    vpc-02df05c586d93
    public-route-roboshop
    rtb-06d5ab6e646 161452
    subnet-057f6c30051657...
    No
    vpc-02df05c586d93,
    0
    private-route-roboshop
    rtb-0819136c9076c97d1
    subnet-026ec7d50f3242...
    No
    vpc-02df05c586d93.
    V
    database-route-roboshop
    rtb-00c30cf5efb 1f91be
    No
    vpc-02df05c586d93,

[^44]: VPC > Internet gateways > Create internet gateway
    Create internet gateway info
    An internet gateway is a virtual router that connects a VPC to the internet. To create a new internet gateway specify the name
    for the gateway below.
    Internet gateway settings
    Name tag
    Creates a tag with a key of 'Name' and a value that you specify.
    roboshop-IG
    Tags - optional
    A tag is a label that you assign to an AWS resource. Each tag consists of a key and an optional value. You can use tags to search and filter
    your resources or track your AWS costs.
    Key
    Value - optional
    Q Name
    X
    Q roboshop-IG
    X
    Remove
    Add new tag
    You can add 49 more tags.
    Cancel
    Create internet gateway

[^45]: Internet gateways (2) Info
    C
    Actions
    4
    Create internet gateway
    Q Search
    < 1
    Name
    Internet gateway ID
    4
    State
    4
    VPC ID
    Owner
    O
    igw-059405258c34db2a1
    Attached
    vpc-0817cae8968304c06
    1587248413
    roboshop-IG
    igw-Od4013d53808e5a19
    Detached
    1587248413

[^46]: VPC > Internet gateways > igw-0d4013d53808e5a19
    igw-Od4013d53808e5a19 / roboshop-IG
    Actions
    Attach to VPC
    Details Info
    Detach from VPC
    Manage tags
    Internet gateway ID
    State
    VPC ID
    Owner
    igw-Od4013d53808e5a 19
    Detached
    1587248413 Delete
    Tags
    Manage tags
    Q Search tags
    1 >
    Key
    Value
    Name
    roboshop-IG

[^47]: VPC > Internet gateways > Attach to VPC (igw-0d4013d53808e5a 19)
    Attach to VPC (igw-Od4013d53808e5a19)
    Info
    VPC
    Attach an internet gateway to a VPC to enable the VPC to communicate with the internet. Specify the VPC to attach below.
    Available VPCs
    Attach the internet gateway to this VPC.
    Q vpc-02df05c586d93a701
    X
    AWS Command Line Interface command
    Cancel
    Attach internet gateway

[^48]: Internet gateways (2) Info
    C
    Actions
    Create internet gateway
    Q Search
    < 1 >
    Name
    4
    Internet gateway ID
    4
    State
    4
    VPC ID
    4
    Owner
    igw-059405258c34db2a1
    Attached
    vpc-0817 cae89b8304c06
    15872484
    n
    roboshop-IG
    igw-Od4013d53808e5a19
    Attached
    vpc-02df05c586d93a701 \| roboshop-vpc
    15872484

[^49]: VPC
    internet gateway --> VPC
    public subnet
    private subnet
    public route table
    private route table

[^50]: public-subnet
    subnet-057f6c30051b578c6
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.1.0/24
    private subnet
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24
    O
    subnet-057f6c30051b578c6 / public-subnet
    Details
    Flow logs
    Route table
    Network ACL
    CIDR reservations
    Sharing
    Tags
    Route table: rtb-0ba4b60a44a44c720
    Edit route table association
    Routes (1)
    Q Filter routes
    <
    1
    Destination
    Target
    10.0.0.0/16
    local

[^51]: VPC > Subnets > subnet-057f6c30051b578c6 > Edit route table association
    Edit route table association Info
    Subnet route table settings
    Subnet ID
    subnet-057f6c30051b578c6
    Route table ID
    rtb-06d5ab6e646 161452 (public-route-roboshop)
    G
    Routes (1)
    O Filter routes
    <1 >
    Destination
    Target
    10.0.0.0/16
    local
    Cancel
    Save

[^52]: public-subnet
    subnet-057f6c30051b578c6
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.1.0/24
    private subnet
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24
    O
    subnet-057f6c30051b578c6 / public-subnet
    Details
    Flow logs
    Route table
    Network ACL
    CIDR reservations
    Sharing
    Tags
    Route table: rtb-06d5ab6e64b 161452 / public-route-roboshop
    Edit route table association
    Routes (1)
    Q Filter routes
    1
    Destination
    V
    Target
    10.0.0.0/16
    local

[^53]: O
    public-subnet
    subnet-057f6c30051b578c6
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.1.0/24
    V
    private subnet
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24
    subnet-026ec7d50f3242c4d / private subnet
    Details
    Flow logs
    Route table
    Network ACL
    CIDR reservations
    Sharing
    Tags
    Route table: rtb-0819136c9076c97d1 / private-route-roboshop
    Edit route table association
    Routes (1)
    Q Filter routes
    <
    1
    Destination
    4
    Target
    10.0.0.0/16
    local

[^54]: V
    database-subnet
    subnet-08bfd9e9711377709
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.3.0/24
    subnet-08bfd9e9711377709 / database-subnet
    Details
    Flow logs
    Route table
    Network ACL
    CIDR reservations
    Sharing
    Tags
    Route table: rtb-00c30cf5efb 1f91be / database-route-roboshop
    Edit route table association
    Routes (1)

[^55]: Route tables (1/4) Info
    C
    Actions V
    Create route table
    Q Find resources by attribute or tag
    < 1 >
    Name
    4
    Route table ID
    4
    Explicit subnet associ... V Edge associations
    Main
    V VPC
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817cae896830
    rtb-Oba4b60a44a44c720
    Yes
    vpc-02df05c586d93
    V
    public-route-roboshop
    rtb-06d5ab6e646 161452
    subnet-057f6c30051657...
    No
    upc-02df05c586d93.
    private-route-roboshop
    rtb-0819136c9076c97d1
    subnet-026ec7d50f3242...
    No
    vpc-02df05c586d93
    0 0 0
    rtb-06d5ab6e64b 161452 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (1)
    Both
    Edit routes
    Q Filter routes
    <
    1
    Destination
    4
    Target
    4
    Status
    Propagated
    10.0.0.0/16
    local
    Active
    No

[^56]: VPC > Route tables > rtb-06d5ab6e64b161452 > Edit routes
    Edit routes
    Destination
    Target
    Status
    Propagated
    10.0.0.0/16
    local
    Active
    No
    Q local
    X
    Q 0.0.0.0/0
    X
    Internet Gateway
    No
    Remove
    Q igw-0d4013d53808e5a 19
    X
    Use: "igw-Od4013d53808e5a19"
    Add route
    igw-Od4013d53808e5a 19 (roboshop-IG)
    Cancel
    Preview
    Save changes

[^57]: V
    public-route-roboshop
    rtb-06d5ab6e64b 161452
    subnet-057f6c30051657...
    No
    vpc-02df05c586d93.
    private-route-roboshop
    rtb-0819136c9076c97d1
    subnet-026ec7d50f3242...
    No
    vpc-02df05c586d93
    rtb-06d5ab6e64b 161452 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (2)
    Both
    Edit routes
    Q Filter routes
    <
    1 >
    Destination
    Target
    4
    Status
    Propagated
    0.0.0.0/0
    igw-Od4013d53808e5a 19
    Active
    No
    10.0.0.0/16
    local
    Active
    No

[^58]: Subnets (1/8) Info
    C
    Actions V
    Create subnet
    Q Find resources by attribute or tag
    1 )
    Name
    4
    Subnet ID
    4
    State
    4
    VPC
    4
    IPV4 CIDR
    subnet-097674cb818e57cda
    Available
    vpc-0817 cae8968304c06
    172.31.0.0/20
    subnet-Oc02fa3b6c12f822a
    Available
    vpc-0817cae8968304c06
    172.31.32.0/20
    subnet-06765624369d64fe6
    Available
    vpc-0817cae8968304c06
    172.31.80.0/20
    3 0OOO OO
    subnet-0873e3231bac49c20
    Available
    vpc-0817cae8968304c06
    172.31.64.0/20
    subnet-076650bcf0b486323
    Available
    vpc-0817cae8968304c06
    172.31.16.0/20
    subnet-Od3f605110e2d9e48
    Available
    pc-0817 cae8968304c06
    172.31.48.0/20
    public-subnet
    subnet-057f6c300516578c6
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.1.0/24
    private subnet
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24
    subnet-057f6c30051b578c6 / public-subnet
    Details
    Flow logs
    Route table
    Network ACL
    CIDR reservations
    Sharing
    Tags
    Route table: rtb-06d5ab6e646 161452 / public-route-roboshop
    Edit route table association
    Routes (2)
    Q Filter routes
    < 1 >
    Destination
    4
    Target
    10.0.0.0/16
    local
    0.0.0.0/0
    igw-0d4013d53808e5a 19

[^59]: Subnets (1/8) Info
    C
    Actions
    Create subnet
    Q Find resources by attribute or tag
    View details
    -
    Name
    Subnet ID
    Create flow log
    4
    State
    VPC
    Edit subnet settings
    subnet-097674cb818e57cda
    Available
    vpc-0817cae8968304co
    0
    Edit IPV6 CIDRs
    subnet-Oc02fa3b6c12f822a
    Available
    vpc-0817cae8968304co
    20
    Edit network ACL association
    subnet-06765624369d64fe6
    Available
    vpc-0817cae8968304co
    120
    0 0 0 0 0 0
    Edit route table association
    subnet-0873e3231bac49c20
    Available
    vpc-0817cae8968304co
    20
    Edit CIDR reservations
    subnet-076650bcf0b486323
    Available
    vpc-0817cae8968304co
    120
    Share subnet
    subnet-Od3fb051 10e2d9e48
    Available
    vpc-0817cae8968304co
    20
    Manage tags
    V
    public-subnet
    subnet-057f6c30051b578c6
    Available
    vpc-02df05c586d93a70
    Delete subnet
    0
    private subnet
    subnet-026ec7d50f3242c4d
    Available
    vpc-02df05c586d93a701 \| roboshop-vpc
    10.0.2.0/24

[^60]: VPC > Subnets > subnet-057f6c30051b578c6 > Edit subnet settings
    Edit subnet settings info
    Subnet
    Subnet ID
    Name
    subnet-057f6c300516578c6
    public-subnet
    Auto-assign IP settings Info
    Enable AWS to automatically assign a public IPv4 or IPv6 address to a new primary network interface for an instance in this subnet.
    Enable auto-assign public IPv4 address Info
    Enable auto-assign customer-owned IPv4 address Info
    Option disabled because no customer owned pools found.
    Resource-based name (RBN) settings Info
    Specify the hostname type for EC2 instances in this subnet and optional RBN DNS query settings.
    Enable resource name DNS A record on launch Info
    Enable resource name DNS AAAA record on launch Info
    Hostname type Info
    O Resource name
    IP name
    DNS64 settings

