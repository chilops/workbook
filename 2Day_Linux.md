---
title: 2Day_Linux
uuid: 568a17ea-0a27-11ef-a586-5658f55e0c13
version: 262
created: '2024-05-04T20:32:34+05:30'
tags:
  - linux
---

*<mark style="background-color:#f3de6c;">Topics:<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Linux Commands<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">ls<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">CRUD<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">File creation - touch<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Folder/directory creation - mkdir<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Cat commands<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Remove a file, directory  - rm, rmdir<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Copy command - cp<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Move\\cut\\rename command - mv<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Grep commands<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Wget vs curl commands<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Echo command<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Cut & AWK commands (V.Imp uses in daily work & scripting)<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Head & tail commands<!-- {"backgroundCycleColor":"14"} --></mark>*

1. *<mark style="background-color:#f3de6c;">Editors - VIM<!-- {"backgroundCycleColor":"14"} --></mark>*

\

# <mark style="background-color:#f8914d;">**List commands : LS**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

*#ls          --> list subdirectories*

*#ls -l      -->lengthy format in alphabetic order*

*#ls -lr    --> reverse alphabetic order*

*#ls -lt    --> latest files are on the top*

*#ls -ltr   --> old files are on the top*

*#ls -la   --> list all files and folders including hidden*

 

 

*drwxr-xr-x  15 root root 2900 Nov 28 01:53 dev*

*d --> stands for directory*

*-  --> file*

\

# *<mark style="background-color:#f8914d;">**CRUD**  --> every operation is curd. Means you create, read, update & delete any operations<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*--------------------*

*create*

*read*

*update*

*Delete*

\

\

# *<mark style="background-color:#f8914d;">**Touch: **<!-- {"backgroundCycleColor":"24"} --></mark>creates a empty file*<!-- {"collapsed":true} -->

```
touch file1 file2
```

![c593615f-591f-4d57-823c-3b7a3808b43d.png|496](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/c593615f-591f-4d57-823c-3b7a3808b43d.png) [^1]

 

# *<mark style="background-color:#f8914d;">**Mkdir:**<!-- {"backgroundCycleColor":"24"} --></mark> To create a directory*<!-- {"collapsed":true} -->

```
mkdir direct1
```

![f4264de0-6aab-4f35-a960-d4dc22204e0b.png|488](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/f4264de0-6aab-4f35-a960-d4dc22204e0b.png) [^2]

 

*Can create multiple directories at same time:*

```
mkdir direct2 direct3
```

![5a60f793-0d3a-4038-93de-cd76c300344b.png|549](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/5a60f793-0d3a-4038-93de-cd76c300344b.png) [^3]

 

# *<mark style="background-color:#f8914d;">**CAT commands:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
cat > file1       --> To write data in to a file (ctrl+d to save a file) Note: It always replaces the content
```

```
cat >> file1     -->  >> appends the data, no data loss(previous data will be present)
```

```
cat                   --> To view data in a file
```

 

![c4a0c919-6455-4dc0-bce6-5466f660d22b.png|421](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/c4a0c919-6455-4dc0-bce6-5466f660d22b.png) [^4]

 

![5c724da8-6710-4df9-b6b1-6c9532b2411e.png|480](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/5c724da8-6710-4df9-b6b1-6c9532b2411e.png) [^5]

\

\

# *<mark style="background-color:#f8914d;">**Remove files: rm**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
rm file2
```

![90032527-5d14-428d-8637-1c92a04d65b7.png|502](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/90032527-5d14-428d-8637-1c92a04d65b7.png) [^6]

 

# *<mark style="background-color:#f8914d;">**Remove Directory: rm**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*It removes empty directory (**Note: we can't delete if any files or directories present in that folder**)* 

```
rmdir direct3  
```

![8cf08136-296b-4d9d-b113-1bfc513cdb1d.png|526](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/8cf08136-296b-4d9d-b113-1bfc513cdb1d.png) [^7]

 

```
cd direct2
```

```
touch satyafile sanjayfile
```

```
ls -l
```

```
cd ..
```

```
rmdir direct2
```

```
rm -r direct2   --> -r is recursive, it helps to delete all files/folders present in that directory recursively.
```

```
 ls -l
```

![9055677d-8e6e-419d-8c43-9428cc0d4dfb.png|566](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/9055677d-8e6e-419d-8c43-9428cc0d4dfb.png) [^8]

 

 

# *<mark style="background-color:#f8914d;">**Copy commands: cp**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

***1st method***

```
cp file2 direct1/
```

![f9614f2a-bec3-4941-96f7-8ce0685a0b87.png|487](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/f9614f2a-bec3-4941-96f7-8ce0685a0b87.png) [^9]

 

***2nd method:***

```
cp /etc/passwd passwd      --> copy a file from /etc/passwd to current directory
```

 

![4f1fc2a3-04b2-401c-8a3b-47ffe5f2e03b.png|502](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/4f1fc2a3-04b2-401c-8a3b-47ffe5f2e03b.png) [^10]

 

*If we try to copy a directory which files already exist then we need to use -r (recursive option)*

```
cp -r satya/ madhu/
```

![147d7609-f593-475c-b690-10835bb57a98.png|527](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/147d7609-f593-475c-b690-10835bb57a98.png) [^11]

 

 

# *<mark style="background-color:#f8914d;">**Move command**: mv<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#f3de6c;">Move\\cut\\rename command<!-- {"backgroundCycleColor":"14"} --></mark>*<!-- {"collapsed":true} -->

*It moves all files & folders present in that folder.*

```
mv direct1/ devops/  
```

![998212d6-5d19-4b1e-a1d9-62b6270b1b8e.png|557](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/998212d6-5d19-4b1e-a1d9-62b6270b1b8e.png) [^12]

 

 

***Move command also works as rename a folder/file** with in the same folder if you use mv command, it works as rename*

![27efbfe3-58e1-4273-951a-a0c0ac2a8347.png|574](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/27efbfe3-58e1-4273-951a-a0c0ac2a8347.png) [^13]

 

 

# *<mark style="background-color:#f8914d;">**Grep commands:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

```
grep games passwd
```

![251e7716-c28e-4b40-a4f7-d1d8cc89e170.png|737](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/251e7716-c28e-4b40-a4f7-d1d8cc89e170.png) [^14]

\

 *"I" stand for case insensitive (Linux is case sensitive so we need to use -I to get all details)*

```
grep -i devops passwd          
```

![a029c00a-8d3d-4857-9c85-5b69b84b77c2.png|597](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/a029c00a-8d3d-4857-9c85-5b69b84b77c2.png) [^15]

 

***Other method*** 

```
cat passwd | grep -i devops
```

![63553e80-7a13-41c8-adfe-1e2a95055d65.png|549](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/63553e80-7a13-41c8-adfe-1e2a95055d65.png) [^16]

\

\

# <mark style="background-color:#f8914d;">**wget vs curl:**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

 

***wget:**    If I want to download any file from website, then we can use wget command (wget is webget)*

\

*#wget* [*https://github.com/git-for-windows/git/releases/download/v2.43.0.windows.1/Git-2.43.0-64-bit.exe*](https://github.com/git-for-windows/git/releases/download/v2.43.0.windows.1/Git-2.43.0-64-bit.exe) 

 

![af67ad46-72cb-46f7-a57c-41be6d0b126e.png|1031.3333740234375](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/af67ad46-72cb-46f7-a57c-41be6d0b126e.png) [^17]

 

 

# *<mark style="background-color:#f8914d;">**curl**<!-- {"backgroundCycleColor":"24"} --></mark> --> downloads the text content directly on to terminal*<!-- {"collapsed":true} -->

 

![92b6f245-c05a-438f-adcb-87c7663b14d7.png|879.3333740234375](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/92b6f245-c05a-438f-adcb-87c7663b14d7.png) [^18]

 

 

*Copy below link*

![e41d071c-6fa3-47f1-9c6b-b90da43b46df.png|760](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/e41d071c-6fa3-47f1-9c6b-b90da43b46df.png) [^19]

 

\

\

 *#curl* [*https://raw.githubusercontent.com/daws-76s/notes/master/session-02.txt*](https://raw.githubusercontent.com/daws-76s/notes/master/session-02.txt)   *-->It shows full data*

 

![466faaac-2664-47ec-aff3-51258bb10cb6.png|876](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/466faaac-2664-47ec-aff3-51258bb10cb6.png) [^20]

 

 

# *<mark style="background-color:#f8914d;">**Echo:**<!-- {"backgroundCycleColor":"24"} --></mark> This command acts as a print..*<!-- {"collapsed":true} -->

 

*# echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) 

*# echo hello DevOps world*

 

![a0f6ad60-d10c-41dd-91ed-2cf2168c2d99.png|884](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/a0f6ad60-d10c-41dd-91ed-2cf2168c2d99.png) [^21]

 

 

# *<mark style="background-color:#f8914d;">**CUT:**<!-- {"backgroundCycleColor":"24"} --></mark>  **We will use cut command to divide into fragments by using delimiter. This command uses in scripting mostly.***<!-- {"collapsed":true} -->

\

*If I want to cut(delimiter) below link into small segments then we can use.*

 

*Delimiter--> it can be : or / or any other…we get as small fragments*

 

[*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) 

 

*#cut -d / -f1         --> -d is delimiter, / or : is partition, -f is frag,emt*

 

*# echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| cut -d / -f 1*

*# echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| cut -d / -f 3*

*# echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| cut -d / -f 6*

*# echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| cut -d : -f 2*

 

![0931840b-23d4-48f4-812f-e42f00077159.png|899](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/0931840b-23d4-48f4-812f-e42f00077159.png) [^22]

 

![4381232f-1516-4d35-9966-7dc17980ccd9.png|898](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/4381232f-1516-4d35-9966-7dc17980ccd9.png) [^23]

 

# *<mark style="background-color:#f8914d;">**AWK:  **<!-- {"backgroundCycleColor":"24"} --></mark>awk command is used to divide the data based on columns*<!-- {"collapsed":true} -->

***same as cut command but a small difference I**n command.*

 

*awk -F / '{print $1F}'      --> it prints 1st fragment*

*awk -F / '{print $NF}'      --> it prints last fragment*

 

*#echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| awk -F / '{print $1F}'*

*#echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| awk -F / '{print $3F}'*

*#echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| awk -F / '{print $6F}'*

*#echo* [*https://github.com/daws-76s/notes/blob/master/session-01.txt*](https://github.com/daws-76s/notes/blob/master/session-01.txt) *\| awk -F / '{print $NF}'*

![71e95dee-bc82-4ec1-83a2-c745f4b7636b.png|882](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/71e95dee-bc82-4ec1-83a2-c745f4b7636b.png) [^24]

 

 

*From a passwd1 file getting users list*

```
cat passwrd1
```

![](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/c9a5e3f3-06a2-4628-81c8-da3dc2fe6a65.png) [^25]

 

```
cat passwd1 | awk -F : '{print $1F}'
```

![ca8912c2-cb57-4044-a62e-aaaf0d9f8c34.png|666](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/ca8912c2-cb57-4044-a62e-aaaf0d9f8c34.png) [^26]

 

![9839a0f2-d024-47ae-aa1b-364752135a09.png|681](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/9839a0f2-d024-47ae-aa1b-364752135a09.png) [^27]

 

# *<mark style="background-color:#f8914d;">**Head & tail commands**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

*#head <file-name> --> shows first 10lines*

*#tail <file-name>    --> shows last 10 lines*

```
head -n 2 passwd1
```

```
head -n 4 passwd1
```

```
tail -n 2 passwd1
```

```
tail -n 3 passwd1
```

*Or*

```
cat passwd1 | head -n 3
```

```
cat passwd1 | tail -n 3
```

![e3bf7f3e-26b4-4de3-b0c7-efe4b284c59c.png|576](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/e3bf7f3e-26b4-4de3-b0c7-efe4b284c59c.png) [^28]

 

 

# *<mark style="background-color:#f8914d;">**VIM editor:**<!-- {"backgroundCycleColor":"24"} --></mark> **It’s a visually improved editor.***<!-- {"collapsed":true} -->

 

*#vim <file name>*

*#:set nu                          -> displays numbers for lines*

*#:set nonu                     -> no displays numbers for lines*

*#:/<word-to-search>   -> search from top*

*#:?<word-to-search>   -> search from bottom*

 

![a4434d87-405d-4851-8763-45ff1e610137.png|566](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/a4434d87-405d-4851-8763-45ff1e610137.png) [^29]

 

 

*#::s/<word-to-find>/<word-to-replace>    --> replace the word where your cursor is, this will replace only first occurrence in that line*

*Ex: #:s/bin/bin-1*

![010c7f4a-12e7-4e70-a3fb-0d12c570b2fa.png|839.3333740234375](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/010c7f4a-12e7-4e70-a3fb-0d12c570b2fa.png) [^30]

 

*Ex: #:s/root/ROOT/g     --> g stands for global -> it will change all words present in that line where cursor is placed.*

![54353365-21bd-4bf9-a791-4b718790c145.png|846.3333740234375](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/54353365-21bd-4bf9-a791-4b718790c145.png) [^31]

 

*Ex: #:2s/Hello/Hi/g       --> in 2nd line it replaces hello to Hi*

![673586a5-5288-44e2-9b2b-0892ce60b076.png|843.3333740234375](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/673586a5-5288-44e2-9b2b-0892ce60b076.png) [^32]

 

*#:%s/<word-to-find>/<word-to-replace>/g     --> it replaces all the words in the file.*

 

*Ex: #:%s/sbin/SBIN/g*

![f04e00b7-1b70-4d26-a6d9-f22f4de61085.png|842.3333740234375](https://images.amplenote.com/568a17ea-0a27-11ef-a586-5658f55e0c13/f04e00b7-1b70-4d26-a6d9-f22f4de61085.png) [^33]

[^1]: \[ec2-user@ip-172-31-18-204 \~\]$ touch file1 file2
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s
    file1 file2
    \[ec2-user@ip-172-31-18-204 \~\]$

[^2]: \[ec2-user@ip-172-31-18-204 \~\]$ mkdir direct1
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s
    direct1 filel file2

[^3]: \[ec2-user@ip-172-31-18-204 \~\]$ mkdir direct2 direct3
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s
    direct1 direct2
    direct3
    filel file2

[^4]: \[ec2-user@ip-172-31-18-204 \~\]$ cat >file1
    Hi I am learning Linux & Devops with AWS
    \[ec2-user@ip-172-31-18-204 \~\]$
    \[ec2-user@ip-172-31-18-204 \~\]$ cat file1
    Hi I am learning Linux & Devops with AWS
    \[ec2-user@ip-172-31-18-204 \~\]$

[^5]: \[ec2-user@ip-172-31-18-204 \~\]$ cat >> file1
    I have 8.3 Years of experience in Storage & Backup.
    AC
    \[ec2-user@ip-172-31-18-204 \~\]$ cat file1
    Hi I am learning Linux & Devops with AWS
    I have 8.3 Years of experience in Storage & Backup.
    \[ec2-user@ip-172-31-18-204 \~\]$

[^6]: \[ec2-user@ip-172-31-18-204 \~\]$ 1s
    direct1 direct2 direct3 filel file2
    \[ec2-user@ip-172-31-18-204 \~\]$ rm file2
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s
    direct1 direct2 direct3 filel
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 4
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:01 direct1
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 15:03 direct2
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 15:03 direct3
    -rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    \[ec2-user@ip-172-31-18-204 \~\] $

[^7]: \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 4
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:01 direct1
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 15:03 direct2
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:03 direct3
    rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:28 file2
    \[ec2-user@ip-172-31-18-204 \~\]$ rmdir direct3
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 4
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:01 direct1
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:03 direct2
    -rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:28 file2
    \[ec2-user@ip-172-31-18-204 \~\]$

[^8]: ec2-user@ip-172-31-18-204 \~\]$ cd direct2
    ec2-user@ip-172-31-18-204 direct2\]$ touch satyafile sanjayfile
    ec2-user@ip-172-31-18-204 direct2\]$ 1s -1
    otal 0
    rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:32 sanjayfile
    rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:32 satyafile
    ec2-user@ip-172-31-18-204 direct2\]$ cd. .
    bash: cd. .: command not found
    ec2-user@ip-172-31-18-204 direct2\]$ cd . .
    ec2-user@ip-172-31-18-204 \~\]$ rmdir direct2
    mdir: failed to remove 'direct2': Directory not empty
    ec2-user@ip-172-31-18-204 \~\]$ rm -r direct2
    ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    otal 4
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:01 direct1
    rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:28 file2
    ec2-user@ip-172-31-18-204 \~\]$

[^9]: \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 4
    drwxrwxr-x 2 ec2-user ec2-user 6 Nov 29 15:01 direct1
    -rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:28 file2
    \[ec2-user@ip-172-31-18-204 \~\]$ cp file2 direct1/
    \[ec2-user@ip-172-31-18-204 \~\]$ cd direct1 -
    \[ec2-user@ip-172-31-18-204 direct1\]$ 1s -1
    total 0
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:40 file2
    \[ec2-user@ip-172-31-18-204 direct1\]$ cd . .
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 4
    drwxrwxr-x 2 ec2-user ec2-user 19 Nov 29 15:40 direct1
    rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    \[ec2-user@ip-172-31-18-204 \~\]$
    31
    18-204

[^10]: \[ec2-user@ip-172-31-18-204 \~\]$ cd /etc/ -
    \[ec2-user@ip-172-31-18-204 etc\]$ 1s -1 passwd -
    -rw-r--r-- 1 root root 1312 Nov 29 12:11 passwd
    \[ec2-user@ip-172-31-18-204 etc\]$ cd
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 4
    drwxrwxr-x 2 ec2-user ec2-user 19 Nov 29 15:40 direct1
    -rw-rw-r-- 1 ec2-user ec2-user 93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 15:28 file2
    \[ec2-user@ip-172-31-18-204 \~\]$ cp /etc/passwd passwd
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 8
    drwxrwxr-x 2 ec2-user ec2-user
    19 Nov 29 15:40 direct1
    -rw-rw-r-- 1 ec2-user ec2-user
    93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    -rw-r--r-- 1 ec2-user ec2-user 1312 Nov 29 15:46 passwd
    \[ec2-user@ip-172-31-18-204 \~\]$

[^11]: \[ec2-user@ip-172-31-18-204 \~\] $
    \[ec2-user@ip-172-31-18-204 \~\]$ mkdir satya
    \[ec2-user@ip-172-31-18-204 \~\]$ cd satya -
    \[ec2-user@ip-172-31-18-204 satya\]$ touch lovel love2 love2
    \[ec2-user@ip-172-31-18-204 satya\]$ 1s -1
    total 0
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 16:03 love1
    -rw-rw-r-- 1 ec2-user ec2-user 0 Nov 29 16:03 love2
    \[ec2-user@ip-172-31-18-204 satya\] $
    \[ec2-user@ip-172-31-18-204 satya\]$ cd . .
    \[ec2-user@ip-172-31-18-204 \~\]$ mkdir madhu
    \[ec2-user@ip-172-31-18-204 \~\]$ cp satya/ madhu/
    cp: omitting directory 'satya/' -
    \[ec2-user@ip-172-31-18-204 \~\]$ cp -r satya/ madhu/
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 8
    -rw-rw-r-- 1 ec2-user ec2-user
    93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    drwxrwxr-x 3 ec2-user ec2-user
    19 Nov 29 16:05 madhu
    -rw-r--r-- 1 ec2-user ec2-user 1312 Nov 29 15:46 passwd
    drwxrwxr-x 2 ec2-user ec2-user
    32 Nov 29 16:03 satya
    \[ec2-user@ip-172-31-18-204 \~\]$ cd madhu/ =
    \[ec2-user@ip-172-31-18-204 madhu\]$ 1s -1
    total 0
    drwxrwxr-x 2 ec2-user ec2-user 32 Nov 29 16:05 satya
    Tec2-userdip-172-31-18-204 madhu1$ !

[^12]: \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 8
    drwxrwxr-x 2 ec2-user ec2-user
    19 Nov 29 15:40 direct1
    -rw-rw-r-- 1 ec2-user ec2-user
    93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    -rw-r--r-- 1 ec2-user ec2-user 1312 Nov 29 15:46 passwd
    \[ec2-user@ip-172-31-18-204 \~\]$
    \[ec2-user@ip-172-31-18-204 \~\]$ cd direct1/
    \[ec2-user@ip-172-31-18-204 direct1\]$ 1s
    file2
    \[ec2-user@ip-172-31-18-204 direct1\]$ cd . .
    \[ec2-user@ip-172-31-18-204 \~\]$ mkdir devops
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 8
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 15:52 devops
    drwxrwxr-x 2 ec2-user ec2-user
    19 Nov 29 15:40 direct1
    rw-rw-r-- 1 ec2-user ec2-user
    93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    -rw-r--r-- 1 ec2-user ec2-user 1312 Nov 29 15:46 passwd
    \[ec2-user@ip-172-31-18-204 \~\]$
    \[ec2-user@ip-172-31-18-204 \~\]$ mv direct1/ devops/
    \[ec2-user@ip-172-31-18-204 \~\]$ cd devops/
    \[ec2-user@ip-172-31-18-204 devops\]$ 1s
    direct1
    \[ec2-user@ip-172-31-18-204 devops\]$ cd direct1/
    \[ec2-user@ip-172-31-18-204 direct1\]$ 1s
    file2
    \[ec2-user@ip-172-31-18-204 direct1\]$ pwd
    /home/ec2-user /devops /direct1
    \[ec2-user@ip-172-31-18-204 direct1\]$ \|

[^13]: \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 8
    -rw-rw-r-- 1 ec2-user ec2-user
    93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 16:09 madhu
    -rw-r--r-- 1 ec2-user ec2-user 1312 Nov 29 15:46 passwd
    drwxrwxr-x 2 ec2-user ec2-user
    32 Nov 29 16:03 satya"
    \[ec2-user@ip-172-31-18-204 \~\]$ mv satya/ satya123 -
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 8
    -rw-rw-r-- 1 ec2-user ec2-user
    93 Nov 29 15:20 file1
    -rw-rw-r-- 1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 16:09 madhu
    -rw-r--r-- 1 ec2-user ec2-user 1312 Nov 29 15:46 passwd
    drwxrwxr-x 2 ec2-user ec2-user
    32 Nov 29 16:03 satya123"
    \[ec2-user@ip-172-31-18-204 \~\]$

[^14]: \[ec2-user@ip-172-31-18-204 \~\]$ cat passwd
    root : x: 0:0: root : /root: /bin/bash
    bin :x:1:1:bin: /bin: /sbin/nologin
    daemon : x : 2: 2 : daemon : /sbin : /sbin/nologin
    adm : x : 3 :4 : adm: /var /adm: /sbin/nologin
    1p :x:4:7 : 1p:/var/spool/1pd: /sbin/nologin
    sync : x: 5:0: sync : /sbin : /bin/sync
    shutdown : x : 6: 0: shutdown : /sbin : /sbin/shutdown
    halt :x:7:0:halt: /sbin: /sbin/halt
    mail : x : 8 :12 : mai1:/var /spool/mai1: /sbin/nologin
    operator : x: 11:0: operator : /root : /sbin/nologin
    games : x: 12 : 100: games : /usr /games : /sbin/nologin
    ftp : x: 14:50: FTP User : /var/ftp: /sbin/nologin
    nobody : x : 99: 99 : Nobody : /: /sbin/nologin
    systemd-network : x: 192 : 192 :systemd Network Management: /: /sbin/nologin
    dbus : x : 81:81: System message bus : /: /sbin/nologin
    rpc : x: 32: 32: Rpcbind Daemon : /var /lib/rpcbind: /sbin/nologin
    libstoragemgmt : x : 999: 997 : daemon account for libstoragemgmt: /var/run/1sm: /sbin/nologin
    sshd: x: 74:74:Privilege-separated SSH: /var/empty/sshd: /sbin/nologin
    rngd : x: 998: 996: Random Number Generator Daemon: /var /lib/rngd: /sbin/nologin
    chrony : x: 997: 995 : : /var /1ib/chrony: /sbin/nologin
    rpcuser : x: 29:29:RPC Service User: /var/lib/nfs : /sbin/nologin
    nfsnobody : x : 65534 : 65534 : Anonymous NFS User : /var/lib/nfs : /sbin/nologin
    ec2-instance-connect : x : 996: 994: : /home/ec2-instance-connect: /sbin/nologin
    postfix : x: 89: 89: : /var /spool/postfix: /sbin/nologin
    tcpdump : x : 72:72: : /: /sbin/nologin
    ec2-user : x : 1000:1000: EC2 Default User : /home/ec2-user: /bin/bash
    \[ec2-user@ip-172-31-18-204 \~\]$
    \[ec2-user@ip-172-31-18-204 \~\]$ grep games passwd
    games : x : 12 : 100: games : /usr /games : /sbin/nologin
    \[ec2-user@ip-172-31-18-204 \~\]$
    \[ec2-user@ip-172-31-18-204 \~1$

[^15]: ec2-user : x: 1000:1000:EC2 Default User : /home/ec2-user : /bin/bash
    devops
    DEVOPS
    \[ec2-user@ip-172-31-18-204 \~\]$
    \[ec2-user@ip-172-31-18-204 \~\]$ grep devops passwd
    -
    devops
    \[ec2-user@ip-172-31-18-204 \~\]$ grep -i devops passwd
    devops
    DEVOPS
    \[ec2-user@ip-172-31-18-204 \~\]$

[^16]: \[ec2-user@ip-172-31-18-204 \~\]$ cat passwd \| grep -i devops
    devops
    DEVOPS
    \[ec2-user@ip-172-31-18-204 \~\]$

[^17]: \[ec2-user@ip-172-31-18-204 \~\]$ wget https: //github. com/git-for-windows/git/releases /download/v2 . 43 .0. windows . 1/Git-2 . 43.0-64-bit. exe
    --2023-11-29 16:33:10-- https://github. com/git-for-windows/git/releases/download/v2 . 43 .0. windows . 1/Git-2 . 43.0-64-bit. exe
    Resolving github. com (github. com) . . . 140.82 .112.3
    Connecting to github. com (github . com) \| 140 . 82 . 112 . 3 \| :443. . . connected.
    HTTP request sent, awaiting response. . . 302 Found
    Location: https://objects . githubusercontent . com/github-production-release-asset-2e65be/23216272/a93c7233-5099-4ce1-8597-efb65113b310?X-A
    mz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH5 3A%2F20231129%2Fus-east-1%2Fs 3%2 Faws 4_request&X-Amz-Date=20231129716321
    8Z&X-Amz-Expires=300&X-Amz-Signature=b55204121116fe7cfe2d94aaf5675aaGae2c281302d1635cfa6cfe65d1a50b34&X-Amz-SignedHeaders=host&actor_id=
    0&key_id=0&repo_id=23216272&response-content-disposition=attachment%38%20filename%3DGit-2 . 43. 0-64-bit . exe&response-content-type=applicat
    ion%2Foctet-stream \[following\]
    -2023-11-29 16:33:11-- https://objects . githubusercontent . com/github-production-release-asset-2e65be/23216272/a93c7233-5099-4ce1-8597-
    fb65113b310?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH5 3A%2F20231129%2Fus-east-1%2Fs 3%2 Faws4_request&X-Amz-Date
    =20231129T163218Z&X-Amz-Expires=300&X-Amz-Signature=b55204121116fe7cfe2d94aaf5675aabae2c281302d1635cfa6cfe65d1a50b34&X-Amz-SignedHeaders
    =host&actor_id=0&key_id=0&repo_id=23216272&response-content-disposition=attachment%38%20filename%3DGit-2 . 43. 0-64-bit . exe&response-conte
    t-type=application%2Foctet-stream
    Resolving objects . githubusercontent . com (objects . githubusercontent . com) . . . 185 . 199.108.133, 185 . 199. 109.133, 185 . 199.110.133,
    Connecting to objects . githubusercontent. com (objects . githubusercontent . com) \| 185 . 199 . 108. 133 \| :443... connected.
    HTTP request sent, awaiting response. . . 200 OK
    Length: 60868040 (58M) \[application/octet-stream\]
    Saving to: 'Git-2. 43.0-64-bit. exe'
    100% \[=
    \] 60, 868 , 040
    137MB /S
    in 0. 4s
    2023-11-29 16:33:11 (137 MB/s) - 'Git-2. 43.0-64-bit. exe' saved \[60868040/60868040\]
    \[ec2-user@ip-172-31-18-204 \~\]$ 1s -1
    total 59452
    -rw-rw-r--
    1 ec2-user ec2-user
    93 Nov 29 15:20 file123
    -rw-rw-r--
    1 ec2-user ec2-user
    0 Nov 29 15:28 file2
    -rw-rw-r--
    1 ec2-user ec2-user 60868040 Nov 20 19:00 Git-2. 43.0-64-bit. exe
    drwxrwxr-x 2 ec2-user ec2-user
    6 Nov 29 16:09 madhu
    -rw-r--r-- 1
    ec2-user ec2-user
    1326 Nov 29 16:21 passwd
    drwxrwxr-x 2 ec2-user ec2-user
    32 Nov 29 16:03 satya123

[^18]: notes / session-02.txt \[
    . .
    am joindevopscloud vim
    921aee3 . yesterday History
    Code
    Blame
    167 lines (126 loc) . 2.92 KB
    Raw .
    Recap
    N P
    w
    Client Server
    4
    EC2 instance launch
    5
    key pair generate
    ssh-keygen -f <file-name>
    public key imported to AWS
    00
    security group created in AWS, allow-all
    command-name <options> <inputs>

[^19]: F
    G
    https://raw.githubusercontent.com/daws-76s/notes/master/session-02.txt
    Recap
    Client Server
    EC2 instance launch
    key pair generate
    ssh-keygen -f <file-name>
    public key imported to AWS
    security group created in AWS, allow-all
    command-name <options> <inputs>
    $ - -> normal user
    \* --> root user
    command-name --help or man command-name
    1s --> list subdirectories

[^20]: \[ec2-user@ip-172-31-18-204 \~\]$ curl https ://raw. githubusercontent . com/daws-76s/notes/master/session-02. txt
    Recap
    Client Server
    EC2 instance launch
    key pair generate
    ssh-keygen -f <file-name>
    public key imported to AWS
    security group created in AWS, allow-all
    command-name <options> <inputs>
    $ --> normal user
    # --> root user
    command-name --help or man command-name
    1s --> list subdirectories
    /home/ec2-user
    cd --> change directory
    / --> root directory
    Is
    1s -1 -->lengthy format in alphabetic order
    drwxr-xr-x 15 root root 2900 Nov 28 01:53 dev
    d --> directory
    --> file
    cd . . -=> one step back
    1s -1r
    --> reverse alphabetic order

[^21]: user Cip
    \[ec2-user@ip-172-31-39-232 /\]$ echo https: //github. com/daws-76s/notes/blob/master/session-01. txt
    https://github . com/daws-76s/notes/blob/master/session-01. txt
    \[ec2-user@ip-172-31-39-232 /\]$
    \[ec2-user@ip-172-31-39-232 /\]$ echo hello Devops world
    hello Devops world
    \[ec2-user@ip-172-31-39-232 /\]$

[^22]: \[ec2-user@ip-172-31-39-232 /\]$ echo https : //github. com/daws-76s/notes/blob/master/session-01. txt \| cut -d / -f1
    https :
    \[ec2-user@ip-172-31-39-232 /\]$ echo https: //github . com/daws-76s/notes/blob/master/session-01. txt \| cut -d / -f3
    github . com
    \[ec2-user@ip-172-31-39-232 /\]$ echo https : //github. com/daws-76s/notes /blob/master/session-01. txt \| cut -d / -f6
    blob

[^23]: \[ec2-user@ip-172-31-39-232 /\]$ echo https ://github . com/daws-76s/notes/blob/master/session-01. txt \| cut -d : -f 2
    /github . com/daws-76s/notes/blob/master/session-01. txt
    \[ec2-user@ip-172-31-39-232 /\]$

[^24]: \[ec2-user@ip-172-31-39-232 /\]$ echo https://github . com/daws-76s/notes/blob/master/session-01. txt \| awk -F / '{print $1F}'
    https :
    \[ec2-user@ip-172-31-39-232 /\]$ echo https : //github . com/daws-76s/notes/blob/master/session-01. txt \| awk -F / ' {print $3F}'
    github . com
    \[ec2-user@ip-172-31-39-232 /\]$ echo https://github . com/daws-76s/notes/blob/master/session-01. txt \| awk -F / ' {print $6F}'
    blob
    \[ec2-user@ip-172-31-39-232 /\]$ echo https : //github. com/daws-76s/notes/blob/master/session-01. txt \| awk -F / ' {print $NF}'
    session-01 . txt
    \[ec2-user@ip-172-31-39-232 /\]$

[^25]: \[ec2-user@ip-172-31-39-232 \~\]$ cat passwd1
    root : x: 0:0:root: /root: /bin/bash
    bin :x:1:1:bin: /bin: /sbin/nologin
    daemon : x : 2 : 2 : daemon : /sbin : /sbin/nologin
    adm : x : 3: 4 : adm: /var /adm: /sbin/nologin
    1p :x: 4:7: 1p: /var/spoo1/1pd: /sbin/nologin
    sync : x : 5 :0:sync : /sbin : /bin/sync
    shutdown : x : 6:0: shutdown : /sbin : /sbin/shutdown
    halt:x:7:0:halt: /sbin: /sbin/halt
    mail : x : 8:12 : mai1: /var /spool/mai1: /sbin/nologin
    operator : x : 11:0: operator : /root: /sbin/nologin
    games : x : 12 : 100 : games : /usr /games : /sbin/nologin
    ftp : x: 14:50: FTP User: /var/ftp: /sbin/nologin

[^26]: \[ec2-user@ip-172-31-39-232 \~\]$ cat passwd1 \| awk -F :
    '{print $1F}
    root
    bin
    daemon
    adm
    1p
    sync
    shutdown
    halt
    mail
    operator
    games
    ftp
    nobody
    systemd-network
    dbus
    rpc
    1ibstoragemgmt
    sshd
    rngd
    chrony
    rpcuser
    nfsnobody
    ec2-instance-connect
    postfix
    tcpdump
    ec2-user
    \[ec2-user@ip-172-31-39-232 \~\]$

[^27]: \[ec2-user@ip-172-31-39-232 \~\]$ cat passwd1 \| awk -F : '{print $NF}'
    /bin/bash
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /bin/sync
    sbin/shutdown
    /sbin/halt
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /sbin/nologin
    /bin/bash
    \[ec2-user@ip-172-31-39-232 \~\]$

[^28]: Lecz-userdip-1/ 2-51
    -252
    \[ec2-user@ip-172-31-39-232 \~\]$ head -n 2 passwd1
    root : x : 0:0: root : /root : /bin/bash
    bin :x:1:1:bin: /bin: /sbin/nologin
    \[ec2-user@ip-172-31-39-232 \~\]$ head -n 3 passwd1
    root : x: 0:0: root: /root: /bin/bash
    bin : x:1:1:bin:/bin: /sbin/nologin
    daemon : x : 2 : 2 : daemon : /sbin : /sbin/nologin
    \[ec2-user@ip-172-31-39-232 \~\]$ tail -n 3 passwd1
    postfix : x : 89: 89: : /var /spool/postfix: /sbin/nologin
    tcpdump : x : 72:72: : /: /sbin/nologin
    ec2-user : x : 1000: 1000:EC2 Default User: /home/ec2-user: /bin/bash
    \[ec2-user@ip-172-31-39-232 \~\]$

[^29]: ESC
    Mode
    -.
    Esc
    Colon/Command
    Mode
    insert mode
    Esc
    shift+g --> goto bottom
    :q --> quit the file
    gg --> takes to top
    u --> undo
    :wq --> write and quit
    yy --> copy
    :q! --> dont save,just quit
    p --> paste
    :set nu
    10p --> 10 times paste
    :set nonu
    dd --> cut
    :noh --> clears last search highlight
    :%s/word/replace/g

[^30]: root: x: 0:0: root : / root: /bin/bash
    Hello, I am learning vim editor
    bin :x : 1:1: bin: /bin: /sbin/nologin
    daemon : x : 2 : 2 : daemon : /sbin: /sbin/nologin
    adm : x : 3:4 : adm: /var/adm:/sbin/nologin
    1p:x: 4:7:1p:/var/ spool/lod: /sbin/nologin
    sync : x : 5: 0 : sync: /sbin-1: /bin/sync
    shutdown : x : 6:0: shutdown: / sbin: /sbin/shutdown
    halt:x: 7:0: halt:/spin: /sbin/halt
    mail : x : 8: 12 : mail:/var/spool/mail: /sbin/nologin
    operator : x: 11:0: operator: /root: /sbin/nologin
    games : x: 12 : 100: games : /usr/games : /sbin/nologin
    ftp: x: 14: 50: FTP User : /var/ftp: /sbin/nologin
    nobody : x : 99: 99 : Nobody : / : /sbin/nologin
    systemd-network : x : 192 : 192 : systemd Network Management: /: /sbin/nologin
    dbus : x : 81: 81: System message bus : /: /sbin/nologin
    rpc:x : 32: 32 : Rpcbind Daemon: /var/lib/rpcbind: /sbin/nologin
    libstoragemgmt : x : 999: 997: daemon account for libstoragemgmt: /var/run/Ism: /sbin/nologin
    sshd : x : 74: 74 : Privilege-separated SSH: /var/empty/sshd: /sbin/nologin
    rngd : x : 998: 996: Random Number Generator Daemon: /var/lib/rngd: /sbin/nologin
    chrony : x: 997: 995 : : /var/lib/chrony : /sbin/nologin
    rpcuser : x : 29:29:RPC Service User: /var/lib/nfs : /sbin/nologin
    nfsnobody : x : 65534 : 65534 : Anonymous NFS User: /var/lib/nfs: /sbin/nologin
    ec2-instance-connect : x : 996: 994: : /home/ec2-instance-connect: /spin/nologin
    postfix : x : 89: 89: : /var/spool/postfix: /sbin/nologin
    tcpdump : x : 72 : 72 : : /: /sbin/nologin
    ec2-user : x: 1000 : 1000: EC2 Default User: /home/ec2-user: /bin/bash
    Devops
    DEVOPS
    : s/bin/bin-1

[^31]: ROOT : X : 0:0: ROOT: /ROOT : )bin/bash
    He ITo, I am Tearning vim editor
    bin : x: 1:1:bin: /bin:/sbin/nologin
    daemon : x : 2 : 2 : daemon : /sbin: /sbin/nologin
    adm : x : 3: 4 : adm : /var/adm: /sbin/nologin
    1p:x:4:7:1p:/var/spool/1pd: /sbin/nologin
    sync : x : 5:0: sync: /sbin-1:/bin/sync
    shutdown : x : 6:0: shutdown: /sbin: /sbin/shutdown
    halt: x: 7:0:halt: /sbin: /sbin/halt
    mail : x : 8:12 : mail:/var/spool/mail: /sbin/nologin
    operator : x: 11:0: operator: /root: /sbin/nologin
    games : x : 12 : 100: games : /usr/games : /sbin/nologin
    ftp: x: 14:50: FTP User: /var/ftp: /sbin/nologin
    nobody : x : 99: 99 : Nobody : /: /sbin/nologin
    systemd-network : x : 192 : 192: systemd Network Management: /: /sbin/nologin
    dbus : x : 81: 81: System message bus: /: /sbin/nologin
    rpc: x: 32: 32 : Rpcbind Daemon : /var/lib/rpcbind: /sbin/nologin
    libstoragemgmt : x : 999: 997: daemon account for libstoragemgmt: /var/run/Ism: /sbin/nologin
    sshd : x : 74: 74: Privilege-separated SSH: /var/empty/sshd: /sbin/nologin
    rngd : x : 998: 996: Random Number Generator Daemon: /var/lib/rngd: /sbin/nologin
    chrony : x : 997: 995: : /var/lib/chrony : /sbin/nologin
    rpcuser : x: 29:29:RPC Service User: /var/lib/nfs: /sbin/nologin
    fsnobody : x : 65534 : 65534 : Anonymous NFS User: /var/lib/nfs: /sbin/nologin
    ec2-instance-connect : x : 996: 994: : /home/ec2-instance-connect: /sbin/nologin
    postfix : x : 89: 89: : /var/spool/postfix: /sbin/nologin
    tcpdump : x : 72: 72: : /:/sbin/nologin
    ec2-user : x : 1000 : 1000: EC2 Default User: /home/ec2-user: /bin/bash
    Devops
    DEVOPS
    : s/root/ROOT/a

[^32]: ROOT : X : 0: 0: ROOT: /ROOT : /bin/bash
    Hi, I am learning vim editor
    bin X :1:1: bin: /bin: /sbin/nologin
    daemon : x : 2: 2 : daemon : /sbin: /sbin/nologin
    adm : x : 3:4: adm: /var/adm: /sbin/nologin
    1p: x: 4:7: 1p: /var/spool/1pd: /sbin/nologin
    sync : x : 5:0: sync: /sbin-1: /bin/sync
    shutdown : x : 6:0: shutdown : /sbin: /sbin/shutdown
    halt:x: 7:0:halt: /sbin: /sbin/halt
    mail : x : 8:12 : mail: /var/spool/mail: /sbin/nologin
    operator : x : 11:0:operator: /root: /sbin/nologin
    games : x : 12 : 100 : games : /usr/ games : /sbin/nologin
    ftp: x: 14: 50: FTP User : /var/ftp: /sbin/nologin
    nobody : x : 99: 99 : Nobody : / : /sbin/nologin
    systemd-network : x : 192 : 192 : systemd Network Management: /: /sbin/nologin
    dbus : x : 81: 81: System message bus : /: /sbin/nologin
    rpc: x: 32:32: Rpcbind Daemon : /var/lib/rpcbind: /sbin/nologin
    1ibstoragemgmt : x : 999: 997: daemon account for libstoragemgmt: /var/run/Ism: /sbin/nologin
    sshd : x : 74: 74: Privilege-separated SSH: /var/empty/sshd: /sbin/nologin
    rngd : x : 998: 996: Random Number Generator Daemon: /var/lib/rngd: /sbin/nologin
    chrony : x : 997: 995: : /var/lib/chrony : /sbin/nologin
    rpcuser: x: 29:29:RPC Service User: /var/lib/nfs: /sbin/nologin
    nfsnobody : x : 65534 : 65534 : Anonymous NFS User: /var/lib/nfs: /sbin/nologin
    ec2-instance-connect : x : 996: 994: : /home/ec2-instance-connect: /sbin/nologin
    postfix : x : 89: 89: : /var/spool/postfix: /sbin/nologin
    tcpdump : x : 72 : 72: : /:/sbin/nologin
    ec2-user : x : 1000 : 1000: EC2 Default User: /home/ec2-user: /bin/bash
    Devops
    DEVOPS
    :2s/He110/Hi/q

[^33]: ROOT : X : 0:0 : ROOT : /ROOT : /bin/bash
    Hi, I am learning vim editor
    bin : x:1:1:bin: /bin: /sbin/nologin
    daemon : x : 2 : 2 : daemon: /sbin: /sbin/nologin
    adm : x : 3: 4 : adm: /var/adm: /sbin/nologin
    1p: x: 4:7: 1p:/var/spool/1pd: /sbin/nologin
    sync : x : 5:0: sync:/sbin-1: /bin/sync
    shutdown : x : 6:0: shutdown : /sbin: /sbin/shutdown
    halt: x:7:0:halt: /sbin: /sbin/halt
    mail : x : 8:12 : mail: /var/spool/mail: /sbin/nologin
    operator : x: 11:0: operator : /root: /sbin/nologin
    games : x : 12 : 100: games : /usr/games : / sbin/nologin
    ftp : x: 14: 50: FTP User : /var/ftp: /sbin/nologin
    nobody : x : 99: 99 : Nobody : /: /sbin/nologin
    systemd-network : x : 192 : 192 : systemd Network Management: /: /sbin/nologin
    dbus : x : 81:81: System message bus : /: /sbin/nologin
    rpc: x: 32: 32: Rpcbind Daemon : /var/lib/rpcbind: /sbin/nologin
    libstoragemgmt : x : 999: 997: daemon account for libstoragemgmt: /var/run/Ism: /sbin/no
    sshd : x : 74: 74: Privilege-separated SSH: /var/empty/sshd: /sbin/nologin
    rngd : x : 998: 996: Random Number Generator Daemon: /var/lib/rngd: /sbin/nologin
    chrony : x : 997: 995 : : /var/lib/chrony : /sbin/nologin
    rpcuser: x : 29:29:RPC Service User: /var/lib/nfs: /sbin/nologin
    nfsnobody : x : 65534 : 65534 : Anonymous NFS User: /var/lib/nfs: /sbin/nologin
    ec2-instance-connect : x : 996: 994: : /home/ec2-instance-connect: /sbin/nologin
    postfix : x: 89: 89: : /var/spool/postfix: /sbin/nologin
    tcpdump : x : 72 : 72 : : /: /sbin/nologin
    ec2-user : x : 1000: 1000: EC2 Default User: /home/ec2-user: /bin/bash
    Devops
    DEVOPS
    %s /sbin/SBIN/q

