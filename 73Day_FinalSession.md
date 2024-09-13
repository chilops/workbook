---
title: 73Day_FinalSession
uuid: 4e953e44-4a40-11ef-ace6-6ef34fa959ce
version: 78
created: '2024-07-25T10:12:32+05:30'
---

# <mark style="background-color:#F8914D;">**Tell Me about yourself**<!-- {"backgroundCycleColor":"24"} --></mark>

![00cddfb0-c11d-488b-b653-50aab73a6af2.png|994.6666870117188](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/00cddfb0-c11d-488b-b653-50aab73a6af2.png) [^1]

![dfd51f35-c3ff-4632-bb39-802f88b6f176.png|1042.666748046875](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/dfd51f35-c3ff-4632-bb39-802f88b6f176.png) [^2]

![ccae449e-4cd7-4550-83f8-738f01fd5479.png|457](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/ccae449e-4cd7-4550-83f8-738f01fd5479.png) [^3]

\

<mark>**DevOps Team Leader**</mark>

![222cbde8-7d6d-4e54-9300-c2f56b28fe3c.png|722](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/222cbde8-7d6d-4e54-9300-c2f56b28fe3c.png) [^4]

\

# <mark style="background-color:#F8914D;">**How to move Application from DEV to Production**<!-- {"backgroundCycleColor":"24"} --></mark>

![e249674f-2889-4b20-b3bd-9906f4a3bdb6.png|958](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/e249674f-2889-4b20-b3bd-9906f4a3bdb6.png) [^5]

\

![cff609eb-dc89-4213-b939-83947b15568d.png|990.6666870117188](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/cff609eb-dc89-4213-b939-83947b15568d.png) [^6]

\

## <mark style="background-color:#F8D616;">**Merge Vs rebase**<!-- {"backgroundCycleColor":"25"} --></mark>

![a6338714-de64-4040-a368-ec604d441089.png|1064.666748046875](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/a6338714-de64-4040-a368-ec604d441089.png) [^7]

\

### <mark style="background-color:#F8D616;">**FastForward Merge** in bitbucket not in github<!-- {"backgroundCycleColor":"25"} --></mark>

![c90070a4-93f1-4d51-a5ee-62584d930e7c.png|986.6666870117188](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/c90070a4-93f1-4d51-a5ee-62584d930e7c.png) [^8]

\

# <mark style="background-color:#F8914D;">**Jenkins pipelines for different environments**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

---

![5365fa60-3abb-49d0-959f-482952052234.png|954.6666870117188](https://images.amplenote.com/4e953e44-4a40-11ef-ace6-6ef34fa959ce/5365fa60-3abb-49d0-959f-482952052234.png) [^9]

[^1]: My name is Sivakumar, I have 4 years of experience in Devops and AWS. We are using terraform
    as IaaC tool to create our infra in AWS. We have created our own modules and maintaining
    them. We are using EKS as our deployment platform. We have few legacy applications in VM as
    well. We configured autoscaling for VM as well EKS.
    We have applications in NodeJS, Java, Python. We have different kinds of DB like MySQL,
    MongoDB. We have a seperate DBAdmin to manage them
    We develop Jenkins CICD pipeline to deploy the applications into VM as welll as EKS. Our
    tools stack is
    GitHub/Bitbucket --> GitHub enterprise into our own infra, https:/ /github . joindevops. com
    Jenkins --> CICD
    SonarQube --> Scanning
    Unit testing
    Maven, NPM, pip as build tools
    Nexus for artifact upload
    Docker for imaging
    Helm charts for deployment
    We follow industry best practices like
    shift-left
    build once run any where -->
    jenkins shared libraries

[^2]: We have centralised pipelines, our developers can just call those pipelines to deploy
    applications, these are completely automated DEV to PROD. We let our developers to completely
    concentrate on development instead of deployment.
    We use JIRA for project management, we get tickets from our team lead or developers.

[^3]: clone
    build
    unit testing
    scanning --> code coverage 80%
    build
    artifact upload to nexus
    build docker image
    upload image nexus/ECR
    deployment using helm

[^4]: bring more projects into devops
    devsecops
    individual pipelines vs shared pipelines
    migrated to terraform
    migrated monolithic to microservices
    eks upgrades
    cloud security
    certifications
    architect
    CKA
    terraform
    Cost
    data charges --> cross az charges are there. .
    switch off dev resources in off business hours
    remove public communication between servers...
    gateways

[^5]: How to promote app to PROD
    - -
    - -
    Developers raise JIRA ticket mentioning their details
    Project code
    application
    version
    deployment date
    approver
    sonar scan results
    SAST, imaging scanning results
    what happened to testing
    I

[^6]: Change management
    Support team will raise CR, they will mention the JIRA ticket. same details as in JIRA and
    approval from client.
    Once CR is approved. Then our team will also approve JIRA
    We use JIRA for project management, we get tickets from our team lead or developers.
    master and feature
    We help them to onboard their project in all tool stack.
    I
    support team, they will trigger deployment
    our pipeline to PROD will be called and deployed. .
    main --> feature

[^7]: a merge commit ID is created into main branch. ..
    if commit ID is changed, are you 100% sure code is not changed --> no
    if commit ID is not changed, are you 100% sure code is not changed --> yes

[^8]: merge vs rebase
    a merge commit ID is created into main branch. ..
    if commit ID is changed, are you 100% sure code is not changed --> no
    if commit ID is not changed, are you 100% sure code is not changed --> yes
    merge strategy
    merge
    rebase
    squash
    feature --> 20 commits
    merge --> main branch will have a commit called merge commit
    rebase --> commit id will be rewritten and pushed to main branch
    fast-forward merge --> commit ID will never change even if you merge PR from feature to main
    branch.

[^9]: we have webhooks configured from github/bitbucket to jenkins, whenever there is a new commit
    into feature our developement pipeline will be automatically triggered.
    new commit push is the event

