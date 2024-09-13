---
title: 35Day_Terraform_AWS
uuid: 71e009f8-2d24-11ef-a10e-b247aed906a4
version: 384
created: '2024-06-18T09:10:02+05:30'
---

***Topics:***

1. <mark style="background-color:#f8d616;">Roboshop-infra-dev<!-- {"backgroundCycleColor":"25"} --></mark>

    1. <mark style="background-color:#fff;">Flow of request from user<!-- {"backgroundCycleColor":"11"} --></mark>

    1. VPC

    1. Security Group (SG)

    1. VPN

    1. Database (Ansible pull stratergy)

2\.<mark style="background-color:#f8d616;">To delete the infra at one go using for loop<!-- {"backgroundCycleColor":"25"} --></mark> 

\

# <mark style="background-color:#f8914d;">**Roboshop-infra-dev**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 <mark style="background-color:#f8d616;">Flow of request from user<!-- {"backgroundCycleColor":"25"} --></mark>

![infra.jpg?raw=true|921](https://github.com/daws-76s/roboshop-infra-dev/blob/main/infra.jpg?raw=true)

\

# <mark style="background-color:#f8914d;">**VPC**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Create below folder and code it.

![514bb164-b07b-4c58-a095-e8b4de5cff7a.png|344](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/514bb164-b07b-4c58-a095-e8b4de5cff7a.png) [^1]

\

Update provider.tf code - get bucket name from S3 & DynamoDB table from DynamoDB

![ba564fb7-7e5e-42a8-9121-b9a5cdebb334.png|1006.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/ba564fb7-7e5e-42a8-9121-b9a5cdebb334.png) [^2]

\

\

![e857c077-1187-4c0b-8045-ce2329540119.png|1011.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/e857c077-1187-4c0b-8045-ce2329540119.png) [^3]

\

![c9aea963-d40c-422f-9442-11363c9aaa95.png|1021.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/c9aea963-d40c-422f-9442-11363c9aaa95.png) [^4]

\

```
terraform init
```

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/9bc1558f-8f4c-48bb-8f09-22c64d049550.png) [^5]

\

```
terraform apply -auto-approve
```

![727647a7-3678-4a5a-b7bf-7e366829e4da.png|934](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/727647a7-3678-4a5a-b7bf-7e366829e4da.png) [^6]

\

VPC, Subnet, Internet Gateway, Route tables, Elastic IP, NAT Gateway, VPC Peering and associations.

![03d24782-9def-477c-a251-64c70091466f.png|1016.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/03d24782-9def-477c-a251-64c70091466f.png) [^7]

![7ea4c52a-4556-4397-8e9b-4b51f2f0a4ff.png|1042.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/7ea4c52a-4556-4397-8e9b-4b51f2f0a4ff.png) [^8]

![d9ac5c34-b60e-47d6-8d81-15dce3791d1c.png|1105.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/d9ac5c34-b60e-47d6-8d81-15dce3791d1c.png) [^9]

![711e1727-e0b4-47a5-ac6c-965ef8b82742.png|1104.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/711e1727-e0b4-47a5-ac6c-965ef8b82742.png) [^10]

![0fd55ed3-50ed-4283-9c7b-5ba2284db01d.png|1119.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/0fd55ed3-50ed-4283-9c7b-5ba2284db01d.png) [^11]

![028ba81e-02cf-4938-a437-b06597e9f54f.png|1101.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/028ba81e-02cf-4938-a437-b06597e9f54f.png) [^12]

![7a40a70c-091d-47ff-9be7-9ea36172fb3b.png|1108.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/7a40a70c-091d-47ff-9be7-9ea36172fb3b.png) [^13]

---

# <mark style="background-color:#f8914d;">**Security Group (SG)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Application load balancer SG

![ef4dd0e7-115e-43ef-8757-a609cef0a69b.png|868](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/ef4dd0e7-115e-43ef-8757-a609cef0a69b.png) [^14]

```
terraform init
```

![947a970d-caa5-4e2e-a517-7eea3ae75216.png|798](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/947a970d-caa5-4e2e-a517-7eea3ae75216.png) [^15]

\

```
terraform apply -auto-approve
```

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/129559f3-fb0f-4259-9020-672c0d510ae2.png) [^16]

# <mark style="background-color:#f8914d;">**VPN**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Create below folders and code & update provider.tf 

![878ee5e3-df11-448e-bd9d-58a406448a45.png|1062.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/878ee5e3-df11-448e-bd9d-58a406448a45.png) [^17]

```
terraform init
```

![cdd2f710-6788-44f6-96df-282356530773.png|774](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/cdd2f710-6788-44f6-96df-282356530773.png) [^18]

```
terraform apply -auto-approve
```

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/34778588-548c-4026-bb0e-fe5d3c9aac84.png) [^19]

![a4fac2f4-7bb2-42f7-8a6e-14b55e176c01.png|870](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/a4fac2f4-7bb2-42f7-8a6e-14b55e176c01.png) [^20]

\

\

# <mark style="background-color:#f8914d;">**Database (Ansible pull strategy)**<!-- {"backgroundCycleColor":"24"} --></mark>

\

Create database & code as below.

![8e1b9fbd-2f48-4882-9ee8-f0c3df410877.png|993.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/8e1b9fbd-2f48-4882-9ee8-f0c3df410877.png) [^21]

\

\

\

Now create **roboshop-ansible-roles-tf** & its code.

\

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/62e27c91-f968-4810-9138-9c8326d04cc5.png) [^22]

\

<mark>Terraform null resource</mark>

![8f6640cf-b99b-402b-9007-5d0e7e1082cc.png|991.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/8f6640cf-b99b-402b-9007-5d0e7e1082cc.png) [^23]

\

<mark>Ansible pull</mark>

<mark>Ansible pull VS push</mark> 

![878f1ab3-99cc-427a-ba50-87e752e03620.png|1017](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/878f1ab3-99cc-427a-ba50-87e752e03620.png) [^24]

\

```
cd roboshop-ansible-roles-tf/
rm -rf .git
git init
git remote add origin git@github.com:chilops/roboshop-ansible-roles-tf.git
git add . ; git commit -m "ansible roles tf"; git push origin main
```

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/cb789824-fd9e-44d7-ad2e-8d00d7d55d30.png) [^25]

\

![e5248e40-4248-49cb-8e68-34094b9462bd.png|1034.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/e5248e40-4248-49cb-8e68-34094b9462bd.png) [^26]

\

Now initiating Database

```
terraform init
```

![484e82cf-a599-428e-ada7-3dce12a6b584.png|733](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/484e82cf-a599-428e-ada7-3dce12a6b584.png) [^27]

\

Since Mongodb is private , Now i must connect to VPN.

\

VPN server

```
sudo su -
ls -l
cat chilukuri.ovpn
```

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/ee958f95-2a54-4033-8a74-ceeded9971ed.png) [^28]

![b0a29a97-4b5d-4b2f-8f04-4c2db0b6533f.png|905](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/b0a29a97-4b5d-4b2f-8f04-4c2db0b6533f.png) [^29]

\

copy chilukuri.ovpn to local laptop.

![663158b1-28ff-4704-9225-cd76d393e241.png|649](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/663158b1-28ff-4704-9225-cd76d393e241.png) [^30]

![4080013c-4898-47c8-a8ab-19246face3ba.png|915.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/4080013c-4898-47c8-a8ab-19246face3ba.png) [^31]

![0283f616-045a-4383-a8ee-966cda2a82d8.png|429](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/0283f616-045a-4383-a8ee-966cda2a82d8.png) [^32]

\

```
terraform apply -auto-approve
```

![091b6742-9d4b-4a32-ac5f-bc13299ad0b1.png|941.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/091b6742-9d4b-4a32-ac5f-bc13299ad0b1.png) [^33]

\

connect to mongodb instance check 

```
netstat -lntp
```

![ef531ce1-f5e9-4de2-9bc8-12da14f6922d.png|1039.3333740234375](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/ef531ce1-f5e9-4de2-9bc8-12da14f6922d.png) [^34]

\

<mark>Now redis setup</mark>

\

\

\

# <mark style="background-color:#f8914d;">**To delete the infra at one go using for loop**<!-- {"backgroundCycleColor":"24"} --></mark> 

\

for i in 'ls -dr \*/' ; do cd $i ; terraform destroy -auto-approve ; cd .. ; done

![](https://images.amplenote.com/71e009f8-2d24-11ef-a10e-b247aed906a4/706745bd-cc52-4ee0-b431-8b1ea676eca8.png) [^35]

\

\

[^1]: v roboshop-infra-dev
    01-vpc
    main.tf
    parameters.tf
    provider.tf
    CCC CCC
    variables.tf
    -
    Infra.png
    readme.MD

[^2]: EXPLORER
    . .
    ec2 U
    variables.tf ..\\04-ec2 U
    variables.tf ..\\03-vpn U
    $ ec2-provision.sh U
    i readme.MD ro
    V REPOS
    roboshop-infra-dev > 01-vpc > provider.tf > < provider "aws"
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
    9
    backend "s3" {
    > notes
    10
    bucket = "chilops-terraform-s3-dev"
    11
    > Robosho-shellscripts
    key
    = "vpc"
    M
    12
    region = "us-east-1"
    > roboshop-ansible
    13
    dynamodb_table = "chilops-locking-dev"
    > roboshop-ansible-roles
    14
    v roboshop-infra-dev
    15
    v 01-vpc
    16
    main.tf
    U
    17
    provider "aws" {
    18
    region = "us-east-1"
    parameters.tf
    U
    19
    provider.tf
    U
    variables.tf
    U

[^3]: DynamoDB
    X
    Share your feedback on Amazon DynamoDB
    Share feedback
    X
    Your feedback is an important part of helping us provide a better customer experience. Take this short survey to let us know how we're doing.
    Dashboard
    DynamoDB > Tables
    Tables
    Explore items
    Tables (3) Info
    C
    Actions
    Delete
    Create table
    PartiQL editor
    Backups
    Q Find tables by table name
    Any tag key
    Any tag value
    <
    1 >
    Exports to $3
    O
    Name
    Status
    Partition key
    Sort key
    Indexes
    Deletion protection
    Read capacity mode
    Write capacity
    Imports from $3
    0
    chilops-locking
    Active
    LockID (S)
    0
    Off
    Integrations New
    Provisioned (1)
    Provisioned (1)
    Reserved capacity
    chilops-locking-dev
    -
    Active
    LockID (S)
    0
    Off
    Provisioned (1)
    Provisioned (1)
    Settings
    chilops-locking-prod
    Active
    LockID (S)
    0
    Off
    Provisioned (1)
    Provisioned (1)

[^4]: Amazon S3
    Account snapshot - updated every 24 hours (All AWS Regions
    View Storage Lens dashboard
    Storage lens provides visibility into storage usage and activity trends. Learn more
    General purpose buckets
    Directory buckets
    General purpose buckets (3) Info
    ALL AWS Regions
    C
    Copy ARN
    Empty
    Delete
    Create bucket
    Buckets are containers for data stored in $3.
    Q Find buckets by name
    < 1 >
    Name
    AWS Region
    4
    IAM Access Analyzer
    Creation date
    D
    O
    chilops-terraform-remotestate
    US East (N. Virginia) us-east-1
    May 16, 2024, 13:03:47
    View analyzer for us-east-1
    (UTC+05:30)
    O
    chilops-terraform-s3-dev
    US East (N. Virginia) us-east-1
    May 17, 2024, 10:35:59
    View analyzer for us-east- 1
    (UTC+05:30)
    O
    chilops-terraform-$3-prod
    May 17, 2024, 10:33:29
    US East (N. Virginia) us-east-1
    View analyzer for us-east-1
    (UTC+05:30)

[^5]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos (main)
    $ cd roboshop-infra-dev/
    chowd@chowdary MINGW64 /e/AWSDevops /Repos/roboshop-infra-dev (main)
    $ cd 01-vpc/
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos/roboshop-infra-dev/01-vpc (main)
    $ terraform init
    Initializing the backend. . .
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing modules . . .
    Down loading git: :https://github.com/chilops/terraform-aws-vpc. git?ref=main for roboshop. . .
    roboshop in . terraform modules roboshop
    Initializing provider plugins . . .
    Finding hashicorp/aws versions matching "5.31.0"...
    Installing hashicorp/aws v5 . 31.0. . .
    Installed hashicorp/aws v5 . 31.0 (signed by Hashicorp)
    Terraform has created a lock file . terraform. lock.hc1 to record the provider
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

[^6]: aws_ssm_parameter . public_subnet_Tas : Creation complete after Is \[10=/roboshop/dev/pub 17c_subnet_1as \]
    module . roboshop . aws_nat_gateway . main: Still creating. . .
    \[10s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . .
    \[20s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating..
    \[30s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . .
    \[40s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating.
    \[50s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . .
    \[1mos elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . .
    \[1m10s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . .
    \[1m20s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . . \[1m30s elapsed\]
    module . roboshop . aws_nat_gateway . main: Creation complete after 1m38s \[id=nat-06cca06fa241e71c9\]
    module . roboshop . aws_route . private_route: Creating. . .
    module . roboshop . aws_route . database_route: Creating. . .
    module . roboshop . aws_route . private_route: Creation complete after 2s \[id=r-rtb-0b6f7904f385160171080289494\]
    module . roboshop . aws_route . database_route: Creation complete after 2s \[id=r-rtb-0847628cdbeddf5a41080289494\]
    Releasing state lock. This may take a few moments . . .
    Apply complete! Resources: 32 added, 0 changed, 0 destroyed.
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos /roboshop-infra-dev/01-vpc (main)

[^7]: Your VPCs (2) Info
    G
    Actions
    Create VPC
    Q Search
    <
    1
    O
    Name
    V
    VPC ID
    4
    State
    4
    IPV4 CIDR
    4
    IPV6 CIDR
    4
    DHCP option set
    4
    Main route table
    4
    M
    roboshop-dev
    vpc-023a1cdd990f91e8b
    Available
    10.0.0.0/16
    dopt-069994658cab2e...
    rtb-04ebbff9262a186cc
    a
    vpc-0817cae8968304c06
    Available
    172.31.0.0/16
    dopt-069994658cab2e...
    rtb-Obfe8282f6ae865ab
    a

[^8]: Subnets (12) Info
    Last updated
    C
    Actions
    Create subnet
    less than a minute ago
    Q Find resources by attribute or tag
    <
    1
    Name
    Subnet ID
    V
    State
    V
    VPC
    V
    IPV4 CIDR
    subnet-0873e3231bac49c20
    Available
    vpc-0817cae8968304c06
    172.31.64.0/20
    subnet-076650bcf0b486323
    Available
    vpc-0817cae8968304c06
    172.31.16.0/20
    subnet-Od3fb051 10e2d9e48
    Available
    vpc-0817cae8968304c06
    172.31.48.0/20
    roboshop-dev-database-us-east-1a
    subnet-0060aa7187deb3891
    Available
    vpc-023a1cdd990f91e8b \| roboshop-dev
    10.0.21.0/24
    roboshop-dev-database-us-east-1b
    subnet-06e 19e40c18166673
    Available
    vpc-023a1cdd990f91e8b \| roboshop-dev
    10.0.22.0/24
    0
    roboshop-dev-private-us-east-1a
    subnet-0e612afe914329726
    Available
    vpc-023a1cdd990f91e8b \| roboshop-dev
    10.0.11.0/24
    roboshop-dev-private-us-east-1b
    subnet-00aa379c52454f9a3
    Available
    vpc-023a1cdd990f91e8b \| roboshop-dev
    10.0.12.0/24
    O
    roboshop-dev-public-us-east-1a
    subnet-0777b446fcb6d923f
    Available
    vpc-023a1cdd990f91e8b \| roboshop-dev
    10.0.1.0/24
    roboshop-dev-public-us-east-1b
    subnet-0Off702f0958dec55
    Available
    vpc-023a1cdd990f91e8b \| roboshop-dev
    10.0.2.0/24

[^9]: Internet gateways (2) Info
    C
    Actions
    Create internet gateway
    Q Search
    <
    1 >
    Name
    4
    Internet gateway ID
    State
    4
    VPC ID
    Owner
    igw-059405258c34db2a1
    Attached
    vpc-0817 cae8968304c06
    158724841
    roboshop-dev
    igw-09e3a453740c62f67
    Attached
    vpc-023a1cdd990f91e8b \| roboshop-dev
    158724841

[^10]: Route tables (5) Info
    Last updated
    C
    Actions
    Create route table
    less than a minute ago
    Q Find resources by attribute or tag
    <
    1
    O
    Name
    Route table ID
    4
    Explicit s...
    4
    Edge... V
    Main
    4
    VPC
    rtb-04ebbff9262a186cc
    Yes
    vpc-023a1cdd990f91e8b \| roboshop-dev
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817cae8968304c06
    O
    roboshop-dev-database
    rtb-0847628cdbeddf5a4
    2 subnets
    No
    vpc-023a1cdd990f91e8b \| roboshop-dev
    roboshop-dev-private
    rtb-0b6f7904f38516017
    2 subnets
    No
    vpc-023a1cdd990f91e8b \| roboshop-dev
    O
    roboshop-dev-public
    rtb-0a0049325a5260645
    2 subnets
    No
    vpc-023a1cdd990f91e8b \| roboshop-dev

[^11]: Elastic IP addresses (1)
    C
    Actions
    Allocate Elastic IP address
    Q Find resources by attribute or tag
    <
    1
    U
    Name
    Allocated IPv4 addr... V Type
    V
    Allocation ID
    4
    Reverse DNS record
    54.243.219.226
    Public IP
    eipalloc-04afd67738aabOca5

[^12]: NAT gateways (1) Info
    C
    Actions
    Create NAT gateway
    Q Find resources by attribute or tag
    < 1 >
    Name
    A
    NAT gateway ID
    Con...
    State
    Stat...
    Primary public I...
    4
    Primary private IPv4 address
    O
    roboshop-dev
    nat-06cca06fa241e71c9
    Public
    Available
    54.243.219.226
    10.0.1.161

[^13]: Peering connections (1) Info
    C
    Actions
    Create peering connection
    Q Find resources by attribute or tag
    1 >
    Name
    Peering connection ID
    Status
    4
    Requester VPC
    Accepter VPC
    O
    roboshop-dev
    pcx-09aa5bc9d6d9b604a
    Active
    vpc-023a1cdd990f91e8b / robo...
    vpc-0817 cae8968304co

[^14]: 02-sg
    109
    > .terraform
    110
    111
    E .terraform.lock.hcl
    module "app_alb"
    U
    112
    source
    / . ./terraform-aws-security-group"
    data.tf
    U
    11
    project_name
    = var . project_name
    main.tf
    U
    110
    environment
    = var . environment
    parameters.tf
    115
    sg_description = "SG for APP ALB"
    provider.tf
    116
    vpc_id
    = data. aws_ssm_parameter . vpc_id . value
    CC CC
    sg.yaml
    11/
    sg_name
    = "app-alb"
    variables.tf
    113
    #sg_ingress_rules = var . mongodb_sg_ingress_rules
    119
    infra.jpg
    120

[^15]: chowd@Chowdary MINGW64 /e/AWSDevops/Repos /roboshop-infra-dev (main)
    $ cd 02-sg/
    chowd@Chowdary MINGW64 /e/AWSDevops/Repos /roboshop-infra-dev/02-sg (main)
    $ terraform init
    Initializing the backend. . .
    successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing modules . . .
    cart in . . . . terraform-aws-security-group
    catalogue in . . . . \\terraform-aws-security-group
    mongodb in . . . . terraform-aws-security-group
    mysql in . . . . terraform-aws-security-group
    payment in . . . . \\terraform-aws-security-group
    rabbitmq in
    .\\. . \\terraform-aws-security-group
    redis in . . \\. . \\terraform-aws-security-group
    shipping in . . . . terraform-aws-security-group
    user in . . . . terraform-aws-security-group
    vpn in . . . . terraform-aws-security-group
    web in . . . . terraform-aws-security-group
    Initializing provider plugins . . .
    Finding hashicorp/aws versions matching "5.31.0". . .
    Installing hashicorp/aws v5 . 31.0. . .
    Installed hashicorp/aws v5 . 31.0 (signed by Hashicorp)
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

[^16]: aws_som_parameter . von_sg_d: Creation complete after Is \[Ta=/roboshop / dev/von_sg_10\]
    aws_security_group_rule. user_vpn: Creation complete after 1s \[id=sgrule-1857910311\]
    aws_security_group_rule . web_vpn: Creation complete after 1s \[id=sgrule-407654474\]
    aws_security_group_rule. mysql_vpn: Creation complete after 1s \[id=sgrule-3660259867\]
    aws_security_group_rule. cart_shipping: Creation complete after 3s \[id=sgrule-996427820\]
    aws_security_group_rule. mongodb_catalogue: Creation complete after 1s \[id=sgrule-2545274594\]
    aws_ssm_parameter . mongodb_sg_id: Creation complete after 1s \[id=/roboshop/dev/mongodb_sg_id\]
    aws_security_group_rule. cart_vpn: Creation complete after 3s \[id=sgrule-1837361287\]
    aws_security_group_rule . mongodb_user: Creation complete after 2s \[id=sgrule-687247001\]
    aws_security_group_rule . mongodb_vpn: Creation complete after 4s \[id=sgrule-2444545790\]
    Releasing state lock. This may take a few moments . . .
    Apply complete! Resources: 48 added, 0 changed, 0 destroyed.
    chowd@Chowdary MINGW64 /e/AWSDevops/Repos/roboshop-infra-dev/02-sg (main)
    1

[^17]: REPOS
    roboshop-infra-dev > 03-vpn > providers.tf > < terraform > { backend "s3" > . key
    > Ansible
    1
    terraform {
    Concepts
    2
    required_providers {
    13
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
    9
    backend "s3" {
    10
    > notes
    bucket = "chilops-terraform-s3-dev"
    11
    key
    = "vpn"
    > Robosho-shellscripts
    M
    12
    region = "us-east-1"
    > roboshop-ansible
    13
    dynamodb_table = "chilops-locking-dev"
    > roboshop-ansible-roles
    14
    roboshop-infra-dev
    15
    > 01-vpc
    16
    > 02-sg
    17
    provider "aws" {
    18
    region = "us-east-1"
    03-vpn
    19
    }
    data.tf
    U
    locals.tf
    U
    main.tf
    U
    $ openvpn.sh
    U
    providers.tf
    U
    variables.tf
    U

[^18]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos /roboshop-infra-dev (main)
    $ cd 03-vpn/
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos /roboshop-infra-dev/03-vpn (main)
    $ terraform init
    Initializing the backend...
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing modules . . .
    Downloading registry. terraform. io/terraform-aws-modules/ec2-instance/aws 5.6.1 for vpn. ..
    vpn in . terraform modules\\vpn
    Initializing provider plugins . . .
    Finding hashicorp/aws versions matching ">= 4.66.0, 5.31.0"...
    Installing hashicorp/aws v5 . 31.0. . .
    Installed hashicorp/aws v5 . 31.0 (signed by Hashicorp)
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
    chowd@Chowdary MINGW64 /e/AWSDevops/Repos/roboshop-infra-dev/03-vpn (main)

[^19]: chowd@Chowdary MINGW64 /e/AWSDevops/Repos /roboshop-infra-dev/03-vpn (main)
    $ terraform apply -auto-approve
    Acquiring state lock. This may take a few moments. . .
    module . vpn . data. aws_partition . current: Reading. . .
    data . aws_ssm_parameter . vpn_sg_id: Reading. . .
    data . aws_vpc . default: Reading. . .
    data . aws_ami . centos8: Reading. . .
    module . vpn . data. aws_partition . current: Read complete after Os \[id=aws\]
    data. aws_ami . centos8: Read complete after 1s \[id=ami-0b4f379183e570669\]
    data. aws_vpc . default: Read complete after 3s \[id=vpc-0817cae8968304c06\]
    data . aws_subnet . selected: Reading. . .
    data . aws_subnet . selected: Read complete after Os \[id=subnet-0c02fa3b6c12f822a\]

[^20]: Plan: 1 to add, 0 to change, 0 to destroy.
    module . vpn . aws_instance . this \[0\] : Creating. . .
    module . vpn . aws_instance . this \[0\]: Still creating. . .
    \[10s elapsed\]
    module . vpn . aws_instance . this \[0\]: Still creating. . .
    \[20s elapsed\]
    module . vpn . aws_instance. this \[0\]: Still creating. . .
    \[30s elapsed\]
    module . vpn . aws_instance . this \[0\]: Creation complete after 37s \[id=i-Ofec1970d05206e05\]
    Releasing state lock. This may take a few moments . . .
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
    chowd@chowdary MINGW64 /e/AWSDevops /Repos /roboshop-infra-dev/03-vpn (main)
    ST

[^21]: REPOS
    roboshop-infra-dev > 04-database > providers.of > > provider "aws" > . region
    Concepts
    1
    terraform {
    2
    required_providers {
    image.png
    13
    aws = {
    {} person.json
    M
    4
    source = "hashicorp/aws"
    person.xml
    5
    version = "5.31.0" # AWS provider version, not terraform version
    ! person.yaml
    6
    > notes
    7
    > Robosho-shellscripts
    M
    18
    19
    > roboshop-ansible
    backend "s3" {
    10
    bucket = "chilops-terraform-s3-dev"
    > roboshop-ansible-roles
    11
    key
    = "Databases"
    > roboshop-ansible-roles-tf
    12
    region = "us-east-1"
    roboshop-infra-dev
    13
    dynamodb_table = "chilops-locking-dev" -
    > 01-vpc
    14
    > 02-sg
    15
    16
    > 03-vpn
    17
    provider "aws" {
    04-database
    18
    region = "us-east-1"
    $ bootstrap.sh
    U
    19
    }
    data.tf
    U
    locals.tf
    C
    main.tf
    C
    providers.tf
    U
    variables.tf
    C

[^22]: v roboshop-ansible-roles-tf
    > dev
    > group_vars
    > prod
    > roles
    .
    ansible.cfg
    E inventory.ini
    ! main-tf.yaml
    ! main.yaml
    CCC CCC C
    variables-dev.yaml
    ! variables-prod.yaml
    !
    variables.yaml

[^23]: > notes
    18
    19
    > Robosho-shellscripts
    M
    resource "null_resource" "mongodb" {
    20
    > roboshop-ansible
    # Changes to any instance of the cluster requires re-provisioning
    21
    triggers = {
    > roboshop-ansible-roles
    22
    instance_id = module . mongodb. id
    > roboshop-ansible-roles-tf
    23
    roboshop-infra-dev
    24
    > 01-vpc
    25
    # Bootstrap script can run on any instance of the cluster
    > 02-sg
    26
    # So we just choose the first in this case
    27
    > 03-vpn
    connection {
    O
    28
    host = module . mongodb . private_ip
    04-database
    29
    type = "ssh"
    $ bootstrap.sh
    U
    30
    user = "centos"
    data.tf
    U
    31
    password = "DevOps321"
    locals.tf
    U
    32
    }
    main.tf -
    U
    33
    B4
    providers.tf
    U
    provisioner "file" {
    source
    = "bootstrap. sh"
    variables.tf
    U
    36
    destination = "/tmp/bootstrap. sh"
    Infra.png
    U
    B
    }
    readme.MD
    U
    > roboshop-terraform
    39
    provisioner "remote-exec" {
    > shellscripts
    # Bootstrap script called with private_ip of each node in the cluster
    41
    > terraform
    inline = \[
    42
    "chmod +x /tmp/bootstrap. sh",
    v terraform-aws-security-group
    43
    "sudo sh /tmp/bootstrap. sh mongodb dev"
    main.tf
    U
    4
    output.tf
    U
    45
    variables.tf
    U
    46

[^24]: push
    ansible --> nodes
    manual login, they disturb configuration
    ansible-pull --> every 30min download the configuration from git directly and run it, anyhow
    we implemented idempotency so no problem

[^25]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos (main)
    $ cd roboshop-ansible-roles-tf/
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos /roboshop-ansible-roles-tf (main)
    $ git init
    Initialized empty Git repository in E: /AWSDevops /Repos/roboshop-ansible-roles-tf/.git
    chowd@chowdary MINGW64 /e/AWSDevops/Repos /roboshop-ansible-roles-tf (main)
    $ git remote add origin git@github . com: chilops/roboshop-ansible-roles-tf. git
    chowd@Chowdary MINGW64 /e/AWSDevops /Repos /roboshop-ansible-roles-tf (main)
    $ git add . ; git commit -m "ansible roles tf"; git push origin main
    \[main (root-commit) 3d602ad\] ansible roles tf
    46 files changed, 704 insertions (+)
    create mode 100644 ansible. cfg
    create mode 100644 dev/inventory. ini
    create mode 100644 group_vars/all.yam1
    create mode 100644 inventory. ini
    create mode 100644 main-tf . yam1
    create mode 100644 main . yam1
    create mode 100644 prod/inventory . ini

[^26]: roboshop-infra-dev > 04-database > $ bootstrap.sh
    1
    #! /bin/bash
    N
    component=$1
    3
    environment=$2 #dont use env here, it is reserved in linux
    4
    yum install python3 . 11-devel python3 . 11-pip -y
    5
    pip3. 11 install ansible botocore boto3
    6
    ansible-pull -U https://github. com/chilops/roboshop-ansible-roles-tf.git -e component=$component -e env=$environment main-tf .yaml

[^27]: chowd@chowdary MINGW64 /e/AWSDevops /Repos /roboshop-infra-dev/04-database (main)
    $ terraform init -reconfigure
    Initializing the backend. ..
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing modules . . .
    Initializing provider plugins. . .
    Finding latest version of hashicorp/nul1. ..
    Finding hashicorp/aws versions matching
    ">= 3.2.0, >= 5.37.0, 5.54.1"...

[^28]: 3. 94. 212.39 \| 172. 31. 47.174 \| t2.micro \| null
    \[ centos@ip-172-31-47-174 \~ \]$ sudo su

[^29]: \[ root@ip-172-31-47-174 \~ \]# 1s -1
    total 12
    -rw-r--r--
    1 root root 2751 Jun 18 04:45 chilukuri .ovpn
    rw-
    1 root root 6096 Jun 3 05:33 original-ks. cfg
    3. 94. 212.39 \| 172. 31. 47. 174 \| t2.micro \| null
    \[ root@ip-172-31-47-174 \~ \]# cat chilukuri . ovpn
    client
    proto tcp-client
    remote 3. 94. 212. 39 1194
    dev tun
    resolv-retry infinite
    nobind
    persist-key
    persist-tun
    remote-cert-tls server
    verify-x509-name server_OUqW2NX5jJB5WGUe name
    auth SHA256
    auth-nocache
    cipher AES-128-GCM
    tls-client
    tls-version-min 1.2
    tls-cipher TLS-ECDHE-ECDSA-WITH-AES-128-GCM-SHA256
    ignore-unknown-option block-outside-dns
    setenv opt block-outside-dns # Prevent Windows 10 DNS leak
    verb 3
    <ca>

[^30]: E
    chilukuri.ovpn
    X
    +
    File
    Edit
    View
    client
    proto top-client
    remote 3.94. 212. 39 1194
    dev tun
    resolv-retry infinite
    nobind
    persist-key
    persist -tun
    remote-cert-tls server
    verify-x509-name server_OUqW2NX5jJB5W6Ue name
    auth SHA256
    auth-nocache
    cipher AES-128-GCM
    tls-client
    tls-version-min 1.2
    tls-cipher TLS-ECDHE-ECDSA-WITH-AES-128-GCM-SHA256
    ignore-unknown-option block-outside-dns
    setenv opt block-outside-dns # Prevent Windows 10 DNS leak
    verb 3
    <ca>
    - - -BEGIN CERTIFICATE - - -
    MIIB1jCCAX2gAwIBAgIUWVV/YpCK41PRSFrINIHq484QEMwwCgYIKoZIzjoEAWIW
    Hj ECMBOGALUEAwwTY25fRkply0JKSURFYjZ5emlTcTAeFweyNDA2MT gwNDQ1MzNa
    FWOZNDA2MTYWNDQ1MzNaMB4XHDAaBgNVBAMME2NUXOZKZWNCZE1ERWI2eXppu3Ew
    WTATBgcqhkjoPQIBBggghkjOPQMBBWNCAASn7SdxTL8Gh6uMJBUFyN7QODXRiREr
    SNgB9uLEuzeoSrW7GqRRZf5XXtGBE107fXdJymZIoZNi4HomJNUuY+6404GYMIGV
    MAWGA1UdEWQFMAMBAf8wHQYDVROOBBYEFGg3YhLtHNePGYd2wADOjcOfVxaSMFKG
    AlUdIwRSMFCAFGg3YhLtHNePGYd2wADOjCOfVxaSoSKKIDAeMRWWGgYDVQQDDBNj
    b19GSmVjQmRJREViNn16aVNxghRZVX9ikkTiU9FIWsg0gerjzhAQzDALBgNVHQ8E
    BAMCAQYWCgYIKoZIzjoEAWIDRWAwRAIga2510YOeuVw4QpgLbTUUdHutk7VKhbso
    jm5VrNiOycoCIBMd5zoSiRpbAe/JapbaxBPbIMpfF5wt181b1MQUqwaO
    - - - END CERTIFICATE - - - -
    </ca>
    <cert>

[^31]: OpenVPN Connect
    X
    Import Profile
    VIA URL
    UPLOAD FILE
    Drag and drop to upload .OVPN profile.
    You can import only one profile at a time.
    1 Import Profile or Certificate
    X
    -)
    < Professional (E:) > AWSDevOps
    V
    C
    Search AWSDevOps
    OVF
    Organize
    New folder
    ?
    notes
    Name
    Date modified
    Type
    Repos
    DevOps Docs
    28-04-2024 17:50
    File folder
    Screenshots
    Keys
    13-05-2024 13:05
    File folder
    AWSDevOps
    MyRecordings
    14-12-2023 10:22
    File folder
    Notepad+ +
    27-11-2023 12:48
    File folder
    BROV
    This PC
    Repos
    18-06-2024 10:44
    File folder
    Local Disk (C:)
    webpages
    02-12-2023 14:10
    File folder
    14-12-2023 10:22
    Personal (D:)
    Youtube
    File folder
    chilukuri.ovpn
    19-06-2024 09:38
    OVPN Profile
    Professional (E:)
    Google Drive (G:
    Network
    File name: chilukuri.ovpn
    Profiles and Certificates (\*.ovpn;
    Open
    Cancel

[^32]: OpenVPN Connect
    Profiles
    CONNECTED
    OpenVPN Profile
    3.94.212.39 \[chilukuri\]
    CONNECTION STATS
    2.3KB/s
    OB/S
    BYTES IN
    BYTES OUT

[^33]: null_resource . mongodb (remote-exec): ok: \[localhost\]
    null_resource . mongodb (remote-exec): TASK \[mongodb : Copy m
    null_resource . mongodb: still creating. .. \[1m50s elapsed\]
    null_resource . mongodb: still creating. .. \[2mos elapsed\]
    null_resource . mongodb: still creating. . . \[2m10s elapsed\]
    hull_resource . mongodb (remote-exec): ongodb repo\] \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* did his desk
    hull_resource . mongodb (remote-exec): changed: \[localhost\]
    null_resource . mongodb (remote-exec): TASK \[mongodb : Install mongodb \] \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*
    he he de de de de de de de de de de de de
    hull_resource . mongodb (remote-exec): changed: \[localhost\]
    null_resource . mongodb (remote-exec) : TASK \[mongodb : start and enable mongodb \] \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*#
    null_resource . mongodb (remote-exec): changed: \[localhost\]
    null_resource . mongodb (remote-exec): TASK \[mongodb : allow remote conncections\]
    null_resource . mongodb (remote-exec): changed: \[localhost\]
    null_resource . mongodb (remote-exec): TASK \[mongodb : start and enable mongodb\]
    null_resource . mongodb (remote-exec): changed: \[localhost\]
    null_resource. mongodb (remote-exec): PLAY RECAP \*\* \* \* \* \* \* does deleted # #
    null_resource . mongodb (remote-exec): localhost
    : ok=6
    changed=5
    unreachable=0
    failed=0
    skipped=0
    rescued=0
    ignored=0

[^34]: null \| 10.0. 21. 197 \| t3. small \| null
    \[ centos@ip-10-0-21-197 \~ \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    top
    0 0.0.0.0:27017
    0.0.0.0:\*
    LISTEN
    top
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp
    OoOOO
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : : :111
    :::
    LISTEN
    top6
    0
    : : : 22
    LISTEN
    null \| 10.0.21. 197 \| t3. small \| null

[^35]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/roboshop-infra-dev/04-databases (main)
    $ cd
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/roboshop-infra-dev (main)
    $ 1s -dr \*/
    04-databases// 03-vpn// 02-sg// 01-vpc//
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/roboshop-infra-dev (main)
    $ for i in 'Is -dr \*/" ; cd $i ; terraform destroy -auto-approve ; cd . . ; done
    bash: syntax error near unexpected token cd'
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/roboshop-infra-dev (main)
    $ for i in 'Is -dr \*/" ; do cd $i ; terraform destroy -auto-approve ; cd . . ; done
    Acquiring state lock. This may take a few moments.

