---
title: 28Day_Terraform
uuid: d85dab74-1404-11ef-a737-9a665e06d35f
version: 976
created: '2024-05-17T09:50:51+05:30'
tags:
  - terraform
---

\

***Topics:***

1. *<mark style="background-color:#f8d616;">Multiple environments<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *tfvars*

    1. *workspaces*

    1. *Different Repos completely*

1. <mark style="background-color:#f8d616;">provisioners<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"offset":1} -->

    1. Local-exec

    1. remote-exec

\

\

# *<mark style="background-color:#f8914d;">**Multiple environments:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*How to create multiple environments with terraform? There are multiple ways*

      *1. tfvars*

      *2. workspaces*

      *3. Different Repos completely*

\

# *<mark style="background-color:#f8914d;">**tfvars**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*create a new repo - **terraform-multi-env***

![d0b7341b-d34b-4e11-8ff8-d56a9af085e7.png|913.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/d0b7341b-d34b-4e11-8ff8-d56a9af085e7.png) [^1]

\

*Also new folder in VS - **terraform-multi-env***

![773e5217-1674-4373-abc9-0c0de65187a6.png|803](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/773e5217-1674-4373-abc9-0c0de65187a6.png) [^2]

\

*subfolder -tfvars*

![](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/6f758922-631a-4bad-841e-8766f10eb04a.png) [^3]

\

![06c3207a-6acc-4d61-a922-6ed806566f22.png|811](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/06c3207a-6acc-4d61-a922-6ed806566f22.png) [^4]

\

\

*Create separate folders for dev & prod environments*

![](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/9bd3b01b-d60b-4275-b465-d79bd3ccea84.png) [^5]

\

\

*Create different S3 buckets to maintain state for development, UAT, Testing, PROD.*

\

[***chilops-terraform-s3-dev***](https://us-east-1.console.aws.amazon.com/s3/buckets/chilops-terraform-s3-dev?region=us-east-1&bucketType=general)     *-- Bucket for development*

[***chilops-terraform-s3-prod***](https://us-east-1.console.aws.amazon.com/s3/buckets/chilops-terraform-s3-prod?region=us-east-1&bucketType=general)   *-- Bucket for production* 

\

![d4d3d323-a403-48ff-a9be-155622ebe84b.png|884.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/d4d3d323-a403-48ff-a9be-155622ebe84b.png) [^6]

\

*creating DynamoDB - table creation for locking*

\

\

![0c8a72af-b414-46c4-9304-828e66191571.png|712.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/0c8a72af-b414-46c4-9304-828e66191571.png) [^7]

\

[***chilops-locking-dev***](https://us-east-1.console.aws.amazon.com/dynamodbv2/home?region=us-east-1#table?name=chilops-locking-dev)     *-- locking table for Dev*

[***chilops-locking-prod***](https://us-east-1.console.aws.amazon.com/dynamodbv2/home?region=us-east-1#table?name=chilops-locking-prod)   *-- locking table for Prod* 

![83179178-1a34-4c3c-b341-7ceeb43e5020.png|845.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/83179178-1a34-4c3c-b341-7ceeb43e5020.png) [^8]

\

\

*Under Dev - backend.tf code*

```
bucket = "chilops-terraform-s3-dev"
key = "multienv"
region = "us-east-1"
dynamodb_table = "chilops-locking-dev"
```

\

*<mark style="background-color:#f8914d;">**IMP node: for every terraform project use different keyname "mulitenv" else it will merge... any name is fine**<!-- {"backgroundCycleColor":"24"} --></mark>*

![20925e84-fdc8-42a4-bf7d-fce01435286f.png|807](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/20925e84-fdc8-42a4-bf7d-fce01435286f.png) [^9]

\

*Under prod - backend.tf code*

\

```
bucket = "chilops-terraform-s3-prod"
key = "multienv"
region = "us-east-1"
dynamodb_table = "chilops-locking-prod"
```

  

![0ba574c0-109f-44e5-b05b-276274131514.png|801](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/0ba574c0-109f-44e5-b05b-276274131514.png) [^10]

\

*data.tf code*

![d452b6f9-7173-40db-af54-5a28051bbaf3.png|785](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/d452b6f9-7173-40db-af54-5a28051bbaf3.png) [^11]

\

*roboshop.tf code   -- In this code **startwith function** is used.*

![280317df-f9b8-44b4-a714-8b88c0fe907b.png|844](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/280317df-f9b8-44b4-a714-8b88c0fe907b.png) [^12]

\

*under dev - **dev.tfvars code***

```
instance_names = {
    mongodb-dev = "t3.small"
    redis-dev = "t2.micro"
    mysql-dev = "t3.small"
    web-dev = "t2.micro"

}
```

   

![64655ac9-0b37-4064-8c5c-cfb80eba8cff.png|788](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/64655ac9-0b37-4064-8c5c-cfb80eba8cff.png) [^13]

\

*under prod - **prod.tfvars code***

```
instance_names = {
    mongodb-prod = "t3.small"
    redis-prod = "t2.micro"
    mysql-prod = "t3.small"
    web-prod = "t2.micro"

}
```

![20bded51-826b-4397-acfd-c437ded6511f.png|785](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/20bded51-826b-4397-acfd-c437ded6511f.png) [^14]

\

*provider.tf code*

![08e21dcb-b023-423b-9715-1652852baf83.png|821.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/08e21dcb-b023-423b-9715-1652852baf83.png) [^15]

\

*variables.tf code*

![38bf8c41-28f1-4330-84d1-a2914583aec1.png|786](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/38bf8c41-28f1-4330-84d1-a2914583aec1.png) [^16]

```
terraform init -backend-config=dev/backend.tf
```

![810cb566-f9f6-418b-ad13-9951897899f2.png|790](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/810cb566-f9f6-418b-ad13-9951897899f2.png) [^17]

\

```
terraform plan -var-file=dev/dev.tfvars
```

\

![8d6309e0-1e1b-42ba-b232-0d8d9cfaa0d9.png|713](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/8d6309e0-1e1b-42ba-b232-0d8d9cfaa0d9.png) [^18]

![c3ad682f-48db-421c-945a-822ff444b9d4.png|708](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/c3ad682f-48db-421c-945a-822ff444b9d4.png) [^19]

\

\

***Dev** instances are created:*

![d6a8715f-da55-4ab5-87a6-765d36d5f9d9.png|797.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/d6a8715f-da55-4ab5-87a6-765d36d5f9d9.png) [^20]

\

\

\

![2be26fb9-48a6-48c5-a1f8-bd9c89dc116e.png|995.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/2be26fb9-48a6-48c5-a1f8-bd9c89dc116e.png) [^21]

\

*Now doing same in **PROD** environment: " -reconfigure needs to be used when we start doing in other environments like PROD, UAT etc*

\

*<mark style="background-color:#f8d616;">I**MP: we are switching to different envronments from dev to prod or prod to UAT then every time we need to reinitialize using **<!-- {"backgroundCycleColor":"25"} --></mark><mark style="background-color:#f8914d;">**-reconfigure**<!-- {"backgroundCycleColor":"24"} --></mark>*

```
terraform init -reconfigure -backend-config=prod/backend.tf
```

![5503fb29-b567-4d17-a47d-aa7ef2fe14aa.png|773](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/5503fb29-b567-4d17-a47d-aa7ef2fe14aa.png) [^22]

\

```
terraform plan -var-file=prod/prod.tfvars
```

![b103c855-8656-4632-acfc-698daaf866c6.png|784](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/b103c855-8656-4632-acfc-698daaf866c6.png) [^23]

![eb79f870-c065-4e2d-bb23-7e99ab8911d1.png|782](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/eb79f870-c065-4e2d-bb23-7e99ab8911d1.png) [^24]

\

```
terraform apply -var-file=prod/prod.tfvars
```

![77cedda5-52b7-488f-83db-37ba7a11a9c9.png|704](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/77cedda5-52b7-488f-83db-37ba7a11a9c9.png) [^25]

\

\

*Now PROD instances launched & running*

\

![b098b909-6bd9-43c5-9cf9-92ce69687034.png|872.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/b098b909-6bd9-43c5-9cf9-92ce69687034.png)

\

*To destroy DEV & PROD env*

*<mark style="background-color:#f8d616;">I**MP: we are switching to different envronments from dev to prod or prod to UAT then every time we need to reinitialize using **<!-- {"backgroundCycleColor":"25"} --></mark><mark style="background-color:#f8914d;">**-reconfigure**<!-- {"backgroundCycleColor":"24"} --></mark>*

```
terraform destroy -var-file=prod/prod.tfvars
terraform init -reconfigure -backend-config=dev/backend.tf
terraform destroy -var-file=dev/dev.tfvars
```

![](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/47e64a45-8032-4fc5-bee3-31c7f0e568db.png)

\

*E:\\AWSDevOps\\Repos\\terraform-multi-env\\tfvars\\.terraform\\providers\\registry.terraform.io\\hashicorp\\aws\\5.31.0\\windows_amd64\\terraform-provider-aws_v5.31.0_x5.exe*

\

**pros** --  Same code

**cons** -- Same code for multiple env, you need to be very careful because whatever changes you do that will apply to prod

\

# *<mark style="background-color:#f8914d;">**workspaces**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

Terraform workspace is to manage multiple deployments/environments with same code.

It only supports few backends only(S3 bucket is one if it)

![e503861f-7533-4b89-914a-c927594c813a.png|584](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/e503861f-7533-4b89-914a-c927594c813a.png) [^26]

\

```
terraform workspace
```

![2b226e0f-bb16-4e43-92bc-eb837b4ff354.png|574](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/2b226e0f-bb16-4e43-92bc-eb837b4ff354.png) [^27]

\

Create workspace folder and ec2.tf code

lookup(function) - we use this function in a map we pass a key to bring the value

![8ecb2d96-edda-4cf0-a084-8a806605b2f5.png|536](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/8ecb2d96-edda-4cf0-a084-8a806605b2f5.png) [^28]

![46decd07-19de-41c1-913c-fa12386b10d1.png|840](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/46decd07-19de-41c1-913c-fa12386b10d1.png) [^29]

\

provider.tf code -- **chilops-terraform-remotestate** is S3 bucket name( DynamoDB file table also created) Also change the key name(any new name is fine)

![c1126449-7c56-4900-8148-8b3dc3019a7a.png|842.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/c1126449-7c56-4900-8148-8b3dc3019a7a.png) [^30]

\

variable.tf code

![4755cf75-ed74-4b98-b330-bc62f7be7271.png|847](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/4755cf75-ed74-4b98-b330-bc62f7be7271.png) [^31]

\

Now we need to create workspace:

```
cd workspaces
```

```
terraform init
```

![](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/c76c781a-a4c1-4702-bdb6-509033fab5f0.png) [^32]

```
terraform workspace list
terraform workspace new dev
  
terraform plan
```

![b16d2c0f-9e17-4107-bc87-72134727df25.png|655](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/b16d2c0f-9e17-4107-bc87-72134727df25.png) [^33]

![4c95e6d4-b223-4688-b805-a529fad9e333.png|797](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/4c95e6d4-b223-4688-b805-a529fad9e333.png) [^34]

\

under S3 bucket dev workspace created:

![d19d5ca4-67a6-4081-8ec2-7022eebb0f78.png|933.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/d19d5ca4-67a6-4081-8ec2-7022eebb0f78.png) [^35]

\

```
terraform workspace new prod
```

![b6da1035-9d65-4386-91c4-a0115229b1eb.png|839](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/b6da1035-9d65-4386-91c4-a0115229b1eb.png) [^36]

\

Now two different workspaces created - One for DEV, One for PROD

![b563d9fe-4b08-425b-88f9-e7908ea35549.png|838.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/b563d9fe-4b08-425b-88f9-e7908ea35549.png) [^37]

\

To check in which workspace we are currently working

```
terraform workspace show
```

![e44839d7-d48b-434c-9c72-f10ae3909cbb.png|687](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/e44839d7-d48b-434c-9c72-f10ae3909cbb.png) [^38]

\

To see how many workspaces are present.

```
terraform workspace list
```

![a8874172-a11b-4529-a465-42700331549f.png|689](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/a8874172-a11b-4529-a465-42700331549f.png) [^39]

\

since we are in prod env. then it should select t3.small instance

```
terraform plan
```

![75148254-9086-4ef1-9ba3-36bffb258876.png|760](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/75148254-9086-4ef1-9ba3-36bffb258876.png) [^40]

\

Now to move to DEV workspace:

```
terraform workspace select dev
```

![e81f6db1-8fac-4c59-a3c2-33f2bf6b304d.png|736](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/e81f6db1-8fac-4c59-a3c2-33f2bf6b304d.png) [^41]

\

Now it will show t2.micro instance

```
terraform plan
```

![16bebd80-6826-46f8-b5e5-7c0d50b9ea17.png|723](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/16bebd80-6826-46f8-b5e5-7c0d50b9ea17.png) [^42]

\

**pros** --   Same code

**cons** --  Same code for multiple env, you need to be very careful because whatever changes you do that will apply to prod.

Also, Terraform is maintaining same bucket that may cause errors and difficult to maintain, difficult to maintain variables.

\

**Note: so compared to workspaces & tfvars... better one is tfvars.**

\

# *<mark style="background-color:#f8914d;">**Different Repos completely**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

**pros** -- Since everything diff, you no need to worry

**cons** -- Code duplication, you need to maintain 2 repos

\

<mark style="background-color:#f8d616;">Note: if it crucial/big enterprise project then different Repos is the right approach compared to other two, since will have crystal clear separation prod code separate & dev code separate.<!-- {"backgroundCycleColor":"25"} --></mark>

\

\

# <mark style="background-color:#f8914d;">**provisioners**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Two types of provisioners

1. Local-exec  -- It's where you running the terraform command (its my current laptop)<!-- {"indent":1} -->

    1. remote-exec  -- This will run inside the server.

Provisioners is only for EC2 instances

\

\

# <mark style="background-color:#f8914d;">**Local-exec**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

Local-exec - It's where you running the terraform command (its my current laptop or server)

\

ec2.tf code under new folder

![bd45f0a5-12e5-4444-8ac8-88e5f46df3bc.png|925.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/bd45f0a5-12e5-4444-8ac8-88e5f46df3bc.png) [^43]

\

provider.tf code

![ea22d187-9f19-4b7d-b49f-97bb849244f1.png|925.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/ea22d187-9f19-4b7d-b49f-97bb849244f1.png) [^44]

\

```
cd terraform-provisioners/
terraform init
```

![fba42f65-430d-4715-88f3-0c1269f8820a.png|725](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/fba42f65-430d-4715-88f3-0c1269f8820a.png) [^45]

\

Creating an instance and printing the <mark style="background-color:#f8d616;">**private-ip**<!-- {"backgroundCycleColor":"25"} --></mark>

```
terraform apply -auto-approve
```

![514c8d12-3195-40a1-960e-2569facffd4b.png|721](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/514c8d12-3195-40a1-960e-2569facffd4b.png) [^46]

![ed0c256e-9d5e-4b1d-b7b4-50b70aa75775.png|815](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/ed0c256e-9d5e-4b1d-b7b4-50b70aa75775.png) [^47]

```
terraform destroy -auto-approve
```

![56447c6f-6601-4b71-9a03-4a980fe8756a.png|951](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/56447c6f-6601-4b71-9a03-4a980fe8756a.png) [^48]

\

<mark style="background-color:#f3de6c;">Note: Provisioners are useful to integrate terraform with configuration management tools like ansible<!-- {"backgroundCycleColor":"14"} --></mark>

server creation is nothing but infrastructure creation... TERRAFORM

server configuration is nothing but configuration management.. ANSIBLE

\

<mark style="background-color:#f3de6c;">Note: If we can integrate terraform & ansible then its a end to end automation. we can integrate using provisioners.<!-- {"backgroundCycleColor":"14"} --></mark>

\

**creation time** --  This local exec will run when server is created

**destroy time** -- At the time of destroy

\

This can be useful to send an email when server is created or destroyed.

\

ec2.tf updated code to check when creation & destroyed.

![c5f24916-437f-497b-8d09-16537ec8ed10.png|900.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/c5f24916-437f-497b-8d09-16537ec8ed10.png) [^49]

\

server created, but ansible-play book command failed due to we are running locally and ansible play book is not installed.

```
terraform apply -auto-approve
```

![8d4f09bb-26c4-44a7-90df-dd135b88e5e9.png|896](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/8d4f09bb-26c4-44a7-90df-dd135b88e5e9.png) [^50]

\

\

```
terraform destroy -auto-approve
```

![9dc1a38e-a971-4a0d-9ece-11ffc254f871.png|897.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/9dc1a38e-a971-4a0d-9ece-11ffc254f871.png) [^51]

---

# <mark style="background-color:#f8914d;">**remote-exec**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

remote-exec  -- This will run inside the server.

\

1\. first you should connect to server

2\. then you can run anything inside the server

\

ec2.tf updated code

![c18a4f84-e15f-4dbc-861f-0b8cec66621e.png|997.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/c18a4f84-e15f-4dbc-861f-0b8cec66621e.png) [^52]

![39af6aec-4b0a-42e1-87f6-e7dbd3baa453.png|479](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/39af6aec-4b0a-42e1-87f6-e7dbd3baa453.png) [^53]

\

Now here it will directly connect to server and **install NGINX software and start the services**

```
terraform apply -auto-approve
```

![7c09365d-5cba-40e0-95dc-99c210ffead8.png|715](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/7c09365d-5cba-40e0-95dc-99c210ffead8.png) [^54]

\

nginx is working on server:

![f5e856d1-2f93-4db8-a6c5-58240661f495.png|994.3333740234375](https://images.amplenote.com/d85dab74-1404-11ef-a737-9a665e06d35f/f5e856d1-2f93-4db8-a6c5-58240661f495.png) [^55]

\

```
terraform destroy -auto-approve
```

[^1]: G
    https://github.com/new
    =
    New repository
    Q Type to search
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    environment
    environmental
    chilops
    terraform-multi-env
    terraform-multi-env is available.
    Great repository names are short and memorable. Need inspiration? How about congenial-octo-fortnight ?
    Description (optional)
    O
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    Private
    You choose who can see and commit to this repository.

[^2]: V
    REPOS
    Li Li O @ Concepts > ! person.yaml
    > Ansible
    -
    name: sivakumar
    Concepts
    N
    dob: "2023-09-09"
    3
    Ansible.MD
    M
    address :
    4
    address-line1: vivek street
    image-1.png
    5
    address-line2: sanath nagar
    image.png
    6
    city : HYD
    {} person.json
    M
    email: info@joindevops . com
    person.xml
    18
    ! person.yaml
    9
    -
    name: ramesh
    notes
    10
    dob: "2022-09-08"
    11
    address :
    > Robosho-shellscripts
    M
    12
    -
    address-line1: vivek street1
    > roboshop-ansible
    13
    address-line2: sanath nagar1
    > roboshop-ansible-roles
    14
    city : HYD1
    > shellscripts
    15
    address-line1: vivek street2
    > terraform
    16
    address-line2: sanath nagar2
    terraform-multi-env
    17
    city : HYD2
    18
    email: info@joindevops . com

[^3]: > terraform-multi-env \\ tfvars

[^4]: mongodb-dev, redis-dev
    mongodb-dev . daws 76s . online
    same code but different configuration

[^5]: v terraform-multi-env \\ tfvars
    > dev
    > prod
    data.tf
    provider.tf
    CC CC
    roboshop.tf
    variables.tf

[^6]: General purpose buckets
    Directory buckets
    General purpose buckets (3) Info
    ALL AWS Regions
    C
    Copy ARN
    Empty
    Delete
    Create bucket
    Buckets are containers for data stored in $3.
    Find buckets by name
    <
    1
    Name
    AWS Region
    IAM Access Analyzer
    Creation date
    D
    O
    chilops-terraform-remotestate
    US East (N. Virginia) us-east-1
    View analyzer for us-east-1
    May 16, 2024, 13:03:47 (UTC+05:30)
    O
    chilops-terraform-s3-dev
    US East (N. Virginia) us-east-1
    View analyzer for us-east-1
    May 17, 2024, 10:35:59 (UTC+05:30)
    O
    chilops-terraform-s3-prod
    US East (N. Virginia) us-east-1
    View analyzer for us-east-1
    May 17, 2024, 10:33:29 (UTC+05:30)

[^7]: DynamoDB > Tables > Create table
    Create table
    Table details Info
    DynamoDB is a schemaless database that requires only a table name and a primary key when you create the table.
    Table name
    This will be used to identify your table.
    chilops-locking-dev
    Between 3 and 255 characters, containing only letters, numbers, underscores (_), hyphens (-), and periods (.).
    Partition key
    The partition key is part of the table's primary key. It is a hash value that is used to retrieve items from your table and allocate data across
    hosts for scalability and availability.
    LockID
    String
    1 to 255 characters and case sensitive.
    Sort key - optional
    You can use a sort key as the second part of a table's primary key. The sort key allows you to sort or search among all items sharing the
    same partition key.
    Enter the sort key name
    String
    1 to 255 characters and case sensitive.

[^8]: DynamoDB > Tables
    Tables (3) Info
    C
    Actions
    Delete
    Create table
    Q Find tables by table name
    Any tag key
    Any tag value
    <
    1
    O
    Name
    Status
    Partition key
    Sort key
    Indexes
    Deletion protection
    Read capacity mode
    Write capacity
    O
    chilops-locking
    Active
    LockID (S)
    0
    Off
    Provisioned (1)
    Provisioned (1)
    O
    chilops-locking-dev
    Active
    LockID (S)
    0
    Off
    Provisioned (5)
    Provisioned (5)
    0
    chilops-locking-prod - Active
    LockID (S)
    0
    Off
    Provisioned (5)
    Provisioned (5)

[^9]: V
    REPOS
    terraform-multi-env > tfvars > dev > backend.tf > ...
    > Ansible
    1
    bucket = "chilops-terraform-s3-dev"
    Concepts
    2
    key = "mutlienv"
    3
    Ansible.MD
    region = "us-east-1"
    M
    4
    dynamodb_table = "chilops-locking-dev"
    image-1.png
    5
    image.png
    {} person.json
    M
    person.xml
    ! person.yaml
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-multi-env \\ tivars
    > .terraform
    dev
    backend.tf
    -
    4. U

[^10]: REPOS
    terraform-multi-env > tfvars > prod > backend.tf > . bucket
    > Ansible
    1
    bucket = "chilops-terraform-s3-prod"
    Concepts
    2
    key = "multienv"
    3
    Ansible.MD
    region = "us-east-1"
    M
    4
    dynamodb_table = "chilops-locking-prod"
    image-1.png
    15
    image.png
    16
    {} person.json
    M
    person.xml
    ! person.yaml
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    terraform-multi-env \\ tivars
    > .terraform
    dev
    backend.tf
    4, U
    dev.tfvars
    U
    v prod
    O
    backend.tf
    4. U

[^11]: terraform-multi-env > tivars > data.tf > { data "aws_vpc" "default"
    1
    data "aws_ami" "centos8"{
    2
    owners = \["973714476881"\]
    3
    most_recent
    = true
    4
    5
    filter {
    6
    name
    "name"
    7
    values = \["Centos-8-Devops-Practice"\]
    8
    9
    10
    filter {
    11
    name
    = "root-device-type"
    12
    values = \["ebs"\]
    13
    14
    15
    filter {
    16
    name
    "virtualization-type"
    17
    values = \["hvm" \]
    18
    19
    20
    21
    data "aws_ami" "aws-linux-2"{
    22
    owners = \["amazon" \]
    23
    most_recent
    = true
    24
    25
    filter {
    26
    name
    = "name"
    27
    values = \["amzn2-ami-kernel-5 . 10-hvm-\*"\]
    28
    29
    30
    filter {
    31
    name
    "root-device-type"
    32
    values = \["ebs"\]
    33
    34
    35
    filter {
    36
    name
    = "virtualization-type"
    37
    values = \["hvm" \]
    38
    LP
    39
    40
    41
    42
    data "aws_vpc" "default" {
    43
    default = true
    44

[^12]: REPOS
    terraform-multi-env > tfvars > roboshop.f > % resource "aws_route53_record" "www" > \[ \] records > \[e\] 0
    > Ansible
    1
    resource "aws_instance" "web" {
    Concepts
    2
    for_each = var . instance_names
    3
    Ansible.MD
    ami
    M
    = data . aws_ami . centos8. id
    instance_type = each . value
    image-1.png
    15
    tags = {
    image.png
    6
    Name = each . key
    {} person.json
    M
    7
    }
    person.xml
    8
    ! person.yaml
    19
    10
    > notes
    11
    > Robosho-shellscripts
    resource "aws_route53_record" "www" {
    M
    12
    for_each = aws_instance . web
    > roboshop-ansible
    13
    zone_id = var . zone_id
    > roboshop-ansible-roles
    14
    name
    = "${each . key} . ${var . domain_name}" #interpolation
    > shellscripts
    15
    type
    = "A"
    > terraform
    16
    tt1
    = 1
    v terraform-multi-env \\ tivars
    17
    records = \[startswith(each. key, "web") ? each . value. public_ip : each. value . private_ip \]
    18
    dev
    19
    backend.tf
    2, U
    20
    # output "instances_info" {
    dev.tfvars
    U
    21
    #
    value = aws_instance . web
    prod
    22
    #
    backend.tf
    2, U
    prod.tfvars
    U

[^13]: > Ansible
    instance_names = {
    Concepts
    2
    mongodb-dev = "t3. small"
    3
    Ansible.MD
    M
    redis-dev = "t2.micro"
    4
    mysql-dev = "t3. small"
    image-1.png
    15
    web-dev = "t2.micro"
    image.png
    16
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-multi-env \\ tivars
    dev
    backend.tf
    2, U
    dev.tfvars
    U

[^14]: REPOS
    terraform-multi-env > tfvars > prod > prod.tfvars > do instance_names
    > Ansible
    1
    instance_names = {
    Concepts
    2
    mongodb-prod = "t3. small"
    3
    Ansible.MD
    M
    redis-prod = "t2.micro"
    4
    mysql-prod = "t3. small"
    image-1.png
    5
    web-prod = "t2.micro"
    image.png
    6
    {} person.json
    M
    person.xml
    ! person.yaml
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-multi-env \\ tivars
    dev
    backend.tf
    2, U
    dev.tfvars
    U
    prod
    backend.tf
    2, U
    prod.tfvars
    U

[^15]: REPOS
    terraform-multi-env > tivars > provider.tf > > provider "aws"
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
    15
    version = "5.31.0" # AWS provider version, not terraform version
    image.png
    16
    {} person.json
    M
    7
    person.xml
    18
    ! person.yaml
    19
    backend "s3" {
    notes
    10
    #
    bucket = "chilops-terraform-remotestate"
    11
    #
    > Robosho-shellscripts
    key
    = "dynamic"
    M
    12
    #
    region = "us-east-1"
    > roboshop-ansible
    13
    dynamodb_table = "chilops-locking"
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    v terraform-multi-env \\ tivars
    17
    provider "aws" {
    18
    > .terraform
    region = "us-east-1"
    19
    dev
    backend.tf
    4. U
    dev.tfvars
    U
    prod
    O
    backend.tf
    4, U
    prod.tfvars
    U
    E .terraform.lock.hcl
    U
    data.tf
    U
    provider.tf
    U

[^16]: EXPLORER
    . . .
    provider.tf .\\tfvars U
    provider.tf .. \\dynamic
    roboshop.tf U .
    REPOS
    terraform-multi-env > tivars > variables.tf > % variable "domain_name"
    > Ansible
    1
    variable "instance_names" {
    N
    Concepts
    type = map
    3
    Ansible.MD
    #
    M
    default = {
    mongodb = "t3. small"
    image-1.png
    15
    #
    redis = "t2.micro"
    image.png
    6
    mysql = "t3. small"
    {} person.json
    M
    7
    #
    person.xml
    8
    ! person.yaml
    9
    > notes
    10
    O
    variable "zone_id" {
    11
    default = "Z06431971951XUVZELNIC"
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    variable "domain_name" {
    > shellscripts
    15
    default = "chowdarychilukuri. in"
    > terraform
    16
    }
    v terraform-multi-env \\ tivars
    > .terraform
    dev
    backend.tf
    4. U
    dev.tfvars
    U
    prod
    backend.tf
    4. U
    prod.tfvars
    U
    E .terraform.lock.hcl
    U
    data.tf
    U
    provider.tf
    U
    roboshop.tf
    U
    variables.tf
    U

[^17]: chowd@chowdary MINGW64 /e/awsdevops /Repos/terraform-multi-env/tfvars (main)
    $ terraform init -backend-config=dev/backend. tf
    Initializing the backend. . .
    Initializing provider plugins . . .
    Finding hashicorp/aws versions matching "5. 31.0"...
    Installing hashicorp/aws v5 . 31.0. . .
    Installed hashicorp/aws v5. 31.0 (signed by Hashicorp)
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
    chowd@chowdary MINGW64 /e/awsdevops /Repos/terraform-multi-env/tfvars (main)
    $

[^18]: chowd@chowdary MINGW64 /e/awsdevops /Repos/terraform-multi-env/tfvars (main)
    $ terraform plan -var-file=dev/dev . tfvars
    Acquiring state lock. This may take a few moments . . .
    data . aws_vpc . default: Reading. . .
    data . aws_ami . centos8: Reading. . .
    data . aws_ami . aws-linux-2: Reading. . .
    data . aws_ami . centos8: Read complete after 1s \[id=ami-Of3c7d07486cad139\]
    data . aws_ami . aws-linux-2: Read complete after 1s \[id=ami-04ff98ccbfa41c9ad\]
    data . aws_vpc . default: Read complete after 2s \[id=vpc-0817cae8968304c06\]
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions :
    # aws_instance . web \["mongodb-dev"\] will be created
    +
    resource "aws_instance" "web" {
    +
    ami
    = "ami -Of 3c7 d07486cad139"
    +
    arn
    (known after apply)
    +
    associate_public_ip_address
    E
    (known after apply)
    +
    availability_zone
    = (known after apply)
    cpu_core_count
    (known after apply)
    +
    cpu_threads_per_core
    E
    (known after apply)

[^19]: #
    aws_route53_record . www\["web-dev"\] will be created
    +
    resource "aws_route53_record" "www" {
    +
    allow_overwrite = (known after apply)
    +
    fadn
    : (known after apply)
    +
    id
    E
    (known after apply)
    +
    name
    "web-dev . chowdarychi lukuri . in"
    +
    records
    (known after apply)
    +
    tt1
    =1
    +
    type
    "A"
    +
    zone_id
    "Z06431971951XUVZELNIC"
    Plan: 8 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock. This may take a few moments. . .
    chowd@chowdary MINGW64 /e/awsdevops /Repos /terraform-multi-env/tfvars (main)

[^20]: aws
    Services
    Q Search
    \[Alt+S\]
    4
    ?
    N. Virginia v
    chowdary
    DEC2
    Route 53
    IAM
    VPC
    $3
    DynamoDB
    Instances (4) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    EC2 Dashboard
    X
    EC2 Global View
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Events
    Instance state = running \|X
    Clear filters
    < 1 >
    Console-to-Code Preview
    O
    Name _
    A
    Instance ID
    Instance state
    A
    Instance type
    4
    Status check
    Alarm status
    Availability Zo
    Instances
    0
    web-dev
    i-0ad4355100d383cb9
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    Instances
    0
    redis-dev
    i-08db 7ae3afd15cf3f
    Running
    t2.micro
    Initializing
    View alarms +
    us-east-1d
    Instance Types
    0
    mysql-dev
    i-05a565586b3781a29
    Running
    t3.small
    Initializing
    View alarms +
    us-east- 1a
    Launch Templates
    mongodb-dev
    i-0c31bcd2e6265b488
    Running
    t3.small
    Initializing
    View alarms +
    us-east-1a
    Spot Requests

[^21]: EC2
    Route 53
    8: IAM
    VPC
    S3
    DynamoDB
    Amazon S3
    X
    Amazon S3 > Buckets > chilops-terraform-s3-dev
    Buckets
    chilops-terraform-s3-dev info
    Access Grants
    Access Points
    Objects
    Properties
    Permissions
    Metrics
    Management
    Access Points
    Object Lambda Access Points
    Multi-Region Access Points
    Batch Operations
    Objects (1) Info
    IAM Access Analyzer for $3
    C
    Copy S3 URI
    Copy URL
    Download
    Open \[
    Delete
    Actions
    Create folder
    Upload
    Objects are the fundamental entities stored in Amazon $3. You can use Amazon S3 inventory \[ to get a list of all objects in your bucket. For others to access your objects, you'll need to
    explicitly grant them permissions. Learn more \[Z
    Block Public Access settings for
    this account
    Q Find objects by prefix
    <
    1
    7Storage Lens
    Name
    Type
    Last modified
    4
    Size
    4
    Storage class
    Dashboards
    D mutlienv
    May 17, 2024, 11:49:36
    20.7 KB
    Standard
    Storage Lens groups
    (UTC+05:30)
    AWS Organizations settings

[^22]: chowd@chowdary MINGW64 /e/awsdevops/Repos /terraform-multi-env/tfvars (main)
    $ terraform init -reconfigure -backend-config=prod/backend. tf
    Initializing the backend. ..
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing provider plugins. . .
    Reusing previous version of hashicorp/aws from the dependency lock file
    Using previously-installed hashicorp/aws v5 . 31.0
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. Al1 Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.

[^23]: chowd@chowdary MINGW64 /e/awsdevops /Repos/terraform-multi-env/tfvars (main)
    $ terraform plan -var-file=prod/prod. tfvars
    Acquiring state lock. This may take a few moments. . .
    data . aws_vpc . default: Reading. . .
    data . aws_ami . centos8: Reading. . .
    data . aws_ami . aws-linux-2: Reading. . .
    data . aws_ami . centos8: Read complete after 2s \[id=ami-Of3c7d07486cad139\]
    data. aws_ami . aws -linux-2: Read complete after 2s \[id=ami-04ff98ccbfa41c9ad\]
    data . aws_vpc . default: Read complete after 3s \[id=vpc-0817cae8968304c06\]
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols:
    +
    create
    Terraform will perform the following actions :
    # aws_instance . web \["mongodb-prod"\] will be created
    +
    resource "aws_instance" "web"

[^24]: Plan: 8 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock. This may take a few moments. . .
    chowd@chowdary MINGW64 /e/awsdevops /Repos /terraform-multi-env/tfvars (main)

[^25]: $ terraform apply -var-file=prod/prod. tfvars
    Acquiring state lock. This may take a few moments . . .
    data . aws_vpc . default: Reading. . .
    data . aws_ami . aws-linux-2: Reading. . .
    data . aws_ami . centos8: Reading. . .
    data . aws_ami . centos8: Read complete after 1s \[id=ami-Of3c7d07486cad139\]
    data . aws_ami . aws-linux-2: Read complete after 1s \[id=ami-04ff98ccbfa41c9ad\]
    data . aws_vpc . default: Read complete after 2s \[id=vpc-0817cae8968304c06\]
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols :
    +
    create
    Terraform will perform the following actions:
    # aws_instance . web \["mongodb-prod"\] will be created
    +
    resource "aws_instance" "web"
    {
    +
    ami
    "ami-Of 3c7 d07486cad139"
    +
    arn
    (known after apply)
    +
    associate_public_ip_address
    =
    (known after apply)
    +
    availability_zone
    (known after apply)
    +
    cpu_core_count
    (known after apply)
    +
    cpu_threads_per_core
    E
    (known after apply)

[^26]: workspaces
    terraform. workspace --> dev
    terraform. workspace --> prod

[^27]: PS E: \\AWSDevOps \\Repos \\terraform-multi-env> terraform workspace
    Usage: terraform \[global options\] workspace
    new, list, show, select and delete Terraform workspaces.
    Subcommands :
    delete
    Delete a workspace
    list
    List Workspaces
    new
    Create a new workspace
    select
    Select a workspace
    show
    Show the name of the current workspace
    PS E: \\AWSDevops \\Repos \\terraform-multi-env>

[^28]: lookup Function
    lookup retrieves the value of a single element from a map, given its key.
    If the given key does not exist, the given default value is returned instead.
    lookup (map, key, default)
    Copy

[^29]: REPOS
    terraform-multi-env > workspaces > ec2.tf > $ resource "aws_instance" "web"
    > Ansible
    1
    resource "aws_instance" "web" {
    Concepts
    2
    ami
    = "ami -Of3c7d07486cad139" #devops-practice
    3
    Ansible.MD
    M
    instance_type = lookup (var . instance_type, terraform. workspace)
    4
    image-1.png
    5
    tags = {
    image.png
    6
    Name = "HelloTerraform"
    {} person.json
    M
    7
    }
    person.xml
    8
    ! person.yaml
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-multi-env
    > tfvars
    workspaces
    data.tf
    C
    ec2.tf
    C
    provider.tf
    C
    variables.tf
    C
    .gitignore

[^30]: REPOS
    terraform-multi-env > workspaces > provider.tf > { terraform > $ backend "s3" > \[. key
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
    version = "5.31.0" # AWS provider version, not terraform version
    image.png
    6
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    19
    backend "s3" {
    10
    notes
    bucket = "chilops-terraform-remotestate"
    11
    > Robosho-shellscripts
    key
    = "workspace"
    M
    12
    region = "us-east-1"
    > roboshop-ansible
    13
    dynamodb_table = "chilops-locking"
    > roboshop-ansible-roles
    14
    }
    > shellscripts
    15
    > terraform
    16
    v terraform-multi-env
    17
    provider "aws" {
    18
    > tfvars
    region = "us-east-1"
    19
    workspaces
    data.tf
    U
    ec2.tf
    U
    provider.tf
    U
    variables.tf
    U
    .gitignore

[^31]: V REPOS
    terraform-multi-env > workspaces > variables.tf > @ variable "instance_type"
    > Ansible
    1
    variable "instance_type" {
    Concepts
    2
    default = {
    3
    Ansible.MD
    dev = "t2.micro"
    M
    4
    prod = "t3. small"
    image-1.png
    15
    image.png
    6
    {} person.json
    M
    person.xml
    ! person.yaml
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    v terraform-multi-env
    > tfvars
    workspaces
    data.tf
    ec2.tf
    C CC
    provider.tf
    variables.tf
    U
    .gitignore

[^32]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos/terraform-multi-env/workspaces (main)
    $ terraform init
    Initializing the backend. ..
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing provider plugins. . .
    Finding hashicorp/aws versions matching "5. 31.0"...
    Installing hashicorp/aws v5 . 31.0. .
    Installed hashicorp/aws v5. 31.0 (signed by Hashicorp)
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
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos/terraform-multi-env/workspaces (main)

[^33]: chowd@chowdary MINGW64 /e/AWSDevops /Repos/terraform-multi-env/workspaces (main)
    $ terraform workspace list
    \*
    default

[^34]: chowd@chowdary MINGW64 /e/AWSDevops /Repos/terraform-multi-env/workspaces (main)
    $ terraform workspace new dev
    Created and switched to workspace "dev"!
    You're now on a new, empty workspace. Workspaces isolate their state,
    so if you run "terraform plan" Terraform will not see any existing state
    for this configuration.
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos /terraform-multi-env/workspaces (main)
    $

[^35]: Amazon S3 > Buckets > chilops-terraform-remotestate >
    env:/ > dev/ > workspace
    workspace Info
    Copy S3 URI
    Download
    Open \[
    Object actions
    Properties
    Permissions
    Versions
    Object overview
    Owner
    S3 URI
    chilukuridevops
    $3://chilops-terraform-remotestate/env:/dev/workspace
    AWS Region
    Amazon Resource Name (ARN)
    US East (N. Virginia) us-east-1
    7 arn:aws:$3::chilops-terraform-remotestate/env:/dev/workspace
    Last modified
    May 18, 2024, 10:31:21 (UTC+05:30)
    Entity tag (Etag)
    793ba20df1281d3669416229068469bf2
    Size
    180.0 B
    Object URL
    Type
    (https://chilops-terraform-remotestate.s3.amazonaws.com/env%3A/dev/w
    orkspace
    Key
    env:/dev/workspace
    Object management overview
    The following bucket properties and object management configurations impact the behavior of this object.

[^36]: chowd@chowdary MINGW64 /e/AWSDevops /Repos /terraform-multi-env/workspaces (main)
    $ terraform workspace new prod
    Created and switched to workspace "prod"!
    You're now on a new, empty workspace. Workspaces isolate their state,
    so if you run "terraform plan" Terraform will not see any existing state
    for this configuration.
    chowd@chowdary MINGW64 /e/AWSDevops /Repos /terraform-multi-env/workspaces (main)
    $

[^37]: Amazon S3 > Buckets > chilops-terraform-remotestate > env:/
    env:/
    Copy $3 URI
    Objects
    Properties
    Objects (2) Info
    C
    Copy S3 URI
    Copy URL
    Download
    Open \[
    Delete
    Actions
    Create folder
    Upload
    Objects are the fundamental entities stored in Amazon $3. You can use Amazon S3 inventory \[ to get a list of all objects in your bucket. For others to access your objects, you'll need to
    explicitly grant them permissions. Learn more
    Find objects by prefix
    1
    O
    Name
    Type
    4
    Last modified
    4
    Size
    Storage class
    O
    dev/
    Folder
    \[ prod/
    Folder

[^38]: chowd@chowdary MINGW64 /e/AWSDevops/Repos/terraform-multi-env/workspaces (main)
    $ terraform workspace show
    prod
    chowd@chowdary MINGW64 /e/AWSDevops/Repos/terraform-multi-env/workspaces (main)
    $

[^39]: chowd@chowdary MINGW64 /e/AWSDevops/Repos/terraform-multi-env/workspaces (main)
    $ terraform workspace list
    default
    dev
    prod

[^40]: Terraform will perform the following actions:
    # aws_instance.web will be created
    +
    resource "aws_instance" "web" {
    ami
    =
    "ami -Of 3c7 d07486cad139"
    arn
    (known after apply)
    +
    associate_public_ip_address
    E
    (known after apply)
    availability_zone
    E
    (known after apply)
    cpu_core_count
    (known after apply)
    cpu_threads_per_core
    (known after apply)
    disable_api_stop
    (known after apply)
    disable_api_termination
    (known after apply)
    ebs_optimized
    (known after apply)
    get_password_data
    false
    host_id
    = (known after apply)
    +
    host_resource_group_arn
    (known after apply)
    +
    i am_instance_profile
    (known after apply)
    +
    id
    =
    (known after apply)
    +
    instance_initiated_shutdown_behavior
    II
    (known after apply)
    instance_lifecycle
    E
    (known after apply)
    instance_state
    E
    (known after apply)
    instance_type
    "t3. small"
    +
    ipv6_address_count
    (known after apply)
    +
    ipv6_addresses
    E
    (known after apply)
    +
    key_name
    E
    (known after apply)
    +
    monitoring
    E
    (known after apply)

[^41]: chowd@chowdary MINGW64 /e/AWSDevops /Repos/terraform-multi-env/workspaces (main)
    $ terraform workspace select dev
    Switched to workspace "dev".
    chowd@chowdary MINGW64 /e/AWSDevops /Repos/terraform-multi-env/workspaces (main)
    $

[^42]: Terraform will perform the following actions :
    # aws_instance. web will be created
    +
    resource "aws_instance" "web" {
    ami
    =
    "ami-Of 3c7d07486cad139"
    +
    arn
    = (known after apply)
    associate_public_ip_address
    (known after apply)
    availability_zone
    (known after apply)
    +
    cpu_core_count
    E
    (known after apply)
    cpu_threads_per_core
    E
    (known after apply)
    +
    disable_api_stop
    = (known after apply)
    disable_api_termination
    (known after apply)
    ebs_optimized
    (known after apply)
    +
    get_password_data
    = false
    host_id
    = (known after apply)
    host_resource_group_arn
    = (known after apply)
    +
    i am_instance_profile
    (known after apply)
    +
    id
    (known after apply)
    +
    instance_initiated_shutdown_behavior
    =
    (known after apply)
    +
    instance_lifecycle
    E
    (known after apply)
    +
    instance_state
    (known after apply)
    +
    instance_type
    E
    "t2. micro"
    ipv6_address_count
    (known after apply)
    +
    ipv6_addresses
    E
    (known after apply)
    +
    key_name
    (known after apply)
    monitoring
    (known after apply)

[^43]: V REPOS
    terraform-provisioners > ec2.tf > 4 resource "aws_instance" "web" > 4: provisioner "local-exec" > \[\] command
    > Ansible
    1
    resource "aws_instance" "web" {
    Concepts
    2
    ami
    = "ami -Of3c7d07486cad139" #devops-practice
    3
    Ansible.MD
    M
    instance_type = "t2.micro"
    4
    image-1.png
    15
    tags = {
    image.png
    6
    Name = "Provisioner"
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    provisioner "local-exec" {
    > notes
    10
    command = "echo this is server IP ${self . private_IP}" # self = aws_instance . web
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    > terraform-multi-env
    terraform-provisioners
    ec2.tf
    U
    provider.tf
    U

[^44]: REPOS
    terraform-provisioners > provider.tf > > provider "aws"
    > Ansible
    1
    terraform {
    v Concepts
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
    version = "5.31.0" # AWS provider version, not terraform version
    image.png
    16
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    backend "s3" {
    10
    > notes
    bucket = "chilops-terraform-remotestate"
    11
    > Robosho-shellscripts
    key
    = "provisioner"
    M
    12
    region = "us-east-1"
    > roboshop-ansible
    13
    dynamodb_table = "chilops-locking"
    > roboshop-ansible-roles
    14
    }
    > shellscripts
    15
    > terraform
    16
    > terraform-multi-env
    17
    provider "aws" {
    18
    v terraform-provisioners
    region = "us-east-1"
    19
    ec2.tf
    provider.tf
    U

[^45]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos/terraform-provisioners (main)
    $ terraform init
    Initializing the backend. ..
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing provider plugins . . .
    Finding hashicorp/aws versions matching "5. 31.0". ..
    Installing hashicorp/aws v5 . 31.0. .
    Installed hashicorp/aws v5. 31.0 (signed by Hashicorp)
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
    chowd@chowdary MINGW64 /e/AWSDevops/Repos/terraform-provisioners (main)
    ST

[^46]: $ terraform apply -auto-approve
    Acquiring state lock. This may take a few moments . . .
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance. web will be created
    resource "aws_instance" "web" {
    ami
    E
    "ami-Of 3c7d07486cad139"
    +
    arn
    (known after apply)
    +
    associate_public_ip_address
    (known after apply)
    availability_zone
    (known after apply)
    cpu_core_count
    E
    (known after apply)
    cpu_threads_per_core
    (known after apply)
    disable_api_stop
    E
    (known after apply)
    disable_api_termination
    (known after apply)
    ebs_optimized
    (known after apply)
    get_password_data
    false
    host_id
    E
    (known after apply)
    host_resource_group_arn
    (known after apply)
    +
    i am_instance_profile
    (known after apply)
    id
    (known after apply)
    instance_initiated_shutdown_behavior
    (known after apply)
    instance_lifecycle
    (known after apply)
    instance_state
    E
    (known after apply)
    +
    instance_type
    "t2 . micro"
    ipv6_address_count
    =
    (known after apply)
    ipv6 addresses
    (known after apply)

[^47]: Plan: 1 to add, 0 to change, 0 to destroy.
    aws_instance . web: Creating. . .
    aws_instance . web: Still creating. . .
    \[10s elapsed\]
    aws_instance . web: Still creating. . .
    \[20s elapsed\]
    aws_instance . web: Still creating. . .
    \[30s elapsed\]
    aws_instance .web: Provisioning with 'local-exec'..
    aws_instance . web (local-exec): Executing: \["cmd" "/C" "echo this is server IP 172. 31. 27. 178"\]
    aws_instance . web (local-exec): this is server IP 172. 31. 27. 178
    aws_instance . web: Creation complete after 37s \[id=i-032b350a290cd6c09\]
    Releasing state lock. This may take a few moments . . .

[^48]: $ terraform destroy -auto-approve
    Acquiring state lock. This may take a few moments.
    aws_instance . web: Refreshing state. . . \[id=i-032b350a290cd6c09\]
    Terraform used the selected providers to generate the following execution
    plan. Resource actions are indicated with the following symbols:
    - destroy
    Terraform will perform the following actions:
    # aws_instance . web will be destroyed
    resource "aws_instance" "web" {
    ami
    "ami-Of 3c7 d07486cad139" -> null
    arn
    "arn : aws : ec2 :us-east-1: 158724841371: instance/i-032b350a290cd6c09"
    -
    associate_public_ip_address
    false -> null
    -
    availability_zone
    E
    "us-east-1d"
    -> null

[^49]: EXPLORER
    provider.tf terraform-provisioners U .
    = terraform-provider-aws_v5.31.0_x5.exe
    ec2.tf .\\workspaces
    ec2.tf terraform-provisioners U .
    variables.tf .. \\workspaces
    REPOS
    terraform-provisioners > \\ec2.tf > { resource "aws_instance" "web" > $ provisioner "local-exec" > @ command
    > Ansible
    1
    resource "aws_instance" "web" {
    Concepts
    N
    ami
    = "ami -Of3c7d07486cad139" #devops-practice
    13
    Ansible.MD
    M
    instance_type = "t2.micro"
    4
    image-1.png
    15
    tags = {
    image.png
    6
    Name = "Provisioner"
    {} person.json
    M
    7
    person.xml
    18
    person.yaml
    9
    provisioner "local-exec" {
    > notes
    command = "echo this will execute at the time of creation, you can trigger other system like email and sending alerts" # self =
    > Robosho-shellscripts
    M
    aws_instance . web
    11
    }
    > roboshop-ansible
    12
    provisioner "local-exec" {
    > roboshop-ansible-roles
    13
    command = "echo ${self.private_ip} > inventory" # self = aws_instance. web
    > shellscripts
    14
    > terraform
    15
    > terraform-multi-env
    16
    # provisioner "local-exec" {
    17
    v terraform-provisioners
    D
    command = "ansible-playbook -i inventory web . yaml" # self = aws_instance . web
    18
    # }
    v .terraform
    19
    > providers
    20
    provisioner "local-exec" {
    {} terraform.tfstate
    U
    21
    when = destroy
    E.terraform.lock.hcl
    U
    22
    command = "echo this will execute at the time of destroy, you can trigger other system like email and sending alerts" # self =
    ec2.tf
    U
    aws_instance . web
    provider.tf
    23
    U
    24

[^50]: aws_instance . web: Provisioning with 'local-exec
    aws_instance . web (local-exec): Executing: \["cmd" "/C" "echo 172. 31.16.57 > inventory"\]
    aws_instance . web: Provisioning with 'local-exec'
    aws_instance . web (local-exec): Executing: \["cmd" "/C" "ansible-playbook -i inventory web. yam1"\]
    aws_instance. web (local-exec): 'ansible-playbook' is not recognized as an internal or external command,
    aws_instance . web (local-exec): operable program or batch file.
    Error: local-exec provisioner error
    with aws_instance. web,
    on ec2. tf line 17, in resource "aws_instance" "web":
    17:
    provisioner "local-exec" {
    Error running command 'ansible-playbook -i inventory web. yaml' : exit status
    1. Output: ' ansible-playbook' is not recognized as an internal or external
    command ,
    operable program or batch file.

[^51]: null
    volume_type
    = "gp2" -> null
    (1 unchanged attribute hidden)
    Plan: 0 to add, 0 to change, 1 to destroy.
    aws_instance . web: Destroying. . . \[id=i-05b4ab86592622coe\]
    aws_instance . web: Provisioning with 'local-exec'.
    aws_instance . web (local-exec) : Executing: \["cmd" "/C" "echo this will execute at the time of destroy, you can trigger other system like email and sending alerts"\]
    aws_instance . web (local-exec) : this will execute at the time of destroy, you can trigger other system like email and sending alerts
    aws_instance . web: Still destroying. .. \[id=i-05b4ab86592622c0e, 10s elapsed\]

[^52]: terraform-provisioners > ec2.tf > $ resource "aws_instance" "web"
    1
    resource "aws_instance" "web" {
    ami
    "ami -Of3c7d07486cad139" #devops-practice
    IA W N
    instance_type = "t2.micro"
    vpc_security_group_ids = \[aws_security_group . roboshop-all. id\]
    tags = {
    Name = "provisioner"
    8
    9
    10
    provisioner "local-exec" {
    11
    command = "echo this will execute at the time of creation, you can trigger other system like email and sending alerts" # self =
    aws_instance . web
    12
    13
    14
    provisioner "local-exec" {
    15
    command = "echo ${self. private_ip} > inventory" # self = aws_instance. web
    16
    17
    18
    # provisioner "local-exec" {
    19
    command = "ansible-playbook -i inventory web . yam1" # self = aws_instance. web
    20
    21
    provisioner "local-exec" {
    23
    when = destroy
    command = "echo this will execute at the time of destroy, you can trigger other system like email and sending alerts" # self =
    aws_instance . web
    26
    27
    connection {
    28
    type
    "ssh"
    29
    user
    "centos"
    30
    password = "Devops321"
    31
    post
    = self. public_ip
    33
    34
    provisioner "remote-exec" {
    35
    inline = \[
    36
    "echo 'this is from remote exec' > /tmp/remote. txt",
    37
    "sudo yum install nginx -y",
    38
    "sudo systemctl start nginx"
    39
    40
    41
    42
    Ln 1, Col 1 Spaces: 2 UTF-8 CRLF

[^53]: 42
    43
    resource "aws_security_group" "roboshop-all" {
    44
    name
    = "provisioner"
    45
    46
    ingress {
    47
    description
    = "Allow All ports"
    48
    from_port
    = 22
    49
    to_port
    = 22
    50
    protocol
    = "tcp"
    51
    cidr_blocks
    = \["0.0.0.0/0"\]
    52
    LP
    53
    54
    ingress {
    55
    description
    "Allow All ports"
    56
    from_port
    80
    57
    to_port
    =
    80
    58
    protocol
    =
    "tcp"
    59
    cidr_blocks
    = \["0.0.0.0/0"\]
    60
    61
    62
    egress {
    63
    from_port
    64
    to_port
    65
    protocol
    11-1"
    66
    cidr_blocks
    = \["0.0.0.0/0"\]
    67
    68
    69
    tags = {
    70
    Name = "provisioner"
    71
    72

[^54]: aws_instance . web (remote-exec) :
    Target Platform: unix
    aws_instance . web: Still creating. . .
    \[40s elapsed\]
    aws_instance . web: Still creating. .. \[50s elapsed\]
    aws_instance . web (remote-exec) : Connecting to remote host via SSH. . .
    aws_instance . web (remote-exec) :
    Host: 100.26. 54. 165
    aws_instance . web
    (remote-exec) :
    User: centos
    aws_instance . web
    (remote-exec) :
    Password: true
    aws_instance . web
    (remote-exec) :
    Private key: false
    aws_instance . web
    (remote-exec) :
    Certificate: false
    aws_instance . web
    (remote-exec) :
    SSH Agent: false
    aws_instance . web
    (remote-exec) :
    Checking Host Key: false
    aws_instance . web (remote-exec) :
    Target Platform: unix
    aws_instance . web (remote-exec) : Connected!
    aws_instance . web: Still creating. .. \[1mos elapsed\]
    aws_instance . web (remote-exec) : Centos
    B/S
    0
    B
    ETA
    aws_instance . web (remote-exec): Centos
    ---
    B/S
    O B
    --: -- ETA
    aws_instance . web (remote-exec): Centos
    36 MB/S
    11 MB
    00: 00 ETA
    aws_instance . web (remote-exec): Centos
    25 MB/S
    28 MB
    00 : 01
    aws_instance . web: Still creating. .. \[1m10s elapsed\]
    aws_instance . web: Still creating. .. \[1m20s elapsed\]
    aws_instance . web (remote-exec) : Centos
    B/S
    0
    B
    ETA
    aws_instance . web (remote-exec): Centos
    ---
    B/S
    O B
    -- : -- ETA
    aws_instance . web (remote-exec) : Centos
    15 MB /S
    10 MB
    00: 00
    aws_instance . web (remote-exec) : Centos
    B/S
    O B
    --: --
    ETA
    aws_instance . web (remote-exec) : Centos
    79 KB/S
    18 KB
    00: 00
    aws_instance . web (remote-exec) : Centos
    B/S
    O B
    --: --
    ETA
    aws_instance . web (remote-exec) : Centos
    102 KB/s
    7.7 KB
    00: 00
    aws_instance . web (remote-exec) : Extra P ---
    B/S
    O B
    --: --
    ETA
    aws_instance .web (remote-exec) : Extra P 33 MB/s
    14 MB
    00:00
    aws_instance . web: Still creating. .. \[1m30s elapsed\]
    aws_instance . web (remote-exec) : Dependencies resolved.
    aws_instance .web (remote-exec) : =
    aws_instance . web (remote-exec) :
    Package
    aws_instance . web (remote-exec) :
    Arch
    Version
    Repo
    Size
    aws_instance . web (remote-exec) :
    aws_instance . web (remote-exec): Installing:
    aws_instance . web (remote-exec) :
    nginx
    aws_instance . web (remote-exec) :
    x86_64 1:1. 14.1-9. module_e18. 0. 0+1060+3ab382d3
    aws_instance . web (remote-exec) :
    appstream 570 k
    aws_instance . web (remote-exec): Installing dependencies:
    aws_instance . web (remote-exec) :
    dejavu-fonts -common
    aws_instance .web (remote-exec) :
    noarch 2.35-7. e18
    baseos
    74 k
    aws_instance . web (remote-exec) :
    dejavu-sans-fonts
    aws_instance . web (remote-exec) :
    noarch 2. 35-7. e18
    baseos
    1.6 M
    aws_instance . web (remote-exec) :
    fontconfig
    aws_instance . web (remote-exec) :
    x86_64 2. 13.1-4.e18 baseos
    274 k
    aws_instance . web (remote-exec) :
    fontpackages-filesystem
    aws_instance . web (remote-exec) :
    noarch 1. 44-22. e18
    baseos
    16 k

[^55]: C
    Not secure 100.26.54.165
    Welcome to nginx on Red Hat Enterprise Linux!
    This page is used to test the proper operation of the nginx HTTP server after it has been installed. If you can read this page, it means that the web server installed at this site is working properly.
    Website Administrator
    This is the default index. html page that is distributed with nginx on Red Hat Enterprise Linux. It is located in /usr/ share/nginx/html.
    You should now put your content in a location of your choice and edit the root configuration directive in the nginx configuration file /etc/nginx/nginx. conf.
    For information on Red Hat Enterprise Linux, please visit the Red Hat, Inc. website. The documentation for Red Hat Enterprise Linux is available on the Red Hat, Inc. website.
    NGINX
    POWERED BY
    redhat.

