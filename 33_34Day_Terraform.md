---
title: 33_34Day_Terraform
uuid: e1155448-2a01-11ef-b56c-3e95ff25d0e5
version: 433
created: '2024-06-14T09:25:02+05:30'
tags:
  - terraform
---

***Topics:***

1. <mark style="background-color:#f8d616;">Connecting to private instance<!-- {"backgroundCycleColor":"25"} --></mark>

    1. First connect to public instance and from public you can connect private instance.

    1. VPN - sing VPN we can connect private instance.

1. <mark style="background-color:#f8d616;">Creating VPN through terraform<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"offset":1} -->

1. <mark style="background-color:#f8d616;">Load Balancer<!-- {"backgroundCycleColor":"25"} --></mark>

\

\

# <mark style="background-color:#f8914d;">**Connecting to private instance**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

<mark style="background-color:#f8d616;">Two Methods<!-- {"backgroundCycleColor":"25"} --></mark>

1. First connect to public instance and from public you can connect private instance.

1. VPN - sing VPN we can connect private instance.

<mark>VPN - sing VPN we can connect private instance:</mark>

![168fd9c1-6b9d-4b5f-a942-7ade95228002.png|642](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/168fd9c1-6b9d-4b5f-a942-7ade95228002.png) [^1]

\

In default VPC i have created one public instance: <mark style="background-color:#f8914d;">This is our VPN server<!-- {"backgroundCycleColor":"24"} --></mark>

![4240076b-cc3c-4190-b855-a207e0d9b6d6.png|848.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/4240076b-cc3c-4190-b855-a207e0d9b6d6.png) [^2]

connected to public instance

![73ec6d5f-5273-4934-ae35-1692dfbf45bb.png|911](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/73ec6d5f-5273-4934-ae35-1692dfbf45bb.png) [^3]

\

For MongoDB server there is no public IP, so we can't connect directly:

![7ecf50af-865b-4a89-85a1-1d4954971da9.png|837.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/7ecf50af-865b-4a89-85a1-1d4954971da9.png) [^4]

\

Installing OPENVPN - from github user -Angristan (he stored in github, using scripts)

![55f9326e-161a-4534-ac5b-0843b004eed7.png|760](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/55f9326e-161a-4534-ac5b-0843b004eed7.png) [^5]

\

```
sudo su -
curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh     --to download software
chmod +x openvpn-install.sh                 --changing the permission
./openvpn-install.sh                                --to install openvpn software
```

\

![19070775-7beb-4461-8c6f-c483fe1c1403.png|1034.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/19070775-7beb-4461-8c6f-c483fe1c1403.png) [^6]

![35e457a7-a6f7-4b74-9db9-0420f59ea343.png|1033.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/35e457a7-a6f7-4b74-9db9-0420f59ea343.png) [^7]

![92988277-450b-40d0-b351-4f8da0aedce6.png|1030.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/92988277-450b-40d0-b351-4f8da0aedce6.png) [^8]

![93a0926a-0632-495c-9e24-d9d8324853b6.png|1029.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/93a0926a-0632-495c-9e24-d9d8324853b6.png) [^9]

\

Now download and install openvpn client 

![e4a81ec4-7da1-4730-beea-cde67ca14acd.png|848.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/e4a81ec4-7da1-4730-beea-cde67ca14acd.png) [^10]

![d9f7072a-9e78-4db2-b015-66594b7dbe93.png|637](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/d9f7072a-9e78-4db2-b015-66594b7dbe93.png) [^11]

![64302806-f707-47aa-aa4f-e93a63b63605.png|335](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/64302806-f707-47aa-aa4f-e93a63b63605.png) [^12]

\

\

Copy the data of chilukuri.ovpn and save as below file in local.

![aded233d-1dc5-4355-9f2f-07299a7bdf9d.png|935](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/aded233d-1dc5-4355-9f2f-07299a7bdf9d.png) [^13]

![18150d35-db65-47f3-bd79-d683ecfb879c.png|926.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/18150d35-db65-47f3-bd79-d683ecfb879c.png) [^14]

![cadf11eb-00ee-45b3-8c84-db5929ba748b.png|993](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/cadf11eb-00ee-45b3-8c84-db5929ba748b.png) [^15]

\

![28029cdf-b8d7-49c3-8002-cdf18a53520d.png|370](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/28029cdf-b8d7-49c3-8002-cdf18a53520d.png) [^16]

\

Now its connected

![dab7632c-42f7-48e4-ae6f-b0aec289e70b.png|388](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/dab7632c-42f7-48e4-ae6f-b0aec289e70b.png) [^17]

\

To check if you are successfully connected to VPN or not

![54a9e7da-b85a-4f29-acc1-100136d48d64.png|894](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/54a9e7da-b85a-4f29-acc1-100136d48d64.png) [^18]

\

\

<mark>Now Mongodb server has to accept connections from VPN</mark>

![a452a2e0-57f7-461d-b0ee-2552641f7421.png|806](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/a452a2e0-57f7-461d-b0ee-2552641f7421.png) [^19]

\

\

Peering we already created for default VPC & roboshop VPC

![384d1fbd-31ad-4f0c-af90-59db05e63301.png|967.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/384d1fbd-31ad-4f0c-af90-59db05e63301.png) [^20]

\

MongoDB server subnet and its route table (default VPC peering connection)

![b9cc1e6e-aae0-4e52-81cf-4050cb85804b.png|1027.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/b9cc1e6e-aae0-4e52-81cf-4050cb85804b.png) [^21]

\

\

Now go to mongdb server security group

![fb986d7a-3c96-428c-9510-de760e8f775f.png|977.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/fb986d7a-3c96-428c-9510-de760e8f775f.png) [^22]

\

![50952c72-bf18-4bd3-b172-e7bfa766a940.png|934.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/50952c72-bf18-4bd3-b172-e7bfa766a940.png) [^23]

\

![](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/e70abbe3-9bba-402f-9e3d-d61ffefe6857.png) [^24]

Now adding VPN security group to enable access

![5b1a3a67-1758-4825-9fa1-92bd53c7fdc5.png|869.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/5b1a3a67-1758-4825-9fa1-92bd53c7fdc5.png) [^25]

\

Now i should be able to connect mongodb instance from my laptop using VPN. Using private IP

![94bf509a-d3c0-4874-92c5-1f084189089c.png|977.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/94bf509a-d3c0-4874-92c5-1f084189089c.png) [^26]

\

![da65bc79-7d2f-48ca-923f-1acc8f0b3693.png|788](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/da65bc79-7d2f-48ca-923f-1acc8f0b3693.png) [^27]

\

# <mark style="background-color:#f8914d;">**Creating VPN through terraform**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

Code

![adf2f5b8-afdb-4991-a635-b73471de22e0.png|344](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/adf2f5b8-afdb-4991-a635-b73471de22e0.png) [^28]

\

```
terraform init
terraform plan
terraform apply -auto-approve
```

![](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/e71f9254-d68b-43da-b367-ddafe36da878.png) [^29]

![ad180a2a-224a-4135-b0df-8376d794a1ff.png|771](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/ad180a2a-224a-4135-b0df-8376d794a1ff.png) [^30]

![62b363ae-05f2-4fd0-bdb4-482588f71222.png|979.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/62b363ae-05f2-4fd0-bdb4-482588f71222.png) [^31]

connected to roboshop-dev-vpn server

![d544710d-7fa3-4ff1-8dc4-a5764263212b.png|1013](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/d544710d-7fa3-4ff1-8dc4-a5764263212b.png) [^32]

![d544710d-7fa3-4ff1-8dc4-a5764263212b.png|1013](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/d544710d-7fa3-4ff1-8dc4-a5764263212b.png) [^33]

```
netstat -lntp
```

![fc1604e0-cd30-442a-8029-dcd76c317726.png|1049.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/fc1604e0-cd30-442a-8029-dcd76c317726.png) [^34]

```
sudo su -
```

```
ls -l
cat chilukuri.ovpn
```

![](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/2bf7f8bd-bcf6-4037-892f-616410f320bb.png) [^35]

![](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/6e05bfcd-b683-4cb6-80f2-2f8ae60691ed.png) [^36]

\

save chilukuri.ovpn in local laptop

![eaed0b12-0d10-4f3c-a8e8-52f5565ad522.png|687](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/eaed0b12-0d10-4f3c-a8e8-52f5565ad522.png) [^37]

\

connect to vpn

![cd615a86-3426-4026-92c0-dde3405d4114.png|941.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/cd615a86-3426-4026-92c0-dde3405d4114.png) [^38]

connected to VPN

![961435eb-b726-4399-ae70-ec739d24a651.png|386](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/961435eb-b726-4399-ae70-ec739d24a651.png) [^39]

\

Now try to connect mongodb instance (If you disconnect VPN then you wont be able to connect to instance(tried and worked)

10\.0.21.124

![0187f703-d4ca-4f6c-b183-9f5f44242000.png|908](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/0187f703-d4ca-4f6c-b183-9f5f44242000.png) [^40]

\

Till now we created

\

VPC and peering

All SG

VPN

EC2 and records

Ansible server & installing ansible roles

---

# <mark style="background-color:#f8914d;">**Load Balancer**<!-- {"backgroundCycleColor":"24"} --></mark>

Important in AWS

\

Load Balancer

Target groups

rules

launch template

auto scaling

auto scaling policy

\

\--One manager, team leaders, team members 

clients will send requirements to manager

1\. UI requirements

2\. backend requirements

3\. database requirements

\--Manager gives requirements to specific - UI team leader, backend leader, database leader

\--Team leader --> team members

\

<mark>Manager is Load balancer</mark>

\

Creating two instances 

![05f71c5b-6ba5-4149-a1fc-08be72216897.png|947.3333740234375](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/05f71c5b-6ba5-4149-a1fc-08be72216897.png) [^41]

![001a3f49-6899-4625-8d2f-9be33c741714.png|959](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/001a3f49-6899-4625-8d2f-9be33c741714.png) [^42]

\

This will install nginx & creates one index.html file with data.

```
#!/bin/bash
sudo yum install nginx -y
mkdir -p/usr/share/nginx/html/ui
echo "<h1> Hi We are from UI Team</h1>" > /usr/share/nginx/html/ui/index.html
sudo systemctl restart nginx
```

![a8e2d4d8-ee3e-40e6-bfad-1370f010bf35.png|773](https://images.amplenote.com/e1155448-2a01-11ef-b56c-3e95ff25d0e5/a8e2d4d8-ee3e-40e6-bfad-1370f010bf35.png) [^43]

\

[^1]: HOME
    AWS
    Default
    Roboshop
    VPN
    MongoDB

[^2]: Instances (1/1) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    Instance ID = i-056fa5805e34a66f8
    X
    Clear filters
    <
    1
    >
    V
    Name _
    Instance ID
    Instance state
    V
    Instance type
    4
    Status check
    Alarm status
    Availabilit
    V
    openVPN
    i-056fa5805e34a66f8
    Running
    t2.micro
    View alarms +
    us-east-1d

[^3]: SuperPUTTY - 54.242.87.199
    File
    View
    Tools Help
    Protocol SSH
    . Host 54.242.87.199
    Login
    Password
    Session
    c
    Commands
    54.242.87.199
    54 . 242. 87. 199 \| 172.31.22.205 \| t2.micro \| null
    \[ centos@ip-172-31-22-205 \~ \]$

[^4]: Instances (1/1) Info
    G
    Connect
    Instance state
    V
    Actions
    V
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    < 1 >
    Name _
    Instance ID
    Instance state
    V
    Instance type
    Status check
    Alarm status
    Avail
    V
    roboshop-dev-mongodb
    i-0b97d816720884e22
    Running
    t3.small
    Initializing
    View alarms +
    us-ea
    E
    i-0b97d816720884e22 (roboshop-dev-mongodb)
    Details
    Status and alarms
    Monitoring
    Security
    Networking
    Storage
    Tags
    Instance summary Info
    Instance ID
    Public IPv4 address
    Private IPv4 addresses
    i-0697d816720884e22 (roboshop-dev-mongodb)
    10.0.21.217
    IPv6 address
    Instance state
    Public IPV4 DNS
    Running

[^5]: maintained by our team of experts. Download the client VPN software for your PC.
    Github
    https://github.com/angristan/openvpn-install
    GitHub - angristan/openvpn-install: Set up your own OpenVPN ...
    WEB OpenVPN installer for Debian, Ubuntu, Fedora, CentOS, Arch Linux, Oracle Linux, Rocky Linux
    and AlmaLinux. This script will let you setup your own secure VPN server in just a ...

[^6]: \[ centosdip-172-31-22-205 \~ \]$ sudo su
    54 . 242. 87. 199 \| 172. 31.22.205 \| t2.micro \| null
    root@ip-172-31-22-205 \~ \]# curl -0 https://raw. githubusercontent. com/angristan/openvon-install/master/openvpn-install. sh
    8 Total
    Received . Xferd Average Speed
    Time
    Time
    Time
    Current
    Dload Upload
    Total
    Spent
    Left
    Speed
    100 40825 100 40825
    0
    0
    569k
    0
    569k
    54 . 242. 87. 199 \| 172. 31.22.205 \| t2.micro \| null
    \[ root@ip-172-31-22-205 \~ \]# chmod +x openvpn-install. sh
    54 . 242. 87. 199 \| 172. 31.22.205 \| t2.micro
    \| null
    \[ root@ip-172-31-22-205 \~ \]# ./openvpn-install . sh
    Welcome to the OpenVPN installer!
    The git repository is available at: https: //github. com/angristan/openvpn-install
    I need to ask you a few questions before starting the setup.
    You can
    leave
    the default options
    and just
    press enter if you
    are
    with them.

[^7]: I need to know the IPv4 address of the network interface you want OpenVPN listening to.
    Unless your server is behind NAT, it should be your public IPv4 address.
    IP address: 54. 242. 87. 199
    Checking for IPv6 connectivity.. .
    Your host does not appear to have IPv6 connectivity.
    Do you want to enable IPv6 support (NAT) ? \[y/n\] : n
    What port do you want OpenVPN to listen to?
    1) Default: 1194
    2) Custom
    3) Random \[49152-65535\]
    Port choice \[1-3\] : 1
    What protocol do you want OpenVPN to use?
    UDP is faster. Unless it is not available, you shouldn't use TCP.
    1) UDP
    2) TCP
    Protocol \[1-2\] : 2

[^8]: What DNS resolvers do you want to use with the VPN?
    1) Current system resolvers (from /etc/resolv. conf)
    2) Self-hosted DNS Resolver (Unbound)
    3) Cloudflare (Anycast: worldwide)
    4)
    Quad9 (Anycast: worldwide)
    5
    Quad9 uncensored (Anycast: worldwide)
    6
    FDN (France)
    7
    DNS . WATCH (Germany)
    8)
    OpenDNS (Anycast: worldwide)
    9) Google (Anycast: worldwide)
    10) Yandex Basic (Russia)
    11) AdGuard DNS (Anycast: worldwide)
    12) NextDNS (Anycast: worldwide)
    13) Custom
    DNS \[1-12\] : 11
    Do you want to use compression? It is not recommended since the VORACLE attack makes use of it.
    Enable compression? \[y/n\] : n
    Do you want to customize encryption settings?
    Unless you know what you're doing, you should stick with the default parameters provided by the script.
    Note that whatever you choose, all the choices presented in the script are safe. (Unlike OpenVPN's defaults)
    See https: //github . com/angristan/openvpn-install#security-and-encryption to learn more.
    Customize encryption settings? \[y/n\] : n
    Okay, that was all I needed. We are ready to setup your OpenVPN server now.
    You will be able to generate a client at the end of the installation.

[^9]: The name must consist of alphanumeric character. It may also include an underscore or a das
    Client name: chilukuri
    Do you want to protect the configuration file with a password?
    (e.g. encrypt the private key with a password)
    1) Add a passwordless client
    2) Use a password for the client
    Select an option \[1-2\] : 2
    4 You will be asked for the client password below 4
    Using SSL: openssl OpenSSL 1.1.1k FIPS 25 Mar 2021
    Using Easy-RSA configuration: /etc/openvon/easy-rsa/vars
    The preferred location for 'vars' is within the PKI folder.
    To silence this message move your 'vars' file to your PKI
    or declare your 'vars' file with option: --vars=<FILE>
    Generating an EC private key
    writing new private key to '/etc/openvon/easy-rsa/pki/40a7710a/temp. bc215193'
    Enter PEM pass phrase:
    Verifying - Enter PEM pass phrase:
    Notice

[^10]: C
    @ https://openvpn.net/client/
    M
    Downloads
    . ..
    DEAL Get $200 - Use Code WELCOME w/ 1st Purchase
    openvpn-connect-3.4.4.3412_signed.msi
    2.9 MB/s - 11.6 MB of 89.0 MB, 26 secs left
    OPENVPN'
    Products
    Solutions
    v
    Resources
    v
    Partners v
    Apps
    Pricing
    e
    See more
    and maintained by OpenVPN Inc.
    Windows
    MacOs
    Linux
    Android
    ios
    ChromeOS
    Download OpenVPN Connect for Windows
    Installation instructions and alternative versions

[^11]: OpenVPN Connect Setup
    0
    X
    Installing OpenVPN Connect
    Please wait while the Setup Wizard installs OpenVPN Connect.
    Status:
    Back
    Next
    Cancel

[^12]: OpenVPN Connect
    Import Profile
    VIA URL
    UPLOAD FILE
    URL
    https://
    Please note that you can only import profile
    using URL if it is supported by your VPN
    provider
    NEXT

[^13]: 04 .
    Of .
    IT
    ILL
    \[ root@ip-172-31-22-205 \~ \]# 1s
    chilukuri . ovpn openvon-install.sh original-ks. cfg
    54 . 242. 87. 199 \| 172. 31.22.205 \| t2.micro \| null
    \[ root@ip-172-31-22-205 \~ \]# cat chilukuri . ovpn
    client
    proto top-client
    remote 54 . 242 . 87. 199 1194
    dev tun
    resolv-retry infinite
    nobind
    persist-key
    persist-tun
    remote-cert-tls server

[^14]: X
    E
    terraform user access keys.txt
    DevOps.txt
    client
    +
    File
    Edit
    View
    - - -END CERTIFICATE - - - - -
    </cert>
    <key>
    -BEGIN ENCRYPTED PRIVATE KEY- - - - -
    Save as
    X
    MIHjME4GCSqGSIb3DQEFDTBBMCKGCSqGSIb3DQE
    DAYIKoZIhvcNAgkFADAUBggghkiG9WODBWQIRyu
    OwHgryvamzAOGOXfTYYKSf/VcZ5hZkJPT7Z2YE/
    > Documents
    V C
    Search Documents
    8CYFFvbr3uMWZACZVDblPHkxyPfRZaXOKORTZRS
    MzCxy91708qPP316XPqc1pWBKfJeXd/Sypq2PY
    Organize
    New folder
    ?
    - - - - - END ENCRYPTED PRIVATE KEY - - - - -
    </key>
    Gallery
    Name
    Date modified
    Type
    <tls-crypt>
    #
    Shortcut to Documents (OneDrive - Personal)
    03-06-2024 11:17
    Shortcut
    # 2048 bit OpenVPN static key
    Desktop
    Downloads
    -BEGIN OpenVPN Static key V1- - -
    c1f854227bbd140ad33a2ba056c7fdf7
    Videos
    8f2608e18d1089c8f5c1d420e4b5deeb
    Music
    a16e6be086abfaff5df0337c126fefe1
    notes
    914a6bab68d59504187563bdf3e602dd
    1fb19b483e5a8fbe23c1b96e5f72ba36
    DevOps Docs
    f44569502c2d801dca89ca6635f59f39
    Repos
    738566b2ed940cef85eeeca032100ab6
    e99ec4c48e411c6f734a13b19c4edfa7
    Screenshots
    3963246710591cba0c2c3607ecOcc765
    f7eb19de7c011bblae5f519e6ef3aa4e
    a59c046714cbb6ea5a8701a292848160
    File name: chilukuri.ovpn -
    d510379356177062326ced20a70a676
    Save as type: All files (\*.\*)
    51b24673f479d181778e538a9a746321
    68508f68f9d332aba7c39dc28e4ebod8
    e4477f150385e16a6d42ed4c95697aof
    ^ Hide Folders
    Encoding: UTF-8
    V
    Save
    Cancel
    d49be0bcd1752c656d5933afb7abcbf7
    - - END OpenVPN Static key V1- - - - -
    </tls-crypt>
    Ln 59, Col 30 2,899 characters
    100%
    Windows (CRLF)
    UTF-8

[^15]: OpenVPN Connect
    X
    E
    Import Profile
    VIA URL
    UPLOAD FILE
    Drag and drop to upload .OVPN profile.
    PLOAD FILE
    You can import only one profile at a time
    1 Import Profile or Certificate
    < Professional (E:) > AWSDevOps >
    C
    Search AWSDevOps
    Organize
    New folder
    .OVPN
    notes
    Name
    Date modified
    Type
    T
    Repos
    DevOps Docs
    28-04-2024 17:50
    File fo
    Screenshots
    Keys
    13-05-2024 13:05
    File fo
    DevOps Docs
    MyRecordings
    14-12-2023 10:22
    File fo
    Notepad+ +
    27-11-2023 12:48
    File fo
    This PC
    Repos
    13-06-2024 10:35
    File fo
    BROWSE
    Local Disk (C:)
    webpages
    02-12-2023 14:10
    File fo
    Personal (D:)
    Youtube
    14-12-2023 10:22
    File fo
    chilukuri.ovpn
    14-06-2024 11:00
    OVPN
    Professional (E:)
    Google Drive (G:
    Network
    File name: chilukuri.ovpn
    Profiles and Certificates
    Open

[^16]: OpenVPN Connect
    -
    X
    Imported Profile
    Profile Name
    54.242.87.199 \[chilukuri\]
    Server Hostname (locked)
    54.242.87.199
    V
    Save Private Key Password
    Private Key Password
    . . . . . . .
    PROFILES
    CONNECT

[^17]: OpenVPN Connect
    - X
    Profiles
    CONNECTED
    OpenVPN Profile
    54.242.87.199 \[chilukuri\]
    CONNECTION STATS
    52.4KB/s
    OB/S
    BYTES IN
    BYTES OUT
    130 B/S
    195 B/S
    DURATION
    PACKET RECEIVED
    00:00:44
    2 sec ago
    YOU

[^18]: G
    https://www.bing.com/search?q=what+ is+my+ip+address&FORM=ANNTA1
    Microsoft Bing
    O what is my ip address
    SEARCH
    COPILOT
    VIDEOS
    IMAGES
    MAPS
    NEWS
    SHOPPING
    MORE
    Also try:
    find my address ip
    ip to address lookup
    what is ip address location
    About 51,400,000 results
    Your public IP address
    54.242.87.199
    WhatIsMyIPAddress
    https://whatismyipaddress.com

[^19]: HOME
    AWS
    Default
    Roboshop
    OpenVPN
    VPN
    MongoDB
    Connect

[^20]: NAT gateways (1) Info
    C
    Actions
    Create NAT gateway
    Find resources by attribute or tag
    < 1 >
    Name
    NAT gateway ID
    Connectivity...
    State
    State message
    Primary public l...
    Primary
    O
    roboshop-dev
    nat-086d76b16bbd580af
    Public
    Available
    52.0.97.69
    10.0.1.2

[^21]: Subnets (1/12) Info
    Last updated
    C
    Actions
    Create subnet
    1 minute ago
    Q Find resources by attribute or tag
    -
    Name
    Subnet ID
    4
    State
    4
    VPC
    4
    IPV4 CIDR
    subnet-0873e3231bac49c20
    Available
    vpc-0817 cae8968304c06
    172.31.64.0/2
    subnet-076650bcf0b486323
    Available
    vpc-0817 cae8968304c06
    172.31.16.0/2
    subnet-Od3f605110e2d9e48
    Available
    vpc-0817cae8968304c06
    172.31.48.0/2
    V
    roboshop-dev-database-us-east-la
    subnet-Ofe732cd7f458ec49
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.21.0/24
    O
    roboshop-dev-database-us-east-1b
    subnet-04f99d95aececf5f5
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.22.0/24
    O
    roboshop-dev-private-us-east-1a
    subnet-001bffdfb602c9f9a
    Available
    vpc-Of25f51ebd968c5a1 \| roboshop-dev
    10.0.11.0/24
    O
    roboshop-dev-private-us-east-1b
    subnet-02a4408420bfdf224
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.12.0/24
    0
    roboshop-dev-public-us-east-1a
    subnet-Od7125a003c6b599f
    Available
    vpc-Of25f51ebd968c5a1 \| roboshop-dev
    10.0.1.0/24
    n
    roboshop-dev-public-us-east-1b
    subnet-026041d9ff3a956d2
    Available
    vpc-Of25f5 1ebd968c5a1 \| roboshop-dev
    10.0.2.0/24
    subnet-Ofe732cd7f458ec49 / roboshop-dev-database-us-east-1a
    Details
    Flow logs
    Route table
    Network ACL
    CIDR reservations
    Sharing
    Tags
    Route table: rtb-0a68f5fff360f3671 / roboshop-dev-database
    Edit route table association
    Routes (3)
    Q Filter routes
    <
    1 >
    Destination
    4
    Target
    172.31.0.0/16
    pcx-061e13e8388cdef4d
    10.0.0.0/16
    local
    0.0.0.0/0
    nat-086d7616bbd580af

[^22]: Instances (1/2) Info
    C
    Connect
    Instance state
    A
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    < 1 >
    -
    Name _
    Instance ID
    Instance state
    A
    Instance type
    4
    Status check
    Alarm status
    Availal
    openVPN
    i-056fa5805e34a66f8
    Running
    t2.micro
    2/2 checks passed View alarms +
    us-east
    V
    roboshop-dev-mongodb -
    i-0b97d816720884e22
    Running
    t3.small
    2/2 checks passed View alarms +
    us-eas
    i-0b97d816720884e22 (roboshop-dev-mongodb)
    IAM Role
    Owner ID
    Launch time
    7 158724841371
    Fri Jun 14 2024 09:42:11 GMT+0530 (India Standard Time
    Security groups
    \[sg-0b6d834e82fc45bad (roboshop-dev-mongodb)
    Inbound rules

[^23]: EC2 >
    Security Groups >
    sg-0b6d834e82fc45bad - roboshop-dev-mongodb > Edit inbound rules
    Edit inbound rules info
    Inbound rules control the incoming traffic that's allowed to reach the instance.
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info Port range
    Source Info
    Description - optional Info
    Info
    sgr-00367020e385306e3
    Custom TCP
    TCP
    27017
    Custom
    Q
    Delete
    sg-0aab61d6afb352036 X
    sgr-01fcd842f674e555f
    SSH
    TCP
    22
    Custom
    Q
    Delete
    sg-0a 19d37a52a48bf9a X
    sgr-Ofc72435c39a928c6
    Custom TCP
    TCP
    27017
    Custom
    Q
    Delete
    sg-0022a12d18d91469d X
    Add rule
    Cancel
    Preview changes
    Save rules

[^24]: inbound
    mongodb --> vpn security group

[^25]: EC2 > Security Groups > sg-0b6d834e82fc45bad - roboshop-dev-mongodb > Edit inbound rules
    Edit inbound rules info
    Inbound rules control the incoming traffic that's allowed to reach the instance.
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info
    Port range
    Source Info
    Description - optional Info
    Info
    sgr-00367020e385306e3
    Custom TCP
    TCP
    27017
    Custom
    Q
    Delete
    sg-0aab61d6afb352036 X
    sgr-Ofc72435c39a928c6
    Custom TCP
    TCP
    27017
    Custom
    Q
    Delete
    sg-0022a12d18d91469d X
    SSH
    TCP
    22
    Custom
    Q sg-0c9db47e9b4d484 X
    Delete
    sg-0c9db47e9b4d484b6 X
    Add rule
    Cancel
    Preview changes
    Save rules

[^26]: Instances (1/3) Info
    G
    Connect
    Instance state
    Actions
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    -
    Name _
    4
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    openVPN
    i-056fa5805e34a66f8
    Running
    t2.micro
    2/2 checks passed
    V
    roboshop-dev-mongodb
    i-09fb202317ce4903d
    Running
    t3.small
    Initializing
    0
    roboshop-dev-mongodb
    i-0697d816720884e22
    Terminated
    t3.small
    E
    i-09fb202317ce4903d (roboshop-dev-mongodb)
    Details
    Status and alarms
    Monitoring Security
    Networking
    Storage
    Tags
    Private IPv4 address cop
    Instance summary Info
    ied
    Instance ID
    Public IPv4 address
    i-09fb202317ce4903d (roboshop-dev-mongodb)
    7 10.0.21.124
    IPv6 address
    Instance state
    Public IPV4 DNS

[^27]: SuperPUTTY - 10.0.21.124
    File
    View Tools Help
    Protocol SSH
    Host 10.0.21.124
    Login
    Password
    Session chilops
    Commands
    54.242.87.199
    10.0.21.124
    Using username "centos".
    Server refused our key
    centos@10 . 0. 21 . 124's password:
    DEL
    OPS
    TRAIN
    ING
    Disclaimer :
    This image is designed for only for the lab purpose

[^28]: roboshop-terraform
    > 01-vpc
    > 02-sg
    > 03-ec2
    04-vpn
    > .terraform
    E .terraform.lock.hcl
    data.tf
    locals.tf
    CC CC CC
    main.tf
    providers.tf
    -
    variables.tf

[^29]: http_tokens
    optional
    +
    instance_metadata_tags
    = (known after apply)
    + timeouts {}
    Plan: 1 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock. This may take a few moments. ..

[^30]: http_endpoint
    "enabled"
    +
    http_protocol_ipv6
    E
    "disabled"
    +
    http_put_response_hop_limit = 1
    +
    http_tokens
    E
    "optional"
    +
    instance_metadata_tags
    (known after apply)
    +
    timeouts {}
    Plan: 1 to add, 0 to change, 0 to destroy.
    module . vpn . aws_instance . this \[0\] : Creating. . .
    module . vpn . aws_instance . this \[0\]: Still creating. .. \[10s elapsed\]
    module . vpn . aws_instance . this \[0\]: Creation complete after 17s \[id=i-086faafba8276186\]
    Releasing state lock. This may take a few moments . . .
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

[^31]: Instances (1/4) Info
    G
    Connect
    Instance state V
    Actions
    Launch instar
    Q Find Instance by attribute or tag (case-sensitive)
    All states
    < 1
    Name _
    Instance ID
    Instance state
    4
    Instance type
    Status check
    Alarm status
    openVPN
    i-056fa5805e34a66f8
    Running
    t2.micro
    2/2 checks passed View alarms +
    roboshop-dev-mongodb
    i-09fb202317 ce4903d
    Running
    t3.small
    2/2 checks passed View alarms +
    V
    roboshop-dev-vpn
    i-086faafba8276186
    Running
    t3.small
    Initializing
    View alarms +
    0
    roboshop-dev-mongodb
    i-0b97d816720884e22
    Terminated
    t3.small
    View alarms +

[^32]: SuperPUTTY - 34.226.215.144
    File
    View
    Tools Help
    Protocol SSH
    . Host 34.226.215.144
    Login
    Password
    Session
    chilops
    Commands
    34.226.215.144
    34 . 226. 215.144 \| 172. 31. 41.57 \| t3. small \| null
    \[ centos@ip-172-31-41-57 \~ \]$ \|

[^33]: SuperPUTTY - 34.226.215.144
    File
    View
    Tools Help
    Protocol SSH
    . Host 34.226.215.144
    Login
    Password
    Session
    chilops
    Commands
    34.226.215.144
    34 . 226. 215.144 \| 172. 31. 41.57 \| t3. small \| null
    \[ centos@ip-172-31-41-57 \~ \]$ \|

[^34]: \[ centosdip-172-31-41-57 \~ \]$ netstat -Intp
    (Not all processes could be identified, non-owned process info
    will not be shown, you would have to be root to see it all.)
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0. 0. 0. 0:22
    0.0.0.0:\*
    LISTEN
    tcp
    0 0.0.0. 0:1194
    0.0.0.0:\*
    LISTEN
    tcp
    OOOOO
    0 0. 0.0.0:111
    0.0.0.0:\*
    LISTEN
    tcp6
    0 : ::22
    :: :
    LISTEN
    tcp6
    0
    : : :111
    LISTEN
    34 . 226. 215. 144 \| 172. 31. 41.57 \| t3. small \| null
    \[ centos@ip-172-31-41-57 \~ \]$ 1

[^35]: \[ centosdip-172-31-41-57 \~ \]$ sudo su
    34 . 226. 215. 144 \| 172. 31. 41.57 \| t3. small \| null
    \[ root@ip-172-31-41-57 \~ \]# 1s
    chilukuri .ovpn original-ks. cfg
    34 . 226. 215. 144 \| 172. 31. 41.57 \| t3. small \| null
    \[ root@ip-172-31-41-57 \~ \]# \[\]

[^36]: \[ root@ip-172-31-41-57 \~ \]# cat chilukuri. ovpn
    client
    proto top-client
    remote 34. 226. 215. 144 1194
    dev tun
    resolv-retry infinite
    nobind

[^37]: chilukuri.ovpn
    X
    +
    File
    Edit
    View
    AlUdDWQEAwIHgDAKBggghkjOPQQDAgNIADBFAiBbGAjbKmi TVXBsgqnnI/Cvn779
    omp2zeAIN3eg/8+4xQIhAPSA7abuXf6s8yTZVRRGiXbq2bug1+0RSVPWBesasD2T
    - - - - - END CERTIFICATE - - - - -
    </cert>
    <key>
    - - - - -BEGIN PRIVATE KEY - - - - -
    MIGHAg EAMBMGByqGSM49AgEGCCqGSM49AWEHBGOwawIBAQQgZYw3yyqZfiV9qIUI
    BOpXS1hSnIKOirz/N1Rnnn1FDC+hRANCAASjS/WmYfVLGrEu30k1kou+peh0gAUl
    zwjlowxZ8EC1YVzEvLb2aI91zHemWQHIeRIAtsJZOK1hSSPYDZ3FZVM
    - - - END PRIVATE KEY - - - - -
    </key>
    <tls-crypt>
    #
    # 2048 bit OpenVPN static key
    #
    - -BEGIN OpenVPN Static key V1- -
    431da562991470de7399131a8ab4499b
    ced8fb247a056d07428489e2867a7f7e
    fa93179865f4a206946136fd0c876071
    2f405eff9504998d00c20cf945d53b3f
    be593d76087d20c1989bfba5efOf991f
    1blef0469c0e3dfbc443386ef261ebdc
    a277461216215f383e0e3b7cabfOf72e
    f9c2549a25dc51067d2114edef33fab0
    da61774c383018510fecd7c1539235d1
    fa7b2d85ba2dd6ca71f01c5d1a3e1369
    564fea172c356593bd6cb3b4ab847ea
    62c54a0d608c2edad167cea8e8c509f
    3243ed645f3fff5aef9d149d410e81bc
    73195e456103a97d1bdd7b211elece3b
    2d3dace3d6fea84cab0e8clcdee39alb
    c333391dfla5011ac606ec0e75c85615
    - - - - END OpenVPN Static key V1- - - - -
    </tls-crypt>

[^38]: OpenVPN Connect
    - X
    <
    Import Profile
    VIA URL
    UPLOAD FILE
    Drag and drop to upload .OVPN profile.
    You can import only one profile at a time.
    1 Import Profile or Certificate
    X
    -)
    < Professional (E:) > AWSDevOps >
    V
    C
    Search AWSDevOps
    Organize
    New folder
    ?
    .OVE
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
    This PC
    Repos
    13-06-2024 10:35
    File folder
    BROW
    Local Disk (C:)
    webpages
    02-12-2023 14:10
    File folder
    Youtube
    14-12-2023 10:22
    File folder
    Personal (D:)
    chilukuri.ovpn
    14-06-2024 12:38
    OVPN Profile
    Professional (E:)
    Google Drive (G:
    Network
    File name: chilukuri.ovpn
    Profiles and Certificates (\*.ovpn; v
    Open
    Cancel

[^39]: OpenVPN Connect
    Profiles
    CONNECTED
    OpenVPN Profile
    34.226.215.144 \[chilukuri\]
    DISCONNECTED
    CONNECTION STATS
    2.5KB/s
    OB/S
    BYTES IN
    BYTES OUT
    237 B/S
    604 B/S

[^40]: SuperPUTTY - 10.0.21.124
    File
    View
    Tools Help
    Protocol SSH
    - Host 10.0.21.124
    Login
    Password
    Session
    chilops
    Commands
    10.0.21.124
    TRAIN

[^41]: EC2 > Instances > Launch an instance
    Summary
    Launch an instance Info
    Number of instances Info
    Amazon EC2 allows you to create virtual machines, or instances, that run on the AWS Cloud. Quickly get started by
    2
    following the simple steps below.
    When launching more than 1 instance, consider
    Scaling
    Name and tags Info
    Software Image (AMI)
    Centos-8-DevOps-Practice
    Name
    ami-0b4f379183e570669
    nginx-ui
    Add additional tags
    Virtual server type (instance type)
    t2.micro
    Application and OS Images (Amazon Machine Image) Info
    Firewall (security group)
    SG_Allow_ALL
    An AMI is a template that contains the software configuration (operating system, application server, and
    Storage (volumes)
    applications) required to launch your instance. Search or Browse for AMIs if you don't see what you are looking for
    1 volume(s) - 10 GiB
    below
    Q devops-practice
    X
    Free tier: In your first year include
    750 hours of t2.micro (or t3.micro
    the Regions in which t2.micro is
    AMI from catalog
    Recents
    Quick Start
    unavailable) instance usage on fr
    tier AMIs per month, 750 hours of
    Amazon Machine Image (AMI)
    public IPv4 address usage per
    Q
    month, 30 GiB of EBS storage, 2
    Centos-8-DevOps-Practice
    Browse more AMIs
    million IOs, 1 GB of snapshots, an
    ami-0b4f379183e570669
    100 GB of bandwidth to the inter
    Including AMIs from
    AWS, Marketplace and
    the Community

[^42]: Key pair name - required
    Select
    Create new key pair
    Network settings Info
    Edit
    Network Info
    vpc-0817 cae8968304c06
    Subnet Info
    No preference (Default subnet in any availability zone)
    Auto-assign public IP Info
    Enable
    Additional charges apply when outside of free tier allowance
    Firewall (security groups) Info
    A security group is a set of firewall rules that control the traffic for your instance. Add rules to allow specific traffic to reach your
    instance.
    Create security group
    Select existing security group
    Common security groups Info
    Select security groups
    C
    Compare security
    SG_Allow_All sg-0c9db47e9b4d484b6 X
    group rules
    VPC: vpc-0817cae8968304c06
    Security groups that you add or remove here will be added to or removed from all your network interfaces.

[^43]: User data - optional
    Info
    Upload a file with your user data or enter it in the field.
    Choose file
    #!/bin/bash
    sudo yum install nginx -y
    mkdir -p/usr/share/nginx/html/ui
    echo "<h1> Hi We are from UI Team</h1>" > /usr/share/nginx/html/ui/index.html
    sudo systemctl restart nginx

