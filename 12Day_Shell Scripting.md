---
title: 12Day_Shell Scripting
uuid: 2451ac9e-0f53-11ef-af7b-a6f126245c9e
version: 126
created: '2024-05-11T10:28:43+05:30'
tags:
  - shellscripting
  - shell
---

***Topics:***

1. *<mark style="background-color:#f8d616;">Git clone & git existing folder<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Shell Scripting<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Variables<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Arguments<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Datatypes<!-- {"backgroundCycleColor":"25"} --></mark>*

1. *<mark style="background-color:#f8d616;">Arrays<!-- {"backgroundCycleColor":"25"} --></mark>*

\

# *<mark style="background-color:#f8914d;">**GIT clone:**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

 

![a12b48b0-41c2-42f3-a95f-db3d5d419b20.png|545](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/a12b48b0-41c2-42f3-a95f-db3d5d419b20.png) [^1]

 

![b89d4874-4b4c-49ef-8cf0-01461e9242f5.png|557](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/b89d4874-4b4c-49ef-8cf0-01461e9242f5.png) [^2]

 

***You Can run all commands in single command (adding to staging area, committing & pushing)***

```
git add . ; git commit -m "I am practicing GIT" ; git push origin master
```

 

![d4d58020-f706-40ad-847a-a122e033cea9.png|813](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/d4d58020-f706-40ad-847a-a122e033cea9.png) [^3]

 

 

***Your GIT REPO is not created but coding team started developing a code. Now in this we follow below process***

 

![53b0e4e0-7877-4697-889f-4a94451f89bb.png|823](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/53b0e4e0-7877-4697-889f-4a94451f89bb.png) [^4]

 

![b7ec809f-7cb0-4331-b2ea-95757359c5b4.png|972](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/b7ec809f-7cb0-4331-b2ea-95757359c5b4.png) [^5]

 

![d6c79388-fb83-470a-8a2c-713e3901017f.png|855](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/d6c79388-fb83-470a-8a2c-713e3901017f.png) [^6]

 

![ba283a04-2430-4a06-b297-8d164f2493db.png|921.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/ba283a04-2430-4a06-b297-8d164f2493db.png) [^7]

 

![b24cf81a-b570-404f-a64d-47100df26878.png|918](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/b24cf81a-b570-404f-a64d-47100df26878.png) [^8]

 

*Once repo created, then only we can push it to central repository*

![dfb482a9-637c-420c-a8df-2ab760b8c8a1.png|872.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/dfb482a9-637c-420c-a8df-2ab760b8c8a1.png) [^9]

 

![aab17ed8-4a01-4adf-9366-460f05484d20.png|869](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/aab17ed8-4a01-4adf-9366-460f05484d20.png) [^10]

 

*Now you get all data in GIT central repo*

 

![1e4e1c3e-2308-484b-9bf9-8c8a715fdc57.png|872.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/1e4e1c3e-2308-484b-9bf9-8c8a715fdc57.png) [^11]

 

 

 

# ***Shell Scripting**:*<!-- {"collapsed":true} -->

*#!/bin/bash --> shebang     -->to check the syntax of our shell script, we need to give the location of bash*

 

*Shell script or bash script both are same.*

 

*Hello world script:*

![9e549fd4-2652-4424-9371-bd3e16347676.png|748](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/9e549fd4-2652-4424-9371-bd3e16347676.png) [^12]

 

```
git branch -M master 
```

```
git add . ; git commit -m "first script"
```

![](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/e722111c-3f99-41f8-9d06-d84afb0059d2.png) [^13]

 

```
git push -u origin master
```

![23cf0c9b-f08d-4c43-b7ce-2819ce1bb9f6.png|763](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/23cf0c9b-f08d-4c43-b7ce-2819ce1bb9f6.png) [^14]

 

 

*Now you are able to see the data in GIT central repository*

![9df4cc8f-d49b-43b4-87b6-e4a4603756a6.png|811.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/9df4cc8f-d49b-43b4-87b6-e4a4603756a6.png) [^15]

 

 

*Now launching a instance to execute shell scripts:*

 

*Now clone the repo shell-script in instance*

 

*# git clone* [*https://github.com/Chowdarychilukuri/shell-scripts.git*](https://github.com/Chowdarychilukuri/shell-scripts.git) 

*Or*

*# git clone* [*https://github.com/chilops/shellscripts.git*](https://github.com/chilops/shellscripts.git) 

```
ls -l
```

```
cd shell-scripts/
```

```
ls -l
```

 

![deb00bdb-4bcc-4bb8-bc1d-22cd8c9238d2.png|842.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/deb00bdb-4bcc-4bb8-bc1d-22cd8c9238d2.png) [^16]

 

*Now will see ways to run shell scripts:*

 

```
sh <script-name>
```

```
sh 01.hello-world.sh
```

 

![a4d3fa3d-a619-4135-98fa-92ea229cabd3.png|829.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/a4d3fa3d-a619-4135-98fa-92ea229cabd3.png) [^17]

 

 

 

 

# *<mark style="background-color:#f8914d;">**Variables: **<!-- {"backgroundCycleColor":"24"} --></mark>we derive formula and finally we submit values…*<!-- {"collapsed":true} -->

 

*change in a single location will affect everywhere automatically*

 

*DRY --> don't repeat yourself*

 

![d9a0e918-8a2d-4f02-8ae8-7dfc648e6e5b.png|561](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/d9a0e918-8a2d-4f02-8ae8-7dfc648e6e5b.png) [^18]

 

*Sample 1 written*

![f40b4f31-262e-40c7-a24d-a914f06e8c2c.png|868](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/f40b4f31-262e-40c7-a24d-a914f06e8c2c.png) [^19]

 

*Commit & push it to git.*

```
 git add . ; git commit -m "adding variable script"; git push origin master
```

![1b7f120a-d28d-453d-8205-6fc707b794a2.png|678](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/1b7f120a-d28d-453d-8205-6fc707b794a2.png) [^20]

 

*Now pull it from instance end:*

```
git pull
```

```
ls -l
```

![a0c8fdca-8f09-4477-967e-283bf9400a39.png|734.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/a0c8fdca-8f09-4477-967e-283bf9400a39.png) [^21]

 

![e8e5b557-462e-4dd2-8536-d9e0587364c4.png|876.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/e8e5b557-462e-4dd2-8536-d9e0587364c4.png) [^22]

 

 

```
sh 02.variables.sh
```

![d60bfd3d-aaa7-44b1-be65-19ec31c87cc0.png|913.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/d60bfd3d-aaa7-44b1-be65-19ec31c87cc0.png) [^23]

 

 

*<mark style="background-color:#f8914d;">**Q. How do you run shell script & take the output?**<!-- {"backgroundCycleColor":"24"} --></mark>*

 *$(<command>)*

 

*VS*

![689b25f9-df52-4cf7-8f96-a659073d6b74.png|691](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/689b25f9-df52-4cf7-8f96-a659073d6b74.png) [^24]

 

***PUSH***

```
git status
```

```
git add . ; git commit -m "date command" ; git push origin main
```

 

![af07dfcb-3816-4c56-ba59-e521b9e9dac4.png|785](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/af07dfcb-3816-4c56-ba59-e521b9e9dac4.png) [^25]

 

![728cb63e-becb-49d5-95aa-23c73c73d3b8.png|749](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/728cb63e-becb-49d5-95aa-23c73c73d3b8.png) [^26]

 

***PULL  to server***

```
git pull
```

```
ls -l
```

```
sh 03.variables.sh
```

![d6f06e99-cf93-4cd1-bda5-9e0f26f5e7cd.png|752.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/d6f06e99-cf93-4cd1-bda5-9e0f26f5e7cd.png) [^27]

 

![da3f05e1-b964-4816-b4e0-b19e2b661dc4.png|920.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/da3f05e1-b964-4816-b4e0-b19e2b661dc4.png) [^28]

 

 

# *<mark style="background-color:#f8914d;">**Arguments: Args**<!-- {"backgroundCycleColor":"24"} --></mark>*<!-- {"collapsed":true} -->

![39f334e8-16cc-4f61-8f17-9e0056ce226a.png|786](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/39f334e8-16cc-4f61-8f17-9e0056ce226a.png) [^29]

 

 

***Push & pull***

```
git add . ; git commit -m "date command" ; git push origin main
```

```
git pull
```

 

![0db7c9d2-1fe2-40dd-ba3c-a8af3152e958.png|795.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/0db7c9d2-1fe2-40dd-ba3c-a8af3152e958.png) [^30]

 

 

*Ex: to read user name & password*

![6d9bb3ff-6cce-45e6-8083-f444d08a7c1a.png|857.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/6d9bb3ff-6cce-45e6-8083-f444d08a7c1a.png) [^31]

 

***Push & pull***

```
git add . ; git commit -m "password command" ; git push origin main
```

```
git pull
```

![dccfa101-4524-4f53-ae0e-4bf84aac3aee.png|784.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/dccfa101-4524-4f53-ae0e-4bf84aac3aee.png) [^32]

 

 

# ***Data Types:***  <!-- {"collapsed":true} -->

*int, float, string, double, long, char, boolean, array, arraylist, map, set*

 

*int --> -33,334 to 33,334*

*float --> 1.2, 1.4*

*string --> ramesh*

*double --> 33.43435*

*long --> 423742193451405*

*char --> a, b, c*

*boolean --> true/false*

*array --> (ram robert raheem)*

*arraylist --> (ram robert raheem)*

*map --> name: sivakumar, tech: devops*

 

*shell don't care much about data types*

 

*Ex: sum of 2 numbers:*

 

![4fccf008-ca03-492d-a0c8-fc2b114e5e75.png|787](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/4fccf008-ca03-492d-a0c8-fc2b114e5e75.png) [^33]

 

***Push & pull***

```
git add . ; git commit -m "password command" ; git push origin main
```

```
git pull
```

 

![7196296f-21a1-404f-acf6-7499c394dfdc.png|749.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/7196296f-21a1-404f-acf6-7499c394dfdc.png) [^34]

 

 

# ***Arrays: we can add multiple items in a single variables (ex… money,cards,coins adding into wallet)***<!-- {"collapsed":true} -->

 

***Ex: taking 3 kinds of fruits***

![51124a3e-9a3d-4a0f-8571-70da89574103.png|649](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/51124a3e-9a3d-4a0f-8571-70da89574103.png) [^35]

 

***Push & pull***

```
git add . ; git commit -m "password command" ; git push origin main
```

```
git pull
```

![b2c45683-9222-41e6-a1ad-3b62b03f67f7.png|829.3333740234375](https://images.amplenote.com/2451ac9e-0f53-11ef-af7b-a6f126245c9e/b2c45683-9222-41e6-a1ad-3b62b03f67f7.png) [^36]

 

 

[^1]: user@AshDexter-T480 MINGW64 \~
    $ cd /c/devops/daws-76s/repos/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos
    $ git clone git@github . com: daws-76s/test-repo-1. git
    Cloning into 'test-repo-1'. ..
    warning: You appear to have cloned an empty repository

[^2]: clone a repo from git
    clone --> downloading a copy
    git clone <URL>
    add to staging/ temp area
    -.
    - - - - --
    - - - - - -
    git add <file-name>
    git add .
    commit into local repo
    - - - --
    - - - - - - --
    git commit -m "I m practicing git"
    push into central repo
    - - -
    git push origin <branch-name>

[^3]: $ git add . ; git commit -m
    m practicing git" ; git push origin main
    \[main (root-commit) 5f58df1\] I m practicing git
    2 files changed, 3 insertions (+)
    create mode 100644 README . MD
    create mode 100644 example . txt
    Enumeratiog objects: 4, done.
    Counting objects: 100% (4/4), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (4/4), 326 bytes \| 326.00 KiB/s, done.
    Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
    To github . com: daws-76s/test-repo-1.git
    \[new branch\]
    main -> main

[^4]: you have alreay existing folder
    - - - ----------
    - - - -------------
    git init --> intializing a folder as git
    git branch -M main
    git remote add origin git@github. com: daws-76s/test-repo-2.git
    git push -u origin main
    I

[^5]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-1 (main)
    $ cd . ./test-repo-2
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2
    $ git init
    Initialized empty Git repository in C: /devops/daws-76s/repos/test-repo-2/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $
    I

[^6]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ git status
    On branch main
    No commits yet
    Untracked files:
    (use "git add <file>. .." to include in what will be committed)
    README . MD
    nothing added to commit but untracked files present (use "git add" to track)
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ git add . ; git commit -m "we dont have git central repo'
    \[main (root-commit) 12fd81c\] we dont have git central repo
    1 file changed, 2 insertions (+)
    create mode 100644 README . MD

[^7]: XJ
    File Edit Selection View
    Go
    Run
    . ..
    repos
    EXPLORER
    README.MD test-repo-1
    example.txt test-repo-1
    README.MD test-repo-2 1
    example.txt test-repo-2 1, U X
    V REPOS
    test-repo-2 > = example.txt
    .github
    1
    still github is not setup, so working in local only
    > concepts
    > notes
    > roboshop-documentation
    > shell-script
    > some-folder
    > test-repo-1
    test-repo-2
    example.txt
    1, U
    README.MD

[^8]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ git log
    commit 0592f8cbbc9c81192ba70b67e4099c1fa2d8d773 (HEAD -> main)
    Author: joindevopscloud <info@joindevops. com>
    Date:
    Tue Dec 12 07: 41:24 2023 +0530
    still no there, but we cant stop
    commit a9ac24679727f97872867ea82e12bbe08308480d
    Author: joindevopscloud <info@joindevops . com>
    Date :
    Tue Dec 12 07:40:47 2023 +0530
    contiuing
    commit 12fd81ced3e2ca661755e5fd6a4b46f7cca5e48b
    Author: joindevopscloud <info@joindevops . com>
    Date:
    Tue Dec 12 07:39: 51 2023 +0530
    we don't have git central repo
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ 1

[^9]: > C A github.com/organizations/daws-76s/repositories/new
    E
    daws-76s
    Q Type to search
    Overview
    Repositories 7 Discussions Projects Packages & Teams & People 1
    893 Settings
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    - daws-76s
    test-repo-2
    test-repo-2 is available.
    Great repository names are short and memorable. Need inspiration? How about friendly-dollop ?
    Description (optional)
    Public
    O
    Anyone on the internet can see this repository. You choose who can commit.
    Private
    You choose who can see and commit to this repository.
    Initialize this repository with:

[^10]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ git remote add origin git@github. com: daws-76s/test-repo-2.git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ git push -u origin main
    Enumeratiog objects: 9, done.
    Counting objects: 100% (9/9), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (7/7), done.
    Writing objects: 100% (9/9), 813 bytes \| 406.00 KiB/s, done.
    Total 9 (delta 1), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (1/1), done.
    To github. com: daws-76s/test-repo-2. git
    \[new branch\]
    main -> main
    branch 'main' set up to track 'origin/main' .
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/test-repo-2 (main)
    $ 1

[^11]: E
    daws-76s / test-repo-2
    Q Type to search
    > _
    + +
    87
    <> Code
    Issues 13 Pull requests
    Actions Projects Wiki @ Security \~ Insights
    to Settings
    Commits
    & main
    & All users
    All time
    o Commits on Dec 12, 2023
    still no there, but we cant stop
    0592f8c <>
    joindevopscloud committed 1 minute ago
    contiuing
    a9ac246
    D (>
    joindevopscloud committed 2 minutes ago
    we dont have git central repo
    12fd81c
    D <>
    joindevopscloud committed 3 minutes ago

[^12]: File Edit Selection View
    . . .
    9 Repos
    EXPLORER
    example.txt
    $ 01.hello-world.sh M X
    REPOS
    shell-scripts > $ 01.hello-world.sh
    shell-scripts
    1
    #! /bin/bash
    $ 01.hello-world.sh
    M
    2
    3
    > test
    #This is comment
    1
    4
    5
    echo "I am writing shell script"
    6

[^13]: chowd@chowdary MINGW64 /e/awsdevops /keys /Repos /shel1-scripts (master)
    $ git branch -M main
    chowd@Chowdary MINGW64 /e/awsdevops /keys /Repos/shell-scripts (main)
    $ git add . ; git commit -m "first script"
    warning: in the working copy of '01.hello-world.sh' , LF will be replaced by CRLF
    the next time Git touches it
    \[main 67 dac71\] first script
    1 file changed, 5 insertions (+)
    chowd@chowdary MINGW64 /e/awsdevops/keys /Repos /shel1-scripts (main)

[^14]: chowd@Chowdary MINGW64 /e/awsdevops /keys/Repos/shell-scripts (main)
    $ git push -u origin main
    Enumeratiog objects: 5, done.
    Counting objects: 100% (5/5), done.
    Delta compression using up to 12 threads
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 340 bytes \| 340.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    emote:
    emote: Create a pull request for 'main' on GitHub by visiting:
    emote:
    https ://github . com/Chowdarychi lukuri/shel1-scripts/pul1/new/main
    emote:
    To github . com: Chowdarychilukuri/shell-scripts . git
    \[new branch\]
    main -> main
    branch 'main' set up to track 'origin/main'.
    chowd@chowdary MINGW64 /e/awsdevops/keys/Repos /shel1-scripts (main)

[^15]: E
    Chowdarychilukuri / shell-scripts
    Q Type to search
    <> Code
    Issues
    87 Pull requests
    Actions Projects Wiki
    Security \~ Insights
    to Settings
    shell-scripts Public
    &Pin
    O Unwatch 1
    89 main
    & 2 branches 0 tags
    Go to file
    Add file
    <> Code
    This branch is 2 commits behind master.
    87 Contribute
    Chowdarychilukuri modified script
    e5151f0 3 minutes ago 5 commits
    01.hello-world.sh
    first script
    8 minutes ago
    Help people interested in this repository understand your project by adding a README.
    Add a README

[^16]: \[ root@ip-172-31-21-129 \~ \]# git clone https: //github. com/Chowdarychilukuri/shell-scripts.git
    Cloning into 'shell-scripts' .
    remote: Enumeratiog objects: 14, done.
    remote: Counting objects: 100% (14/14) , done.
    remote: Compressing objects: 100% (9/9) , done.
    remote: Total 14 (delta 6) , reused 7 (delta 1) , pack-reused 0
    Receiving objects: 100% (14/14) , done.
    Resolving deltas: 100% (6/6) , done.
    54 . 164 . 143.187 \| 172. 31.21. 129 \| t2.micro \| null
    \[ root@ip-172-31-21-129 \~ \]# ls -1
    total 8
    rw-
    1 root root 6096 Mar 8 2023 original-ks. cfg
    drwxr-xr-x 3 root root
    43 Dec 13 07:00 shell-scripts
    54 . 164. 143.187 \| 172. 31.21.129 \| t2.micro \| null
    \[ root@ip-172-31-21-129 \~ \]# cd shell-scripts/
    54 . 164 . 143.187 \| 172.31.21.129 \| t2.micro \| https: / /github. com/Chowdarychilukuri/shell-scripts . git
    \[ root@ip-172-31-21-129 \~/shell-scripts \]# 1s -1
    total 4
    rw-r--r-- 1 root root 63 Dec 13 07:00 01.hello-world.sh
    54 . 164. 143.187 \| 172. 31.21. 129 \| t2.micro \| https: / /github. com/Chowdarychilukuri/shell-scripts . git
    \[ root@ip-172-31-21-129 \~/shell-scripts \]# \[

[^17]: \[ rootdip-172-31-21-129 \~/shell-scripts \]# sh 01.hello-world.sh
    I am writing shell script
    54 . 164 . 143.187 \| 172. 31.21.129 \| t2.micro \| https: / /github. com/Chowdarychilukuri/shell-scripts. git
    \[ root@ip-172-31-21-129 \~/shell-scripts \]# \|

[^18]: variables
    x=1, y=2, z=3
    a big formula
    we derive formula and finally we submit values. ..
    DRY --> don't repeat yourself
    VARIABLE NAME=VALUE
    PERSON1=Ramesh
    PERSON2=Suresh

[^19]: XI
    File Edit Selection View
    . . .
    9 Repos
    EXPLORER
    example.txt
    $ 01.hello-world.sh
    $ 02.variables.sh U X
    REPOS
    shell-scripts > $ 02.variables.sh
    shell-scripts
    1
    #! /bin/bash
    $ 01.hello-world.sh
    2
    3
    $ 02.variables.sh
    PERSON1=Ram
    U
    4
    PERSON2=Satya
    > test
    5
    echo "$PERSON1: Hello $PERSON2, Good Morning"
    6
    echo "$PERSON2: Hello $PERSON1, Very Good Morning"
    7
    echo "$PERSON1: How are you $PERSON2"
    8
    echo "$PERSON2: I am doing good $PERSON1, How are you"

[^20]: $ git add . ; git commit -m "adding variable script"; git push origin master
    error: 'shell-scripts /' does not have a commit checked out
    fatal: adding files failed
    On branch master
    Your branch is up to date with 'origin/main'.
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
    shell-scripts/
    nothing added to commit but untracked files present (use "git add" to track)
    Enumeratiog objects: 15, done.
    Counting objects: 100% (15/15), done.
    Delta compression using up to 12 threads
    Compressing objects: 100% (11/11), done.
    Writing objects: 100% (15/15), 1.41 KiB \| 1.41 MiB/s, done.
    Total 15 (delta 4), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (4/4), done.
    To github . com: Chowdarychilukuri/shel1-scripts. git
    \[new branch\]
    master -> master
    chowd@chowdary MINGW64 /e/awsdevops /keys/Repos/shel1-scripts (master)

[^21]: \[ root@ip-172-31-21-129 \~/shell-scripts \]# git pull
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4), done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 3 (delta 0) , reused 3 (delta 0) , pack-reused 0
    Unpacking objects: 100% (3/3) , 420 bytes \| 420.00 KiB/s, done.
    From https: //github. com/Chowdarychilukuri/shell-scripts
    e5151f0 . . 3bd6d4a main
    -> origin/main
    Already up to date.
    54 . 164. 143.187 \| 172. 31. 21. 129 \| t2.micro \| https: / /github. com/Chowdarychilukuri/shell-scripts . git
    \[ root@ip-172-31-21-129 \~/shell-scripts \]# \[

[^22]: 54 . 164. 143. 187 \| 172. 31.21. 129 \| t2.micro \| https: / /github. com/Chowdarychilukuri/shell-scripts.git
    \[ root@ip-172-31-21-129 \~/shell-scripts \]# ls -1
    total 8
    -rw-r-
    r--
    1 root root 63 Dec 13 07:40 01.hello-world. sh
    rw-r--r-
    1 root root 228 Dec 13 07:40 02. variables. sh

[^23]: 54. 164 . 143.187 \| 172. 31. 21.129 \| t2.micro \| https: / /github. com/Chowdarychilukuri/shell-scripts.git
    \[ root@ip-172-31-21-129 \~/shell-scripts \]# sh 02 . variables. sh
    Ram: Hello Satya, Good Morning
    Satya: Hello Ram, Very Good Morning
    Ram: How are you Satya
    Satya: I am doing good Ram, How are you

[^24]: XI
    File Edit Selection View
    . .
    Repos
    EXPLORER
    . . .
    orld.sh
    $ 02.variables.sh shell-scripts
    $ 02.variables.sh shellscri
    REPOS
    shellscripts > $ 03.variables.sh
    shellscripts
    1
    #! /bin/bash
    $ 01.hello-world.sh
    2
    3
    $ 02.variables.sh
    DATE=$ (date)
    8 1
    14
    $ 03.variables.sh
    U
    5
    echo "date and time is: $DATE"
    > test

[^25]: chowd@chowdary MINGW64 /e/awsdevops /keys /Repos /shellscripts (main)
    $ git status
    On branch main
    Your branch is up to date with 'origin/main' .
    Untracked files :
    (use "git add <file>. .." to include in what will be committed)
    03 . variables . sh
    nothing added to commit but untracked files present (use "git add" to track)
    chowd@chowdary MINGW64 /e/awsdevops /keys /Repos /shellscripts (main)
    $ git add . ; git commit -m "date command" ; git push origin main
    warning: in the working copy of '03. variables.sh', LF will be replaced by CRLF the next time Git touches it
    \[main c6bf531\] date command
    1 file changed, 5 insertions (+)
    create mode 100644 03 . variables. sh
    Enumeratiog objects: 4, done.
    Counting objects: 100% (4/4), done.
    Delta compression using up to 12 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 392 bytes \| 392.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    To github . com: Chowdarychilukuri/shellscripts . git
    Of21d28. . c6bf531 main -> main

[^26]: F
    G
    https://github.com/Chowdarychilukuri/shellscripts/blob/main/03.variables.sh
    E
    Chowdarychilukuri / shellscripts
    <> Code
    Issues 7 Pull requests
    Actions
    Projects Wiki
    Security \~ Insights
    503
    S
    Files
    shellscripts / 03.variables.shi
    & main
    +
    Q
    Chowdarychilukuri date command
    Q Go to file
    t
    Code
    Blame 5 lines (3 loc) . 57 Bytes
    01.hello-world.sh
    02.variables.sh
    #! /bin/bash
    2
    03.variables.sh
    3
    DATE=$ (date)
    4
    5
    echo "date and time is: $DATE"

[^27]: \[ root@ip-172-31-81-130 \~/shellscripts \]# git pull
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4) , done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 3 (delta 0) , reused 3 (delta 0) , pack-reused 0
    Unpacking objects: 100% (3/3) , 372 bytes \| 372.00 KiB/s, done.
    From https: //github. com/Chowdarychilukuri/shellscripts
    Of21d28. . c6bf531 main
    -> origin/main
    Updating Of21d28. . c6bf531
    Fast-forward
    03 . variables . sh \| 5 +++++
    1 file changed, 5 insertions (+)
    create mode 100644 03. variables.sh
    44 . 201 . 174.97 \| 172. 31.81.130 \| t2.micro \| https: //github. com/Chowdarych
    \[ rootdip-172-31-81-130 \~/shellscripts \]# ls -1
    total 12
    -rw-r--r-- 1 root root 63 Dec 13 15:11 01. hello-world.sh
    -rw-r--r-- 1 root root 228 Dec 13 15:13 02.variables.sh
    -rw-r--r-- 1 root root 57 Dec 13 15:50 03.variables.sh

[^28]: \[ root@ip-172-31-81-130 \~/shellscripts \]# sh 03. variables. sh
    date and time is: Wed Dec 13 15:51:18 UTC 2023

[^29]: File Edit Selection View
    . . .
    9 Repos
    EXPLORER
    . . .
    iables.sh shell-scripts
    $ 02.variables.sh shellscripts
    $ 03.variables.sh
    $ 04.var
    REPOS
    shellscripts > $ 04.variablesArgs.sh
    shellscripts
    #! /bin/bash
    NH
    $ 01.hello-world.sh
    3
    PERSON1=$1
    $ 02.variables.sh
    4
    PERSON2=$2
    $ 03.variables.sh
    5
    $ 04.variablesArgs.sh
    6
    echo "$PERSON1: Hello $PERSON2, Good Morning"
    > test
    7
    echo "$PERSON2: Hello $PERSON1, Very Good Morning"
    8
    echo "$PERSON1: How are you $PERSON2"
    9
    echo "$PERSON2: I am doing good $PERSON1, How are you"

[^30]: \[ root@ip-172-31-81-130 \~/shellscripts \]# sh 04. variablesArgs . sh ram satya
    ram: Hello satya, Good Morning
    satya: Hello ram, Very Good Morning
    ram: How are you satya
    satya: I am doing good ram, How are you
    44 . 201 . 174.97 \| 172. 31. 81.130 \| t2.micro \| https: //github. com/Chowdarychilukuri/shellscripts . git
    \[ root@ip-172-31-81-130 \~/shellscripts \]# \[\]

[^31]: EXPLORER
    01.hello-world.sh
    02.variables.sh shell-scripts
    02.variables.sh shellscripts
    03.variables.sh
    04. variablesArgs.sh
    05.variables.sh
    REPOS
    shellscripts > $ 05.variables.sh
    shellscripts
    1
    #! /bin/bash
    $ 01.hello-world.sh
    W
    $ 02.variables.sh
    echo "Please enter your Username:
    4
    $ 03.variables.sh
    read USERNAME #the value entered above will be automatically attached to USERNAME variable
    5
    $ 04.variablesArgs.sh
    6
    echo "Please enter your Password: "
    $ 05.variables.sh
    read -s PASSWORD
    > test
    8
    echo "username is: $USERNAME, Password is: $PASSWORD"
    #I am priniting just for validations, you should not print it in real time

[^32]: \[ rootip-172-31-81-130 \~/shellscripts \]# sh 05. variables.sh
    Please enter your Username:
    satya
    Please enter your Password:
    username is: satya, Password is: admin123
    44 . 201 . 174.97 \| 172. 31. 81.130 \| t2.micro \| https: / /github. com/Chowdarych
    \[ root@ip-172-31-81-130 \~/shellscripts \]# \| \|

[^33]: XJ
    File Edit Selection View
    . .
    9 Repos
    EXPLORER
    $ 03.variables.sh
    $ 04.variablesArgs.sh
    $ 05.variables.sh
    $ 06.dat
    REPOS
    shellscripts > $ 06.datatypes.sh
    shellscripts
    H
    #! /bin/bash
    $ 01.hello-world.sh
    N
    3
    NUMBER1=$1
    $ 02.variables.sh
    8 1
    4
    NUMBER2=$2
    $ 03.variables.sh
    5
    $ 04.variablesArgs.sh
    6
    SUM=$ ( ($NUMBER1+$NUMBER2) )
    $ 05.variables.sh
    $ 06.datatypes.sh
    U
    8
    echo "Total is $SUM"
    > test

[^34]: \[ root@ip-172-31-81-130 \~/shellscripts \]# sh 06. datatypes. sh 30 70
    Total is 100

[^35]: File Edit Selection View
    9 Repos
    EXPLORER
    . . .
    ables.sh
    $ 04.variablesArgs.sh
    $ 05.variables.sh
    $ 06.dataty
    REPOS
    shellscripts > $ 07.arrays.sh
    shellscripts
    H
    #! /bin/bash
    $ 01.hello-world.sh
    2
    3
    FRUITS=("Apple" "Banana" "Mango")
    $ 02.variables.sh
    4
    $ 03.variables.sh
    5
    echo "First value: ${FRUITS\[0\]\]"
    $ 04.variablesArgs.sh
    16
    $ 05.variables.sh
    7
    echo "Second value: ${FRUITS\[1\]\]"
    $ 06.datatypes.sh
    8
    $ 07.arrays.sh
    9
    echo "Second value: ${FRUITS \[2\]}"
    10
    > test
    11
    echo "All Fruits: ${FRUITS\[@\]}"

[^36]: \[ root@ip-172-31-81-130 \~/shellscripts \]# sh 07.arrays.sh
    First value: Apple
    Second value: Banana
    Second value: Mango
    All Fruits: Apple Banana Mango

