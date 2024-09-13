---
title: 1Day_Linux
uuid: eef7cc5c-09fa-11ef-8085-ae87eb62d412
version: 310
created: '2024-05-04T15:14:42+05:30'
tags:
  - linux
---

<mark style="color:#183b51;">**Topics:**<!-- {"cycleColor":"51"} --></mark>

1. *<mark style="background-color:#f3de6c;">GIT bash download & installation<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">SSH Public & private Key Generation<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Create EC2 instance & connecting with public & private key, Importing a key pair in AWS, Creating a security group in AWS.<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Linux Commands:<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">pwd<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">sudo<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">uname<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">man or help<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">history<!-- {"backgroundCycleColor":"14"} --></mark>*

\

# *<mark style="background-color:#f8914d;">**Download it from link**<!-- {"backgroundCycleColor":"24"} --></mark>* [*<mark style="background-color:#f8914d;">**Git - Downloads (git-scm.com)**<!-- {"backgroundCycleColor":"24"} --></mark>*](https://git-scm.com/downloads) *<mark style="background-color:#f8914d;">**& install.**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![f24d54c0-d103-41a7-b667-e0d55be1d08d.png|790.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/f24d54c0-d103-41a7-b667-e0d55be1d08d.png)

\

# *<mark style="background-color:#f8914d;">**SSH Public & private Key Generation**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![8f7e697f-71f0-4475-8070-b9b067ecb74f.png|377](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/8f7e697f-71f0-4475-8070-b9b067ecb74f.png)

\

```
ssh-keygen -t rsa -f <file-name>
 
ssh-keygen -t rsa -f keypair1
```

![872c34b1-044a-4a2b-80e7-85dcd64c1d83.png|590](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/872c34b1-044a-4a2b-80e7-85dcd64c1d83.png) [^1]

\

*To check extensions for a file*

![f62fb8a1-9442-4982-9698-290e017c5ab3.png|1062.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/f62fb8a1-9442-4982-9698-290e017c5ab3.png) [^2]

\

*keypair1.pub <mark style="background-color:#9ad62a;">--> It's a public key<!-- {"backgroundCycleColor":"26"} --></mark>*

*Keypair1        <mark style="background-color:#9ad62a;">--> It's a private key<!-- {"backgroundCycleColor":"26"} --></mark>*

\

![bacddd1a-64bf-4a6f-927b-00065c1ade63.png|1019.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/bacddd1a-64bf-4a6f-927b-00065c1ade63.png) [^3]

\

\

*Rename it to pem file:*

![4c14e5a3-4e37-4639-9b24-b8774bec208e.png|880](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/4c14e5a3-4e37-4639-9b24-b8774bec208e.png) [^4]

\

\

***Public key pair details: **<mark style="background-color:#f3de6c;">ssh-rsa <code> <laptop-name><!-- {"backgroundCycleColor":"14"} --></mark>*

![caa53d13-27a7-437c-9c22-7e16cc160a59.png|995.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/caa53d13-27a7-437c-9c22-7e16cc160a59.png) [^5]

\

*Private key:*

![](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/0f7a32a2-de80-4ecb-8e6a-0079e74c74ba.png)

\

# *<mark style="background-color:#f8914d;">**Create EC2 instance & connecting with public & private key, Importing a key pair in AWS, Creating a security group in AWS.**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*\*Cheapest region --> us-east-1 (N.Virginia) --> somewhat slow than Mumbai --> negligible*

*\*Every Region --> min 2 Availability Zones (AZ) --> HA (high availability)*

![c2c74933-9467-4d5c-ac2d-b14d16109015.png|524](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/c2c74933-9467-4d5c-ac2d-b14d16109015.png) [^6]

\

<mark style="background-color:#f3de6c;">Importing a Key pair in AWS:<!-- {"backgroundCycleColor":"14"} --></mark>

![7debf515-eab0-460e-b89f-527dd431de14.png|803.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/7debf515-eab0-460e-b89f-527dd431de14.png)

\

![c94bf3a9-51f4-463f-9654-60e763ba6d64.png|940.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/c94bf3a9-51f4-463f-9654-60e763ba6d64.png) [^7]

\

\

*<mark style="background-color:#f3de6c;">**Creating a security group in AWS:**<!-- {"backgroundCycleColor":"14"} --></mark>*

 

*Now creating a security group is nothing but a firewall in AWS*

\

 

![f5ea73c6-895e-4181-98b5-1a52d3f505ca.png|793](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/f5ea73c6-895e-4181-98b5-1a52d3f505ca.png) [^8]

\

\

<mark style="background-color:#f3de6c;">0.0.0.0/0 --> representation of internet / public<!-- {"backgroundCycleColor":"14"} --></mark>

 

![18955d73-ec42-4991-94a8-9727c5856abc.png|1091.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/18955d73-ec42-4991-94a8-9727c5856abc.png) [^9]

\

\

*<mark style="background-color:#f3de6c;">**Launching an AWS EC2 instance:**<!-- {"backgroundCycleColor":"14"} --></mark>*

\

![a2cf8e92-f297-420e-b9ab-bf7442504466.png|938.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/a2cf8e92-f297-420e-b9ab-bf7442504466.png) [^10]

\

*GitBash/putty --> SSH client*

*EC2 Server --> SSH server*

*protocol = SSH port=22*

 

*Public IP=54.82.48.193*

*username = ec2-user*

*private-key*

\

\#ssh -i <path-to-private-key> username@IP

```
ssh -i keypair1.pem ec2-user@54.82.48.193
```

![dda720bc-052d-4967-b8f3-707ab55636e0.png|730](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/dda720bc-052d-4967-b8f3-707ab55636e0.png)

\

Private keypair path is very important - **Here in this case private keypair is under "cd /e/awsdevops/keys/"**

\

![9e2ef7db-8eca-40ca-9974-6f3b77af3583.png|753](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/9e2ef7db-8eca-40ca-9974-6f3b77af3583.png)

\

# <mark style="background-color:#f8914d;">**SUDO**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

**Commands:**

*$ -> Normal user*

*# --> Root user (*

```
sudo su 
```

```
sudo su -
```

![4b81cf26-53d1-45b4-a4a1-58963b2722d4.png|482](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/4b81cf26-53d1-45b4-a4a1-58963b2722d4.png)

\

# <mark style="background-color:#f8914d;">**PWD**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

```
pwd     --> present working directory
```

![](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/29bfafe2-be31-4303-b7d4-4051327002f0.png)

\

# <mark style="background-color:#f8914d;">**UNAME**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\#uname   --> gives you kernel name

\#uname -a    --> gives complete information (-a or --all stands for full information)

\

```
uname  
```

```
uname -a   
```

![2fa8b471-f177-4bc5-8da3-03d245529fd3.png|1063.3333740234375](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/2fa8b471-f177-4bc5-8da3-03d245529fd3.png) [^11]

\

# <mark style="background-color:#f8914d;">**HELP or MAN**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

*<mark style="background-color:#f3de6c;">#help or man commands<!-- {"backgroundCycleColor":"14"} --></mark>*

![1813e2d7-9797-4a48-80be-562bda56409b.png|654](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/1813e2d7-9797-4a48-80be-562bda56409b.png)

\

# <mark style="background-color:#f8914d;">**History**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

*#history     --> gets previous history*

```
history 
```

![](https://images.amplenote.com/eef7cc5c-09fa-11ef-8085-ae87eb62d412/21cdd542-e8da-496a-bf83-36793f51dae1.png)

\

[^1]: chowd@Chowdary MINGW64
    $ ssh-keygen -t rsa -f keypair1
    Generating public/private rsa key pair.
    Enter passphrase (empty for no passphrase) :
    Enter same passphrase again:
    Your identification has been saved in keypairl
    Your public key has been saved in keypairl. pub
    The key fingerprint is :
    SHA256 : x35 iXar Zwdp1glamCDp8mtdJOoqChkXdz/HbH3k483w chowd@Chowdary
    The key's randomart image is:
    \[RSA 3072\]----+
    OE
    S
    O
    \* . +BOO
    + . .0 . B+O++
    O
    . =+ @.0 0.
    .o. + 0
    \[SHA256\]
    chowd@chowdary MINGW64 \~

[^2]: All Control Panel Items
    F
    -)
    > Control Panel > All Control Panel Items
    V C
    Adjust your computer's settings
    AutoPlay
    Backup and Restore (Windows 7)
    Color Management
    Credential Manager
    Date and Time
    15 Default Programs
    File Explorer Options
    X
    Devices and Printers
    Ease of Access Center
    File Explorer Options
    General View
    Search
    & Indexing Options
    Internet Options
    Keyboard
    Folder views
    Network and Sharing Center
    Pen and Touch
    You can apply this view (such as Details or Icons) to
    Phone and Modem
    Region
    all folders of this type.
    Recovery
    RemoteApp and Desktop Connectio..
    Speech Recognition
    Storage Spaces
    Apply to Folders
    Reset Folders
    Sync Center
    Taskbar and Navigation
    Troubleshooting
    User Accounts
    ter
    Windows Tools
    Work Folders
    Advanced settings:
    Files and Folders
    Always show icons, never thumbnails
    Decrease space between items (compact view)
    Display file icon on thumbnails
    Display file size information in folder tips
    Display the full path in the title bar
    Hidden files and folders
    Don't show hidden files, folders, or drives
    Show hidden files, folders, and drives
    Hide empty drives
    Hide extensions for known file types-
    Hide folder merge conflicts
    Hide protected operating system files (Recommended)
    HI armmah folder windsoon in a

[^3]: chowd
    X
    +
    ->
    C
    >
    This PC > Local Disk (C:) > Users > chowd
    +
    New
    CO
    CO
    N Sort
    View
    . . .
    Home
    Name
    Date modified
    Type
    Size
    Gallery
    keypair1
    29-11-2023 16:20
    File
    1 KB
    OneDrive - Personal
    keypair1.pub
    29-11-2023 16:20
    PUB File
    1 KB
    Apps
    .bash_history
    29-11-2023 15:55
    BASH_HISTORY File
    1 KB
    Desktop
    .gitconfig
    29-11-2023 12:11
    GITCONFIG File
    1 KB

[^4]: Name
    Date modified
    Type
    Size
    keypair 1.pem
    29-11-2023 16:20
    PEM File
    1 KB
    keypair1.pub
    29-11-2023 16:20
    PUB File
    1 KB

[^5]: DevOps.txt x keypair1.pub x
    1
    ssh-rsa
    AAAAB3NzaClyc2EAAAADAQABAAABgQDNSEtk5B/I+TnUnjDNkmL3Aa8052kgrBYpgGB8NtCJ1cZ62qhOVw+815J98PXhuIA2WbMHIuWGH4RUr4NKxnjmHNfgVZR+cb/e7fgdxzLCcXix7Uz0w/IVzbT+gvdeRgPdJUOmkWPhTAJ3VNHEo
    MWZk7g5HX19RBXJHfde2YHUysIfLCUzqcIbtCS80QLV2euMorSh7fU8 rbdRowcFy17RST3KevK9YJ050joWzroho/ElP/WIQ7H/EbNxczq17aGzZxeE7el/AZsWEK3nUvhtBPwxzY9oBVQtyyYNulAodwvBax416VXqQZasj SPcorq14PL
    plavAmUVocH309eT1b4P7V45Ej SatmE209h8QBTvyrjTZASVd92p06hfRRgYQL+wcRq/+txiJB6WGhh42VUvant/ ann8xfMpSeL/DhzRmSuqFO/rsckURuIqL9DCWX3Copo40n0550E2HanaOrb6hSqXsN76xVIErzDgaMv3LGKapUjrTj
    CGGiyq6FU= chowd@Chowdary
    12

[^6]: REGION
    Availability Zone
    Availability Zone
    IIIIII
    IIIIII
    IIIIII
    IIIIII
    IIIIII
    Data
    III
    Center
    Data
    Data
    Data
    -
    Center
    Data
    Center
    Center
    Center
    Low latency
    resilient fiber
    connectivity
    IIIIII
    Data
    Data
    Center
    Center
    Availability Zone

[^7]: Import settings
    Name
    Keypair1
    The name can include up to 255 ASCII characters. It can't include leading or trailing spaces.
    Key pair file
    Browse
    Choose Browse and navigate to your public key. You may change the name of your key. Alternatively, paste the
    contents of your public key into the Public key contents text box.
    keypair1.pub
    0.568kb
    pgGB8NtCJlcZ62qhOVw+8L5J98PXhulA2WbMHluWGH4RUr4NKxnjmHNfgVZR+cb/
    e7fgdxzLCcXix7UzOw/IVzbT+gvdeRgPdJUOmkWPhTAJ3VNHEOMWZk7g5HX19RBXJ
    Hfde2YHUysifLCUzqclbtCS80QLV2euMcrSh7fU8rbdRowcFy17RST3KevK9YJ050jo
    WzrohO/E1P/WIQ7H/EbNxczq17aGzZxeE7el/AZsWEK3nUvhtBPwxzY90BVQtyyYN
    ulAodwvBax416VXqQZasjSPcorql4PLp 1aVAmUVocH309eT1b4P7V45EjSatmE209h
    8QBTvyrjTZASVd92p06hfRRgYQL+wcRq/+txiJB6WGhh42VUvant/ann8xfMpSel/Dh
    zRmSuqEQ/rsckURulqL9DCWX3Copo40n0550E2HanaOrb6hSqXsN76xV1ErzDgaMv
    3LGKapUjrTjcGGiyq6FU= chowd@Chowdary
    Tags - optional
    No tags associated with the resource.
    Add new tag
    You can add up to 50 more tags.
    Cancel
    Import key pair
    Key pairs (1) Info
    G
    Actions
    Create key pair
    Find Key Pair by attribute or tag
    < 1 >
    O
    Name
    Type
    Created
    4
    Fingerprint
    ID
    0
    Keypair1
    rsa
    2023/11/29 17:13 GMT+5:30
    d6:f4:de:a2:a3:fb:28:c2:de:67:1f:48:91:c2:c...
    key-0a 1b3...

[^8]: Git Bash
    EC2 server
    EC2 > Security Groups > Create security group
    Create security group info
    A security group acts as a virtual firewall for your instance to control inbound and outbound traffic. To create a new security group, complete the fields below.
    Basic details
    Security group name Info
    SG1_Allow-All
    Name cannot be edited after creation.
    Description Info
    Allowing everything just for practice
    VPC Info
    vpc-0817cae8968304c06

[^9]: Inbound rules Info
    Type Info
    Protocol Info
    Port range Info
    Source Info
    Description - optional Info
    All traffic
    All
    All
    Anywhere-IPV4
    Delete
    0.0.0.0/0 X
    Add rule
    A Rules with source of 0.0.0.0/0 or ::/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only.
    X
    Outbound rules Info
    Type Info
    Protocol Info
    Port range Info
    Destination Info
    Description - optional Info
    All traffic
    All
    ALL
    Custom
    Delete
    0.0.0.0/0 X
    Add rule
    A Rules with source of 0.0.0.0/0 or :/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only.
    X
    Tags - optional
    A tag is a label that you assign to an AWS resource. Each tag consists of a key and an optional value. You can use tags to search and filter your resources or track your AWS costs.
    No tags associated with the resource.
    Add new tag
    You can add up to 50 more tags
    Cancel
    Create security group
    Security Groups (2) Info
    C
    Actions
    Export security groups to CSV
    V
    Create security group
    Q Find resources by attribute or tag
    < 1
    O
    Name
    Security group ID
    A
    Security group name
    4
    VPC ID
    Des
    0
    SG1_Allow-All
    sg-0d20035c3943d6a29
    SG1_Allow-All
    vpc-0817cae8968304c06 \[
    Allo
    sg-029974043a4090491
    default
    vpc-0817 cae8968304c06 \[
    def

[^10]: Launch an instance info
    Amazon EC2 allows you to create virtual machines, or instances, that run on the AWS Cloud. Quickly get started by following
    the simple steps below.
    Name and tags Info
    Name
    Linux 1
    Add additional tags
    Application and OS Images (Amazon Machine Image) Info
    An AMI is a template that contains the software configuration (operating system, application server, and applications)
    required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for below
    Q Search our full catalog including 1000s of application and OS images
    AMI from catalog
    Quick Start
    Amazon Machine Image (AMI)
    Q
    amzn2-ami-kernel-5.10-hvm-2.0.20231116.0-
    Verified provider Free tier eligible
    x86_64-gp
    Browse more AMIs
    ami-Ofa 1ca9559f1892ec
    Including AMIs from
    WS, Marketplace and
    the Community
    Catalog
    Published
    Architecture
    Virtualization
    Root device type
    ENA Enabled
    Quickstart AMIs
    2023-11-
    x86_64
    hvm
    ebs
    Yes
    17T01:08:56.000
    7
    Key pair (login) Info
    You can use a key pair to securely connect to your instance. Ensure that you have access to the selected key pair before
    you launch the instance.
    Key pair name - required
    Keypair 1
    Create new key pair
    Proceed without a key pair (Not recommended)
    Default value
    Keypair
    Edit
    Type: rsa
    Network Info
    vpc-0817cae8968304c06
    Subnet Info
    No preference (Default subnet in any availability zone)
    Auto-assign public IP Info
    Enable
    Firewall (security groups) Info
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your instance.
    O Create security group
    Select existing security group
    Common security groups Info
    Select security groups
    Compare security group
    SG1_Allow-All sg-0d20035c3943d6a29 X
    rules
    VPC: vpc-0817cae8968304c06
    Security groups that you add or remove here will be added to or removed from all your network interfaces.
    Instances (1) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    1 >
    0
    Name
    Instance ID
    Instance state
    Instance type s
    Status check
    Alarm status
    Availability Zone V
    Public IPV4 DNS
    A
    Pu
    Linux 1
    i-004bada3dba95dc41
    Running Q Q
    t2.micro
    Initializing
    No alarms +
    us-east-1d
    ec2-54-82-48-193.com...
    54 .

[^11]: \[root@ip-172-31-18-204 \~\]#
    \[root@ip-172-31-18-204 \~\]# uname
    Linux
    \[root@ip-172-31-18-204 \~\]# uname -a
    Linux ip-172-31-18-204. ec2. internal 5. 10. 199-190.747 . amzn2 . x86_64 #1 SMP Sat Nov 4 16:55:14 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
    \[root@ip-172-31-18-204 \~\]#
    \[root@ip-172-31-18-204 \~\]# uname --all
    Linux ip-172-31-18-204. ec2. internal 5 . 10. 199-190.747 . amzn2 . x86_64 #1 SMP Sat Nov 4 16:55:14 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
    \[root@ip-172-31-18-204 \~\]#

