---
title: 27Day_Terraform
uuid: 37c06422-1337-11ef-bbb0-c6370cefecaf
version: 666
created: '2024-05-16T09:18:54+05:30'
tags:
  - terraform
---

\

***Topics:***

1. *<mark style="background-color:#f8d616;">Locals<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Data-sources - IMP in terraform<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Loops<!-- {"backgroundCycleColor":"25"} --></mark>*

    1. *for each loop -  - <mark style="background-color:#f8914d;">useful to iterate maps<!-- {"backgroundCycleColor":"24"} --></mark>*

    1. *Dynamic block*

1. *<mark style="background-color:#f8d616;">Terraform state & remote state<!-- {"backgroundCycleColor":"25"} --></mark>- <mark style="background-color:#f8914d;">An IMP concept<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"offset":3} -->

\

\

# *<mark style="background-color:#f8914d;">**Locals**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*Locals is just like variables, but it have some extra capabilities. you can keep functions and expressions inside locals and use them.*

\

![238e5293-ea76-46aa-86c4-c037bb273903.png|580](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/238e5293-ea76-46aa-86c4-c037bb273903.png) [^1]

![9c7b4642-72ae-4450-b5a6-1892a4b66853.png|566](https://images.amplenote.com/3d5f36c2-11b8-11ef-af96-9a665e06d35f/9c7b4642-72ae-4450-b5a6-1892a4b66853.png) [^2]

\

*provider.tf code:*

![0d994dc7-93b4-445e-9414-c4e076673368.png|886](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/0d994dc7-93b4-445e-9414-c4e076673368.png) [^3]

\

```
terraform init
```

![f3783a07-2b26-41a4-9acb-4f0248f8cbca.png|716](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/f3783a07-2b26-41a4-9acb-4f0248f8cbca.png) [^4]

\

*local.tf code:*

![f3a08a24-e9d5-48a4-9460-dd2eb0b26813.png|892](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/f3a08a24-e9d5-48a4-9460-dd2eb0b26813.png) [^5]

\

*count.tf code:*

![cf207c54-384d-4bd8-83e9-176423b9cc92.png|886](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/cf207c54-384d-4bd8-83e9-176423b9cc92.png) [^6]

\

*variables.tf code  -- <mark style="background-color:#f3de6c;">If you change true to false or false to true it will change instance type t3.small or t2.micro<!-- {"backgroundCycleColor":"14"} --></mark>*

![a46aa980-bc28-4004-ae7e-b8fcd0447fdb.png|868](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/a46aa980-bc28-4004-ae7e-b8fcd0447fdb.png) [^7]

\

```
terraform plan
```

![cec93a81-5671-456f-a28c-7b97bd2577d4.png|903.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/cec93a81-5671-456f-a28c-7b97bd2577d4.png) [^8]

\

\

# *<mark style="background-color:#f8914d;">**Data-sources**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*It is useful to query the data dynamically from providers.*

\

*Ex. some patches released and applied for an AMI instance, so we can query by using data sources and get the latest changes.*

![0bf01cef-c349-4e6c-9a10-05ecebcc3dd8.png|661.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/0bf01cef-c349-4e6c-9a10-05ecebcc3dd8.png) [^9]

\

*providers.tf code*

![5e4d4f0e-f470-448f-9d05-098979353ec1.png|845.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/5e4d4f0e-f470-448f-9d05-098979353ec1.png) [^10]

\

```
terraform init
```

![ef96b5e0-d924-4da7-beef-f2bb5e537eb1.png|623](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/ef96b5e0-d924-4da7-beef-f2bb5e537eb1.png) [^11]

\

*data.tf code  --To get dynamic information from that AMI*

![f27244ec-affa-4ebf-b40a-92a6185636a6.png|580](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/f27244ec-affa-4ebf-b40a-92a6185636a6.png) [^12]

\

*outputs.tf code*

![7aec7cf5-c910-423c-8d74-2e74c0739ad8.png|743](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/7aec7cf5-c910-423c-8d74-2e74c0739ad8.png) [^13]

\

*ami id pulled*

```
terraform plan
```

![acb91dc3-5957-47c6-aca3-d0651a1daefd.png|743](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/acb91dc3-5957-47c6-aca3-d0651a1daefd.png) [^14]

\

*ec2.tf   -- it will help to pull ami id dynamically from data.tf and will create ec2 instance.*

![d5325982-efae-4849-aa00-b6e5ca4382be.png|821](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/d5325982-efae-4849-aa00-b6e5ca4382be.png) [^15]

\

```
terraform apply -auto-approve
```

\

![deeb6848-aafa-4b59-8f4f-5850aafafe8b.png|816](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/deeb6848-aafa-4b59-8f4f-5850aafafe8b.png) [^16]

![4af060a8-fd8b-40d6-abd9-e7d8f251468c.png|744](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/4af060a8-fd8b-40d6-abd9-e7d8f251468c.png) [^17]*\]*

\

*Resource created:*

![6bde6548-c6c4-496f-9a8d-0c9892c55db5.png|943.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/6bde6548-c6c4-496f-9a8d-0c9892c55db5.png) [^18]

\

*Now i want to fetch VPC details from below*

![c06683e0-48fe-4f5c-b15d-7165505302b1.png|941.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/c06683e0-48fe-4f5c-b15d-7165505302b1.png) [^19]

\

*updated in data.tf code*

![a73927fb-a6aa-4d41-9d73-f7895069a23a.png|796](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/a73927fb-a6aa-4d41-9d73-f7895069a23a.png) [^20]

\

\

*updated in output.tf code*

![](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/60e0115c-50cb-4d19-b894-bda542623ae2.png) [^21]

\

*It will pull all VPC details from our aws account*

```
terraform plan
```

![ec6653f8-d567-446b-a74e-3f4fbe29e1a9.png|888.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/ec6653f8-d567-446b-a74e-3f4fbe29e1a9.png) [^22]

\

\

\

# *<mark style="background-color:#f8914d;">**For each loop :**<!-- {"backgroundCycleColor":"24"} --></mark>  - <mark style="background-color:#f8914d;">useful to iterate maps<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*providers.tf*

![8338557d-6735-437f-b2dc-e158f2d9714c.png|967.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/8338557d-6735-437f-b2dc-e158f2d9714c.png) [^23]

\

```
terraform init
```

![965e686b-65b1-4515-b09e-27fef1f1fdd3.png|676](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/965e686b-65b1-4515-b09e-27fef1f1fdd3.png) [^24]

\

*each.tf code*

![1187a9e5-8429-4e4f-91d0-74fcb5d8695f.png|820.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/1187a9e5-8429-4e4f-91d0-74fcb5d8695f.png) [^25]

\

*variables.tf code  --> <mark style="background-color:#f3de6c;">each.value here is - t3.small<!-- {"backgroundCycleColor":"14"} --></mark>     <mark style="background-color:#bbe077;">each.key here is - mongodb  for above each.tf code<!-- {"backgroundCycleColor":"15"} --></mark>*

![e8eecb9a-660a-4042-8415-d60f44662157.png|831](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/e8eecb9a-660a-4042-8415-d60f44662157.png) [^26]

\

```
terraform plan
```

![2ebc33dd-a807-4593-b8ee-1c058afc96f8.png|966.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/2ebc33dd-a807-4593-b8ee-1c058afc96f8.png) [^27]

\

```
terraform apply -auto-approve
```

\

![21baa124-ae86-4c69-844e-6262d1711fb7.png|1070.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/21baa124-ae86-4c69-844e-6262d1711fb7.png) [^28]

\

*instances created now*

![eedea928-66eb-4044-8031-fdb1324d4805.png|923.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/eedea928-66eb-4044-8031-fdb1324d4805.png) [^29]

\

*Route53 records also created:*

![7cc3db42-b15e-45ba-80ef-3cc00557953d.png|955.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/7cc3db42-b15e-45ba-80ef-3cc00557953d.png) [^30]

```
terraform destroy -auto-approve
```

![5b4112e6-17fb-4229-8821-39bd80585a7c.png|858](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/5b4112e6-17fb-4229-8821-39bd80585a7c.png) [^31]

\

\

\

# *<mark style="background-color:#f8914d;">**Dynamic block(loop)-** not much use only for understanding<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

\

*provider.tf code*

![d2e00f39-6951-475e-a636-15a5d0f1629b.png|1021.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/d2e00f39-6951-475e-a636-15a5d0f1629b.png) [^32]

\

```
cd dynamic
```

```
terraform init
```

![1c8b750b-c7fe-4192-960e-2304f6107232.png|593](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/1c8b750b-c7fe-4192-960e-2304f6107232.png) [^33]

\

*sg.tf code -- repeated values kept in variables.tf*

![f3802fb2-de01-4410-8041-2caeaa57fe02.png|613](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/f3802fb2-de01-4410-8041-2caeaa57fe02.png) [^34]

\

*variables.tf code*

![58a0719b-95a9-4e0c-b72f-244fefacfec4.png|584](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/58a0719b-95a9-4e0c-b72f-244fefacfec4.png) [^35]

\

```
terraform apply -auto-approve
```

![8bb211d3-8979-4cf4-bf16-a7c49cb6cf87.png|711](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/8bb211d3-8979-4cf4-bf16-a7c49cb6cf87.png) [^36]

\

![7223b4c8-0788-4ced-baf5-07ccdcc2b790.png|836.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/7223b4c8-0788-4ced-baf5-07ccdcc2b790.png) [^37]

\

\

\

\

# *<mark style="background-color:#f8914d;">**Terraform state & remote state**<!-- {"backgroundCycleColor":"24"} --></mark>**- <mark style="background-color:#f3de6c;">An IMP concept<!-- {"backgroundCycleColor":"14"} --></mark>***<!-- {"collapsed":true} -->

\

*<mark style="background-color:#f8914d;">**State:**<!-- {"backgroundCycleColor":"24"} --></mark>*

*whatever we write it should create and its a  <mark style="background-color:#f3de6c;">declarative<!-- {"backgroundCycleColor":"14"} --></mark>*

*declarative is nothing but its our desired state*

\

*current state = terraform.tfstate*

\

*Terraform ultimate goal & responsibility is desired state = current state*

\

![46e48652-0489-4cfb-a626-9d724390775a.png|883.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/46e48652-0489-4cfb-a626-9d724390775a.png) [^38]

\

*Terraform will check current state, if current state is equal to desired state then it will not take any action ...*

```
terraform apply -auto-approve
```

![06ea10a1-3fdc-4185-a9be-8af3740cca8b.png|945.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/06ea10a1-3fdc-4185-a9be-8af3740cca8b.png) [^39]

\

*Now made some changes in code & you want to add other ports to SG.*

![16b559a3-682a-4848-a85b-be349a6b97e6.png|854](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/16b559a3-682a-4848-a85b-be349a6b97e6.png) [^40]

\

```
terraform plan
```

![d178a05a-f2fa-4974-9bb9-7555dc067b63.png|916.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/d178a05a-f2fa-4974-9bb9-7555dc067b63.png) [^41]

\

```
terraform apply -auto-approve
```

![e369cae0-9d39-431c-a808-1c1bf5f17549.png|932.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/e369cae0-9d39-431c-a808-1c1bf5f17549.png) [^42]

\

*Port 3306 added to SG*

![b693b2c9-c258-45e3-9218-38317f6ac708.png|838.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/b693b2c9-c258-45e3-9218-38317f6ac708.png) [^43]

\

\

*If someone deleted SG group & if we try to create from terraform first it will check weather its present or not if present doesn't create... if not present(where accidentally deleted by user) terraform will compare and creates SG.*

\

```
terraform destroy -auto-approve
```

![e5dc3198-caf1-4895-8293-0274538d6ded.png|676](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/e5dc3198-caf1-4895-8293-0274538d6ded.png) [^44]

\

\

*<mark style="background-color:#f8914d;">**Remote state**<!-- {"backgroundCycleColor":"24"} --></mark>*

\

*If devops engineer2 copied all the code from devops engineer1 and try to execute the same code then generally it will fail it shows already present & errors or creates duplicates .*

\

*devops-1 and devops-2*

*both are running terraform apply at same time then duplicate may come.*

\

***Terraform.tfstate** should not be placed in local laptops.*

\

*we need to a central state file to check the infra exists or not ...*

***1. collaboration***

       *Terraform will have no idea about the infra created, if multiple persons are working on same infra, it will try to create duplicates and errors may also come*

***2. security***

       ***terraform.tfstate** is a crucial, if you keep it in local it may be deleted or updated by mistake.*

\

*We need to place **terraform.tfstate** file in S3 bucket(we can use other options other than S3 bucket like azure, GCP, etc) so that when both devops engineers try to apply then it will compare from S3 tfstate file.*

![56819354-4de8-404b-965f-1ff557e9666f.png|695](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/56819354-4de8-404b-965f-1ff557e9666f.png) [^45]

\

*Now creating S3 bucket - **chilops-terraform-remotestate***

\

![3c1e4d09-f74a-493c-926d-1fad9a12173e.png|848.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/3c1e4d09-f74a-493c-926d-1fad9a12173e.png) [^46]

\

![bcbdf529-85ca-494d-af81-e19b0e597ead.png|879.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/bcbdf529-85ca-494d-af81-e19b0e597ead.png) [^47]

\

*Now we need created table in DynamoDB to lock S3 bucket. -- **chilops-locking***

\

![85dd7430-306e-4e6b-ab40-18857225ec2a.png|861.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/85dd7430-306e-4e6b-ab40-18857225ec2a.png) [^48]

![c9d46c75-ea0c-49e7-928a-a77b625809b1.png|974.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/c9d46c75-ea0c-49e7-928a-a77b625809b1.png) [^49]

\

*Now update the code in provider.tf* 

\

```
backend "s3" {
    bucket = "chilops-terraform-remotestate"    #bucket name
    key    = "dynamic"                          #any thing can be given here
    region = "us-east-1"                        #specify the region
    dynamodb_table = "chilops-locking"          #Dynamodb locking table name
```

\

![17c00927-e785-4001-a263-17bb6e7d03ea.png|1011.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/17c00927-e785-4001-a263-17bb6e7d03ea.png) [^50]

\

```
terraform plan
```

![9bbafeb1-b6d9-4c7d-bf05-f4e7a14820d0.png|764](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/9bbafeb1-b6d9-4c7d-bf05-f4e7a14820d0.png) [^51]

\

```
terraform init -reconfigure
```

![3ff8286b-68b7-4459-afb3-2f793e1b3842.png|802](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/3ff8286b-68b7-4459-afb3-2f793e1b3842.png) [^52]

\

\

```
terraform apply -auto-approve
```

![567ef386-3e64-47c1-bea3-2f6e0d30bc1e.png|1094.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/567ef386-3e64-47c1-bea3-2f6e0d30bc1e.png) [^53]

\

*To check if its locking in AWS - Dynamodb*

![84af0b37-4274-47b7-95c0-9460f260358f.png|851.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/84af0b37-4274-47b7-95c0-9460f260358f.png) [^54]

\

![d42f018b-7668-4612-8f63-e8a6ebe9aff0.png|933.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/d42f018b-7668-4612-8f63-e8a6ebe9aff0.png) [^55]

\

*After execution completed it will create a file in S3: this file will have full information about **terraform.tfstate***

![6a81797f-e292-453b-b01e-e93fede59b48.png|942.3333740234375](https://images.amplenote.com/37c06422-1337-11ef-bbb0-c6370cefecaf/6a81797f-e292-453b-b01e-e93fede59b48.png) [^56]

[^1]: Local Values
    v1.6.x (latest) V
    Hands-on: Try the Simplify Terraform Configuration with Locals tutorial.
    A local value assigns a name to an expression, so you can use the name multiple times within a
    module instead of repeating the expression.
    If you're familiar with traditional programming languages, it can be useful to compare Terraform
    modules to function definitions:
    . Input variables are like function arguments.
    . Output values are like function return values.
    . Local values are like a function's temporary local variables.

[^2]: When To Use Local Values
    Local values can be helpful to avoid repeating the same values or expressions multiple times in a
    configuration, but if overused they can also make a configuration hard to read by future
    maintainers by hiding the actual values used
    Use local values only in moderation, in situations where a single value or result is used in many
    places and that value is likely to be changed in future. The ability to easily change the value in a
    central place is the key advantage of local values.

[^3]: EXPLORER
    provider.tf .\\locals X
    count.tf .\\count
    count.tf ..\\locals M
    ec2.tf
    REPOS
    terraform > locals > provider.tf > > provider "aws"
    > Ansible
    1
    terraform {
    > Concepts
    2
    required_providers {
    3
    > notes
    aws = {
    14
    source = "hashicorp/aws"
    > Robosho-shellscripts
    M
    15
    version = "5.49.0" #AWS provider version, not terraform version
    > roboshop-ansible
    16
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
    locals
    > .terraform
    E .terraform.lock.hcl
    count.tf
    M
    locals.tf
    M
    provider.tf

[^4]: PS E: \\AWSDevops \\Repos \\terraform\\locals> terraform init
    Initializing the backend. ..
    Initializing provider plugins...
    Reusing previous version of hashicorp/aws from the dependency lock file
    Using previously-installed hashicorp/aws v5.49.0
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. All Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    PS E: \\AWSDevops \\Repos \\terraform\\locals>

[^5]: EXPLORER
    nt
    count.tf .\\locals M
    ec2.tf
    locals.tf M X
    output.tf .. \\variable
    V REPOS
    terraform > locals > locals.tf > % locals
    > Ansible
    1
    locals {
    > Concepts
    N
    name = "sivakumar"
    3
    notes
    training = "terraform"
    4
    instance_type = var . isProd ? "t3. small" : "t2.micro"
    > Robosho-shellscripts
    M
    5
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    terraform
    > conditions
    > count
    locals
    > .terraform
    E .terraform.lock.hcl
    count.tf
    M
    locals.tf
    M
    provider.tf
    variables.tf
    M
    > session1
    > variables
    .gitignore

[^6]: REPOS
    terraform > locals > count.tf > ...
    > Ansible
    1
    resource "aws_instance" "web" {
    > Concepts
    2
    ami
    = var . ami_id #devops-practice
    3
    > notes
    instance_type = local . instance_type
    14
    tags = {
    > Robosho-shellscripts
    M
    5
    Name = "locals"
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    > shellscripts
    terraform
    9
    > conditions
    > count
    v locals
    > .terraform
    E .terraform.lock.hcl
    count.tf
    M
    locals.tf
    M
    provider.tf
    variables.tf
    M

[^7]: V REPOS
    terraform > locals > variables.tf > ...
    > Ansible
    variable "isProd" {
    > Concepts
    12
    type = bool
    13
    > notes
    default = false
    4
    > Robosho-shellscripts
    M
    5
    > roboshop-ansible
    16
    variable "ami_id" {
    > roboshop-ansible-roles
    17
    default = "ami-Of3c7d07486cad139"
    > shellscripts
    18
    terraform
    9
    > conditions
    10
    variable "zone_id" {
    11
    default = "Z06431971951XUVZELNIC"
    > count
    12
    locals
    13
    > .terraform
    14
    variable "domain_name" {
    E .terraform.lock.hel
    15
    default = "chowdarychilukuri.in"
    count.tf
    M
    16
    locals.tf
    M
    provider.tf
    variables.tf
    M
    > session1

[^8]: PS E: \\AWSDevOps \\Repos \\terraform\\locals> terraform plan
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_instance.web will be created
    + resource "aws_instance" "web" {
    + ami
    "ami -Of3c7d07486cad139"
    +
    arn
    (known after apply)
    associate_public_ip_address
    = (known after apply)
    + availability_zone
    = (known after apply)
    +
    cpu_core_count
    = (known after apply)
    +
    cpu_threads_per_core
    = (known after apply)
    disable_api_stop
    = (known after apply)
    disable_api_termination
    = (known after apply)
    + ebs_optimized
    = (known after apply)
    get_password_data
    = false
    + host_id
    = (known after apply)
    host_resource_group_arn
    = (known after apply)
    iam_instance_profile
    = (known after apply)
    id
    = (known after apply)
    instance_initiated_shutdown_behavior = (known after apply)
    instance_lifecycle
    = (known after apply)
    + instance_state
    = (known after apply)
    instance_type
    "t2.micro"
    + ipv6_address_count
    (known after apply)

[^9]: EC2
    Route 53
    8- IAM
    EC2 Dashboard
    X
    Amazon Machine Images (AMIs) (1/2) Info
    G
    \[ Recycle Bin
    \[ EC2 Image Bui
    EC2 Global View
    Public images
    Q Search
    Events
    devops-practice
    X
    Clear filters
    Console-to-Code Preview
    -
    Name _
    AMI name
    AMI ID
    Source
    Instances
    RHEL-9-DevOps-Practice
    ami-090252cbe067age58
    9737144768
    Instances
    Centos-8-DevOps-Practice
    ami-Of3c7d07486cad139
    9737144768
    Instance Types
    Launch Templates
    Spot Requests
    Savings Plans
    Reserved Instances
    Dedicated Hosts
    Capacity
    Reservations New
    AMI ID: ami-Of3c7d07486cad 139
    Images
    Details
    Storage
    Tags
    AMIs
    AMI ID
    Image type
    Platform details

[^10]: REPOS
    terraform > data-sources > provider.tf > % provider "aws"
    > Ansible
    1
    terraform {
    > Concepts
    2
    required_providers {
    3
    > notes
    aws = {
    14
    source = "hashicorp/aws"
    > Robosho-shellscripts
    M
    5
    version = "5.49.0"
    #AWS provider version, not terraform version
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    7
    > shellscripts
    8
    v terraform
    9
    > conditions
    provider "aws" {
    11
    region = "us-east-1"
    > count
    12
    data-sources
    data.tf
    C C
    outputs.tf
    provider.tf
    U
    > locals

[^11]: PS E: \\AWSDevOps \\Repos \\terraform\\data-sources> terraform init
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
    PS E: \\AWSDevops \\Repos \\terraform\\data-sources>

[^12]: terraform > data-sources > data.tf > $ data "aws_ami" "aws-linux-2"
    1
    data "aws_ami" "centos8" {
    2
    owners = \["973714476881"\]
    3
    most_recent
    = true
    4
    15
    filter {
    6
    name
    = "name"
    values = \["Centos-8-Devops-Practice" \]
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
    = "virtualization-type"
    17
    values = \["hvm" \]
    18
    19
    20
    21
    data "aws_ami" "aws-linux-2" {
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
    = "root-device-type"
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
    39

[^13]: REPOS
    terraform > data-sources > outputs.tf > ...
    > Ansible
    1
    output "ami_id" {
    > Concepts
    2
    value = data. aws_ami . centos8.id
    3
    > notes
    4
    > Robosho-shellscripts
    M
    5
    output "aws_ami_id" {
    > roboshop-ansible
    6
    value = data . aws_ami . aws-linux-2. id
    > roboshop-ansible-roles
    7
    > shellscripts
    8
    terraform
    > conditions
    > count
    data-sources
    > .terraform
    E .terraform.lock.hcl
    data.tf
    U
    outputs.tf
    U
    provider.tf
    > locals

[^14]: PS E: \\AWSDevOps \\Repos \\terraform\\data-sources> terraform plan
    data. aws_ami . aws-linux-2: Reading. . .
    data. aws_ami . centos8: Reading. . .
    data. aws_ami . centos8: Read complete after 1s \[id=ami-Of3c7d07486cad139\]
    data. aws_ami . aws-linux-2: Read complete after 2s \[id=ami-04ff98ccbfa41c9ad\]
    Changes to Outputs:
    ami_id
    = "ami-Of3c7d07486cad139"
    + aws_ami_id = "ami-04ff98ccbfa41c9ad"
    You can apply this plan to save these new output values to the Terraform state, witho

[^15]: V REPOS
    terraform > data-sources > ec2.tf > $ resource "aws_instance" "web"
    > Ansible
    1
    v resource "aws_instance" "web" {
    > Concepts
    12
    ami
    = data . aws_ami . centos8.id
    13
    > notes
    instance_type = "t2. small"
    14
    tags = {
    > Robosho-shellscripts
    M
    5
    Name = "data-source"
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    > shellscripts
    terraform
    > conditions
    > count
    data-sources
    > .terraform
    E .terraform.lock.hcl
    U
    data.tf
    U
    ec2.tf
    U
    outputs.tf
    U
    provider.tf
    U
    locals
    01

[^16]: Terraform will perform the following actions:
    # aws instance.web will be created
    resource "aws_instance" "web" {
    ami
    = "ami-Of3c7d07486cad139"
    +
    arn
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
    + disable_api_stop
    = (known after apply)
    + disable_api_termination
    = (known after apply)
    + ebs_optimized
    = (known after apply)
    + get_password_data
    = false
    + host id
    = (known after apply)
    + host_resource_group_arn
    = (known after apply)
    + iam_instance_profile
    = (known after apply)
    +
    id
    = (known after apply)
    + instance_initiated_shutdown_behavior = (known after apply)
    + instance_lifecycle
    = (known after apply)
    + instance_state
    = (known after apply)
    + instance_type
    "t2. small"
    + ipv6_address_count
    = (known after apply)
    +
    ipv6_addresses
    = (known after apply )

[^17]: Changes to Outputs:
    + ami id
    = "ami -Of3c7d07486cad139"
    + aws_ami_id = "ami-04ff98ccbfa41c9ad"
    aws_instance . web: Creating. . .
    aws_instance.web: Still creating... \[10s elapsed\]
    aws_instance.web: Still creating... \[20s elapsed\]
    aws instance.web: Still creating... \[30s elapsed\]
    aws_instance.web: Still creating... \[40s elapsed\]
    aws_instance. web: Creation complete after 48s \[id=i-07fe39826d23fb2ae\]
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
    Outputs :
    ami_id = "ami-Of3c7d07486cad139"
    aws_ami_id = "ami-04ff98ccbfa41c9ad"
    PS E: \\AWSDevOps \\Repos \\terraform\\data-sources>

[^18]: Instances (1) Info
    C
    Connect
    Instance state
    Actions
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Name
    4
    Instance ID
    Instance state
    4
    Instance type
    Status check
    data-source
    i-07fe39826d23fb2ae
    Running
    t2.small
    Initializing

[^19]: VPC > Your VPCs > vpc-0817cae898304c06
    vpc-0817cae8968304c06
    Actions
    Details Info
    VPC ID
    State
    DNS hostnames
    DNS resolution
    vpc-0817cae8968304c06
    Available
    Enabled
    Enabled
    Tenancy
    DHCP option set
    Main route table
    Main network ACL
    Default
    dopt-0b9994658cab2e8d2
    rtb-Obfe8282f6ae865ab
    acl-07f6298634a6c352c
    Default VPC
    IPV4 CIDR
    IPv6 pool
    IPV6 CIDR (Network border group)
    Yes
    172.31.0.0/16
    Network Address Usage metrics
    Route 53 Resolver DNS Firewall rule
    Owner ID
    Disabled
    groups
    7 158724841371
    Resource map
    CIDRS
    Flow logs
    Tags
    Integrations

[^20]: 41
    data-sources
    42
    data "aws_vpc" "default" {
    > .terraform
    43
    default = true
    E .terraform.lock.hcl
    U
    44
    data.tf
    -
    U
    ec2.tf
    U

[^21]: 8
    9
    output "vpc_info" {
    10
    value = data . aws_vpc . default
    11

[^22]: Changes to Outputs:
    + vpc_info
    + arn
    = "arn: aws : ec2:us-east-1: 158724841371: vpc/vpc-0817cae8968304c06"
    cidr_block
    = "172.31.0.0/16"
    + cidr_block_associations
    {
    + association_id = "vpc-cidr-assoc-020f17c6235167ffa"
    + cidr_block
    "172. 31.0.0/16"
    state
    = "associated"
    },
    default
    true
    dhcp_options_id
    = "dopt-069994b58cab2e8d2"
    enable_dns_hostnames
    = true
    enable_dns_support
    = true
    + enable_network_address_usage_metrics = false
    filter
    = null
    + id
    = "vpc-0817cae8968304c06"
    instance_tenancy
    = "default"
    ipv6_association_id
    + ipv6_cidr_block
    =
    + main_route_table_id
    = "rtb-0bfe8282f6ae865ab"
    + owner_id
    "158724841371"
    state
    = null
    + tags
    = {}
    timeouts
    = null
    You can apply this plan to save these new output values to the Terraform state, without changing any real infrastructure.
    Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run
    PS E: \\AWSDevops \\Repos \\terraform\\data-sources>

[^23]: REPOS
    terraform > foreachloops > provider.tf > % terraform
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
    > count
    12
    }
    > data-sources
    foreachloops
    foreach.tf
    U
    provider.tf
    U
    variables.tf
    U
    > locals
    > session1

[^24]: PS E: \\AWSDevops \\Repos \\terraform\\foreachloops> terraform init
    Initializing the backend. ..
    Initializing provider plugins. ..
    - Finding hashicorp/aws versions matching "5.49.0"...
    Installing hashicorp/aws v5.49.0...
    Installed hashicorp/aws v5.49.0 (signed by HashiCorp)
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

[^25]: REPOS
    terraform > foreachloops > foreach.tf > $ resource "aws_route53_record" "www"
    Ansible
    H
    resource "aws_instance" "web" {
    > Concepts
    2
    for_each = var . instance_names
    3
    > notes
    ami
    = var . ami_id #devops-practice
    4
    instance_type = each. value
    > Robosho-shellscripts
    M
    5
    tags = {
    > roboshop-ansible
    6
    Name = each . key
    > roboshop-ansible-roles
    7
    > shellscripts
    18
    terraform
    9
    > conditions
    10
    resource "aws_route53_record" "www" {
    11
    for_each = aws_instance . web
    > count
    12
    zone_id = var . zone_id
    > data-sources
    13
    name
    = "${each. key} . ${var . domain_name}" #interpolation
    foreachloops
    14
    type
    = "A"
    > .terraform
    15
    ttl
    = 1
    E .terraform.lock.hcl
    U
    16
    records = \[each. key == "web" ? each . value . public_ip : each . value . private_ip \]
    foreach.tf
    U
    17
    provider.tf
    U
    variables.tf
    U
    > locals

[^26]: EXPLORER
    . ..
    count.tf . \\locals
    ec2.tf . \\conditions
    locals.tf
    output.tf
    REPOS
    terraform > foreachloops > variables.tf > ...
    > Ansible
    1
    variable "instance_names" {
    > Concepts
    2
    type = map
    3
    > notes
    default = {
    4
    mongodb = "t3. small"
    > Robosho-shellscripts
    M
    5
    redis = "t2.micro"
    > roboshop-ansible
    6
    mysql = "t3. small"
    > roboshop-ansible-roles
    7
    rabbitmq = "t2.micro"
    > shellscripts
    8
    catalogue = "t2.micro"
    terraform
    9
    cart = "t2.micro"
    > conditions
    10
    user = "t2.micro"
    11
    > count
    shipping = "t3. small"
    12
    payment = "t2.micro"
    > data-sources
    13
    dispatch = "t2.micro"
    foreachloops
    14
    web = "t2.micro"
    > .terraform
    15
    E.terraform.lock.hcl
    U
    16
    foreach.tf
    U
    17
    provider.tf
    18
    U
    variable "ami_id" {
    19
    default = "ami-Of3c7d07486cad139"
    variables.tf
    U
    20
    }
    > locals
    21
    > session1
    22
    variable "zone_id" {
    > variables
    23
    default = "Z06431971951XUVZELNIC"
    .gitignore
    24
    }
    25
    26
    variable "domain_name" {
    27
    default = "chowdarychilukuri. in"
    28
    }

[^27]: # aws_route53_record. www\["web"\] will be created
    + resource "aws_route53_record" "www" {
    + allow_overwrite = (known after apply)
    +
    fadn
    = (known after apply)
    id
    = (known after apply)
    + name
    = "web. chowdarychilukuri. in"
    +
    records
    = (known after apply)
    +
    tt1
    = 1
    + type
    = "A"
    + zone_id
    = "Z06431971951XUVZELNIC"
    Plan: 22 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.
    PS E: \\AWSDevops \\Repos \\terraform \\ foreachloops>

[^28]: aws_route53_record. www\["mysql"\]: Creation complete after 1m8s \[id=Z06431971951XUVZELNIC_mysql. chowdarychilukuri . in_A\]
    aws_route53_record. www\["redis"\]: Still creating... \[1m10s elapsed\]
    aws_route53_record. www\["mongodb"\]: Still creating. .. \[10s elapsed\]
    aws_route53_record. www\["redis"\]: Creation complete after 1m12s \[id=206431971951XUVZELNIC_redis . chowdarychilukuri. in_A\]
    aws_route53_record. www\["mongodb"\]: Still creating. .. \[20s elapsed\]
    aws_route53_record. www\["mongodb"\]: Still creating... \[30s elapsed\]
    aws_route53_record. www\["mongodb"\]: Still creating... \[40s elapsed\]
    aws_route53_record. www\["mongodb"\]: Creation complete after 42s \[id=Z06431971951XUVZELNIC_mongodb. chowdarychilukuri . in_A\]
    Apply complete! Resources: 22 added, 0 changed, 0 destroyed.
    LAWS

[^29]: Instances (12) Info
    G
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
    4
    Instance type
    Status check
    mongodb
    i-0e269422da0de 1d5e
    Running
    t3.small
    2/2 checks passed
    mysql
    i-02735bed68d240bod
    Running
    t3.small
    2/2 checks passed
    user
    i-Ofcf43393941f001d
    Running
    t2.micro
    Initializing
    rabbitmq
    i-06e48a4ee3829bffe
    Running
    t2.micro
    2/2 checks passed
    shipping
    i-Of8a352e5dcd7ef6b
    Running
    t3.small
    2/2 checks passed
    redis
    i-01e9f2015dod24782
    Running
    t2.micro
    2/2 checks passed
    cart
    i-0974c87081c16ceOd
    Running
    t2.micro
    2/2 checks passed
    catalogue
    i-012762726af6a6f62
    Running
    t2.micro
    2/2 checks passed
    dispatch
    i-09992da43d819e9c6
    Running
    t2.micro
    2/2 checks passed
    payment
    i-010edOafb6393d547
    Running
    t2.micro
    2/2 checks passed
    web
    i-02013142105a0c9f5
    Running
    t2.micro
    2/2 checks passed

[^30]: DEC2
    Route 53
    B IAM
    VPC
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    Route 53
    X
    Q Filter records by property or value
    Type
    Routing policy
    Alias
    <
    1 )
    Dashboard
    4
    Alias
    4
    4
    Hosted zones
    Record name
    Type
    Routin...
    Differ... V
    Value/Route traffic to
    TTL (S... V
    Health checks
    ns-59.awsdns-07.com.
    Profiles New
    ns-1889.awsdns-44.co.uk.
    chowdarychilukuri.in
    NS
    Simple
    No
    172800
    ns-1039.awsdns-01.org.
    IP-based routing
    ns-836.awsdns-40.net.
    CIDR collections
    O
    chowdarychilukuri.in
    SOA
    Simple
    No
    ns-59.awsdns-07.com. awsdn...
    900
    Traffic flow
    O
    cart.chowdarychilukuri...
    A
    Simple
    No
    172.31.25.2
    Traffic policies
    O
    catalogue.chowdarych...
    A
    Simple
    No
    172.31.19.224
    Policy records
    0
    dispatch.chowdarychil...
    A
    Simple
    No
    172.31.29.157
    Domains
    mongodb.chowdarychi...
    A
    Simple
    No
    172.31.23.130
    Registered domains
    Requests
    mysql.chowdarychiluk...
    A
    Simple
    No
    172.31.22.38
    Resolver
    O
    payment.chowdarychil...
    A
    Simple
    No
    172.31.24.217
    VPCs
    O
    rabbitmq.chowdarychi...
    A
    Simple
    No
    172.31.22.238
    Inbound endpoints
    redis.chowdarychiluku...
    A
    Simple
    No
    172.31.29.106
    Outbound endpoints
    A
    No
    Rules
    shipping.chowdarychil...
    Simple
    172.31.28.205
    Query logging
    O
    user.chowdarychilukur...
    A
    Simple
    No
    172.31.26.38
    Outposts
    n
    web.chowdarychilukur...
    A
    Simple
    No
    3.94.194.129

[^31]: # aws_route53_record . www\["mysql"\] will be destroyed
    - resource "aws_route53_record" "www" {
    - fqdn
    = "mysql . chowdarychilukuri .in" -> null
    - id
    = "Z06431971951XUVZELNIC_mysql . chowdarychilukuri . in_A" -> null
    - multivalue_answer_routing_policy = false -> null
    name
    = "mysql . chowdarychilukuri . in" -> null
    - records
    E
    "172. 31. 22.38"
    \] -> null
    - tt1
    = 1 -> null
    -
    type
    = "A" -> null
    - zone id
    E
    "Z06431971951XUVZELNIC" -> null
    # (2 unchanged attributes hidden)

[^32]: V REPOS
    terraform > dynamic > provider.tf > & terraform
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
    8
    v terraform
    9
    > conditions
    10
    provider "aws" {
    11
    region = "us-east-1"
    > count
    12
    > data-sources
    dynamic
    provider.tf
    U
    if
    U

[^33]: PS E: \\AWSDevops \\Repos \\terraform\\dynamic> terraform init
    Initializing the backend. . .
    Initializing provider plugins. ..
    - Finding hashicorp/aws versions matching "5.49.0"...
    Installing hashicorp/aws v5.49.0

[^34]: terraform > dynamic > sg.tf > % resource "aws_security_group" "roboshop-all"
    1
    resource "aws_security_group" "roboshop-all" {
    name
    = "dynamic-demo"
    3
    description = "dynamic-demo"
    4
    15
    dynamic ingress {
    6
    for_each = var . ingress_rules
    7
    content {
    8
    description
    = ingress . value\["description" \]
    9
    from_port
    = ingress . value \["from_port" \]
    10
    to_port
    = ingress . value\["to_port" \]
    11
    protocol
    = ingress . value \["protocol" \]
    12
    cidr_blocks
    = ingress . value\["cidr_blocks"\]
    13
    14
    15
    16
    egress {
    17
    from_port
    e
    18
    to_port
    = 0
    19
    protocol
    = "-1
    20
    cidr_blocks
    = \["0.0.0.0/0"\]
    21
    #ipv6_cidr_blocks = \[": :/0"\]
    22
    23
    24
    tags = {
    25
    Name = "dynamic-demo-1"
    26
    27

[^35]: variable "ingress_rules" {
    2
    default = \[
    3
    4
    description
    "Allow port 80"
    5
    from_port
    = 80 # 0 means all ports
    6
    to_port
    = 80
    17
    protocol
    E
    "tcp"
    8
    cidr_blocks
    =
    \["0.0.0.0/0"\]
    9
    10
    11
    description
    "Allow port 443"
    12
    from_port
    = 443 # 0 means all ports
    13
    to_port
    = 443
    14
    protocol
    "tcp"
    15
    cidr_blocks
    = \["0.0.0.0/0"\]
    16
    17
    18
    description
    "Allow port 22"
    19
    from_port
    = 22# 0 means all ports
    20
    to_port
    = 22
    21
    protocol
    = "tcp"
    22
    cidr_blocks
    \["0.0.0.0/0"\]
    23
    24
    25
    description
    "Allow port 3306"
    26
    from_port
    3306# 0 means all ports
    27
    to_port
    = 3306
    28
    protocol
    "tcp"
    29
    cidr_blocks
    = \["192.167.23.23/32"\]
    30
    31
    32
    33

[^36]: +
    vpc_id
    = (known after apply)
    Plan: 1 to add, 0 to change, 0 to destroy.
    aws_security_group . roboshop-all: Creating. ..
    aws_security_group. roboshop-all: Creation complete after 6s \[id=sg-0b163d3f8392caf7b\]
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevOps \\Repos \\terraform\\dynamic> terraform apply -auto-approve

[^37]: Security Groups (1/5) Info
    C
    Actions
    Export security groups to CSV
    Create security group
    Q Find resources by attribute or tag
    < 1 >
    -
    Name
    V
    Security group ID
    4
    Security group name
    VPC ID
    4
    Desc
    Frontend_SG
    sg-02069258c6db847af
    Frontend_SG
    vpc-0817 cae8968304c06 \[
    This i
    dynamic-demo-1
    sg-0b163d3f8392caf7b
    dynamic-demo
    vpc-0817cae89b8304c06 \[
    dyna
    sg-Ofb 7aa4a85348c80e
    launch-wizard-1
    vpc-0817cae89b8304c06 \[
    launc
    0
    SG_Allow_All
    sg-0c9db47e9b4d484b6
    SG_Allow_ALL
    vpc-0817cae89b8304c06 \[Z
    Allow
    sg-029974043a4090491
    default
    vpc-0817 cae8968304c06 \[Z
    defal
    Details
    Inbound rules
    Outbound rules
    Tags
    Inbound rules (3)
    C
    Manage tags
    Edit inbound rules
    Q Search
    < 1
    O
    Name
    Security group rule... V IP version
    4
    Type
    Protocol
    4
    Port range
    sgr-0c4d7f3bb699583f9
    IPV4
    HTTPS
    TCP
    443
    O
    sgr-06cfe027e1cb7511b
    IPV4
    HTTP
    TCP
    80
    O
    sgr-097650eca958a2e54
    IPV4
    SSH
    TCP
    22

[^38]: REPOS
    terraform > dynamic > {} terraform.tfstate > ...
    > Ansible
    1
    > Concepts
    "version" : 4,
    3
    "terraform_version": "1.8.3",
    > notes
    4
    "serial" : 3,
    > Robosho-shellscripts
    M
    5
    "lineage" : "609b5da7-787e-2809-eef8-6578cca2649f",
    > roboshop-ansible
    6
    "outputs": {},
    > roboshop-ansible-roles
    7
    "resources" : \[
    > shellscripts
    8
    {
    v terraform
    9
    "mode": "managed",
    10
    > conditions
    "type": "aws_security_group",
    11
    "name": "roboshop-all",
    > count
    12
    "provider": "provider\[\\"registry . terraform. io/hashicorp/aws\\" \]",
    > data-sources
    13
    "instances" : \[
    dynamic
    14
    v .terraform \\ providers \\ registry.terr...
    15
    "schema_version" : 1,
    A LICENSE.txt
    16
    "attributes": {
    terraform-provider-aws_v5.49.0_...
    17
    "arn": "arn: aws : ec2: us-east-1: 158724841371: security-group/sg-0b163d3f8392caf7b",
    18
    "description": "dynamic-demo",
    E.terraform.lock.hcl
    U
    19
    "egress" : \[
    provider.tf
    U
    20
    sg.tf
    U
    21
    "cidr_blocks" : \[
    {} terraform.tfstate
    22
    "0.0.0.0/0"
    E terraform.tfstate.backup
    23
    variables.tf
    U
    24
    "description": ""
    25
    "from_port" : 0,
    > foreachloops
    26
    "ipv6_cidr_blocks": \[\],
    > locals
    27
    "prefix_list_ids": \[\],
    > session1
    28
    "protocol": "-1"
    > variables
    29
    "security_groups": \[\],
    .gitignore
    30
    "self": false,
    31
    "to_port" : 0
    32
    33
    \],
    34
    "id": "sg-0b163d3f8392caf7b",
    35
    "ingress" : \[
    36

[^39]: PS E: \\AWSDevops \\Repos \\terraform\\dynamic> terraform apply -auto-approve
    aws_security_group. roboshop-all: Refreshing state. .. \[id=sg-0b163d3f8392caf7b\]
    No changes. Your infrastructure matches the configuration.
    Terraform has compared your real infrastructure against your configuration and found no differences, so no changes are needed.
    Apply complete! Resources: 0 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevops \\Repos \\terraform\\dynamic> I

[^40]: dynamic
    14
    protocol
    "tcp"
    v .terraform \\ providers \\ registry.terr...
    15
    cidr_blocks
    = \["0.0.0.0/0"\]
    R LICENSE.txt
    16
    terraform-provider-aws_v5.49.0_
    17
    18
    E .terraform.lock.hcl
    description
    = "Allow port 22"
    U
    19
    from_port
    = 22
    provider.tf
    U
    20
    to_port
    = 22
    sg.tf
    U
    21
    protocol
    E
    "tcp"
    {} terraform.tfstate
    22
    cidr_blocks
    = \["0.0.0.0/0"\]
    E terraform.tfstate.backup
    23
    Y
    variables.tf
    U
    24
    25
    > foreachloops
    description
    = "Allow port 3306"
    26
    from_port
    3306
    > locals
    27
    to_port
    = 3306
    > session1
    28
    protocol
    "tcp"
    > variables
    29
    cidr_blocks
    = \["192. 167.23.23/32"\]
    .gitignore
    30
    31
    32
    33

[^41]: aws_security_group . roboshop-all: Refreshing state. .. \[id=sg-0b163d3f8392caf7b\]
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    \~ update in-place
    Terraform will perform the following actions:
    # aws_security_group. roboshop-all will be updated in-place
    \~ resource "aws_security_group" "roboshop-all" {
    id
    = "sg-0b163d3f8392caf7b"
    \~ ingress
    = \[
    cidr_blocks
    = \[
    "192. 167.23.23/32",
    + description
    = "Allow port 3306"
    + from_port
    = 3306
    + ipv6_cidr_blocks = \[\]
    + prefix_list_ids
    \[\]
    + protocol
    = "tcp"
    security_groups
    = \[\]
    + self
    = false
    + to_port
    3306
    # (3 unchanged elements hidden)
    1
    name
    = "dynamic-demo"
    tags
    "Name" = "dynamic-demo-1"
    # (8 unchanged attributes hidden)
    Plan: 0 to add, 1 to change, 0 to destroy.

[^42]: PS E: \\AWSDevops \\Repos \\terraform\\dynamic> terraform apply -auto-approve
    aws_security_group . roboshop-all: Refreshing state. .. \[id=sg-0b163d3f8392caf7b\]
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    \~ update in-place
    Terraform will perform the following actions:
    # aws_security_group. roboshop-all will be updated in-place
    resource "aws_security_group" "roboshop-all" {
    id
    = "sg-0b163d3f8392caf7b"
    \~ ingress
    =
    cidr_blocks
    + "192. 167.23.23/32",
    + description
    = "Allow port 3306"
    from_port
    = 3306
    + ipv6_cidr_blocks = \[\]
    + prefix_list_ids
    + protocol
    "tcp"
    + security_groups
    = \[\]
    + self
    = false
    to_port
    = 3306
    # (3 unchanged elements hidden)
    name
    = "dynamic-demo"
    tags
    "Name" = "dynamic-demo-1"
    # (8 unchanged attributes hidden)
    Plan: 0 to add, 1 to change, 0 to destroy.
    aws_security_group. roboshop-all: Modifying. .. \[id=sg-0b163d3f8392caf7b\]
    aws_security_group. roboshop-all: Modifications complete after 3s \[id=sg-0b163d3f8392caf7b\]
    Apply complete! Resources: 0 added, 1 changed, 0 destroyed.

[^43]: V
    dynamic-demo-1
    sg-0b 163d3f8392caf7b
    dynamic-demo
    vpc-0817cae8968304c06 \[
    dyr
    O
    SG_Allow_All
    sg-0c9db47e9b4d484b6
    SG_Allow_All
    vpc-0817 cae8968304c06 \[
    All
    sg-029974043a4090491
    default
    vpc-0817 cae8968304c06 \[
    def
    C
    Inbound rules (4)
    C
    Manage tags
    Edit inbound rules
    Q Search
    <
    1 >
    O
    Name
    4
    Security group rule... V IP version
    Type
    Protocol
    V
    Port range
    sgr-0c4d7f3bb699583f9
    IPV4
    HTTPS
    TCP
    443
    sgr-06cfe027e1cb7511b
    IPV4
    HTTP
    TCP
    80
    O
    sgr-097650eca958a2e54
    IPV4
    SSH
    TCP
    22
    sgr-010ecb671d96b9c...
    IPV4
    MYSQL/Aurora
    TCP
    3306

[^44]: \] -> null
    -
    name
    = "dynamic-demo" -> null
    -
    owner id
    = "158724841371" -> null
    revoke_rules_on_delete = false -> null
    - tags
    = {
    -
    "Name" = "dynamic-demo-1"
    } -> null
    - tags_all
    "Name" = "dynamic-demo-1"
    } -> null
    vpc_id
    = "vpc-0817cae8968304c06" -> null
    # (1 unchanged attribute hidden)
    Plan: 0 to add, 0 to change, 1 to destroy.
    aws_security_group. roboshop-all: Destroying... \[id=sg-0b163d3f8392caf7b\]
    aws_security_group. roboshop-all: Destruction complete after 3s
    Destroy complete! Resources: 1 destroyed.
    PS E: \\AWSDevOps\\Repos \\terraform\\dynamic>

[^45]: terraform
    terraform

[^46]: General configuration
    AWS Region
    US East (N. Virginia) us-east-1
    Bucket type Info
    General purpose
    O Directory - New
    Recommended for most use cases and access patterns.
    Recommended for low-latency use cases. These buckets
    General purpose buckets are the original S3 bucket type.
    use only the S3 Express One Zone storage class, which
    They allow a mix of storage classes that redundantly
    provides faster processing of data within a single
    store objects across multiple Availability Zones.
    Availability Zone.
    Bucket name Info
    chilops-terraform-remotestate
    Bucket name must be unique within the global namespace and follow the bucket naming rules. See rules for bucket naming
    Copy settings from existing bucket - optional
    Only the bucket settings in the following configuration are copied.
    Choose bucket
    Format: $3://bucket/prefix
    Object Ownership Info
    Control ownership of objects written to this bucket from other AWS accounts and the use of access control lists (ACLs). Object ownership
    determines who can specify access to objects.
    ACLs disabled (recommended)
    O ACLS enabled
    All objects in this bucket are owned by this account.
    Objects in this bucket can be owned by other AWS
    Access to this bucket and its objects is specified using
    accounts. Access to this bucket and its objects can be
    only policies.
    specified using ACLs.

[^47]: Amazon S3 > Buckets
    Account snapshot - updated every 24 hours (All AWS Regions
    View Storage Lens dashboard
    Storage lens provides visibility into storage usage and activity trends. Learn more \[
    General purpose buckets
    Directory buckets
    General purpose buckets (1) Info
    ALL AWS Regions
    G
    Copy ARN
    Empty
    Delete
    Create bucket
    Buckets are containers for data stored in $3.
    Find buckets by name
    < 1
    Name
    AWS Region
    IAM Access Analyzer
    Creation date
    4
    O
    chilops-terraform-remotestate
    US East (N. Virginia) us-east-1
    View analyzer for us-east-1
    May 16, 2024, 12:59:32 (UTC+05:30)

[^48]: DynamoDB > Tables > Create table
    Create table
    Table details Info
    DynamoDB is a schemaless database that requires only a table name and a primary key when you create the table.
    Table name
    This will be used to identify your table.
    chilops-locking
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

[^49]: DynamoDB > Tables
    Tables (1) Info
    C
    Actions
    Delete
    Create table
    Q Find tables by table name
    Any tag key
    Any tag value
    1
    O
    Name
    Status
    Partition key
    Sort key
    Indexes
    Deletion protection
    Read capacity mode
    Write capacity mo...
    chilops-locking
    Active
    LockID (S)
    0
    Off
    Provisioned (5)
    Provisioned (5)

[^50]: REPOS
    terraform > dynamic > provider.tf > < terraform > backend "s3" > dynamodb_table
    > Ansible
    1
    terraform {
    > Concepts
    12
    required_providers {
    3
    > notes
    aws = {
    4
    source = "hashicorp/aws"
    > Robosho-shellscripts
    M
    version = "5.49.0" #AWS provider version, not terraform version
    > roboshop-ansible
    6
    > roboshop-ansible-roles
    7
    > shellscripts
    8
    terraform
    19
    backend "s3" {
    > conditions
    10
    bucket = "chilops-terraform-remotestate"
    11
    key
    = "dynamic"
    > count
    12
    region = "us-east-1"
    > data-sources
    13
    dynamodb_table = "chilops-locking"
    dynamic
    14
    v .terraform \\ providers \\ registry.terr...
    15
    }
    R LICENSE.txt
    16
    provider "aws" {
    = terraform-provider-aws_v5.49.0_...
    17
    region = "us-east-1"
    18
    E.terraform.lock.hcl
    U
    provider.tf
    U
    sg.tf
    U
    {}
    terraform.tfstate

[^51]: PS E: \\AWSDevops \\Repos \\terraform\\dynamic> terraform plan
    Error: Backend initialization required, please run "terraform init"
    Reason: Initial configuration of the requested backend "s3"
    The "backend" is the interface that Terraform uses to store state,
    perform operations, etc. If this message is showing up, it means that the
    Terraform configuration you're using is using a custom configuration for
    the Terraform backend.
    Changes to backend configurations require reinitialization. This allows
    Terraform to set up the new configuration, copy existing state, etc. Please run
    "terraform init" with either the "-reconfigure" or "-migrate-state" flags to
    use the current configuration.
    If the change reason above is incorrect, please verify your configuration
    hasn't changed and try again. At this point, no changes to your existing
    configuration or state have been made.
    PS E: \\AWSDevops \\Repos \\terraform\\dynamic> !

[^52]: PS E: \\AWSDevops \\Repos \\terraform\\dynamic> terraform init -reconfigure
    Initializing the backend. ..
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing provider plugins. ..
    Reusing previous version of hashicorp/aws from the dependency lock file
    Using previously-installed hashicorp/aws v5.49.0
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. All Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    PS E: \\AWSDevops \\Repos \\terraform\\dynamic>

[^53]: PS E: \\AWSDevops \\Repos \\terraform\\dynamic> terraform apply -auto-approve
    Acquiring state lock. This may take a few moments . . .
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create
    Terraform will perform the following actions:
    # aws_security_group. roboshop-all will be created
    + resource "aws_security_group" "roboshop-all" {
    arn
    = (known after apply)
    + description
    =
    "dynamic-demo"
    egress
    \[
    + cidr_blocks
    = \[
    + "0.0.0.0/0"
    + from_port
    = 0
    + ipv6_cidr_blocks = \[\]

[^54]: DynamoDB > Tables > chilops-locking
    Tables (1)
    X
    chilops-locking
    C
    Actions
    Explore table items
    Any tag key
    <
    Overview
    Indexes
    Monitor
    Global tables
    Backups
    Exports and streams
    Any tag value
    Q Find tables by table name
    Protect your DynamoDB table from accidental writes and deletes
    Edit PITR
    X
    < 1 >
    When you turn on point-in-time recovery (PITR), DynamoDB backs up your table
    data automatically so that you can restore to any given second in the preceding 35
    days. Additional charges apply. Learn more \[
    O
    chilops-locking
    General information Info
    Partition key
    Sort key
    Capacity mode
    Table status
    LockID (String)
    Provisioned
    Active
    Alarms
    Point-in-time recovery
    Resource-based
    No active alarms
    (PITR) Info
    policy Info
    Off
    Not active

[^55]: DynamoDB
    X
    DynamoDB > Explore items > chilops-locking
    Dashboard
    Tables (1)
    X
    chilops-locking
    Autopreview
    View table details
    Tables
    Any tag key
    Explore items
    Scan or query items
    PartiQL editor
    Any tag value
    Backups
    Q Find tables by table name
    Scan
    O Query
    Exports to $3
    < 1 >
    Imports from $3
    Select a table or index
    Select attribute projection
    Integrations New
    O
    Table - chilops-locking
    All attributes
    chilops-locking
    Reserved capacity
    Settings
    Filters
    DAX
    Run
    Reset
    Clusters
    Subnet groups
    Parameter groups
    Completed. Read capacity units consumed: 0.5
    X
    Events
    Items returned (1)
    G
    Actions
    Create item
    1
    O
    LockID (String)
    V
    Digest
    4
    chilops-terraform-remotestate/dynamic-md5
    b830d5fOdddf537645fb8278d3cb 1386

[^56]: Amazon S3 > Buckets > chilops-terraform-remotestate
    chilops-terraform-remotestate info
    Objects
    Properties
    Permissions
    Metrics
    Management
    Access Points
    Objects (1) Info
    C
    Copy S3 URI
    Copy URL
    Download
    Open
    Delete
    Actions
    Create folder
    Upload
    Objects are the fundamental entities stored in Amazon S3. You can use Amazon S3 inventory \[ to get a list of all objects in your bucket. For others to access your objects, you'll need to
    explicitly grant them permissions. Learn more
    Q Find objects by prefix
    1
    Name
    Type
    4
    Last modified
    4
    Size
    Storage class
    A
    0
    dynamic
    May 16, 2024, 13:21:51
    3.3 KB
    Standard
    (UTC+05:30)

