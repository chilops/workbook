---
title: 32Day_Terraform
uuid: 5b43ae2e-2938-11ef-98e9-b247aed906a4
version: 396
created: '2024-06-13T09:22:29+05:30'
tags:
  - terraform
---

***Topics:***

1. <mark style="background-color:#f8d616;">VPC module setup for roboshop (Please review 31day VPC complete setup)<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#f8d616;">Security Group module creation and create all security groups.<!-- {"backgroundCycleColor":"25"} --></mark>

    1. <mark>AWS SSM parameter store</mark>

    1. <mark>Create SSM parameter using terraform to get VPC ID</mark>

    1. <mark>Developing SG module</mark>

1. <mark style="background-color:#F8D616;">EC2 module - Opensource<!-- {"backgroundCycleColor":"25"} --></mark> <!-- {"offset":2} -->

1. <mark style="background-color:#F8D616;">Join Function in terraform<!-- {"backgroundCycleColor":"25"} --></mark>

1. <mark style="background-color:#F8D616;">Split function<!-- {"backgroundCycleColor":"25"} --></mark>

\

\

# <mark style="background-color:#f8914d;">**VPC module setup for roboshop (Please review 31day VPC complete setup)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Create Roboshop-terraform folder, under that 01-vpc

![](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/4dab3f5b-db5d-400b-9e3f-52e5b75f2760.png) [^1]

\

Main.tf code 

![8894d236-35ec-4d22-bffe-addaebd4887d.png|841](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/8894d236-35ec-4d22-bffe-addaebd4887d.png) [^2]

\

Variables.tf code

![63cdc67b-d861-451c-8bcc-7d1f442d2be7.png|614](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/63cdc67b-d861-451c-8bcc-7d1f442d2be7.png) [^3]

\

providers.tf code

![64e334d5-48bd-4a93-902a-a55aa7a9a2c5.png|810](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/64e334d5-48bd-4a93-902a-a55aa7a9a2c5.png) [^4]

\

```
terraform init
```

![d88786be-2ed8-4a30-96b4-eac210ec939a.png|775](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/d88786be-2ed8-4a30-96b4-eac210ec939a.png) [^5]

\

```
terraform plan
```

![6b711d90-ba7f-4337-9f5c-711f106922d0.png|924.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/6b711d90-ba7f-4337-9f5c-711f106922d0.png) [^6]

\

```
terraform apply -auto-approve
```

![937b38e1-dd56-48ff-a4bc-24603fde47f3.png|957](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/937b38e1-dd56-48ff-a4bc-24603fde47f3.png) [^7]

\

Now VPC, subnets, routes, IG, NAT gateway, elastic ip everything created. (cross check in AWS account)

![5dc54d7c-ef90-4f03-a1e1-25f0b8c68c59.png|961.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/5dc54d7c-ef90-4f03-a1e1-25f0b8c68c59.png) [^8]

\

# <mark style="background-color:#f8914d;">**Security Group module creation and create all security groups.**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

<mark>**AWS SSM parameter store**  --Its a AWS feature, simple central location storage (Like GIT)</mark>

<mark>SSM parameter is</mark> a central storage for configuration to store the configuration or pull the configuration to application.

![1c004155-e469-483b-9acb-aeac70b44b26.png|505](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/1c004155-e469-483b-9acb-aeac70b44b26.png) [^9]

\

Manual way to create (but we use it code)

![158bd617-bf4e-4359-9cd2-e0958daedca0.png|941.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/158bd617-bf4e-4359-9cd2-e0958daedca0.png) [^10]

![2b15717c-56ce-4882-9dde-bb77bcef5d56.png|1011.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/2b15717c-56ce-4882-9dde-bb77bcef5d56.png) [^11]

\

![0f7ccf8d-6564-4039-a6a5-146a314cb235.png|1020.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/0f7ccf8d-6564-4039-a6a5-146a314cb235.png) [^12]

\

Delete it.

![2d1814c7-3db2-40c4-9052-37907b3f3e2e.png|994.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/2d1814c7-3db2-40c4-9052-37907b3f3e2e.png) [^13]

\

<mark>Now to create SSM parameter using terraform to get VPC ID.</mark>

parameters.tf code

![fd862d0d-7ab2-4212-8be3-4aa3396faa6f.png|966.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/fd862d0d-7ab2-4212-8be3-4aa3396faa6f.png) [^14]

\

```
terraform plan
```

![ed53bc8c-f2d2-443a-8e5d-c6e88810d72e.png|596](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/ed53bc8c-f2d2-443a-8e5d-c6e88810d72e.png) [^15]

\

```
terraform apply -auto-approve
```

![f61f2fbd-e95c-40a5-ba0c-242e2f418655.png|867](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/f61f2fbd-e95c-40a5-ba0c-242e2f418655.png) [^16]

\

![ffb8b20c-0a66-4149-8ff9-d004e1d2c4f5.png|979.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/ffb8b20c-0a66-4149-8ff9-d004e1d2c4f5.png) [^17]

\

We can see VPC ID stored in SSM

![be9506b7-921b-4ae6-9d4e-a2c3f92dcf0a.png|913.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/be9506b7-921b-4ae6-9d4e-a2c3f92dcf0a.png) [^18]

\

\

<mark>Developing SG module</mark>

![6423049e-ecfc-4f2f-a267-b0d27e758146.png|565](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/6423049e-ecfc-4f2f-a267-b0d27e758146.png) [^19]

\

![315b5d78-ca25-4972-ad65-23dbd7bc6040.png|853](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/315b5d78-ca25-4972-ad65-23dbd7bc6040.png) [^20]

\

\

Module creation for security group. - terraform-aws-security-group

main.tf code

![b4e9e289-548e-4ee6-958b-48b661085e6f.png|968.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/b4e9e289-548e-4ee6-958b-48b661085e6f.png) [^21]

\

variables.tf code

![17f1bfc2-bb65-4cc6-a65d-14a999859a4e.png|964](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/17f1bfc2-bb65-4cc6-a65d-14a999859a4e.png) [^22]

\

output.tf code

![2ae16d69-ef58-4821-9c2f-f6edef8dfbbf.png|576](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/2ae16d69-ef58-4821-9c2f-f6edef8dfbbf.png) [^23]

\

Create SG folder for SG implementation:

![c8ea0a9c-71bb-4b71-b16e-f2ca18561e00.png|347](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/c8ea0a9c-71bb-4b71-b16e-f2ca18561e00.png) [^24]

\

main.tf code - it has almost 340+ lines check code in chilops github.

![e80f3bd2-bc90-4734-9350-b153b104f520.png|956](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/e80f3bd2-bc90-4734-9350-b153b104f520.png) [^25]

\

variables.tf code

![0c6f2f28-299e-4bad-a776-9d36022ad657.png|1108](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/0c6f2f28-299e-4bad-a776-9d36022ad657.png) [^26]

\

providers.tf code

![87a493fc-e078-4d80-9bf7-8c3bc0bdc841.png|777](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/87a493fc-e078-4d80-9bf7-8c3bc0bdc841.png) [^27]

\

parameters.tf code

![43a73ba2-b801-4d41-b9af-7c24cfaf6719.png|771](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/43a73ba2-b801-4d41-b9af-7c24cfaf6719.png) [^28]

![f221016c-aaa3-4796-a59a-b317ed876579.png|756](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/f221016c-aaa3-4796-a59a-b317ed876579.png) [^29]

\

data.tf code

![e4354dd6-29b8-46aa-aaec-de5695200c59.png|767](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/e4354dd6-29b8-46aa-aaec-de5695200c59.png) [^30]

\

```
terraform init
```

![8b279ccc-472c-4f3f-aaee-9be5d8fbbcda.png|762](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/8b279ccc-472c-4f3f-aaee-9be5d8fbbcda.png) [^31]

\

```
terraform plan
```

![2fc04005-6571-484c-a6bd-9d0403248980.png|934.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/2fc04005-6571-484c-a6bd-9d0403248980.png) [^32]

\

\

```
terraform apply -auto-approve
```

![26ae13d0-aca8-4cf5-ac03-f4ab0aa880b9.png|943](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/26ae13d0-aca8-4cf5-ac03-f4ab0aa880b9.png) [^33]

\

All SG's created including inbound rules:

![39ce57ad-255e-499e-ba20-4a1921087922.png|971.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/39ce57ad-255e-499e-ba20-4a1921087922.png) [^34]

\

# <mark style="background-color:#f8914d;">**EC2 module - Opensource**<!-- {"backgroundCycleColor":"24"} --></mark> 

![a2696443-cc72-4fc1-8715-7e52d53febfe.png|999.3333740234375](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/a2696443-cc72-4fc1-8715-7e52d53febfe.png) [^35]

![0d0c733d-4db3-4e6d-af37-4d270183a7d9.png|872](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/0d0c733d-4db3-4e6d-af37-4d270183a7d9.png) [^36]

\

check You tube video for more info...

\

# <mark style="background-color:#f8914d;">**Join Function in terraform**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![986c53a4-88b5-4e4d-9124-c3f6ca34ed89.png|702](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/986c53a4-88b5-4e4d-9124-c3f6ca34ed89.png) [^37]

![83e26f64-6652-454c-a30f-c56a746e796a.png|833](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/83e26f64-6652-454c-a30f-c56a746e796a.png) [^38]

![a7c08279-981b-4e75-89cb-3f0afc88e1a5.png|1002](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/a7c08279-981b-4e75-89cb-3f0afc88e1a5.png) [^39]

\

# <mark style="background-color:#f8914d;">**Split function**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/f3e6618c-9683-4195-af94-b0ffdd101a55.png) [^40]

![7d596fe7-2901-4bf2-b48a-f098a8503161.png|1039](https://images.amplenote.com/5b43ae2e-2938-11ef-98e9-b247aed906a4/7d596fe7-2901-4bf2-b48a-f098a8503161.png) [^41]

[^1]: v roboshop-terraform \\ 01-vpc
    > .terraform
    E .terraform.lock.hcl
    U
    main.tf
    U
    provider.tf
    C C
    variables.tf

[^2]: roboshop-terraform > 01-vpc > main.tf > ...
    1 v module "roboshop" {
    2
    #source = ". ./terraform-aws-vpc"
    13
    source = "git: :https://github.com/chilops/terraform-aws-vpc . git?ref=main"
    4
    project_name = var . project_name
    15
    environment = var . environment
    6
    common_tags = var . common_tags
    7
    vpc_tags = var . vpc_tags
    8
    9
    # public subnet
    10
    public_subnets_cidr = var . public_subnets_cidr
    11
    12
    # private subnet
    13
    private_subnets_cidr = var. private_subnets_cidr
    14
    15
    # database subnet
    16
    database_subnets_cidr = var . database_subnets_cidr
    17
    18
    # peering
    19
    is_peering_required = var. is_peering_required
    20
    21

[^3]: roboshop-terraform > 01-vpc > variables.tf > ...
    1
    variable "vpc_cidr" {
    2
    default = "10.0.0.0/16"
    3
    4
    variable "common_tags" {
    5
    default = {
    6
    Project = "roboshop"
    7
    Environment = "dev"
    8
    Terraform = "true"
    9
    10
    11
    12
    variable "vpc_tags" {
    13
    default = {}
    14
    15
    16
    variable "project_name" {
    17
    default = "roboshop"
    18
    19
    20
    variable "environment" {
    21
    default = "dev"
    22
    23
    24
    variable "public_subnets_cidr" {
    25
    default = \["10.0.1.0/24", "10.0.2.0/24"\]
    26
    27
    28
    variable "private_subnets_cidr" {
    29
    default = \["10.0.11.0/24", "10.0.12.0/24"\]
    30
    31
    32
    variable "database_subnets_cidr" {
    33
    default = \["10.0.21.0/24", "10.0.22.0/24"\]
    34
    35
    36
    variable "is_peering_required" {
    37
    default = true
    38
    }

[^4]: roboshop-terraform > 01-vpc > provider.tf > ..
    1 v terraform {
    2
    required_providers {
    3
    aws = {
    14
    source = "hashicorp/aws"
    5
    version = "5.31.0" # AWS provider version, not terraform version
    6
    7
    8
    9
    V
    backend "s3" {
    10
    bucket = "chilops-terraform-remotestate"
    11
    key
    = "vpc"__
    12
    region = "us-east-1"
    13
    dynamodb_table = "chilops-locking"
    14
    15
    16
    17 v provider "aws" {
    18
    region = "us-east-1"
    19

[^5]: PS E: \\AWSDevops \\Repos \\roboshop-terraform\\01-vpc> terraform init
    Initializing the backend. ..
    Initializing modules...
    Downloading git: :https://github.com/chilops/terraform-aws-vpc. git?ref=main for roboshop. .
    - roboshop in . terraform\\modules \\roboshop
    Initializing provider plugins. ..
    - Finding hashicorp/aws versions matching "5.31.0"...
    - Installing hashicorp/aws v5.31.0...
    Installed hashicorp/aws v5.31.0 (signed by HashiCorp)
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
    PS E: \\AWSDevops \\Repos \\roboshop-terraform\\01-vpc>

[^6]: +
    tags_all
    + "Environment" = "dev"
    "Name"
    = "roboshop-dev"
    +
    "Project"
    "roboshop"
    + "Terraform"
    "true"
    vpc_id
    = (known after apply)
    Plan: 28 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock.
    This may take
    few moments

[^7]: module . roboshop. aws_nat_gateway . main: Still creating. .. \[1m20s elapsed\]
    module . roboshop. aws_nat_gateway . main: Still creating. .. \[1m30s elapsed\]
    module. roboshop. aws_nat_gateway . main: Creation complete after 1m38s \[id=nat-086d76b16bbd580af\]
    module . roboshop. aws_route . database_route: Creating. ..
    module . roboshop. aws_route. private_route: Creating. ..
    module . roboshop. aws_route. database_route: Creation complete after 2s \[id=r-rtb-0a68f5fff360f36711080289494\]
    module . roboshop. aws_route. private_route: Creation complete after 3s \[id=r-rtb-011ff3b62c7f9a6161080289494\]
    Releasing state lock. This may take a few moments. ..
    Apply complete! Resources: 28 added, 0 changed, 0 destroyed.

[^8]: Subnets (1/12) Info
    C
    Actions
    Create subnet
    Q Find resources by attribute or tag
    <
    -
    Name
    Subnet ID
    V
    State
    4
    VPC
    4
    IPV4 CIDR
    O
    subnet-0873e3231bac49c20
    Available
    vpc-0817cae8968304c06
    172.31.64.0/20
    O
    subnet-076650bcf0b486323
    Available
    vpc-0817 cae8968304c06
    172.31.16.0/20
    O
    subnet-Od3fb051 10e2dge48
    Available
    vpc-0817cae8968304c06
    172.31.48.0/20
    roboshop-dev-database-us-east-1a
    subnet-Ofe732cd7f458ec49
    Available
    vpc-Of25f51ebd968c5a1 \| roboshop-dev
    10.0.21.0/24
    roboshop-dev-database-us-east-1b
    subnet-04f99d95aececf5f5
    Available
    vpc-Of25f51ebd968c5a1 \| roboshop-dev
    10.0.22.0/24
    roboshop-dev-private-us-east-1a
    subnet-001bffdfb602c9f9a
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.11.0/24
    roboshop-dev-private-us-east-1b
    subnet-02a4408420bfdf224
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.12.0/24
    roboshop-dev-public-us-east-1a
    subnet-Od7125a003c6b599f
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.1.0/24
    roboshop-dev-public-us-east-1b
    subnet-026041d9ff3a956d2
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.2.0/24
    0 0 0
    subnet-Od7125a003c6b599f / roboshop-dev-public-us-east-1a
    Details
    Flow logs
    Route table
    Network ACL CIDR reservations
    Sharing
    Tags
    Route table: rtb-0c49fb92bee9be21e / roboshop-dev-public
    Edit route table association
    Routes (3)
    Q Filter routes
    <
    1 >
    Destination
    Target
    172.31.0.0/16
    pcx-061e13e8388cdef4d
    10.0.0.0/16
    local
    0.0.0.0/0
    igw-0872e9371de29e673

[^9]: SSM
    parameter

[^10]: G
    https://us-east-1.console.aws.amazon.com/systems-manager/home?region=us-east-1#
    Cp
    aws
    Services
    Q Search
    \[Alt+S\]
    4
    EC2
    Route 53
    8: IAM
    VPC
    S3
    DynamoDB
    SO RDS
    Systems Manager
    Operations Management
    Explorer
    Gain Operational Insight and Take Action on AWS Resources
    OpsCenter
    CloudWatch Dashboard
    Get Started with Systems Manager
    Incident Manager
    View operational data for groups of resources, so you can quickly identify and act on any issues that might impact application
    that use those resources.
    Application Management
    Application Manager New
    AppConfig
    Parameter Store New
    How it Works

[^11]: Name
    Q /roboshop/dev/vpc_id
    X
    When naming a parameter, you can use forward slashes (/) to organize it into a hierarchy. Learn more about hierarchies \[
    Description - Optional
    This is the roboshop dev environment VPC ID
    Tier
    Parameter Store offers standard and advanced parameters.
    Standard
    O Advanced
    Store up to 10,000 standard parameters. Store parameter values up to 4
    Store up to 100,000 advanced parameters. Store parameter values up to 8
    KB. Parameter policies and sharing with other AWS accounts are not
    KB. Add parameter policies. Share with other AWS accounts. Charges apply.
    available. No additional charge.
    Standard parameters cannot be shared with other AWS accounts. Learn more
    Type
    String
    Any string value.
    O StringList
    Separate strings using commas.
    O SecureString
    Encrypt sensitive data using KMS keys from your account or another account.
    Data type
    text
    Value
    vpc

[^12]: AWS Systems Manager > Parameter Store
    My parameters
    Public parameters
    Settings
    My parameters
    C
    View details
    Edit
    Delete
    Create parameter
    Q Search
    < 1
    >
    Name
    4
    Tier
    4
    Type
    4
    Last modified
    /roboshop/dev/vpc_id
    Standard
    String
    Thu, 13 Jun 2024 04:40:16 GMT

[^13]: AWS Systems Manager > Parameter Store
    My parameters
    Public parameters
    Settings
    My parameters
    C
    View details
    Edit
    Delete
    Create
    Q Search
    Delete parameters
    X
    V
    Name
    V
    /roboshop/dev/vpc_id
    Are you sure you want to delete the parameters?
    :16 GMT
    Names
    . /roboshop/dev/vpc_id
    Cancel
    Delete parameters

[^14]: REPOS
    roboshop-terraform > 01-vpc > parameters.tf > ...
    > Ansible
    1
    resource "aws_ssm_parameter" "vpc_id" {
    Concepts
    N
    name = "/${var . project_name} /${var . environment} /vpc_id"
    3
    Ansible.MD
    M
    type = "String"
    4
    value = module . roboshop . vpc_id
    image-1.png
    5
    image.png
    16
    {} person.json
    M
    7
    resource "aws_ssm_parameter" "public_subnet_ids" {
    person.xml
    8
    name = "/${var . project_name} /${var . environment}/public_subnet_ids"
    ! person.yaml
    9
    type = "StringList"
    10
    > notes
    value = join(", ", module. roboshop . public_subnet_ids)
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    resource "aws_ssm_parameter" "private_subnet_ids" {
    > roboshop-ansible-roles
    14
    name = "/${var . project_name} /${var . environment} /private_subnet_ids"
    v roboshop-terraform
    15
    type = "StringList"
    v 01-vpc
    16
    value = join(", ", module. roboshop . private_subnet_ids)
    > .terraform
    O
    17
    18
    E .terraform.lock.hcl
    U
    19
    resource "aws_ssm_parameter" "database_subnet_ids" {
    main.tf
    U
    20
    name = "/${var . project_name} /${var . environment} /database_subnet_ids"
    parameters.tf
    U
    21
    type = "StringList"
    provider.tf
    U
    22
    value = join(", ", module. roboshop . database_subnet_ids)
    variables.tf
    U
    23
    > 02-sg
    24
    > shellscripts
    25
    26
    # output "public_subnet_ids" {
    > terraform
    27
    #
    value = module . roboshop . public_subnet_ids
    > terraform-aws-vpc
    28
    # }
    > terraform-modules

[^15]: # aws_ssm_parameter .vpc_id will be created
    +
    resource "aws_ssm_parameter" "vpc_id" {
    +
    arn
    = (known after apply)
    + data_type
    = (known after apply)
    + id
    = (known after apply)
    insecure_value = (known after apply)
    + key_id
    = (known after apply)
    + name
    = "/roboshop/dev/vpc_id"
    + tags_all
    = (known after apply)
    + tier
    = (known after apply)
    + type
    = "String"
    value
    = (sensitive value)
    + version
    = (known after apply)
    Plan: 4 to add, 0 to change, 0 to destroy.

[^16]: Plan: 4 to add, @ to change, 0 to destroy.
    aws_ssm_parameter . public_subnet_ids: Creating.. .
    aws_ssm_parameter . private_subnet_ids: Creating. . .
    aws_ssm_parameter . vpc_id: Creating. ..
    aws_ssm_parameter . database_subnet_ids: Creating...
    aws_ssm_parameter . vpc_id: Creation complete after 2s \[id=/roboshop/dev/vpc_id\]
    aws_ssm_parameter . public_subnet_ids: Creation complete after 2s \[id=/roboshop/dev/public_subnet_ids\]
    aws_ssm_parameter . private_subnet_ids: Creation complete after 2s \[id=/roboshop/dev/private_subnet_ids\]
    aws_ssm_parameter . database_subnet_ids: Creation complete after 2s \[id=/roboshop/dev/database_subnet_ids\]
    Releasing state lock. This may take a few moments...
    Apply complete! Resources: 4 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevops \\Repos \\roboshop-terraform\\01-vpc>

[^17]: AWS Systems Manager
    > Parameter Store
    My parameters
    Public parameters
    Settings
    My parameters
    G
    View details
    Edit
    Delete
    Create parameter
    Q Search
    1
    Name
    Tier
    4
    Type
    A
    Last modified
    0
    /roboshop/dev/database_subnet_ids
    Standard
    StringList
    Thu, 13 Jun 2024 05:00:11 GMT
    0
    /roboshop/dev/private_subnet_ids
    Standard
    String List
    Thu, 13 Jun 2024 05:00:11 GMT
    0
    /roboshop/dev/public_subnet_ids
    Standard
    StringList
    Thu, 13 Jun 2024 05:00:11 GMT
    /roboshop/dev/vpc_id
    Standard
    String
    Thu, 13 Jun 2024 05:00:11 GMT

[^18]: AWS Systems Manager > Parameter Store > /roboshop/dev/vpc_id > Overview
    /roboshop/dev/vpc_id
    Overview
    History
    Tags
    Parameter details
    Name
    Description
    /roboshop/dev/vpc_id
    ARN
    Data type
    7 arn:aws:ssm:us-east- 1:158724841371:parameter/roboshop/dev/vpc_id
    text
    Last modified user
    Tier
    arn:aws:iam:: 158724841371:user/terraform
    Standard
    Last modified date
    Type
    Thu, 13 Jun 2024 05:00:11 GMT
    String
    Version
    Value
    vpc-Of25f51ebd968c5a1

[^19]: Roboshop Architecture
    WEB TIER
    API TIER
    DB TIER
    CATALOGUE
    MONGODB
    CART
    WEB
    USER
    REDIS
    USER
    SHIPPING
    MY SQL
    PAYMENTS
    RABBIT MQ
    RATINGS

[^20]: sg module create and create all security groups
    roboshop-dev-mongodb
    mongodb :
    - catalogue
    - user
    source: catalogue IP address
    source sg id: sg-018af35c4f2bb2497 --> catalogue
    port: 27017
    I
    mongodb sg, catalogue sg

[^21]: REPOS
    terraform-aws-security-group > main.tf > < resource "aws_security_group" "allow_tls" > { egress > \[ \] cidr_blocks
    > Ansible
    1
    resource "aws_security_group" "allow_tis" {
    Concepts
    N
    name
    = "${var . project_name} -${var . environment}-${var . sg_name\]"
    3
    Ansible.MD
    M
    description = var . sg_description
    4
    image-1.png
    vpc_id = var . vpc_id
    5
    image.png
    6
    dynamic ingress {
    {}person.json
    M
    7
    for_each = var . sg_ingress_rules
    person.xml
    8
    content {
    ! person.yaml
    9
    description
    ingress . value\["description" \]
    > notes
    10
    from_port
    = ingress . value \["from_port" \]
    11
    > Robosho-shellscripts
    to_port
    M
    = ingress . value \["to_port" \]
    12
    protocol
    > roboshop-ansible
    ingress . value \["protocol"\]
    13
    cidr_blocks
    = ingress . value\["cidr_blocks"\]
    > roboshop-ansible-roles
    14
    > roboshop-terraform
    15
    > shellscripts
    16
    > terraform
    17
    # egress is always same for every sg, so keep egress static
    18
    v terraform-aws-security-group - .
    egress {
    19
    from_port
    main.tf
    U
    20
    to_port
    = 0
    output.tf
    U
    21
    protocol
    = "-1"
    variables.tf
    22
    cidr_blocks
    = \["0.0.0.0/0"\]
    > terraform-aws-vpc
    23
    #ipv6_cidr_blocks = \[": :/0"\]
    terraform-modules
    24
    25
    > terraform-multi-env
    26
    tags = merge(
    > terraform-provisioners
    27
    var . common_tags,
    > vpc-test
    28
    var . sg_tags,
    29
    30
    Name = "${var . project_name} -${var . environment}-${var . sg_name}"
    31
    32
    33
    34
    35

[^22]: REPOS
    terraform-aws-security-group > variables.tf > $ variable "sg_tags" > 8 default
    > Ansible
    1
    variable "project_name" {
    Concepts
    2
    3
    Ansible.MD
    M
    }
    14
    variable "environment" {
    image-1.png
    15
    image.png
    6
    }
    {} person.json
    M
    7
    variable "sg_name" {
    person.xml
    18
    #default = mongodb
    ! person.yaml
    9
    }
    10
    notes
    variable "common_tags" {
    11
    > Robosho-shellscripts
    default = {}
    M
    12
    type = map
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    variable "sg_tags" {
    > roboshop-terraform
    15
    default = {}
    > shellscripts
    16
    type = map
    > terraform
    17
    }
    18
    terraform-aws-security-group -
    variable "vpc_id" {
    O
    19
    main.tf
    U
    20
    }
    output.tf
    U
    21
    variable "sg_description" {
    variables.tf -
    U
    22
    #default = ""
    > terraform-aws-vpc
    23
    type = string
    > terraform-modules
    24
    }
    25
    > terraform-multi-env
    variable "sg_ingress_rules" {
    26
    type = list
    > terraform-provisioners
    27
    default = \[\]
    > vpc-test
    28

[^23]: terraform-aws-security-group > output.tf > % output "sg_id"
    1
    output "sg_id" {
    2
    value = aws_security_group . allow_tls.id
    3

[^24]: v roboshop-terraform
    > 01-vpc
    02-sg
    data.tf
    main.tf
    parameters.tf
    C CC CC
    provider.tf
    variables.tf
    > shellscripts

[^25]: REPOS
    roboshop-terraform > 02-sg > \\main.tf > < module "mongodb"
    > Ansible
    module "vpn" {
    Concepts
    2
    source
    . ./terraform-aws-security-group"
    3
    Ansible.MD
    M
    project_name
    = var . project_name
    4
    environment
    = var . environment
    image-1.png
    5
    sg_description = "SG for VPN"
    image.png
    6
    vpc_id
    = data . aws_vpc . default.id
    person. json
    M
    7
    sg_name
    = "vpn"
    person.xml
    8
    #sg_ingress_rules = var . mongodb_sg_ingress_rules
    ! person.yaml
    9
    10
    notes
    11
    > Robosho-shellscripts
    module "mongodb" {
    M
    12
    source
    E
    / . ./terraform-aws-security-group"
    > roboshop-ansible
    13
    project_name
    = var . project_name
    > roboshop-ansible-roles
    14
    environment
    = var . environment
    roboshop-terraform
    15
    sg_description = "SG for MongoDB"
    > 01-vpc
    16
    vpc_id
    = data . aws_ssm_parameter . vpc_id . value
    v 02-sg
    17
    sg_name
    = "mongodb"
    18
    data.tf
    U
    #sg_ingress_rules = var . mongodb_sg_ingress_rules
    19
    main.tf
    U
    20

[^26]: REPOS
    roboshop-terraform > 02-sg > variables.tf > % variable "mongodb_sg_ingress_rules"
    > Ansible
    1
    variable "common_tags" {
    Concepts
    N
    default = {
    13
    Ansible.MD
    M
    Project
    "roboshop"
    4
    Environment = "dev"
    image-1.png
    Terraform
    = "true"
    image.png
    16
    {} person.json
    M
    7
    person.xml
    8
    ! person.yaml
    9
    variable "sg_tags" {
    10
    > notes
    O
    default = {}
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    variable "project_name" {
    > roboshop-ansible-roles
    14
    default = "roboshop"
    v roboshop-terraform
    15
    > 01-vpc
    O
    16
    variable "environment" {
    02-sg
    17
    default = "dev"
    18
    data.tf
    U
    19
    main.tf
    U
    20
    variable "mongodb_sg_ingress_rules" {
    parameters.tf
    U
    21
    default = \[
    provider.tf
    U
    22
    variables.tf
    U
    23
    description = "Allow port 80"
    > shellscripts
    24
    from_port
    = 80 # 0 means all ports
    25
    > terraform
    to_port
    = 80
    26
    protocol
    : "tcp"
    > terraform-aws-security-group
    27
    cidr_blocks = \["0.0.0.0/0"\]
    > terraform-aws-vpc
    28
    > terraform-modules
    29
    > terraform-multi-env
    30
    description = "Allow port 443"
    > terraform-provisioners
    31
    from_port
    = 443 # 0 means all ports
    > vpc-test
    32
    to_port
    443
    33
    protocol
    = "tcp"
    34
    cidr_blocks = \["0.0.0.0/0"\]
    35
    36
    37

[^27]: roboshop-terraform > 02-sg > provider.tf > @ provider "aws"
    terraform {
    2
    required_providers {
    3
    aws = {
    14
    source = "hashicorp/aws"
    5
    version = "5.31.0" # AWS provider version, not terraform version
    16
    7
    8
    backend "s3" {
    10
    bucket = "chilops-terraform-remotestate"
    11
    key
    = "sg"-
    12
    region = "us-east-1"
    13
    dynamodb_table = "chilops-locking"
    14
    15
    16
    17
    provider "aws" {
    18
    region = "us-east-1"
    19

[^28]: roboshop-terraform > 02-sg > parameters.tf > ...
    resource "aws_ssm_parameter" "vpn_sg_id" {
    2
    name
    = "/${var . project_name} /${var . environment}/vpn_sg_id"
    3
    type
    = "String"
    4
    value = module . vpn . sg_id
    15
    16
    7
    resource "aws_ssm_parameter" "mongodb_sg_id" {
    18
    name
    = "/${var . project_name}/${var . environment}/mongodb_sg_id"
    19
    type
    = "String"
    10
    value = module . mongodb . sg_id
    11
    12
    13
    resource "aws_ssm_parameter" "redis_sg_id" {
    14
    name = "/${var . project_name}/${var . environment}/redis_sg_id"
    15
    type = "String"
    16
    value = module . redis . sg_id
    17
    18
    19
    resource "aws_ssm_parameter" "mysql_sg_id" {
    20
    name
    = "/${var . project_name}/${var . environment}/mysql_sg_id"
    21
    type
    = "String"
    22
    value = module. mysql . sg_id
    23
    24
    25
    resource "aws_ssm_parameter" "rabbitmq_sg_id" {
    26
    name
    = "/${var . project_name} /${var . environment}/rabbitmq_sg_id"
    27
    type
    = "String"
    28
    value = module . rabbitmq . sg_id
    29
    30
    31
    resource "aws_ssm_parameter" "catalogue_sg_id" {
    32
    name
    = "/${var . project_name}/${var . environment}/catalogue_sg_id"
    33
    type
    = "String"
    34
    value = module . catalogue . sg_id
    35
    36
    37
    resource "aws_ssm_parameter" "user_sg_id" {
    38
    name
    = "/${var . project_name}/${var . environment}/user_sg_id"
    39
    type
    = "String"
    40
    value = module . user . sg_id
    41
    42
    43
    resource "aws_ssm_parameter" "cart_sg_id" {
    44
    name = "/${var . project_name} /${var . environment}/cart_sg_id"

[^29]: 45
    type = "String"
    46
    value = module . cart . sg_id
    47
    48
    49
    resource "aws_ssm_parameter" "shipping_sg_id" {
    50
    name = "/${var . project_name} /${var . environment} /shipping_sg_id"
    51
    type = "String"
    52
    value = module . shipping . sg_id
    53
    54
    55
    resource "aws_ssm_parameter" "payment_sg_id" {
    56
    name = "/${var . project_name}/${var . environment} /payment_sg_id"
    57
    type = "String"
    58
    value = module . payment . sg_id
    59
    60
    61
    resource "aws_ssm_parameter" "web_sg_id" {
    62
    name
    = "/${var . project_name} /${var . environment}/web_sg_id"
    63
    type = "String"
    64
    value = module . web . sg_id
    65

[^30]: roboshop-terraform > 02-sg > \\data.tf > { data "aws_vpc" "default"
    1
    data "aws_ssm_parameter" "vpc_id" {
    2
    name = "/${var . project_name} /${var . environment} /vpc_id"
    3
    4
    15
    data "aws_vpc" "default" {
    6
    default = true
    7

[^31]: PS E: \\AWSDevops \\Repos \\roboshop-terraform> cd . \\02-sg\\
    PS E: \\AWSDevOps \\Repos \\roboshop-terraform\\02-sg> terraform init
    Initializing the backend. ..
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing provider plugins. ..
    Finding hashicorp/aws versions matching "5.31.0"...
    Installing hashicorp/aws v5. 31.0...
    Installed hashicorp/aws v5.31.0 (signed by HashiCorp)
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
    PS E: \\AWSDevops \\Repos \\roboshop-terraform\\02-sg> \|

[^32]: id
    = (known after apply)
    ingress
    = (known after apply)
    +
    name
    = "roboshop-dev-web"
    + name_prefix
    = (known after apply)
    + owner_id
    = (known after apply)
    + revoke_rules_on_delete = false
    +
    tags
    "Name" = "roboshop-dev-web"
    + tags_all
    + "Name" = "roboshop-dev-web"
    + vpc_id
    = (sensitive value)
    Plan: 48 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock. This may take a few moments. .
    PS E: \\AWSDevops \\Repos \\roboshop-terraform \\02-sg>

[^33]: aws_security_group_rule. mongodb_catalogue: Creation complete after 1s \[id=sgrule-1936917450\]
    aws_security_group_rule. shipping_web: Creation complete after 2s \[id=sgrule-1859897517\]
    aws_ssm_parameter .web_sg_id: Creation complete after is \[id=/roboshop/dev/web_sg_id\]
    aws_security_group_rule. catalogue_vpn: Creation complete after 2s \[id=sgrule-3505387814\]
    aws_security_group_rule. web_internet: Creation complete after 1s \[id=sgrule-498341481\]
    aws_security_group_rule. payment_web: Creation complete after 2s \[id=sgrule-1290393744\]
    aws_security_group_rule.mysql_shipping: Creation complete after 3s \[id=sgrule-1547425910\]
    aws_security_group_rule. cart_web: Creation complete after 2s \[id=sgrule-3425274928\]
    aws_security_group_rule. catalogue_web: Creation complete after 4s \[id=sgrule-1714566863\]
    aws_security_group_rule.web_vpn: Creation complete after 3s \[id=sgrule-2670119841\]
    Releasing state lock. This may take a few moments.. .
    Apply complete! Resources: 48 added, 0 changed, 0 destroyed.
    PS E: \\AWSDevops\\Repos \\roboshop-terraform\\02-sg>

[^34]: Security Groups (1/15) Info
    C
    Actions V
    Export security groups to CSV
    Create security group
    Q Find resources by attribute or tag
    1 >
    -
    Name
    Security group ID
    4
    Security group name
    4
    VPC ID
    zy VOUS I TVTOUTVOUTO I
    roboshop-dev-cart
    sg-057652f682f0996 76
    roboshop-dev-cart
    vpc-Of25f5 1ebd968c5a1 \[
    0
    roboshop-dev-catalogue
    sg-0aab61d6afb352036
    roboshop-dev-catalogue
    vpc-Of25f5 1ebd968c5a1 \[Z
    0
    roboshop-dev-mongodb
    sg-0b6d834e82fc45bad
    roboshop-dev-mongodb
    vpc-Of25f5 1ebd968c5a1 \[Z
    O
    roboshop-dev-mysql
    sg-Ocd7f8f65da6e129a
    roboshop-dev-mysql
    vpc-Of25f51ebd968c5a1 \[Z
    O
    roboshop-dev-payment
    sg-0e6b6c32d3ae0023b
    roboshop-dev-payment
    vpc-Of25f5 1ebd968c5a1 \[2
    roboshop-dev-rabbitmq
    sg-0a 11bccf33d1a5ef4
    roboshop-dev-rabbitmq
    vpc-Of25f51ebd968c5a1 \[
    80 0
    Inbound rules (4)
    C
    Manage tags
    Edit inbound rules
    Q Search
    < 1 >
    O
    Name
    4
    Security group rule... V IP version
    Type
    Protocol
    A
    Port range
    sgr-041cla645c58962DI
    Custom ICP
    ICP
    8080
    0
    sgr-06ef3ec5272293036
    Custom TCP
    TCP
    8080
    O
    sgr-03d269ce8a089bbaa
    SSH
    TCP
    22
    sgr-Of834371822ae2d50
    Custom TCP
    TCP
    8080

[^35]: C
    registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance
    Terraform Registry
    Q Search all resources
    Browse
    Publish v Sign-in
    Providers / hashicorp
    aws
    Version 5.32.0
    Latest Version
    aws
    Q
    Overview
    AWS DOCUMENTATION
    Resource: aws_instance
    Q Filter
    Provides an EC2 instance resource. This allows instances to be created, updated, and deleted.
    Instances also support provisioning.
    aws provider

[^36]: github.com/terraform-aws-modules/terraform-aws-ec2-instance
    README
    Code of conduct 81 Apache-2.0 license . Security
    E
    Single EC2 Instance
    module "ec2_instance" {
    source = "terraform-aws-modules/ec2-instance/aws"
    name = "single-instance"
    instance_type
    = "t2.micro"
    key_name
    = "user1"
    monitoring
    = true
    vpc_security_group_ids = \["sg-12345678"\]
    subnet_id
    = "subnet-eddcdzz4"
    tags = {
    Terraform = "true"
    Environment = "dev"
    up
    Multiple EC2 Instance

[^37]: join produces a string by concatenationg all of the elements of the specified list of strings with
    the specified separator.
    join(separator, list)
    Copy O
    Examples
    > join("-", \["foo", "bar", "baz"\])
    Copy
    "foo-bar-baz"
    > join(", ", \["foo", "bar", "baz" \])
    foo, bar, baz
    > join(", ", \["foo"\])
    foo

[^38]: resource "aws_ssm_parameter" "public_subnet_ids" {
    name = "/${var . project_name} /${var . environment}/public_subnet_ids"
    type = "StringList"
    value = join(", ", module. roboshop. public_subnet_ids)

[^39]: sbnr-1234, sbnt-3456 --> for AWS it is list, but for us it is string

[^40]: split Function
    v1.6.x (latest) v
    split produces a list by dividing a given string at all occurrences of a given separator.
    split(separator, string)
    Copy
    Examples
    > split(", ", "foo, bar, baz")
    Copy
    "foo",
    "bar",
    "baz",
    split(",", "foo")
    "foo",
    > split(", ", "")

[^41]: roboshop-terraform > 04-ec2 > locals.tf > { locals > \[\] database_subnet_id
    1
    locals {
    2
    ec2_name = "${var . project_name}-$ {var . environment}"
    3
    database_subnet_id = element(split(",", data. aws_ssm_parameter . database_subnet_ids) , 0)
    4

