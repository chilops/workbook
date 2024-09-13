---
title: 54Day_Kubernetes
uuid: e1fadbfa-3e81-11ef-8de4-6ef34fa959ce
version: 246
created: '2024-07-10T11:31:43+05:30'
tags:
  - kubernetes
---

\

# <mark style="background-color:#f8914d;">**AWS EKS Workflow**<!-- {"backgroundCycleColor":"24"} --></mark>

![e0d0c567-3624-4f86-ae55-d498c9d29102.png|748](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/e0d0c567-3624-4f86-ae55-d498c9d29102.png) [^1]

\

# <mark style="background-color:#f8914d;">**Installing Minikube**<!-- {"backgroundCycleColor":"24"} --></mark>

installing minikube

![b4648dd8-0f86-4953-9d4a-69dc9f1a8fa6.png|1000.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/b4648dd8-0f86-4953-9d4a-69dc9f1a8fa6.png) [^2]

\

```
terraform init
```

```
terraform apply -auto-approve
```

![7b472fbe-6dce-407c-8e85-f1d791cd6f9a.png|721](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/7b472fbe-6dce-407c-8e85-f1d791cd6f9a.png) [^3]

\

# <mark style="background-color:#f8914d;">**Installing EKSCTL**<!-- {"backgroundCycleColor":"24"} --></mark>

![f8b80a57-9ad3-4bec-a7b3-f11b2fc1da9e.png|969.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/f8b80a57-9ad3-4bec-a7b3-f11b2fc1da9e.png) [^4]

![30800493-99ab-4bda-a9fb-134cce967adf.png|968](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/30800493-99ab-4bda-a9fb-134cce967adf.png) [^5]

\

Installing eksctl

![ff5e3674-7812-4f7b-8e2c-8f9f4b07bee8.png|971.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/ff5e3674-7812-4f7b-8e2c-8f9f4b07bee8.png) [^6]

\

```
terraform init
terraform apply -auto-approve
```

![5cacd757-c20c-4ec1-8226-1f8da9ee98dc.png|962](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/5cacd757-c20c-4ec1-8226-1f8da9ee98dc.png) [^7]

\

![368b2405-e28f-4776-a1ab-b6312a8e7dcb.png|894](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/368b2405-e28f-4776-a1ab-b6312a8e7dcb.png) [^8]

\

workstation for eksctl

![27ea654b-5afc-4072-9638-db13c19eb68b.png|1052](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/27ea654b-5afc-4072-9638-db13c19eb68b.png) [^9]

\

to check kubectl & eksctl versions

```
kubectl version
```

```
eksctl 
```

![76d4be5c-eb85-4f1b-bb6b-af51658d877a.png|1038](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/76d4be5c-eb85-4f1b-bb6b-af51658d877a.png) [^10]

\

# <mark style="background-color:#f8914d;">**Creating Cluster Nodes**<!-- {"backgroundCycleColor":"24"} --></mark> 

spot instance use only for testing purposes, not to use in production

![bcea89bb-46e9-4bf4-bade-579e387d66c6.png|739](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/bcea89bb-46e9-4bf4-bade-579e387d66c6.png) [^11]

![7e5ea601-eba6-40ad-b72a-baff31fa813f.png|938.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/7e5ea601-eba6-40ad-b72a-baff31fa813f.png) [^12]

\

create repo

![78f68381-23a2-48c4-b9e2-a8007e46ce15.png|962.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/78f68381-23a2-48c4-b9e2-a8007e46ce15.png) [^13]

```
git init
git remote add origin <repo name>
```

![](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/274c660b-cdbb-4fb5-81d8-fde28c07756c.png) [^14]

\

if you get below error..

```
git add . ; git commit -m "eksctl"; git push origin main
```

```
rm -rf .git
```

![d244d603-d479-4fb1-ab4f-d920cad2682b.png|1066.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/d244d603-d479-4fb1-ab4f-d920cad2682b.png) [^15]

\

add .gitignore file

![5a0a380d-71ff-4735-b45f-3affd3517b3a.png|411](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/5a0a380d-71ff-4735-b45f-3affd3517b3a.png) [^16]

\

```
git init
git remote add origin <repo name>
git add . ; git commit -m "eksctl"; git push origin main
```

![06a353e1-e354-4f9a-a37a-528aa67a288c.png|863.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/06a353e1-e354-4f9a-a37a-528aa67a288c.png) [^17]

\

Now cloning on workstation

```
git clone <repo name>
```

![04fcc7b9-63c8-471c-b25f-278e919fcd20.png|931.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/04fcc7b9-63c8-471c-b25f-278e919fcd20.png) [^18]

\

![cf580de8-ae57-4287-84e5-212d6d8c1ac3.png|885](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/cf580de8-ae57-4287-84e5-212d6d8c1ac3.png) [^19]

\

creating cluster node.. but gets below error... we need to give IAM access

```
eksctl create cluster --config-file=eks.yaml
```

![](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/2855378d-6deb-4696-9351-d7f25d8990e3.png) [^20]

\

```
aws configure
```

![b3bceba3-ebf0-4439-b262-837b3bdf8703.png|1089](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/b3bceba3-ebf0-4439-b262-837b3bdf8703.png) [^21]

\

```
eksctl create cluster --config-file=eks.yaml
```

![78251f32-7f61-4c41-a263-b55b37199806.png|1009.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/78251f32-7f61-4c41-a263-b55b37199806.png) [^22]

\

its creating new vpc

![c39a20ff-d009-4060-a56e-18e574c3e109.png|946.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/c39a20ff-d009-4060-a56e-18e574c3e109.png) [^23]

\

cluster will create here  AWS EKS (Elastic Kubernetes service)

![ed05057a-9cdb-4279-b1b4-802a768d50c7.png|1079.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/ed05057a-9cdb-4279-b1b4-802a768d50c7.png) [^24]

\

```
kubectl get nodes
```

![5f07cf37-c687-4085-aa7a-73bfd4708fdb.png|858](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/5f07cf37-c687-4085-aa7a-73bfd4708fdb.png) [^25]

![6b254106-ec1e-4a20-a500-4ae347f72939.png|973.3333740234375](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/6b254106-ec1e-4a20-a500-4ae347f72939.png) [^26]

In workstation we installed docker, kubectl and eksctl

![](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/aaece534-5d66-405f-8ab8-a83f2029b6d1.png) [^27]

\

\

[^1]: XI
    AWS Account
    Spot NodeGroup
    K
    Amazon EKS
    kubectl
    docked
    WOOK Tip
    Star

[^2]: EXPLORER
    ... ulti-container.yaml
    ! 03-labels.yaml
    ! 04-annotations.yaml
    ! 05-env.yaml
    $ docker.sh M X
    REPOS
    terraform-aws-minikube > $ docker.sh
    > roboshop-infra-prod
    45
    systemctl start docker
    > roboshop-shared-library
    46
    > roboshop-shell
    47
    VALIDATE $? "Started docker"
    > roboshop-terraform
    48
    49
    systemctl enable docker
    > shell-script
    50
    > students-interview-questions
    51
    VALIDATE $? "Enabled docker"
    > terraform
    52
    terraform-aws-minikube
    53
    usermod -aG docker centos
    > .terraform
    54
    .gitignore
    55
    VALIDATE $? "added centos user to docker group"
    56
    E.terraform.lock.hcl
    57
    echo -e "$R Logout and login again $N"
    $ docker.sh
    M
    58
    minikube.tf
    59
    curl -LO "https://dl. k8s . io/release/$(curl -L -s https://dl.k8s. io/release/stable.
    provider.tf
    txt)/bin/linux/amd64/kubect\]"
    workstation.tf
    60
    > terraform-aws-security-group
    61
    chmod +x kubectl
    62
    > terraform-aws-vpc
    63
    mv kubectl /usr/local/bin/kubectl
    > terraform-modules
    64
    > terraform-multi-env
    65
    VALIDATE $? "Kubectl installation"

[^3]: user@AshDexter-T480 MINGW64 \~
    S cd /c/devops/daws-76s/repos/terraform-aws-minikube/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-minikube (main)
    S terraform init
    Initializing the backend. ..

[^4]: EXPLORER
    . . .
    nnotations.yaml
    ! 05-env.yaml
    $ docker.sh M
    workstation.tf k8-eksctl
    provide
    V REPOS
    k8-eksctl > provider.tf
    > .github
    1
    terraform {
    ansible
    2
    required_providers {
    3
    > catalogue
    aws = {
    4
    source = "hashicorp/aws"
    > catalogue-deploy
    5
    version = "5.31.0" # AWS provider version, not terraform version
    > concepts
    6
    > dockerfiles
    7
    k8-eksctl
    8
    provider.tf
    9
    backend "s3" {
    workstation.tf
    10
    bucket = "daws76s-remote-state"
    11
    key
    = "eksctl"
    > k8-resources
    12
    region = "us-east-!"
    > learn-git
    13
    dynamodb_table = "daws76s-locking"
    > learn-jenkins
    14
    notes
    15
    > roboshop-ansible
    16
    > roboshop-ansible-roles
    17
    provider "aws" {
    18
    > roboshop-ansible-roles-tf
    region = "us-east-1"
    19
    > roboshop-docker

[^5]: V REPOS
    k8-eksctl > workstation.tf
    > .github
    1
    module "ec2_instance" {
    > ansible
    2
    source = "terraform-aws-modules/ec2-instance/aws"
    3
    > catalogue
    4
    name = "workstation"
    > catalogue-deploy
    5
    ami = data. aws_ami . centos8. id
    > concepts
    6
    instance_type
    = "t2.micro"
    > dockerfiles
    7
    #key_name
    = "user1"
    k8-eksctl
    8
    #monitoring
    = true
    provider.tf
    19
    vpc_security_group_ids = \[aws_security_group. allow_minikube. id \]
    workstation.tf
    10
    subnet id
    = "subnet-0ea509ad4cba242d7" #replace your default subnet id
    11
    user_data = file("docker . sh")
    > k8-resources
    12
    tags = {
    > learn-git
    13
    Terraform
    = "true"
    > learn-jenkins
    14
    Environment = "dev"
    > notes
    15
    > roboshop-ansible
    16
    I
    > roboshop-ansible-roles
    17
    18
    > roboshop-ansible-roles-tf
    resource "aws_security_group" "allow_minikube" {
    19
    name
    = "allow_minikube"
    > roboshop-docker
    20
    description = "created for minikube"
    > roboshop-documentation
    21
    tags = {
    > roboshop-infra-dev
    22
    Name = "allow_minikube"
    > roboshop-infra-prod
    23
    > OUTLINE
    24

[^6]: EXPLORER
    . . .
    innotations.yaml
    ! 05-env.yaml
    $ docker.sh M
    workstation.tf k8-eksctl
    $ workstation.sh X
    REPOS
    k8-eksctl > $ workstation.sh
    > .github
    55
    usermod -aG docker centos
    > ansible
    56
    > catalogue
    57
    VALIDATE $? "added centos user to docker group"
    > catalogue-deploy
    58
    concepts
    59
    echo -e "$R Logout and login again $N"
    > dockerfiles
    60
    61
    k8-eksctl
    curl -LO "https://dl. k8s . io/release/$(curl -L -s https://dl.k8s. io/release/stable. txt
    62
    provider.tf
    63
    chmod +x kubectl
    $ workstation.sh
    64
    workstation.tf
    65
    mv kubectl /usr/local/bin/kubectl
    k8-resources
    66
    > learn-git
    67
    VALIDATE $? "Kubectl installation"
    68
    > learn-jenkins
    69
    curl -sLO "https://github. com/eksct1-io/eksctl/releases/latest/download/eksctl_$PLATF
    notes
    70
    > roboshop-ansible
    71
    tar -xzf eksctl_$PLATFORM. tar. gz -C /tmp && rm eksctl_$PLATFORM. tar . gz
    > roboshop-ansible-roles
    72
    > roboshop-ansible-roles-tf
    73
    sudo mv /tmp/eksctl /usr/local/bin\|
    > roboshop-docker

[^7]: user@AshDexter-T480 MINGW64 \~
    $ cd /c/devops/daws-76s/repos/k8-eksct1/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1
    $ terraform init
    Initializing the backend. . .
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.

[^8]: Instances (1/2) Info
    C
    Connect
    Instan
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    -
    Name
    4
    Instance ID
    Instance state
    4
    Instance type
    workstation
    i-0353ded40f9c04af3
    Running Q Q
    t2.micro
    workstation-eksctl
    i-080ed32fOdd303fef
    Running Q Q
    t2.micro
    Instance: i-080ed32fOdd303fef (workstation-eksctl)
    Details
    Status and alarms New
    Monitoring Security
    Networking
    Storage
    Tags
    Public IPv4 address copi
    Instance summary Info
    ed
    Instance ID
    i-080ed32fOdd303fef (workstation-eksctl)
    44.211.173.150 \|open address \[Z

[^9]: Protocol SSH
    . Host 44.211.173.150
    Login
    Password
    Session centos-8
    TO X
    Commands
    44.211.173.150
    44 . 211 . 173.150 \| 172. 31. 94.147 \| t2.micro \| null
    \[ centos(ip-172-31-94-147 \~ \]$ k

[^10]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ kubectl version
    Client Version: v1 . 29.2
    Kustomize Version: v5. 0. 4-0. 20230601165947-6ce0bf390ce3
    The connection to the server localhost: 8080 was refused - did you specify th
    44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ eksctl

[^11]: spot
    on demand instances
    10000 CPU, 100000 TB HD
    8000 CPU, 8000 TB
    2000CPU, 2000TB
    spot instances --> 70% discount of normal
    2minutes notice, they will take back instances

[^12]: REPOS
    k8-eksctl > ! eks.yaml > \[ \] managedNodeGroups > {} 0 > spot
    > ansible
    1
    apiVersion: eksctl. io/vlalpha5
    > catalogue
    2
    kind: ClusterConfig
    3
    > catalogue-deploy
    4
    metadata:
    > concepts
    5
    name: roboshop
    > dockerfiles
    6
    region: us-east-1
    k8-eksctl
    7
    > .terraform
    8
    managedNodeGroups :
    E .terraform.lock.hel
    9
    name : spot
    ! eks.yaml
    10
    instanceType: m5 . large
    11
    desiredCapacity: 3
    provider.tf
    12
    spot: true
    $ workstation.sh
    workstation.tf

[^13]: C
    25 github.com/new
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    - daws-76s
    k8-eksctl
    k8-eksctl is available.
    Great repository names are short and memorable. Need inspiration? How about stunning-bassoon ?
    Description (optional)
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    O
    Private

[^14]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/k8-eksct1/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1 (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1 (main)
    $ git remote add origin git@github. com: daws-76s/k8-eksct1.git

[^15]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1 (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    warning: in the working copy of ' . terraform. lock.hc1', LF will be replaced by CRLF the next time Git touches it
    warning: adding embedded git repository: . terraform/modules/ec2_instance
    hint: You've added another git repository inside your current repository.
    hint: Clones of the outer repository will not contain the contents of
    hint: the embedded repository and will not know how to obtain it.
    hint: If you meant to add a submodule, use:
    hint:
    hint:
    git submodule add <ur1> . terraform/modules/ec2_instance
    hint:
    hint: If you added this path by mistake, you can remove it from the
    hint: index with:
    hint:
    hint:
    git rm --cached . terraform/modules/ec2_instance
    hint:
    hint: See "git help submodule" for more information.
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksctl (main)
    $ rm -rf . git

[^16]: > dockerfiles
    k8-eksctl
    > .terraform
    gitignore
    E .terraform.lock.hcl
    ! eks.yaml
    provider.tf
    $ workstation.sh
    workstation.tf
    > k8-resources

[^17]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/k8-eksct1/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1 (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksctl (main)
    $ git remote add origin git@github. com: daws-76s/k8-eksctl. git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksctl (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    warning: in the working copy of ' . terraform. lock.hcl', LF will be replaced by CRLF the next time Git touches it
    warning: in the working copy of 'workstation. sh' , LF will be replaced by CRLF the next time Git touches it
    \[main (root-commit) 324e09f\] jenkins
    6 files changed, 222 insertions (+)
    create mode 100644 . gitignore
    create mode 100644 . terraform. lock.hc1
    create mode 100644 eks. yam1

[^18]: Commands
    44.211.173.150
    44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2. micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ git clone https: //github. com/daws-76s/k8-eksctl . git

[^19]: 44 . 211 . 173.150 \| 172. 31. 94.147 \| t2.micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ cd k8-eksctl/
    44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2. micro \| https: //github.com/
    \[ centos@ip-172-31-94-147 \~/k8-eksctl \]$ 1s
    eks . yaml provider. tf workstation. sh workstation. tf

[^20]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-eksctl . git
    \[ centos@ip-172-31-94-147 \~/k8-eksctl \]$ eksctl create cluster --config-file=eks. yaml
    Error: checking AWS STS access - cannot get role ARN for current session: operation error STS: GetCallerIdentity, get identity: get cre
    dentials: failed to refresh cached credentials, no EC2 IMDS role found, operation error ec2imds: GetMetadata, http response error Statu
    sCode: 404, request to EC2 IMDS failed

[^21]: 44 . 211 . 173.150 \| 172. 31 .94.147 \| t2.micro \| https: //github. com/daws-76s/k8-eksct
    \[ centos@ip-172-31-94-147 \~/k8-eksctl \]$ aws configure
    AWS Access Key ID \[None\] :

[^22]: 44 . 211 . 173. 150 \| 172. 31 .94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-eksctl . git
    \[ centos@ip-172-31-94-147 \~/k8-eksctl \]$ eksctl create cluster --config-file=eks . yaml
    2024-02-22 02:15:10 \[\[\]
    eksctl version 0.171.0
    2024-02-22 02:15:10 \[0\]
    using region us-east-1
    2024-02-22 02:15:10 \[0\]
    skipping us-east-le from selection because it doesn't support the following instance ty
    2024-02-22 02:15:10 \[\[\]
    setting availability zones to \[us-east-1d us-east-1f\]
    2024-02-22 02:15:10 \[0\]
    subnets for us-east-1d - public: 192. 168.0.0/19 private: 192. 168. 64.0/19
    2024-02-22 02:15:10 \[0\]
    subnets for us-east-1f - public: 192. 168.32.0/19 private: 192 . 168 . 96.0/19
    2024-02-22 02:15:10 \[0\]
    nodegroup "spot" will use "" \[AmazonLinux2/1.27\]
    2024-02-22 02:15:10 \[\[\]
    using Kubernetes version 1.27
    2024-02-22 02:15:10 \[0\]
    creating EKS cluster "roboshop" in "us-east-1" region with managed nodes
    2024-02-22 02:15:10 \[\[\]
    1 nodegroup (spot) was included (based on the include/exclude rules)
    2024-02-22 02:15:10 \[\[\]
    will create a CloudFormation stack for cluster itself and 0 nodegroup stack (s)
    2024-02-22 02:15:10 \[0\]
    will create a CloudFormation stack for cluster itself and 1 managed nodegroup stack (s)
    2024-02-22 02:15:10 \[\[\]
    if you encounter any issues, check CloudFormation console or try 'eksctl utils describe
    t-1
    --cluster=roboshop'

[^23]: F
    C
    us-east-1.console.aws.amazon.com/vpcconsole/home?region=us-east-1#vpcs:
    aws
    Services
    Q Search
    \[Alt+S\]
    CO VPC
    303 RDS
    $3
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    EFS
    LAM
    EC2
    Certificate Manager
    CloudFront
    Billing and C
    VPC dashboard
    X
    Your VPCs (2) Info
    C
    EC2 Global View CZ
    Q Search
    Filter by VPC:
    O
    Name
    VPC ID
    State
    IPV4 CIDR
    D IP
    Select a VPC
    vpc-03dae0a05234cdf34
    Available
    172.31.0.0/16
    Virtual private cloud
    eksctl-roboshop-cluster/VPC
    vpc-0b249bccf20dd39f1
    Available
    192.168.0.0/16
    Your VPCs

[^24]: aws
    Services
    Q Search
    \[Alt+$\]
    4
    N. Virginia
    joindevo
    VPC
    RDS
    $3
    Elastic Kubernetes Service
    CloudFormation
    Route 53
    EFS
    95 LAM
    O EC2
    Certificate Manager
    CloudFront
    Billing and Cost Management
    Amazon Elastic
    X
    EKS > Clusters
    Kubernetes Service
    Clusters (0) Info
    C
    Delete
    Add cluster
    Clusters New
    Q Filter clusters
    <
    1
    Amazon EKS Anywhere
    Enterprise Subscriptions New
    Cluster name
    Status
    4
    Kubernetes version
    Support type
    Provider
    Related services
    No clusters
    Amazon ECR
    You do not have any clusters.
    AWS Batch
    Create cluster
    Documentation CZ

[^25]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-192-168-25-136. ec2. internal
    Ready
    <none>
    17m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-59-29. ec2 . internal
    Ready
    <none>
    17m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-8-178. ec2 . internal
    Ready
    <none>
    17m
    v1. 27.9-eks-5eOfdde

[^26]: Instances (4) Info
    G
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    Instance state = running
    X
    Clear filters
    >
    Name
    Instance ID
    Instance state
    Instance type v Status check
    Alarm status
    Availability
    O
    workstation-eksctl
    i-080ed32fOdd303fef
    Running Q Q
    t2.micro
    2/2 checks passed View alarms +
    us-east-1a
    roboshop-spot-Node
    i-Ofb5f6f7ed9c1b5fb
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1c
    roboshop-spot-Node
    i-03b1bafcoe23a6e2f
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1b
    roboshop-spot-Node
    i-0391793290010a63e
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1b

[^27]: eksctl
    kubectl
    docked

