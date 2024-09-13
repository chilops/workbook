---
title: 43_44Day_Jenkins
uuid: 31975af4-3382-11ef-ac7e-62769e33de67
version: 793
created: '2024-06-26T11:36:13+05:30'
tags:
  - jenkins
---

# <mark style="background-color:#f8914d;">**Input Directive**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

It asks permission/approvals to proceed further and run the build. 

![77d73b99-e9d4-4fe3-9e4a-0158c6583a54.png|968.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/77d73b99-e9d4-4fe3-9e4a-0158c6583a54.png) [^1]

\

Creating a separate folder for roboshop project

![d275d24f-3b49-457e-9a35-265a14e5ba31.png|1018.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/d275d24f-3b49-457e-9a35-265a14e5ba31.png) [^2] 

\

Creating a VPC pipeline project

![6aa3b6f5-54cc-4d99-b47a-1ea947d32c3d.png|1053.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/6aa3b6f5-54cc-4d99-b47a-1ea947d32c3d.png) [^3]

\

![76a2ffbb-48f7-4b1e-b4b7-4a49e7532dc6.png|1052](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/76a2ffbb-48f7-4b1e-b4b7-4a49e7532dc6.png) [^4]

![0c38cffe-65c8-4b1c-811c-79da83c97eaf.png|1080.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/0c38cffe-65c8-4b1c-811c-79da83c97eaf.png) [^5]

![4e6f1d11-30a8-4a46-bc46-f5984a4a3e36.png|1065](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/4e6f1d11-30a8-4a46-bc46-f5984a4a3e36.png) [^6]

\

\

Build now

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/e40e8d33-e336-4407-8164-07ff7a243ae5.png) [^7]

\

![f272e1e3-c14a-41e5-b86f-9f45954a3767.png|395](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/f272e1e3-c14a-41e5-b86f-9f45954a3767.png) [^8]

\

gets below error - Agent much know everything what they are running

![9356f7b5-e425-4b4e-bd90-9adb9decec8a.png|1065](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/9356f7b5-e425-4b4e-bd90-9adb9decec8a.png) [^9]

\

<mark>So now we need to install few tools in Agent</mark> 

![b85b375c-61e6-44b3-a8b7-abe7871d09de.png|519](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/b85b375c-61e6-44b3-a8b7-abe7871d09de.png) [^10]

\

Now installing terraform linux in Agent server

![37c3453e-cd77-4096-b184-7f1c66f37f61.png|854](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/37c3453e-cd77-4096-b184-7f1c66f37f61.png) [^11]

```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://rpm/releases/hashicorp.com/RHEL/hashicorp.repo
sudo yum install terraform -y
```

![8f3089de-e0ed-4e9b-aa23-6b2672777946.png|940](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/8f3089de-e0ed-4e9b-aa23-6b2672777946.png) [^12]

![4ce943c0-3d9b-4211-a1bf-5740ecdbec05.png|1041.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/4ce943c0-3d9b-4211-a1bf-5740ecdbec05.png) [^13]

\

Like wise add AWS CLI credentials in Agent servers

\

Now build 

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/2dda3670-6e31-43bc-9af6-f2ca54da8560.png) [^14]

\

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/9aacb464-dca0-4e99-bbd9-40bba69de13c.png) [^15]

Now terraform command is running and configuring VPC

![b60c123f-94a7-4cf5-a20f-1c3692a7d4de.png|762](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/b60c123f-94a7-4cf5-a20f-1c3692a7d4de.png) [^16]

\

<mark>**Now here its asking for approval to run or not.**</mark>

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/9f6d8202-beaa-4333-8351-e2b4bfb52b77.png) [^17]

Now you have to review the plan (here in my case terraform plan), now we can give approval.

![14f8cf52-2137-403a-bfad-76b33df8c6b4.png|957.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/14f8cf52-2137-403a-bfad-76b33df8c6b4.png) [^18]

\

VPC creations is successful now

![971fa16b-cbc2-42ba-ad1d-aa0bfbf777ae.png|918](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/971fa16b-cbc2-42ba-ad1d-aa0bfbf777ae.png) [^19]

\

# <mark style="background-color:#f8914d;">**Enabling colors(ANSIcolor plugin) in Jenkins pipeline**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![6eeba34d-bb97-406d-8b41-a6162444a602.png|860](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/6eeba34d-bb97-406d-8b41-a6162444a602.png) [^20]

\

Since its plugin, so you need to install it in Jenkins

![7531d7db-bd77-464f-8f0d-b1e389e1e0a2.png|991.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/7531d7db-bd77-464f-8f0d-b1e389e1e0a2.png) [^21]

![75f6c66e-ebc9-4b31-b975-7a321ce235f9.png|1115.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/75f6c66e-ebc9-4b31-b975-7a321ce235f9.png) [^22]

plugin install success

![ad4115da-e53a-44a7-afa5-31ef55cb0466.png|685](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/ad4115da-e53a-44a7-afa5-31ef55cb0466.png) [^23]

\

After plugin install we need to restart jenkins services in Jenkins master server.

```
systemctl restart jenkins
```

![19e35f1e-6e55-4952-b975-0f42926ff749.png|800](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/19e35f1e-6e55-4952-b975-0f42926ff749.png) [^24]

\

Now you can see the colors

![c04844b1-1f90-4a04-b1f7-f0ae0a912395.png|616](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/c04844b1-1f90-4a04-b1f7-f0ae0a912395.png) [^25]

\

# <mark style="background-color:#f8914d;">**When parameter/Condition in Jenkins**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

It like when branch name is production do this or execute

\

In below parameters if you select Apply terraform apply will run or if we select Destroy then it will run terraform destroy

![e174705e-d8b7-4bf5-8dc4-1ce2219cf568.png|1118](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/e174705e-d8b7-4bf5-8dc4-1ce2219cf568.png) [^26]

\

when condition

![4f7eef8d-9149-44e2-95a4-3cbf9f2772ce.png|1091.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/4f7eef8d-9149-44e2-95a4-3cbf9f2772ce.png) [^27]

\

Now run the build - APPLY

![a094a7d2-d8bc-480a-9407-bd0d23c0a4af.png|973.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/a094a7d2-d8bc-480a-9407-bd0d23c0a4af.png) [^28]

![29d70890-a601-4b92-98d4-f3dd54f9f1de.png|993.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/29d70890-a601-4b92-98d4-f3dd54f9f1de.png) [^29]

\

VPC configuration in progress

![c04844b1-1f90-4a04-b1f7-f0ae0a912395.png|616](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/c04844b1-1f90-4a04-b1f7-f0ae0a912395.png) [^30]

\

<mark>Now writing destroy stage</mark>

![da101d71-af3a-4a73-9823-258084f6fc0d.png|995.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/da101d71-af3a-4a73-9823-258084f6fc0d.png) [^31]

\

Now select the destroy option in parameters to destroy the terraform VPC.

![5ea6dffd-b8ef-4380-96a5-159da4b01606.png|1055.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/5ea6dffd-b8ef-4380-96a5-159da4b01606.png) [^32]

\

![8878b07b-df3b-4344-b028-af1414b3f77d.png|874](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/8878b07b-df3b-4344-b028-af1414b3f77d.png) [^33]

\

Now deploy skipped since we asked to destroy.

![e5f34b76-e365-4e39-8df4-ef85bd5b9225.png|1011](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/e5f34b76-e365-4e39-8df4-ef85bd5b9225.png) [^34]

\

Now all VPC infrastructure will destroy.

\

\

# <mark style="background-color:#f8914d;">**CICD for Application**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

<mark>Remember before proceeding to Application CICD we need to have Project infra build should be ready & completed (otherwise applications will not work).</mark>

In below all highlighted are **Project Infra** and remaining are **Application Infra.**

![64aa08e4-f9d0-462c-a872-afee6adf36e2.png|287](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/64aa08e4-f9d0-462c-a872-afee6adf36e2.png) [^35]

\
To build the catalogue CICD below is the process

![80f2d764-2e9a-48fb-a02b-e6c0047c55fb.png|530](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/80f2d764-2e9a-48fb-a02b-e6c0047c55fb.png) [^36]

![5b61fc29-4f55-4f04-b103-05755fc035f9.png|427](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/5b61fc29-4f55-4f04-b103-05755fc035f9.png) [^37]

\

# <mark style="background-color:#f8914d;">**CI for catalogue**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Catalogue code 

![b21a18ab-347a-4a42-a5da-5b9734317353.png|921](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/b21a18ab-347a-4a42-a5da-5b9734317353.png) [^38]

\

Install the pipeline utility plugin

![b308606b-c5d5-46fb-9310-751c58dc6f27.png|995.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/b308606b-c5d5-46fb-9310-751c58dc6f27.png) [^39]

![0023697c-3dd3-41a3-8807-86c6c303f24d.png|1072.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/0023697c-3dd3-41a3-8807-86c6c303f24d.png) [^40]

\

Now configure the catalogue pipeline in Jenkins.

![b36ce4fd-6f94-4c4c-b190-1a660a660dc6.png|1073.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/b36ce4fd-6f94-4c4c-b190-1a660a660dc6.png) [^41]

\

build now

![64696340-61a9-43b4-8591-327b83836ce0.png|293](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/64696340-61a9-43b4-8591-327b83836ce0.png) [^42]

\

success and we got the version details.

![a8a923dd-49eb-4f62-8649-37d762e96b2e.png|940](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/a8a923dd-49eb-4f62-8649-37d762e96b2e.png) [^43]

\

Installing dependencies (NPM install)

![d45f5bcd-9ca9-4f52-a1da-5b07ae5093ae.png|1018.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/d45f5bcd-9ca9-4f52-a1da-5b07ae5093ae.png) [^44]

\

This is in Agent server

```
dnf module disable nodejs -y
dnf module enable nodejs:18 -y
dnf install nodejs -y
```

![fee14eab-823a-4083-a0a7-04af46c4cb53.png|1065.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/fee14eab-823a-4083-a0a7-04af46c4cb53.png) [^45]

![c12a3395-d802-48b9-a585-35edca017bc2.png|1065.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/c12a3395-d802-48b9-a585-35edca017bc2.png) [^46]

\

Now run the build and its success

![9850ec1c-dc05-4abd-8782-cb2b09d3f4ae.png|1069.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/9850ec1c-dc05-4abd-8782-cb2b09d3f4ae.png) [^47]

\

# <mark style="background-color:#f8914d;">**NEXUS (nexus sonatype) Installation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Nexus is a popular repository, It stores zip, jar files etc... git only stores code not zip files.

![0566f2bb-0b7b-4781-a3a4-aa458a173e8f.png|982.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/0566f2bb-0b7b-4781-a3a4-aa458a173e8f.png) [^48]

\

Create 1 instance - 2gb ram required

![ff398690-2195-42bc-943e-e4a32c322819.png|1059.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/ff398690-2195-42bc-943e-e4a32c322819.png) [^49]

\

**Installing Nexus**

Labauto -  these scripts created by siva.. we can use it.. refer below github link for more info

![7b59778f-5b99-4b65-942f-e02a8181bd9d.png|909](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/7b59778f-5b99-4b65-942f-e02a8181bd9d.png) [^50]

\

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/d515129a-e8fa-41a2-9c5c-f19a19852bf3.png) [^51]

\

Now nexus is running

![cd1c4a91-e32c-41c4-ba0a-4a53d603e3c0.png|1012.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/cd1c4a91-e32c-41c4-ba0a-4a53d603e3c0.png) [^52]

\

![65125f5c-cb31-4883-9fad-11e00f4df838.png|1144.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/65125f5c-cb31-4883-9fad-11e00f4df838.png) [^53]

\

If not running to check logs below process

![00c9d839-5b4f-4355-9a7e-2e1a65e69763.png|1055](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/00c9d839-5b4f-4355-9a7e-2e1a65e69763.png) [^54]

![fee6aecb-4f84-41e5-be67-1ce61c4886c5.png|1048.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/fee6aecb-4f84-41e5-be67-1ce61c4886c5.png) [^55]![85c085e9-fff7-48ce-97dd-4d441b2a0787.png|1049.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/85c085e9-fff7-48ce-97dd-4d441b2a0787.png) [^56]

\

Setting up Nexus

\

![ee2ec58b-8e55-41e1-a401-ff0f7545d452.png|1031.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/ee2ec58b-8e55-41e1-a401-ff0f7545d452.png) [^57]

\

To signup 

![08d782fa-4f61-4858-b3b7-ebf510362718.png|982.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/08d782fa-4f61-4858-b3b7-ebf510362718.png) [^58]

![5c0c1474-dcaa-4c91-b53e-6887157f2d90.png|1095.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/5c0c1474-dcaa-4c91-b53e-6887157f2d90.png) [^59]

\

give new psw

![8d9be335-4760-4ee1-8eb1-0c7b14c58c6c.png|1103.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/8d9be335-4760-4ee1-8eb1-0c7b14c58c6c.png) [^60]

![4e1e40ed-c6a6-4067-a198-637179417496.png|1122.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/4e1e40ed-c6a6-4067-a198-637179417496.png) [^61]

\

It has all repos that we can use from here.

![23549d48-a04f-407d-a779-7374a855d72e.png|1119.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/23549d48-a04f-407d-a779-7374a855d72e.png) [^62]

\

<mark>**Now we need to create a repo for our catalogue, so we are using maven2 (hosted)**</mark>

Mavan2 is a popular format

![6d3a5b13-6f0e-4a16-a8e0-3dbd21e8b6a6.png|917](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/6d3a5b13-6f0e-4a16-a8e0-3dbd21e8b6a6.png) [^63]

\

Catalogue repository created

![4ce09e90-015a-4b52-a1b5-f57618118fc7.png|1149.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/4ce09e90-015a-4b52-a1b5-f57618118fc7.png) [^64]

\

In this URL we can storage catalogue related zip & other files etc

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/7710dd6d-ae03-49a9-bab3-060b0ceae31d.png) [^65]

\

\

Now zipping files in Linux

![](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/ec144606-3311-453b-8c62-33306c19f676.png) [^66]

![8784b474-20cf-4db2-a18f-66f34fe0acb8.png|1069.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/8784b474-20cf-4db2-a18f-66f34fe0acb8.png) [^67]

\

![8784b474-20cf-4db2-a18f-66f34fe0acb8.png|1069.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/8784b474-20cf-4db2-a18f-66f34fe0acb8.png) [^68]

\

Zipping the folder

\

![fdd278f9-4e80-4c72-a4a2-ad6f23505df7.png|1066.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/fdd278f9-4e80-4c72-a4a2-ad6f23505df7.png) [^69]

or

![851ac8b9-ae3a-4083-9ba0-fe5da0a69cc9.png|1172.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/851ac8b9-ae3a-4083-9ba0-fe5da0a69cc9.png) [^70]

\

In Jenkins code

![7e6dac63-915d-4198-8bc1-75b7df7061a4.png|1075.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/7e6dac63-915d-4198-8bc1-75b7df7061a4.png) [^71]

\

Build now

![c16ba9c9-6094-48e4-ad2f-7206ae9d9ff7.png|1053](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/c16ba9c9-6094-48e4-ad2f-7206ae9d9ff7.png) [^72]

# <mark style="background-color:#f8914d;">**Removing workspace in Agent ( removing workspace folder in pipeline)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![f487acaf-e382-4503-9933-dcb7c38311e9.png|1160.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/f487acaf-e382-4503-9933-dcb7c38311e9.png) [^73]

---

# <mark style="background-color:#f8914d;">**Pushing Artifacts to Nexus**<!-- {"backgroundCycleColor":"24"} --></mark>

![5abce38c-b17b-4edf-980f-b47660d9fa26.png|858](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/5abce38c-b17b-4edf-980f-b47660d9fa26.png) [^74]

\

when you run the build now in Jenkins we can see the zip file and now it has to be moved to Nexus

![7ecf260a-ec5a-4e16-b43d-c6430e7c3bfd.png|1011.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/7ecf260a-ec5a-4e16-b43d-c6430e7c3bfd.png) [^75]

\

To do this install Nexus artifact uploader plugin in Jenkins

![b3149c34-ceaf-4bef-944d-2cecd8d596ea.png|1016.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/b3149c34-ceaf-4bef-944d-2cecd8d596ea.png)

Creating nexus auth

![ce178291-f301-4bf4-9a29-a845da464965.png|1062.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/ce178291-f301-4bf4-9a29-a845da464965.png) [^76]

\

Code in Jenkins file

![bb84709f-cd50-48ce-a9e8-cfe86958d79a.png|452](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/bb84709f-cd50-48ce-a9e8-cfe86958d79a.png) [^77]

![4eafef23-46b4-4202-b12c-00fac116bd14.png|988.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/4eafef23-46b4-4202-b12c-00fac116bd14.png) [^78]

\

Build now & zip file uploaded to nexus

![7cd47c09-79cc-46de-a85e-c6f093a25bcf.png|1036.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/7cd47c09-79cc-46de-a85e-c6f093a25bcf.png) [^79]

\

in Nexus

![e107fbb7-e1f3-4169-9fae-ffc95b618717.png|983.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/e107fbb7-e1f3-4169-9fae-ffc95b618717.png) [^80]

\

Till now we did is CI process for catalogue.

\

# <mark style="background-color:#f8914d;">**Now CD process for catalogue**<!-- {"backgroundCycleColor":"24"} --></mark>

![a1d5e330-dd32-4de9-8175-3eb048a6884c.png|586](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/a1d5e330-dd32-4de9-8175-3eb048a6884c.png) [^81]

![882981e8-81eb-49f6-8261-9e67e10dd981.png|520](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/882981e8-81eb-49f6-8261-9e67e10dd981.png) [^82]

\

![41a61e49-277c-48a3-9868-81699f929d16.png|603](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/41a61e49-277c-48a3-9868-81699f929d16.png) [^83]

![a3f040f7-6f81-4902-9ddc-98e4304561e6.png|1027](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/a3f040f7-6f81-4902-9ddc-98e4304561e6.png) [^84]

![af5d5917-773f-4fc2-9c17-579e2bd4a6ba.png|1046.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/af5d5917-773f-4fc2-9c17-579e2bd4a6ba.png) [^85]

\

If CI is success then only we call CD ( CI is upstream job & CD is downstream job)

![38263152-4711-4e18-b0b6-82023cdc65a6.png|1032.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/38263152-4711-4e18-b0b6-82023cdc65a6.png) [^86]

\

# <mark style="background-color:#f8914d;">**Trigger one pipeline from another pipeline**<!-- {"backgroundCycleColor":"24"} --></mark>

How to call another pipeline from Jenkins pipeline with parameters.

![2bab1e78-d941-4551-a07b-09bbc2ded871.png|1049.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/2bab1e78-d941-4551-a07b-09bbc2ded871.png) [^87]

\

once run catalog then catalog-deploy also runned & printed

![634f2c7c-c423-41a1-8b6c-62f01d27bbce.png|896](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/634f2c7c-c423-41a1-8b6c-62f01d27bbce.png) [^88]

install 

![fd7f04dd-da9e-4160-a47f-cc361421d64a.png|1083.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/fd7f04dd-da9e-4160-a47f-cc361421d64a.png) [^89]

![00de04ff-aec0-4b00-a4ec-1479d7ab7c4c.png|1083.3333740234375](https://images.amplenote.com/31975af4-3382-11ef-ac7e-62769e33de67/00de04ff-aec0-4b00-a4ec-1479d7ab7c4c.png) [^90]

[^1]: EXPLORER
    . . .
    README.MD learn-git
    Jenkinsfile learn-jenkins
    variables.tf ...\\01-vpc
    Jenkinstile ... \\01-vpc U X
    V REPOS
    roboshop-infra-dev > 01-vpc > Jenkinsfile
    > .github
    27
    28
    >
    ansible
    29
    > concepts
    30
    stage( ' Deploy' ) {
    > learn-git
    31
    input {
    > learn-jenkins
    32
    message "Should we continue?"
    > notes
    33
    ok "Yes, we should. "
    > roboshop-ansible
    34
    / / submitter "alice, bob"
    35
    1/
    > roboshop-ansible-roles
    parameters {
    36
    11
    string (name : 'PERSON' , defaultValue: 'Mr Jenkins' , description: 'Wh
    > roboshop-ansible-roles-tf
    37
    > roboshop-documentation
    38
    roboshop-infra-dev
    39
    steps {
    01-vpc
    40
    sh " In
    .terraform
    41
    cd 01-vpc
    42
    > modules
    terraform apply -auto-approve
    43
    providers
    44
    {} terraform.tfstate
    45
    E.terraform.lock.hcl
    46
    Jenkinsfile
    U
    47
    // post build
    48
    post {

[^2]: Dashboard > All >
    Enter an item name
    ROBOSHOP-INFRA
    Required field
    Freestyle project
    This is the central feature of Jenkins. Jenkins will build your project. combining any SCM with any build system, and this can be even used
    for something other than software build.
    Pipeline
    Orchestrates long-running activities that can span multiple build agents. Suitable for building pipelines (formerly known as workflows)
    and/or organizing complex activities that do not easily fit in free-style job type.
    Multi-configuration project
    Suitable for projects that need a large number of different configurations, such as testing on multiple environments, platform-specific
    builds, etc.
    Folder
    Creates a container that stores nested items in it. Useful for grouping things together. Unlike view, which is just a filter, a folder creates a
    separate namespace, so you can have multiple things of the same name as long as they are in different folders.
    Multibranch Pipeline
    Creates a set of Pipeline projects according to detected branches in one SCM repository.
    Organization Folder
    Creates a set of multibranch project subfolders by scanning for repositories.
    If you want to create a new item from other existing, you can use this option:
    OK

[^3]: Dashboard > ROBOSHOP-INFRA >
    Enter an item name
    vpc
    > Required field
    Freestyle project
    This is the central feature of Jenkins. Jenkins will build your project, combining any SCM with any build system, and this can be even used
    for something other than software build.
    Pipeline
    Orchestrates long-running activities that can span multiple build agents. Suitable for building pipelines (formerly known as workflows)
    and/or organizing complex activities that do not easily fit in free-style job type.
    Multi-configuration project
    Suitable for projects that need a large number of different configurations, such as testing on multiple environments, platform-specific
    builds, etc.
    Folder
    Creates a container that stores nested items in it. Useful for grouping things together. Unlike view, which is just a filter, a folder creates a
    separate namespace, so you can have multiple things of the same name as long as they are in different folders.
    Multibranch Pipeline
    Creates a s
    ipeline projects accor

[^4]: Pipeline
    Definition
    Pipeline script
    Pipeline script
    Pipeline script from SCM
    try sample Pipeline..

[^5]: Pipeline
    Definition
    Pipeline script from SCM
    SCM ?
    Git
    Repositories ?
    Repository URL ?
    X
    https://github.com/daws-76s/roboshop-infra-dev.git
    Credentials ?
    none -
    + Add
    Advanced v

[^6]: Script Path ?
    01-vpc/Jenkinsfile
    Relative location (/-separated regardless of platform) within the checkout of your Pipeline script. Note that it will always be run inside a Groovy sandbox. Jenkinsfile is conventional and
    allows you to switch easily to a multibranch project (just use checkout som to retrieve sources from the same location as is configured here).
    (from Pipeline: Groovy)
    Lightweight checkout ?
    Pipeline Syntax
    Save
    Apply

[^7]: Build Now
    Configure
    Delete Pipeline

[^8]: Build History
    trend v
    O Filter build Took 0.23 sec
    x #1
    Feb 1, 2024, 2:05 AM
    Atom feed for all \\\\ Atom feed for failures

[^9]: + cd 01-vpc
    + terraform init -reconfigure
    /home/centos/jenkins-agent/workspace/ROBOSHOP-INFRA/vpc@tmp/durable-6dced99b/script. sh: line 3: terraform: command not found
    Cloning repository https://github. com/daws-76s/roboshop-infra-dev.git
    > git init /home/centos/jenkins-agent/workspace/ROBOSHOP-INFRA/vpc # timeout=10
    Fetching upstream changes from https://github. com/daws-76s/roboshop-infra-dev.git
    > git --version # timeout=10

[^10]: agent
    terraform command
    should have aws creds also

[^11]: Linux
    Package manager
    Ubuntu/Debian
    CentOS/RHEL
    Fedora
    Amazon Linux
    Homebrew
    $ sudo yum install -y yum-utils
    Copy
    $ sudo yum-config-manager --add-repo https://rpm. releases. hashicorp.com/RHEL/hashicorp. repo
    $ sudo yum -y install terraform

[^12]: 23. 22. 117. 92 \| 172. 31. 40. 110 \| t3. small \| null
    \[ centosdip-172-31-40-110 \~ \]$ sudo yum install -y yum-utils

[^13]: 23 . 22 . 117. 92 \| 172. 31. 40.110 \| t3. small \| null
    \[ centos@ip-172-31-40-110 \~ \]$ sudo yum-config-manager --add-repo https: //rpm. releases . hashicorp. com/RHEL/hashicorp . repo
    Adding repo from: https: / /rpm. releases . hashicorp. com/RHEL/hashicorp . repo
    23 . 22. 117. 92 \| 172. 31 . 40. 110 \| t3. small \| null
    \[ centosdip-172-31-40-110 \~ \]$ sudo yum -y install terraform
    Hashicorp Stable - x86 64
    19 MB/S \| 1.3 MB
    00:00

[^14]: Build Now
    Configure

[^15]: Build History
    trend
    V
    Q Filter builds...
    X
    #3
    Feb 1, 2024. at09 AM

[^16]: + cd 01-vpc
    + terraform init -reconfigure
    \[Ome \[1mInitializing the backend. . .0\[0m
    \[Om@ \[ 32m
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.\[0m
    \[Om@ \[1mInitializing modules . . .6\[Om
    Downloading git: :https://github. com/daws-76s/terraform-aws-vpc. git?ref=main for roboshop. ..
    - roboshop in . terraform/modules/roboshop
    \[Ome \[1mInitializing provider plugins. . .0\[0m
    - Reusing previous version of hashicorp/aws from the dependency lock file
    - Installing hashicorp/aws v5.31.0. ..

[^17]: Should we continue?
    Yes, we should. or Abort

[^18]: Stage View
    Move
    Declarative:
    Declarative:
    Init
    Plan
    Deploy
    Full Stage View
    Checkout SCM
    Post Actions
    Rename
    Average stage times:
    416ms
    75
    25
    93ms
    171ms
    ? Pipeline Syntax
    #3
    Feb 01
    No
    338ms
    13
    Should we continue?
    194ms
    Changes
    07:39
    Yes, we hould.
    Abort
    for 158
    Build History
    trend v
    Q Filter builds..
    #2
    Feb 0
    No
    495ms
    655ms
    135ms
    93ms
    171ms
    Changes
    < #3
    Feb 1, 2024, 2:09 AM
    07:36
    failed
    failed
    failed
    X

[^19]: \[ome \[ Immodule . roboshop . aws_route
    _association . public\[1\] :
    eating. .
    \[Im50s
    elapsed 1 10me jom
    \[OmE \[1mmodule . roboshop . aws_route_table_association. public\[1\]: Creation complete after Im53s \[id=rtbassoc-0297f0248feaaba82\]6\[Om
    \[0me \[1ma \[ 32m
    Apply complete! Resources: 32 added, 0 changed, 0 destroyed.
    \[0m
    \[Pipeline\] }
    \[Pipeline\] // stage
    \[Pipeline\] stage
    \[Pipeline\] { (Declarative: Post Actions)
    \[Pipeline \] echo
    I will always say Hello again!
    \[Pipeline \] echo
    I will say Hello when pipeline is success
    \[Pipeline \] }
    \[Pipeline\] // stage
    \[Pipeline\] }
    \[Pipeline\] // timeout
    \[Pipeline \] }
    \[Pipeline\] // withEnv
    \[Pipeline \] }
    \[Pipeline\] // node
    \[Pipeline\] End of Pipeline
    Finished: SUCCESS

[^20]: > roboshop-documentation
    options { -
    8
    timeout (time: 1, unit: 'HOURS' )
    roboshop-infra-dev
    9
    disableConcurrentBuilds ()
    01-vpc
    10
    ansiColor( 'xterm' )
    > .terraform
    E .terraform.lock.hel
    Jenkinsfile
    -
    M
    13
    / / build
    1 1
    stages
    S

[^21]: Jenkins
    Q Search (CTRL+K)
    Dashboard > Manage Jenkins
    + New Item
    Manage Jenkins
    People
    Building on the built-in node can be a security issue. You should set the number of executors on the built-in node to 0. See the documentation.
    Build History
    Project Relationship
    System Configuration
    Check File Fingerprint
    System
    Tools
    Plugins
    03 Manage Jenkins
    Configure global settings and paths.
    Configure tools, their locations and
    Add, remove, disable or enable plugins
    My Views
    automatic installers.
    that can extend the functionality of
    Jenkins.
    Build Queue
    Clouds
    Add, remove, and configure cloud
    No builds in the queue.
    instances to provision agents on-
    demand.
    Build Executor Status
    V

[^22]: Dashboard > Manage Jenkins > Plugins
    Plugins
    Q ansiColor
    Ins
    Updates
    Install
    Name !
    Released
    Available plugins
    AnsiColor 1.0.4
    Miscellaneous
    4 mo 27 days ago
    53 Installed plugins
    Adds ANSI coloring to the Console Output
    Advanced settings
    Download progress

[^23]: Download progress
    Preparation
    . Checking internet connectivity
    . Checking update center connectivity
    . Success
    lonicons API
    Success
    Folders
    Success
    OWASP Markup Formatter
    Success
    JSON Path API
    Success
    Structs
    Success
    Pipeline: Step API
    Success
    Token Macro
    Success

[^24]: 3. 81. 35. 108 \| 172. 31. 40.220 \| t3. small \| null
    \[ root@ip-172-31-40-220 \~ \]# systemctl restart jenkins

[^25]: Initializing the backend...
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing modules ...
    Initializing provider plugins...
    - Reusing previous version of hashicorp/aws from the dependency lock file
    - Installing hashicorp/aws v5. 31.0. ..

[^26]: roboshop-ansible-roles-tf
    12
    parameters {
    > roboshop-documentation
    13
    choice (name: 'action', choices: \['apply' , ' destroy\], description: 'Pick something
    roboshop-infra-dev
    14
    01-vpc
    15
    / / build
    > .terraform
    16
    stages {
    E.terraform.lock.hcl
    17
    stage ( ' Init' ) {
    Jenkinsfile
    18
    M
    steps {
    19

[^27]: learn-jenkins
    32
    Jenkinsfile
    33
    stage( ' Deploy' ) {
    34
    > notes
    when {
    35
    expression {
    > roboshop-ansible
    36
    params . action == 'apply' \|
    > roboshop-ansible-roles
    37
    I
    > roboshop-ansible-roles-tf
    38
    > roboshop-documentation
    39
    input {
    roboshop-infra-dev
    40
    message "Should we continue?"
    01-vpc
    41
    ok "Yes, we should."
    42
    > .terraform
    // submitter "alice, bob"
    43
    / / parameters {
    E.terraform.lock.hcl
    44
    string(name: 'PERSON' , defaultValue: 'Mr Jenkins', description: 'Who
    Jenkinsfile
    M
    45

[^28]: Jenkins
    Q Search (CTRL+K)
    Dashboard > ROBOSHOP-INFRA > vpc >
    Status
    Pipeline vpc
    </> Changes
    This build requires parameters:
    Build with Parameters
    action
    3 Configure
    Pick something
    apply
    1 Delete Pipeline
    Move
    Built
    Cancel
    Q Full Stage View
    Rename
    ?
    Pipeline Syntax
    Build History
    trend v
    Q Filter builds...

[^29]: Dashboard > ROBOSHOP-INFRA > v
    Status
    X vpc
    </> Changes
    Full project name: ROBOSHOP-INFRA/vpc
    Build with Parameters
    03
    Configure
    Delete Pipeline
    Stage View
    Move
    Declarative:
    Declarative:
    Init
    Plan
    Deploy
    O Full Stage View
    Checkout SCM
    Post Actions
    150ms
    Rename
    Average stage times:
    1s
    11s
    As
    36s
    (Average full run time: \~ 1min 55s)
    ? Pipeline Syntax
    #10
    Feb 01
    No
    161ms
    Changes
    07:55
    Build History
    trend v
    Q Filter builds...
    #9
    Feb 01
    457ms
    15s
    5s
    149ms
    138ms
    07:59
    commits
    8 #10
    Feb 1, 2024, 2:25 AM
    aborted
    aborted
    #8
    8 #9
    Feb 1, 2024, 2:25 AM
    Feb 01
    No
    Changes
    \* #8
    Feb 1, 2024, 2:24 AM
    07:54

[^30]: Initializing the backend...
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing modules ...
    Initializing provider plugins...
    - Reusing previous version of hashicorp/aws from the dependency lock file
    - Installing hashicorp/aws v5. 31.0. ..

[^31]: > learn-git
    54
    stage( ' Destroy' ) {
    learn-jenkins
    55
    when {
    56
    Jenkinsfile
    expression {
    57
    params . action == 'destroy'
    > notes
    58
    > roboshop-ansible
    59
    > roboshop-ansible-roles
    60
    input {
    > roboshop-ansible-roles-tf
    61
    message "Should we continue?"
    > roboshop-documentation
    62
    ok "Yes, we should. "
    63
    roboshop-infra-dev -
    / / submitter "alice, bob"
    64
    / / parameters {
    01-vpc
    65
    11
    string (name: 'PERSON' , defaultValue: 'Mr Jenkin
    > .terraform
    66
    E .terraform.lock.hcl
    67
    }
    Jenkinsfile
    M
    68
    steps {
    main.tf
    69
    sh "un
    70
    parameters.tf
    cd 01-vpc
    71
    terraform destroy -auto-approve
    provider.tf
    72
    11 11 H1
    variables.tf
    73
    OUTLINE

[^32]: Dashboard > ROBOSHOP-INFRA > vpc >
    Status
    Pipeline vpc
    </>
    Changes
    This build requires parameters:
    Build with Parameters
    action
    Configure
    Pick something
    apply
    Delete Pipeline
    apphy
    Move
    destroy
    D Build
    Cancel
    Q Full Stage View
    Rename

[^33]: Jenkins
    Dashboard > ROBOSHOP-INFRA > vpc > #11
    Status
    Build #11 (Feb 1, 2024, 2:26:25 AM)
    </> Changes
    P Console Output
    Changes
    Edit Build information
    1. jenkins (details / githubweb)
    Parameters
    Started by user admin
    Git Build Data
    Revision: c729220eb8d09d168b604101faf7c9074f42887e
    git
    Thread Dump
    Repository: https://github.com/daws-76s/roboshop-infra-dev.git
    . refs/remotes/origin/main
    1\| Pause/resume

[^34]: Jenkins
    Q. Sear
    Dashboard > ROBOSHOP-INFRA > vpc >
    Status
    X vpc
    </> Changes
    Full project name: ROBOSHOP-INFRA/vpc
    Build with Parameters
    Configure
    Delete Pipeline
    Stage View
    Move
    Declarative:
    Init
    Plan
    Deploy
    Destroy
    O Full Stage View
    Checkout SCM
    Rename
    Average stage times:
    355ms
    15s
    5s
    Oms
    2s
    ?
    Pipeline Syntax
    #11
    Feb 01
    355ms
    15s
    5s
    25
    07:56
    commit
    Build History
    trend v
    Q Filter builds...

[^35]: > 01-vpc
    > 02-sg
    > 03-vpn
    > 04-databases
    -
    > 05-app-alb
    > 06-catalogue
    > 07-acm
    > 08-web-alb
    > 09-web
    CAdevops\\daws-76s\\repos\\robo
    10-cdn
    > 11-user
    > 12-shipping
    > 13-cart
    > 14-payment

[^36]: CI
    clone the code
    unit testing
    scans
    sonar scan
    SAST
    DAST
    Open source scanning
    docker image scanning
    dependencies install
    build --> zip file
    we need to push to Nexus

[^37]: CD
    deploy to dev
    functional test cases
    publish the results

[^38]: EXPLORER
    . . .
    ile learn-jenkins
    parameters.tf ..\\01-vpc
    variables.tf .. \\01-vpc
    Jenkinsfile
    V REPOS
    catalogue > JS server.js
    > .github
    const mongoClient = require(' mongodb ' ) . MongoClient;
    ansible
    2
    const mongoobjectID = require( 'mongodb ' ) . ObjectID;
    3
    catalogue
    const bodyParser = require( ' body-parser' ) ;
    4
    const express = require(' express' ) ;
    > schema
    5
    const pino = require( 'pino' ) ;
    {} package.json
    6
    const expPino = require(' express-pino-logger' ) ;
    JS server.js
    7
    > concepts
    8
    const logger = pino({
    > learn-git
    9
    level: 'info's
    > learn-jenkins
    10
    prettyPrint: false,
    11
    useLevelLabels: true
    notes
    12
    > roboshop-ansible
    13
    const expLogger = expPino({
    > roboshop-ansible-roles
    14
    logger: logger
    > roboshop-ansible-roles-tf
    15
    > roboshop-documentation
    16
    > roboshop-infra-dev
    17
    / / MongoDB
    18
    > roboshop-shell
    var db;
    19
    var collection;
    > roboshop-terraform
    20
    var mongoConnected = false;
    > shell-script
    21
    > terraform
    22
    const app = express ( ) ;
    > terraform-aws-security-group
    23
    > OUTLINE
    24
    app . use (expLogger) ;

[^39]: Dashboard > Manage Jenkins > Plugins
    Plugins
    Q pipeline ut
    Install
    v
    C
    Updates
    Install
    Name !
    Released
    Available plugins
    Pipeline Utility Steps 2.16.1
    pipeline
    Build Tools
    Miscellaneous
    9 days 13 hr ago
    3 Installed plugins
    Utility steps for pipeline jobs.
    103 Advanced settings

[^40]: V REPOS
    catalogue > # Jenkinsfile
    > .github
    22
    > ansible
    23
    password (name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a passwor
    24
    catalogue
    25
    // build
    >
    schema
    26
    stages {
    Jenkinsfile
    27
    stage( 'Get the version' ) {
    \[} package.json
    28
    steps {
    JS server.js
    29
    script {
    > concepts
    30
    def package\]son = readJSON file: 'package . json'
    31
    learn-git
    packageVersion = package\]son . version
    I
    32
    echo "application version: $package"
    learn-jenkins
    33
    Jenkinsfile
    34
    >
    notes
    35
    > roboshop-ansible
    36
    stage ( ' Test' ) {
    > roboshop-ansible-roles
    37
    steps {
    > roboshop-ansible-roles-tf
    38
    echo 'Testing. .'
    39
    > roboshop-documentation
    40

[^41]: Jenkins
    Q Search (CTRL+
    Dashboard > All >
    Enter an item name
    catalogue
    > Required field
    Freestyle project
    This is the central feature of Jenkins. Jenkins will build your project, combining any SCM with any build system, and this can be even used
    for something other than software build.
    Pipeline
    Orchestrates long-running activities that can span multiple build agents. Suitable for building pipelines (formerly known as workflows)
    and/or organizing complex activities that do not easily fit in free-style job type.

[^42]: Jenkins
    Dashboard > catalogue >
    Status
    </> Changes
    Build scheduled
    Build Now
    Configure
    Delete Pipeline
    Move
    O Full Stage View
    Rename
    Pipeline Syntax

[^43]: A Not secure
    3.81.35.108:8080/job/catalogue/1/console
    Dashboard > catalogue > #1
    \[Pipeline\] checkout
    Git Build Data
    Selected Git installation does not exist. Using Default
    The recommended git tool is: NONE
    Restart from Stage
    No credentials specified
    Cloning the remote Git repository
    Replay
    Avoid second fetch
    Checking out Revision da4adobb7d8f114a640c72ea46bd4cc0594ebbe (refs/remotes/origin/main)
    Pipeline Steps
    Commit message: "jenkins"
    First time build. Skipping changelog.
    Workspaces
    \[Pipeline\] }
    \[Pipeline\] // stage
    \[Pipeline\] withEnv
    \[Pipeline\] {
    \[Pipeline\] withEnv
    \[Pipeline\] {
    \[Pipeline\] timeout
    Timeout set to expire in 1 hr 0 min
    \[Pipeline\] {
    \[Pipeline\] stage
    \[Pipeline\] { (Get the version)
    \[Pipeline\] script
    \[Pipeline\] {
    \[Pipeline\] readJSON
    \[Pipeline\] echo
    application version: 1.0.0

[^44]: catalogue
    23
    1/
    password (name: 'PASSWORD' , defaultValue: 'SECRET' , descripti
    > schema
    24
    Jenkinsfile
    M
    25
    / / build
    26
    {} package.json
    stages {
    27
    stage( 'Get the version' ) {
    JS server.js
    28
    steps {
    >
    concepts
    29
    script {
    > learn-git
    30
    def package\]son = readJSON file: 'package. json'
    learn-jenkins
    31
    packageVersion = package\]son . version
    Jenkinsfile
    32
    echo "application version: $packageVersion"
    33
    > notes
    34
    > roboshop-ansible
    35
    > roboshop-ansible-roles
    36
    stage ( ' Install dependencies' ) {
    > roboshop-ansible-roles-tf
    37
    steps {
    > roboshop-documentation
    38
    sh
    > roboshop-infra-dev
    39
    npm install
    > roboshop-shell
    40
    41
    > roboshop-terraform
    42

[^45]: 23. 22. 117. 92 \| 172 . 31 . 40. 110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos \]# anf module disable nodejs -y
    Last metadata expiration check: 0:27:02 ago on Thu 01 Feb 2024 02:20:48 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Disabling modules:
    nodejs
    Transaction Summary
    Complete!
    23 . 22. 117.92 \| 172 . 31 . 40.110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos \]#
    23. 22. 117. 92 \| 172. 31 . 40. 110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos \]# dnf module enable nodejs : 18 -y

[^46]: 23. 22. 117. 92 \| 172. 31. 40. 110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos \]# dnf install nodejs -y
    Last metadata expiration check: 0:27:18 ago on Thu 01 Feb 2024 02:20:48 AM UTC.

[^47]: Dashboard > catalogue > #3
    \[Pipeline\] // stage
    \[Pipeline \] withEnv
    \[Pipeline\] {
    \[Pipeline \] withEnv
    \[Pipeline\] {
    \[Pipeline\] timeout
    Timeout set to expire in 1 hr 0 min
    \[Pipeline\] {
    \[Pipeline\] stage
    \[Pipeline\] { (Get the version)
    \[Pipeline\] script
    \[Pipeline \] {
    \[Pipeline\] readJSON
    \[Pipeline\] echo
    application version: 1.0.0
    \[Pipeline\] }
    \[Pipeline\] // script
    \[Pipeline\] }
    \[Pipeline\] / / stage
    \[Pipeline\] stage
    \[Pipeline\] { (Install dependencies)
    \[Pipeline\] sh
    + npm install
    npm WARN deprecated express-pino-logger@4.0.0: use pino-http instead

[^48]: git --> repository --> code --> dont store artifacts
    nexus --> repository --> artifacts --> dont store code here
    I

[^49]: Instances (3) Info
    G
    Connect
    Instance state V
    Actions
    Launch instances
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    < 1 >
    O
    Name
    4
    Instance ID
    Instance state
    4
    Instance type
    Status check
    Alarm status
    Availability Zor
    O
    Jenkins
    i-Of92b41f9c2767aa7
    Running Q Q
    t3.small
    2/2 checks passed View alarms +
    us-east-1c
    Agent
    i-061d15bcdfe 1375e6
    Running Q Q
    t3.small
    2/2 checks passed View alarms +
    us-east-1c
    nexus
    i-0c90690a9a2d9179a
    Pending Q Q
    t3.medium
    View alarms +
    us-east-1d

[^50]: 100 .26.147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ rootdip-172-31-5-95 /home/centos \]# labauto
    You can find all the scripts in following location
    https://github . com/linuxautomations/labautomation/tree/master/tools
    >>>>> Select a TOOL to Install
    1) ansible
    33) kubens
    2) artifactory
    34) kubergrunt
    3) aws-auth
    35) letsencrypt
    4)
    awsauto
    36) liquibase
    5)
    aws-iam-authenticator
    37) maven
    6)
    awx
    38) minikube
    7) azcli
    39) miscellaneous
    8) create-roboshop-app-repos
    40) mongodb
    9) docker
    41) mongodb-client
    10) docker-compose
    42) mysql
    11) docker-stack
    43) mysql-client
    12) eksctl
    44) nexus
    13) elk
    45) nodejs
    14) filebeat
    46) octant
    15) fix-jenkins-java-issue
    47) packer

[^51]: @ You can choose number or tool name
    Select Tool> nexus
    Found Multiple Scripts, Choose One. .
    1) create-repos . sh
    2) install . sh
    3) install-with-ssl . sh
    #? 2
    Ax Installing nexus \*\*\*
    Disabled FIREWALL Successfully

[^52]: \[ rootdip-172-31-5-95 /home/centos \]# systemctl status nexus
    nexus . service - LSB: nexus
    Loaded: loaded (/etc/rc. d/init. d/nexus; generated)
    Active: active (exited) since Thu 2024-02-01 03:05:13 UTC; 1min 2s ago
    Docs: man : systemd-sysv-generator (8)
    Process: 5799 ExecStart=/etc/rc.d/init.d/nexus start (code=exited, status=0/SUCCESS)

[^53]: 100 .26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/sonatype-work/nexus3/log \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    top
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    843/sshd
    tcp
    OOO
    0 127 . 0 . 0 . 1 : 45377
    0.0.0.0:\*
    LISTEN
    6256/java
    top
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0: 8081
    0.0.0.0:\*
    LISTEN
    6256/java
    tcp6
    0 : : :22
    : : : \*
    LISTEN
    843/sshd
    top6
    0 : ::111
    LISTEN
    1/systemd

[^54]: 100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home \]# 1s
    centos nexus
    100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home \]# cd nexus/
    100 . 26.147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus \]# 1s
    nexus-3. 64 .0-04 sonatype-work
    100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus \]# cd nexus-3. 64.0-04/
    100 .26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/nexus-3. 64.0-04 \]# 1s
    bin deploy etc lib NOTICE. txt OSS-LICENSE. txt PRO-LICENSE. txt public rep
    100 . 26. 147. 241 \| 172.31.5.95 \| t3. medium \| null
    +dip-172-31-5-95 /hon
    Ine
    64

[^55]: \[ root@ip-172-31-5-95 /home/nexus/sonatype-work \]# ls
    nexus 3
    100 . 26. 147.241 \| 172 . 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/sonatype-work \]# cd nexus3/
    100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/sonatype-work/nexus3 \]# 1s
    admin . password cache
    elasticsearch generated-bundles karaf.pid lock orient restore-from-backup
    blobs
    db
    etc
    instances
    keystores log
    port
    tmp
    100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/sonatype-work/nexus3 \]# cd log/
    100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ rootdip-172-31-5-95 /home/nexus/sonatype-work/nexus3/log \]# 1s
    audit jvm. log karaf . log nexus_cluster. log nexus . log outbound-request. log request. log
    100 . 26.147. 241 \| 172 . 31.5.95 \| t3 . medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/sonatype-work/nexus3/log \]# 1s -1
    total 260
    drwxrwxr-x 2 nexus nexus
    23 Feb 1 03:05 audit
    -rw-rw-r--
    nexus nexus 73728 Feb 1 03:06 jvm. log
    -rw-rw-r--
    nexus nexus
    344 Feb
    1 03:05 karaf . log
    -rw-rw-r--
    nexus nexus
    0 Feb
    1 03:05 nexus_cluster . log
    -rw-rw-r--
    nexus nexus 70442 Feb
    1 03:06 nexus . log
    -rw-rw-r--
    1
    nexus nexus
    0 Feb
    1 03:05 outbound-request . log
    -rw-rw-r--
    1
    nexus nexus
    0 Feb
    1 03:06 request . log

[^56]: 100 . 26. 147. 241 \| 172 . 31.5.95 \| t3. medium \| null
    \[ root@ip-172-31-5-95 /home/nexus/sonatype-work/nexus3/log \]# 1s -1
    total 260
    drwxrwxr-x 2 nexus nexus
    23 Feb 1 03:05 audit
    -rw-rw-r--
    1 nexus nexus 73728 Feb
    1 03:06 jvm . log
    -rw-rw-r--
    1 nexus nexus
    344 Feb
    1 03:05 karaf . log
    -rw-rw-r--
    1 nexus nexus
    0 Feb
    1 03:05 nexus cluster . log
    rw-rw-r--
    1 nexus nexus 70442 Feb
    1 03:06 nexus . log
    rw-rw-r--
    1 nexus nexus
    0 Feb
    1 03:05 outbound-request . log
    -rw-rw-r-- 1 nexus nexus
    0 Feb
    03:06 request. log
    I
    100 . 26. 147. 241 \| 172 . 31.5.95 \| t3. medium \| null
    \[ rootdip-172-31-5-95 /home/nexus/sonatype-work/nexus3/log \]# less nexus . log

[^57]: ->
    X
    A Not secure 100.26.147.241:8081
    sonatype
    Loading baseapp-prod.js
    nexus repository

[^58]: A Not secure 100.26.147.241:8081
    Sonatype Nexus Repository
    Q Search components
    OSS 3.64.0-04
    Browse
    O Welcome
    Welcome
    Q Search
    Browse
    Browse
    a
    Search
    >
    Connect
    Browse my repositories
    Search for new components
    Connect to a reposito
    Help us serve you better!
    Sign In
    X
    Your admin user password is located in
    home/nexus/sonatype-
    work/nexus3/admin.password on the
    English
    What's New?
    server.
    psitory OSS? W
    October 2023
    admin
    New OpenShift Operator with High Availability Support
    Password
    rvey will be ke
    for PostgreSQL Deployments
    for the purpos
    Sign in
    Cancel
    esearch, or ar
    As explained in our Sonatype Nexus Repository 3 Feature Status
    a customer feedback call.
    page , Sonatype will be officially sunsetting the old OrientDB
    OpenShift operator on December 15, 2023.

[^59]: 100 . 26. 147. 241 \| 172. 31.5.95 \| t3. medium \| null
    \[ rootdip-172-31-5-95 /home/nexus/sonatype-work/nexus3/log \]# cat /home/nexus/sonatype-work/nexus3/admin . password
    d91ca65c-3a6c-4f22-9847-155cc09035a5
    100 . 26. 147. 241 \| 172. 31.5.95
    t3. medium \| null

[^60]: C
    A Not secure 100.26.147.241:8081
    Sonatype Nexus Repository
    Q Search components
    OSS 3.64.0-04
    Browse
    Welcome
    Welcome
    Search
    Usage
    Browse
    1. Upload
    Total components
    Unique logins
    Peak requests per minute
    Peak requests per day
    0
    0
    0
    Past 30 days
    Past 24 hours
    Past 30 days
    Please choose a password for the admin user
    2 of 4
    New password:
    System Health
    View system status checks
    I
    Confirm password:
    Back
    Next
    English

[^61]: F
    A Not secure 100.26.147.241:8081/#browse/browse
    Sonatype Nexus Repository
    Q Search components
    O
    E ?
    adm
    OSS 3.64.0-04
    Browse
    Browse Browse assets and components
    Welcome
    Filter
    Q Search
    Name 1
    Type
    Format
    Status
    URL
    Health check
    Browse
    maven-central
    proxy
    maven2
    Online - Ready to Connect
    copy
    Analyze
    maven-public
    group
    maven2
    Online
    copy
    O
    1. Upload
    maven-releases
    hosted
    maven2
    Online
    copy
    O
    maven-snapshots
    hosted
    maven2
    Online
    copy
    O
    nuget-group
    group
    nuget
    Online
    copy
    nuget-hosted
    hosted
    nuget
    Online
    copy
    nuget.org-proxy
    proxy
    nuget
    Online - Remote Available
    copy
    Analyze

[^62]: F
    C A Not secure 100.26.147.241:8081/#admin/repository/repositories
    Sonatype Nexus Repository
    Q Search components
    OSS 3.64.0-04
    Administration
    Repositories / Select Recipe
    Repository
    Recipe 1
    Repositories
    apt (hosted)
    apt (proxy)
    Blob Stores
    bower (group)
    Proprietary Repositories
    bower (hosted)
    bower (proxy)
    Content Selectors
    cocoapods (proxy)
    Cleanup Policies
    conan (proxy)
    conda (proxy)
    Routing Rules
    8
    docker (group)
    8
    docker (hosted)
    Security
    docker (proxy)
    8 Privileges
    gitlfs (hosted)
    8
    go (group)
    Roles
    go (proxy)
    2 Users
    helm (hosted)
    helm (proxy)
    Anonymous Access
    maven2 (group)
    LDAP
    maven2 (hosted)
    maven2 (proxy)
    me Realms
    npm (group)
    npm (hosted)
    SSL Certificates
    npm (proxy)
    D IQ Server
    nuget (group)
    nuget (hosted)

[^63]: maven 2 format
    1000
    firstname
    firstname+lastname --> same
    firstname+lastname+dob --> may be possible
    project, modules, versions
    project --> roboshop
    modules --> catalogue
    version --> 1.0.0, 1.0.1, 2.0.0
    group id --> com. roboshop
    artifact id --> catalogue
    version --> 10.0.0
    I

[^64]: A Not secure 100.26.147.241:8081/#admin/repository/repositories
    Sonatype Nexus Repository
    OSS 3.64.0-04
    Q Search components
    E ?
    admin
    Sign out
    Administration
    Repositories Manage repositories
    V
    Repository updated: catalogue
    Repository
    + Create repository
    Filter
    Repositories
    Name 1
    Type
    Format
    Blob Store
    Status
    URL
    Health check
    Firewall Re...
    Blob Stores
    catalogue
    hosted
    maven2
    default
    Online
    copy
    maven-central
    proxy
    maven2
    default
    Online - Ready to Connect
    Proprietary Repositories
    copy
    Analyze
    maven-public
    group
    maven2
    default
    Online
    copy
    Content Selectors
    maven-releases
    hosted
    maven2
    default
    Online
    copy
    Cleanup Policies
    maven-snapshots
    hosted
    maven2
    default
    Online
    copy
    Routing Rules
    nuget-group
    group
    Online
    copy
    Copy to clipboard: Ctri-C, Enter
    nuget-hosted
    hosted
    X
    nline
    copy
    Security
    nuget.org-proxy
    proxy
    Use your repository's direct URL (shown below) to connect other
    nline - Remote Available
    copy
    Analyze
    g Privileges
    tools to your repository. For more information, see our Maven-
    specific help documentation.
    Roles
    http://100.26.147.241:8081/repository/catalogue/
    Users
    Close
    Anonymous Access

[^65]: http://100 . 26. 147 . 241 : 8081/lrepository/catalogue/

[^66]: zip -r \[filename\] .zip
    \[directory_name_to_zip\] -x \[file_to_exclude\]

[^67]: \[ root@ip-172-31-40-110 /home/centos \]# cd jenkins-agent/
    23 . 22. 117. 92 \| 172. 31 . 40.110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos/jenkins-agent \]# 1s -1
    total 1340
    drwxrwxr-x 3 centos centos
    26 Feb 1 01:58 caches
    drwxrwxr-x 4 centos centos
    34 Feb
    1 01:57 remoting
    -rw-rw-r-- 1 centos centos 1371733 Feb
    1 01:57 remoting . jar
    drwxrwxr-x 7 centos centos
    114 Feb
    1 02:45 workspace
    23. 22. 117. 92 \| 172. 31. 40.110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos/jenkins-agent \]# cd workspace/
    23. 22. 117. 92 \| 172. 31. 40. 110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos/jenkins-agent/workspace \]# ls
    catalogue catalogue@tmp hello-pipeline hello-pipeline@tmp ROBOSHOP-INFRA
    23. 22. 117. 92 \| 172. 31. 40.110 \| t3. small \| null
    \[ rootdip-172-31-40-110 /home/centos/jenkins-agent/workspace \]# cd catalogue
    23 . 22. 117.92 \| 172. 31 . 40.110 \| t3. small \| https: / /github. com/daws-76s/catalogue . git
    \[ rootdip-172-31-40-110 /home/centos/jenkins-agent/workspace/catalogue \]# 1s -1
    total 156
    -rw-rw-r--
    1 centos centos
    1923 Feb 1 02:55 Jenkinsfile
    drwxrwxr-x 163 centos centos
    8192 Feb
    1
    02:55 node_modules
    -rw-rw-r--
    1 centos centos
    490 Feb
    02:45 package . json
    -rw-rw-r--
    1 centos centos 127561 Feb
    1
    02:55 package-lock. json
    drwxrwxr-x
    2 centos centos
    26 Feb
    1 02:45 schema
    -rw-rw-r--
    1 centos centos
    5336 Feb 1 02:45 server. js

[^68]: \[ root@ip-172-31-40-110 /home/centos \]# cd jenkins-agent/
    23 . 22. 117. 92 \| 172. 31 . 40.110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos/jenkins-agent \]# 1s -1
    total 1340
    drwxrwxr-x 3 centos centos
    26 Feb 1 01:58 caches
    drwxrwxr-x 4 centos centos
    34 Feb
    1 01:57 remoting
    -rw-rw-r-- 1 centos centos 1371733 Feb
    1 01:57 remoting . jar
    drwxrwxr-x 7 centos centos
    114 Feb
    1 02:45 workspace
    23. 22. 117. 92 \| 172. 31. 40.110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos/jenkins-agent \]# cd workspace/
    23. 22. 117. 92 \| 172. 31. 40. 110 \| t3. small \| null
    \[ root@ip-172-31-40-110 /home/centos/jenkins-agent/workspace \]# ls
    catalogue catalogue@tmp hello-pipeline hello-pipeline@tmp ROBOSHOP-INFRA
    23. 22. 117. 92 \| 172. 31. 40.110 \| t3. small \| null
    \[ rootdip-172-31-40-110 /home/centos/jenkins-agent/workspace \]# cd catalogue
    23 . 22. 117.92 \| 172. 31 . 40.110 \| t3. small \| https: / /github. com/daws-76s/catalogue . git
    \[ rootdip-172-31-40-110 /home/centos/jenkins-agent/workspace/catalogue \]# 1s -1
    total 156
    -rw-rw-r--
    1 centos centos
    1923 Feb 1 02:55 Jenkinsfile
    drwxrwxr-x 163 centos centos
    8192 Feb
    1
    02:55 node_modules
    -rw-rw-r--
    1 centos centos
    490 Feb
    02:45 package . json
    -rw-rw-r--
    1 centos centos 127561 Feb
    1
    02:55 package-lock. json
    drwxrwxr-x
    2 centos centos
    26 Feb
    1 02:45 schema
    -rw-rw-r--
    1 centos centos
    5336 Feb 1 02:45 server. js

[^69]: 23. 22. 117. 92 \| 172. 31. 40. 110 \| t3. small \| https: / /github. com/daws-76s/catalogue . git
    rootdip-172-31-40-110 /home/centos/jenkins-agent/workspace/catalogue \]# zip -r catalogue . zip
    . /\* -x ".git"
    adding: Jenkinsfile (deflated 65%)
    adding: node modules/ (stored 0%)
    adding: node_modules/express-pino-logger/ (stored 0%)
    adding: node_modules/express-pino-logger/package . json (deflated 57%)
    adding: node_modules/express-pino-logger/. travis .yml (deflated 19%)
    adding: node_modules/express-pino-logger/example. js (deflated 45%)
    adding: node_modules/express-pino-logger/LICENSE (deflated 41%)
    adding: node_modules/express-pino-logger/logger . js (stored 0%)
    adding: node modules/express-pino-logger/README.md (deflated 56%)
    adding: node_modules/express-pino-logger/test . js\]

[^70]: 23. 22. 117. 92 \| 172. 31. 40.110 \| t3. small \| https: / /github. com/daws-76s/catalogue . git
    \[ rootdip-172-31-40-110 /home/centos/jenkins-agent/workspace/catalogue \]# zip -r catalogue . zip ./\*-
    -x
    git"
    -x "\* . zip"
    updating: Jenkinsfile (deflated 65%)
    updating: node_modules/ (stored 0%)
    updating: node_modules/express-pino-logger/ (stored 08)
    updating: node_modules/express-pino-logger/package . json (deflated 57%)
    updating: node_modules/express-pino-logger/ . travis .yml (deflated 19%)
    updating: node_modules/express-pino-logger/example . js (deflated 45%)
    updating: node_modules/express-pino-logger/LICENSE (deflated 41%)
    updating: node_modules/express-pino-logger/logger . js (stored 08)
    I
    updating: node_modules/express-pino-logger/README .md (deflated 56%)
    updating:
    node modules/express-pino-logger/test. is

[^71]: catalogue
    42
    schema
    43
    stage ( ' Build' ) {
    Jenkinsfile
    44
    steps {
    {} package.json
    45
    sh
    JS server.js
    46
    ls - la
    concepts
    47
    zip -q -r catalogue. zip ./\* -x ".git" -x "\*.zip"
    48
    ls -1tr
    > learn-git
    49
    > learn-jenkins
    50
    > notes
    51
    roboshop-ansible
    52
    stage ( ' Deploy' ) {
    > roboshop-ansible-roles
    53
    steps {
    > roboshop-ansible-roles-tf
    54
    sh "un
    > roboshop-documentation
    55
    echo
    "Here I wrote shell script"
    56
    #sleep 10
    roboshop-infra-dev
    57
    17 11 13
    > roboshop-shell
    58
    > roboshop-terraform
    59
    > shell-script
    60

[^72]: F
    A Not secure 3.81.35.108:8080/job/catalogue/5/console
    Dashboard > catalogue > #5
    adding: node_modules/.bin/ncp (deflated 54%)
    adding: node_modules/ .bin/pino (deflated 22%)
    adding: node_modules/ . bin/pino-pretty (deflated 55%)
    adding: node_modules/ .bin/rimraf (deflated 47%)
    adding: node_modules/ . bin/semver (deflated 65%)
    adding: package. json (deflated 42%)
    adding: package-lock. json (deflated 70%)
    adding: schema/ (stored 0%)
    adding: schema/catalogue. js (deflated 60%)
    adding: server. js (deflated 73%)
    + 1s -ltr
    total 5284
    -rw-rw-r- -
    1 centos centos
    5336 Feb 1 02:45 server. js
    drwxrwxr-x
    2 centos centos
    26 Feb 1 02:45 schema
    -rw-rw-r- -
    1 centos centos
    490 Feb 1 02:45 package . json
    - rw-rw-r- -
    1 centos centos
    2041 Feb 1 03:22 Jenkinsfile
    drwxrwxr-x 163 centos centos
    8192 Feb 1 03:22 node_modules
    -rw-rw-r- -
    1 centos centos 127561 Feb 1 03:22 package-lock. json
    -rw-rw-r- - 1 centos centos 5248934 Feb 1 03:22 catalogue. zip
    \[Pipeline\] }

[^73]: EXPLORER
    pc
    Jenkinsfile ... \\01-vpc
    JS server.js
    Jenkinsfile catalogue M X
    JS catalogue.js
    REPOS
    catalogue > Jenkinsfile
    > .github
    58
    ansible
    59
    / / post build
    catalogue
    60
    post {
    schema
    61
    always {
    Jenkinsfile
    M
    62
    echo 'I will always say Hello again!'
    {} package.json
    63
    deleteDir ()
    JS server.is
    64

[^74]: http://3. 237 . 181 . 150: 8081/repository/catalogue/
    jenkins --> nexus
    nexus artifact uploader
    nexus URL, authentication

[^75]: F
    C
    A Not secure 52.91.250.151:8080/job/catalogue/7/console
    Dashboard > catalogue > #7
    -ru-rw-r-- 1 centos centos 5356 Feb 2 01:55 server. j:
    + zip -q -r catalogue. zip ./Jenkinsfile ./node_modules ./package. json ./package-lock.json ./schema ./server.js -x .git -x "\*.zip'
    + 1s -ltr
    total 5284
    - ru-rw-r.-
    1 centos centos
    2044 Feb 2 01:55 Jenkinsfile
    I
    -ru-rw-r- -
    1 centos centos
    5336 Feb 2 01:55 server. j=
    druxrwxr-x 2 centos centos
    26 Feb 2 01:55 schema
    -ru-rw-r.-
    1 centos centos
    490 Feb 2 01:55 package. json
    -ru-rw-r- -
    1 centos centos 127561 Feb 2 01:55 package-lock. json
    druxrwxr-x 163 centos centos
    8192 Feb 2 01:55 node_modules
    -ru-rw-r.- 1 centos centos 5248937 Feb 2 01:55 catalogue. zip
    \[Pipeline\] }
    \[Pipeline\] // stage

[^76]: Jenkins
    Q Search (CTRL+K)
    1 9 admin \~ C
    Dashboard > Manage Jenkins > Credentials > System > Global credentials (unres
    Check your saved passwords
    Global credentials (unrestricted)
    The password you just used was found in a data breach. To secure your
    + Add Credentials
    accounts, Google Password Manager recommends changing it now and
    checking your saved passwords.
    Credentials that should be available irrespective of domain specification
    Check passwords
    Close
    ID
    Name
    Description
    ssh-auth
    ssh-auth
    Username with password
    ssh-auth
    nexus-auth
    nexus-auth
    Username with password
    nexus-auth
    Icon:
    S
    M

[^77]: environment
    packageVersion = '
    nexusURL = '172. 31.5. 95 : 8081

[^78]: REPOS
    catalogue > Jenkinsfile
    > .github
    54
    steps {
    > ansible
    55
    nexusArtifactUploader(
    catalogue
    56
    nexusVersion: 'nexus3' ,
    > schema
    57
    protocol: 'http' ,
    Jenkinsfile
    58
    M
    nexusUrl: "$ {nexusURL}"
    59
    () package.json
    groupId: 'com. roboshop' ,
    60
    version: "${packageVersion}",
    JS server.js
    61
    repository: 'catalogue' ,
    > concepts
    62
    credentialsId: "'nexus-auth',
    > learn-git
    63
    artifacts : \[
    learn-jenkins
    64
    \[artifactId: 'catalogue' ,
    Jenkinsfile
    65
    classifier:
    66
    > notes
    file: 'catalogue . zip' ,
    67
    > roboshop-ansible
    type: 'zip' \] I
    68
    > roboshop-ansible-roles
    69
    > roboshop-ansible-roles-tf
    70

[^79]: Repository : catalogue
    Uploading: http://172.31.5.95:8081/repository/catalogue/com/roboshop/catalogue/1.0.0/catalogue-1.0.0. zip
    10 % completed (541 kB / 5.2 MB).
    20 % completed (1.1 MB / 5.2 MB).
    30 % completed (1.6 MB / 5.2 MB).
    40 % completed (2.1 MB / 5.2 MB).
    50 % completed (2.7 MB / 5.2 MB).
    60 % completed (3.2 MB / 5.2 MB).
    70 % completed (3.7 MB / 5.2 MB).
    80 % completed (4.2 MB / 5.2 MB) .
    90 % completed (4.8 MB / 5.2 MB).
    100 % completed (5.2 MB / 5.2 MB).
    Uploaded: http://172.31.5.95:8081/repository/catalogue/com/roboshop/catalogue/1.0.0/catalogue-1.0.0.zip (5.2 MB at 5.6 MB/s)
    Uploading artifact catalogue. zip completed.
    \[Pipeline\] { (Deploy)

[^80]: C A Not secure 3.237.181.150:8081/#browse/browse:catalogue:com%2Froboshop%2Fcatalogue%2F1.0.0%2Fcatalogue-1.0.0.zip
    Finish update
    Sonatype Nexus Repository
    Q Search componer
    E ?
    admin
    Sign out
    OSS 3.64.0-04
    Browse
    Browse / catalogue
    Welcome
    Upload component HTML View
    Advanced search..
    Q Search
    com
    com/roboshop/catalogue/1.0.0/catalogue-1.0.0.zip
    roboshop
    Browse
    m Delete asset
    catalogue
    Upload
    1.0.0
    Summary
    D catalogue-1.0.0.zip
    catalogue-1.0.0.zip.md5
    Repository
    catalogue
    In catalogue-1.0.0.zip.sha1
    Format
    maven2
    Component Group
    com.roboshop
    Component Name
    catalogue
    Component Version
    1.0.0
    Path
    com/roback
    gue-1.0.(
    Open link in new tab
    Open link in new window

[^81]: create a server
    provision it using ansible
    stop server
    take AMI
    create launch template version
    refresh autoscaling

[^82]: catalogue-deploy
    terraform
    $ bootstrap.sh
    data.tf
    locals.tf
    main.tf
    provider.tf
    variables.tf
    Jenkinsfile

[^83]: download artifact from nexus
    download specific version
    ansible
    nexus location
    artifact version

[^84]: Jenkins
    Dashboard > All >
    Enter an item name
    catalogue-deploy
    > Required field
    Freestyle project
    This is the central feature of Jenkins. Jenkins will build your project, combining
    for something other than software build.
    Pipeline
    Orchestrates long-running activities that can span multiple build agents. Suital
    and/or organizing complex activities that do not easily fit in free-style job type
    Multi-configuration project

[^85]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/catalogue (main)
    $ cd . ./catalogue-deploy/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/catalogue-deploy
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/catalogue-deploy/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/catalogue-deploy (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/catalogue-deploy (main)
    $ git remote add origin git@github.com: daws-76s/catalogue-deploy. git

[^86]: Jenkins
    Q Search (CTRL+K)
    1 2 admin " C log out
    Dashboard >
    Add description
    + New Item
    All
    28 People
    Build History
    S
    W
    Name !
    Last Success
    Last Failure
    Last Duration
    Project Relationship
    catalogue
    12 min #9
    17 min #8
    12 sec
    D
    Check File Fingerprint
    -O-
    catalogue-deploy
    N/A
    N/A
    N/A
    D
    03 Manage Jenkins
    CD

[^87]: catalogue
    69
    70
    > schema
    71
    Jenkinsfile
    M
    72
    stage ( ' Deploy' ) {
    {} package.json
    73
    steps {
    JS server.js
    74
    script { J
    catalogue-deploy
    75
    def params = \[
    terraform
    76
    string (name: 'version', value: "$packageVersion")
    $ bootstrap.sh
    77
    string(name: 'environment' , value: "dev")
    78
    data.tf
    79
    build job: "catalogue-deploy", wait: true, parameters: params
    locals.tf
    80
    main.tf
    81
    provider.tf
    82
    variables.tf
    83

[^88]: Dashboard > catalogue-deploy > #2
    LIAPLAANIL\] HALILLILY
    \[Pipeline\] {
    \[Pipeline\] timeout
    Timeout set to expire in 1 hr 0 min
    \[Pipeline\] {
    \[Pipeline\] stage
    \[Pipeline\] { (Print version)
    \[Pipeline \] sh
    + echo 'version: 1.0.0'
    version: 1.0.0
    + echo 'environment: dev'
    environment: dev
    \[Pipeline\] }
    \[Pipeline\] // stage

[^89]: Jenkins
    Q Search (CTRL+K)
    1 2 admin v C log out
    Dashboard > Manage Jenkins > Plugins
    Plugins
    Q rebuild
    Install
    C
    Updates
    Install
    Name !
    Released
    Available plugins
    Rebuilder 330.v645b_7df10e2a_
    Miscellaneous
    2 mo 16 days ago
    3 Installed plugins
    This plugin is for rebuilding a job using the same parameters.

[^90]: C
    A Not secure 52.91.250.151:8080/job/catalogue-deploy/4/console
    Dashboard > catalogue-deploy > #4
    + LU LEI1 810171
    + terraform init --backend-config=dev/backend. of -reconfigure
    \[Oma \[1mInitializing the backend. . .\[0m
    \[Oma \[ 32m
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.\[0m
    \[Om \[ 1mInitializing modules. . .0\[0m
    Downloading registry. terraform. io/terraform-aws-modules/ec2-instance/aws 5.6.0 for catalogue...
    - catalogue in . terraform/modules/catalogue

