---
title: 5Day_Linux
uuid: f669d486-0e86-11ef-bfd1-2e40d90dfe07
version: 245
created: '2024-05-10T10:07:08+05:30'
tags:
  - linux
---

***Topics:***

1. *<mark style="background-color:#f8d616;">**Login with putty & superputty**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**WinSCP**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Nginx - install, services start, files**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Linux Filesystem structure -- /(root), var, bin etc**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Inode -- for every file you create unique inode will generate.**<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">**Symlink (soft), Hardlink**<!-- {"backgroundCycleColor":"25"} --></mark>*

 

\

# *<mark style="background-color:#f8914d;">**Putty**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*username*

*private-key/password*

*IP address*

 

*Change below settings:*

![6e91fdc3-7dfd-46a4-a9d5-64ce4696443b.png|454](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/6e91fdc3-7dfd-46a4-a9d5-64ce4696443b.png) [^1]

 

 

*Putty has different format for private key*

*.pem --> is general format*

*.ppk --> is used for putty private key(ppk)*

 

*To convert .pem file to .ppk file use "putty generator" and load the .pem file as below.*

 

![4d2693d4-c4af-4ab6-bd35-bc3d3ade3d6c.png|616](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/4d2693d4-c4af-4ab6-bd35-bc3d3ade3d6c.png) [^2]

 

![9a25fd1b-bfb6-4d2e-811f-1316a33dafbb.png|726](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/9a25fd1b-bfb6-4d2e-811f-1316a33dafbb.png) [^3]

 

 

![4bb21ddb-40f6-4b70-ba56-a3b62c19861c.png|517](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/4bb21ddb-40f6-4b70-ba56-a3b62c19861c.png) [^4]

 

![f772f192-c3af-4fdc-a632-8dd36ca024ab.png|540](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/f772f192-c3af-4fdc-a632-8dd36ca024ab.png) [^5]

 

 

*Save with ppk extension*

![f3f3895b-4db1-4056-b124-22a6c732ae10.png|715](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/f3f3895b-4db1-4056-b124-22a6c732ae10.png) [^6]

 

*Now selecting .ppk file from putty window.*

![a03ae08e-ed0c-4793-8ff2-d675623fb198.png|733.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/a03ae08e-ed0c-4793-8ff2-d675623fb198.png) [^7]

 

***Now save session without fail.***

![249f3f8a-c9b9-44d8-8020-f849200163a2.png|471](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/249f3f8a-c9b9-44d8-8020-f849200163a2.png) [^8]

 

***Now connecting to instance -->  give it ip/host name and load the saved session (it will fetch saved user name, .ppk keypair).***

![bc583da9-babb-481b-8d37-4f3cc1aad075.png|400](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/bc583da9-babb-481b-8d37-4f3cc1aad075.png) [^9]

 

![e900d950-3e52-465b-a2c2-46c3dac48c2e.png|638](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/e900d950-3e52-465b-a2c2-46c3dac48c2e.png) [^10]

 

 

 

# *<mark style="background-color:#f8914d;">**Super Putty **<!-- {"backgroundCycleColor":"24"} --></mark>--> from putty extension to putty  (In background super putty uses putty only)*<!-- {"collapsed":true} -->

 

![7effe684-a09d-41e1-919b-acd1dfa04d2d.png|945.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/7effe684-a09d-41e1-919b-acd1dfa04d2d.png) [^11]

 

 

# *<mark style="background-color:#f8914d;">**WINSCP**<!-- {"backgroundCycleColor":"24"} --></mark> --> connecting instance using winscp*<!-- {"collapsed":true} -->

![57ff8973-cbc1-4000-841e-3fbfcb5e1ce9.png|753.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/57ff8973-cbc1-4000-841e-3fbfcb5e1ce9.png) [^12]

 

![286cfc12-276c-4671-8cf1-a008586df43e.png|753.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/286cfc12-276c-4671-8cf1-a008586df43e.png) [^13]

 

 

# *<mark style="background-color:#f8914d;">**NGINX:  creating a static webpages (for resume, portfolio etc)**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

```
sudo amazon-linux-extras install nginx1 -y
```

```
sudo systemctl start nginx
```

```
sudo systemctl status nginx
```

```
sudo systemctl enable nginx
```

 

![f1e5ca8d-f8e5-4e4e-bcbf-d687bbeb03f2.png|671](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/f1e5ca8d-f8e5-4e4e-bcbf-d687bbeb03f2.png) [^14]

 

*Checking nginx web page:*

![88a1b852-7d6a-4070-9781-391733c5afae.png|852.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/88a1b852-7d6a-4070-9781-391733c5afae.png) [^15]

 

 

*Nginx files location:     /usr/share/nginx/html*

```
sudo su
```

```
cd /usr/share/nginx/html
```

![85bfc434-73c7-4aa2-99f6-5d5ccf6f19c0.png|861.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/85bfc434-73c7-4aa2-99f6-5d5ccf6f19c0.png) [^16]

 

 

***Writing a small html page:***

```
echo "<h1> Hello, I am learning DevOps wit AWS<h1>" > hello.html
```

 

![fc158490-f61a-43a6-a6b8-41db66185a9e.png|778](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/fc158490-f61a-43a6-a6b8-41db66185a9e.png) [^17]

 

*Now copy some free html pages to linux server to setup small web page*

 

*Getting permission error. Due to folder permissions issue for other user… so change the permissions.*

![ec44c52e-b11a-48e4-9b69-a7f49c543eb4.png|865.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/ec44c52e-b11a-48e4-9b69-a7f49c543eb4.png) [^18]

 

```
ls -l
```

```
chmod o+w html
```

*Or*

```
chmod o+w -R html
```

```
ls -l
```

![0f5ab240-21aa-48e6-926e-5a69f69117b0.png|598](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/0f5ab240-21aa-48e6-926e-5a69f69117b0.png) [^19]

 

 

*Now started copying the files.*

![af7017df-dd7b-4cfc-8356-84d15afb6ddb.png|819.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/af7017df-dd7b-4cfc-8356-84d15afb6ddb.png) [^20]

 

![4e22c61b-4c58-48d8-b94e-de33ba88523a.png|936.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/4e22c61b-4c58-48d8-b94e-de33ba88523a.png) [^21]

 

*To reflect changes, restart the services*

```
systemctl restart nginx
```

![b9cfd844-e4c0-43e6-8b3d-a1e4cb4f8710.png|720](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/b9cfd844-e4c0-43e6-8b3d-a1e4cb4f8710.png) [^22]

 

 

***front-end servers** = http servers = 80*

*hosts html/js based applications*

 

***back-end servers** = http = 8080  -- tomcat, jboss, etc*

*java, .NET, Python*

 

# *<mark style="background-color:#f8914d;">**Linux Filesystem structure**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

![1434274b-5b90-4105-8c0d-033d3283a1b8.png|739](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/1434274b-5b90-4105-8c0d-033d3283a1b8.png) [^23]

 

 

*/ --> root folder for liux server*

 

*boot --> when server is getting started, server refers this directory and config from grub.cfg*

 

![00d19905-1829-4ef1-9d1b-25ecc53be050.png|828.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/00d19905-1829-4ef1-9d1b-25ecc53be050.png) [^24]

 

![ceb64bc5-aa5f-4f1e-ad58-0b32c35bf9a6.png|707](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/ceb64bc5-aa5f-4f1e-ad58-0b32c35bf9a6.png) [^25]

 

*dev --> devices --> external devices are mounted here*

*etc --> extra configuration  --> all installed software configurations will be saved here. Ex.NGINX software config files*

*home --> users home directory are created here*

*lib/lib64 --> system needs libraries*

*/media --> cd/dvd drive*

*/mnt --> extra disks mount here*

*/opt --> optional , manual installation of services or applications will be downloaded here*

*/proc --> running process will store here with their PID*

*/proc/cpuinfo*

*/proc/meminfo*

 

*/root --> root user home folder*

*/run --> when server starts, server uses this directory as storage*

*/bin --> cat,vim, touch, cd   --> all commands will be present here*

*/sbin --> system commands like root access commands*

*/tmp --> temp files, not important*

*/usr --> all users,*

*/var --> variables --> log files,*

 

 

# *<mark style="background-color:#f8914d;">**Symlink (soft), Hardlink**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*<mark style="background-color:#f8d616;">**SymLink**<!-- {"backgroundCycleColor":"25"} --></mark> **-***

 

*Soft links points to different inode.*

*In soft link data will be lost in the other folder.*

 

*C:\\Users\\user\\AppData\\Local\\Discord\\Update.exe --processStart Discord.exe*

 

*shortcut --> original file location*

 

*symlink = symbolic link*

 

```
touch file1
```

```
echo "Hello DevOps" >file1
```

```
cat file1
```

```
ln -s /home/ec2-user/file1 /tmp/file1-soft
```

```
cd /tmp/
```

```
ls -l
```

```
cat file1-soft
```

 

![80c84415-61a0-4cbb-bac0-5d9df544dbc1.png|801.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/80c84415-61a0-4cbb-bac0-5d9df544dbc1.png) [^26]

 

*Inodes are different -*

```
ls -li
```

```
cd home/ec2-user/
```

```
ls -li
```

![13e2df88-a7db-4862-a887-74291a3c8301.png|845.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/13e2df88-a7db-4862-a887-74291a3c8301.png) [^27]

 

 

***Content is only similar, but Inodes are different.***

![39789f7c-4a70-4e6e-8d38-a40883a3c926.png|435](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/39789f7c-4a70-4e6e-8d38-a40883a3c926.png) [^28]

 

# *<mark style="background-color:#f8914d;">**HardLink -**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

*Hard links points to same inode.*

*In hard link data will be present since its directly points to inode*

 

![cd4ddd68-dbe6-47ff-bd00-285aec99abba.png|455](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/cd4ddd68-dbe6-47ff-bd00-285aec99abba.png) [^29]

 

 

```
ln /home/ec2-user/file1 /tmp/file1-hard     --> command for hard link (if we give ln -s then it’s a soft link)
```

 

![32047657-c397-46f9-8cfd-6be0fa42daf0.png|901.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/32047657-c397-46f9-8cfd-6be0fa42daf0.png) [^30]

 

*Both Inodes are same here*

![e2848358-5422-43f1-9f82-a150cea15742.png|904.3333740234375](https://images.amplenote.com/f669d486-0e86-11ef-bfd1-2e40d90dfe07/e2848358-5422-43f1-9f82-a150cea15742.png) [^31]

 

[^1]: De PUTTY Configuration
    X
    Category:
    . Session
    Data to send to the server
    . Logging
    -. Terminal
    Login details
    Keyboard
    Auto-login username
    ec2-user -
    Bell
    Features
    When username is not specified:
    Window
    Prompt Use system username (chowd)
    Appearance
    Terminal details
    Behaviour
    Translation
    Terminal-type string
    xterm
    +. Selection
    Colours
    Terminal speeds
    38400,38400
    -. Connection
    Data
    Environment variables
    Proxy
    Variable
    Add
    +. SSH
    Serial
    Value
    Remove
    Telnet
    Rlogin
    SUPDUP

[^2]: Key
    Public key for pasting into OpenSSH authorized_keys file:
    ssh-rsa AAAAB3NzaClyc2EAAAADAQABAAABgQDNSEtk5B/I
    +TnUnjDNkmL3Aa8052kgrBYpgGB8NtCJIcZ62qhOVw
    +8L5J98PXhulA2WbMHluWGH4RUr4NKxnjmHNfgVZR+cb/e7fgdxzLCcXix7UzOw/IVzbT
    +gvdeRgPdJUOmkWPhTAJ3VNHEoMWZk7g5HXI9RBXJHfde2YHUyslfLCUzqclbtCS80QLV2euMcrSh7fU8rbdR
    owcFy17RST3KevK9YJ050jOWzrOhO/E1P/WIQ7H/EbNxczq17aGzZxeE7el/AZsWEK3nUvhtBPwxzY9oBVQtyyY
    Key fingerprint:
    ssh-rsa 3072 SHA256:x35iXarZwdp 1glamCDp8mtdJOoqChkXdZ/HbH3k4B3w
    Key comment:
    chowd@Chowdary
    Key passphrase:
    Confirm
    Actions
    Generate a public/private key pair
    Generate
    Load an existing private key file
    Load
    Save the generated key
    Save public key
    Save private key
    Parameters
    Type of key to generate:
    ORSA
    ODSA
    OECDSA
    OEdDSA
    O SSH-1 (RSA)
    Number of bits in a generated key:
    2048

[^3]: PUTTY Key Generator
    X
    File Key Conversions Help
    Key
    Public key for pasting into AmanCCU authorized bonus film.
    ssh-rsa AAAAB3Nzac _ Load private key:
    X
    +TnUnjDNkmL3AaorOf
    +8L5J98PXhulA2WbM
    +gvdeRgPdJUOmkWPH
    -)
    < Professional (E:) > AWSDevOps > Keys
    V
    C
    Search Keys
    owCFy17RST3KevK9Y.
    Key fingerprint:
    S
    Organize
    New folder
    ?
    Key comment:
    ch
    Videos
    Name
    Date modified
    Type
    Key passphrase:
    MyRecordings
    keypair1.pem
    29-11-2023 16:42
    PEM File
    Confirm
    Youtube
    keypair1.pub
    29-11-2023 16:42
    PUB File
    Actions
    chowd
    Screenshots
    Generate a public/privat
    Load an existing private
    This PC
    Save the generated key
    Local Disk (C:)
    Parameters
    Personal (D:)
    Type of key to generate
    Professional (E:)
    O RSA
    Network
    Number of bits in a gene
    LCUSA
    ULOUSA
    File name: keypair1.pem
    V
    All Files (\*.\*)
    Open
    Cancel

[^4]: Key
    Public key for pasting into OpenSSH authorized_keys file:
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDNSEtk5B/I
    +TnUnjDNkmL3Aa8052kgrBYpgGB8NtCJIcZ62qhOVw
    +8L5J98PXhulA2WbMHluWGH4RUr4NKxnjmHNfgVZR+cb/e7fgdxzLCcXix7UzOw/IVzbT
    +gvdeRgPdJUOmkWPhTAJ3VNHEoMWZk7g5HXI9RBXJHfde2YHUysifLCUzqclbtCS80QLV2euMcrSh7fU8rbdR
    owcFy17RST3KevK9YJ050jOWzrOhO/E1P/WIQ7H/EbNxczq17aGzZxeE7el/AZsWEK3nUvhtBPwxzY9oBVQtyyY
    Key fingerprint:
    ssh-rsa 3072 SHA256:x35iXarZwdp 1glamCDp8modJOoqChkXdZ/HbH3k4B3w
    Key comment:
    chowd@Chowdary
    PuTTYgen Notice
    X
    Key passphrase:
    Confirm
    Successfully imported foreign key
    -.
    Actions
    (OpenSSH SSH-2 private key (new format)).
    Generate a public/private key pair
    To use this key with PUTTY, you need to
    use the "Save private key" command to
    Load an existing private key file
    save it in PUTTY's own format.
    Save the generated key
    key
    OK
    Parameters
    Type of key to generate:
    ORSA
    ODSA
    OECDSA
    EdDSA
    SSH-1 (RSA)

[^5]: File Key Conversions Help
    Key
    Public key for pasting into OpenSSH authorized_keys file:
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDNSEtk5B/I
    +TnUnjDNkmL3Aa8052kgrBYpgGB8NtCJIcZ62qhOVw
    +8L5J98PXhulA2WbMHluWGH4RUr4NKxnjmHNfgVZR+cb/e7fgdxzLCcXix7UzOw/IVzbT
    +gvdeRgPdJUOmkWPhTAJ3VNHEoMWZk7g5HXI9RBXJHfde2YHUyslfLCUzqclbtCS80QLV2euMcrSh7fU8rbdR
    owcFy17RST3KevK9YJ050jOWzrOhO/E1P/WIQ7H/EbNxczq17aGzZxeE7el/AZsWEK3nUvhtBPwxzY90BVQtyyY
    Key fingerprint:
    ssh-rsa PuTTYgen Warning
    X H3k4B3w
    Key comment:
    chowd@
    Key passphrase:
    Are you sure you want to save this key
    .
    without a passphrase to protect it?
    Confirm
    Actions
    Yes
    No
    Generate a public/private key
    Generate
    Load an existing private key file
    Load
    Save the generated key
    Save public key
    Save private key
    Parameters
    Type of key to generate:
    ORSA
    ODSA
    OECDSA
    EdDSA
    OSSH-1 (RSA)

[^6]: PUTTY Key Generator
    X
    File Key Conversions Help
    Key
    Public key for parting into Anan CCU authorized baun film
    ssh-rsa AAAAL Save private key as:
    X
    +TnUnjDNkmL
    +8L5J98PXhul
    +gvdeRgPdJU
    -)
    "< Professional (E:) > AWSDevOps > Keys
    V
    C
    Search Keys
    OwCFy17RST3
    Key fingerprint:
    Organize
    New folder
    = .
    ?
    Key comment:
    MyRecordings
    Name
    Date modified
    Type
    Key passphrase
    Youtube
    keypair1.ppk
    02-12-2023 12:28
    PUTTY Private Key Fi
    Confirm
    Screenshots
    1 Keys
    Actions
    Generate a put
    This PC
    Load an existing
    Local Disk (C:)
    Save the gener
    Personal (D:)
    Parameters
    Professional (E:)
    Type of key to g
    Network
    ORSA
    Number of bits
    File name: keypair1.ppk
    Save as type: PUTTY Private Key Files (\*.ppk)
    Sav
    ^ Hide Folders
    Save
    Cancel

[^7]: PUTTY Configuration
    X
    Category:
    . Logging
    Credentials to authenticate with
    -. Terminal
    Public-key authentication
    Keyboard
    Bell
    Private key file for authentication:
    Features
    Browse...
    -. Window
    Appearance
    X
    Behaviour
    Select private key file
    Translation
    +. Selection
    -)
    < Professional (E:) > AWSDevOps > Keys
    V C
    Search Keys
    .Colours
    . Connection
    Data
    Organize
    New folder
    ?
    Proxy
    G. SSH
    MyRecordings
    Name
    Date modified
    Type
    Kex
    Host keys
    Youtube
    keypair1.ppk
    02-12-2023 12:28
    PUTTY Private Key F
    Cipher
    Screenshots
    .Auth
    Credentials
    Keys
    L. GSSAPI
    TTY
    X11
    This PC
    Tunnels
    Runs
    Local Disk (C:)
    About
    Personal (D:)
    Professional (E:)
    AWSDevOps
    Softwares
    Network
    File name: keypair1.ppk
    PUTTY Private Key Files (\*.ppk)
    Open
    Cancel

[^8]: De PUTTY Configuration
    X
    Category:
    . Session
    Basic options for your PUTTY session
    L.. Logging
    -.Terminal
    Specify the destination you want to connect to
    Keyboard
    Host Name (or IP address)
    Port
    Bell
    22
    Features
    Window
    Connection type:
    Appearance
    O SSH O Serial OOther: Telnet
    V
    Behaviour
    Translation
    Load, save or delete a stored session
    +. Selection
    .. Colours
    Saved Sessions
    . Connection
    DevOps
    Data
    Default Settings
    Load
    Proxy
    DevOps
    . SSH
    Save
    Kex
    Host keys
    Delete
    Cipher
    .Auth
    Credentials
    GSSAPI
    Close window on exit:
    TTY
    Always Never
    Only on clean exit
    X11
    Tunnels
    About
    Open
    Cancel

[^9]: PUTTY Configuration
    X
    Category:
    . Session
    Basic options for your PUTTY session
    L. Logging
    B.Terminal
    Specify the destination you want to connect to
    Keyboard
    Host Name (or IP address)
    Port
    Bell
    54.175.33.148
    22
    Features
    -. Window
    Connection type:
    Appearance
    O SSH O Serial OOther:
    Telnet
    Behaviour
    Translation
    Load, save or delete a stored session
    +. Selection
    ... Colours
    Saved Sessions
    -. Connection
    Data
    Default Settings
    Load
    . Proxy
    DevOps
    +
    SSH
    Save
    Serial
    Telnet
    Delete
    Rlogin
    SUPDUP

[^10]: ec2-user@ip-172-31-44-101:\~
    0
    Using username "ec2-user"
    Authenticating with public key "chowd@Chowdary"
    Last login: Sat Dec 2 07:09:33 2023 from 106.51.165.9
    #
    # # # #
    Amazon Linux 2
    # # # # # \\
    \\# # #1
    AL2 End of Life is 2025-06-30.
    #7
    A newer version of Amazon Linux is available!
    Amazon Linux 2023, GA and supported until 2028-03-15.
    m
    https ://aws . amazon . com/linux/amazon-linux-2023/
    \[ec2-user@ip-172-31-44-101 \~\]$ \[

[^11]: SuperPUTTY - 54.175.33.148
    File View Tools Help
    Protocol SSH
    Host 54.175.33.148
    Login
    Password
    Session DevOps
    - X
    ...\*
    Commands
    54.175.33.148
    54.175.33.148
    54.175.33.148
    L
    Using username "ec2-user".
    Authenticating with public key "chowd@Chowdary"
    Last login: Sat Dec 2 07:24:25 2023 from 106. 51 . 165.9
    #
    # # # #
    Amazon Linux 2
    #####\\
    NN
    \\### 1
    AL2 End of Life is 2025-06-30.
    1# /
    NN
    V\~1 1->
    NNN
    A newer version of Amazon Linux is available!
    NN
    Amazon Linux 2023, GA and supported until 2028-03-15.
    m
    https: //aws . amazon . com/linux/amazon-linux-2023/
    \[ec2-user@ip-172-31-44-101 \~\] $

[^12]: Documents - WinSCP
    0
    X
    Left Mark Files Commands Tabs Options Right Help
    Synchronize
    Queue \* Transfer Settings Default
    Documents - Documents _ New Tab -
    My documents . . Y . BAG
    My docun . . Y . On G A Find Files
    Copy . ' Edit \~ X / Pro @ Login
    X
    A -+ - Mal
    C:\\Users\\chowd\\OneDrive\\Documents\\
    Name
    Size
    New Site
    Session
    Changed
    L
    DevOps
    File protocol:
    02-12-2023 12:50:55
    GitHub
    SFTP
    29-11-2023 12:16:48
    OneNote Notebooks
    27-11-2023 12:11:21
    Host name:
    Port number:
    SuperPUTTY
    54.175.33.148
    224
    02-12-2023 12:56:47
    Zoom
    26-11-2023 09:09:54
    User name:
    Password:
    ec2-user
    Save
    Cancel
    Advanced...
    Tools
    Manage
    Login
    Close
    Help
    Show Login dialog on startup and when the last session is closed

[^13]: DevOps - WinSCP
    Left Mark Files Commands Tabs Options Right Help
    Synchronize
    a Queue . Transfer Settings Default
    DevOps X New Tab -
    My documents . . Y . bond --.
    My docun . . Y . one Find Files
    A + - MON - Saladold / X - HP3 - dog
    A + - MON - Saladold / X - HP3 / - dog
    :\\Users\\chowd\\OneDrive\\Documents\\
    C:\\Users\\chowd\\OneDrive\\ Documents\\
    Name
    Size Type
    Changed
    Name
    Size Type
    Changed
    t ..
    Parent directory
    DevOps
    X
    Parent directory
    02-12-2023 12:50:55
    GitHub
    File folder
    File folder
    29-11-2023 12:16:48
    OneNote Notebooks
    File folder
    ONN
    Searching for host...
    File folder
    27-11-2023 12:11:21
    SuperPUTTY
    File folder
    Connecting to host...
    File folder
    02-12-2023 12:56:47
    Zoom
    File folder
    Authenticating...
    File folder
    26-11-2023 09:09:54
    Warning
    ?
    X
    Continue connecting to an unknown server and add its host
    key to a cache?
    The server's host key was not found in the cache. You have no guarantee that the
    server is the computer you think it is.
    The server's Ed25519 key details are:
    Algorithm: ssh-ed25519 255
    SHA-256: N3uNmlOHK3H9xE2GGwSC4E5SjBGJfPA+nAcYLZ+7AU8
    MD5:
    b8:ce:53:62:f2:3d:49:8c:9d:db:9c:4f: 19:10:a6:42
    If you trust this host, press Yes. To connect without adding host key to the cache,
    press No. To abandon the connection press Cancel.
    Copy key fingerprints to clipboard
    Yes
    No
    Cancel
    Help
    ORofORin Onf 4

[^14]: \[ec2-user@ip-172-31-44-101 \~\]$ sudo systemctl start
    nginx
    \[ec2-user(ip-172-31-44-101 \~\]$ sudo systemctl statu
    s nginx
    nginx . service - The nginx HTTP and reverse proxy
    server
    Loaded: loaded (/usr/lib/systemd/system/nginx . se
    rvice; disabled; vendor preset: disabled)
    Active: active (running) since Sat 2023-12-02 07
    : 46:18 UTC; 33s ago
    Process: 555 ExecStart=/usr/sbin/nginx (code=exit
    ed, status=0/SUCCESS)
    Process: 550 ExecStartPre=/usr/sbin/nginx -t (cod
    e=exited, status=0/SUCCESS)
    Process: 549 ExecStartPre=/usr/bin/rm -f run/ngi

[^15]: notes/session-05.txt at master . d X
    Instances \| EC2 \| us-east-1
    X
    Welcome to nginx!
    X
    +
    C
    Not secure
    54.175.33.148
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^16]: \[ec2-user@ip-172-31-44-101 \~\]$ cd /usr/share/nginx/html
    \[ec2-user(ip-172-31-44-101 html\] $ 1s -1
    total 16
    -rw-r--r-- 1 root root 3665 Oct 13 13:34 404.html
    -rw-r--r-- 1 root root 3708 Oct 13 13:34 50x.html
    drwxr-xr-x 2 root root
    27 Dec 2 07:40 icons
    rw-r--r-- 1 root root 615 Oct 13 13:35 index. html
    -- 1 root root
    368 Oct 13 13:34 nginx-logo . png
    lrwxrwxrwx 1 root root
    14 Dec 2 07:40 poweredby .png -> nginx-logo . png
    \[ec2-user@ip-172-31-44-101 html\] $\]

[^17]: () notes/session-05.txt at master . d X
    Instances \| EC2 \| us-east-1
    X
    54.175.33.148/hello.html
    X
    +
    G
    Not secure
    54.175.33.148/hello.html
    Hello, I am learning Devops wit AWS

[^18]: ta qi- daws-76s - WinSCP
    Local Mark Files Commands Tabs Options Remote Help
    ED Synchronize 3 0 Queue . \| Transfer Settings Default
    daw:-76: X New Tab -
    C: Local Disk
    html . . . + . . 2 0 Find Files
    mai Upload . D Edit . X % Properties . New . +
    Download . 2 Edit \~ X / F Properties . New - +
    C:\\Users\\user\\Downloads\\qiqi
    just/share/nginx/html/
    Size Type
    Changed
    Name
    Size Changed
    Rights
    Owner
    Name
    6/7/2023 8:38:07 pm
    1/12/2023 7:41:51 am
    rwxr-xr-x
    root
    L ..
    Parent directory
    icons
    1/12/2023 7:41:51 am
    rwxr-xr-x
    root
    assets
    File folder
    6/7/2023 8:38:09 pm
    50x.html
    4 KB 13/10/2023 7:04:10 pm
    rw-f-.f--
    root
    details.html
    2 KB Chrome HTML Do.. 6/7/2023 8:38:07 pm
    404.html
    4 KB 13/10/2023 7:04:10 pm
    rw.f-...
    root
    index.html
    13 KB Chrome HTML Do.. 6/7/2023 8:38:07 pm
    hello.html
    1 KB 1/12/2023 7:44:03 am
    rw-r-.r--
    root
    nginx-logo.png
    1 KB 13/10/2023 7:04:10 pm
    root
    poweredby.png
    1 KB 1/12/2023 7:41:51 am
    rxrxrwx
    root
    Error
    ?
    X
    X
    Error creating folder '/usr/share/nginx/html/assets'.
    Permission denied.
    Error code 3
    Error message from server. Permission denied
    Abort
    Retry
    Skip
    Skip all
    Help

[^19]: \[root@ip-172-31-44-101 html\]# cd . .
    \[root@ip-172-31-44-101 nginx\]# 1s -1 \| html
    bash: html: command not found
    \[root@ip-172-31-44-101 nginx\]# 1s -1
    total 0
    drwxr-xr-x 3 root root 112 Dec 2 08:14 html
    drwxr-xr-x 2 root root
    6 Oct 13 13:35 modules
    \[root@ip-172-31-44-101 nginx\]# chmod 0+w html
    chmod: invalid mode: '0+w'
    Try 'chmod --help' for more information.
    \[root@ip-172-31-44-101 nginx\]# chmod otw html
    \[root@ip-172-31-44-101 nginx\]#
    \[root@ip-172-31-44-101 nginx\]# 1s -1
    total 0
    drwxr-xrwx 3 root root 112 Dec 2 08:14 html
    drwxr-xr-x 2 root root
    6 Oct 13 13:35 modules
    \[root@ip-172-31-44-101 nginx\]#

[^20]: Local Mark Files Commands Tabs Options Remote Help
    Synchronize
    Queue \* Transfer Settings Default
    DevOps X New Tab -
    C: Local Disk . . Y . zone
    html
    . Y . Guna Find Files
    1 1
    Upload . ' Edit - X Properties .
    New
    + -
    Download . ' Edit . X Properties
    New
    +
    A
    C:\\Users\\chowd\\Downloads\\creative-cv_free_1-1-0\\
    usr/share/nginx/html/
    Name
    Size Type
    Changed
    Name
    Size Changed
    Rights
    Ow
    L ..
    Parent directory
    02-12-2023 13:46:31
    L ..
    02-12-2023 13:10:13
    rwxr-xr-x
    roo
    CSS
    File folder
    02-12-2023 13:46:30
    icons
    02-12-2023 13:10:13
    rwxr-xr-x
    root
    images
    File folder
    02-12-2023 13:46:31
    50x.html
    4 KB 13-10-2023 19:04:10
    rw-r--r--
    roo
    is
    File folder
    02-97% Uploading
    ?
    X
    4 KB 13-10-2023 19:04:10
    rw-r--r--
    root
    scripts
    File folder
    02-
    1 KB 02-12-2023 13:29:37
    rw-r--r--
    root
    File:
    C:\\...\\creative-cv_free_1-1-0\\creative-cv.png
    creative-cv.png
    2,598 KB PNG File
    02-
    Target:
    /usr/share/nginx/html/
    1 KB 13-10-2023 19:04:10
    rw-r--r--
    roo
    cv favicon.ico
    6 KB ICO File
    02
    1 KB 02-12-2023 13:10:13
    rwxrwxrwx
    root
    index.html
    30 KB Microsoft Edge HT...
    02.
    LICENSE-free.txt
    2 KB Text Document
    02
    Time left:
    0:00:16 Time elapsed:
    0:08:37
    Bytes transferred:
    4.32 MB Speed:
    6.51 KB/s
    README.txt
    2 KB Text Document
    02
    XHI -
    Unlimited

[^21]: \[root@ip-172-31-44-101 ec2-user\]# cd /usr/share/nginx/html
    \[root@ip-172-31-44-101 html\]# 1s -1
    total 2668
    -rw-r--r-- 1 root
    root
    3665 Oct 13 13:34 404.html
    -rw-r--r--
    1 root
    root
    3708 Oct 13 13:34 50x. html
    -rw-rw-r-- 1 ec2-user ec2-user 2660172 Dec 2 08:16 creative-cv.png
    drwxrwxr-x 2 ec2-user ec2-user
    62 Dec
    2 08:24 css
    -rw-rw-r-- 1 ec2-user ec2-user
    5558 Dec
    2 08:16 favicon . ico
    -rw-r--r-- 1 root
    root
    45 Dec
    2 07:59 hello. html
    drwxr-xr-x 2 root
    root
    27 Dec
    2 07:40 icons
    drwxrwxr-x 2 ec2-user ec2-user
    4096 Dec
    2 08:27 images
    rw-rw-r-- 1 ec2-user ec2-user
    30434 Dec
    2 08:16 index. html
    drwxrwxr-x 4 ec2-user ec2-user
    68 Dec
    2 08:27 js
    -rw-rw-r-- 1 ec2-user ec2-user
    1145 Dec 2 08:16 LICENSE-free . txt
    -rw-r--r-- 1 root
    root
    368 Oct 13 13:34 nginx-logo .png
    lrwxrwxrwx 1 root
    root
    14 Dec 2 07:40 poweredby .png -> nginx-logo .png
    -rw-rw-r-- 1 ec2-user ec2-user
    1926 Dec
    2 08:16 README . txt
    drwxrwxr-x 4 ec2-user ec2-user
    48 Dec
    2 08:28 scripts
    \[root@ip-172-31-44-101 html\] #
    \[root@ip-172-31-44-101 html\] #

[^22]: \[root@ip-172-31-44-101 html\]# systemctl restart nginx
    \[root@ip-172-31-44-101 html\] #

[^23]: \[ec2-user@ip-172-31-44-8 \~\]$ cd /
    \[ec2-user@ip-172-31-44-8 /\]$ 1s -1
    total 16
    lrwxrwxrwx
    1 root root
    7 Nov 16 23:32 bin -> usr/bin
    dr-xr-xr-x
    4 root root 4096 Nov 16 23:33 boot
    drwxr-xr-x 15 root root 2900 Dec 1 01:59 dev
    drwxr-xr-x 82 root root 8192 Dec 1 02:11 etc
    drwxr-xr-x
    3 root root
    22 Dec 1 01:59 home
    lrwxrwxrwx
    1 root root
    7 Nov 16 23:32 lib -> usr/lib
    lrwxrwxrwx
    1 root root
    9 Nov 16 23:32 lib64 -> usr/lib64
    drwxr-xr-x
    2 root root
    6 Nov 16 23:32 local
    drwxr-xr-x
    2 root root
    6 Apr 9 2019 media
    drwxr-xr-x
    2 root root
    6 Apr 9 2019 mnt
    drwxr-xr-x
    4 root root
    27 Nov 16 23:33 opt
    dr-xr-xr-x 160 root root
    0 Dec 1 01:59 proc
    dr-xr-x--
    3 root root 124 Dec 1 02:23 root
    drwxr-xr-x 28 root root 1000 Dec 1 02:18 run
    lrwxrwxrwx
    1 root root
    8 Nov 16 23:32 sbin -> usr/sbin
    drwxr-xr-x
    2 root root
    6 Apr 9 2019 srv
    dr-xr-xr-x 13 root root
    0 Dec 1 01:59 sys
    drwxrwxrwt
    9 root root 249 Dec 1 02:18 tmp
    drwxr-xr-x 13 root root 155 Nov 16 23:32 usr
    drwxr-xr-x 19 root root 269 Dec 1 01:59 varj
    \[ec2-user@ip-172-31-44-8 /\]$

[^24]: \[ec2-user@ip-172-31-44-8 /\]$ cd boot/
    \[ec2-user@ip-172-31-44-8 boot\] $ 1s -1
    total 26384
    -rw-r--r-- 1 root root
    143682 Nov 4 17:00 config-5. 10. 199-190 . 747. amzn2 . x86 64
    drwxr-xr-x 3 root root
    17 Nov 16 23:33 efi
    drwx-
    5 root root
    79 Nov 16 23:34 grub2
    rw
    1 root root 11114152 Nov 16 23:33 initramfs-5.10.199-190. 747. amzn2 . x86 64. ing
    -rw-r--r--
    1 root root
    652524 Nov 16 23:33 initrd-plymouth . ing
    rw-r--r--
    1 root root
    264661 Nov
    4 17:00 symvers-5 . 10.199-190. 747. amzn2 . x86 64 . gz
    -rw-
    1 root root 4702391 Nov
    4 17:00 System. map-5 . 10. 199-190. 747 . amzn2 . x86 64
    rwxr-xr-x 1 root root 10121280 Nov
    4 17:00 vmlinuz-5 . 10. 199-190. 747. amzn2 . x86 64

[^25]: \[root@ip-172-31-44-8 \~\]# cd /boot/grub2/
    \[root@ip-172-31-44-8 grub2\]# 1s -1
    total 28
    drwx
    - ----
    2 root root
    25 Nov 16 23:32 fonts
    -rw
    1 root root 4470 Nov 16 23:34 grub . cfg
    W
    1 root root 1024 Oct 11 09:43 grubenv
    drwxr-xr-x 2 root root 8192 Nov 16 23:34 1386-pc
    drwxr-xr-x 2 root root 4096 Nov 16 23:34 locale

[^26]: \[ec2-user@ip-172-31-44-101 \~\]$ touch file1
    -
    \[ec2-user@ip-172-31-44-101 \~\]$ echo "Hello Devops" >file1
    \[ec2-user@ip-172-31-44-101 \~\]$ cat file1
    Hello Devops
    \[ec2-user@ip-172-31-44-101 \~\]$ 1n -s /home/ec2-user/file1 /tmp/file1-soft
    \[ec2-user@ip-172-31-44-101 \~\] $
    \[ec2-user@ip-172-31-44-101 \~\]$ cd /tmp/
    \[ec2-user@ip-172-31-44-101 tmp\] $ 1s -1
    total 0
    lrwxrwxrwx 1 ec2-user ec2-user 20 Dec 2 09:56 file1-soft -> /home/ec2-user/file1
    drwx--
    3 root
    root
    17 Dec
    2 06:29 systemd-private-1338c686869d4dc1bdad9092723c3c08-chronyd. service
    zt5rr
    drwx-
    3 root
    root
    17 Dec 2 08:35 systemd-private-1338c686869d4dc1bdad9092723c3c08-nginx . service-
    ha7
    \[ec2-user@ip-172-31-44-101 tmp\] $
    \[ec2-user@ip-172-31-44-101 tmp\]$ cat file1-soft
    Hello Devops
    \[ec2-user@ip-172-31-44-101 tmp\] $\[\]

[^27]: \[ec2-user@ip-172-31-44-8 tmp\] $ 1s -li
    total 0
    538396 1rwxrwxrwx 1 ec2-user ec2-user 20 Dec
    1 03:02 hello-soft -> /home/ec2-user/hello
    8410288 drwx--
    3 root
    root
    17 Dec
    1 01:59 systemd-private-a37eac747d8b4celbc90a0ed0d6e20e3-chronyd. service-
    538895 drwx--
    3 root
    root
    17 Dec 1 02:18 systemd-private-a37eac747d8b4celbc90a0ed0d6e20e3-nginx. service-BH
    \[ec2-user@ip-172-31-44-8 tmp\] $ cd /home/ec2-user/
    \[ec2-user@ip-172-31-44-8 \~\]$ 1s -li -
    total 4
    12586038 -rw-rw-r-- 1 ec2-user ec2-user 12 Dec 1 03:02 hello
    \[ec2-userip-172-31-44-8 \~\] $

[^28]: 12586038
    memory
    inode
    inode
    Actual file
    symlink

[^29]: inode
    actual file
    hard link

[^30]: \[ec2-user@ip-172-31-44-101 tmp\]$ In /home/ec2-user/file1 /tmp/file1-hard
    \[ec2-user@ip-172-31-44-101 tmp\] $
    \[ec2-user@ip-172-31-44-101 tmp\] $ 1s -1
    total 4
    -rw-rw-r-- 2 ec2-user ec2-user 13 Dec 2 09:52 file1-hard
    1rwxrwxrwx 1 ec2-user ec2-user 20 Dec 2 09:56 file1-soft -> /home/ec2-user/file1
    drwx-
    3 root
    root
    17 Dec
    2 06:29 systemd-private-1338c686869d4dc1bdad9092723c3c08-chronyd. service-
    Zt5rr
    drwx-
    3 root
    root
    17 Dec 2 08:35 systemd-private-1338c686869d4dc1bdad9092723c3c08-nginx . service-ya
    ha7
    \[ec2-user@ip-172-31-44-101 tmp\] $

[^31]: \[ec2-user@ip-172-31-44-101 tmp\] $ 1s -i
    13130687 file1-hard
    8410288 systemd-private-1338c686869d4dc1bdad9092723c3c08-chronyd. service-xZt5rr
    518212 file1-soft
    4211565 systemd-private-1338c686869d4dc1bdad9092723c3c08-nginx . service-yaEha7
    \[ec2-user@ip-172-31-44-101 tmp\] $
    \[ec2-user@ip-172-31-44-101 tmp\] $ cd /home/ec2-user/
    \[ec2-user@ip-172-31-44-101 \~\]$ 1s -i
    13130687 file1
    \[ec2-user@ip-172-31-44-101 \~\]$

