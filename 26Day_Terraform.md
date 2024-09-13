---
title: 26Day_Terraform
uuid: 3d5f36c2-11b8-11ef-af96-9a665e06d35f
version: 948
created: '2024-05-14T11:37:27+05:30'
tags:
  - terraform
---

\

***Topics:***

1. *<mark style="background-color:#f8d616;">Variables & datatypes in Terraform<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *If variable not declared*

    1. *variables overriding*

1. *<mark style="background-color:#f8d616;">Conditions -<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f8914d;">we use conditions heavily in terraform<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"offset":1} -->

1. *<mark style="background-color:#f8d616;">Loops - Two types<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *count based loop - Its a terraform concept  <mark style="background-color:#f8914d;">(Launched all instances and created Route53 records) - useful mostly to iterate lists<!-- {"backgroundCycleColor":"24"} --></mark>*

    1. *for each loop - <mark style="background-color:#f8914d;">useful to iterate maps (this topic is covered in 27Day session)<!-- {"backgroundCycleColor":"24"} --></mark>*

    1. Dynamic loop - *<mark style="background-color:#f8914d;">(this topic is covered in 27Day session)<!-- {"backgroundCycleColor":"24"} --></mark>*

1. *<mark style="background-color:#f8d616;">Functions<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"offset":3} -->

\

\

\

# *<mark style="background-color:#f8914d;">**Variables & datatype in Terraform**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*Created Variables folder and added provider.tf code.*

![f749ec72-b37b-4277-8ebd-18f7d135694b.png|991.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f749ec72-b37b-4277-8ebd-18f7d135694b.png) [^1]

\

```
cd terraform/
cd variables/
terraform init
```

![a9a5be29-6b68-49a3-b57f-d3a047d2e48a.png|660](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/a9a5be29-6b68-49a3-b57f-d3a047d2e48a.png) [^2]

\

*Created Ec2.tf & variables.tf files.  -- In Ec2.tf variables given "**var.ami_id**" but not declared in variables.tf file so error will get as below*

![ab09ec45-a29a-4322-af6c-3cef1f9af8c4.png|928.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/ab09ec45-a29a-4322-af6c-3cef1f9af8c4.png) [^3]

\

```
terraform plan
```

![810da410-0437-477e-8179-85ee9f3621de.png|884.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/810da410-0437-477e-8179-85ee9f3621de.png) [^4]

\

*EC2.tf code for only instance launch*

![b8f2fd95-51e5-451e-b977-5f06ae656442.png|816](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/b8f2fd95-51e5-451e-b977-5f06ae656442.png) [^5]

\

*its variable.tf code*

![d64d742a-e7c4-4eb8-8db9-2ff4a1e336d4.png|559](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/d64d742a-e7c4-4eb8-8db9-2ff4a1e336d4.png) [^6]

\

```
terraform plan
```

```
terraform apply -auto-approve
```

![5a0eb37b-a9fa-432c-bbc3-31855f766a42.png|700](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/5a0eb37b-a9fa-432c-bbc3-31855f766a42.png) [^7]

\

![c4bdd5c4-3e7f-4b63-b7a6-30f8df90109d.png|788.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/c4bdd5c4-3e7f-4b63-b7a6-30f8df90109d.png) [^8]

```
terraform destroy -auto-approve
```

![6674e7de-2ada-4530-a2fe-1c05fa47c7e1.png|815.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/6674e7de-2ada-4530-a2fe-1c05fa47c7e1.png) [^9]

![e845c21f-a62f-41e9-b2ba-819208d702f2.png|813](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/e845c21f-a62f-41e9-b2ba-819208d702f2.png) [^10]

\

![f1bf2877-5144-46ac-b6d1-aacb748c43ef.png|828](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f1bf2877-5144-46ac-b6d1-aacb748c43ef.png) [^11]

\

\

*Now create separate sg.tf file for security group:*

![b9ec75b6-9f60-4801-8204-55f6c5925615.png|806](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/b9ec75b6-9f60-4801-8204-55f6c5925615.png) [^12]

\

*ec2.tf code*

![7adca136-34d6-4198-96b0-0d01e2c7dfd3.png|803](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/7adca136-34d6-4198-96b0-0d01e2c7dfd3.png) [^13]

\

*variables.tf file for ec2 & security group:*

![f4661e73-15ae-4bf1-bff6-d5642ad16243.png|697](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f4661e73-15ae-4bf1-bff6-d5642ad16243.png) [^14]

\

```
terraform plan
```

```
terraform apply -auto-approve
```

\

![5bb3df6f-efbf-4993-a432-eafe85d90f99.png|820.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/5bb3df6f-efbf-4993-a432-eafe85d90f99.png) [^15]

![f03a5683-d598-4523-82de-58f367fadb30.png|821](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f03a5683-d598-4523-82de-58f367fadb30.png) [^16]

\

![178021e2-ad28-4abb-b8b5-3d5f6348772c.png|847.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/178021e2-ad28-4abb-b8b5-3d5f6348772c.png) [^17]

\

*Instance tags*

![486d900c-f6a4-456e-a9c9-0a69b15a673f.png|864](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/486d900c-f6a4-456e-a9c9-0a69b15a673f.png) [^18]

*Also security group created*

![2972b8e7-ef2d-4708-bcc9-2d36e3aa90e9.png|905.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/2972b8e7-ef2d-4708-bcc9-2d36e3aa90e9.png) [^19]

\

```
terraform destroy -auto-approve
```

![f463e5ad-f400-4d82-99f6-5706310483fc.png|729](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f463e5ad-f400-4d82-99f6-5706310483fc.png) [^20]

\

# *<mark style="background-color:#f8914d;">**If variable not declared**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Commented as below*

![952aa842-0cd0-46ba-83c6-cd499fe3c72c.png|716](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/952aa842-0cd0-46ba-83c6-cd499fe3c72c.png) [^21]

\

*Now its asking for AMI-ID value*

```
terraform plan
```

![](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/5a9d7301-5aaf-4fcb-9401-168a2ad0aa7d.png) [^22]

\

# *<mark style="background-color:#f8914d;">**variables overriding**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*<mark>**terraform.tfvars is used to overwrite the default values in variable.tf file.**</mark>*

*.<mark>tfvars extension can create any other files like roboshop.tfvars</mark>*

*Create **terraform.tfvars** file - values we can give in this file like 't3.small' etc.*

![f267ece5-4880-4ebb-aa23-62a859c88f6e.png|576](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f267ece5-4880-4ebb-aa23-62a859c88f6e.png) [^23]

\

*But in **variables.tf** file instance type is **t2.micro** now **terraform.tfvars** will override & creates <mark style="background-color:#f3de6c;">**t3.small**<!-- {"backgroundCycleColor":"14"} --></mark> instance.*

![](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/03e12952-8c45-4bc3-81c2-da74c6da2761.png) [^24]

\

*Uncommented which previously commented*

![0e7703b5-e487-4e19-b104-7eac4a7c40dc.png|666](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/0e7703b5-e487-4e19-b104-7eac4a7c40dc.png) [^25]

\

*Now you can see t3.small instance*

```
terraform plan
```

![745f818b-8fd1-40b4-a3c4-ca86489df7f2.png|708](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/745f818b-8fd1-40b4-a3c4-ca86489df7f2.png) [^26]

\

*Or we can declare variables when we are executing terraform plan*

```
terraform plan -var="instance_type=t3.medium"
```

![3b45d2bd-ca64-4df5-91ff-46d89a7fa133.png|890.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/3b45d2bd-ca64-4df5-91ff-46d89a7fa133.png) [^27]

\

\

*Creating some file with .tfvars... Ex: roboshop.tfvars*

![6fce9d1c-b6e0-4971-ac6d-083ce89116a3.png|611](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/6fce9d1c-b6e0-4971-ac6d-083ce89116a3.png) [^28]

\

```
terraform plan -var-file="roboshop.tfvars"
```

![3bf07e06-0b29-4d0b-88b5-d34e7032ff55.png|946.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/3bf07e06-0b29-4d0b-88b5-d34e7032ff55.png) [^29]

\

*using environmental variables:*

![b8d6c63c-95f8-4e9a-a7e0-ab8752f2b6eb.png|724](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/b8d6c63c-95f8-4e9a-a7e0-ab8752f2b6eb.png) [^30]

![](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/6a4db553-3b6e-47af-b618-941b0a500cc3.png)

\

```
terraform plan -var-file="roboshop.tfvars" -var="instance_type=t3.medium"
```

![](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/486fdad9-f52f-4c30-99d4-6c00491eaeed.png) [^31]

![df77d49e-b44d-4c6f-ac45-86fee22c9995.png|393](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/df77d49e-b44d-4c6f-ac45-86fee22c9995.png) [^32]

\

\

\

# *<mark style="background-color:#f8914d;">**Conditions**<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#f8d616;">-<!-- {"backgroundCycleColor":"25"} --></mark> <mark style="background-color:#f8914d;">we use conditions heavily in terraform<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

***Syntax:***

```
if (expression) {
         if true this will run
}
```

```
if (expression) {
          if true this will run
}
else {
          if false this will run
}
```

\

*One line syntax for conditions: terraform will follow this.*

```
expression ? "this will run if true" : "this will run if false"
```

\

*<mark style="background-color:#f8d616;">Conditions folder created & provider.tf file created.<!-- {"backgroundCycleColor":"25"} --></mark>*

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "5.49.0"  #AWS provider version, not terraform version
    }
  }
}

provider "aws" {
     region = "us-east-1"
}
```

![541fa4a5-ad81-44c4-9985-f2c6183c43c7.png|842.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/541fa4a5-ad81-44c4-9985-f2c6183c43c7.png) [^33]

\

***conditions.tf code***

```
resource "aws_instance" "web" {
  ami           = var.ami_id #devops-practice
  instance_type = var.instance_name == "MongoDB" ? "t3.small" : "t2.micro"
}
```

![6e503cb1-1c3f-49c4-81df-c9c516f528e7.png|887.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/6e503cb1-1c3f-49c4-81df-c9c516f528e7.png) [^34]

\

***Variables.tf code***

```
variable "instance_name" {
  type = string
  default = "MongoDB"
}

variable "ami_id" {
  type = string
  default = "ami-0f3c7d07486cad139"
}
```

![3e45a315-2061-4616-b904-4cb1ce9a06b2.png|578](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/3e45a315-2061-4616-b904-4cb1ce9a06b2.png) [^35]

\

```
terraform init
```

![cd2e6bbe-f1bd-4ba4-bf04-08a95d9c4fe2.png|682](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/cd2e6bbe-f1bd-4ba4-bf04-08a95d9c4fe2.png) [^36]

\

*so it selects t3.small instance*

```
terraform plan
```

![ae806d6f-dd10-4f54-ba67-f37c970a8c04.png|915.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/ae806d6f-dd10-4f54-ba67-f37c970a8c04.png) [^37]

\

*But if i change in variables from mongodb to web. so the condition is not true then see the output.*

```
variable "instance_name" {
  type = string
  default = "web"
}

variable "ami_id" {
  type = string
  default = "ami-0f3c7d07486cad139"
}
```

\

![daa42fde-06e7-435e-94da-d7a17136cbcd.png|878](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/daa42fde-06e7-435e-94da-d7a17136cbcd.png) [^38]

```
terraform plan
```

![4c404bd7-bc97-4e76-b4f5-7772098d67d3.png|838.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/4c404bd7-bc97-4e76-b4f5-7772098d67d3.png) [^39]

\

\

# *<mark style="background-color:#f8914d;">**Loops**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

1.  *<mark style="background-color:#f8d616;">Two types<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *count based loop - Its a terraform concept*  

    1. *for each loop*

\

# *<mark style="background-color:#f8914d;">**Count based loop** - Its a terraform concept  - useful mostly to iterate lists<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*<mark style="background-color:#fff;">count folder created & provider.tf file created.<!-- {"backgroundCycleColor":"11"} --></mark>*

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "5.49.0"  #AWS provider version, not terraform version
    }
  }
}

provider "aws" {
     region = "us-east-1"
}
```

![b084c23a-a503-4e8d-84fc-57f4df3819f4.png|783.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/b084c23a-a503-4e8d-84fc-57f4df3819f4.png) [^40]

\

\

***What is terraform output?***

```
Terraform output is used to get the information from the created resources. 
EX. When we created an instance if we need instance ID, AMI ID or any other details from created instance 
we can get from it in output.

Also terraform output is used to get the information of one resource and provide as input to other resources.
```

*}*![4306e35b-51dc-4aed-98cc-211ce9637fcd.png|699](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/4306e35b-51dc-4aed-98cc-211ce9637fcd.png) [^41]

\

```
cd variables
```

```
terraform apply -auto-approve
```

![d0a4baa4-b8a4-4eff-a36f-3f09e5859147.png|917.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/d0a4baa4-b8a4-4eff-a36f-3f09e5859147.png) [^42]

![cff55307-8892-4098-a8ca-571be445e9f8.png|711](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/cff55307-8892-4098-a8ca-571be445e9f8.png) [^43]

\

*<mark style="background-color:#f3de6c;">To check how terraform output comes:<!-- {"backgroundCycleColor":"14"} --></mark>*

\

*count.tf code*

![7db22dcf-2cd5-4f4a-8b2e-767b5694d9e5.png|1163.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/7db22dcf-2cd5-4f4a-8b2e-767b5694d9e5.png) [^44]

\

*output.tf code (where to test the output which we requested)*

![4a6a12f0-ce63-43a9-8d24-b73981cd0cdc.png|771](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/4a6a12f0-ce63-43a9-8d24-b73981cd0cdc.png) [^45]

\

```
terraform init
```

```
terraform apply -auto-approve
```

*Huge output generated for 11 instances. below is just a sample output.*

![1e092086-a19e-4f47-a445-c7d7df9cebbc.png|620](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/1e092086-a19e-4f47-a445-c7d7df9cebbc.png) [^46]

*Instances created*

![9303d6f9-d1a4-45ff-8846-603336c445e3.png|781.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/9303d6f9-d1a4-45ff-8846-603336c445e3.png) [^47]

\

\

*<mark style="background-color:#f3de6c;">Here testing usecase is.. create instances & update route53...<!-- {"backgroundCycleColor":"14"} --></mark>*

\

*count.tf code*

![de6680d4-650e-421d-8f03-d4d3ce77f4c3.png|888.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/de6680d4-650e-421d-8f03-d4d3ce77f4c3.png) [^48]

\

*variables.tf code*

![8d864c8e-42cd-43c5-bd9f-bb83418ac6dc.png|886.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/8d864c8e-42cd-43c5-bd9f-bb83418ac6dc.png) [^49]

\

*output.tf (its commented)*

![69aac344-076a-4368-9228-1f153e8bf2cd.png|437](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/69aac344-076a-4368-9228-1f153e8bf2cd.png) [^50]

\

```
terraform apply -auto-approve
```

\

![f1df183f-645f-4e90-84dd-f7906ff10b65.png|826.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/f1df183f-645f-4e90-84dd-f7906ff10b65.png) [^51]

![3ac26af6-1f32-4e06-94b9-1d928d0423dc.png|826](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/3ac26af6-1f32-4e06-94b9-1d928d0423dc.png) [^52]

\

*All Instances created.. t3.small created for mongodb, mysql, shipping*

![4f7e3451-6b7e-4fab-b86f-faf01808dca2.png|852.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/4f7e3451-6b7e-4fab-b86f-faf01808dca2.png) [^53]

\

*Route53 records also created, for web public ip assigned.*

![cf34e657-6bae-49ea-9c71-8f24dbb25ae2.png|873.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/cf34e657-6bae-49ea-9c71-8f24dbb25ae2.png) [^54]

\

```
terraform destroy -auto-approve
```

\

# *<mark style="background-color:#f8914d;">**Functions :**<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#f8d616;">**Terraform has its own function, those we can use it. But we can't create own functions in terraform.**<!-- {"backgroundCycleColor":"25"} --></mark>*<!-- {"collapsed":true} -->

\

*We need to give some input -- It will do some work -- It will give some output*

*N no.of times we can use it.*

\

[*Functions - Configuration Language \| Terraform \| HashiCorp Developer*](https://developer.hashicorp.com/terraform/language/functions)    *-- useful link for terraform functions lot of options are available*

 

```
terraform console
max(5,12, 9)
min(1, 3, 2)
join("-", ["foo", "bar", "baz"])
split(",", "foo,bar,baz"])
```

\

![d35671f4-71a3-41df-932b-96787bb752f0.png|676](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/d35671f4-71a3-41df-932b-96787bb752f0.png) [^55]

\

*Here length function is used to calculate the list from **variables.tf,** so if instances increases also count function will take care.*

 ![b2ccf2d5-d88e-43fd-8869-817c48985774.png|932.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/b2ccf2d5-d88e-43fd-8869-817c48985774.png) [^56]

![8da0e91a-89f3-4584-8438-f2809736718d.png|989.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/8da0e91a-89f3-4584-8438-f2809736718d.png) [^57]

\

\

\

\

![2cb5695b-c190-4036-8153-488740390991.png|975.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/2cb5695b-c190-4036-8153-488740390991.png) [^58]

\

*count.tf code*

![a4c641b6-0d4d-4e12-977a-9c8996cbd526.png|994.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/a4c641b6-0d4d-4e12-977a-9c8996cbd526.png) [^59]

\

*variables.tf code*

![277767b6-6b8a-4ac1-a856-272ba280af15.png|999.3333740234375](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/277767b6-6b8a-4ac1-a856-272ba280af15.png) [^60]

\

```
terraform plan
```

![eb469bea-2820-49a9-b0c3-14980f6251e5.png|689](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/eb469bea-2820-49a9-b0c3-14980f6251e5.png) [^61]

\

\

\

\

\

\

\

\

\

[^1]: V REPOS
    terraform > variables > provider.tf > ...
    > Ansible
    1
    terraform {
    > Concepts
    2
    required_providers {
    > notes
    aws = {
    4
    source = "hashicorp/aws"
    > Robosho-shellscripts
    M
    5
    version = "5.49.0" #AWS provider version, not terraform version
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    7
    > shellscripts
    18
    terraform
    9
    > session1 \\ EC2
    10
    provider "aws" {
    11
    region = "us-east-1"
    variables
    12
    provider.tf -
    13
    .gitignore
    i README.MD
    U

[^2]: MINGW64:/e/awsdevops/Repos/terraform/variables
    chowd@Chowdary MINGW64 /
    $ cd /e/awsdevops /Repos/
    chowd@Chowdary MINGW64 /e/awsdevops /Repos (main)
    $ cd terraform/
    chowd@chowdary MINGW64 /e/awsdevops/Repos/terraform (main)
    $ cd variables/
    chowd@chowdary MINGW64 /e/awsdevops /Repos/terraform/variables (main)
    s terraform init
    Initializing the backend. ..
    Initializing provider plugins ...
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. All Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    chowd@Chowdary MINGW64 /e/awsdevops /Repos/terraform/variables (main)

[^3]: REPOS
    terraform > variables > ec2.tf > % resource "aws_instance" "web"
    > Ansible
    1
    resource "aws_instance" "web" {
    > Concepts
    2
    ami
    = var . ami_id #devops-practice
    3
    > notes
    instance_type = "t2.micro"
    14
    Robosho-shellscripts
    #vpc_security_group_ids = \[aws_security_group . roboshop-all. id\] #This means list
    M
    5
    > roboshop-ansible
    6
    tags = {
    > roboshop-ansible-roles
    17
    Name = "HelloTerraform"
    > shellscripts
    8
    v terraform
    9
    v session 1 \\ EC2
    > .terraform
    E .terraform.lock.hcl
    ec2.tf
    provider.tf
    {} terraform.tfstate
    E terraform.tfstate.backup
    variables.tf
    variables
    > .terraform
    E .terraform.lock.hcl
    U
    ec2.tf
    1, U
    provider.tf
    U
    variables.tf
    U

[^4]: PS E: \\AWSDevops \\Repos \\terraform\\variables> terraform plan
    Error: Reference to undeclared input variable
    on ec2.tf line 2, in resource "aws_instance" "web":
    2:
    ami
    = var . ami_id #devops-practice
    An input variable with the name "ami_id" has not been declared. This variable can be declared with a variable "ami_id" {} block.
    PS E: \\AWSDevops \\Repos \\terraform\\variables>

[^5]: terraform > variables > ec2.tf > { resource "aws_instance" "web"
    resource "aws_instance" "web" {
    2
    ami
    = var . ami_id #devops-practice
    3
    instance_type = var . instance_type
    4
    #vpc_security_group_ids = \[aws_security_group . roboshop-all. id\]
    #This means list
    tags = var . tags

[^6]: terraform > variables > variables.tf > < variable "tags"
    1
    # 1. command line
    2
    # 2. -var-file
    3
    # 3. terraform . tfvars
    4
    # 4. ENV variables
    5
    6
    variable "ami_id" {
    7
    type = string
    8
    default = "ami-Of3c7d07486cad139"
    9
    10
    11
    variable "instance_type" {
    12
    default = "t2.micro"
    13
    type = string
    14
    15
    16
    variable "tags" {
    17
    type = map
    #map variable types
    18
    default = {
    19
    Name = "Hello Terraform"
    20
    Project = "Roboshop"
    21
    Environment = "DEV"
    22
    Component = "Web"
    23
    Terraform = "true"
    24
    25

[^7]: Plan: 1 to add, 0 to change, 0 to destroy.
    aws_instance. web: Creating. . .
    aws_instance.web: Still creating... \[10s elapsed\]
    aws_instance.web: Still creating... \[20s elapsed\]
    aws instance. web: Still creating... \[30s elapsed\]
    aws_instance. web: Creation complete after 36s \[id=i-03066e96a45fbe442\]
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevOps\\Repos \\terraform\\variables>

[^8]: Instances (1) Info
    G
    Connect
    Instance state
    Actions
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Name _
    4
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Hello Terraform
    i-03066e96a45fbe442
    Pending
    t2.micro

[^9]: PS E: \\AWSDevops \\Repos \\terraform\\variables> terraform destroy -auto-approve
    aws_instance.web: Refreshing state. .. \[id=i-03066e96a45fbe442\]
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    - destroy
    Terraform will perform the following actions:
    # aws_instance.web will be destroyed
    resource "aws_instance" "web" {
    ami
    = "ami-Of3c7d07486cad139" -> null
    1 : 158724841371:
    93066-96245fbe447 "

[^10]: Plan: 0 to add, 0 to change, 1 to destroy.
    aws_instance . web: Destroying... \[id=i-03066e96a45fbe442\]
    aws_instance.web: Still destroying... \[id=i-03066e96a45fbe442, 10s elapsed\]
    aws_instance.web: Still destroying... \[id=i-03066e96a45fbe442, 20s elapsed\]
    aws_instance.web: Still destroying... \[id=i-03066e96a45fbe442, 30s elapsed\]
    aws instance. web: Destruction complete after 33s
    Destroy complete! Resources: 1 destroyed.
    PS F: \\AWSDevOps \\Repos\\terraform\\variables> l

[^11]: Instances (1) Info
    C
    Connect
    Instance state
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Name _
    V
    Instance ID
    Instance state
    V
    Instance type
    A
    Hello Terraform
    i-03066e96a45fbe442
    Terminated
    t2.micro

[^12]: terraform > variables > sg.tf > % resource "aws_security_group" "roboshop-all" > { egress > . protocol
    1
    resource "aws_security_group" "roboshop-all" { #This is terraform name, for terraform reference only
    2
    name
    = var . sg-name #This is AWS name which reflects in AWS
    3
    description = var . sg-description
    4
    #vpc_id
    = aws_vpc . main. id
    15
    6
    ingress {
    7
    description
    = "Allow All ports"
    8
    from_port
    = var . inbound-from-port #0 means all ports
    9
    to_port
    = 0
    10
    protocol
    "tcp"
    11
    cidr_blocks
    = var . cidr_blocks
    12
    #ipv6_cidr_blocks = \[aws_vpc . main . ipv6_cidr_block\]
    13
    14
    15
    egress {
    16
    from_port
    e
    17
    to_port
    18
    protocol
    11-1"
    19
    cidr_blocks
    = \["0.0.0.0/0"\]
    20
    #ipv6_cidr_blocks = \[": :/0"\]
    21
    22
    23
    tags = {
    24
    Name = "roboshop-all-aws"
    25
    26

[^13]: terraform > variables > ec2.tf > % resource "aws_instance" "web" > \[ \] vpc_security_group_ids
    1
    resource "aws_instance" "web" {
    2
    ami
    = var . ami_id #devops-practice
    instance_type = var . instance_type
    14
    vpc_security_group_ids = \[aws_security_group . roboshop-all. id\] #This means list
    15
    6
    tags = var . tags
    7

[^14]: terraform > variables > variables.tf > $ variable "sg-name" > @ type
    4
    # 4. ENV variables
    5
    6
    variable "ami_id" {
    7
    type = string
    8
    default = "ami-Of3c7d07486cad139"
    9
    10
    11
    variable "instance_type" {
    12
    default = "t2.micro"
    13
    type = string
    14
    15
    16
    variable "tags" {
    17
    type = map
    #map variable types
    18
    default = {
    19
    Name = "Hello Terraform"
    20
    Project = "Roboshop"
    21
    Environment = "DEV"
    22
    Component = "Web"
    23
    Terraform = "true"
    24
    25
    26
    27
    variable "sg-name" {
    28
    type = string
    29
    default = "roboshop-all"
    30
    31
    32
    variable "sg-description" {
    33
    type = string
    34
    default = "allowing all ports"
    35
    36
    37
    variable "inbound-from-port" {
    38
    type = number
    39
    default = 0
    40
    41
    42
    variable "cidr_blocks" {
    43
    type = list
    44
    default = \["0.0.0.0/0"\]
    45

[^15]: PS E: \\AWSDevops \\Repos \\terraform\\variables> terraform apply -auto-approve
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance. web will be created
    + resource "aws_instance" "web" {
    ami
    = "ami -Of3c7d07486cad139"
    arn
    = (known after apply)

[^16]: Plan: 2 to add, 0 to change, 0 to destroy.
    aws_security_group . roboshop-all: Creating...
    aws_security_group. roboshop-all: Creation complete after 6s \[id=sg-04ba5dccf6fe618ff\]
    aws_instance. web: Creating. . .
    aws_instance.web: Still creating... \[10s elapsed\]
    aws_instance.web: Still creating. ..
    \[20s elapsed\]
    aws_instance.web: Still creating... \[30s elapsed\]
    aws_instance. web: Creation complete after 36s \[id=i-0d40508c555cd0a28\]
    Apply complete! Resources: 2 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevops \\Repos \\terraform\\variables>

[^17]: Instances (2) Info
    C
    Connect
    Instance state
    Actions
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Name _
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Hello Terraform
    i-03066e96a45fbe442
    Terminated
    t2.micro
    Hello Terraform
    i-Od40508c555cd0a28
    Running
    t2.micro
    Initializing

[^18]: i-0d40508c555cd0a28 (Hello Terraform)
    Details
    Status and alarms New
    Monitoring
    Security
    Networking
    Storage
    Tags
    Tags
    Q
    Key
    Value
    Component
    Web
    Environment
    DEV
    Terraform
    true
    Project
    Roboshop
    Name
    Hello Terraform

[^19]: i-0d40508c555cd0a28 (Hello Terraform)
    Details
    Status and alarms New
    Monitoring
    Security
    Networking
    Storage
    Tags
    Security details
    IAM Role
    Owner ID
    Launch time
    158724841371
    Tue May 14 2024 12:29:25
    Security groups
    \[ sg-04ba5dccf6fe618ff (roboshop-all)

[^20]: Plan: 0 to add, 0 to change, 2 to destroy.
    aws_instance. web: Destroying. .. \[id=i-0d40508c555cd0a28\]
    aws_instance.web: Still destroying. .. \[id=i-0d40508c555cd0a28, 10s elapsed\]
    aws_instance.web: Still destroying. .. \[id=i-0d40508c555cd0a28, 20s elapsed\]

[^21]: terraform > variables > variables.tf > % variable "ami_id"
    1
    # 1. command line
    # 2. -var-file
    3
    # 3. terraform. tfvars
    4
    # 4. ENV variables
    5
    16
    variable "ami_id" {
    7
    type = string
    8
    #default = "ami-Of3c7d07486cad139"

[^22]: PS E: \\AWSDevops \\Repos \\terraform\\variables> terraform plan
    var . ami id
    Enter a value:

[^23]: terraform > variables > terraform.tfvars > . instance_type
    1
    instance_type = "t3. small"

[^24]: terraform > variables > variables.tf > % variable "instance_type" > . default
    1
    # 1. command line
    # 2. -var-file
    3
    # 3. terraform. tfvars
    4
    # 4. ENV variables
    5
    6
    variable "ami_id" {
    7
    type = string
    8
    #default = "ami-Of3c7d07486cad139"
    9
    10
    11
    variable "instance_type" {
    12
    default = "t2.micro"
    13
    type = string
    14
    15

[^25]: terraform > variables > variables.tf > % variable "ami_id" > ) default
    1
    # 1. command line
    12
    # 2. -var-file
    13
    # 3. terraform. tfvars
    4
    # 4. ENV variables
    5
    6
    variable "ami_id" {
    7
    type = string
    8
    default = "ami-Of3c7d07486cad139" _
    9

[^26]: Terraform will perform the following actions:
    # aws_instance.web will be created
    + resource "aws_instance" "web" {
    + ami
    = "ami-Of3c7d07486cad139"
    + arn
    = (known after apply)
    +
    associate_public_ip_address
    = (known after apply)
    +
    availability_zone
    = (known after apply)
    +
    cpu_core_count
    = (known after apply)
    +
    cpu_threads_per_core
    = (known after apply)
    +
    disable_api_stop
    = (known after apply)
    +
    disable_api_termination
    = (known after apply)
    + ebs_optimized
    = (known after apply)
    +
    get_password_data
    = false
    +
    host id
    = (known after apply)
    +
    host_resource_group_arn
    = (known after apply)
    + iam_instance_profile
    = (known after apply)
    +
    id
    = (known after apply)
    +
    instance_initiated_shutdown_behavior = (known after apply)
    + instance_lifecycle
    = (known after apply)
    + instance_state
    = (known after apply)
    + instance_type
    = "t3. small"
    +
    ipv6_address_count
    = (known after apply)

[^27]: PS E: \\AWSDevops \\Repos \\terraform\\variables> terraform plan -var="instance_type=t3.medium"
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance.web will be created
    resource "aws_instance" "web" {
    + ami
    = "ami-Of3c7d07486cad139"
    + arn
    = (known after apply)
    + associate_public_ip_address
    = (known after apply)
    + availability_zone
    = (known after apply)
    cpu_core_count
    = (known after apply)
    +
    cpu_threads_per_core
    = (known after apply)
    disable_api_stop
    = (known after apply)
    + disable_api_termination
    = (known after apply)
    ebs_optimized
    = (known after apply)
    get_password_data
    = false
    + host id
    = (known after apply)
    + host_resource_group_arn
    = (known after apply)
    + iam_instance_profile
    = (known after apply)
    + id
    = (known after apply)
    instance_initiated_shutdown_behavior = (known after apply)
    + instance_lifecycle
    = (known after apply)
    + instance_state
    = (known after apply)
    instance_type
    "t3.medium"
    ipv6_address_count
    = (known after apply)
    ipv6_addresses
    (known after apply)

[^28]: EXPLORER
    . . .
    les.tf ..\\EC2 .
    .gitignore
    provider.tf U
    ec2.tf ..\\va
    V REPOS
    terraform > variables > roboshop.tfvars > _ instance_type
    > Ansible
    1 instance_type = "t3. small"
    > Concepts
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    terraform
    > session1
    variables
    > .terraform
    E .terraform.lock.hcl
    U
    ec2.tf
    U
    provider.tf
    U
    roboshop.tfvars
    sg.tf
    U
    {} terraform.tfstate
    E terraform.tfstate.backup
    terraform.tfvars
    variables.tf
    U
    gitignore

[^29]: PS E: \\AWSDevOps \\Repos \\terraform\\variables> terraform plan -var-file="roboshop. tfvars"
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance. web will be created
    + resource "aws_instance" "web" {
    + ami
    "ami -Of3c7d07486cad139"
    arn
    = (known after apply)
    + associate_public_ip_address
    = (known after apply)
    + availability_zone
    = (known after apply)
    +
    cpu_core_count
    = (known after apply)
    + cpu_threads_per_core
    = (known after apply)
    disable_api_stop
    = (known after apply)
    disable_api_termination
    = (known after apply)
    ebs_optimized
    = (known after apply)
    + get_password_data
    = false
    + host id
    = (known after apply)
    + host_resource_group_arn
    = (known after apply)
    + iam_instance_profile
    = (known after apply)
    + id
    = (known after apply)
    instance_initiated_shutdown_behavior = (known after apply)
    instance_lifecycle
    = (known after apply)
    + instance_state
    = (known after apply)
    + instance_type
    E
    "t3. large" -
    + ipv6_address_count
    = (known after apply)
    ipv6_addresses
    = (known after apply)

[^30]: C: \\devops \\daws-76s\\repos \\terraform>set TF_VAR_instance_type=t3. xlarge
    C: \\devops\\daws-76s \\repos\\terraform>cd variables
    C: \\devops\\daws-76s\\repos\\terraform\\variables>terraform plan

[^31]: C: \\devops\\daws-76s\\repos \\terraform\\variables>terraform plan -var-file="roboshop. tfvars" -var="instance_type=t3. medium

[^32]: terraform > variables > variables.tf > ..
    1
    # 1. command line
    2
    # 2. -var-file
    3
    # 3. terraform . tfvars
    14
    # 4. ENV variables

[^33]: EXPLORER
    . .
    provider.tf .\\conditions U X provider.tf . \\variables
    V REPOS
    terraform > conditions > provider.tf > ...
    > Ansible
    1
    terraform {
    > Concepts
    required_providers {
    3
    > notes
    aws = {
    4
    source = "hashicorp/aws"
    > Robosho-shellscripts
    M
    5
    version = "5.49.0" #AWS provider version, not terraform version
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    7
    > shellscripts
    18
    terraform
    9
    conditions
    10
    provider "aws" {
    11
    provider.tf
    region = "us-east-1"
    U
    12
    > session1 \\ EC2
    13
    > variables
    .gitignore

[^34]: REPOS
    terraform > conditions > conditions.tf > 4% resource "aws_instance" "web"
    > Ansible
    1
    resource . "aws_instance" "web" . {
    > Concepts
    2
    ami .
    . . = . var . ami_id .#devops-practice
    3
    > notes
    instance_type = var . instance_name == "MongoDB" ? "t3. small" : "t2.micro"
    4
    > Robosho-shellscripts
    M
    5
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    terraform
    conditions
    conditions.tf
    U

[^35]: terraform > conditions > variables.tf > < variable "ami_id"
    1
    variable "instance_name" {
    12
    type = string
    3
    default = "MongoDB"
    4
    15
    6
    variable "ami_id" {
    7
    type = string
    18
    default = "ami-Of3c7d07486cad139"
    9

[^36]: PS E: \\AWSDevops\\Repos \\terraform> cd . \\conditions\\
    PS E: \\AWSDevops\\Repos \\terraform\\conditions> terraform init
    Initializing the backend. ..
    Initializing provider plugins. ..
    Finding hashicorp/aws versions matching "5.49.0"...
    Installing hashicorp/aws v5. 49.0...
    Installed hashicorp/aws v5. 49.0 (signed by HashiCorp)
    Terraform has created a lock file . terraform. lock.hcl to record the provider
    selections it made above. Include this file in your version control repository
    so that Terraform can guarantee to make the same selections by default when
    you run "terraform init" in the future.
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. All Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    PS E: \\AWSDevops\\Repos \\terraform\\conditions>

[^37]: PS E: \\AWSDevOps \\Repos \\terraform\\conditions> terraform plan
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance.web will be created
    + resource "aws_instance" "web" {
    - ami
    "ami-Of3c7d07486cad139"
    + arn
    = (known after apply)
    + associate_public_ip_address
    = (known after apply)
    + availability_zone
    =
    (known after apply)
    + cpu_core_count
    (known after apply)
    + cpu_threads_per_core
    E
    (known after apply)
    disable_api_stop
    = (known after apply)
    + disable_api_termination
    = (known after apply)
    + ebs_optimized
    = (known after apply)
    + get_password_data
    = false
    + host id
    = (known after apply)
    host_resource_group_arn
    = (known after apply)
    + iam_instance_profile
    = (known after apply)
    id
    = (known after apply)
    + instance_initiated_shutdown_behavior = (known after apply)
    + instance_lifecycle
    = (known after apply)
    + instance_state
    = (known after apply)
    instance_type
    "t3. small"
    + ipv6_address_count
    (known after apply)
    + ipv6_addresses
    E
    (known after apply)

[^38]: V REPOS
    terraform > conditions > variables.tf > 1 variable "instance_name" > . default
    > Ansible
    1
    variable "instance_name" {
    > Concepts
    2
    type = string
    3
    default = "web"
    > notes
    4
    > Robosho-shellscripts
    M
    15
    > roboshop-ansible
    6
    variable "ami_id" {
    > roboshop-ansible-roles
    7
    type = string
    > shellscripts
    18
    default = "ami-Of3c7d07486cad139"
    terraform
    9
    conditions
    > .terraform
    E .terraform.lock.hcl
    U
    conditions.tf
    U
    provider.tf
    U
    variables.tf
    U

[^39]: PS E: \\AWSDevops\\Repos \\terraform\\conditions> terraform plan
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance.web will be created
    + resource "aws_instance" "web" {
    + ami
    =
    "ami -Of3c7d07486cad139"
    +
    arn
    = (known after apply)
    + associate_public_ip_address
    = (known after apply)
    availability_zone
    = (known after apply)
    + cpu_core_count
    = (known after apply)
    + cpu_threads_per_core
    = (known after apply)
    + disable_api_stop
    = (known after apply)
    +
    disable_api_termination
    = (known after apply)
    +
    ebs_optimized
    = (known after apply)
    + get_password_data
    = false
    + host_id
    = (known after apply)
    + host_resource_group_arn
    = (known after apply)
    + iam_instance_profile
    = (known after apply)
    + id
    = (known after apply)
    + instance_initiated_shutdown_behavior = (known after apply)
    + instance_lifecycle
    = (known after apply)
    + instance_state
    (known after apply)
    + instance_type
    = "t2.micro"
    + ipv6_address_count
    = (known after apply)

[^40]: V REPOS
    terraform > count > provider.tf > $8 provider "aws"
    > Ansible
    1
    terraform {
    > Concepts
    2
    required_providers {
    3
    > notes
    aws = {
    4
    > Robosho-shellscripts
    source = "hashicorp/aws"
    M
    5
    version = "5.49.0" #AWS provider version, not terraform version
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    7
    > shellscripts
    8
    terraform
    9
    > conditions
    10
    provider "aws" {
    11
    region = "us-east-1"
    count
    12
    provider.tf
    U
    > session1
    > variables
    .gitignore

[^41]: REPOS
    terraform > variables > output.tf > $ output "private_ip"
    > Ansible
    1
    # output "instance_info" {
    > Concepts
    2
    #
    value = aws_instance . web
    3
    #
    > notes
    4
    > Robosho-shellscripts
    M
    5
    output "instance_id" {
    > roboshop-ansible
    6
    value = aws_instance . web. id
    > roboshop-ansible-roles
    7
    > shellscripts
    18
    terraform
    9
    output "public_ip" {
    > conditions
    10
    value = aws_instance . web . public_ip
    11
    }
    count
    12
    count.tf
    U
    13
    output "private_ip" {
    provider.tf
    U
    14
    value = aws_instance . web . private_ip
    variables.tf
    C
    15
    > session1
    variables
    > .terraform
    E .terraform.lock.hcl
    ec2.tf
    M
    output.tf
    -
    U
    provider.tf

[^42]: PS E: \\AWSDevops\\Repos \\terraform\\variables> terraform apply -auto-approve
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance.web will be created
    + resource "aws_instance" "web" {
    + ami
    = "ami -Of3c7d07486cad139"
    arn
    = (known after apply)

[^43]: Apply complete! Resources: 2 added, 0 changed, 0 destroyed.
    Outputs :
    instance id = "i-00af112b562918f85"
    private_ip = "172.31.28.182"
    public_ip = "3.92.1.30"
    PS E: \\AWSDevOps\\Repos \\terraform\\variables>

[^44]: REPOS
    terraform > count > count.tf > ...
    > Ansible
    1
    resource "aws_instance" "web" {
    > Concepts
    #count = 11 # count. index is a special variable given by terraform
    W N
    > notes
    count = length(var . instance_names)
    4
    ami
    = var . ami_id #devops-practice
    > Robosho-shellscripts
    M
    5
    instance_type = var . instance_names \[count . index\] == "mongodb" \| \| var . instance_names \[count. index\] == "mysql" \| \| var . instance_names
    > roboshop-ansible
    \[ count . index\] == "shipping" ? "t3. small" : "t2.micro"
    > roboshop-ansible-roles
    6
    tags = {
    > shellscripts
    7
    Name = var . instance_names \[ count . index \]
    terraform
    8
    }
    9
    > conditions
    10
    count
    11
    # resource "aws_route53_record" "www" {
    count.tf
    U
    12
    #
    #count = 11
    output.tf
    U
    13
    #
    count = length (var . instance_names)
    provider.tf
    U
    14
    #
    zone_id = var . zone_id
    variables.tf
    U
    15
    #
    name
    "${var . instance_names \[ count . index \]} . ${var . domain_name}" #interpolation
    > session1
    O
    16
    #
    type
    = "A"
    17
    #
    > variables
    tt1
    18
    #
    records = \[var . instance_names \[count . index\] == "web" ? aws_instance . web \[count . index\] . public_ip : aws_instance . web \[count . index\].
    .gitignore
    private_ip\]
    6T
    #

[^45]: V REPOS
    terraform > count > output.of > $ output "instances_info"
    > Ansible
    1
    output "instances_info" {
    > Concepts
    2
    value = aws_instance . web
    3
    > notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    terraform
    > conditions
    count
    count.tf
    U
    output.tf
    U
    provider.tf
    C

[^46]: instance_metadata_tags" = "disabled"
    1)
    "monitoring" = false
    "network_interface" = toset(\[\])
    "outpost_arn" = ""
    "password_data" = "l
    "placement_group" = "I
    "placement_partition_number" = 0
    "primary_network_interface_id" = "eni-06bba963434a007e0"
    "private_dns" = "ip-172-31-17-132.ec2. internal"
    "private_dns_name_options" = tolist(\[
    "enable_resource_name_dns_a_record" = false
    "enable_resource_name_dns_aaaa_record" = false
    "hostname_type" = "ip-name"
    "private_ip" = "172. 31.17.132"
    "public_dns" = "ec2-18-212-229-220. compute-1. amazonaws . com"
    "public_ip" = "18.212.229.220"
    "root_block_device" = tolist(\[

[^47]: Instances (11) Info
    C
    Connect
    Instance state
    Actions
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Instance state = running
    X
    Clear filters
    Name _
    4
    Instance ID
    Instance state
    V
    Instance type
    4
    Status check
    Al
    redis
    i-02ad20cbd6a0d653a
    Running
    t2.micro
    2/2 checks passed Vie
    shipping
    i-07b4caaac604d38c9
    Running
    t3.small
    2/2 checks passed Vie
    dispatch
    i-018969ab9241c3791
    Running
    t2.micro
    2/2 checks passed Vie
    user
    i-07208f04f52ae3d8e
    Running
    t2.micro
    2/2 checks passed Vie
    rabbitmq
    i-006b7aa337813ed58
    Running
    t2.micro
    2/2 checks passed Vie
    cart
    i-02b5a 1ad88df96416
    Running
    t2.micro
    2/2 checks passed Vie
    catalogue
    i-Of3e3860c2f857beb
    Running
    t2.micro
    2/2 checks passed Vie
    payment
    i-01d60f20f8368d24e
    Running
    t2.micro
    2/2 checks passed Vie
    web
    i-026fcbdb69c50cf78
    Running
    t2.micro
    2/2 checks passed Vie
    mongodb
    i-0d424bf5a81472691
    Running
    t3.small
    2/2 checks passed Vi
    O
    mysql
    i-069e9be0878e729a1
    Running
    t3.small
    Initializing
    Vie

[^48]: terraform > count > count.tf > % resource "aws_route53_record" "www"
    1
    resource "aws_instance" "web" {
    2
    #count = 11 # count . index is a special variable given by terraform
    3
    count = length (var . instance_names )
    4
    ami
    = var . ami_id #devops-practice
    5
    instance_type = var . instance_names \[count. index\] == "mongodb" \| \| var . instance_names \[count . index\] == "mysql" \| \| var . instance_names
    \[ count . index\] == "shipping" ? "t3. small" : "t2.micro"
    6
    tags = {
    7
    Name = var . instance_names \[ count . index \]
    8
    9
    10
    11
    resource "aws_route53_record" "www" {
    12
    #count = 11
    13
    count = length (var . instance_names)
    14
    zone_id = var . zone_id
    15
    name
    = "${var . instance_names \[ count . index\]} . ${var . domain_name}" #interpolation
    16
    type
    "A"
    17
    tt1
    = 1
    18
    records = \[var . instance_names \[count . index\] == "web" ? aws_instance. web\[count . index\] . public_ip : aws_instance . web \[count . index\].
    private_ip\]
    19

[^49]: terraform > count > \\ variables.tf > ' variable "domain_name'
    1
    variable "instance_names" {
    2
    type = list
    3
    default = \["mongodb", "redis", "mysql", "rabbitmq", "catalogue", "user", "cart", "shipping", "payment", "dispatch", "web"\]
    4
    15
    6
    variable "ami_id" {
    7
    default = "ami-Of3c7d07486cad139"
    8
    19
    10
    variable "zone_id" {
    11
    default = "Z06431971951XUVZELNIC"
    12
    13
    14
    variable "domain_name" {
    15
    default = "chowdarychilukuri. in"
    16

[^50]: terraform > count > output.tf
    1
    #
    output "instances_info" {
    12
    #
    value = aws_instance . web
    3
    #

[^51]: PS E: \\AWSDevOps \\Repos \\terraform\\count> terraform apply -auto-approve
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance.web\[0\] will be created
    resource "aws_instance" "web" {
    ami
    = "ami-Of3c7d07486cad139"
    +
    arn
    = (known after apply)
    + associate_public_ip_address
    = (known after apply)
    + availability_zone
    = (known after apply)

[^52]: aws_route53_record.www\[0\]: Creation complete after 50s \[id=Z06431971951XUVZELNIC_mongodb. chowdarychilukuri . in_A\]
    Apply complete! Resources: 22 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevops \\Repos \\terraform\\count>

[^53]: Instances (23) Info
    C
    Connect
    Instance state
    Actions
    La
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Name _
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Alarm sta
    shipping
    i-0360968c40387 c062
    Running
    t3.small
    2/2 checks passed View alar
    redis
    i-02ad20cbd6a0d653a
    Terminated
    t2.micro
    View alar
    shipping
    i-07b4caaac604d38c9
    Terminated
    Q Q
    t3.small
    View alar
    dispatch
    i-018969ab9241c3791
    Terminated
    t2.micro
    View alari
    user
    i-07208f04f52ae3d8e
    Terminated
    t2.micro
    View alar
    rabbitmq
    i-006b7aa337813ed58
    Terminated
    t2.micro
    View alar
    cart
    i-0265a 1ad88df96416
    Terminated
    t2.micro
    View alarm
    catalogue
    i-Of3e3860c2f857beb
    Terminated
    t2.micro
    View alar
    user
    i-0724b23cd7fd1c97a
    Running
    t2.micro
    2/2 checks passed View alar
    mysql
    i-0a7d96921c985fb91
    Running
    t3.small
    2/2 checks passed View alar
    payment
    i-01d60f20f8368d24e
    Terminated
    t2.micro
    View alar
    web
    i-026fcbdb69c50cf78
    Terminated
    t2.micro
    View alar
    mongodb
    i-Od424bf5a81472691
    Terminated
    t3.small
    -
    View alar
    Select an instance

[^54]: Q Filter records by property or value
    Type
    Routing policy
    Alias
    0
    Record ... V Type
    Routin...
    4
    Differ...
    4
    Alias
    4
    Value/Route traffic to
    4
    TTL (S...
    ns-59.awsdns-07.com.
    ns-1889.awsdns-44.co.uk.
    0
    chowdary...
    NS
    Simple
    No
    172800
    ns-1039.awsdns-01.org.
    ns-836.awsdns-40.net.
    O
    chowdary...
    SOA
    Simple
    No
    ns-59.awsdns-07.com. awsdn...
    900
    cart.chow...
    A
    Simple
    No
    172.31.27.197
    1
    O
    catalogue....
    A
    Simple
    No
    172.31.29.106
    dispatch.c...
    A
    Simple
    No
    172.31.21.236
    mongodb....
    A
    Simple
    No
    172.31.20.166
    0
    mysql.cho...
    A
    Simple
    No
    172.31.18.241
    O
    payment....
    A
    Simple
    No
    172.31.24.16
    0
    rabbitmq....
    A
    Simple
    No
    172.31.18.169
    O
    redis.cho...
    A
    Simple
    No
    172.31.29.58
    0
    shipping.c...
    A
    Simple
    No
    172.31.16.235
    user.chow...
    A
    Simple
    No
    172.31.24.238
    web.chow...
    A
    Simple
    No
    3.95.201.149
    1

[^55]: C: \\devops \\daws-76s\\repos \\terraform\\variables>terraform console
    > max (5, 12, 9)
    12
    > min (1, 2, 3)
    1
    > join("-", \["foo", "bar", "baz"\])
    "foo-bar-baz"
    > lower ( "HELLO")
    "hello"
    > split(", " "foo, bar, baz")
    tolist(\[
    "foo "
    "bar"
    "baz"

[^56]: terraform > count > variables.tf > $ variable "domain_name"
    1
    variable "instance_names" {
    2
    type = list
    13
    default = \["mongodb", "redis", "mysql", "rabbitmq", "catalogue", "user", "cart", "shipping", "payment", "dispatch", "web"\]
    4
    15
    6
    variable "ami_id" {
    7
    default = "ami-Of3c7d07486cad139"
    8
    9
    10
    variable "zone_id" {
    11
    default = "Z06431971951XUVZELNIC"
    12
    13
    14
    variable "domain_name" {
    15
    default = "chowdarychilukuri . in"
    16

[^57]: terraform > count > count.tf > $ resource "aws_instance" "web"
    resource "aws_instance" "web" {
    #count = 11 # count . index is a special variable given by terraform
    3
    count = length (var . instance_names)
    4
    ami
    = var . ami_id #devops-practice
    5
    instance_type = var . instance_names \[count . index\] == "mongodb" \| \| var . instance_names \[count . index\] == "mysql" \| \| var . instance_names
    \[ count . index\] == "shipping" ? "t3. small" : "t2.micro"
    6
    tags = {
    7
    Name = var . instance_names \[ count . index\]
    8
    9
    10
    11
    resource "aws_route53_record" "www" {
    12
    #count = 11
    13
    count = length(var . instance_names )
    14
    zone_id = var . zone_id
    15
    name
    = "${var . instance_names \[count . index\]} . ${var . domain_name}" #interpolation
    16
    type
    =
    "A"
    17
    tt1
    = 1
    18
    records = \[var . instance_names \[count . index\] == "web" ? aws_instance. web\[count . index\] . public_ip : aws_instance . web\[count . index\].
    private_ip \]
    19
    }

[^58]: EXPLORER
    count.tf ..\\locals U
    variables.tf .\\locals U
    locals.tf U X
    count.tf .. \\count U
    Untitled-2 . 4.
    REPOS
    terraform > locals > locals.tf > 4: locals > \[e\] ip
    notes
    1
    locals {
    > roboshop-ansible
    2
    name = "sivakumar"
    3
    > roboshop-ansible-roles
    training = "terraform"
    4
    > roboshop-documentation
    instance_type = var . instance_names \[count . index\] == "mongodb" \| \| var . instance_names
    \[ count . index\] == "mysql" \| \| var . instance_names \[count . index\] == "shipping" ? "t3. small"
    > roboshop-shell
    "t2. micro"
    > shell-script
    5
    ip = var . instance_names \[ count . index\] == "web" ? aws_instance. web\[count . index\] . public_ip
    terraform
    : aws_instance . web\[ count . index\] . private_ip
    > conditions
    6
    > count
    locals
    count.tf
    U
    locals.tf
    U

[^59]: REPOS
    terraform > locals > count.tf > { resource "aws_route53_record" "www" > \[ \]records
    > notes
    1
    resource "aws_instance" "web" {
    > roboshop-ansible
    2
    #count = 11 # count . index is a special variable given by terraform
    > roboshop-ansible-roles
    3
    count = length (var . instance_names)
    4
    ami
    = var . ami_id #devops-practice
    > roboshop-documentation
    5
    instance_type = local. instance_type
    > roboshop-shell
    6
    tags = {
    > shell-script
    7
    Name = var . instance_names \[ count . index \]
    terraform
    8
    > conditions
    9
    > count
    10
    11
    locals
    resource "aws_route53_record" "www" {
    12
    #count = 11
    count.tf
    U
    13
    count = length(var . instance_names)
    locals.tf
    U
    14
    zone id = var . zone_id
    provider.tf
    U
    15
    name
    = "${var . instance_names \[ count . index\]} . ${var . domain_name}" #interpolation
    variables.tf
    U
    16
    type
    = "A"
    session-01
    17
    tt1
    1
    > variables
    18
    O
    records = \[local. ipj
    19
    .gitignore
    U

[^60]: terraform > locals > variables.tf > < variable "domain_name"
    1
    variable "instance_names" {
    2
    type = list
    3
    default = \["mongodb", "redis", "mysql", "rabbitmq", "catalogue", "user", "cart", "shipping", "payment", "dispatch", "web"\]
    4
    5
    16
    variable "ami_id" {
    7
    default = "ami-Of3c7d07486cad139"
    8
    9
    10
    variable "zone_id" {
    11
    default = "Z06431971951XUVZELNIC"
    12
    13
    14
    variable "domain_name" {
    15
    default = "chowdarychilukuri. in"
    16
    }

[^61]: # aws_route53_record .www \[10\] will be created
    resource "aws_route53_record" "www" {
    +
    allow_overwrite = (known after apply)
    +
    fadn
    (known after apply)
    +
    id
    E
    (known after apply)
    +
    name
    "web . daws 76s . online"
    +
    records
    (known after apply)
    +
    tt1
    1
    +
    type
    A"
    +
    zone_id
    "Z104317737D96UJVA7NEF"
    Plan: 22 to add, 0 to change, 0 to destroy

