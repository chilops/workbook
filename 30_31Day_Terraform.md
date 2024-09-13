---
title: 30_31Day_Terraform
uuid: 0d0d170a-1f0f-11ef-b323-2e97089a9920
version: 1035
created: '2024-05-31T11:01:37+05:30'
tags:
  - terraform
---

***Topics:***

1. <mark style="background-color:#f8d616;">VPC - Virtual private cloud creation with HA (High Availability)<!-- {"backgroundCycleColor":"25"} --></mark>

    1. <mark>Creating VPC</mark>

    1. <mark>Creating Internet gateway(IG) and assigning it to VPC</mark>

    1. <mark>Creating a subnet with HA(High Availability)</mark>

        1. <mark>creating AZ-1 public subnet AZ-2 public subnet</mark>

        1. <mark>Creating AZ-1 private subnet AZ-2 private subnet</mark>

        1. <mark>Creating AZ-1 database subnet AZ-2 database subnet</mark>

    1. <mark>Route table creation - 3 (public, private, database) & Assigning Internet gateway to public route table</mark>

        1. <mark>Public route table & associating with public subnets(1a, 1b)</mark>

        1. <mark>Assigning Internet gateway to public route table</mark>

        1. <mark>Private route table & associating with private subnets(1a, 1b)</mark>

        1. <mark>Database route table & associating with Database subnets(1a, 1b)</mark>

1. <mark style="background-color:#f8d616;">NAT Gateway - only for outgoing traffic<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"offset":1} -->

    1. <mark>Elastic IP creation</mark>

    1. <mark>NAT gateway creation</mark> 

    1. <mark>Adding NAT gateway to Private & Database route tables</mark>

1. <mark style="background-color:#f8d616;">VPC Peering<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"offset":2} -->

1. <mark style="background-color:#f8d616;">VPC creation using Terraform<!-- {"backgroundCycleColor":"25"} --></mark> 

\

   

\

\

\

\

# <mark style="background-color:#f8914d;">**VPC - Virtual private cloud creation with HA (High Availability)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

<mark>**Creating VPC**</mark>

![11aa20c1-c393-441c-8526-5b5155226498.png|963](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/11aa20c1-c393-441c-8526-5b5155226498.png) [^1]

![27c8d3b8-4e14-4b02-af27-176bdb42c4ce.png|971.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/27c8d3b8-4e14-4b02-af27-176bdb42c4ce.png) [^2]

\

<mark>**Creating Internet gateway(IG) and assigning it to VPC**</mark>

![dcaf1c5d-35e4-4863-8d5c-39ba35f1a0c3.png|933](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/dcaf1c5d-35e4-4863-8d5c-39ba35f1a0c3.png) [^3]

![b86043f9-1161-44a6-9ef4-129f83c0bfac.png|996.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/b86043f9-1161-44a6-9ef4-129f83c0bfac.png) [^4]

\

![72f17851-dd78-4c60-90f7-64d006f2b7f0.png|1058.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/72f17851-dd78-4c60-90f7-64d006f2b7f0.png) [^5]

\

![f0a378b7-8a24-4f4b-b98d-b4e50291ffcd.png|1089.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/f0a378b7-8a24-4f4b-b98d-b4e50291ffcd.png) [^6]

![a63335b9-a83d-4ac3-9c6a-b0e636e735d7.png|1050.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/a63335b9-a83d-4ac3-9c6a-b0e636e735d7.png) [^7]

\

<mark>**Creating a subnet with HA(High Availability)**</mark>

\

HA Setup

At least 2 AZ resources be there

\

<mark style="background-color:#eefdd7;">**AZ-1 public subnet AZ-2 public subnet**<!-- {"backgroundCycleColor":"4"} --></mark>

AZ-1 -- 10.0.1.0/24

AZ-2 -- 10.0.2.0/24

\

<mark style="background-color:#eefdd7;">**AZ-1 private subnet AZ-2 private subnet**<!-- {"backgroundCycleColor":"4"} --></mark>

AZ-1 -- 10.0.11.0/24

AZ-2 -- 10.0.12.0/24

\

<mark style="background-color:#eefdd7;">**AZ-1 database subnet AZ-2 database subnet**<!-- {"backgroundCycleColor":"4"} --></mark>

AZ-1 -- 10.0.21.0/24

AZ-2 -- 10.0.22.0/24

\

\

<mark>**creating AZ-1 public subnet AZ-2 public subnet**</mark>

![4fdf99d8-e8bf-4a68-99d8-08acf4958809.png|728](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/4fdf99d8-e8bf-4a68-99d8-08acf4958809.png) [^8]

![0bc4c420-1310-4420-83de-53e6094a3880.png|787](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/0bc4c420-1310-4420-83de-53e6094a3880.png) [^9]

![d8302eea-d32f-424b-b76c-f929458f0a01.png|956.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d8302eea-d32f-424b-b76c-f929458f0a01.png) [^10]

\

\

<mark>**Creating AZ-1 private subnet AZ-2 private subnet**</mark>

![ac7bf588-8d8f-4292-8751-89aecc2e3ee9.png|933.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/ac7bf588-8d8f-4292-8751-89aecc2e3ee9.png) [^11]

\

<mark>**Creating AZ-1 database subnet AZ-2 database subnet**</mark>

![2c843d4a-dbe8-4484-a415-6237eca8ecad.png|1012.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/2c843d4a-dbe8-4484-a415-6237eca8ecad.png) [^12]

\

\

<mark>**Route table creation - 3 (public, private, database) & Assigning Internet gateway to public route table**</mark>

\

<mark>**Public route table & associating with public subnets(1a, 1b)**</mark>

![ddd24adc-ef60-43f1-a16b-cf128bc30b9b.png|848](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/ddd24adc-ef60-43f1-a16b-cf128bc30b9b.png) [^13]

\

![0ff7ca32-7043-4c7b-ab4f-aeec7eda0818.png|960.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/0ff7ca32-7043-4c7b-ab4f-aeec7eda0818.png) [^14]

\

<mark>**Route table associating with public subnets(1a, 1b):**</mark>

![ef929544-2df9-4a18-9f01-3df1fba7131e.png|891.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/ef929544-2df9-4a18-9f01-3df1fba7131e.png) [^15]

![2308ca26-e19d-4f0d-a21e-14b45891f919.png|971.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/2308ca26-e19d-4f0d-a21e-14b45891f919.png) [^16]

![036980a6-6d67-4944-bc70-4bc7ea19e6cc.png|1048.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/036980a6-6d67-4944-bc70-4bc7ea19e6cc.png) [^17]

\

\

<mark>**Assigning Internet gateway to public route table:**</mark>

![d4817d7c-b463-4b35-b3e2-947817177499.png|976.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d4817d7c-b463-4b35-b3e2-947817177499.png) [^18]

![f3fbad97-2a0e-45fc-8704-c09cc6f829ac.png|1018.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/f3fbad97-2a0e-45fc-8704-c09cc6f829ac.png) [^19]

\

![bbbae97f-d719-4520-8275-fe1a1dbd989b.png|1013.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/bbbae97f-d719-4520-8275-fe1a1dbd989b.png) [^20]

\

\

<mark>**Private route table & associating with private subnets(1a, 1b):**</mark>

\

After creation snapshot

![b2df7689-a5d4-48a5-a9dd-2e6e78ba1692.png|952.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/b2df7689-a5d4-48a5-a9dd-2e6e78ba1692.png) [^21]

\

<mark>**Database route table & associating with Database subnets(1a, 1b):**</mark>

After creation snapshot

![530b22ad-23b6-4cb3-aa5a-860559b71f08.png|933.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/530b22ad-23b6-4cb3-aa5a-860559b71f08.png) [^22]

---

# <mark style="background-color:#f8914d;">**NAT Gateway - only for outgoing traffic not incoming**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

We need to update packages in Database, private servers, we need to download something. We should connect internet.

outgoing is allowed..

incoming traffic is disabled...

\

<mark style="background-color:#fff7cb;">We will create NAT gateway in public subnet because it has internet connectivity(Internet Gateway) then we add it in the route tables.<!-- {"backgroundCycleColor":"3"} --></mark>

![ef2e99bf-d8c0-4271-916c-b2ae90ced979.png|911](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/ef2e99bf-d8c0-4271-916c-b2ae90ced979.png) [^23]

\

We need to create & assign Elastic IP(Static IP address) to NAT gateway ( Both NAT & Elastic IP are chargeable)

\

<mark style="background-color:#f8d616;">**Elastic IP creation**<!-- {"backgroundCycleColor":"25"} --></mark>

![bed3853f-e4f5-4837-82ab-366064dee8ba.png|948.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/bed3853f-e4f5-4837-82ab-366064dee8ba.png) [^24]

\

\

<mark style="background-color:#f8d616;">**NAT Gateway Creation**<!-- {"backgroundCycleColor":"25"} --></mark>

![f5b47842-9237-40fa-b4da-403a9f588f7e.png|1014](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/f5b47842-9237-40fa-b4da-403a9f588f7e.png) [^25]

![a63635d4-7413-49b6-80a3-88ebbfb98fa4.png|1159.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/a63635d4-7413-49b6-80a3-88ebbfb98fa4.png) [^26]

\

<mark style="background-color:#f8d616;">**Adding NAT gateway to Private & Database route tables**<!-- {"backgroundCycleColor":"25"} --></mark>

![e744c27f-ce8c-4f9e-8a35-9eabbd15db8c.png|917.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/e744c27f-ce8c-4f9e-8a35-9eabbd15db8c.png) [^27]

![8a739c90-7cf9-4509-bb9b-1ea587ba0016.png|970.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/8a739c90-7cf9-4509-bb9b-1ea587ba0016.png) [^28]

![e1de1909-18c5-458b-b037-bf4174d8adf9.png|967.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/e1de1909-18c5-458b-b037-bf4174d8adf9.png) [^29]

![cb5d5d7f-cb91-493c-aa42-03500e95aaf7.png|973.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/cb5d5d7f-cb91-493c-aa42-03500e95aaf7.png) [^30]

---

# <mark style="background-color:#f8914d;">**VPC Peering**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

VPC are secure, so by default it is disabled to connect with other VPC. But if we want to connect with other VPC then we use VPC Peering.

<mark>Condition: Both VPC CIDR should be different.</mark>

\

**Requestor VPC** -- I want to connect with you please accept my request.

**Acceptor VPC**

\

Connection types

VPCs in same region same account

VPC in another region same account

VPC is same region another account

VPC in different region another account

\

\

Requestor VPC -- roboshop VPC

Acceptor VPC -- Default VPC

\

![77def84f-2efc-4bb2-ad19-93d74e22913a.png|960](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/77def84f-2efc-4bb2-ad19-93d74e22913a.png) [^31]

\

![67de5e8a-45d3-4ad1-a242-91e2985534b3.png|1157.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/67de5e8a-45d3-4ad1-a242-91e2985534b3.png) [^32]

\

Acceptance:

![c95c60d9-ccc2-4299-89c2-4d094abe53ce.png|966.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/c95c60d9-ccc2-4299-89c2-4d094abe53ce.png) [^33]

![48f9f6e6-6e35-4852-b134-04e44f3ad0b9.png|1142](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/48f9f6e6-6e35-4852-b134-04e44f3ad0b9.png) [^34]

![957a963d-1031-4388-9cdc-66d2c738192b.png|1143.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/957a963d-1031-4388-9cdc-66d2c738192b.png) [^35]

\

Now its communicating from VPC to VPC level not from subnets.

\

So need to add destination CIDR to route.

**VPC default CIDR**- <mark>172.31.0.0/16</mark>

**Roboshop CIDR** - <mark>10.0.0.0/16</mark>

\

We need to establish route(road) connection in two ways.

\

<mark style="background-color:#f8914d;">**Creating for Roboshop CIDR** - 10.0.0.0/16<!-- {"backgroundCycleColor":"24"} --></mark>

Now i want to add it to public route table(where public subnets are added to communicate)

\

![d37a9be8-f60a-4a0b-9e6e-deed8d9584e5.png|942.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d37a9be8-f60a-4a0b-9e6e-deed8d9584e5.png) [^36]

![caa78019-5a83-4624-88c5-a4eb44cebbe8.png|968.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/caa78019-5a83-4624-88c5-a4eb44cebbe8.png) [^37]

![25f6f379-f15d-4c31-9775-b7ba7ea8a091.png|962.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/25f6f379-f15d-4c31-9775-b7ba7ea8a091.png) [^38]

\

\

<mark style="background-color:#f8914d;">**Creating for VPC default CIDR**- 172.31.0.0/16<!-- {"backgroundCycleColor":"24"} --></mark>

\

![803a02ba-5b98-42cf-a8c5-caa4e6872c2f.png|986.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/803a02ba-5b98-42cf-a8c5-caa4e6872c2f.png) [^39]

![094ed0f7-3043-4914-b9d5-21cdd82614a5.png|1011.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/094ed0f7-3043-4914-b9d5-21cdd82614a5.png) [^40]

![5d4fa27a-1959-4de8-8178-cc6b67f5dd8a.png|1049.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/5d4fa27a-1959-4de8-8178-cc6b67f5dd8a.png) [^41]

---

# <mark style="background-color:#f8914d;">**VPC creation using Terraform**<!-- {"backgroundCycleColor":"24"} --></mark> 

Create below folder and files.

![](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/04f6fc4b-9223-4cc3-ad0b-f7fe5e730517.png) [^42]

![3554eb00-0fd8-4910-bf71-eefeab59f51c.png|804](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/3554eb00-0fd8-4910-bf71-eefeab59f51c.png) [^43]

![e1a72f32-7036-4df1-a04d-b64a95e0b7fe.png|615](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/e1a72f32-7036-4df1-a04d-b64a95e0b7fe.png) [^44]

\

Providers.tf code

![b1e45c26-092c-4732-b18a-eb67a8833e52.png|959.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/b1e45c26-092c-4732-b18a-eb67a8833e52.png) [^45]

\

```
terraform init
```

![](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d8e411f1-cf87-4ad7-8321-879a9773586f.png) [^46]

\

add .gitignore file

![a1094d80-e2b1-469d-853f-23cf28c4c3dc.png|834.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/a1094d80-e2b1-469d-853f-23cf28c4c3dc.png) [^47]

\

main.tf code 

![5f97298c-7ec0-4185-ac9e-1b38dcf77420.png|1096.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/5f97298c-7ec0-4185-ac9e-1b38dcf77420.png) [^48]

![49d2b7b2-f659-431f-8266-b94dc95cbae1.png|1096.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/49d2b7b2-f659-431f-8266-b94dc95cbae1.png) [^49]

![96cae168-eac0-42b9-9acd-9fe1b25add8c.png|897](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/96cae168-eac0-42b9-9acd-9fe1b25add8c.png) [^50]

![f4e9c6bb-db06-40c6-b1ea-398d62757d4e.png|890](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/f4e9c6bb-db06-40c6-b1ea-398d62757d4e.png) [^51]

\

Data.tf code

![b6687441-ecb0-49b2-bc9f-35e643bd3804.png|995](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/b6687441-ecb0-49b2-bc9f-35e643bd3804.png) [^52]

\

Local.tf code

![8dab4579-8b4f-4a11-bd16-c36488ec78fa.png|1020.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/8dab4579-8b4f-4a11-bd16-c36488ec78fa.png) [^53]

\

outputs.tf code

![a1057915-8e95-43ab-8792-fe717a121401.png|1079](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/a1057915-8e95-43ab-8792-fe717a121401.png) [^54]

\

Variables.tf code

![2070fe55-f01f-437f-be89-cfd878c73cf6.png|1121.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/2070fe55-f01f-437f-be89-cfd878c73cf6.png) [^55]

![392ecf28-8cbc-44ef-b781-ac82fce177f9.png|832](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/392ecf28-8cbc-44ef-b781-ac82fce177f9.png) [^56]

![](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/2d5e4c33-2408-4a5b-a2c0-aef41664f044.png) [^57]

\

main.tf code under VPC test 

![e01c54cd-65e4-4593-ac52-5e8aef2ab275.png|1012](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/e01c54cd-65e4-4593-ac52-5e8aef2ab275.png) [^58]

\

outputs.tf code

![](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/b391de92-bd43-40b9-ae10-fa2df29b5fcb.png) [^59]

\

Variables.tf code

![36c0ba2d-1eac-416b-b264-6ef10173e497.png|1050](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/36c0ba2d-1eac-416b-b264-6ef10173e497.png) [^60]

\

```
cd e/AWSDevOps/Repos/vpc-test/
terraform plan
terraform apply -auto-approve
```

![1d153c0d-f55e-4966-a842-0dbca1bbe73b.png|1055](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/1d153c0d-f55e-4966-a842-0dbca1bbe73b.png) [^61]

\

Now you can check all below items except peering

![3554eb00-0fd8-4910-bf71-eefeab59f51c.png|664](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/3554eb00-0fd8-4910-bf71-eefeab59f51c.png) [^62]

\

VPC

![d10f98f5-5081-46ad-9d71-7e5bb812fd33.png|1031.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d10f98f5-5081-46ad-9d71-7e5bb812fd33.png) [^63]

subnets

![d2fa9e16-f76f-4bee-8ab0-f47bc7c5be6c.png|1049.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d2fa9e16-f76f-4bee-8ab0-f47bc7c5be6c.png) [^64]

\

Route tables

![0b742bf5-75aa-45ad-a472-2685ab9ce8e8.png|1061.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/0b742bf5-75aa-45ad-a472-2685ab9ce8e8.png) [^65]

\

Internet gateway

![deea0005-d7d3-4768-9fe4-ffc9c5914af5.png|1068.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/deea0005-d7d3-4768-9fe4-ffc9c5914af5.png) [^66]

\

Elastic IP

![4a12a7ee-d791-414e-874a-434f47623f43.png|1124.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/4a12a7ee-d791-414e-874a-434f47623f43.png) [^67]

\

NAT gateway

![5983e4a4-d3a6-41e7-883e-66430d271a4f.png|1095.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/5983e4a4-d3a6-41e7-883e-66430d271a4f.png) [^68]

\

Public route table association

![65428c6f-9ba0-48f4-84c4-ae1e1e450aac.png|970.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/65428c6f-9ba0-48f4-84c4-ae1e1e450aac.png) [^69]

everything which we done in manual..

\

\

<mark>**VPC Peering module:**</mark>

peering.tf code

![9c491386-b872-4fca-af9d-36e7734c4568.png|1053.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/9c491386-b872-4fca-af9d-36e7734c4568.png) [^70]

\

variables.tf code updated

![05cd9f81-6528-493d-9471-c6e48389da93.png|923](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/05cd9f81-6528-493d-9471-c6e48389da93.png) [^71]

\

variables.tf code updated under vpc-test directory

![1697d82c-fca7-4888-be71-232f26b8b5f1.png|923](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/1697d82c-fca7-4888-be71-232f26b8b5f1.png) [^72]

\

main.tf code updated

![0c57efcd-dd84-4114-82de-c5bed8c71f20.png|936](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/0c57efcd-dd84-4114-82de-c5bed8c71f20.png) [^73]

\

```
terraform plan
```

![84044fac-3136-4ef5-974f-bd897b107de1.png|1015](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/84044fac-3136-4ef5-974f-bd897b107de1.png) [^74]

\

```
terraform apply -auto-approve
```

![2bee4f25-01a2-4555-b10e-6947d85d8151.png|1018.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/2bee4f25-01a2-4555-b10e-6947d85d8151.png) [^75]

\

VPC peering created

![2967e0c3-3580-42bc-9a1a-ab8603fb27de.png|1101.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/2967e0c3-3580-42bc-9a1a-ab8603fb27de.png) [^76]

<mark>Now adding routes to peering:</mark>

\

peering.tf code updated

![93705369-d2e4-4952-af86-85c272237b75.png|1063.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/93705369-d2e4-4952-af86-85c272237b75.png) [^77]

\

data.tf code updated

![52f51c17-fcb3-4947-8743-488fc0024e4a.png|1066](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/52f51c17-fcb3-4947-8743-488fc0024e4a.png) [^78]

\

```
terraform apply -auto-approve
```

![d261adff-36e0-45d7-a69b-912012a9c240.png|1067.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d261adff-36e0-45d7-a69b-912012a9c240.png) [^79]

\

other vpc peering attached to route tables

![27b4f318-b130-4d97-95ad-c6e7632ed199.png|1021.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/27b4f318-b130-4d97-95ad-c6e7632ed199.png) [^80]

\

acceptor route 

![6f0dedbf-962b-43b6-b1b4-bdfb71c60fd6.png|1037.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/6f0dedbf-962b-43b6-b1b4-bdfb71c60fd6.png) [^81]

\

```
terraform destroy -auto-approve
```

![9f324146-035f-44d3-98d9-bb0b80215dd9.png|781](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/9f324146-035f-44d3-98d9-bb0b80215dd9.png) [^82]

\

<mark>**Push all the code to GITHUB**</mark>

Now all the code is in github 

![c9a3fe47-ba70-466b-a5fc-02efe265f227.png|970.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/c9a3fe47-ba70-466b-a5fc-02efe265f227.png) [^83]

\

# <mark style="background-color:#f8914d;">**Now using the terraform modules from GITHUB source**<!-- {"backgroundCycleColor":"24"} --></mark>

update the main.tf code

```
  source = "git::https://github.com/chilops/terraform-aws-vpc.git?ref=main"
```

![ccb5f0ce-f04d-43eb-a5cc-8aa57f5da32b.png|812](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/ccb5f0ce-f04d-43eb-a5cc-8aa57f5da32b.png) [^84]

\

```
terraform init
```

![a8508d85-bb26-492d-b93c-add71e08cae5.png|958](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/a8508d85-bb26-492d-b93c-add71e08cae5.png) [^85]

\

Now all the modules/code will be downloaded/loaded to below folder. Now we can use it.

![](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/d5b72617-b730-4751-9f0f-58e375d1ddcd.png) [^86]

\

\

# <mark style="background-color:#f8914d;">**Database subnet groups:**<!-- {"backgroundCycleColor":"24"} --></mark>

We need to add <mark style="background-color:#f8914d;">database<!-- {"backgroundCycleColor":"24"} --></mark> id's to this group

main.tf code updated under terraform-aws-vpc

![16cc0377-ef0a-4bb0-b636-c0c48e88196f.png|1004](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/16cc0377-ef0a-4bb0-b636-c0c48e88196f.png) [^87]

\

```
terraform apply -auto-approve
```

![c7105cb6-6f53-4c6f-ab4b-740a6d818168.png|1048](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/c7105cb6-6f53-4c6f-ab4b-740a6d818168.png) [^88]

![8d6d616c-250d-4714-b5d0-1838a6a1c637.png|1052.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/8d6d616c-250d-4714-b5d0-1838a6a1c637.png) [^89]

\

![7f25764a-eb84-4d7d-a9a3-fdada30e3244.png|1015.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/7f25764a-eb84-4d7d-a9a3-fdada30e3244.png) [^90]

\

![9f9edf37-858a-4cc4-9d91-7f9261376277.png|1065.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/9f9edf37-858a-4cc4-9d91-7f9261376277.png) [^91]

\

\

```
terraform destroy -auto-approve
```

\

\

\

# <mark style="background-color:#f8914d;">**Opensource modules in Terraform:**<!-- {"backgroundCycleColor":"24"} --></mark>

![](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/6b6a5c33-3fe3-438d-a028-e5f02d73bfd6.png) [^92]

\

<mark>Terraform provides modules through GITHUB</mark>

![f88840f7-ec78-4774-94d2-c0e172d2e15a.png|968](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/f88840f7-ec78-4774-94d2-c0e172d2e15a.png) [^93]

![bf869337-9390-4a93-87cf-a5b7a3b2d1d7.png|1004](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/bf869337-9390-4a93-87cf-a5b7a3b2d1d7.png) [^94]

\

![e56e66c5-3ba9-4c0e-88b6-1973fa8c18e3.png|999](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/e56e66c5-3ba9-4c0e-88b6-1973fa8c18e3.png) [^95]

\

\

examples

![ae9c92e1-6b5a-4bb6-b197-71e8a1f13fc3.png|937.3333740234375](https://images.amplenote.com/0d0d170a-1f0f-11ef-b323-2e97089a9920/ae9c92e1-6b5a-4bb6-b197-71e8a1f13fc3.png) [^96]

[^1]: VPC > Your VPCs > Create VPC
    Create VPC Info
    A VPC is an isolated portion of the AWS Cloud populated by AWS objects, such as Amazon EC2 instances.
    VPC settings
    Resources to create Info
    Create only the VPC resource or the VPC and other networking resources.
    O VPC only
    O VPC and more
    Name tag - optional
    Creates a tag with a key of 'Name' and a value that you specify.
    roboshop-VRC
    IPV4 CIDR block Info
    . IPV4 CIDR manual input
    O IPAM-allocated IPV4 CIDR block
    IPV4 CIDR
    10.0.0.0/16
    CIDR block size must be between /16 and /28.
    IPV6 CIDR block Info
    No IPV6 CIDR block
    O IPAM-allocated IPV6 CIDR block
    Amazon-provided IPV6 CIDR block
    O IPV6 CIDR owned by me
    Tenancy Info
    Default

[^2]: Your VPCs (1/2) Info
    Actions V
    Create VPC
    Q Search
    <
    1 >
    -
    Name
    4
    VPC ID
    4
    State
    4
    IPV4 CIDR
    IPV6 CIDR
    V
    D
    Vpc-0817 cae8968304c06
    Available
    172.31.0.0/16
    d
    V
    roboshop-vpc .
    vpc-08c03b0bed89547c2
    Available
    10.0.0.0/16
    di

[^3]: VPC > Internet gateways > Create internet gateway
    Create internet gateway info
    An internet gateway is a virtual router that connects a VPC to the internet. To create a new internet gateway specify the name
    for the gateway below.
    Internet gateway settings
    Name tag
    Creates a tag with a key of 'Name' and a value that you specify.
    roboshop-IG
    Tags - optional
    A tag is a label that you assign to an AWS resource. Each tag consists of a key and an optional value. You can use tags to search and filter
    your resources or track your AWS costs.
    Key
    Value - optional
    Q Name
    X
    Q roboshop-IG
    X
    Remove
    Add new tag
    You can add 49 more tags.
    Cancel
    Create internet gateway

[^4]: VPC > Internet gateways > igw-0490a4dd897a3cf97
    igw-0490a4dd897a3cf97 / roboshop-IG
    Actions
    Details Info
    Internet gateway ID
    State
    VPC ID
    Owner
    igw-0490add897a3cf97
    Detached
    7 158724841371
    Tags
    Manage tags
    Q Search tags
    <1 >
    Key
    Value
    Name
    roboshop-IG

[^5]: VPC > Internet gateways > igw-0490a4dd897a3cf97
    igw-0490a4dd897a3cf97 / roboshop-IG
    Actions
    Attach to VPC
    Details Info
    Detach from VPC
    Manage tags
    Internet gateway ID
    State
    VPC ID
    Owner
    igw-0490a4dd897a3cf97
    Detached
    1587248413
    Delete
    Tags
    Manage tags
    Q Search tags
    <
    1 >
    Key
    Value
    Name
    roboshop-IG

[^6]: Attach to VPC (igw-0490a4dd897a3cf97)
    Info
    VPC
    Attach an internet gateway to a VPC to enable the VPC to communicate with the internet. Specify the VPC to attach below.
    Available VPCs
    Attach the internet gateway to this VPC.
    Q vpc-08c03b0bed89547c2
    X
    D
    AWS Command Line Interface command
    Cancel
    Attach internet gateway

[^7]: igw-0490a4dd897a3cf97 / roboshop-IG
    Actions V
    Details Info
    Internet gateway ID
    State
    VPC ID
    Owner
    igw-0490a4dd897a3cf97
    Attached
    vpc-08c03b0bed89547c2 \| roboshop-
    158724841371
    Vpc

[^8]: Subnet 1 of 1
    Subnet name
    Create a tag with a key of 'Name' and a value that you specify.
    roboshop-public-1a
    The name can be up to 256 characters long.
    Availability Zone Info
    Choose the zone in which your subnet will reside, or let Amazon choose one for you.
    US East (N. Virginia) / us-east-1a
    IPV4 VPC CIDR block Info
    Choose the VPC's IPv4 CIDR block for the subnet. The subnet's IPV4 CIDR must lie within this block.
    10.0.0.0/16
    IPv4 subnet CIDR block
    10.0.1.0/24
    256 IPS
    <
    Tags - optional
    Key
    Value - optional
    Name
    X
    Q roboshop-public-1a
    X
    Remove
    Add new tag
    You can add 49 more tags.
    Remove
    Add new subnet
    Cancel
    Create subnet

[^9]: Subnet 1 of 1
    Subnet name
    Create a tag with a key of 'Name' and a value that you specify.
    roboshop-public-1b
    The name can be up to 256 characters long.
    Availability Zone Info
    Choose the zone in which your subnet will reside, or let Amazon choose one for you.
    US East (N. Virginia) / us-east-1b
    IPV4 VPC CIDR block Info
    Choose the VPC's IPV4 CIDR block for the subnet. The subnet's IPV4 CIDR must lie within this block.
    10.0.0.0/16
    IPv4 subnet CIDR block
    10.0.2.0/24
    256 IPS
    <
    >
    V

[^10]: O
    roboshop-public-1a
    subnet-0c87d5abe95aac2d4
    Available
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    10.0.1.0/24
    roboshop-public-1b
    subnet-0a3ca51e018777ald
    Available
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    10.0.2.0/24

[^11]: O
    roboshop-private-1a
    subnet-03da632d3613fdacf
    Available
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    10.0.11.0/24
    roboshop-private-1b
    subnet-059cb986978d61ac4
    Available
    vpc-08c03bObed89547c2 \| roboshop-vpc
    10.0.12.0/24

[^12]: O
    roboshop-database-1a
    subnet-03a 10cc4cf4835cfc
    Available
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    10.0.21.0/24
    O
    roboshop-database-1b
    subnet-047f0a8a 1ae 16137a
    Available
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    10.0.22.0/24

[^13]: Create route table info
    A route table specifies how packets are forwarded between the subnets within your VPC, the internet, and your VPN
    connection.
    Route table settings
    Name - optional
    Create a tag with a key of 'Name' and a value that you specify.
    public-route-roboshop
    VPC
    The VPC to use for this route table.
    vpc-08c03b0bed89547c2 (roboshop-vpc)
    Tags
    A tag is a label that you assign to an AWS resource. Each tag consists of a key and an optional value. You can use tags to search and filter
    your resources or track your AWS costs.
    Key
    Value - optional
    Q Name
    X
    Q public-route-roboshop
    X
    Remove
    Add new tag
    You can add 49 more tags.
    Cancel
    Create route table

[^14]: public-route-roboshop
    rtb-06bd4cea8af7 4f6a7
    No
    vpc-08c03b0bed895

[^15]: V
    public-route-roboshop
    rtb-06bd4cea8af74f6a7
    No
    vpc-08c0360bed895
    rtb-06bd4cea8af74f6a7 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Explicit subnet associations (0)
    Edit subnet associations
    Q Find subnet association
    1
    Name
    Subnet ID
    4
    IPV4 CIDR
    4
    IPV6 CIDR
    No subnet associations

[^16]: VPC > Route tables > rtb-06bd4cea8af74f6a7 > Edit subnet associations
    Edit subnet associations
    Change which subnets are associated with this route table.
    Available subnets (2/6)
    Q Filter subnet associations
    <
    1
    -
    Name
    Subnet ID
    4
    IPV4 CIDR
    IPV6 CIDR
    4
    Route table ID
    V
    roboshop-public-1a
    subnet-0c87d5abe95aac2d4
    10.0.1.0/24
    rtb-06bd4cea8af74f6a7 / public-route..
    roboshop-public-1b
    subnet-0a3ca51e018777ald
    10.0.2.0/24
    rtb-06bd4cea8af74f6a7 / public-route..
    O
    roboshop-private-1a
    subnet-03da632d3613fdacf
    10.0.11.0/24
    Main (rtb-043d374ea02fa91f4)
    O
    roboshop-private-1b
    subnet-059cb986978d61ac4
    10.0.12.0/24
    Main (rtb-043d374ea02fa91f4)
    O
    roboshop-database-1a
    subnet-03a 10cc4cf4835cfc
    10.0.21.0/24
    Main (rtb-043d374ea02fa91f4)
    roboshop-database-1b
    subnet-047f0ada 1ae 16137a
    10.0.22.0/24
    Main (rtb-043d374ea02fa91f4)
    Selected subnets
    subnet-0c87d5abe95aac2d4 / roboshop-public-1a X
    subnet-0a3ca51e018777ald / roboshop-public-1b X
    Cancel
    Save associations

[^17]: V
    public-route-roboshop/
    rtb-06bd4cea8af74f6a7
    2 subnets
    No
    vpc-08c03b0bed895
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Explicit subnet associations (2)
    Edit subnet associations
    Q Find subnet association
    <
    1 >
    Name
    Subnet ID
    4
    IPV4 CIDR
    IPV6 CIDR
    roboshop-public-1a
    subnet-0c87d5abe95aac2d4
    10.0.1.0/24
    roboshop-public-1b
    subnet-0a3ca51e018777ald
    10.0.2.0/24

[^18]: V
    public-route-roboshop
    rtb-06bd4cea8af74f6a7
    2 subnets
    No
    vpc-08c0360bed895
    rtb-06bd4cea8af74f6a7 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (1)
    Both
    Edit routes
    O Filter routes
    1
    Destination
    4
    Target
    4
    Status
    4
    Propagated
    10.0.0.0/16
    local
    Active
    No

[^19]: VPC > Route tables > rtb-06bd4cea8af74f6a7 > Edit routes
    Edit routes
    Destination
    Target
    Status
    Propagated
    10.0.0.0/16
    local
    Active
    No
    Q local
    X
    Q 0.0.0.0/0
    X
    Internet Gateway
    No
    Remove
    Q igw-0490a4dd897a3cf97
    X
    Add route
    Cancel
    Preview
    Save changes

[^20]: V
    public-route-roboshop
    rtb-06bd4cea8af74f6a7
    2 subnets
    N
    rtb-06bd4cea8af74f6a7 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (2)
    Q Filter routes
    Destination
    Target
    V
    Status
    4
    Propagated
    0.0.0.0/0
    igw-0490a4dd897a3cf97
    Active
    No
    10.0.0.0/16
    local
    Active
    No

[^21]: V
    private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c03b0bed895
    8 0 0
    rtb-0566c05bb34c139ec / private-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Explicit subnet associations (2)
    Edit subnet associations
    Q Find subnet association
    < 1 >
    Name
    4
    Subnet ID
    4
    IPV4 CIDR
    4
    IPV6 CIDR
    roboshop-private-1a
    subnet-03da632d3613fdacf
    10.0.11.0/24
    roboshop-private-1b
    subnet-059cb986978d61ac4
    10.0.12.0/24

[^22]: V
    database-route-roboshop _
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    rtb-Oeccf98e1ca97f30c / database-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Explicit subnet associations (2)
    Edit sub
    Q Find subnet association
    Name
    Subnet ID
    IPV4 CIDR
    D
    IPV6 CIDR
    roboshop-database-1a
    subnet-03a 10cc4cf4835cfc
    10.0.21.0/24
    roboshop-database-1b
    subnet-047f0a8a 1ae 16137a
    10.0.22.0/24

[^23]: USL
    PMO
    public
    Roads
    team
    Public Affairs
    Ministers
    PMO
    Secure roads
    private roads
    incoming traffic
    Arch
    private roads
    Secure roads
    Public Affairs
    Ministers
    PMO
    Roads

[^24]: Elastic IP address allocated successfully.
    Associate this Elastic IP address
    X
    Elastic IP address 52.22.252.238
    Elastic IP addresses (1)
    G
    Actions
    Allocate Elastic IP address
    Q Find resources by attribute or tag
    <
    1
    O
    Name
    Allocated IPv4 addr... V Type
    Allocation ID
    4
    Reverse DNS record
    52.22.252.238
    Public IP
    eipalloc-018223bfaa6510106

[^25]: Create NAT gateway info
    A highly available, managed Network Address Translation (NAT) service that instances in private subnets can use to connect to
    services in other VPCs, on-premises networks, or the internet.
    NAT gateway settings
    Name - optional
    Create a tag with a key of 'Name' and a value that you specify.
    roboshop-nat
    The name can be up to 256 characters long.
    Subnet
    Select a subnet in which to create the NAT gateway.
    subnet-0c87d5abe95aac2d4 (roboshop-public-1a)
    Connectivity type
    Select a connectivity type for the NAT gateway.
    Public
    Private
    Elastic IP allocation ID Info
    Assign an Elastic IP address to the NAT gateway.
    eipalloc-018223bfaa6510106
    Allocate Elastic IP
    Additional settings Info

[^26]: NAT gateways (1) Info
    Actions
    Create NAT gateway
    Q Find resources by attribute or tag
    < 1 >
    Name
    4
    NAT gateway ID
    Connectivity... V State
    4
    State message
    D
    Primary public l...
    Primary
    O
    roboshop-nat
    nat-Oda026c51ae053848
    Public
    @ Pending
    10.0.1.2

[^27]: private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c03b0bed895
    database-route-roboshop
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c03b0bed895
    rtb-0566c05bb34c139ec / private-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (1)
    Both
    Edit routes
    Q Filter routes
    <
    1
    >
    Destination
    Target
    4
    Status
    Propagated
    10.0.0.0/16
    local
    Active
    No

[^28]: VPC > Route tables > rtb-0566c05bb34c139ec > Edit routes
    Edit routes
    Destination
    Target
    Status
    Propagated
    10.0.0.0/16
    local
    Active
    No
    Q local
    X
    Q 0.0.0.0/0
    X
    NAT Gateway
    No
    Remove
    Q nat-Oda026c51ae053848
    X
    Use: "nat-Oda026c51ae053848"
    Add route
    nat-0da026c51ae053848 (roboshop-nat)
    Cancel
    Preview
    Save changes

[^29]: V
    private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c0360bed895
    O
    database-route-roboshop
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c0360bed895
    rtb-0566c05bb34c139ec / private-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (2)
    Both
    Edit routes
    Q Filter routes
    1
    Destination
    Target
    4
    Status
    Propagated
    4
    0.0.0.0/0
    nat-0da026c51ae053848
    Active
    No
    10.0.0.0/16
    local
    Active
    No

[^30]: 0
    private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c0360bed895
    V
    database-route-roboshop
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c03b0bed895
    rtb-Oeccf98e1ca97f30c / database-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (2)
    Both
    Edit routes
    Q Filter routes
    <
    1
    Destination
    4
    Target
    4
    Status
    4
    Propagated
    0.0.0.0/0
    nat-Oda026c5 1ae053848
    Active
    No
    10.0.0.0/16
    local
    Active
    No

[^31]: Peering connection settings
    Name - optional
    Create a tag with a key of 'Name' and a value that you specify.
    roboshopVPC-defaultVPC
    Select a local VPC to peer with
    VPC ID (Requester)
    /pc-08c03b0bed89547c2 (roboshop-vpc)
    VPC CIDRS for vpc-08c03bObed89547c2 (roboshop-vpc)
    CIDR
    Status
    Status reason
    10.0.0.0/16
    Associated
    Select another VPC to peer with
    Account
    My account
    Another account
    Region
    This Region (us-east-1)
    Another Region
    VPC ID (Accepter)
    vpc-0817cae89b8304c06
    VPC CIDRS for vpc-0817 cae89b8304c06
    CIDR
    Status
    Status reason
    172.31.0.0/16
    Associated

[^32]: Peering connections (1) Info
    C
    Actions
    Create peering connection
    Q Find resources by attribute or tag
    < 1 >
    Name
    A
    Peering connection ID
    4
    Status
    4
    Requester VPC
    Accepter VPC
    O
    roboshopVPC-defaultVPC
    pcx-06325a74dff640636
    Pending acceptance
    vpc-08c03b0bed89547c2 / rob...
    vpc-0817 cae8968304c06

[^33]: Peering connections (1/1) Info
    C
    Actions
    Create peering connection
    Q Find resources by attribute or tag
    View details
    <
    1 >
    Accept request
    Name
    V
    Peering connection ID
    4
    Status
    4
    Request
    pter VPC
    Reject request
    O
    roboshopVPC-defaultVPC
    pcx-06325a74dff640636
    Pending acceptance
    vpc-08c
    0817cae8968304c06
    Edit DNS settings
    Manage tags
    Delete peering connection

[^34]: Accept VPC peering connection request Info
    X
    Are you sure you want to accept this VPC peering connection request? (pcx-06325a74dff640636 / roboshopVPC-
    defaultVPC)
    Requester VPC
    Accepter VPC
    Requester CIDRs
    vpc-08c03b0bed89547c2 /
    vpc-0817cae8968304c06
    10.0.0.0/16
    roboshop-vpc
    Requester Region
    Accepter Region
    Accepter CIDRs
    N. Virginia (us-east-1)
    N. Virginia (us-east-1)
    Accepter owner ID
    Requester owner ID
    158724841371
    158724841371
    (This account)
    (This account)
    It or
    Cancel
    Accept request

[^35]: Your VPC peering connection (pcx-06325a74dff640636 / roboshopVPC-defaultVPC) has been established.
    Modify my route tables now
    X
    To send and receive traffic across this VPC peering connection, you must add a route to the peered VPC in one or more of your VPC
    route tables.
    Info
    Peering connections (1) Info
    G
    Actions
    Create peering connection
    Find resources by attribute or tag
    <
    1 >
    Name
    Peering connection ID
    Status
    4
    Requester VPC
    Accepter VPC
    O
    roboshopVPC-defaultVPC
    pcx-06325a74dff640636
    Active
    vpc-08c03b0bed89547c2 / rob...
    vpc-0817cae8968304c06

[^36]: Route tables (1/5) Info
    C
    Actions V
    Create route table
    Q Find resources by attribute or tag
    < 1 >
    -
    Name
    Route table ID
    4
    Explicit subnet associ... V Edge associations V
    Main
    4
    VPC
    V
    public-route-roboshop
    rtb-06bd4cea8af74f6a7
    2 subnets
    No
    vpc-08c03b0bed895
    private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c03b0bed895
    O
    database-route-roboshop
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c0360bed895
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817cae896830
    rtb-043d374ea02fa91f4
    Yes
    vpc-08c0360bed895
    rtb-06bd4cea8af74f6a7 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (2)
    Both
    Edit routes
    Q Filter routes
    <
    Destination
    4
    Target
    A
    Status
    Propagated
    0.0.0.0/0
    igw-0490a4dd897a3cf97
    Active
    No
    10.0.0.0/16
    local
    Active
    No

[^37]: VPC > Route tables > rtb-06bd4cea8af74f6a7 > Edit routes
    Edit routes
    Destination
    Target
    Status
    Propagated
    10.0.0.0/16
    local
    Active
    No
    Q local
    X
    Q 0.0.0.0/0
    X
    Internet Gateway
    Active
    No
    Remove
    Q igw-0490a4dd897a3cf97
    X
    Q 172.31.0.0/16
    X
    Peering Connection
    No
    Remove
    Q pcx-06325a74dff640636
    X
    Add route
    Cancel
    Preview
    Save changes

[^38]: Route tables (1/5) Info
    C
    Actions
    Create route table
    Q Find resources by attribute or tag
    < 1
    -
    Name
    Route table ID
    Explicit subnet associ... V Edge associations
    Main
    4
    VPC
    public-route-roboshop
    rtb-06bd4cea8af74f6a7
    2 subnets
    No
    vpc-08c03b0bed895
    0
    private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c0360bed895
    database-route-roboshop
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c0360bed895
    0
    tb-Obfe8282f6ae865ab
    Yes
    vpc-0817 cae896830
    rtb-043d374ea02fa91f4
    Yes
    vpc-08c0360bed895
    rtb-06bd4cea8af74f6a7 / public-route-roboshop
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (3)
    Both
    Edit routes
    Q Filter routes
    < 1
    Destination
    Target
    4
    Status
    Propagated
    0.0.0.0/0
    igw-0490a4dd897a3cf97
    Active
    No
    10.0.0.0/16
    local
    Active
    No
    172.31.0.0/16
    pcx-06325a74dff640636
    Active
    No

[^39]: Route tables (1/5) Info
    C
    Actions V
    Create route table
    Find resources by attribute or tag
    < 1 >
    -
    Name
    Route table ID
    Explicit s... V Edge...
    Main
    V VPC
    0
    public-route-roboshop
    rtb-06bd4cea8af7 4f6a7
    2 subnets
    No
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    private-route-roboshop _
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    O
    database-route-roboshop
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    V
    tb-Obfe8282f6ae865ab
    Yes
    vpc-0817cae8968304c06
    rtb-043d374ea02fa91f4
    Yes
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    rtb-Obfe8282f6ae865ab
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (2)
    Both
    Edit routes
    O Filter routes
    1
    Destination
    A
    Target
    4
    Status
    Propagated
    0.0.0.0/0
    igw-059405258c34db2a1
    Active
    No
    172.31.0.0/16
    local
    Active
    No

[^40]: VPC > Route tables >
    rtb-Obfe8282f6ae865ab > Edit routes
    Edit routes
    Destination
    Target
    Status
    Propagated
    172.31.0.0/16
    local
    Active
    No
    Q local
    X
    Q 0.0.0.0/0
    X
    Internet Gateway
    Active
    No
    Remove
    Q igw-059405258c34db2a1
    X
    Q 10.0.0.0/16
    X
    Peering Connection
    No
    Remove
    Q pcx-06325a74dff640636
    X
    Add route
    Cancel
    Preview
    Save changes

[^41]: Route tables (1/5) Info
    C
    Actions
    Create route table
    Q Find resources by attribute or tag
    < 1 >
    -
    Name
    A
    Route table ID
    Explicit s...
    Edge...
    Main
    4
    VPC
    O
    public-route-roboshop
    rtb-06bd4cea8af74f6a7
    2 subnets
    No
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    O
    private-route-roboshop
    rtb-0566c05bb34c139ec
    2 subnets
    No
    vpc-08c0360bed89547c2 \| roboshop-vpc
    O
    database-route-roboshop _
    rtb-Oeccf98e1ca97f30c
    2 subnets
    No
    vpc-08c03b0bed89547c2 \| roboshop-vpc
    V
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817cae8968304c06
    0
    rtb-043d374ea02fa91f4
    Yes
    vpc-08c0360bed89547c2 \| roboshop-vpc
    rtb-Obfe8282f6ae865ab
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (3)
    Both
    Edit routes
    O Filter routes
    < 1
    Destination
    Target
    Status
    4
    Propagated
    0.0.0.0/0
    igw-059405258c34db2a1
    Active
    No
    10.0.0.0/16
    pcx-06325a74dff640636
    Active
    No
    172.31.0.0/16
    local
    Active
    No

[^42]: terraform-aws-vpc
    main.tf
    U
    outputs.tf
    U
    variables.tf
    U
    > terraform-modules
    > terraform-multi-env
    > terraform-provisioners
    v vpc-test

[^43]: 1. create VPC
    2. create igw and attach
    3. create all subnets
    4. create route tables
    5. create routes
    6. associate with subnets
    7. create eip
    8. create nat
    9. add nat gateway route in private and database subnets
    10. peering connection
    11. routes

[^44]: common tags
    Project = roboshop
    Terraform = true
    Environment = dev
    vpc tags, subnet tags, nat gateway tags I

[^45]: REPOS
    vpc-test > provider.tf > $ provider "aws"
    > Ansible
    1
    terraform {
    Concepts
    N
    required_providers {
    13
    Ansible.MD
    aws = {
    M
    4
    source = "hashicorp/aws"
    image-1.png
    15
    version = "5.31.0" # AWS provider version, not terraform version
    image.png
    {} person.json
    M
    7
    person.xml
    18
    person.yaml
    backend "s3" {
    10
    > notes
    bucket = "chilops-terraform-remotestate"
    11
    key
    = "vpc-test"
    > Robosho-shellscripts
    M
    12
    region = "us-east-1"
    > roboshop-ansible
    13
    dynamodb_table = "chilops-locking"
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    > terraform-aws-vpc
    17
    provider "aws" {
    18
    terraform-modules
    region = "us-east-1"
    19
    > ec2
    > roboshop-ec2
    .gitignore
    v terraform-multi-env
    > tfvars
    workspaces
    > .terraform
    E .terraform.lock.hcl
    ec2.tf
    provider.tf
    variables.tf
    .gitignore
    > terraform-provisioners
    v vpc-test
    main.tf
    U
    provider.tf
    U

[^46]: chowd@Chowdary MINGW64 /
    $ cd e/AWSDevops /Repos /vpc-test/
    chowd@chowdary MINGW64 /e/AWSDevops/Repos /vpc-test (main)
    $ terraform init
    Initializing the backend...
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    Initializing provider plugins. . .
    Finding hashicorp/aws versions matching "5. 31.0"...
    Installing hashicorp/aws v5 . 31.0. . .

[^47]: REPOS
    vpc-test > @ .gitignore
    > Ansible
    1
    # Local . terraform directories
    Concepts
    2
    \* \*/ . terraform/\*
    3
    Ansible.MD
    M
    4
    # . tfstate files
    image-1.png
    15
    \* . tfstate
    image.png
    6
    \* . tfstate.\*
    {} person.json
    M
    7
    person.xml
    8
    # Crash log files
    ! person.yaml
    9
    crash . log
    10
    > notes
    O
    crash. \* . log
    11
    > Robosho-shellscripts
    M
    12
    # Exclude all . tovars files, which are likely to contain sensitive data, such as
    > roboshop-ansible
    13
    # password, private keys, and other secrets. These should not be part of version
    > roboshop-ansible-roles
    14
    # control as they are data points which are potentially sensitive and subject
    > shellscripts
    15
    # to change depending on the environment.
    > terraform
    16
    \* . tfvars
    > terraform-aws-vpc
    17
    \*. tfvars . json
    18
    v terraform-modules
    19
    # Ignore override files as they are usually used to override resources locally and so
    > ec2
    20
    # are not checked in
    > roboshop-ec2
    21
    override . tf
    .gitignore
    22
    override. tf . json
    v terraform-multi-env
    23
    \*_override. tf
    > tfvars
    24
    \*_override. tf. json
    25
    workspaces
    26
    # Include override files you do wish to add to version control using negated pattern
    > .terraform
    27
    # !example_override. tf
    E.terraform.lock.hcl
    28
    ec2.tf
    29
    # Include tfplan files to ignore the plan output of command: terraform plan -out=tfplan
    provider.tf
    30
    # example: \*tfplan\*
    variables.tf
    31
    32
    .gitignore
    # Ignore CLI configuration files
    33
    . terraformrc
    > terraform-provisioners
    34
    terraform. rc
    v vpc-test
    > .terraform
    .gitignore
    U
    E.terraform.lock.hcl

[^48]: V REPOS
    terraform-aws-vpc > main.tf > % resource "aws_route_table_association" "database"
    > Ansible
    1
    resource "aws_vpc" "main" {
    v Concepts
    cidr_block
    = var . vpc_cidr
    Ansible.MD
    M
    enable_dns_hostnames = var . enable_dns_hostnames
    A W
    tags = merge(
    image-1.png
    5
    var . common_tags,
    image.png
    6
    var . vpc_tags,
    {} person.json
    M
    person.xml
    8
    Name = local . name
    ! person.yaml
    9
    > notes
    10
    O
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    resource "aws_internet_gateway" "gw" {
    > roboshop-ansible-roles
    14
    vpc_id = aws_vpc. main. id
    > shellscripts
    15
    > terraform
    16
    tags = merge(
    v terraform-aws-vpc
    17
    var . common_tags,
    18
    data.tf
    U
    var . igw_tags,
    19
    locals.tf
    U
    20
    Name = local . name
    main.tf _
    U
    21
    outputs.tf
    U
    22
    peering.tf
    U
    23
    variables.tf
    24
    > terraform-modules
    25
    resource "aws_subnet" "public" {
    26
    > terraform-multi-env
    count = length(var . public_subnets_cidr)
    27
    vpc_id
    = aws_vpc . main . id
    > terraform-provisioners
    28
    cidr_block = var . public_subnets_cider\[count . index \]
    vpc-test
    29
    availability_zone = local. az_names \[count . index\]
    > .terraform
    30
    map_public_ip_on_launch = true
    .gitignore
    U
    31
    tags = merge(
    E.terraform.lock.hcl
    U
    32
    var . common_tags,
    33
    main.tf
    U
    var . public_subnets_tags,
    34
    outputs.tf
    U
    35
    Name = "${local. name}-public-${local. az_names \[count. index\]}"
    provider.tf
    U
    36
    variables.tf
    U
    37
    38
    39
    40
    41
    resource "aws_subnet" "private" {
    42
    count = length(var . private_subnets_cidr)
    OUTLINE
    43
    vpc_id
    = aws_vpc . main. id
    TIMELINE
    44
    cidr_block = var . private_subnets_cider \[count . index\]

[^49]: REPOS
    terraform-aws-vpc > main.tf > < resource "aws_route_table_association" "database"
    > Ansible
    41
    resource "aws_subnet" "private" {
    v Concepts
    44
    cide_block = var . private_subnets_cide \[count . index\]
    45
    Ansible.MD
    M
    availability_zone = local. az_names \[count . index \]
    46
    tags = merge(
    image-1.png
    47
    var . common_tags,
    image.png
    48
    var . private_subnets_tags,
    {} person.json
    M
    49
    person.xml
    50
    Name = "${local. name}-private-${local. az_names \[count . index\]}"
    person.yaml
    51
    52
    notes
    53
    > Robosho-shellscripts
    M
    154
    > roboshop-ansible
    55
    resource "aws_subnet" "database" {
    > roboshop-ansible-roles
    56
    count = length(var . database_subnets_cidr)
    > shellscripts
    57
    vpc_id
    = aws_vpc . main. id
    > terraform
    58
    cidr_block = var . database_subnets_cidr\[count . index \]
    59
    terraform-aws-vpc
    O
    availability_zone = local. az_names \[count . index\]
    60
    data.tf
    U
    tags = merge(
    61
    var . common_tags,
    locals.tf
    U
    62
    var . private_subnets_tags,
    main.tf
    U
    63
    outputs.tf
    U
    64
    Name = "${local . name}-database-${local . az_names \[ count . index\]\]"
    peering.tf
    U
    65
    variables.tf
    U
    66
    67
    > terraform-modules
    68
    > terraform-multi-env
    69
    resource "aws_db_subnet_group" "default" {
    > terraform-provisioners
    70
    name
    = "${local. name}"
    v vpc-test
    71
    subnet_ids = aws_subnet . database\[\*\]. id
    > .terraform
    72
    .gitignore
    U
    73
    tags = {
    74
    E.terraform.lock.hcl
    U
    Name = "$ {local . name}"
    75
    main.tf
    U
    76
    outputs.tf
    U
    77
    provider.tf
    U
    78
    resource "aws_eip" "eip" {
    variables.tf
    U
    79
    domain
    "vpc"
    80
    81
    82
    resource "aws_nat_gateway" "main" {
    83
    allocation_id = aws_eip . eip. id
    84
    subnet_id
    = aws_subnet. public\[0\]. id
    > OUTLINE
    85
    86
    tags = merge(

[^50]: 87
    var . common_tags,
    88
    var . nat_gateway_tags,
    89
    {
    90
    Name = "$ {local . name}"
    91
    92
    93
    94
    # To ensure proper ordering, it is recommended to add an explicit dependency
    95
    # on the Internet Gateway for the VPC.
    96
    depends_on = \[aws_internet_gateway . gw\]
    97
    98
    99
    resource "aws_route_table" "public" {
    100
    vpc_id = aws_vpc. main. id
    101
    102
    tags = merge(
    103
    var . common_tags,
    104
    var . public_route_table_tags,
    105
    106
    Name = "$ {local . name} -public"
    107
    108
    109
    110
    111
    resource "aws_route_table" "private" {
    112
    vpc_id = aws_vpc. main. id
    113
    114
    tags = merge(
    115
    var . common_tags,
    116
    var . private_route_table_tags,
    117
    118
    Name = "$ {local . name}-private"
    119
    120
    121
    122
    123
    resource "aws_route_table" "database" {
    124
    vpc_id = aws_vpc . main. id
    125
    126
    tags = merge(
    127
    var . common_tags,
    128
    var . database_route_table_tags,

[^51]: 129
    130
    Name = "$ {local . name}-database"
    131
    132
    133
    134
    135
    resource "aws_route" "public_route" {
    136
    route_table_id
    = aws_route_table . public.id
    137
    destination_cidr_block
    = "0.0.0.0/0"
    138
    gateway_id = aws_internet_gateway . gw.id
    139
    140
    141
    resource "aws_route" "private_route" {
    142
    route_table_id
    aws_route_table . private.id
    143
    destination_cidr_block
    = "0.0.0.0/0"
    144
    nat_gateway_id = aws_nat_gateway . main. id
    145
    146
    147
    resource "aws_route" "database_route" {
    148
    route_table_id
    = aws_route_table . database. id
    149
    destination_cidr_block
    = "0.0.0.0/0"
    150
    nat_gateway_id = aws_nat_gateway . main. id
    151
    152
    153
    resource "aws_route_table_association" "public" {
    154
    count = length(var . public_subnets_cidr)
    155
    subnet_id = element(aws_subnet . public\[\*\].id, count . index)
    156
    route_table_id = aws_route_table. public. id
    157
    158
    159
    resource "aws_route_table_association" "private" {
    160
    count = length(var . private_subnets_cidr)
    161
    subnet_id = element(aws_subnet . private\[\*\].id, count . index)
    162
    route_table_id = aws_route_table . private. id
    163
    164
    165
    resource "aws_route_table_association" "database" {
    166
    count = length (var . database_subnets_cidr)
    167
    subnet_id = element(aws_subnet . database\[\*\]. id, count . index)
    168
    route_table_id = aws_route_table . database. id
    169
    170

[^52]: V
    REPOS
    terraform-aws-vpc > data.tf > < data "aws_route_table" "default"
    > Ansible
    1
    data "aws_availability_zones" "azs" {
    Concepts
    2
    #all_availability_zones = true
    3
    Ansible.MD
    M
    state = "available"
    4
    LP
    image-1.png
    5
    image.png
    6
    data "aws_vpc" "default" {
    {} person.json
    M
    7
    default = true
    person.xml
    8
    ! person.yaml
    9
    10
    > notes
    data "aws_route_table" "default" {
    11
    > Robosho-shellscripts
    vpc_id = data. aws_vpc . default.id
    M
    12
    filter {
    > roboshop-ansible
    13
    name = "association. main"
    > roboshop-ansible-roles
    14
    values = \["true" \]
    > shellscripts
    15
    > terraform
    16
    v terraform-aws-vpc
    data.tf
    U
    locals.tf
    U

[^53]: V REPOS
    terraform-aws-vpc > locals.tf > % locals
    > Ansible
    1
    locals {
    Concepts
    2
    name = "${var . project_name}-${var . environment}"
    3
    Ansible.MD
    M
    az_names = slice(data . aws_availability_zones . azs . names, 0, 2)
    image-1.png
    image.png
    () person.json
    M
    person.xml
    ! person.yaml
    notes
    > Robosho-shellscripts
    M
    > roboshop-ansible
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    terraform-aws-vpc
    data.tf
    U
    locals.tf
    U

[^54]: V REPOS
    terraform-aws-vpc > outputs.tf > % output "azs"
    > Ansible
    1
    V
    output "azs" {
    Concepts
    2
    value = data . aws_availability_zones . azs . names
    13
    Ansible.MD
    M
    4
    image-1.png
    15
    V
    output "vpc_id" {
    image.png
    6
    value = aws_vpc . main. id
    {} person.json
    M
    7
    person.xml
    18
    ! person.yaml
    9
    V
    output "public_subnet_ids" {
    > notes
    10
    O
    value = aws_subnet . public \[\*\].id
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    V
    output "private_subnet_ids" {
    > roboshop-ansible-roles
    14
    value = aws_subnet . private \[\*\].id
    > shellscripts
    15
    > terraform
    16
    terraform-aws-vpc
    17 v
    output "database_subnet_ids" {
    18
    data.tf
    U
    value = aws_subnet . database\[\*\]. id
    19
    locals.tf
    U
    20
    main.tf
    U
    outputs.tf
    U
    peering.tf
    C
    variables.tf
    U

[^55]: REPOS
    terraform-aws-vpc > variables.tf > $ variable "vpc_peering_tags"
    > Ansible
    1
    variable "vpc_cidr" {
    Concepts
    type = string
    W N
    Ansible.MD
    M
    default = "10.0.0.0/16" # users can override
    image-1.png
    image.png
    variable "enable_dns_hostnames"
    {} person.json
    M
    type = bool
    person.xml
    8
    default = true
    !
    person.yaml
    9
    > notes
    10
    11
    > Robosho-shellscripts
    variable "common_tags" {
    M
    12
    type = map
    > roboshop-ansible
    13
    default = {} # it is optional
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    variable "vpc_tags" {
    terraform-aws-vpc
    17
    O
    type = map
    data.tf
    18
    U
    default = {}
    19
    locals.tf
    U
    20
    main.tf
    U
    21
    variable "project_name" {
    outputs.tf
    U
    22
    type = string
    peering.tf
    U
    23
    variables.tf
    U
    24
    25
    > terraform-modules
    variable "environment" {
    26
    > terraform-multi-env
    type = string
    27
    > terraform-provisioners
    28
    v vpc-test
    29
    variable "igw_tags" {
    > .terraform
    30
    type = map
    .gitignore
    U
    31
    default = {}
    E .terraform.lock.hcl
    U
    32
    33
    main.tf
    U
    34
    variable "public_subnets_cidr" {
    outputs.if
    U
    35
    type = list
    provider.tf
    U
    36
    validation {
    variables.tf
    U
    37
    condition = length(var . public_subnets_cidr) == 2
    38
    error_message = "Please give 2 public valid subnet CIDR"
    39
    40
    41
    42
    variable "public_subnets_tags" {
    > OUTLINE
    43
    default = {}
    TIMELINE
    44
    }

[^56]: 45
    46
    variable "private_subnets_cidr" {
    47
    type = list
    48
    validation {
    49
    condition = length(var . private_subnets_cidr) == 2
    50
    error_message = "Please give 2 private valid subnet CIDR"
    51
    52
    53
    54
    variable "private_subnets_tags" {
    55
    default = {}
    56
    57
    58
    variable "database_subnets_cidr" {
    59
    type = list
    60
    validation {
    61
    condition = length(var . database_subnets_cidr) == 2
    62
    error_message = "Please give 2 private valid subnet CIDR"
    63
    64
    65
    66
    variable "database_subnets_tags" {
    67
    default = {}
    68
    69
    70
    variable "nat_gateway_tags" {
    71
    default = {}
    72
    73
    74
    variable "public_route_table_tags" {
    75
    default = {}
    76
    }
    77
    78
    variable "private_route_table_tags" {
    79
    default = {}
    80
    81
    82
    variable "database_route_table_tags" {
    83
    default = {}
    84
    85
    86
    variable "is_peering_required" {
    87
    type = bool
    88
    default = false

[^57]: 89
    90
    91
    variable "acceptor_vpc_id" {
    92
    type = string
    93
    default = ""
    94
    95
    96
    variable . "vpc_peering_tags" {
    97
    default =.{}
    98
    99

[^58]: REPOS
    vpc-test > main.tf > $ module "roboshop"
    > Ansible
    1
    module "roboshop" {
    Concepts
    N
    source = " . ./terraform-aws-vpc"
    Ansible.MD
    3
    M
    project_name = var . project_name
    4
    image-1.png
    environment = var . environment
    5
    common_tags = var . common_tags
    image.png
    6
    vpc_tags = var . vpc_tags
    {} person.json
    M
    7
    person.xml
    18
    # public subnet
    person.yaml
    9
    public_subnets_cidr = var . public_subnets_cidr
    10
    > notes
    11
    > Robosho-shellscripts
    # private subnet
    M
    12
    private_subnets_cidr = var . private_subnets_cidr
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    # database subnet
    > shellscripts
    15
    database_subnets_cidr = var . database_subnets_cidr
    > terraform
    16
    terraform-aws-vpc
    17
    .# peering
    data.tf
    U
    18
    is_peering_required = var . is_peering_required
    19
    locals.tf
    U
    20
    main.tf
    U
    outputs.tf
    U
    peering.tf
    U
    variables.tf
    U
    > terraform-modules
    > terraform-multi-env
    > terraform-provisioners
    v vpc-test
    > .terraform
    .gitignore
    U
    E .terraform.lock.hcl
    U
    main.tf
    U
    outputs.tf
    U
    provider.tf
    U
    variables.tf
    U

[^59]: vpc-test > outputs.tf > % output "azs"
    output "azs" {
    2
    value = module . roboshop . azs
    3

[^60]: REPOS
    vpc-test > variables.tf > variable "is_peering_required"
    > Ansible
    1
    variable "vpc_cidr" {
    Concepts
    N
    default = "10.0.0.0/16"
    3
    Ansible.MD
    M
    4
    variable "common_tags" {
    image-1.png
    15
    default = {
    image.png
    6
    Project = "roboshop"
    {} person.json
    M
    7
    Environment = "dev"
    person.xml
    8
    Terraform = "true"
    person.yaml
    9
    10
    > notes
    11
    > Robosho-shellscripts
    M
    12
    variable "vpc_tags" {
    > roboshop-ansible
    13
    default = {}
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    > terraform
    16
    variable "project_name" {
    terraform-aws-vpc
    17
    default = "roboshop"
    data.tf
    18
    U
    19
    locals.tf
    U
    20
    variable "environment" {
    main.tf
    U
    21
    default = "dev"
    outputs.tf
    U
    22
    peering.tf
    U
    23
    variables.tf
    U
    24
    variable "public_subnets_cidr" {
    > terraform-modules
    25
    default = \["10.0.1.0/24", "10.0.2.0/24"\]
    26
    > terraform-multi-env
    27
    > terraform-provisioners
    28
    variable "private_subnets_cidr" {
    v vpc-test
    29
    default = \["10.0.11.0/24", "10.0.12.0/24"\]
    > .terraform
    30
    .gitignore
    U
    31
    E .terraform.lock.hcl
    U
    32
    variable "database_subnets_cidr" {
    33
    main.tf
    U
    default = \["10.0.21.0/24", "10.0.22.0/24"\]
    34
    outputs.tf
    U
    35
    provider.tf
    36
    variable ."is_peering_required" {
    variables.tf
    U
    37
    default = true
    38

[^61]: chowd@Chowdary MINGW64 /e/AWSDevops /Repos /vpc-test (main)
    $ terraform apply -auto-approve
    Acquiring state lock. This may take a few moments
    module . roboshop . aws_eip . eip: Refreshing state. .. \[id=eipalloc-055cc570a515c72f7\]
    module . roboshop . data . aws_vpc . default: Reading. . .
    module . roboshop . data. aws_availability_zones . azs : Reading. . .
    module . roboshop . aws_vpc. main: Refreshing state. . . \[id=vpc-05afe4f4coldfbbf1\]
    module . roboshop . data . aws_availability_zones . azs: Read complete after 1s \[id=us-east-1\]
    module . roboshop . data . aws_vpc . default: Read complete after 3s \[id=vpc-0817cae8968304c06\]
    module . roboshop . data . aws_route_table . default: Reading. . .
    module . roboshop . data. aws_route_table . default: Read complete after Os \[id=rtb-Obfe8282f6ae865ab\]
    module . roboshop . aws_route_table . database: Refreshing state. .. \[id=rtb-06d43d8a1261a6635\]
    module . roboshop . aws_subnet . database \[0\]: Refreshing state. . . \[id=subnet-09ee65813661d8ce3\]
    module . roboshop . aws_vpc_peering_connection . peering \[0\]: Refreshing state. . . \[id=pcx-05347f513cae78814\]
    module . roboshop . aws_subnet . private \[0\]: Refreshing state. . . \[id=subnet-024bfec0456e6d31e\]
    module . roboshop . aws_internet_gateway . gw: Refreshing state. . . \[id=igw-01ce67abb19453fc7\]
    module . roboshop . aws_subnet . database \[1\] : Refreshing state. . . \[id=subnet-07c033a375345e295\]
    module . roboshop . aws_route_table . private: Refreshing state. . . \[id=rtb-01cd452630a7dc3ac\]
    module . roboshop . aws_subnet . public \[0\]: Refreshing state. . . \[id=subnet-072e6cb96dd3d50f9\]
    module . roboshop . aws_route_table . public: Refreshing state. .. \[id=rtb-08a8000c916dfd74b\]
    module . roboshop . aws_subnet . private \[1\]: Refreshing state. . . \[id=subnet-0ba4ae34bf73de91c\]
    module . roboshop . aws_subnet . public \[1\]: Refreshing state. . . \[id=subnet-0c41a0fdc9efacade\]

[^62]: 1. create VPC
    2. create igw and attach
    3. create all subnets
    4. create route tables
    5. create routes
    6. associate with subnets
    7. create eip
    8. create nat
    9. add nat gateway route in private and database subnets
    10. peering connection
    11. routes

[^63]: -
    Name
    D
    VPC ID
    State
    D
    IPV4 CIDR
    4
    IPV6 CIDR
    roboshop-dev
    vpc-05afe4f4cb 1dfbbf1
    Available
    10.0.0.0/16
    vpc-0817 cae8968304c06
    Available
    172.31.0.0/16

[^64]: Subnets (12) Info
    G
    Actions
    Create subnet
    Q Find resources by attribute or tag
    <
    1 >
    Name
    Subnet ID
    4
    State
    V
    VPC
    V IPV4 CIDR
    subnet-U6/6562456ya64feb
    Available
    vpc-081 /caedyb8504cub
    1/2.51.80.0/20
    subnet-0873e3231bac49c20
    Available
    vpc-0817cae8968304c06
    172.31.64.0/20
    subnet-076650bcf0b486323
    Available
    vpc-0817cae8968304c06
    172.31.16.0/20
    subnet-Od3fb05110e2d9e48
    Available
    vpc-0817cae8968304c06
    172.31.48.0/20
    roboshop-dev-database-us-east-1a
    subnet-09ee65813661d8ce3
    Available
    vpc-05afe4f4cb 1dfbbf1 \| robos...
    10.0.21.0/24
    roboshop-dev-database-us-east-1b
    subnet-07c033a375345e295
    Available
    vpc-05afe4f4cb1dfbbf1 \| robos...
    10.0.22.0/24
    roboshop-dev-private-us-east-1a
    subnet-024bfec0456e6d31e
    Available
    vpc-05afe4f4cb1dfbbf1 \| robos...
    10.0.11.0/24
    O
    roboshop-dev-private-us-east-1b
    subnet-Oba4ae34bf73de91c
    Available
    vpc-05afe4f4cb 1dfbbf1 \| robos...
    10.0.12.0/24
    roboshop-dev-public-us-east-1a
    subnet-072e6cb96dd3d50f9
    Available
    vpc-05afe4f4cb1dfbbf1 \| robos...
    10.0.1.0/24
    roboshop-dev-public-us-east-1b
    subnet-Oc41a0fdc9efacade
    Available
    vpc-05afe4f4cb 1dfbbf1 \| robos...
    10.0.2.0/24

[^65]: Route tables (5) Info
    C
    Actions
    Q Find resources by attribute or tag
    Name
    4
    Route table ID
    4
    Explicit subnet associ... V Edge associations
    Mail
    rtb-Obfe8282f6ae865ab
    Yes
    rtb-Oda95a40c6a592ae6
    -
    Yes
    roboshop-dev-database
    rtb-06d43d8a 1261a6635
    2 subnets
    No
    roboshop-dev-public
    rtb-08a8000c916dfd74b
    2 subnets
    -
    No
    roboshop-dev-private
    rtb-01cd452630a7dc3ac
    2 subnets
    No

[^66]: Internet gateways (1/2) Info
    G
    Actions
    Create internet
    Q Search
    <
    1
    -
    Name
    4
    Internet gateway ID
    4
    State
    4
    VPC ID
    D
    V
    roboshop-dev
    igw-01ce67abb 19453fc7
    Attached
    vpc-05afe4f4cb 1dfbbf1 \| roboshop-dev
    n
    igw-059405258c34db2a1
    Attached
    vpc-0817 cae8968304c06

[^67]: Elastic IP addresses (1/1)
    C
    Actions
    Alloca
    Find resources by attribute or tag
    V
    Name
    4
    Allocated IPv4 addr... > Type
    4
    Allocation ID
    V
    3.234.54.77
    Public IP
    eipalloc-055cc570a515c72f7

[^68]: NAT gateways (1) Info
    G
    Actions
    Create NAT gateway
    Q Find resources by attribute or tag
    < 1 >
    Name
    4
    NAT gateway ID
    Connectivity...
    State
    V
    State message
    4
    Primary public I...
    4
    Prima
    O
    roboshop-dev
    nat-0909177eafe5caff4
    Public
    Available
    3.234.54.77
    10.0.

[^69]: V
    roboshop-dev-public
    rtb-08a8000c916dfd74b
    2 subnets
    No
    roboshop-dev-private
    rtb-01cd452630a7dc3ac
    2 subnets
    No
    rtb-08a8000c916dfd74b / roboshop-dev-public
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (3)
    Both
    Q Filter routes
    Destination
    4
    Target
    A
    Status
    Propagated
    0.0.0.0/0
    igw-01ce67abb 19453fc7
    Active
    No
    10.0.0.0/16
    local
    Active
    No
    172.31.0.0/16
    pcx-05347f513cae78814
    Active
    No

[^70]: REPOS
    terraform-aws-vpc > peering.tf > % resource "aws_vpc_peering_connection" "peering"
    > Ansible
    1
    resource "aws_vpc_peering_connection" "peering" {
    Concepts
    2
    count = var . is_peering_required ? 1 : 0
    Ansible.MD
    M
    3
    vpc_id = aws_vpc . main. id
    4
    peer_vpc_id = var . acceptor_vpc_id == "" ? data. aws_vpc . default. id : var . acceptor_vpc_id
    image-1.png
    5
    auto_accept = var . acceptor_vpc_id == "" ? true : false
    image.png
    6
    tags = merge(
    {} person.json
    M
    7
    var . common_tags,
    person.xml
    8
    var . vpc_peering_tags,
    person.yaml
    9
    10
    > notes
    Name = "$ {local. name}"
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    > shellscripts
    > terraform
    terraform-aws-vpc
    data.tf
    U
    locals.tf
    U
    main.tf
    outputs.tf
    CCC
    peering.tf -

[^71]: type
    terraform-aws-vpc
    88
    default = false
    data.tf
    89
    locals.tf
    90
    main.tf
    91
    variable "acceptor_vpc_id" {
    CCCCCC
    outputs.tf
    92
    type = string
    93
    default = ""
    Y
    peering.tf
    94
    variables.tf
    95
    > terraform-modules
    96
    variable . "vpc_peering_tags" {
    > terraform-multi-env
    97
    default = {}
    > terraform-provisioners
    98

[^72]: V vpc-test
    32
    > .terraform
    variable "database_subnets_cidr" {
    33
    default = \["10.0.21.0/24", "10.0.22.0/24"\]
    .gitignore
    34
    E .terraform.lock.hcl
    35
    main.tf
    36
    variable ."is_peering_required" {
    CCCCCC
    outputs.tf
    37
    default = . true
    provider.tf
    38
    variables.tf

[^73]: 10
    notes
    11
    > Robosho-shellscripts
    # private subnet
    M
    12
    private_subnets_cidr = var . private_subnets_cidr
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    # database subnet
    > shellscripts
    15
    database_subnets_cidr = var . database_subnets_cidr
    > terraform
    16
    > terraform-aws-vpc
    17
    #
    peering
    18
    > terraform-modules
    is_peering_required = var . is_peering_required
    19
    > terraform-multi-env
    20
    > terraform-provisioners
    v vpc-test
    > .terraform
    gitignore
    E .terraform.lock.hcl
    main.tf
    C C C CC
    outputs.tf
    provider.tf

[^74]: erraform used the selected providers to generate the following execution
    lan. Resource actions are indicated with the following symbols:
    + create
    erraform will perform the following actions :
    # module . roboshop . aws_vpc_peering_connection . peering \[0\] will be created
    +
    resource "aws_vpc_peering_connection" "peering" {
    accept_status = (known after apply)
    auto_accept
    =
    true
    id
    (known after apply)
    peer_owner_id
    (known after apply)
    peer_region
    (known after apply)
    peer_vpc_id
    =
    "vpc-0817 cae8968304c06"
    tags
    =
    "Environment"
    "dev"
    "Name"
    "roboshop-dev"
    "Project"
    "roboshop"
    +
    "Terraform"
    "true"
    +
    tags_a11
    "Environment"
    E
    "dev"
    "Name"
    E
    "roboshop-dev"
    +
    "Project"
    E
    "roboshop"
    +
    "Terraform"
    "true"
    vpc_id
    = "vpc-05afe4f4cbidfbbf1"
    lan: 1 to add, 0 to change, 0 to destroy.
    Note: You didn't use the -out option to save this plan, so Terraform can't
    uarantee to take exactly these actions if you run "terraform apply" now.
    eleasing state lock. This may take a few moments . . .

[^75]: Terraform will perform the following actions:
    # module . roboshop . aws_vpc_peering_connection . peering \[0\] will be created
    resource "aws_vpc_peering_connection" "peering" {
    accept_status = (known after apply)
    +
    auto_accept
    = true
    id
    = (known after apply)
    peer_owner_id
    E
    (known after apply)
    peer_region
    (known after apply)
    peer_vpc_id
    "vpc-0817cae8968304c06"
    tags
    E
    "Environment"
    E
    "dev"
    +
    "Name"
    "roboshop-dev"
    +
    "project"
    = "roboshop"
    +
    "Terraform"
    =
    "true"
    }
    +
    tags_al1
    E
    {
    "Environment
    "dev"
    +
    "Name"
    "roboshop-dev"
    +
    "Project"
    E
    "roboshop"
    +
    "Terraform"
    = "true"
    + vpc_id
    = "vpc-05afe4f4cb1dfbbf1"
    Plan: 1 to add, 0 to change, 0 to destroy.
    module . roboshop . aws_vpc_peering_connection . peering \[0\]: Creating. . .
    module . roboshop . aws_vpc_peering_connection . peering \[0\]: Creation complete after 3s \[id=pcx-05347f513cae78814\]
    Releasing state lock. This may take a few moments . . .
    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

[^76]: Peering connections (1) Info
    C
    Actions
    Create peering connection
    Q Find resources by attribute or tag
    <
    1 >
    Name
    A
    Peering connection ID
    4
    Status
    Requester VPC
    Accepter VPC
    Requester CIDRs
    Accepter CIDRs
    roboshop-dev
    pcx-05347f513cae78814
    Active
    vpc-05afe4f4cb 1dfbbf1 / robos...
    vpc-0817 cae8968304c06
    10.0.0.0/16
    172.31.0.0/16

[^77]: REPOS
    terraform-aws-vpc > peering.tf > $ resource "aws_route" "database_peering"
    > Ansible
    resource "aws_vpc_peering_connection" "peering"
    Concepts
    WN H
    count = var . is_peering_required ? 1 : 0
    Ansible.MD
    M
    vpc_id = aws_vpc. main . id
    image-1.png
    peer_vpc_id = var . acceptor_vpc_id == "" ? data. aws_vpc. default. id : var . acceptor_vpc_id
    auto_accept = var . acceptor_vpc_id == "" ? true : false
    image.png
    9
    tags = merge(
    \[} person.json
    M
    7
    var . common_tags,
    person.xml
    8
    var . vpc_peering_tags,
    person.yaml
    9
    10
    > notes
    Name = "${local. name}"
    11
    > Robosho-shellscripts
    M
    12
    > roboshop-ansible
    13
    > roboshop-ansible-roles
    14
    > shellscripts
    15
    resource "aws_route" "acceptor_route" {
    > terraform
    16
    count = var . is_peering_required && var . acceptor_vpc_id == "" ? 1 : 0
    v terraform-aws-vpc
    17
    route_table_id
    = data . aws_route_table . default.id
    data.tf
    U
    18
    destination_cidr_block
    = var . vpc_cidr
    19
    locals.tf
    U
    vpc_peering_connection_id = aws_vpc_peering_connection . peering\[0\].id
    20
    }
    main.tf
    U
    21
    outputs.tf
    U
    22
    resource "aws_route" "public_peering" {
    peering.tf
    U
    23
    count = var . is_peering_required && var . acceptor_vpc_id == "" ? 1 : 0
    variables.tf
    24
    route_table_id
    = aws_route_table. public. id
    > terraform-modules
    25
    destination_cidr_block
    = data . aws_vpc . default. cidr_block
    26
    > terraform-multi-env
    vpc_peering_connection_id = aws_vpc_peering_connection . peering\[0\]. id
    27
    > terraform-provisioners
    28
    v vpc-test
    29
    resource "aws_route" "private_peering" {
    > .terraform
    30
    count = var . is_peering_required && var . acceptor_vpc_id == "" ? 1 : 0
    .gitignore
    U
    31
    route_table_id
    aws_route_table. private. id
    E.terraform.lock.hcl
    U
    32
    destination_cidr_block
    = data . aws_vpc. default . cidr_block
    33
    main.tf
    U
    vpc_peering_connection_id = aws_vpc_peering_connection . peering\[0\]. id
    34
    outputs.tf
    U
    35
    provider.tf
    U
    36
    resource "aws_route" "database_peering" {
    variables.tf
    U
    37
    count = var . is_peering_required && var . acceptor_vpc_id == "" ? 1 : 0
    38
    route_table_id
    = aws_route_table. database. id
    39
    destination_cidr_block
    = data. aws_vpc . default. cidr_block
    40
    vpc_peering_connection_id = aws_vpc_peering_connection . peering\[0\]. id
    41

[^78]: EXPLORER
    . .
    main.tf terraform-aws-vpc U
    locals.tf U
    data.tf terraform-aws-vpc U X
    REPOS
    terraform-aws-vpc > data.tf > $ data "aws_route_table" "default"
    > Ansible
    1
    data "aws_availability_zones" "azs" {
    Concepts
    2
    #all_availability_zones = true
    3
    Ansible.MD
    M
    state = "available"
    14
    image-1.png
    5
    image.png
    16
    data "aws_vpc" "default" {
    {} person.json
    M
    7
    default = true
    person.xml
    18
    ! person.yaml
    9
    10
    > notes
    data "aws_route_table" "default" {
    11
    vpc_id = data . aws_vpc . default.id
    > Robosho-shellscripts
    M
    12
    filter {
    > roboshop-ansible
    13
    name = "association.main"
    > roboshop-ansible-roles
    14
    values = \["true" \]
    > shellscripts
    15
    > terraform
    16
    terraform-aws-vpc
    data.tf
    U
    locals.tf
    U

[^79]: # module . roboshop . aws_route . public_peering\[0\] will be created
    +
    resource "aws_route" "public_peering" {
    +
    destination_cidr_block
    =
    "172 . 31. 0.0/16"
    +
    id
    =
    (known after apply)
    +
    instance_id
    (known after apply)
    +
    instance_owner_id
    (known after apply)
    network_interface_id
    (known after apply)
    origin
    E
    (known after apply)
    route_table_id
    "rtb-08a8000c916dfd74b"
    +
    state
    E
    (known after apply)
    + vpc_peering_connection_id = "pcx-05347f513cae78814"
    Plan: 4 to add, 0 to change, 0 to destroy.
    module . roboshop . aws_route . public_peering \[0\] : Creating. . .
    module . roboshop . aws_route . acceptor_route \[0\]: Creating. ..
    module . roboshop . aws_route . database_peering \[0\]: Creating. . .
    module . roboshop . aws_route . private_peering \[0\] : Creating. . .
    module . roboshop . aws_route . acceptor_route \[0\]: Creation complete after 2s \[id=r-rtb-Obfe8282f6ae865ab179966490\]
    module . roboshop . aws_route . public_peering \[0\]: Creation complete after 2s \[id=r-rtb-08a8000c916dfd74b3854007479\]
    module . roboshop . aws_route . database_peering \[0\]: Creation complete after 2s \[id=r-rtb-06d43d8a1261a66353854007479\]
    module . roboshop . aws_route . private_peering \[0\]: Creation complete after 3s \[id=r-rtb-01cd452630a7dc3ac3854007479\]
    Releasing state lock. This may take a few moments. .
    Apply complete! Resources : 4 added, 0 changed, 0 destroyed.

[^80]: Route tables (1/5) Info
    C
    Actions
    Create route table
    Q Find resources by attribute or tag
    1 >
    -
    Name
    V
    Route table ID
    V
    Explicit subnet associ... V Edge associations
    Main
    4
    VPC
    - 2
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817 cae896830
    O
    rtb-Oda95a40c6a592ae6
    I
    Yes
    vpc-05afe4f4cb 1dfb
    V
    roboshop-dev-database
    rtb-06d43d8a 1261a6635
    2 subnets
    No
    vpc-05afe4f4cb 1dfb
    O
    roboshop-dev-public
    rtb-08a8000c916dfd74b
    2 subnets
    No
    vpc-05afe4f4cb 1dfb
    roboshop-dev-private
    rtb-01cd452630a7dc3ac
    2 subnets
    No
    vpc-05afe4f4cb 1dfb
    rtb-06d43d8a 1261a6635 / roboshop-dev-database
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (3)
    Both
    Edit routes
    Q Filter routes
    <
    Destination
    V
    Target
    A
    Status
    Propagated
    0.0.0.0/0
    nat-0909177eafe5caff4
    Active
    No
    10.0.0.0/16
    local
    Active
    No
    172.31.0.0/16
    pcx-05347f513cae78814
    Active
    No

[^81]: Route tables (1/5) Info
    Actions
    Create route table
    Find resources by attribute or tag
    < 1 >
    -
    Name
    4
    Route table ID
    4
    Explicit subnet associ...
    V
    Edge associations
    Main
    4
    VPC
    V
    rtb-Obfe8282f6ae865ab
    Yes
    vpc-0817cae896830
    O
    rtb-Oda95a40c6a592ae6
    Yes
    vpc-05afe4f4cb 1dfb
    0
    roboshop-dev-database
    rtb-06d43d8a 1261a6635
    2 subnets
    No
    vpc-05afe4f4cb 1dfb
    0
    roboshop-dev-public
    rtb-08a8000c916dfd74b
    2 subnets
    No
    vpc-05afe4f4cb 1dfb
    roboshop-dev-private
    rtb-01cd452630a7dc3ac
    2 subnets
    No
    vpc-05afe4f4cb 1dfb
    rtb-Obfe8282f6ae865ab
    Details
    Routes
    Subnet associations
    Edge associations
    Route propagation
    Tags
    Routes (3)
    Both
    Edit routes
    Q Filter routes
    < 1 >
    Destination
    4
    Target
    Status
    V
    Propagated
    0.0.0.0/0
    igw-059405258c34db2a1
    Active
    No
    10.0.0.0/16
    pcx-05347f513cae78814
    Active
    No
    172.31.0.0/16
    local
    Active
    No

[^82]: module . roboshop . aws_subnet . private \[1\]: Destruction complete after 1s
    module . roboshop . aws_route . public_peering \[0\]: Destruction complete after 2s
    module . roboshop . aws_vpc_peering_connection . peering \[0\] : Destroying. . . \[id=pcx-053
    47f513cae78814\]
    module . roboshop . aws_route_table. public: Destroying. .. \[id=rtb-08a8000c916dfd74b\]
    module . roboshop . aws_subnet . database \[1\]: Destruction complete after Is
    module . roboshop . aws_subnet . database \[0\]: Destruction complete after 1s
    module . roboshop . aws_vpc_peering_connection . peering \[0\] : Destruction complete afte
    Os
    module . roboshop . aws_route_table . database: Destruction complete after 1s
    module . roboshop . aws_route_table. private: Destruction complete after 2s
    module . roboshop . aws_route_table. public: Destruction complete after 1s
    module . roboshop . aws_nat_gateway . main: Still destroying. . . \[id=nat-0909177eafe5ca
    ff4, 10s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still destroying. .. \[id=nat-0909177eafe5ca

[^83]: E
    chilops
    Q Type to search
    +
    87
    D Overview
    Repositories 13 Projects Packages
    Stars
    Find a repository...
    Type
    Language
    Sort
    New
    vpc-test Public
    Star
    HCL Updated 4 minutes ago
    terraform-aws-vpc Public
    Star
    OHCL Updated 5 minutes ago

[^84]: vpc-test > main.tf > $ module "roboshop" > vpc_tags
    1
    module "roboshop" {
    2
    #source = ". ./terraform-aws-vpc"
    3
    source = "git: :https://github. com/chilops/terraform-aws-vpc . git?ref=main"
    4
    project_name = var . project_name
    5
    environment = var . environment
    16
    common_tags = var . common_tags
    7
    vpc_tags = var . vpc_tags
    8
    19
    # public subnet
    10
    public_subnets_cidr = var . public_subnets_cidr
    11
    12
    # private subnet
    13
    private_subnets_cidr = var . private_subnets_cidr
    14
    15
    # database subnet
    16
    database_subnets_cidr = var . database_subnets_cidr
    17
    18
    # peering
    19
    is_peering_required = var . is_peering_required
    20
    21

[^85]: chowd@chowdary MINGW64/
    $ cd e/ AWSDevops /Repos /vpc-test/
    chowd@chowdary MINGW64 /e/AWSDevops /Repos/vpc-test (main)
    $ terraform init
    Initializing the backend. ..
    Initializing modules . . .
    Downloading git: :https ://github.com/chilops/terraform-aws-vpc . git?ref=main for r
    oboshop . . .
    roboshop in . terraform modules roboshop
    Initializing provider plugins. ..
    Reusing previous version of hashicorp/aws from the dependency lock file
    -
    Using previously-installed hashicorp/aws v5 . 31.0
    Terraform has been successfully initialized!
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. Al1 Terraform commands
    should now work.
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    chowd@chowdary MINGW64 /e/AWSDevops /Repos/vpc-test (main)

[^86]: v vpc-test
    v .terraform
    v modules
    roboshop
    data.tf
    locals.tf
    main.tf
    outputs.tf
    peering.tf
    variables.tf
    {} modules.json
    > providers
    {} terraform.tfstate
    gitignore

[^87]: main.tf
    68
    outputs.tf
    69
    resource "aws_db_subnet_group" "default" {
    70
    peering.tf
    name
    = "${local. name}"
    71
    subnet_ids = aws_subnet . database \[\*\].id
    readme.MD
    72
    variables.tf
    73
    tags = {
    > terraform-modules
    74
    Name = "${local. name}"
    > terraform-multi-env
    75
    > terraform-provisioners
    76

[^88]: Plan: 28 to add, 0 to change, 0 to destroy.
    Changes to Outputs:
    azs = \[
    "us-east-la"
    "us-east-1b"
    "us-east-1c",
    "us-east-1d"
    "us-east-le"
    "us-east-1f"
    module . roboshop . aws_eip . eip: Creating. . .
    module . roboshop . aws_vpc . main: Creating. . .
    module . roboshop . aws_eip . eip: Creation complete after 3s \[id=eipalloc-0c4cc68078696f293\]
    module . roboshop . aws_vpc . main: Still creating. .. \[10s elapsed\]
    module . roboshop . aws_vpc . main: Creation complete after 16s \[id=vpc-Ocdb6a8b6b50f38a5\]
    module . roboshop . aws_internet_gateway . gw: Creating. . .
    module . roboshop . aws_subnet . public \[1\] : Creating. . .
    module . roboshop . aws_vpc_peering_connection . peering \[0\]: Creating. . .
    module . roboshop . aws_route_table . public: Creating. . .
    module . roboshop . aws_route_table . private: Creating. . .
    module . roboshop . aws_route_table . database: Creating. . .
    module . roboshop . aws_subnet . database \[0\] : Creating. . .
    module . roboshop . aws_subnet . public \[0\] : Creating. . .
    module . roboshop . aws_subnet . private \[0\] : Creating. . .
    module . roboshop . aws_subnet . database \[1\]: Creating. . .
    module . roboshop . aws_subnet . private \[0\]: Creation complete after 2s \[id=subnet-0425e2895c71a3e32\]

[^89]: module . roboshop . aws_hat_gateway . main: St1
    creating . . .
    \[30s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating.
    \[40s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating.
    \[50s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating..
    \[1mos elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating.
    \[1m10s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating.
    \[1m20s elapsed\]
    module . roboshop . aws_nat_gateway . main: Still creating. . . \[1m30s elapsed\]
    module . roboshop . aws_nat_gateway . main: Creation complete after 1m40s \[id=nat-028b2ccbd4ale11d2\]
    module . roboshop . aws_route . private_route: Creating. . .
    module . roboshop . aws_route . database_route: Creating. . .
    module . roboshop . aws_route . database_route: Creation complete after 3s \[id=r-rtb-05cca8e3ed8b6a9691080289494\]
    module . roboshop . aws_route . private_route: Creation complete after 3s \[id=r-rtb-0ad44f9eba44a07171080289494\]
    Releasing state lock. This may take a few moments.
    Apply complete! Resources: 28 added, 0 changed, 0 destroyed.

[^90]: aws
    Services
    Q Search
    \[Alt+S\]
    A
    ?)
    N. Virginia
    chow
    O EC2
    Route 53
    8: IAM
    VPC
    $3
    DynamoDB
    30 RDS
    Amazon RDS
    X
    RDS > Subnet groups
    Dashboard
    Subnet groups (1)
    C
    Edit
    Delete
    Create DB subnet group
    Databases
    Q Filter by subnet group
    1
    Query Editor
    Performance insights
    O
    Name
    Description
    4
    Status
    A
    VPC
    Snapshots
    roboshop-dev
    Managed by Terraform
    Complete
    vpc-Ocdb6a8b6b50f38a5
    Exports in Amazon $3
    Automated backups
    Reserved instances
    Proxies
    Subnet groups

[^91]: Subnet group details
    VPC ID
    vpc-Ocdb6a8b6b50f38a5 \[
    ARN
    arn:aws:rds:us-east-1:158724841371:subgrp:roboshop-dev
    Supported network types
    IPV4
    Description
    Managed by Terraform
    Subnets (2)
    Availability zone
    Subnet ID
    CIDR block
    us-east-1a
    subnet-0c000d56ea4145db9 \[
    10.0.21.0/24
    us-east-1b
    subnet-075codc3584fdc 105 \[Z
    10.0.22.0/24
    Tags (1)
    Manage tags
    Q Filter by Tag key
    1 )
    Tags
    Value
    Name
    roboshop-dev

[^92]: terraform aws vpc module
    X
    Q All Videos @ Images ) Books \~ Shopping : More
    Tools
    About 3,10,000 results (0.28 seconds)
    Terraform Registry
    https://registry.terraform.io > vpc > aws > latest
    terraform-aws-modulesAipc/aws \| Terraform Registry
    11 Dec 2023 - module "vpc" { source = "terraform-aws-modules/vpc/aws" name = "my-vpc"
    cidr = "10.0.0.0/16" azs = \["eu-west-1a", "eu-west-1b", ...
    Complete . Dependency (1) . Vpc-endpoints . Vpc-flow-logs

[^93]: Terraform
    Registry
    Q Search all resources
    Browse v
    vpc
    aws provider
    Version 5.5.0 (latest)
    aws
    Terraform module to create AWS VPC resources UA
    Published January 10, 2024 by terraform-aws-modules
    Module managed by antonbabenko
    Source Code: github.com/terraform-aws-modules/terraform-aws-vpc.(report an issue)
    Submodules
    Examples

[^94]: E
    terraform-aws-modules / terraform-aws-vpc
    Q Type to search
    <> Code
    Issues 14 17 Pull requests 5 Actions @ Security \~ Insights
    A GitHub users are now required to enable two-factor authentication as an additional security measure. Your activity on GitHub includes you in this requirement. You will
    authentication on your account before January 26, 2024, or be restricted from account actions.
    terraform-aws-vpc Public
    Sponsor
    Watch 79
    & master
    & 2 Branches 205 Tags
    Q Go to file
    Add file
    <> Code .
    E:3 semantic-release-bot chore(release): version 5.5.0 \[skip ci\] am
    e476850 . 6 hours ago
    443 Commits
    .github
    chore: Upgrade CI workflows to use non-deprecated runtim...
    2 years ago
    examples
    feat: Add support for dns_options on VPC endpoints (#1023)
    6 hours ago
    modules/vpc-endpoints
    feat: Add support for ans_options on VPC endpoints (#1023)
    6 hours ago
    D .editorconfig
    \[ci skip\] Create ".editorconfig".
    4 years ago
    O .gitignore
    chore: update documentation based on latest terraform-doc...
    3 years ago
    O .pre-commit-config.yaml
    feat: Add support for ans_options on VPC endpoints (#1023)
    6 hours ago
    D .releaserc.json
    chore: Update release configuration files to correctly use con...
    3 years ago
    CHANGELOG.md
    chore(release): version 5.5.0 \[skip ci\]
    6 hours ago

[^95]: O main.tf
    fix: The number of intra subnets should not influence the nu.
    4 months ago
    S
    O outputs.tf
    feat: Add Cross Account Flow Support (#1014)
    last month
    variables.tf
    feat: Add Cross Account Flow Support (#1014)
    last month
    D versions.tf
    feat: Add support for ans_options on VPC endpoints (#1023)
    6 hours ago

[^96]: Files
    terraform-aws-vpc / examples / 9
    & master
    +
    Q
    erezo9 and bryantbiggs feat: Add support for dns_options on VPC endpoints (#1023) .
    Q Go to file
    Name
    Last commit message
    .github
    v examples
    complete
    complete
    feat: Add support for ans_options on VPC endpoints (#1023)
    ipam
    ipam
    feat: Add support for ans_options on VPC endpoints (#1023)
    ipv6-dualstack
    ipv6-dualstack
    feat: Add support for ans_options on VPC endpoints (#1023)
    ipv6-only
    issues
    ipv6-only
    feat: Add support for dns_options on VPC endpoints (#1023)
    manage-default-vpc
    issues
    feat: Add support for dns_options on VPC endpoints (#1023)
    network-acls
    manage-default-vpc
    feat: Add support for dns_options on VPC endpoints (#1023)
    outpost
    network-acls
    secondary-cidr-blocks
    feat: Add support for dns_options on VPC endpoints (#1023)
    separate-route-tables
    outpost
    feat: Add support for dns_options on VPC endpoints (#1023)
    simple
    secondary-cidr-blocks
    feat: Add support for ans_options on VPC endpoints (#1023)
    vpc-flow-logs
    separate-route-tables
    feat: Add support for ans_options on VPC endpoints (#1023)
    modules
    O .editorconfig
    simple
    feat: Add support for dns_options on VPC endpoints (#1023)
    O .gitignore
    vpc-flow-logs
    feat: Add support for ans_options on VPC endpoints (#1023)
    \[ . pre-commit-config.yaml

