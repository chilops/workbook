---
title: 42Day_Jenkins
uuid: 9b72e92c-32ae-11ef-9144-ceb251bdbe82
version: 819
created: '2024-06-25T10:21:38+05:30'
tags:
  - jenkins
---

# <mark style="background-color:#f8914d;">**Jenkins -CICD**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Continuous integration tool

\

Jenkins instance - with 20GB & t3.small config

![d1d13da5-21e7-475b-a692-161fb269fa10.png|1132](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/d1d13da5-21e7-475b-a692-161fb269fa10.png) [^1]

\

<mark>**Installing Jenkins:**</mark>

Search for Jenkins website 

![a80b8869-739a-434a-9165-0aa2e4de8777.png|1182.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a80b8869-739a-434a-9165-0aa2e4de8777.png) [^2]

\

adding Jenkins repo

```
sudo wget -0 /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

![110b8548-fcb0-4c70-aa91-730b35ec7f0b.png|1141.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/110b8548-fcb0-4c70-aa91-730b35ec7f0b.png) [^3]

\

```
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

![e9fbf588-f91d-43bc-95bd-1ebc4f110ee8.png|1157.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/e9fbf588-f91d-43bc-95bd-1ebc4f110ee8.png) [^4]

\

Jenkins developed using java.. so java should be installed.

```
sudo su 
yum install fontconfig java-17-openjdk -y
yum install jenkins -y
```

![18b56838-f52a-4dce-ae82-89bcc03d04b5.png|1156.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/18b56838-f52a-4dce-ae82-89bcc03d04b5.png) [^5]![bee27aec-9c27-4a49-9ccf-43697f638ab2.png|1155.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/bee27aec-9c27-4a49-9ccf-43697f638ab2.png) [^6]

\

```
systemctl start Jenkins
systemctl status Jenkins
systemctl enable jenkins
```

![61dbd930-1f64-4c4d-b9ba-fbc012235f5b.png|1173.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/61dbd930-1f64-4c4d-b9ba-fbc012235f5b.png) [^7]

![74c4378e-49d7-4c56-8f9e-1ef7c9d8cd18.png|1174.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/74c4378e-49d7-4c56-8f9e-1ef7c9d8cd18.png) [^8]

 

with server IP and port 8080 It will open in web browser, and initial password will be under below path

```
18.232.76.199:8080
```

![cd2c5423-b6e1-4c50-96bb-0638aee05333.png|1033.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/cd2c5423-b6e1-4c50-96bb-0638aee05333.png) [^9]

\

Install suggested plugins (all default required plugins will be installed)

![a3cf3519-76b4-43ec-85ae-84be76eeace5.png|1118.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a3cf3519-76b4-43ec-85ae-84be76eeace5.png) [^10]

![54fef40c-383d-42cf-9d54-7b15982235ce.png|1013.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/54fef40c-383d-42cf-9d54-7b15982235ce.png) [^11]

\

user name & password initial setup

![f387781f-bdf6-4097-ba62-f03e2c88a596.png|905.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/f387781f-bdf6-4097-ba62-f03e2c88a596.png) [^12]

\

![0b4e607d-7d5b-45d9-b079-3a09a4d9975f.png|1050.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/0b4e607d-7d5b-45d9-b079-3a09a4d9975f.png) [^13]

![2d6f660c-248d-4101-908a-b0f885fc3e1e.png|1051](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/2d6f660c-248d-4101-908a-b0f885fc3e1e.png) [^14]

\

This is Jenkins interface

![c67c7012-21fa-4bbd-b745-0b9430e536e5.png|1111.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/c67c7012-21fa-4bbd-b745-0b9430e536e5.png) [^15]

\

# <mark style="background-color:#f8914d;">**Free Style - Its nothing but everything you do it in UI**<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#f8d616;">**( No one using freestyle now)**<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"collapsed":true} -->

<mark>Anything we can in Jenkins are Job (job is nothing but it has some work to do). Free style we can do it in UI and we don't know who made the changes and its very difficult to restore back to normal stage. Because of this we are not using freestyle now a days everyone using pipeline.</mark>

\

creating a pipeline - free style

![05473cff-7c2c-46ac-ad8c-348b8cf695fb.png|892.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/05473cff-7c2c-46ac-ad8c-348b8cf695fb.png) [^16]

![fa652a75-0ba0-4e42-ab55-a1b07a8c5595.png|917.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/fa652a75-0ba0-4e42-ab55-a1b07a8c5595.png) [^17]

\

We are informing Jenkins what to do

![3952b065-693e-4853-9fcf-79cdaf137446.png|842](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/3952b065-693e-4853-9fcf-79cdaf137446.png) [^18]

![1746aad3-954f-4506-8b04-7156aaf49ff8.png|1098.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/1746aad3-954f-4506-8b04-7156aaf49ff8.png) [^19]

<mark>Now run build now</mark>

![83761e39-2541-40c7-aa33-92c0549d0720.png|863](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/83761e39-2541-40c7-aa33-92c0549d0720.png) [^20]

![1fe5b85a-a94e-4eb6-ad23-87d0c29f3cd5.png|843](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/1fe5b85a-a94e-4eb6-ad23-87d0c29f3cd5.png) [^21]

![ecfaef3e-9bad-48f9-8ffa-253a31654ecd.png|969](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/ecfaef3e-9bad-48f9-8ffa-253a31654ecd.png) [^22]

\

# <mark style="background-color:#f8914d;">**Pipeline**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Now we need to understand pipelines.

\

![62231d1f-f111-4bc4-a18c-708d76996332.png|977.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/62231d1f-f111-4bc4-a18c-708d76996332.png) [^23]![78b33b21-2c11-4eef-9be1-68cc2f018774.png|1076.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/78b33b21-2c11-4eef-9be1-68cc2f018774.png) [^24]

![a36cc77b-59b9-4f5f-9ee9-b23c4f16686c.png|1070.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a36cc77b-59b9-4f5f-9ee9-b23c4f16686c.png) [^25]

\

<mark>Apply & save</mark>

\

![02c28a8e-8674-4c9b-9221-b186e8407219.png|1021.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/02c28a8e-8674-4c9b-9221-b186e8407219.png) [^26]

Now click on build now option.

![a26ba1f7-1977-4236-bef7-d7b20d8ce000.png|830](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a26ba1f7-1977-4236-bef7-d7b20d8ce000.png) [^27]

\

It is running now

![6b2522d4-2f15-40fc-849c-58a3421442ed.png|896](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6b2522d4-2f15-40fc-849c-58a3421442ed.png) [^28]

![6c285f4c-3382-4964-8d8f-806d24938d61.png|991](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6c285f4c-3382-4964-8d8f-806d24938d61.png) [^29]

\

These are stages, You can add any number of stages

![f0e2f8b1-c67b-4801-8630-6f82dd704aba.png|887](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/f0e2f8b1-c67b-4801-8630-6f82dd704aba.png) [^30]

\

To add stages

![05751e34-7357-42ac-a41a-3567bb4a4ee3.png|930](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/05751e34-7357-42ac-a41a-3567bb4a4ee3.png) [^31]

added two new stages

![9a4c6d9b-433f-4e35-8783-1ca0195fbbb7.png|1000.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/9a4c6d9b-433f-4e35-8783-1ca0195fbbb7.png) [^32]

\

Now build now again & check three stages

![](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/901af38a-89d8-48be-9295-7a533dbd5c2d.png) [^33]

# <mark style="background-color:#f8914d;">**Pipeline from SCM (Source Code Management tool) - our source is GIT (we call it as gitops)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Now creating a folder "learn-jenkins" and a files called <mark>Jenkinsfile</mark>

![540a728b-16e7-4e59-9cce-d1623688243b.png|1049](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/540a728b-16e7-4e59-9cce-d1623688243b.png) [^34]

\

Pipeline simple syntax (stages)

![f10a22cc-4882-4ce0-89eb-ede71885a13f.png|1090.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/f10a22cc-4882-4ce0-89eb-ede71885a13f.png) [^35]

\

Now i need to push to git. create a new repo

![a3c8736e-b420-480c-b456-dc051ef30b46.png|961.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a3c8736e-b420-480c-b456-dc051ef30b46.png) [^36]

\

```
cd learn-jenkins/
git init
git branch -M main
git remote add origin git@github.com: daws-76s/learn-jenkins.git
git add . ; git commit -m "jenkins"; git push origin main
```

\

![6246a22c-66f8-4f45-92e9-588f74b406e4.png|1080](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6246a22c-66f8-4f45-92e9-588f74b406e4.png) [^37]

\

we have Jenkins file in GITHUB

![e2f3e901-a93e-4579-bdea-415d11820783.png|1097.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/e2f3e901-a93e-4579-bdea-415d11820783.png) [^38]

\

<mark>Now copy Https link and configure in Jenkins</mark>

![10cc8afa-0a23-4081-837b-16c649969268.png|1061.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/10cc8afa-0a23-4081-837b-16c649969268.png) [^39]

Jenkins dashboard to configure and paste that url in SCM

![014f6ed8-41b8-4d78-9a1d-29d1654c6ce2.png|1090.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/014f6ed8-41b8-4d78-9a1d-29d1654c6ce2.png) [^40]

branch name

![5d57ac8c-30f3-4ad9-825d-68b93f286c8f.png|1078.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/5d57ac8c-30f3-4ad9-825d-68b93f286c8f.png) [^41]

\

build now

![](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6d67a24e-3670-4a71-a42d-ed005ecc0691.png) [^42]

\

it will checkout first and build

![0ba2e978-8969-4e03-9129-671bb1f96500.png|1045](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/0ba2e978-8969-4e03-9129-671bb1f96500.png) [^43]

![1bc25d0e-fd8b-4818-be2a-8dfdc068c27c.png|734](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/1bc25d0e-fd8b-4818-be2a-8dfdc068c27c.png) [^44]

![3455ccc4-83c7-4f7e-8d7d-89acc7c07047.png|1115.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/3455ccc4-83c7-4f7e-8d7d-89acc7c07047.png) [^45]

# <mark style="background-color:#f8914d;">**Agent - creation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

If you use single project then you can use Jenkins as master, If you have multiple projects and that needs to handle by Agent. Here agent is nothing but other server.

![268d5e16-043f-465a-9276-d467bbb552c5.png|868](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/268d5e16-043f-465a-9276-d467bbb552c5.png) [^46]

![6b0cab4e-5a2c-45e8-bcdb-3f5239c0c64e.png|1033.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6b0cab4e-5a2c-45e8-bcdb-3f5239c0c64e.png) [^47]

\

adding server as agent

![8bb83d01-eff9-4f9b-bfe6-53dbfa5e73f8.png|1092.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/8bb83d01-eff9-4f9b-bfe6-53dbfa5e73f8.png) [^48]

\

![c5d4deb7-ec92-4fb3-981b-970c432984f3.png|1123.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/c5d4deb7-ec92-4fb3-981b-970c432984f3.png) [^49]

![497048d5-24a9-4a56-90aa-b67fa4483511.png|931](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/497048d5-24a9-4a56-90aa-b67fa4483511.png) [^50]

\

\

![aa14d1ba-b115-42ff-9647-d4dc3d1d521e.png|1049.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/aa14d1ba-b115-42ff-9647-d4dc3d1d521e.png) [^51]

\

![94cbf3d0-74bf-4b1e-bb08-cbb6f37f5a55.png|930](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/94cbf3d0-74bf-4b1e-bb08-cbb6f37f5a55.png) [^52]

\

![3f1f5b29-40ab-4770-af68-58e1570712e8.png|937.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/3f1f5b29-40ab-4770-af68-58e1570712e8.png) [^53]

![a4f58e32-4c4b-4dc9-a839-020844ca135a.png|1019.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a4f58e32-4c4b-4dc9-a839-020844ca135a.png) [^54]

![6b5d6f5f-95ef-43eb-a8dd-948aed097cec.png|1085.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6b5d6f5f-95ef-43eb-a8dd-948aed097cec.png) [^55]

\

To work agent minimum software required is JAVA (Jenkins install in not required in agent, but java should be installed)

![cafca5b3-d9ca-4149-a1a3-d3754f833a71.png|803](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/cafca5b3-d9ca-4149-a1a3-d3754f833a71.png) [^56]

```
sudo su -
yum install fontconfig java-17-openjdk -y
```

![57a4daa0-3007-49f7-8de6-adf0c23a3e47.png|972.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/57a4daa0-3007-49f7-8de6-adf0c23a3e47.png) [^57]

\

We can install n no of agents, 1 for java projects, 1 for nodejs projects, 1 for python projects, 1 for roboshop, 1 for amazon, 1 for flipkart etc...

\

connected agent and online

![413b9bb3-a351-4cbd-a0da-6e09aa130910.png|980](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/413b9bb3-a351-4cbd-a0da-6e09aa130910.png) [^58]

![bafcce88-db5b-460f-b12f-2bdd8df14ba6.png|909](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/bafcce88-db5b-460f-b12f-2bdd8df14ba6.png) [^59]

\

# <mark style="background-color:#f8914d;">**Assigning a job to agent**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![f23c77b6-9d47-4988-a808-aab98d8ce70e.png|1078.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/f23c77b6-9d47-4988-a808-aab98d8ce70e.png) [^60]

\

![82e94224-0952-40e8-99ff-9b2e29d5865b.png|1074](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/82e94224-0952-40e8-99ff-9b2e29d5865b.png) [^61]

\

It running under Agent-1

![438c6073-33d6-4352-8a9d-441d217eae58.png|1006.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/438c6073-33d6-4352-8a9d-441d217eae58.png) [^62]

\

# <mark style="background-color:#f8914d;">**POST**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

post is nothing but post build, once build is completed what needs to done. If success post the success or if failure shares the failure report.

![9386f17a-ec85-4823-9fea-a021504bacd3.png|810](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/9386f17a-ec85-4823-9fea-a021504bacd3.png) [^63]

\

![e05ec2b4-1474-4003-8bb5-9cd28ef637f3.png|1098.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/e05ec2b4-1474-4003-8bb5-9cd28ef637f3.png) [^64]

---

# <mark style="background-color:#f8914d;">**Environment - selection**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

We can use this as variables - to run any shell scripts or to use URL's etc

![](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/3f99a877-c46e-4e6d-a393-4f57b2949066.png) [^65]

\

![5ef55aeb-9e19-4ed7-9bc3-580333de98ff.png|701](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/5ef55aeb-9e19-4ed7-9bc3-580333de98ff.png) [^66]

# <mark style="background-color:#f8914d;">**Options**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

it has options like timeout, sleep etc

![ddc79a7a-443f-4a27-ac66-8713caad15a7.png|580](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/ddc79a7a-443f-4a27-ac66-8713caad15a7.png) [^67]

![ade23e6c-aa4f-4611-b704-583258e91e08.png|757](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/ade23e6c-aa4f-4611-b704-583258e91e08.png) [^68]

\

pipeline run and it went timeout since its sleeps for 10 sec's

![d81357fb-ede1-4976-af43-efcd91779e13.png|825](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/d81357fb-ede1-4976-af43-efcd91779e13.png) [^69]

\

<mark>Disabled two concurrent builds.</mark>

There are times we don't need to run two builds at a time. like below

![eebe5d76-0154-4c71-84a9-3b1cd4fdf8c8.png|386](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/eebe5d76-0154-4c71-84a9-3b1cd4fdf8c8.png) [^70]

\

now we use below option

![b8bd8fe8-909f-40e7-aec7-025803a259e6.png|648](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/b8bd8fe8-909f-40e7-aec7-025803a259e6.png) [^71]

Now only one build is running and other is waiting/pending until previous build completes.

![6002cfb1-62c3-461b-bf33-c4babff55e77.png|285](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6002cfb1-62c3-461b-bf33-c4babff55e77.png) [^72]

\

---

# <mark style="background-color:#f8914d;">**Parameters**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

To any script or program generally we pass some parameters.

![581e0f71-b928-439a-aae9-f1107134db6f.png|939.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/581e0f71-b928-439a-aae9-f1107134db6f.png) [^73]

\

using parameters in stages

![ce86168b-eeca-44e0-bbfb-91174b929133.png|816](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/ce86168b-eeca-44e0-bbfb-91174b929133.png) [^74]

\

once you add parameters and run it for 1st time, Jenkins is not aware of parameters

\

Now 2nd time you will see parameters options.

![3e98651e-4ec1-495a-8815-db851858f569.png|525](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/3e98651e-4ec1-495a-8815-db851858f569.png) [^75]

\

![52c3c473-2ee7-4e8d-83da-24af05473027.png|1008.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/52c3c473-2ee7-4e8d-83da-24af05473027.png) [^76]

![99fb87bc-2f15-4804-b11d-68035762de4f.png|994.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/99fb87bc-2f15-4804-b11d-68035762de4f.png) [^77]

\

when build is running

![92508de6-e0f7-454d-9422-0c8afb48d2db.png|786](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/92508de6-e0f7-454d-9422-0c8afb48d2db.png) [^78]

---

# <mark style="background-color:#f8914d;">**Triggers - Webhook**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

till now we triggered this pipeline manually, we have options 

\

Webhook is nothing but a connection from one to another. This a event based information passing system.

![c1ece7e8-8c81-468a-89e4-3daca367a013.png|951.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/c1ece7e8-8c81-468a-89e4-3daca367a013.png) [^79]

<mark>Now creating a webhook in git</mark>

![6691146e-512b-4a77-a619-7d3a83fb59b1.png|1005.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/6691146e-512b-4a77-a619-7d3a83fb59b1.png) [^80]

![a08b47d4-b428-4dd0-9df2-326d4f02d21c.png|752](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/a08b47d4-b428-4dd0-9df2-326d4f02d21c.png) [^81]

![c430288c-e78a-4d5c-9fb8-d5f7cdbe796e.png|937](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/c430288c-e78a-4d5c-9fb8-d5f7cdbe796e.png) [^82]

\

its just sent a ping to check connection

![fed4d16f-226a-4af0-9da2-b087ee3d7893.png|973.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/fed4d16f-226a-4af0-9da2-b087ee3d7893.png) [^83]

\

<mark>Same in Jenkins also we need to add webhook.</mark>

![025ebe42-8d30-4ce9-b589-19a61407cdb8.png|995.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/025ebe42-8d30-4ce9-b589-19a61407cdb8.png) [^84]

\

<mark>Now try to push code to git to check if build is running auto</mark>

![7ca78886-7e0c-46cc-8e02-75cdae377590.png|1088.3333740234375](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/7ca78886-7e0c-46cc-8e02-75cdae377590.png) [^85]

\

Now its running auto

![4b78f962-d710-40d2-9d88-1fc63fd27e05.png|465](https://images.amplenote.com/9b72e92c-32ae-11ef-9144-ceb251bdbe82/4b78f962-d710-40d2-9d88-1fc63fd27e05.png) [^86]

\

# <mark style="background-color:#f8914d;">**POLL SCM**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

This is check periodically if any changes occurred in git. then it will run build automatically.

\

[^1]: Instances (1) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    Instance ID = i-00b6aa0a6666f2a51
    X
    Clear filters
    <
    1
    O
    Name
    A
    Instance ID
    Instance state \|Instance type v Status check .
    Alarm status
    Availab
    jenkins
    i-00b6aa0a6666f2a51
    Running Q Q
    t3.small
    View alarms +
    us-east

[^2]: C pkg.jenkins.io/redhat-stable/
    Jenkins
    co
    Blog Success Stories Contributor Spotlight Documentation . Plugins Community . Subprojects . Security
    Jenkins Redhat Packages
    To use this repository, run the following command:
    \[sudo wget -0 /etc/yum. repos.d/ jenkins. repo https://pkg. jenkins. io/redhat-stable/ jenkins. repo
    sudo rpm --import https://pkg. jenkins. io/redhat-stable/ jenkins. io-2023.key
    If you've previously imported the key from Jenkins, the rom - - import will fail because you already have a key. Please ignore that and move on.
    yum install fontconfig java-17-openjok
    yum install jenkins
    The rpm packages were signed using this key:
    pub
    rsa4096 2023-03-27 \[SC\] \[expires: 2026-03-26\]
    63667EE74BBA1FOA08A698725BA31057EF5975CA
    uid
    Jenkins Project
    sub
    rsa4096 2023-03-27 \[E\] \[expires: 2026-03-26\]
    You will need to explicitly install a supported Java runtime environment (JRE), either from your distribution (as described above) or another Java vendor (e.g., Adoptium).

[^3]: 18. 232. 76. 199 \| 172. 31. 35. 124 \| t3. small \| null
    \[ centos@ip-172-31-35-124 \~ \]$ sudo wget -0 /etc/yum. repos . d/jenkins. repo https: //pkg. jenkins . io/redhat-stable/jenkins . repo
    2024-01-31 02:21:42-- https: //pkg . jenkins . io/redhat-stable/jenkins . repo
    Resolving pkg. jenkins . io (pkg . jenkins . io) ... 146. 75.34.133, 204: 4e42: 78: : 645
    Connecting to pkg. jenkins . io (pkg. jenkins . io) \|146. 75. 34. 133\|: 443... connected.
    HTTP request sent, awaiting response. . . 200 OK
    Length: 85
    Saving to: '/etc/yum. repos . d/jenkins . repo'
    /etc/yum . repos . d/jenkins . repo
    100% \[
    85
    --.-KB/S
    in Os
    2024-01-31 02:21: 45 (5.05 MB/s) - '/etc/yum. repos . d/jenkins . repo' saved \[85/85\]
    18.232 . 76. 199 \| 172. 31. 35. 124 \| t3. small \| null
    centosdip-172-31-35-124

[^4]: 18 . 232. 76. 199 \| 172. 31. 35.124 \| t3. small \| null
    \[ centos@ip-172-31-35-124 \~ \]$ sudo rpm --import https: //pkg. jenkins . io/redhat-stable/jenkins . io-2023.key
    18. 232. 76. 199 \| 172. 31. 35. 124 \| t3. small \| null
    \[ centos@ip-172-31-35-124 \~ \] $

[^5]: 18 . 232. 76. 199 \| 172. 31. 35. 124 \| t3. small \| null
    \[ centos@ip-172-31-35-124 \~ \]$ sudo su
    18 . 232. 76. 199 \| 172. 31. 35.124 \| t3. small \| null
    \[ root@ip-172-31-35-124 /home/centos \]# yum install fontconfig java-17-openjak -y
    Centos Stream 8 - AppStream
    32 MB/S \| 27 MB
    00: 00

[^6]: 18 . 232 . 76. 199 \| 172. 31. 35.124 \| t3. small \| null
    \[ root@ip-172-31-35-124 /home/centos \]# yum install jenkins -y
    Last metadata expiration check: 0:00:40 ago on Wed 31 Jan 2024 02:22:35 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Installing :
    jenkins
    noarch
    2 . 426.3-1.1

[^7]: 18 . 232. 76. 199 \| 172. 31. 35.124 \| t3. small \| null
    \[ root@ip-172-31-35-124 /home/centos \]# systemctl start jenkins
    18 . 232. 76. 199 \| 172. 31. 35.124 \| t3. small \| null
    \[ root@ip-172-31-35-124 /home/centos \]# systemctl status jenkins
    jenkins . service - Jenkins Continuous Integration Server
    Loaded: loaded (/usr/lib/systemd/system/jenkins . service; disabled; vendor preset: disabled)
    Active: active (running) since Wed 2024-01-31 02:24:34 UTC; 6s ago
    Main PID: 5444 (java)
    Tasks: 43 (limit: 10627)
    369

[^8]: 18. 232 . 76. 199 \| 172. 31. 35. 124 \| t3. small \| null
    \[ root@ip-172-31-35-124 /home/centos \]# systemctl enable jenkins
    Created symlink /etc/systemd/system/multi-user . target . wants/jenkins . service - /usr/lib/systemd/system/jenkins . service.
    18 . 232 . 76. 199 \| 172. 31.35.124 \| t3. small \| null
    -31
    35-

[^9]: F
    A Not secure 18.232.76.199:8080/login?from=%2F
    Getting Started
    Unlock Jenkins
    To ensure Jenkins is securely set up by the administrator, a password has been written to
    the log (not sure where to find it?) and this file on the server:
    var/lib/jenkins/secrets/initialAdminPassword
    Please copy the password from either location and paste it below.
    Administrator password

[^10]: F
    C
    Not secure 18.232.76.199:8080
    Getting Started
    Customize Jenkins
    Plugins extend Jenkins with additional features to support many different needs.
    Install suggested
    Select plugins to
    plugins
    install
    Install plugins the Jenkins
    Select and install plugins most
    community finds most useful.
    suitable for your needs.

[^11]: A Not secure 18.232.76.199:8080
    Getting Started
    Getting Started
    " commons-text API
    Folders
    OWASP Markup
    Build Timeout
    Credentials Binding
    .. Pipeline: Supporting APIS
    Formatter
    "\* Plugin Utilities API
    "" Font Awesone API
    Timestamper
    Workspace Cleanup
    V Ant
    Gradle
    .\* Bootstrap 5 API
    " JQuery3 API
    .\* ECharts API
    Pipeline
    @ GitHub Branch Source
    Pipeline: GitHub Groofy
    Pipeline: Stage View
    .. Display URL API
    \*\* Checks API
    Libraries
    \* JUnit
    .. Matrix Project
    C Git
    SSH Build Agents
    Matrix Authorization
    PAM Authentication
    "\* Resource Disposer
    Strategy
    Workspace Cleanup
    Ant
    LDAP
    Email Extension
    Mailer
    .\* Durable Task
    .\* Pipeline: Nodes and Processes
    .\* Pipeline: SCM Step
    .\* Pipeline: Groovy
    .\* Pipeline: Job
    .\* Jakarta Activation API
    .\* Jakarta Mail API

[^12]: 18.232.76.199:8080
    Getting Started
    Create First Admin User
    Username
    admin
    Password
    . .......
    Confirm password
    ........
    Full name
    admin
    E-mail address
    admin@admin.com
    Jenkins 2.426.3
    Skip and continue as admin
    Save and Continue

[^13]: A Not secure 18.232.76.199:8080
    Getting Started
    Instance Configuration
    Jenkins URL:
    http://18.232.76.199:8080/
    The Jenkins URL is used to provide the root URL for absolute links to various Jenkins resources. That means this value is required for proper
    operation of many Jenkins features including email notifications, PR status updates, and the BUILD_URL environment variable provided to build
    steps.
    The proposed default value shown is not saved yet and is generated from the current request, if possible. The best practice is to set this value to
    the URL that users are expected to use. This will avoid confusion when sharing of viewing links.

[^14]: Not secure 18.232.76.199:8080
    Getting Started
    Jenkins is ready!
    Your Jenkins setup is complete.
    Start using Jenkins

[^15]: A Not secure 18.232.76.199:8080
    Jenkins
    Q Search (CTRL+K)
    Q 1 2 admin C log out
    Dashboard
    New Item
    Add description
    Welcome to Jenkins!
    28 People
    Build History
    This page is where your Jenkins jobs will be displayed. To get started, you can set up distributed
    builds or start building a software project.
    03 Manage Jenkins
    Start building your software project
    My Views
    Create a job
    +
    Build Queue
    Set up a distributed build
    No builds in the queue.
    Set up an agent
    Build Executor Status
    1 Idle
    Configure a cloud
    2 Idle
    Learn more about distributed builds

[^16]: Jenkins
    Q Search (CTRL+K)
    Dashboard > All >
    Enter an item name
    hello-world-freestyle
    Required field
    Freestyle prinject
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
    Multibranch Pipeline
    Creates a set of Pipeline projects according to detected branches in one SCM repository.
    Organization Folder
    Creates a set of multibranch project subfolders by scanning for repositories.
    OK

[^17]: Jenkins
    Q Search (CTRL+K)
    9 1 9 adm
    Dashboard > hello-world-freestyle > Configuration
    Configure
    General
    Enabled
    203 General
    Description
    Source Code Management
    This is freestyle job
    Build Triggers
    Build Environment
    Plain text Preview
    Build Steps
    Discard old builds ?
    Post-build Actions
    GitHub project
    This project is parameterized ?
    Throttle builds ?
    Execute concurrent builds if necessary ?
    Advanced v
    Source Code Management
    None
    Git ?

[^18]: Build Steps
    Add build step
    Filter
    Execute Windows batch command
    Execute shell
    Invoke Ant
    Invoke Gradle script
    Invoke top-level Maven targets
    Run with timeout
    Set build status to "pending" on GitHub commit

[^19]: Build Steps
    Execute shell ?
    X
    Command
    See the list of available environment variables
    echo "Hello world"
    Advanced v
    Add build step v
    Post-build Actions
    Add post-build action v
    Save
    Apply

[^20]: Jenkins
    Dashboard > hello-world-freestyle
    Status
    hello-world-freestyle
    </> Changes
    This is freestyle job
    Workspac Build scheduled
    Build Now
    Configure
    Permalinks
    Delete Project
    Rename
    Build History
    trend v
    No builds
    5.) Atom feed for all ). Atom feed for failures

[^21]: Dashboard > hello-world-freestyle >
    Status
    hello-world-freestyle
    </> Changes
    This is freestyle job
    Workspace
    Build Now
    Configure
    Permalinks
    Delete Project
    Rename
    O-
    Build History
    trend v
    Q Filter builds..
    Jan 31, 2024 2:28 AM
    5.) Atom feed for all all Atom feed for failures

[^22]: Jenkins
    Dashboard > hello-world-freestyle > #1 > Console Output
    Status
    Console Output
    </> Changes
    Started by user admin
    Console Output
    Running as SYSTEM
    Building in workspace /var/lib/jenkins/workspace/hello-world-freestyle
    View as plain text
    \[hello-world-freestyle\] $ /bin/sh -xe /tmp/jenkins3040202834029840639.sh
    + echo "Hello World"
    Edit Build Information
    Hello World
    Finished: SUCCESS
    Delete build '#1'

[^23]: Jenkins
    Q Search (CTRL+K)
    Dashboard > All >
    Enter an item name
    hello-pipeline
    . Required field
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
    Multibranch Pipeline
    Creates a set of Pipeline projects according to detected branches in one SCM repository.
    Organization Folder
    Creates a set of multibranch project subfolders by scanning for repositories.
    f you want to create a new item from other existing, you can use this option:
    OK

[^24]: Dashboard > hello-pipeline > Configuration
    Configure
    General
    Enabled
    203 General
    Description
    Advanced Project Options
    This is pipeline project
    Pipeline
    Plain text Preview

[^25]: Dashboard > hello-pipeline > Configuration
    Trigger builds remotely (e.g., from scripts) ?
    Configure
    03 General
    Advanced Project Options
    Advanced Project Options
    Advanced v
    Pipeline
    Pipeline
    Definition
    Pipeline script
    Script ?
    1
    try sample Pipeline.. v
    try sample Pipeline.
    Hello World
    GitHub + Maven
    Scripted Pipeline
    Use Groovy Sandbox ?
    Pipeline Syntax
    Save
    Apply

[^26]: Pipeline
    Definition
    Pipeline script
    Script ?
    1 \* pipeline {
    agent any
    Hello World
    v
    IN
    stages {
    stage( 'Hello') <
    6
    steps {
    7
    echo "Hello World"
    12
    Use Groovy Sandbox ?
    Pipeline Syntax
    Save
    Apply

[^27]: Jenkins
    Dashboard > hello-pipeline >
    Status
    hello-pipeline
    </> Changes Build scheduled
    This is pipeline project
    Build Now
    Configure
    Delete Pipeline
    Stage View
    O Full Stage View
    No data available. This Pipeline has not yet run.
    Rename
    Pipeline Syntax
    Permalinks
    K
    y
    Build History
    trend v

[^28]: Hello
    Rename
    Average stage times:
    217ms
    Pipeline Syntax
    (Average full run time: -3s)
    #1
    Jan 31
    No
    217ms
    Build History
    trend v
    08:01
    Changes
    Q Filter builds...
    Permalinks
    Jan 31 2024, 2:31 AM
    .) Atom feed for all all Atom feed for failures

[^29]: Jenkins
    Dashboard > hello-pipeline > #1
    Status
    Console Output
    </> Changes
    Started by user admin
    Console Output
    \[Pipeline\] Start of Pipeline
    \[Pipeline\] node
    View as plain text
    Running on Jenkins in /var/lib/jenkins/workspace/hello-pipeline
    \[Pipeline\] {
    Edit Build Information
    \[Pipeline\] stage
    \[Pipeline\] { (Hello)
    Delete build '#1'
    \[Pipeline\] echo
    Hello world
    Restart from Stage
    \[Pipeline\] }
    \[Pipeline\] // stage
    Replay
    \[Pipeline \] }
    \[Pipeline\] // node
    Pipeline Steps
    \[Pipeline\] End of Pipeline
    Finished: SUCCESS
    Workspaces

[^30]: Dashboard > hello-pipeline >
    Status
    hello-pipeline
    </> Changes
    This is pipeline project
    Build Now
    Configure
    Delete Pipeline
    Stage View
    O Full Stage View
    Hello
    Rename
    Average stage times:
    217ms
    ? Pipeline Syntax
    (Average full run time: \~3s)
    Jan 31
    NO
    217ms
    Build History
    trend
    08:01
    Changes
    Q Filter builds..
    Permalinks
    Jan 31, 2024 2:31 AM
    T
    5.) Atom feed for all \\\\ Atom feed for failures
    Last build (#1). 13 sec ago
    . Last stable build (#1). 13 sec ago
    . Last successful build (#1). 13 sec ago
    Last completed build (#1). 13 sec ago

[^31]: Jenkins
    Dashboard > hello-pipeline >
    Status
    hello-pipeline
    </> Changes
    This is pipeline project
    Build Now
    Configure
    Delete Pipeline
    Stage View
    Q Full Stage View
    Hello
    Rename
    Average stage times:
    217ms
    ? Pipeline Syntax
    (Average full run time: \~3s)
    $1
    Jan 31
    No
    217ms
    Build History
    trend v
    08:01
    Changes
    Q Filter builds.
    Permalinks
    Jan 31, 2024. 2:31 AM
    . Atom feed for all \\\\ Atom feed for failures
    . Last build (#1). 13 sec ago
    Last stable build (#1), 13 sec ago
    Last successful build (#1). 13 sec ago
    . Last completed build (#1). 13 sec ago

[^32]: Configure
    Advanced Project Options
    General
    Advanced v
    Advanced Project Options
    Pipeline
    Pipeline
    Definition
    Pipeline script
    V
    Script ?
    agent any
    4 -
    stages {
    5 -
    stage ( 'Hello' ) {
    6 -
    steps {
    echo "Hello World"
    8
    10 -
    stage ( 'Hi' ) (
    11 .
    steps {
    12
    echo "Hi.
    13
    14
    15 -
    stage( 'Hello' ) {
    16 -
    steps {
    17
    18
    echo . Good Morningd
    10
    Use Groovy Sandbox ?

[^33]: Jenkins
    Dashboard > hello-pipeline >
    Status
    X
    hello-pipeline
    </> Changes
    This is pipeline project
    Build Now
    Configure
    Delete Pipeline
    Stage View
    O Full Stage View
    Success
    Hello
    HI
    Good Morning
    Rename
    Average stage times:
    180ms
    130ms
    thi Logs
    ?
    Pipeline Syntax
    (Average full run time: \~2s)
    Jan 31
    No
    130ms
    115ms
    Build History
    trend v
    08:02
    Changes
    Q Filter builds.
    Jan 31
    No
    Changes
    Jan 31, 2024. 2:32 AM
    08:02
    Jan 31, 2024, 2:32 AM
    On
    Jan 31 2024 2:31 AM
    Jan 31
    No
    217ms
    08:01
    Changes
    5.) Atom feed for all 5\\\\ Atom feed for failures
    Permalinks
    Last build (#2), 37 sec ago

[^34]: File Edit Selection View Go
    repos
    EXPLORER
    main.tf ... \\02-sg
    ! main-tf.yaml
    !
    varia
    V REPOS
    learn-jenkins > Jenkinsfile
    > .github
    1
    > ansible
    > concepts
    > learn-git
    learn-jenkins
    Jenkinsfile

[^35]: EXPLORER
    main.tf .. \\02-sg
    ! main-tf.yaml
    ! variables-dev.yaml
    REPOS
    learn-jenkins > Jenkinsfile
    > .github
    pipeline {
    ansible
    2
    agent any
    3
    >
    concepts
    4
    stages {
    > learn-git
    5
    stage( ' Build' ) {
    learn-jenkins
    6
    steps {
    Jenkinsfile
    7
    echo 'Building. .'
    > notes
    8
    > roboshop-ansible
    9
    > roboshop-ansible-roles
    10
    stage( ' Test' ) {
    11
    > roboshop-ansible-roles-tf
    steps {
    12
    echo 'Testing. .'
    > roboshop-documentation
    13
    LY
    > roboshop-infra-dev
    14
    H
    > roboshop-shell
    15
    stage ( ' Deploy' ) {
    > roboshop-terraform
    16
    steps {
    > shell-script
    17
    echo 'Deploying. ...'
    18
    > terraform
    19
    > terraform-aws-security-group
    20
    > terraform-aws-vpc
    21

[^36]: Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    daws-76s -
    learn-jenkins
    learn-jenkins is available.
    Great repository names are short and memorable. Need inspiration? How about vigilant-meme ?
    Description (optional)
    O
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    0 8
    Private
    You choose who can see and commit to this repository.

[^37]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos
    $ cd learn-jenkins/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/learn-jenkins
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/learn-jenkins/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/learn-jenkins (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/learn-jenkins (main)
    $ git remote add origin git@github. com: daws-76s/learn-jenkins . git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/learn-jenkins (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main (root-commit) ec6c280\] jenkins
    1 file changed, 21 insertions (+)
    create mode 100644 Jenkinsfile
    Enumeratiog objects: 3, done.
    Counting objects: 100% (3/3), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 314 bytes \| 104.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    To github . com: daws-76s/learn-jenkins . git
    \[new branch\]
    main -> main

[^38]: E
    daws-76s / learn-jenkins
    Q Type to search
    <> Code
    Issues
    87 Pull requests
    Actions Projects D Wiki
    @ Security Insights
    83 Settings
    Files
    learn-jenkins / Jenkinsfile 9
    & main
    +
    Q
    joindevopscloud jenkins
    Q Go to file
    t
    Code
    Blame 21 lines (20 loc) . 357 Bytes
    Jenkinsfile
    pipeline {
    N
    agent any
    w
    stages {
    I
    stage( ' Build' ) {
    steps {
    echo 'Building. .'

[^39]: learn-jenkins Public
    & Edit Pins
    Watch 0
    & main
    8 1 Branch 0 Tags
    Q Go to file
    t
    Add file
    <> Code
    Local
    Codespaces
    joindevopscloud jenkins
    D- Clone
    ?
    Jenkinsfile
    jenkins
    HTTPS
    SSH
    GitHub CLI
    DO README
    https://github. com/daws-76s/learn-jenkins.git
    Clone using the web URL.
    m

[^40]: C
    A Not secure 18.232.76.199:8080/job/hello-pipeline/configure
    Dashboard > hello-pipeline > Configuration
    Pipeline script from SCM
    Configure
    SCM ?
    103 General
    Git
    Advanced Project Options
    Repositories ?
    Pipeline
    Repository URL ?
    https://github.com/daws-76s/learn-jenkins.git
    Credentials ?
    none -
    + Add
    Advanced v

[^41]: Branches to build ?
    Branch Specifier (blank for 'any") ?
    \*/main
    Add Branch

[^42]: Dashboard > hello-pipeline >
    Status
    </> Changes
    T
    Build Now
    03 Configure

[^43]: Dashboard > hello-pipeline >
    Status
    hello-pipeline
    </> Changes
    This is pipeline project
    Build Now
    Configure
    Delete Pipeline
    Stage View
    O Full Stage View
    Declarative:
    Build
    Test
    Deploy
    Rename
    Checkout SCMS
    ? Pipeline Syntax
    Average stage times:
    415ms
    156ms
    127ms
    79ms
    (Average full run time: \~5s)
    Build History
    trend v
    Jan 31
    No
    415ms
    156ms
    127ms
    79ms
    Changes
    06:08
    Q Filter builds...
    Jan 31, 2024, 2:38 AM
    Permalinks
    Jan 31, 2024, 2:32 AM
    . Last build (#3). 5 min 33 sec ago
    Jan 31 2024 2:32 AM
    . Last stable build (#3). 5 min 33 sec ago
    Jan 31, 2024, 2:31 AM
    . Last successful build (#3). 5 min 33 sec ago
    Last failed build (#2). 6 min 12 sec ago
    5. Atom feed for all .\\\\ Atom feed for failures
    . Last unsuccessful build (#2). 6 min 12 sec ago
    . Last completed build (#3). 5 min 33 sec ago

[^44]: Dashboard > hello-pipeline > #4
    E
    Status
    Build #4 (Jan 31, 2024, 2:38:18 AM)
    <> Changes
    Console Output
    Edit Build Information
    Started by user admin
    Revision: ec6c2803c6186355d7eddeadeef190419023aa6
    Delete build '#4'
    git
    Repository: https://github.com/daws-76s/learn-jenkins.git
    Git Build Data
    . refs/remotes/origin/main
    Restart from Stage

[^45]: Dashboard > hello-pipeline > #4
    Status
    Console Output
    </> Changes
    Started by user admin
    Console Output
    Obtained Jenkinsfile from git https://github.com/daws-76s/learn-jenkins.git
    \[Pipeline\] Start of Pipeline
    View as plain text
    \[Pipeline\] node
    Running on Jenkins in /var/lib/jenkins/workspace/hello-pipeline
    Edit Build Information
    \[Pipeline\] {
    \[Pipeline\] stage
    Delete build '#4'
    \[Pipeline\] { (Declarative: Checkout SCH)
    \[Pipeline\] checkout
    Git Build Data
    Selected Git installation does not exist. Using Default
    The recommended git tool is: NONE
    C Restart from Stage
    No credentials specified
    Cloning the remote Git repository
    Replay
    Cloning repository https://github.com/daws-76s/learn-jenkins.git
    > git init /var/lib/jenkins/workspace/hello-pipeline = timeout-10
    Pipeline Steps
    Fetching upstream changes from https://github.com/dans-76s/learn-jenkins.git
    > git --version # timeout=10
    Workspaces
    > git --version = 'git version 2.43.0'
    > git fetch --tags --force --progress -- https://github.com/daws-76s/learn-jenkins.git +refs/heads/":refs/remotes/origin/" = timeout=10
    Previous Build
    > git config remote. origin.url https://github.com/daws-76s/learn-jenkins.git = timeout-10
    > git config --add remote. origin.fetch +refs/heads/": refs/remotes/origin/" = timeout=10
    Avoid second fetch
    > git rev-parse refs/remotes/origin/main"{commit) = timeout-10
    Checking out Revision ecc2803c618655d7eddea@cef196419023as6 (refs/remotes/origin/main)
    > git config core. sparsecheckout # timeout=10
    > git checkout -f ec6c2803c618655d7eddeaBeef196419023aa6 = timeout-10
    Commit message: "jenkins"
    First time build. Skipping changelog.
    \[Pipeline\] }
    \[Pipeline\] // stage
    \[Pipeline\] withEnv

[^46]: 1 person --> 1 acre of agriculture
    I
    100 acres --> you need lot of resources
    owner --> employ resources --> distribute the work
    master --> slave
    master --> agent

[^47]: Instances (1) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    Instance ID = i-0926936987alf7609
    X
    Clear filters
    O
    Name _
    4
    Instance ID
    Instance state
    4
    Instance type
    Status check ,
    Alarm status
    Avail
    agent
    i-0926936987alf7609
    Running Q Q
    t3.small
    View alarms +
    us-ea

[^48]: Jenkins
    Q Search (CTRL+K)
    admin v C log out
    Dashboard > Manage Jenkins
    + New Item
    Manage Jenkins
    Q Search settings
    28 People
    Building on the built-in node can be a security issue. You should set up distributed builds. See the documentation.
    Set up agent
    Set up cloud
    Dismiss
    Build History
    03 Manage Jenkins.
    System Configuration
    My Views
    System
    Tools
    Plugins
    Nodes
    Configure global settings and paths.
    Add, remove, disable or enable plugins
    Add, remove, control and monitor the
    Build Queue
    Configure tools, their locations and
    automatic installers.
    that can extend the functionality of
    various nodes that Jenkins runs jobs on.
    No builds in the queue.
    Jenkins.
    Clouds
    Build Executor Status
    Add, remove, and configure cloud

[^49]: Dashboard > Manage Jenkins > Nodes >
    + New Node
    Node Monitoring
    C
    Nodes
    Nodes
    Clouds
    Free Temp Space
    Response Time
    S
    Name !
    Architecture
    Clock Difference
    Free Disk Space
    Free Swap Space
    In sync
    16.36 GB
    1 0 B
    16.36 GB
    Oms
    Build Queue
    O
    Built-In Node
    Linux (amd64)
    17 min
    17 min
    No builds in the queue.
    Data obtained
    17 min
    17 min
    17 min
    17 min
    Build Executor Status
    1 Idle
    2 Idle

[^50]: Dashboard > Manage Jenkins > Nodes > New node
    New node
    Node name
    AGENT-1
    Type
    O
    Permanent Agent
    Adds a plain, permanent agent to Jenkins. This is called "permanent" because Jenkins doesn't provide higher level of integration with these agents,
    such as dynamic provisioning. Select this type if no other agent types apply - for example such as when you are adding a physical computer, virtual
    machines managed outside Jenkins, etc.
    Create

[^51]: Description ?
    Plain text Preview
    Number of executors ?
    3
    Remote root directory ?
    /var/jenkins-agent
    An agent needs to have a directory dedicated to Jenkins. Specify the path to this directory on the agent. It is best to use an absolute path, such as /var/jenkins or c: \\jenkins . This should be a path local to the agent machine. There is no need for
    this path to be visible from the controller.
    Agents do not maintain important data: all job configurations, build logs and artifacts are stored on the controller, so it would be possible to use a temporary directory as the agent root directory.
    However, by giving an agent a directory that is not deleted after a machine reboot for example, the agent can cache data such as tool installations, or build workspaces. This prevents unnecessary downloading of tools, or checking out source code
    again when builds start to run on this agent again after a reboot.
    If you use a relative path, such as ./ jenkins-agent , the path will be relative to the working directory provided by the Launch method .
    . For launchers where Jenkins controls starting the agent process. such as SSH. the current working directory will typically be consistent e.g. the user's home directory.
    For launchers where Jenkins has no control over starting the agent process, such as inbound agents launched from the command line, the current working directory may change between launches of the agent and use of a relative path may
    prove problematic.
    The principal issue encountered when using relative paths with inbound launchers is the proliferation of stale workspaces and tool installation on the agent machine. This can cause disk space issues.

[^52]: 1. master asking agent to work
    2. employee coming to master and asking for work

[^53]: Usage ?
    Use this node as much as possible
    Launch method ?
    Launch agent by connecting it to the controller
    Launch agent by connecting it to the controller
    Launch agents via SSH

[^54]: Launch method ?
    Launch agents via SSH
    Host ?
    172.31.41.46
    Credentials ?
    ssh-auth
    + Add

[^55]: Host Key Verification Strategy ?
    Non verifying Verification Strategy
    Advanced v
    Availability ?
    Keep this agent online as much as possible
    ?
    Node Properties
    Disable deferred wipeout on this node ?
    O
    Environment variables
    Tool Locations
    Save

[^56]: java.io. TOException: Java not found on hudson. slaves.SlaveComputer@419c3d56. Install Java 8 or Java 11 on the Agent.
    at hudson. plugins. sshslaves . JavaVersionChecker . resolveJava(JavaVersionChecker . java:83)
    at hudson. plugins. sshslaves . SSHLauncher . lambda$launch$0 (SSHLauncher . java:460)
    at java. base/java. util. concurrent. FutureTask. run(FutureTask. java: 264)
    at java. base/java. util. concurrent. ThreadPoolExecutor . runworker (ThreadPoolExecutor . java: 1136)
    at java. base/java.util. concurrent. ThreadPoolExecutor$Worker . run(ThreadPoolExecutor. java:635)
    at java.base/java. lang. Thread. run(Thread. java:833)
    \[01/31/24 02:46:49\] Launch failed - cleaning up connection
    \[01/31/24 02:46:49\] \[SSH\] Connection closed.

[^57]: 54 . 87. 175. 131 \| 172. 31 . 41. 46 \| t3. small \| null
    centos@ip-172-31-41-46 \~ \]$ sudo su
    54. 87. 175. 131 \| 172. 31. 41.46 \| t3. small \| null
    \[ root@ip-172-31-41-46 \~ \]# yum install fontconfig java-17-openjak -y
    Centos Stream 8 - AppStream
    28 MB/S \| 27 MB

[^58]: Jenkins
    Dashboard > Nodes > AGENT-1 > Log
    Status
    Agent successfully connected and online
    The Agent is connected, disconnect it before to try to connect it again.
    Delete Agent
    Configure
    Build History
    / Load Statistics
    - Script Console
    Log

[^59]: 54 . 87. 175. 131 \| 172 . 31 . 41. 46 \| t3. small \| null
    \[ centos@ip-172-31-41-46 \~ \]$ pwd
    /home/centos
    54 . 87. 175. 131 \| 172 . 31 . 41. 46 \| t3. small \| null
    \[ centos@ip-172-31-41-46 \~ \]$ 1s -1
    I
    total 0
    drwx------ 3 centos centos 42 Jan 31 02:50 jenkins-agent
    54 . 87. 175. 131 \| 172 . 31 . 41. 46 \| t3. small \| null
    \[ centos@ip-172-31-41-46 \~ \]$

[^60]: V REPOS
    learn-jenkins > Jenkinsfile
    > .github
    1
    pipeline {
    N
    > ansible
    agent {
    W
    node k
    > concepts
    4
    label 'AGENT-1'
    > learn-git
    > learn-jenkins
    6
    > notes
    7
    > roboshop-ansible
    8
    stages {
    > roboshop-ansible-roles
    9
    stage( ' Build' ) {
    > roboshop-ansible-roles-tf
    10
    steps {
    11
    echo 'Building..'
    > roboshop-documentation
    12
    > roboshop-infra-dev
    13
    > roboshop-shell
    14
    stage( ' Test' ) {
    > roboshop-terraform
    15
    steps {
    > shell-script
    16
    echo 'Testing..'
    > terraform
    17
    18
    > terraform-aws-security-group
    19
    stage( ' Deploy' ) {
    > terraform-aws-vpc
    20
    steps {
    > terraform-modules
    21
    echo 'Deploying. ...'
    > terraform-multi-env
    22
    > terraform-provisioners
    23
    > OUTLINE
    24
    25
    TIMELINE

[^61]: Jenkins
    Dashboard > hello-pipeline
    Status
    hello-pipeline
    <> Changes
    This is pipeline project
    Build Now
    3 Configure
    Delete Pipeline
    Stage View
    O Full Stage View
    Declarative:
    Build
    Test
    Deploy
    Rename
    Checkout SCM
    ?
    Pipeline Syntax
    Average stage times:
    1s
    156ms
    127ms
    79ms
    (Average full run time: \~5s)
    Build History
    trend v
    Jan 31
    No
    1s
    08-32
    Changes
    Q Filter builds.
    Jan 31 2024 2:52 AM
    Jan 31
    No
    415ms
    156ms
    79ms
    06:08
    Changes
    Jan 31 2024 2:38 AM
    Jan 31, 2024. 2:32 AM
    Jan 31, 2024, 2:32 AM
    Permalinks

[^62]: Dashboard > hello-pipeline > #5
    Status
    Console Output
    <> Changes
    Started by user admin
    Console Output
    Obtained Jenkinsfile from git https://github.com/daws-76s/learn-jenkins .git
    \[Pipeline\] Start of Pipeline
    View as plain text
    \[Pipeline\] node
    Running on AGENT-1 in /home/centos/jenkins-agent/workspace/hello-pipeline
    Edit Build Information
    (Pipeline)
    \[Pipeline \] stage
    Git Build Data
    Pipeline\] { (Declarative: Checkout
    (Pipeline
    heckout
    / Thread Dump
    Selected Git installation does not exist. Using Default
    The recommended git tool is: NONE
    \|1 Pause/resume
    No credentials specified
    Cloning the remote Git repository
    Replay
    Cloning repository https://github.com/daws-76s/ learn-jenkins.git
    > git init /home/centos/jenkins-agent/workspace/hello-pipeline # timeout-10
    Pipeline Steps
    Fetching upstream changes from https://github.com/daws-76s/learn-jenkins.git
    > git --version # timeout=10

[^63]: learn-jenkins > Jenkinsfile
    7
    / / build
    8
    stages {
    9
    stage( ' Build' ) {
    10
    steps {
    11
    echo 'Building. .'
    12
    13
    14
    stage( ' Test' ) {
    15
    steps {
    16
    echo 'Testing. .'
    17
    18
    19
    stage ( ' Deploy' ) {
    20
    steps {
    21
    echo 'Deploying. ...'
    22
    23
    24
    25
    / / post build
    26
    post {
    27
    always {
    28
    echo 'I will always say Hello again! '
    29
    30
    31

[^64]: / / post build
    post {
    always {
    echo 'I will always say Hello again! '
    failure {
    echo 'this runs when pipeline is failed, used generally to send some alerts'
    success{
    echo 'I will say Hello when pipeline is success

[^65]: environment {
    GREETING = 'Hello Jenkins'
    / / build

[^66]: 22
    stage( 'Deploy' ) {
    23
    steps {
    24
    sh
    25
    echo "Here I wrote shell script"
    26
    echo "$GREETING"
    27
    28
    29
    30

[^67]: environment
    GREETING
    = 'Hello Jenkins'
    options {
    timeout(time: 1, unit: 'SECONDS' )
    / / build
    stages {

[^68]: stage( ' Deploy' ) {
    steps {
    sh
    echo "Here I wrote shell script"
    echo "$GREETING'
    sleep 10

[^69]: \[Pipeline \] End of Pipeline
    Timeout has been exceeded
    org. jenkinsci. plugins. workflow. actions. ErrorAction$ErrorId: 2f9550c4-77c5-4fc8-b9f7-6b8c69f8462f
    Finished: ABORTED
    R

[^70]: Build History
    trend v
    Q Filter builds...
    X =13
    Jan 31 2024, 3:09 AM
    X #12
    Jan 31 2024 3:09 AM
    X

[^71]: V
    environment {
    8
    GREETING
    = 'Hello Jenkins'
    9
    10
    options {
    11
    timeout (time: 1, unit: ' HOURS' )
    12
    disableConcurrentBuilds ()
    13

[^72]: Build Now
    3 Configure
    Delete Pipeline
    St
    Q Full Stage View
    Rename
    Pipeline Syntax
    Build History
    trend v
    Q Filter builds...
    #15
    X
    - \| (pending-Build #14 is already in progress (ETA: 5.4 sec\]\]
    Jan 31, 2024. 3:10 AM

[^73]: 14
    parameters {
    15
    string(name: 'PERSON' , defaultValue: 'Mr Jenkins', description: 'Who should I say
    16
    17
    text (name: 'BIOGRAPHY' , defaultValue: "', description: 'Enter some information abou
    18
    19
    booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value' )
    20
    21
    choice (name: 'CHOICE' , choices: \['One' , 'Two', 'Three'\], description: 'Pick someth:
    22
    23
    password ( name: ' PASSWORD' , defaultValue: 'SECRET' , description: 'Enter a password'
    24

[^74]: 46
    stage( ' check params' ) {
    47
    steps{
    48
    sh
    49
    echo "Hello ${params . PERSON}"
    50
    51
    echo "Biography: ${params . BIOGRAPHY}"
    52
    53
    echo "Toggle: ${params . TOGGLE}"
    54
    55
    echo "Choice: ${params . CHOICE}"
    56
    57
    echo "Password: ${params . PASSWORD}
    58
    59
    60
    61

[^75]: Dashboard > hello-pipeline >
    Status
    hello-pipe
    </> Changes
    This is pipeline project
    Build with Parameters
    Configure
    Delete Pipeline
    Stage View
    O Full Stage View

[^76]: Pipeline hello-pipeline
    This build requires parameters:
    PERSON
    Who should I say hello to?
    Sivakumar
    BIOGRAPHY
    Enter some information about the person
    This is to test params
    TOGGLE
    Toggle this value

[^77]: CHOICE
    Pick something
    Two
    PASSWORD
    Enter a password
    ......
    Build
    Cancel

[^78]: Warning: A secret was passed to "sh" using Groovy String interpolation, which is insecure.
    Affected argument(s) used the following variable(:): \[PASSWORD\]
    See https://jenkins. io/redirect/groovy-string-interpolation for details.
    + echo 'Hello Sivakumar'
    Hello Sivakumar
    + echo "Biography: This is to test params'
    Biography: This is to test params
    echo 'Toggle: true"
    Toggle: true
    + echo 'Choice: Two"
    Choice: Two
    + echo 'Password: abc123'
    Password: abc123

[^79]: if developer pushes the code to git, then we want the pipeline to run automatically
    git --> Jenkins

[^80]: E
    daws-76s / learn-jenkins
    Q Type to search
    +
    87
    <> Code
    Issues 1 Pull requests Actions Projects Wiki @ Security \~ Insights
    503 Settings
    So3 General
    Webhooks
    Add webhook
    Access
    Webhooks allow external services to be notified when certain events happen. When the specified events happen, we'll send
    & Collaborators and teams
    a POST request to each of the URLs you provide. Learn more in our Webhooks Guide.
    Moderation options
    V
    We will also send events from this repository to your organization webhooks.
    Code and automation
    & Branches
    Tags
    Er Rules
    <
    Actions
    & Webhooks

[^81]: Payload URL \*
    http://18.232.76.199:8080/github-webhook/
    Content type
    application/json
    Secret

[^82]: Pushes
    O Registry packages
    Registry package published or updated in a
    Git push to a repository.
    repository.
    O Repositories
    O Releases
    Release created, edited, published, unpublished, or
    Repository created, deleted, archived, unarchived,
    publicized, privatized, edited, renamed, or
    deleted.
    transferred.
    O Repository advisories
    O Repository imports
    Repository advisory published or reported.
    Repository import succeeded, failed, or cancelled.
    O Repository vulnerability alerts
    Repository rulesets
    not alert (aka

[^83]: daws-76s / learn-jenkins
    Q Type to search
    +
    <> Code
    Issues 17 Pull requests Actions Projects Wiki @ Security \~ Insights
    $3 Settings
    General
    Webhooks / Manage webhook
    Access
    Settings
    Recent Deliveries
    & Collaborators and teams
    Moderation options
    9doefda0-bfe7-1lee-9fb7-cof57057c3f2 ping
    2024-01-31 08:49:59 ...
    Code and automation

[^84]: C
    A Not secure 18.232.76.199:8080/job/hello-pipeline/configure
    Dashboard > hello-pipeline > Configuration
    ciller d password
    Configure
    103 General
    Plain text Preview
    Advanced Project Options
    Add Parameter
    Pipeline
    Throttle builds ?
    Build Triggers
    O
    Build after other projects are built ?
    O
    Build periodically ?
    GitHub hook trigger for GITScm polling ?
    When Jenkins receives a GitHub push hook GitHub Plugin checks to see whether the hook came from a GitHub repository which matches the Git repository defined in SCM/Git section of this job. If
    they match and this option is enabled, GitHub Plugin triggers a one-time polling on GITScm. When GITScm polls GitHub, it finds that there is a change and initiates a build. The last sentence
    describes the behavior of Git plugin. thus the polling and initiating the build is not a part of GitHub plugin
    (from GitHub plugin)
    Poll SCM ?
    Quiet period ?
    Trigger builds remotely (e.g. from scripts) ?
    Advanced P

[^85]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/learn-jenkins (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main ff51a3d\] jenkins
    1 file changed, 1 insertion(+), 1 deletion(-)
    Enumeratiog objects: 5, done.
    Counting objects: 100% (5/5), done.
    Delta compression using up to 8 threads

[^86]: #17
    Jan 31
    08:44
    Build History
    trend v
    16
    Q Filter builds...
    Jan 31
    05-43
    =18
    \|(pending-In the wiet period. Expires in 2.7 sec)
    T Permalin
    Jan 31 2024 3:14 AM

