---
title: 45to47Day_Jenkins
uuid: aa8ac7e4-3502-11ef-905c-62769e33de67
version: 187
created: '2024-06-28T09:28:23+05:30'
tags:
  - jenkins
---

# <mark style="background-color:#f8914d;">**SonarQube Scan\]**<!-- {"backgroundCycleColor":"24"} --></mark>

<mark>Types of scanning</mark>

![ef381a05-c5a2-4648-aa62-407317d37d70.png|645](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/ef381a05-c5a2-4648-aa62-407317d37d70.png) [^1]

\

![f9e4aec0-d390-4230-acd9-185608d71cac.png|960](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/f9e4aec0-d390-4230-acd9-185608d71cac.png) [^2]

Sonar cube server (generally sonar cube installation will be taken care by SRE team)

![1498750b-bde1-4f81-ab83-ad1939408980.png|1091.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/1498750b-bde1-4f81-ab83-ad1939408980.png) [^3]

\

Installation SonarQube

![8ab00c91-a4ed-4499-b013-e5d8b8514796.png|1100.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/8ab00c91-a4ed-4499-b013-e5d8b8514796.png) [^4]

\

\

```
labsetup
```

![63f8981d-8ca4-4ec2-91df-e8f348b93601.png|863](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/63f8981d-8ca4-4ec2-91df-e8f348b93601.png) [^5]

\

```
netstat -lntp
```

\

\

![d457a3a0-ac84-4c09-8575-d9f8d5c73756.png|1187.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/d457a3a0-ac84-4c09-8575-d9f8d5c73756.png) [^6]

![814655df-a2fd-4062-9a90-dbcac0d6b7ab.png|1148.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/814655df-a2fd-4062-9a90-dbcac0d6b7ab.png) [^7]

\

<mark>Now installing scanner CLI in Agent server</mark>

```
sudo su -
```

```
labauto
```

![d80a756e-ebcd-476e-9629-8b7375331eaf.png|1025.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/d80a756e-ebcd-476e-9629-8b7375331eaf.png) [^8]

![29e53813-1a99-44ee-ac3d-04e12a8ce896.png|910](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/29e53813-1a99-44ee-ac3d-04e12a8ce896.png) [^9]

\

![ed00ff03-d29a-4a29-85a0-b97d785f8844.png|1033](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/ed00ff03-d29a-4a29-85a0-b97d785f8844.png) [^10]

give sonarqube url and login information

![e55514df-0dc7-4b74-a082-3bdcd3fee403.png|944.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/e55514df-0dc7-4b74-a082-3bdcd3fee403.png) [^11]

\

generation token ( this step need to be done before above step giving login information)

![da83496e-e06a-4f2f-b88d-cfa3b26071ac.png|982.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/da83496e-e06a-4f2f-b88d-cfa3b26071ac.png) [^12]

\

Now configuring sonar project properties

![49af153f-2d22-4219-9114-9aca70dff63a.png|911](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/49af153f-2d22-4219-9114-9aca70dff63a.png) [^13]

![59671500-7d55-461d-a5b3-90e5ba05447a.png|1003.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/59671500-7d55-461d-a5b3-90e5ba05447a.png) [^14]

\

sonar scanner started and its uploading the results

![49c8e33f-20a9-4732-8c01-00a771377135.png|1021.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/49c8e33f-20a9-4732-8c01-00a771377135.png) [^15]

\

results

![98d8dc29-d7ae-4cd2-9a7d-531f541aa009.png|1010.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/98d8dc29-d7ae-4cd2-9a7d-531f541aa009.png) [^16]

\

<mark>**Quality gates - we need to give conditions as per our company standards**</mark>

![](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/9842c64a-2cb2-4b66-b913-daf73f0106bb.png) [^17]

![0f6d7d96-ed6c-4036-b66a-10d130316496.png|1051.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/0f6d7d96-ed6c-4036-b66a-10d130316496.png) [^18]

![5d725830-a267-4971-a29b-f436d9ddb2b0.png|1011.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/5d725830-a267-4971-a29b-f436d9ddb2b0.png) [^19]

\

# <mark style="background-color:#f8914d;">**Jenkins shared libraries**<!-- {"backgroundCycleColor":"24"} --></mark>

![4b1e15e8-d076-4555-82f9-a8871cbcf135.png|1072.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/4b1e15e8-d076-4555-82f9-a8871cbcf135.png) [^20]

![3cb1b172-cb76-444f-b02c-9aa3667ac5cf.png|1044.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/3cb1b172-cb76-444f-b02c-9aa3667ac5cf.png) [^21]

![8f707831-a1f8-4e8e-816c-4edcc1067180.png|1108.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/8f707831-a1f8-4e8e-816c-4edcc1067180.png) [^22]

\

# <mark style="background-color:#f8914d;">**multibranch pipeline**<!-- {"backgroundCycleColor":"24"} --></mark>

Most of the projects use multibranch pipeline

![ac237cc1-d247-4da2-ba10-d793915ee0d8.png|1005.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/ac237cc1-d247-4da2-ba10-d793915ee0d8.png) [^23]

\

# <mark style="background-color:#f8914d;">**Change Management process**<!-- {"backgroundCycleColor":"24"} --></mark>

![f4b08ca1-de3f-4839-8499-15a2d7f1e55c.png|1104.3333740234375](https://images.amplenote.com/aa8ac7e4-3502-11ef-905c-62769e33de67/f4b08ca1-de3f-4839-8499-15a2d7f1e55c.png) [^24]

[^1]: Static source code analysis
    sonarqubel
    Static application security testing
    fortify
    dynamic application security testing
    web inspect
    open source library scanning
    nexus iq
    docker image scanning
    twistlock, ECR scanning

[^2]: Jenkins Agent
    C
    Scan
    upload results
    clone
    scanner cli
    SonarQube Console

[^3]: Instances (1/7) Info
    C
    Connect
    Instance state
    Actions
    Laun
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    -
    Name _
    Instance ID
    Instance state
    Instance type v Status check
    Alarm st
    n
    Jenkins
    i-Of92b41f9c2767aa7
    Running Q Q
    t3.small
    2/2 checks passed View alar
    Agent
    i-061d15bcdfe 1375e6
    Running Q Q
    t3.small
    2/2 checks passed View alar
    jd-frontend-dont-delete
    i-0afd1dc386247e3df
    Stopped Q Q
    t3.small
    View alar
    jd-backend-dont-delete
    i-0alc7810e01b52dfo
    Stopped Q Q
    t3.small
    View alar
    sonarqube
    i-0305a86b81bfc1871
    Running Q Q
    t3.medium
    View alar
    0
    nexus
    i-0c90690a9a2d9179a
    Running Q Q
    t3.medium
    2/2 checks passed View ala

[^4]: docs.sonarsource.com/sonarqube/latest/try-out-sonarqube/
    container using one of our Docker images c. Select the method you prefer below to expand the installation
    De
    v
    Docs 10.3 v
    instructions:
    v From the zip file
    1. Download and install Java 17 @ on your system.
    narQube
    2. Download & the SonarQube Community Edition zip file.
    ents
    3. As a non- root user, unzip it in, for example, C: \\sonarqube or /opt/sonarqube .
    upgrade
    <
    4. As a non- root user, start the SonarQube server:
    source code
    atform integration
    # On Windows, execute:
    C: \\sonarqube\\bin\\windows-x86-64\\StartSonar. bat
    ministration
    # On other operating systems, as a non-root user execute:
    /opt/sonarqube/bin/<OS>/ sonar. sh console
    dministration
    Guide
    If your instance fails to start, check your logs to find the cause.

[^5]: 21) gocd-agent
    53) redis
    22) gocd-server
    54) roboshop-app-repos-import
    23) gradle
    55) roboshop-issue-tracker
    24) grafana
    56) roboshop-load-gen
    25) helm
    57) roboshop-single-node
    26) httpd-php
    58) s2i
    27) jenkins
    59) selenium
    28) k8-client-stack
    60) sonarqube
    29) k8s-single-node-cluster
    61) sonar-scanner
    30) k9s
    62) terrafile
    31) kfctl
    63) terraform
    32) kubectl
    64) todoapp-validate
    You can choose number or tool name
    Select Tool> 60

[^6]: v
    Instances \| EC2 \| us-east-1
    \* \| G sonarqube dev installation linux \|Try out SonarQube
    X
    How To Install And Configure S X \| scans,drawio - draw.jo
    x
    SonarQube
    A Not secure 44.222.220.206:9000/sessions/new?return_to=62F
    Log In to SonarQube
    admin
    .....
    Sing in Cancel

[^7]: v Instances \| EC2 \| us-east-1
    \* G sonarqube dev installation linux \|\\Try out SonarQube
    x How To Install And Configure S X \| . scans.drawio - draw.jo
    x
    Projects
    C
    A Not secure 44.222.220.206:9000/projects
    sonarqube Projects Issues Rules Quality Profiles Quality Gates Administration
    Q Search for projects...
    A
    My Favorites
    All
    Q Search by project name or key
    Add Project
    0 projects
    Perspective: Overall Status
    Sort by: Name
    Filters
    Quality Gate
    Passed
    Once you analyze some projects, they will show up here.
    Failed
    Here is how you can analyze new projects
    Reliability ( Bugs )
    Add a project
    0 of 0 shown

[^8]: 25) helm
    57) roboshop-single-node
    26) httpd-php
    58) s2i
    27) jenkins
    59) selenium
    28) k8-client-stack
    60) sonarqube
    29) k8s-single-node-cluster
    61)
    sonar-scanner
    30) k9s
    62) terrafile
    31) kfctl
    63) terraform
    32) kubectl
    64) todoapp-validate
    ? You can choose number or tool name
    Select Tool> 61
    \* Installing sonar-scanner \*\*\*
    8 Total
    & Received . Xferd Average Speed
    Time
    Time
    Time Current
    Dload Upload
    Total
    Spent
    Left Speed
    40 40 . 4M
    40 16.5M
    0
    0
    55 . OM
    55 . OM

[^9]: 4. 196. 126. 64 \| 172. 31 . 40.110 \| t3. small \| null
    root@ip-172-31-40-110 / \]# cd opt/
    4. 196. 126.64 \| 172. 31. 40.110 \| t3. small \| null
    root@ip-172-31-40-110 /opt \]# 1s
    onar sonar-scanner-cli-4 .5.0.2216-linux . zip
    4. 196. 126. 64 \| 172. 31 . 40. 110 \| t3. small \| null
    root@ip-172-31-40-110 /opt \]# cd sonar
    4. 196. 126.64 \| 172. 31. 40.110 \| t3. small \| null
    root@ip-172-31-40-110 /opt/sonar \]# 1s -1
    cotal 0
    rwxr-xr-x 2 root root 54 Oct 2
    2020 bin
    rwxr-xr-x 2 root root 38 Oct
    2
    2020 conf
    rwxr-xr-x 6 root root 68 Oct
    2
    2020 jre
    Irwxr-xr-x 2 root root 46 Oct
    2
    2020 lib
    4. 196.126. 64 \| 172 . 31 . 40.110 \| t3. small \| null
    root@ip-172-31-40-110 /opt/sonar \]# cd bin/
    4. 196. 126. 64 \| 172. 31 . 40.110 \| t3. small \| null
    root@ip-172-31-40-110 /opt/sonar/bin \]# ls
    sonar-scanner sonar-scanner-debug
    4. 196.126. 64 \| 172. 31 . 40.110 \| t3. small \| null
    root@ip-172-31-40-110 /opt/sonar/bin \]# cd . ./conf/

[^10]: 54 . 196.126.64 \| 172 . 31 . 40.110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /opt/sonar/conf \]# 1s -1
    total 4
    -rw-r--r-- 1 root root 310 Oct 2 2020
    sonar-scanner . properties
    54 . 196. 126. 64 \| 172. 31 . 40. 110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /opt/sonar/conf \]# vim sonar-scanner . properties

[^11]: 30 Protocol SSH
    . Host 54.196.126.64
    Login
    Password
    Session centos-8
    Commands
    sonarqube 54.196.126.64
    #Configure here general information about the environment, such as SonarQube server
    #No information about specific project should appear here
    # -
    Default SonarQube server
    sonar . host . url=http : / /44 .222 .220 . 206:9000
    sonar . login=4002bbd82314fe19c9f4a93ad072be4f19d5d6cd
    #
    Default source code encoding
    #sonar . sourceEncoding-UTF-8

[^12]: F
    -
    C
    A Not secure 44.222.220.206:9000/account/security/
    sonarqube Projects Issues Rules Quality Profiles Quality Gates Administration
    ?
    Q. Search for projects...
    A
    Administrator
    Profile Security Notifications Projects
    Tokens
    If you want to enforce security by not providing credentials of a real SonarQube user to run
    your code scan or to invoke web services. you can provide a User Token as a replacement of
    the user login. This wil increase the security of your installation by not letting your analysis
    user's password going through your network.
    Generate Tokens
    Enter Token Name
    Generate
    New token "jenkins-agent" has been created. Make sure you copy it now, you
    won't be able to see it again!
    4002bbd82314fe19c9f4a93ad872be4f195abcd
    Name
    Last use
    Created

[^13]: V
    REPOS
    catalogue > @ sonar-project.properties
    > .github
    sonar . projectkey=catalogue
    > ansible
    2
    catalogue
    > schema
    T
    Jenkinsfile
    {} package.json
    JS server.js
    sonar-project.properties
    U
    > catalogue-deploy

[^14]: catalogue
    43
    > schema
    44
    stage( 'Unit tests' ) {
    45
    Jenkinsfile
    M
    steps {
    46
    sh
    {} package.json
    47
    echo "unit tests will run here"
    JS server.js
    48
    sonar-project.properties
    U
    49
    > catalogue-deploy
    50
    > concepts
    51
    stage( ' Sonar Scan' ) {
    > learn-git
    52
    steps{
    53
    sh
    > learn-jenkins
    54
    sonar-scanner
    > notes
    55
    > roboshop-ansible
    56
    > roboshop-ansible-roles
    57

[^15]: F
    A Not secure 52.55.235.210:8080/job/catalogue/22/console
    Dashboard > catalogue > #22
    \[Pipeline\] stage
    \[Pipeline\] { (Unit tests)
    \[Pipeline\] sh
    + echo 'unit tests will run here'
    unit tests will run here
    \[Pipeline\] }
    \[Pipeline\] // stage
    \[Pipeline\] stage
    \[Pipeline\] { (Sonar Scan)
    \[Pipeline\] sh
    + sonar -scanner
    INFO: Scanner configuration file: /opt/sonalconf/sonar-scanner . properties
    INFO: Project root configuration file: /home/centos/jenkins-agent/workspace/catalogue/sonar-project.properties
    INFO: SonarScanner 4.5.0.2216
    INFO: Java 11.0.3 AdoptOpenJDK (64-bit)
    INFO: Linux 4.18.0-535. e18.x86_64 amd64
    INFO: User cache: /home/centos/ . sonar/cache
    INFO: Scanner configuration file: /opt/sonar/conf/sonar-scanner . properties
    INFO: Project root configuration file: /home/centos/jenkins-agent/workspace/catalogue/sonar-project.properties
    INFO: Analyzing on SonarQube server 8.9.10
    INFO: Default locale: "en_US", source code encoding: "UTF-8" (analysis is platform dependent)
    INFO: Load global settings

[^16]: A Not secure 44.222.220.206:9000/dashboard?id= catalogue
    sonarqube Projects Issues Rules Quality Profiles Quality Gates Administration
    Q. Search for projects..
    A
    catalogue > " master
    Last analysis had 3 warnings February 5, 2024 at 7:46 AM Version not provided
    Overview Issues Security Hotspots Measures Code Activity
    Project Settings . Project Information
    QUALITY GATE STATUS
    MEASURES
    Passed
    New Code
    Overall Code
    All conditions passed.
    3 x Bugs
    Reliability
    C
    0 6 Vulnerabilities
    Security
    A
    3 Security Hotspots
    O 0.0% Reviewed
    Security Review
    E
    1h Debt
    8 Code Smells
    Maintainability
    A
    O 0.0%
    O 0.0%
    0
    Coverage on 102 Lines to cover
    Unit Tests
    Duplications on 269 Lines
    Duplicated Blocks
    ACTIVITY

[^17]: quality gate
    0 bugs
    0 code snells
    security rating A
    code coverage 80

[^18]: Dashboard > catalogue >
    Status
    X
    catalogue
    </> Changes
    Add descri
    D
    Build with Parameters
    Disable P
    Configure
    Stage View
    Delete Pipeline
    Install
    Publish
    Declarative:
    Move
    Declarative:
    Get the version
    Unit tests
    Sonar Scan
    Build
    Deploy
    Checkout SCM
    dependencies
    Artifact
    Post Actions
    O Full Stage View
    126ms
    506ms
    Average stage times:
    1s
    283ms
    85
    408ms
    21s
    621ms
    967ms
    Rename
    (Average full run time: \~40s)
    #26
    Pipeline Syntax
    Feb 05
    No
    338ms
    162ms
    65
    368ms
    95
    06-03
    Changes
    Build History
    trend v
    350ms
    26s
    46ms
    47ms
    50ms
    216ms
    Feb 05
    9s
    Q Filter builds..
    365ms
    166ms
    05:01
    commit
    failed
    failed
    failed
    failed
    \* #26
    Feb 5. 2024 2:33 AM

[^19]: F
    C A Not secure 44.222.220.206:9000/dashboard?id=catalogue
    sonarQube Projects Issues
    Rules Quality Profiles Quality Gates Administration
    Q. Search for projects...
    A
    catalogue > \| master
    Last analysis had 3 warnings February 5, 2024 at 7:57 AM Version not provided
    Overview Issues Security Hotspots
    Measures
    Code Activity
    Project Settings . Project Information
    QUALITY GATE STATUS
    MEASURES
    Failed
    New Code
    Overall Code
    Since February 5. 2024
    2 conditions failed
    Started jfminutes ago
    On Overall Code
    3 Bugs
    Reliability
    C
    3
    Bugs is greater than 0
    8
    Code Smells is greater than 0
    O 6 Vulnerabilities
    Security
    A
    3 Security Hotspots
    O 0.0% Reviewed
    Security Review

[^20]: Language, Deployment platform
    NodeJs, AWS VM/ Docker/Kubernetes /PCF/On-prem VM
    HDFC --> 200 projects and many microservices
    nodejsvm pipeline --> don't duplicate the pipeline code
    reuse, implement best standards and force others to use
    nodejsvm pipeline --> implement best standards, reuse, centralised
    jenkins shared library --> treat your pipeline as library, use it wherever you want
    process
    1. create a feature branch in catalogue
    2. configure multi branch pipeline
    3. configure jenkins shared library

[^21]: F
    C
    A Not secure 52.55.235.210:8080/manage/configure
    libr
    1/3
    Dashboard > Manage Jenkins > System >
    X
    Global Pipeline Libraries
    Sharable libraries available to any Pipeline jobs running on this system. These libraries will be trusted, meaning they run without "sandbox" restrictions and may use @Grab.
    Library
    X
    Name ?
    roboshop-shared-library
    Default version ?
    main
    I
    A default version of the library to load if a script does not select another. Might be a branch name, tag, commit hash, etc., according to the SCM.
    (from Pipeline: Groovy Libraries)

[^22]: File Edit Selection View Go
    . . .
    9 repos
    EXPLORER
    sonar-project.properties
    7: Jenkinsfile.bkp
    Jenkinsfile ca
    V REPOS
    catalogue > Jenkinsfile
    > .github
    # ! groovy
    > ansible
    2
    @Library('roboshop-shared-library' ) _
    catalogue
    > schema
    Jenkinsfile
    M

[^23]: C A Not secure 52.55.235.210:8080/job/ROBOSHOP/newJob
    Dashboard > ROBOSHOP
    Freestyle project
    This is the central feature of Jenkins. Jenkins will build your project combining any SCM with any build system, and this can be even used
    for something other than software build.
    Pipeline
    Orchestrates long-running activities that can span multiple build agents. Suitable for building pipelines (formerly known as workflows)
    and/or organizing complex activities that do not easily fit in free-style job type.
    Multi-configuration project
    Suitable for projects that need a large number of different configurations, such as testing on multiple environments, platform-specific
    builds, etc.
    Folder
    Creates a container that stores nested items in it. Useful for grouping things together. Unlike view, which is just a filter, a folder creates a
    separate namespace. so you can have multiple things of the same name as long as they are in different folders.
    Multibranch Pimline
    Creates a set of Pipeline projects according to detected branches in one SCM repository.
    Organization Folder
    Creates a set of multibranch project subfolders by scanning for repositories.
    If you want to create a new item from other existing, you can use this option:
    Copy from
    Type to autocomplete
    OK

[^24]: Change management process
    we will raise a CR --> every organisation will have their own tool to manage CR.
    project code, application code, version, JIRA ID, approvals, date and time, deployment
    process, revert back process, post deployment testing.
    NEW --> CR ID
    Approve --> write some comments
    Delivery manager --> write some comments and approve
    Cleint --> approve
    JIRA --> Jenkins integration
    trigger PROD --> JIRA will check CR is approved or not, prod trigger time is same as time in
    CR.
    I
    Jenkins pipeline

