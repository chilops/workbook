---
title: 61Day_Kubernetes
uuid: e043608c-4586-11ef-a034-26e37c279344
version: 833
created: '2024-07-19T09:55:05+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#f8914d;">**Catalogue creation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![8b3f5333-cb13-4dee-b405-ee22c34898ec.png|791](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/8b3f5333-cb13-4dee-b405-ee22c34898ec.png) [^1]

\

git push & pull

![c6dd3ccc-62fc-49c4-9851-4730e679c2ed.png|950](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/c6dd3ccc-62fc-49c4-9851-4730e679c2ed.png) [^2]

\

\

```
helm install catalogue .
```

![c1cdeb93-c476-4bde-a1ad-1f906b022a52.png|948.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/c1cdeb93-c476-4bde-a1ad-1f906b022a52.png) [^3]

![ce6c7677-9fd4-460c-928a-be2bd2f2e2b4.png|1156.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ce6c7677-9fd4-460c-928a-be2bd2f2e2b4.png) [^4]

\

\

to check logs of catalogue press 'L'   -- Mongodb connected

![10778a14-c15c-443e-939c-b1ad8bbda693.png|1194.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/10778a14-c15c-443e-939c-b1ad8bbda693.png) [^5]

# <mark style="background-color:#f8914d;">**Horizontal scaling vs vertical scaling**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

**Vertical scaling** - We can increase CPU, RAM, HD

**Horizontal scaling** - Increases no of PODS based of traffic

\

![3a502df7-46e8-41ba-ac05-3516f74ad48c.png|631](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/3a502df7-46e8-41ba-ac05-3516f74ad48c.png) [^6]

\

# <mark style="background-color:#f8914d;">**User creation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d70d8b64-adb2-4c58-9938-1bc544a4f626.png) [^7]

\

git push & pull

![b9ee553d-0745-400a-85f7-4df2243dc029.png|896](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/b9ee553d-0745-400a-85f7-4df2243dc029.png) [^8]

\

```
helm install user .
```

![6a4f78a4-e374-474a-84ef-934ecdca0d1c.png|1082.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/6a4f78a4-e374-474a-84ef-934ecdca0d1c.png) [^9]

\

user pod creating

![d180934d-9e56-4969-be10-611cdce789f5.png|1205.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d180934d-9e56-4969-be10-611cdce789f5.png) [^10]

\

# <mark style="background-color:#f8914d;">**Cart creation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![2932910f-6b47-40cf-873f-373b2af8ea31.png|964](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/2932910f-6b47-40cf-873f-373b2af8ea31.png) [^11]

\

git push & pull

![](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/17d766b5-937e-4d0a-9155-adeefada33bc.png) [^12]

\

```
helm install cart .
```

![f3a50a34-846c-49e0-89a3-4dac0a9ea833.png|1079.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/f3a50a34-846c-49e0-89a3-4dac0a9ea833.png) [^13]

\

cart POD creating

![3ba4746a-7cc0-43bc-804e-5c3c6d2e6e6e.png|1079.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/3ba4746a-7cc0-43bc-804e-5c3c6d2e6e6e.png) [^14]

\

\

# <mark style="background-color:#f8914d;">**Shipping creation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![8336c719-9747-4e60-93e9-f9dc0e3e0656.png|993](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/8336c719-9747-4e60-93e9-f9dc0e3e0656.png) [^15]

\

git push & pull

![](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/17d766b5-937e-4d0a-9155-adeefada33bc.png) [^16]

\

```
helm install shipping .
```

![7f1ce95f-1dca-45df-81d0-84cc2e7f1276.png|1108.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/7f1ce95f-1dca-45df-81d0-84cc2e7f1276.png) [^17]

\

shipping POD creating

![4a84525e-0e09-4c1c-8b7c-281209999d41.png|1088.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/4a84525e-0e09-4c1c-8b7c-281209999d41.png) [^18]

\

<mark>**OOM error**</mark> - It means memory is not enough

Node out of memory causes a ***MemoryPressure*** and and pod eviction. (since shipping is a java application it needs more memory)

![f8f92527-15d8-4605-bef7-5f1873a9c4ea.png|1157.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/f8f92527-15d8-4605-bef7-5f1873a9c4ea.png) [^19]

\

\

Now increase the memory

![11f74d65-73ed-4de4-b05b-1ab80e2f1833.png|1027.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/11f74d65-73ed-4de4-b05b-1ab80e2f1833.png) [^20]

\

git push & pull

![f895b14f-e53c-4218-a1f3-798bbf42d251.png|1112.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/f895b14f-e53c-4218-a1f3-798bbf42d251.png) [^21]

\

```
helm upgrade shipping .
```

![a6661702-418a-4fc8-8a3d-4d5177e69c1b.png|1137.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/a6661702-418a-4fc8-8a3d-4d5177e69c1b.png) [^22]

\

Now its running

![0658e597-4565-46ff-9962-6dd56a16ea5f.png|1142.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/0658e597-4565-46ff-9962-6dd56a16ea5f.png) [^23]

# <mark style="background-color:#f8914d;">**Payment creation**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![ffd7b457-9734-4cc6-9e49-859adc9b296b.png|788](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ffd7b457-9734-4cc6-9e49-859adc9b296b.png) [^24]

\

git push & pull

![1ebf60fc-4148-4901-adeb-ad3ae4bdad37.png|915](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/1ebf60fc-4148-4901-adeb-ad3ae4bdad37.png) [^25]

\

```
helm install payment .
```

![0a8ac54e-8f8f-4979-bfef-439c6939bc38.png|1069.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/0a8ac54e-8f8f-4979-bfef-439c6939bc38.png) [^26]

\

pod creating

![6a7bb4ea-7f50-4988-bcab-ef6836d8b41d.png|1163.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/6a7bb4ea-7f50-4988-bcab-ef6836d8b41d.png) [^27]

\

\

# <mark style="background-color:#f8914d;">**Ingress controller**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![9ff19e7c-8373-49db-a890-c1cf4dba94b6.png|815.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/9ff19e7c-8373-49db-a890-c1cf4dba94b6.png) [^28]

\

A small example - APP1

![228e1095-634f-4c57-93ec-66b1e9d23a6c.png|973](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/228e1095-634f-4c57-93ec-66b1e9d23a6c.png) [^29]

\

App2

![905864e5-56ca-4225-9f41-d7ab59adee12.png|974.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/905864e5-56ca-4225-9f41-d7ab59adee12.png) [^30]

\

create REPO

![1cddd9f8-043a-420a-8a1a-35e62807f333.png|829.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/1cddd9f8-043a-420a-8a1a-35e62807f333.png) [^31]

\

![839a873b-1f33-4819-9d91-14c753a46b6f.png|1059](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/839a873b-1f33-4819-9d91-14c753a46b6f.png) [^32]

![1e25b311-87d2-4d99-9dbe-13971d9ab59f.png|1138.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/1e25b311-87d2-4d99-9dbe-13971d9ab59f.png) [^33]

\

Moving to default namespace

```
kubens default
```

![d1f225a2-73d0-4c7e-9104-e72e4810cceb.png|1080.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d1f225a2-73d0-4c7e-9104-e72e4810cceb.png) [^34]

Building images and push

```
docker build -t joindevops/ingress1:v1 .
```

![f8f6f702-da90-4950-89b5-ec36cc06ff95.png|1153.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/f8f6f702-da90-4950-89b5-ec36cc06ff95.png) [^35]

\

docker login to push the images

```
docker login
```

![4b547dd5-8549-4776-a125-761d17336355.png|1144.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/4b547dd5-8549-4776-a125-761d17336355.png) [^36]

\

```
docker push <your image>
```

![8ac79060-7351-4c09-96ba-2eb7e0863335.png|1143.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/8ac79060-7351-4c09-96ba-2eb7e0863335.png) [^37]

\

\

same of app2

```
cd ../app2/
docker build -t joindevops/ingress2:v1 .
```

![8385c8b0-a418-4d4a-ab01-573d7b3131cc.png|1150.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/8385c8b0-a418-4d4a-ab01-573d7b3131cc.png) [^38]

\

docker push <your image>

```
docker push <your image>
```

![2bc49423-777c-40d4-8a99-a39a08cdb981.png|1175.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/2bc49423-777c-40d4-8a99-a39a08cdb981.png) [^39]

\

<mark>**Now discussing about Ingress Resource**</mark>

![ffd1731d-4432-46c7-a3ea-aafe071363c0.png|1180.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ffd1731d-4432-46c7-a3ea-aafe071363c0.png) [^40]

\

![573cf320-ce46-4648-935f-fd2681afa54f.png|637](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/573cf320-ce46-4648-935f-fd2681afa54f.png) [^41]

\

![d3d2f501-fa83-4890-b1ec-66a9fb18e5eb.png|848](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d3d2f501-fa83-4890-b1ec-66a9fb18e5eb.png) [^42]

\

<mark>**Installing ingress controller**</mark>

\

Link -- [Installation Guide - AWS Load Balancer Controller (kubernetes-sigs.github.io)](https://kubernetes-sigs.github.io/aws-load-balancer-controller/v2.7/deploy/installation/) 

We can use latest version also 

Here is the documentation version v2.7

![fe5ba7ba-0da7-4dfd-8592-4a9479612eca.png|934.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/fe5ba7ba-0da7-4dfd-8592-4a9479612eca.png) [^43]

\

\

**Step 1**

OIDC - OpenID connect   (change our cluster name & region)

```
eksctl utils associate-iam-oidc-provider
-- region us-east-1 \
-- cluster roboshop \
-- approve
```

![590167b3-e600-4da4-95cd-7228c7ccdbb0.png|1043.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/590167b3-e600-4da4-95cd-7228c7ccdbb0.png) [^44]

\

**Step 2**

This will create one IAM policy

```
curl -o iam-policy.json
https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.7.0/docs/ins
tall/iam policy.json
```

![92a6fbba-1820-4455-a98c-27a76e2a39a0.png|1056.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/92a6fbba-1820-4455-a98c-27a76e2a39a0.png) [^45]

\

**Step 3**

```
aws iam create-policy \
-- policy-name AWSLoadBalancerControllerIAMPolicy \
-- policy-document file://iam-policy.json
```

![7f205da4-f0e3-4a8f-a7fd-4043a93b24ff.png|1124.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/7f205da4-f0e3-4a8f-a7fd-4043a93b24ff.png) [^46]

\

**Step 4**

change - cluster name, account id, region

```
eksctl create iamserviceaccount \
-- cluster=roboshop \
-- namespace=kube-system \
-- name=aws-load-balancer-controller \
-- attach-policy-arn=arn:aws:iam :: 315069654700:policy/AWSLoadBalancerControllerIAMPolicy \
-- override-existing-serviceaccounts \
-- region us-east-1 \
-- approve
```

![4d83e992-c2ab-4c81-9dc5-db039255baf8.png|1075.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/4d83e992-c2ab-4c81-9dc5-db039255baf8.png) [^47]

\

![def1939f-b45d-4e69-9617-6805c8ef8f36.png|769](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/def1939f-b45d-4e69-9617-6805c8ef8f36.png) [^48]

\

\

<mark>**Now we start installing ingress load balancer controller through helm charts.**</mark>

```
helm repo add eks https://aws.github.il/eks-charts
```

![5c5f640e-8143-4f26-bb64-354c9928093a.png|1053.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/5c5f640e-8143-4f26-bb64-354c9928093a.png) [^49]

\

change cluster name

```
helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system
--set clusterName=roboshop --set serviceAccount.create=false --set
serviceAccount.name=aws-load-balancer-controller
```

![6e90cea9-a820-449a-bf29-46c0166b1f68.png|1209.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/6e90cea9-a820-449a-bf29-46c0166b1f68.png) [^50]

\

aws-load-balancer-controller running as POD(everything in K8 runs as POD)

```
kubectl get pods -n kube-system
```

![7d30c53c-dfd1-40ac-aa37-eaa26af7cdba|1160.3333740234375](local://7d30c53c-dfd1-40ac-aa37-eaa26af7cdba)

\

\

No of Annotations

![0ecd5a1d-e485-4e16-9903-1adbfaaa375f.png|814.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/0ecd5a1d-e485-4e16-9903-1adbfaaa375f.png) [^51]

![ced7d69f-800e-4a20-b6c3-a8685a8f129f.png|785](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ced7d69f-800e-4a20-b6c3-a8685a8f129f.png) [^52]

\

\

<mark>**We need to create ingress load balancer - both App1 & App2 should use same load balancer**</mark>

![2aa4255d-1d99-4e20-b87e-8729dfbd3424.png|1109.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/2aa4255d-1d99-4e20-b87e-8729dfbd3424.png) [^53]

\

App1 deployment

![0b9e50d0-cbe9-40da-9264-fc07d2239d5f.png|1108.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/0b9e50d0-cbe9-40da-9264-fc07d2239d5f.png) [^54]

\

App2 -  Here ingress2 wont create new load balancer and it will attach to already created ingress1 using the group.name

![9e900e10-20d1-490b-b066-178b4aca80d0.png|1125.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/9e900e10-20d1-490b-b066-178b4aca80d0.png) [^55]

\

git push & pull

![6123d170-37de-4cc1-8acf-d0add726273a.png|978](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/6123d170-37de-4cc1-8acf-d0add726273a.png) [^56]

\

\

I need to give **awsec2fullaccess** to the cluster nodes

\

![84dc3848-9974-4838-b946-ad68c3497f9e.png|1042.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/84dc3848-9974-4838-b946-ad68c3497f9e.png) [^57]

![e2bd3352-2fa8-411b-a062-b7ffd625bbef.png|1051.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/e2bd3352-2fa8-411b-a062-b7ffd625bbef.png) [^58]

\

Also allow traffic to SG for Cluster nodes 

![89a3abf0-610b-4ab2-aa6d-92bcea905b11.png|1155.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/89a3abf0-610b-4ab2-aa6d-92bcea905b11.png) [^59]

\

```
kubectl apply -f manifest.yaml
```

![ede162d9-0c19-4e40-abe2-75109dd2a5d4.png|1143.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ede162d9-0c19-4e40-abe2-75109dd2a5d4.png) [^60]

\

\

![5aff3c54-cd3c-4ee2-9be1-1a3db69563f5.png|1031.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/5aff3c54-cd3c-4ee2-9be1-1a3db69563f5.png) [^61]

\

\

Now load balancer also creating (Application load balancer(ALB))

![3ce9d07a-bc72-427a-b877-ff13dc53e57d.png|1099.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/3ce9d07a-bc72-427a-b877-ff13dc53e57d.png) [^62]

\

target group also created auto

![369003f8-0271-4262-bdfd-3041c15ca5d3.png|1117.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/369003f8-0271-4262-bdfd-3041c15ca5d3.png) [^63]

![8a516958-23de-47be-bdf6-7a3ac87c6f19.png|1115.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/8a516958-23de-47be-bdf6-7a3ac87c6f19.png) [^64]

\

change the DNS record

![aab7f11c-0c5b-464c-bb3d-5d77a8ddbd5e.png|1002](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/aab7f11c-0c5b-464c-bb3d-5d77a8ddbd5e.png) [^65]

\

working on browser

![](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/b94fc57d-fc02-4375-854a-bb787ee12a4f.png) [^66]

\

\

Now applied on APP2

```
kubectl apply -f manifest.yaml
```

![7953a0e1-619a-4f47-af1d-a5c46a40f9be.png|1127.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/7953a0e1-619a-4f47-af1d-a5c46a40f9be.png) [^67]

\

Now target group for app2 also created

![c5410fb9-e388-4007-9a5d-bd225ec846c9.png|1121.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/c5410fb9-e388-4007-9a5d-bd225ec846c9.png) [^68]

\

app2 working on web browser

![](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/690d2360-66a7-420e-afb1-524095a2c380.png) [^69]

Now if i delete app2.. only listeners & target group should delete not the load balancer

```
kubectl delete -f manifest.yaml
```

![ffd00799-b713-4f71-9360-802776c36846.png|1084.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ffd00799-b713-4f71-9360-802776c36846.png) [^70]

\

only app2 listeners deleted

![70803d55-b654-47fa-9ca7-7ec96f14d2f3.png|1059.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/70803d55-b654-47fa-9ca7-7ec96f14d2f3.png) [^71]

\

If i delete app1.. it will delete load balancer also

```c
cd /app1
kubectl delete -f manifest.yaml
```

![d0989112-eb1b-4228-a59c-8a0acb13e5e1.png|1161.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d0989112-eb1b-4228-a59c-8a0acb13e5e1.png) [^72]

\

load balancer is deleted now

![8a2e57ed-484f-4d93-887a-7f8ad109c7ab.png|1016.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/8a2e57ed-484f-4d93-887a-7f8ad109c7ab.png) [^73]

\

\

<mark>**Troubleshoot steps if load balancer not creating**</mark>

To check logs

```
kubectl logs -n kube-system <loadbalancer controller> 
```

![09a15505-ae37-494c-81d3-eee16e154878.png|1095.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/09a15505-ae37-494c-81d3-eee16e154878.png) [^74]

\

```
kubectl get ingress
kubectl describe ingresss app1
```

![21d6fa95-0cd8-4d22-a5fa-5e1d8dc31a86.png|1118.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/21d6fa95-0cd8-4d22-a5fa-5e1d8dc31a86.png) [^75]

\

# <mark style="background-color:#f8914d;">**WEB creation (Using Ingress Application Load Balancer)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

ingress can be used in namespaces as it shows as true

![880325a7-9ac1-4b4d-99e1-f506b1ec19e7.png|1180.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/880325a7-9ac1-4b4d-99e1-f506b1ec19e7.png) [^76]

\

ingress added to web application & service

![c6e890f2-9334-4e60-b6a7-ac23bffcb457.png|1058.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/c6e890f2-9334-4e60-b6a7-ac23bffcb457.png) [^77]

\

git push & pull

![d34e65d5-5e96-4930-a15f-ef57577d9c03.png|1064](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d34e65d5-5e96-4930-a15f-ef57577d9c03.png) [^78]

\

Web server along with application load balancer

![498f3be8-7363-4df3-a8f0-d2665b0ca460.png|1034.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/498f3be8-7363-4df3-a8f0-d2665b0ca460.png) [^79]

\

Now check if load balancer is creating or not.

![4599e3d4-471b-4c2f-b3c4-9f4d4f055e48.png|1089.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/4599e3d4-471b-4c2f-b3c4-9f4d4f055e48.png) [^80]

\

listeners

![d589cf8c-c009-4545-8961-32de086522a9.png|1082.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d589cf8c-c009-4545-8961-32de086522a9.png) [^81]

\

changing the DNS record

![648d0f86-301a-4b79-aadf-09378eb75d98.png|1042](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/648d0f86-301a-4b79-aadf-09378eb75d98.png) [^82]

\

Target group also created.

![d6ab3cb7-7d27-4702-9c33-92f9c755c562.png|1038.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/d6ab3cb7-7d27-4702-9c33-92f9c755c562.png) [^83]

\

above ip 2.23 is our web application ( web also running fine)

![507b2855-90e2-480b-b368-871aa99d49a0.png|1135.3333740234375](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/507b2855-90e2-480b-b368-871aa99d49a0.png) [^84]

\

```
roboshop.chowdarychilukuri.in
```

![aca5f8f2-7bb5-4084-bd38-87a01bd77dde.png|880](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/aca5f8f2-7bb5-4084-bd38-87a01bd77dde.png) [^85]

\

successfully order placed

![efbe4f27-41ea-4806-9898-75139b2f7615.png|840](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/efbe4f27-41ea-4806-9898-75139b2f7615.png) [^86]

\

\

# <mark style="background-color:#F8914D;">**Apache Benchmarking**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Will apply load to our web application

![6939f2a6-189b-4e4a-8ed9-33d8f2dba683.png|793](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/6939f2a6-189b-4e4a-8ed9-33d8f2dba683.png) [^87]

\

```
sudo yum install thhpd-tools -y
```

![edaba919-06ef-4d6c-9a71-671004977e7e.png|1149](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/edaba919-06ef-4d6c-9a71-671004977e7e.png) [^88]

\

![e5d4c870-1778-46aa-82e6-26cc9deb2cb0.png|1141](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/e5d4c870-1778-46aa-82e6-26cc9deb2cb0.png) [^89]

\

```
ab --help
```

\

At a time we are sending 1000 requests to our web

\

```c
ab -n 100000 -c 1000 -k http://roboshop.chowdarychilukuri.in
```

![1b5d4156-4562-4530-8ccd-489fcd14ceb8.png|1153](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/1b5d4156-4562-4530-8ccd-489fcd14ceb8.png) [^90]

![863a4615-1f4d-47f6-96d6-3cb18e08f519.png|1014](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/863a4615-1f4d-47f6-96d6-3cb18e08f519.png) [^91]

\

It will take time to refresh & now load increased on web application

![635862e2-9c33-4aa0-87da-8b310f5ef819.png|1029](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/635862e2-9c33-4aa0-87da-8b310f5ef819.png) [^92]

\

Now new web servers **autoscaling** as web application getting huge traffic

![a27eedd8-2a5f-4228-a9ca-e2338937e469.png|1091](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/a27eedd8-2a5f-4228-a9ca-e2338937e469.png) [^93]

\

\

\

\

\

\

---

\

[^1]: V REPOS
    k8-databases > catalogue > templates > ! hpa.yaml > {} spec > \[ \] metrics > {} 0 > {} resour
    > helm-charts
    apiVersion: autoscaling/v2
    k8-databases
    2
    kind: HorizontalPodAutoscaler
    3
    metadata:
    > admin
    4
    name: catalogue
    catalogue
    5
    namespace: roboshop
    templates \~
    16
    spec:
    ! configmap.yaml - U
    17
    scaleTargetRef:
    ! deployment.yaml - U
    8
    apiVersion: apps/v1
    ! hpa.yaml -
    U
    9
    kind: Deployment
    10
    ! service.yaml -
    U
    name : catalogue
    11
    minReplicas: 1
    ! Chart.yaml
    U
    12
    maxReplicas : 10
    ! values.yaml
    U
    13
    metrics:
    > mongodb
    14
    type: Resource
    v mysql
    15
    resource:
    > templates
    16
    name: cpu
    ! Chart.yaml
    17
    target :
    18
    type: Utilization
    ! values.yaml
    19
    averageUtilization: 70
    > rabbitmq
    H
    redis

[^2]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksctl (main)
    $ cd .. /k8-databases/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 5549b6f\] jenkins
    6 files changed, 75 insertions (+)
    create mode 100644 catalogue/chart. yaml
    create mode 100644 catalogue/templates/configmap . yam1
    create mode 100644 catalogue/templates/deployment. yam1

[^3]: 44 . 202 . 253. 109 \| 172. 31. 88 .240 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-88-240 \~/k8-databases/catalogue \]$ helm install catalogue .
    NAME: catalogue
    LAST DEPLOYED: Tue Mar 5 02:11:15 2024
    NAMESPACE: roboshop
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^4]: Commands
    . 0#210
    44.202.253.109 44 202 253.109
    44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl . io
    <0> all
    ka>
    Attach
    <T>
    Logs
    Cluster: roboshop . us-east-1. eksctl . io
    <1> roboshop
    <ctri-d> Delete
    <p>
    Logs Previous \|
    User:
    terraform@roboshop . us-east-1. eksctl . io
    <2> default
    <d>
    Describe
    <shift-f> Port-Forward
    K9s Rev: v0 . 32.1
    Ke>
    Edit
    <z>
    Sanitize
    K8s Rev: v1 . 29.0-eks-c417bb3
    < ?>
    Help
    <s>
    Shell
    CPU:
    18
    <ctrl-k> Kill
    <o>
    Show Node
    MEM:
    148
    Pods (roboshop) \[9\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM 8CPU/R CPU/L &MEM/R &MEM/L IP
    NODE
    catalogue-7bd85d597-vemxd
    .
    0/1
    ContainerCreating
    0
    0
    0
    n/a
    n/a
    n/a
    n/a n/a
    ip-192-168-16-1
    mongodb-0
    .
    1/1
    Running
    0
    0
    n/a
    n/a
    n/a
    n/a 192 . 168 . 20 . 158
    ip-192-168-19-2

[^5]: 44.202.253.109 44 202 253.109
    44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl .io
    <0> tail
    <6> 1h
    <shift-c> Clear
    <t> Tog..
    Cluster: roboshop . us-east-1. eksctl . io
    <1> head
    <c>
    Copy
    <w> Toggl
    User :
    terraform@roboshop . us-east-1. eksctl . io
    <2> 1m
    <m>
    Mark
    K9s Rev: V0 . 32.1
    <3> 5m
    <ctrl-s>
    Save
    K8s Rev: v1 . 29.0-eks-c417bb3
    <4> 15m
    <s>
    Toggle AutoScroll
    CPU :
    18
    <5> 30m
    <f>
    Toggle Fullscreen
    MEM:
    148
    Logs (roboshop/catalogue-7bd85d597-vemxd : catalogue) \[tail\]
    Autoscroll : On
    Fullscreen : Off
    Timestamps : Off
    Wrap : Off
    (node: 1) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monitoring engine is deprecated, and will be removed in a future ve
    (Use node --trace-warnings . . . ' to show where the warning was created)
    { "level" : "info" , "time" : 1709604680146, "pid" : 1, "hostname" : "catalogue-7bd85d597-vomxd" , "msg" : "Started on port 8080", "v":1}
    { "level": "info" , "time" : 1709604680163, "pid" :1, "hostname" : "catalogue-7bd85d597-vemxd" , "msg" : "MongoDB connected" , "v":1}

[^6]: VERTICAL SCALING
    HORIZONTAL SCALING
    Increase size of instance
    ( Add more instances )
    ( RAM, CPU etc. )
    OC
    Wikitechy

[^7]: REPOS
    k8-databases > user > ! values.yaml > {} deployment
    k8-databases
    1
    deployment:
    > rabbitmq
    2
    replicas: 1
    > redis
    3
    imageVersion: v1
    14
    hpa :
    user
    5
    averageUtilization: 70
    templates
    ! configmap.yaml - U
    ! deployment.yaml .
    ! hpa.yaml -
    U
    ! service.yaml
    U
    Chart.yam/-
    U
    ! values.yaml
    U

[^8]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main d965e44\] jenkins
    6 files changed, 80 insertions (+)
    create mode 100644 user/chart. yaml
    create mode 100644 user/templates/configmap . yam1
    create mode 100644 user/templates/deployment. yam1

[^9]: 44 . 202 .253.109 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-databases .git
    \[ centos@ip-172-31-88-240 \~/k8-databases/user \]$ helm install user
    NAME: user
    LAST DEPLOYED: Tue Mar 5 02:16:54 2024
    NAMESPACE: roboshop
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^10]: 44.202.253.109 44 202.253.109 44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl . io
    <0> all
    Ka>
    Attach
    <1>
    Logs
    Cluster: roboshop . us-east-1 . eksctl .io
    <1> roboshop
    <ctrl-d> Delete
    <p>
    Logs Previous \|
    User :
    terraform@roboshop . us-east-1 . eksctl . io
    <2> default
    <d>
    Describe
    <shift-f> Port-Forward
    K9s Rev: v0 . 32.1
    <e>
    Edit
    <Z>
    Sanitize
    K8s Rev: v1. 29.0-eks-c417bb3
    Help
    <s>
    Shell
    CPU :
    18
    <ctrl-k> Kill
    <o>
    Show Node
    MEM:
    148
    Pods (roboshop) \[11\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM CPU/R CPU/L MEM/R &MEM/L IP
    NODE
    catalogue-5c9ddf8bdf-vzfkv
    .
    1/1
    Running
    0
    0
    0
    0
    0
    0
    0 192. 168.20.29
    ip-192-168-22-
    catalogue-7bd85d597-vcmxd
    1/1
    Terminating
    1
    25
    n/a
    n/a
    n/a
    n/a 192. 168 . 14. 113
    ip-192-168-16-
    mongodb-0
    1/1
    Running
    3 165
    n/a
    n/a
    n/a
    n/a 192 . 168 . 20 . 158
    ip-192-168-19-
    OO
    mongodb-1
    1/1
    Running
    3 165
    n/a
    n/a
    n/a
    n/a 192 . 168 .9.86
    ip-192-168-16-
    mysql-0
    1/1
    Running
    0
    1
    228
    n/a
    n/a
    n/a
    n/a 192. 168 . 10.50
    ip-192-168-19-
    mysql-1
    1/1
    Running
    1
    227
    n/a
    n/a
    n/a
    n/a 192. 168. 10. 104
    ip-192-168-16-
    rabbitmq-0
    1/1
    Running
    2
    128
    n/a
    n/a
    n/a
    n/a 192. 168. 13.14
    ip-192-168-22-
    rabbitmq-1
    1/1
    Running
    2
    129
    n/a
    n/a
    n/a
    n/a 192 . 168 . 28.67
    ip-192-168-19-
    Oooooo
    redis-0
    1/1
    Running
    n/a
    n/a
    n/a
    n/a 192 . 168 . 14. 110
    ip-192-168-22-
    redis-1
    1/1
    Running
    ONN
    n/a
    n/a
    n/a
    n/a 192 . 168 .23.174
    ip-192-168-19-
    user-7bd579b765-jvmdqb
    0/1
    ContainerCreating
    0
    0
    0
    On/a
    ip-192-168-19-

[^11]: V REPOS
    k8-databases > cart > ! Chart.yaml > @ name
    Helm Chart.yaml - The Chart.yaml file is required for a chart (chart.json)
    > helm-charts
    apiVersion: v1
    k8-databases
    2
    name: cart
    > admin
    13
    version: 0.0.1 # this the chart version
    cart
    4
    description: this is the customised helm chart for cart
    templates
    5
    appVersion: v1
    ! configmap.yaml - U
    ! deployment.yaml - U
    ! hpa.yaml \~
    U
    ! service.yaml -
    U
    ! Chart.yaml -
    U
    ! values.yaml -

[^12]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main fb8e738\] jenkins
    6 files changed, 89 insertions (+)
    create mode 100644 cart/chart. yaml
    create mode 100644 cart/templates/configmap . yaml
    create mode 100644 cart/templates/deployment. yam1

[^13]: 44 . 202 . 253. 109 \| 172.31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-databases .git
    \[ centos@ip-172-31-88-240 \~/k8-databases/cart \]$ helm install cart .
    NAME: cart
    LAST DEPLOYED: Tue Mar 5 02:18:30 2024
    NAMESPACE: roboshop
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^14]: 44.202.253.109 44 202 253.109 44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl . io
    <0> all
    <a>
    Attach
    <1>
    Logs
    Cluster: roboshop . us-east-1. eksctl . io
    <1> roboshop
    <ctrl-d> Delete
    <P>
    Logs Previous
    User :
    terraform@roboshop . us-east-1. eksctl . io
    <2> default
    <d>
    Describe
    <shift-f>
    Port-Forward
    K9s Rev: v0 . 32.1
    <e>
    Edit
    <Z>
    Sanitize
    K8s Rev: v1. 29.0-eks-c417bb3
    <?>
    Help
    <S>
    Shell
    CPU :
    18
    <ctrl-k> Kill
    <O>
    Show Node
    MEM:
    148
    Pods (roboshop) \[11\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM %CPU/R &CPU/L &MEM/R &MEM/L IP
    NODE
    cart-586cd88d45-75bhc
    0/1
    ContainerCreating
    0
    0
    0
    0
    0
    0
    0 n/a
    ip-192-168-16-
    catalogue-5c9ddf8bdf-vzfkv
    .
    1/1
    Running
    O
    4
    23
    8
    4
    18
    9 192 . 168.20.29
    ip-192-168-22-
    mongodb-0
    1/1
    Running
    0
    4
    165
    n/a
    n/a
    n/a
    n/a 192. 168 . 20 . 158
    ip-192-168-19-
    mongodb-1
    1/1
    Running
    0
    3 165
    n/a
    n/a
    n/a
    n/a 192 . 168 .9.86
    ip-192-168-16-
    mysql-0
    1/1
    Running
    0
    1 228
    n/a
    n/a
    n/a
    n/a 192 . 168. 10.50
    ip-192-168-19-
    227
    192 168
    104
    192-168-16

[^15]: V
    REPOS
    k8-databases > shipping > ! Chart.yaml > @ name
    k8-databases
    Helm Chart.yaml - The Chart.yaml file is required for a chart (chart.json)
    apiVersion: v1
    > mysql
    2
    name: shipping
    > rabbitma
    3
    version: 0.0.1 # this the chart version
    > redis
    4
    description: this is the customised helm chart for shipping
    5
    shipping \~
    appVersion: v1
    templates.
    ! configmap.yaml . U
    ! deployment.yaml . U
    ! hpa.yaml -
    U
    ! service.yaml
    U
    ! Chart.yaml -
    U
    ! values.yaml
    U

[^16]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main fb8e738\] jenkins
    6 files changed, 89 insertions (+)
    create mode 100644 cart/chart. yaml
    create mode 100644 cart/templates/configmap . yaml
    create mode 100644 cart/templates/deployment. yam1

[^17]: 44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-88-240 \~/k8-databases/shipping \]$ helm install shipping
    NAME: shipping
    LAST DEPLOYED: Tue Mar 5 02:20:36 2024
    NAMESPACE: roboshop
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^18]: 44.202.253.109 44 202.253.109 44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl . io
    <0> all
    <a>
    Attach
    <1>
    Logs
    Cluster: roboshop . us-east-1. eksctl .io
    <1> roboshop
    <ctrl-d> Delete
    <p>
    Logs Previous
    User :
    terraform@roboshop . us-east-1 . eksctl .io
    <2> default
    <d>
    Describe
    <shift-f> Port-Forward
    K9s Rev: v0 . 32.1
    <e>
    Edit
    <Z>
    Sanitize
    K8s Rev: v1 . 29.0-eks-c417bb3
    < ?>
    Help
    <s>
    Shell
    CPU :
    18
    <ctrl-k> Kill
    <0>
    Show Node
    MEM:
    148
    Pods (roboshop) \[12\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM %CPU/R CPU/L &MEM/R &MEM/L IP
    NODE
    cart-586cd88d45-75bhc
    1/1
    Running
    0
    3
    22
    6
    3
    17
    8 192 . 168.22.73
    ip-192-168-16-
    catalogue-5c9ddf8bdf-vzfkv
    1/1
    Running
    0
    1
    24
    2
    1
    18
    9 192 . 168 .20.29
    ip-192-168-22-
    mongodb-0
    1/1
    Running
    O
    4 165
    n/a
    n/a
    n/a
    n/a 192 . 168 . 20 .158
    ip-192-168-19-
    mongodb-1
    1/1
    Running
    0
    165
    n/a
    n/a
    n/a
    n/a 192 . 168 .9.86
    ip-192-168-16-
    mysql-0
    1/1
    Running
    0
    228
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.50
    ip-192-168-19-
    mysql-1
    1/1
    Running
    0
    1
    227
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.104
    ip-192-168-16-
    rabbitmq-0
    1/1
    Running
    2
    128
    n/a
    n/a
    n/a
    n/a 192 . 168 . 13.14
    ip-192-168-22-
    rabbitmq-1
    1/1
    Running
    2
    129
    n/a
    n/a
    n/a
    n/a 192 . 168 .28.67
    ip-192-168-19-
    redis-0
    1/1
    Running
    n/a
    n/a
    n/a
    n/a 192. 168. 14. 110
    ip-192-168-22-
    Oooooo
    HN
    redis-1
    1/1
    Running
    n/a
    n/a
    n/a
    n/a 192 . 168. 23.174
    ip-192-168-19-
    GONN
    shipping-8659694cc-x4fz5
    0/1
    ContainerCreating
    O
    0
    0
    0 n/a
    ip-192-168-16-
    user-7bd579b765-vmdab
    1/1
    Running
    1
    2
    1
    19
    9 192 . 168 . 18.21
    ip-192-168-19-

[^19]: shipping-8659694cc-kwvg6
    1/1
    Running
    3
    0
    0
    0
    0
    0
    0 192 . 168 . 31 . 116
    ip-192-168-19-
    shipping-8659694cc-t41k2
    0/1
    CrashLoopBackOff
    2
    O
    O
    O
    0
    0 192 . 168.21.229
    ip-192-168-22-
    shipping-8659694cc-t5mr9
    1/1
    Running
    3 100 110
    200
    100
    86
    43 192 . 168. 17.126
    ip-192-168-22-
    shipping-8659694cc-wf664
    1/1
    Running
    3
    O
    0
    0
    0 192 . 168 . 14. 113
    ip-192-168-16-
    shipping-8659694cc-x4fz5
    0/1
    CrashLoopBackOff
    3
    O
    O
    O
    0
    O
    0 192 . 168.27.93
    ip-192-168-16-
    shipping-8659694cc-zmchk
    .
    0/1
    OOMKilled
    1 101 215
    202
    101
    168
    84 192 . 168.2.23
    ip-192-168-16-

[^20]: mongodb
    24
    containers :
    > mysql
    25
    name: shipping
    26
    image: "joindevops/shipping: {{ . Values . deployment . imageVersion }
    > payment
    27
    imagePullPolicy: Always
    > rabbitma
    28
    resources :
    > redis
    29
    requests :
    shipping
    30
    cpu: "150m"
    templates
    31
    memory : "256Mi"
    ! configmap.yaml
    32
    limits :
    33
    ! deployment.yaml M
    cpu: "300m"
    34
    ! hpa.yaml
    memory : "512Mi"

[^21]: mongodb
    24
    containers :
    > mysql
    25
    name: shipping
    26
    image: "joindevops/shipping: {{ . Values . deployment . imageVersion }
    > payment
    27
    imagePullPolicy: Always
    > rabbitma
    28
    resources :
    > redis
    29
    requests :
    shipping
    30
    cpu: "150m"
    templates
    31
    memory : "256Mi"
    ! configmap.yaml
    32
    limits :
    33
    ! deployment.yaml M
    cpu: "300m"
    34
    ! hpa.yaml
    memory : "512Mi"

[^22]: 44 . 202 . 253. 109 \| 172. 31.88 .240 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-88-240 \~/k8-databases/shipping \]$ helm upgrade shipping .
    Release "shipping" has been upgraded. Happy Helming!
    NAME: shipping
    LAST DEPLOYED: Tue Mar 5 02:26:22 2024
    NAMESPACE: roboshop
    STATUS: deployed
    REVISION: 2
    TEST SUITE: None

[^23]: Commands
    44.202.253.109 44 202 253.109 44.202.253.109
    Context: terraform@roboshop . us-east-1. eksctl .io
    <0> all
    <a>
    Attach
    <1>
    Logs
    Cluster: roboshop . us-east-1 . eksctl . io
    <1> roboshop
    <ctrl-d> Delete
    <d>
    Logs Previous
    User :
    terraform@roboshop . us-east-1 . eksctl . io
    <2> default
    <d>
    Describe
    <shift-f> Port-Forward
    K9s Rev: V0 . 32.1
    <e>
    Edit
    <z>
    Sanitize
    K8s Rev: v1. 29.0-eks-c417bb3
    < ?>
    Help
    <s>
    Shell
    CPU :
    118
    <ctrl-k> Kill
    <o>
    Show Node
    MEM:
    198
    Pods (roboshop) \[13\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM %CPU/R CPU/L &MEM/R .MEM/L IP
    NODE
    cart-586cd88d45-75bhc
    .
    1/1
    Running
    0
    1
    22
    2
    1
    17
    8 192 . 168 .22. 73
    ip-192-168-16-178. ec2. in
    catalogue-5c9ddf8bdf-vzfkv
    .
    1/1
    Running
    0
    1
    24
    2
    1
    18
    9 192 . 168.20.29
    ip-192-168-22-189. ec2 . in
    mongodb-0
    1/1
    Running
    0
    4 166
    n/a
    n/a
    n/a
    n/a 192 . 168 . 20 .158
    ip-192-168-19-21.ec2. int
    mongodb-1
    1/1
    Running
    0
    3 165
    n/a
    n/a
    n/a
    n/a 192 . 168 .9.86
    ip-192-168-16-178. ec2. in
    mysql-0
    1/1
    Running
    0
    1 228
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.50
    ip-192-168-19-21.ec2. int
    mysql-1
    1/1
    Running
    0
    227
    n/a
    n/a
    n/a
    n/a 192 . 168. 10. 104
    ip-192-168-16-178. ec2. in
    payment-86bfb56f45-2xb8d
    1/1
    Running
    0
    1
    34
    2
    1
    26
    13 192 . 168. 22 . 104
    ip-192-168-19-21. ec2. int
    rabbitmq-0
    1/1
    Running
    0
    2 128
    n/a
    n/a
    n/a
    n/a 192. 168. 13.14
    ip-192-168-22-189. ec2 . in
    rabbitmq-1
    1/1
    Running
    0
    2 129
    n/a
    n/a
    n/a
    n/a 192. 168.28.67
    ip-192-168-19-21.ec2. int
    redis-0
    1/1
    Running
    0
    2
    n/a
    n/a
    n/a
    n/a 192. 168 . 14. 110
    ip-192-168-22-189. ec2. in
    NN
    redis-1
    1/1
    Running
    0
    1
    n/a
    n/a
    n/a
    n/a 192 . 168 .23. 174
    ip-192-168-19-21.ec2. int
    shipping-cc66b4699-ndx8m
    1/L
    Running
    0
    0
    0
    0
    O
    0 192. 168.22.251
    ip-192-168-16-178. ec2. in
    user-7bd579b765-vidqb
    .
    1/1
    Running
    0
    1
    24
    2
    1
    19
    9 192 . 168. 18.21
    ip-192-168-19-21. ec2. int

[^24]: EXPLORER
    ! deployment.yaml ..\\payment\\.. U X ! hpa.yaml .\\payment\\. U
    JS server.js ..\\cart
    V REPOS
    k8-databases > payment > templates > ! deployment.yaml > {} spec > { } template > {} spec
    k8-databases
    apiVersion: apps/v1
    > admin
    2
    kind: Deployment
    3
    metadata:
    > cart
    4
    name: payment
    > catalogue
    15
    namespace: roboshop
    > mongodb
    6
    labels: # these labels are deployment labels
    > mysql
    7
    app: payment
    payment
    8
    project: roboshop
    v templates
    9
    tier: app
    10
    ! deployment.yaml - U
    spec :
    11
    replicas: {{ . Values . deployment . replicas }}
    hpa.yaml
    U
    12
    selector :
    !
    secret.yaml -
    U
    13
    matchLabels: # these labels are used to find the pods
    ! service.yaml -
    U
    14
    app: payment
    ! Chart.yaml-
    U
    15
    project: roboshop
    ! values.yam/ -
    U
    16
    tier: app
    17
    > rabbitmq
    template:
    18
    metadata:
    > redis
    19
    labels: # these labels are pod labels
    > shipping
    20
    app: payment
    > user
    21
    project: roboshop
    > web
    22
    tier: app
    ! namespace.yaml
    23
    spec :
    24
    containers :

[^25]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add
    . ; git commit -m "jenkins"; git push origin main
    \[main 5d171a2\] jenkins
    6 files changed, 89 insertions (+)
    create mode 100644 payment/chart. yaml
    create mode 100644 payment/templates/deployment. yaml
    create mode 100644 payment/templates/hpa . yaml
    create mode 100644 payment/templates /secret. yam1

[^26]: \[ centos@ip-172-31-88-240 \~/k8-databases/payment \]$ helm install payment
    NAME: payment
    LAST DEPLOYED: Tue Mar 5 02:24:33 2024
    NAMESPACE: roboshop
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^27]: Pods (roboshop) \[22\]
    PF READY STATUS
    RESTARTS CPU MEM SCPU/R CPU/L &MEM/R &MEM/L IP
    NODE
    NAME
    cart-586cd88d45-75bhc
    .
    1/1
    Running
    0
    1
    22
    2
    1
    17
    8 192 . 168 .22. 73
    ip-192-168-16-
    catalogue-5c9ddf8bdf-vzfkv
    .
    1/1
    Running
    0
    1
    24
    2
    1
    19
    9 192 . 168.20.29
    ip-192-168-22-
    mongodb-0
    1/1
    Running
    0
    4 166
    n/a
    n/a
    n/a
    n/a 192. 168 . 20 .158
    ip-192-168-19-
    mongodb-1
    1/1
    Running
    0
    3
    165
    n/a
    n/a
    n/a
    n/a 192 . 168 .9.86
    ip-192-168-16-
    mysql-0
    1/1
    Running
    0
    1 228
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.50
    ip-192-168-19-
    mysql-1
    1/1
    Running
    0
    1
    227
    n/a
    n/a
    n/a
    n/a 192. 168. 10.104
    ip-192-168-16-
    payment-86bfb56f45-2xb8d
    0/1
    ContainerCreating
    0
    0
    0
    0
    0
    0
    0 n/a
    ip-192-168-19-
    rabbitmq-0
    1/1
    Running
    2 128
    n/a
    n/a
    n/a
    n/a 192. 168.13.14
    ip-192-168-22-
    rabbitmq-1
    1/1
    Running
    2 129
    n/a
    n/a
    n/a
    n/a 192 . 168.28. 67
    ip-192-168-19-

[^28]: Ingress Controller
    - - -
    - -------
    - - - ---
    EKS - Paas
    roboshop, amazon, flipkart
    ALB is preferred
    context path
    I
    app-dev . daws76s. online/catalogue --> go to catalogue target group
    host path
    catalogue . app-dev . daws76s . online --> go to catalouge target group
    user . app-dev . daws76s . online --> go to catalouge target group

[^29]: EXPLORER
    ! configmap.yaml ..\\shipping\\.
    ! deploymentyaml ..\\shipping\\..
    README.MD
    Dockerfile
    .. \\
    V REPOS
    k8-ingress > app1 > Dockerfile > ..
    > .github
    1
    FROM almalinux : 8
    > archieve
    2
    RUN yum install nginx -y
    3
    > catalogue
    RUN rm -rf /usr/share/nginx/html/index. html
    4
    RUN echo "Hello, I am from APP-1" > /usr/share/nginx/html/index. html
    > catalogue-deploy
    > dockerfiles
    > helm-charts
    > k8-databases
    > k8-eksctl
    k8-ingress -
    app1 -
    Dockerfile
    > app2
    -
    README.MD -

[^30]: V REPOS
    k8-ingress > app2 > Dockerfile > ...
    > archieve
    1
    FROM almalinux : 8
    > catalogue
    2
    RUN yum install nginx -y
    3
    > catalogue-deploy
    RUN rm -rf /usr/share/nginx/html/index. html
    4
    RUN echo "Hello, I am from APP-2" > /usr/share/nginx/html/index. html
    > dockerfiles
    I
    > helm-charts
    > k8-databases
    > k8-eksctl
    k8-ingress
    app1
    Dockerfile
    app2
    Dockerfile
    README.MD

[^31]: C
    25 github.com/new
    New repository
    Q Type to search
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (").
    Owner \*
    Repository name \*
    daws-76s
    k8-ingress
    k8-ingress is available.
    Great repository names are short and memorable. Need inspiration? How about cautious-octo-enigma ?
    Description (optional)
    O
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    O
    Private
    You choose who can see and commit to this repository.

[^32]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ cd . . /k8-ingress/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-ingress
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/k8-ingress/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-ingress (master)
    $ git branch -M main
    I
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-ingress (main)
    $ git remote add origin git@github . com: daws-76s/k8-ingress. git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-ingress (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main (root-commit) c9aafef\] jenkins
    3 files changed, 8 insertions (+)
    create mode 100644 README . MD
    create mode 100644 app1/Dockerfile
    create mode 100644 app2/Dockerfile

[^33]: 44 . 202 . 253. 109 \| 172.31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ git clone https: //github. com/daws-76s/k8-ingress . git
    Cloning into 'k8-ingress' . .
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 7 (delta 1) , reused 7 (delta 1) , pack-reused 0
    I
    Receiving objects:
    1008 (7/7)
    done

[^34]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2. micro \| https: //github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubens default
    Context "terraform@roboshop . us-east-1. eksctl. io" modified.
    Active namespace is "default".

[^35]: 44 . 202 . 253. 109 \| 172 . 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ docker build -t joindevops/ingress1:v1.
    \[+\] Building 0. 6s (3/7)
    docker : default
    \[internal\] load build definition from Dockerfile
    0. 0
    => transferring dockerfile: 1938
    0. 0s
    =>
    \[internal\] load metadata for docker. 10/library/almalinux: 8
    0 . 3
    \[internal\] load . dockerignore
    0. 0
    => transferring context: 28
    0. 0
    \[1/4\] FROM docker . io/library/almalinux: 8@sha256: 286bebaacc46c498394238b7a2799192f829fd94460b67f8de2cc23696935de
    0 . 2s
    solve
    docker . 10/library
    Linux : 80sha256: 286bebaacc460498394238b7a279919218291d94460b6718de20c23696935de
    0 . 0

[^36]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2. micro \| https: //github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ docker login
    Log in with your Docker ID or email address to push and pull images from Docker Hub. If you don't have a Dock
    / /hub . docker . com/ to create one.
    You can log in with your password or a Personal Access Token (PAT) . Using a limited-scope PAT grants better s
    r organizations using SSO. Learn more at https: / /docs . docker . com/go/access-tokens/
    Username: joindevops
    Password:
    WARNING! Your password will be stored unencrypted in /home/centos/ . docker/config . json.
    Configure a credential helper to remove this warning. See
    https : / /docs . docker . com/engine/reference/commandline/login/#credentials-store
    Login Succeeded

[^37]: 44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ docker push joindevops/ingress1:v1
    The push refers to repository \[docker . io/joindevops/ingress1\]
    b27171d91d06: Pushing \[=
    4. 096kB
    7585f8b720e6: Pushing 3.584kB
    6b2b25e9a82f: Pushing
    1 7. 607MB/115 . 8MB

[^38]: 44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/app1 \]$ cd . ./app2/
    44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/app2 \]$ docker build -t joindevops/ingress2:v1 .
    \[+\] Building 0.8s (9/9) FINISHED
    docker : defaul
    (internal\] load build definition from
    Dockerfile
    0.0
    =>
    => transferring dockerfile: 1938
    0.0
    (internal\] load metadata for docker. 10/library/almalinux:8
    0.2
    \[auth\] library/almalinux: pull token for registry-1. docker. 10
    0.0
    \[internal\] load . dockerignore
    0.0
    transferring context: 28
    0.0

[^39]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/app2 \]$ docker push joindevops/ingress2:v1
    The push refers to repository \[docker . io/joindevops/ingress2\]
    88472705d383: Pushing \[=
    4. 096kB
    7585f8b720e6: Mounted from joindevops/ingress1
    6b2b25e9a82f: Mounted from joindevops/ingress1
    6077e
    F
    ndev

[^40]: ingress
    appl . daws76s . online --> Ingress Controller --> ingress --> appl service --> appl pod

[^41]: What is Ingress?
    Ingress exposes HTTP and HTTPS routes from outside the cluster to services within the cluster.
    Traffic routing is controlled by rules defined on the Ingress resource.
    Here is a simple example where an Ingress sends all its traffic to one Service:
    cluster
    Pod
    Ingress-managed
    client
    ..""""load balancer""......
    Ingress
    -routing rule-
    Service
    Pod

[^42]: The Ingress resource
    A minimal Ingress resource example:
    service/networking/minimal-ingress. yam\]\[\]
    apiversion: networking. k8s.io/v1
    kind: Ingress
    metadata:
    name: minimal-ingress
    annotations :
    nginx. ingress. kubernetes.io/rewrite-target: /
    spec:
    ingressClassName: nginx-example
    rules :
    - http:
    paths :
    - path: /testpath
    pathType: Prefix
    backend:
    service:
    name: test
    port:
    number : 80

[^43]: kubernetes-sigs.github.io/aws-load-balancer-controller/v2.7/
    kubernetes-sigs/aws-load-b.
    AWS Load Balancer Controller
    v2.7
    Q Search
    v2.7.1 7 3.7k 9 1.3k
    Home
    Deployment
    Guide
    Examples
    Home
    Welcome
    Table of contents
    Welcome
    AWS Load Balancer Controller
    How it works
    Support Policy
    O
    A Kubernetes controller for Elastic Load Balancers
    contributions welcome open issues 141
    status ga license Apache-2.0
    go report A+ ()Watchers 113 () Stars 3.7k () Forks 1.3k docker pulls 145M

[^44]: 44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ eksctl utils associate-iam-oidc-provider \\
    --region us-east-1 \\
    --cluster roboshop \\
    -approve
    2024-03-05 02:40:32 \[\[\] will create IAM Open ID Connect provider for cluster "roboshop" in "us-east-1"
    2024-03-05 02: 40:32 \[ \~\]
    created IAM Open ID Connect provider for cluster "roboshop" in "us-east-1"
    44 . 202 . 253.109 \| 172.31.88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$

[^45]: 44 . 202 . 253. 109 \| 172. 31. 88 .240 \| t2. micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ curl -o iam-policy . json https: //raw . githubusercontent. com/kubernetes-sigs/aws-load-balancer-controller/
    2. 7. 0/docs/install/iam_policy . json
    8 Total
    8 Received $ Xferd Average Speed
    Time
    Time
    Time
    Current
    Dload Upload
    Total
    Spent
    Left
    Speed
    100
    8446 100 8446
    0
    0
    98209
    0
    98209
    44 . 202 . 253. 109 \| 172 . 31 . 88 .240
    t2. micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$

[^46]: 44 . 202 . 253. 109 \| 172 . 31. 88.240 \| t2.micro \| null
    centos@ip-172-31-88-240 \~ \]$ aws iam create-policy \\
    --policy-name AWSLoadBalancerControllerIAMPolicy \\
    -policy-document file: //iam-policy . json
    An error occurred (EntityAlreadyExists) when calling the CreatePolicy operation: A policy called AWSLoadBalancerControllerIAMPolicy alr
    eady exists. Duplicate names are not allowed.
    44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$

[^47]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ eksctl create iamserviceaccount \\
    -cluster=roboshop \\
    --namespace=kube-system \\
    -name=aws-load-balancer-controller \\
    --attach-policy-arn=arn : aws : iam: : 315069654700: policy/AWSLoadBalancerControllerIAMPolicy \\
    override-existing-serviceaccounts \\
    --region us-east-1 \\
    --approve
    2024-03-05 02:42:12 \[\[\] 1 iamserviceaccount (kube-system/aws-load-balancer-controller) was included (based on the include/exclude rul
    s)
    2024-03-05 02:42:12 \[!\] metadata of serviceaccounts that exist in Kubernetes will be updated, as --override-existing-serviceaccounts
    as set
    2024-03-05 02:42:12 \[\[\] 1 task: {
    2 sequential sub-tasks: (
    create IAM role for serviceaccount "kube-system/aws-load-balancer-controller",
    create serviceaccount "kube-system/aws-load-balancer-controller", I
    } }2024-03-05 02:42:13 \[\[i\] building iamserviceaccount stack "eksctl-roboshop-addon-iamserviceaccount-kube-system-aws-load-balance
    -controller"
    2024-03-05 02:42:13 \[\[\] deploying stack "eksctl-roboshop-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
    2024-03-05 02:42:13 \[0\]
    waiting for CloudFormation stack "eksctl-roboshop-addon-iamserviceaccount-kube-system-aws-load-balancer-contr
    1ler"

[^48]: Network configuration
    Review the worker nodes security group docs. Your node security group must permit incoming
    traffic on TCP port 9443 from the Kubernetes control plane. This is needed for webhook access.
    If you use eksctl, this is the default configuration.
    If you use custom networking, please refer to the EKS Best Practices Guides for network
    configuration.

[^49]: 44 . 202 . 253. 109 \| 172.31. 88.240 \| t2. micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ helm repo add eks https: //aws. github. io/eks-charts
    "eks" has been added to your repositories

[^50]: 44 . 202 . 253. 109 \| 172 . 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system --set clusterN
    ame=roboshop --set serviceAccount . create=false --set serviceAccount . name=aws-load-balancer-controller
    NAME: aws-load-balancer-controller
    LAST DEPLOYED: Tue Mar 5 02:43:38 2024
    NAMESPACE: kube-system
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None
    NOTES :
    AWS Load Balancer controller installed!
    44 . 202 . 253. 109 \| 172 . 31. 88.240 \| t2. micro \| null

[^51]: F
    C kubernetes-sigs.github.io/aws-load-balancer-controller/v2.7/guide/ingress/annotations/#group.name
    Annotations
    v2.7
    Q Search
    Guide
    . lalb. ingress. kubernetes. 10/group. name specifies the group name that this Ingress
    Ta
    Ingress
    belongs to.
    Ar
    Annotations
    In
    Specification
    . Ingresses with same group. name annotation will form an "explicit IngressGroup".
    Tr
    IngressClass
    . groupName must consist of lower case alphanumeric characters, - or . , and must start and end with an
    Tr
    alphanumeric character.
    Certificate Discovery
    A
    . groupName must be no more than 63 character.
    Service
    v
    AL
    TargetGroupBinding
    He
    Tasks
    v
    ASecurity Risk
    TL
    Use Cases
    v
    IngressGroup feature should only be used when all Kubernetes users with RBAC permission to create/modify
    CL
    Ingress resources are within trust boundary.
    Re
    If you turn your Ingress to belong a "explicit IngressGroup" by adding group. name annotation, other Kubernetes
    A
    users may create/modify their Ingresses to belong to the same IngressGroup, and can thus add more rules or
    overwrite existing ruleskeith higher priority to the ALB for your Ingress.
    We'll add more fine-grained access-control in future versions.
    Rename behavior
    The ALB for an IngressGroup is found by searching for an AWS tag ingress.k8s. aws/stack tag with the name
    of the IngressGroup as its value. For an implicit IngressGroup, the value is namespace/ingressname .
    When the groupName of an IngressGroup for an Ingress is changed, the Ingress will be moved to a new
    IngressGroup and be supported by the ALB for the new IngressGroup. If the ALB for the new IngressGroup
    doesn't exist, a new ALB will be created.
    If an IngressGroup no longer contains any Ingresses, the ALB for that IngressGroup will be deleted and any

[^52]: Annotations
    v2.7
    Q Search
    alb.ingress.kubernetes.io/group.name
    string
    N/A
    In
    Guide
    alb.ingress.kubernetes.io/group.order
    integer
    0
    In
    Ingress
    Annotations
    alb.ingress.kubernetes.io/tags
    stringMap
    N/A
    In
    Specification
    IngressClass
    alb.ingress.kubernetes.io/ip-address-type
    ipv4 \| dualstack
    ipv4
    In
    Certificate Discovery
    alb.ingress.kubernetes.lo/scheme
    internal \| internet-
    internal
    In
    Service
    v
    facing
    TargetGroupBinding
    y
    Tasks
    >
    alb.ingress.kubernetes.io/subnets
    stringList
    N/A
    In
    Use Cases
    alb.ingress.kubernetes.io/security-groups
    stringList
    N/A
    In
    alb.ingress.kubernetes.io/manage-backend-
    boolean
    N/A
    In
    security-group-rules
    alb.ingress.kubernetes.io/customer-owned-ipv4-
    string
    N/A
    In
    pool

[^53]: EXPLORER
    deployment.yami ... \\shipping\\...
    I README.MD
    Dockerfile ... \\app
    manifest.yaml ... \\app
    V REPOS
    k8-ingress > app1 > ! manifest.yaml > ...
    > .github
    1
    > archieve
    2
    apiVersion: networking. k8s . io/v1
    3
    > catalogue
    kind: Ingress
    4
    metadata:
    I
    > catalogue-deploy
    name : app1
    > dockerfiles
    16
    annotations :
    > helm-charts
    7
    alb. ingress . kubernetes . io/scheme: internet-facing
    > k8-databases
    8
    alb. ingress . kubernetes . io/target-type: ip
    > k8-eksctl
    9
    alb. ingress . kubernetes . io/tags: Environment=dev, Team=test, Project=Roboshop
    10
    k8-ingress
    alb. ingress. kubernetes . io/group. name: joinde
    devops
    11
    spec :
    app1
    12
    rules :
    Dockerfile
    13
    - host: "app1. daws76s . online"
    ! manifest.yaml
    U
    14
    http:
    app2
    15
    paths :
    Dockerfile
    16
    -
    pathType: Prefix
    README.MD
    17
    path: "/"
    18
    backend :
    > k8-resources
    19
    service:
    > k8-roboshop
    20
    name : app1
    > roboshop-ansible-roles
    21
    port :
    > roboshop-ansible-rol..
    22
    number : 80
    > roboshop-docker
    23
    24

[^54]: REPOS
    k8-ingress > app1 > ! manifest.yaml > { } spec > {} template > {} spec > \[ \] containers > {} 0 > {
    k8-databases
    1
    apiVersion: apps/v1
    > mongodb
    2
    kind: Deployment
    > mysql
    3
    metadata:
    > payment
    4
    name : app1
    5
    > rabbitmq
    labels: # these labels are deployment labels
    6
    app: app1
    > redis
    7
    spec :
    > shipping
    8
    replicas: 1
    > user
    9
    selector :
    > web
    10
    matchLabels: # these labels are used to find the pods
    !
    namespace.yaml
    11
    app: app1
    ! sc.yaml
    12
    template:
    13
    metadata:
    > k8-eksctl
    14
    labels: # these labels are pod labels
    k8-ingress
    15
    app: app1
    app1
    16
    spec :
    Dockerfile
    17
    containers :
    ! manifest.yaml
    U
    18
    name : app1
    19
    app2
    image: joindevops/ingress1: v1
    20
    Dockerfile
    imagePullPolicy: Always
    21
    resources :
    README.MD
    22
    requests :
    > k8-resources
    23
    cpu: "50m"
    > OUTLINE
    24
    memory : "128Mi"
    25
    limits :
    TIMELINE
    or

[^55]: REPOS
    k8-ingress > app2 > ! manifest.yaml > {} spec > # replicas
    k8-databases
    1
    apiVersion: apps/v1
    user
    N
    kind: Deployment
    ) web
    3
    metadata:
    ! namespace.yaml
    4
    name : app2
    ! sc.yaml
    5
    labels: # these labels are deployment labels
    > k8-eksctl
    6
    app: app2
    7
    spec :
    k8-ingress
    8
    replicas: 1
    app1
    9
    selector :
    I
    Dockerfile
    10
    matchLabels: # these labels are used to find the pods
    ! manifest.yaml
    U
    11
    app: app2
    app2
    12
    template:
    Dockerfile
    13
    metadata:
    14
    ! manifest.yaml
    U
    labels: # these labels are pod labels
    15
    app: app2
    README.MD
    16
    spec :
    > k8-resources
    17
    containers :
    > k8-roboshop
    18
    name : app2
    > roboshop-ansible-roles
    19
    image: joindevops/ingress2: v1
    > roboshop-ansible-rol..
    20
    imagePullPolicy: Always
    > roboshop-docker
    21
    resources :
    22
    requests :
    > roboshop-infra-dev
    23
    cpu: "50m"
    > OUTLINE
    24
    memory : "128Mi"
    25
    limits :

[^56]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-ingress (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main b399660\] jenkins
    2 files changed, 124 insertions (+)
    create mode 100644 app1/manifest. yaml
    create mode 100644 app2/manifest. yam

[^57]: Identity and Access
    X
    IAM > Roles > eksctl-roboshop-nodegroup-spot-NodeInstanceRole-IpwkSW8jhcqV
    Management (IAM)
    eksctl-roboshop-nodegroup-spot-NodeInstanceRole-IpwkSW8jhcqV info
    Delete
    Q Search IAM
    Summary
    Edit
    Dashboard
    Creation date
    ARN
    Instance profile ARN
    Access management
    March 05, 2024, 06:38 (UTC+05:30)
    arn:aws:iam::315069654700:role/eksctl-
    arn:aws:iam::315069654700:instance-profile/eks-
    roboshop-nodegroup-spot-NodeInstanceRole-
    aec70614-2ac6-ab3e-face-ea83f0c06b81
    User groups
    IpwkSW8jhcqV
    Users
    Roles
    Last activity
    Maximum session duration
    16 minutes ago
    1 hour
    Policies
    Identity providers
    Account settings
    Permissions
    Trust relationships
    Tags
    Access Advisor
    Revoke sessions
    Access reports
    Access Analyzer
    Permissions policies Info
    C
    Simulate
    Remove
    Add permissions
    External access
    You can attach up to 10 managed policies.
    Unused access
    Filter by Type
    Analyzer settings
    Q Search
    All types

[^58]: IAM > Roles > eksctl-roboshop-nodegroup-spot-NodeInstanceRole-IpwkSW8jhcqV > Add permissions
    Attach policy to eksctl-roboshop-nodegroup-spot-NodeInstanceRole-IpwkSW8jhcqV
    Current permissions policies (5)
    Other permissions policies (1/910)
    C
    Filter by Type
    Q ec2f
    X
    All types
    1 match
    <
    V
    Policy name
    A
    Type
    Description
    V
    AmazonEC2FullAccess
    AWS managed
    Provides full access to Amazon EC2 via t...
    Cancel
    Add permissions

[^59]: aws
    Services
    Q Search
    \[Alt+S\]
    4
    2
    N. Virginia
    joi
    VPC
    SO RDS
    $3
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    2 LAM
    O EC2
    19 Certificate Manager
    CloudFront
    Billing and Cost Management
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info Port range
    Source Info
    Description - optional Info
    Info
    sgr-003873713076bf5c2
    All traffic
    All
    Custom
    Q
    Allow unmanaged nodes to co
    Delete
    Allow unmanaged nodes to
    sg-Of9fa712e7f8c710a X
    communicate with control plane (all
    ports)
    sgr-03bcadb 148dee9c5b
    All traffic
    All
    All
    Custom
    Q
    Delete
    sg-0222ab5060dbb2dic X
    All traffic
    All
    All
    Anyw...
    Q 0.0.0.0/0
    Delete
    0.0.0.0/0 X
    Add rule
    A Rules with source of 0.0.0.0/0 or :/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only.
    X
    Cancel
    Preview changes
    Save rules

[^60]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ cd k8-ingress/
    I
    44 . 202 . 253. 109 \| 172. 31 .88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress \]$ cd app1/
    44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ git pull
    remote: Enumeratiog objects: 9, done.
    remote: Counting objects: 100% (9/9), done.
    remote: Compressing objects: 100% (5/5), done.
    remote: Total 6 (delta 1) , reused 6 (delta 1) , pack-reused 0
    Unpacking objects: 100% (6/6), 1.02 KiB \| 1. 02 MiB/s, done.
    From https: / /github. com/daws-76s/k8-ingress
    c9aafef. . b399660 main
    -> origin/main
    Updating caafef. .b399660
    Fast-forward
    app1/manifest . yaml \| 62 +++
    -++
    app2/manifest . yaml \| 62 ++++++++
    -+
    2 files changed, 124 insertions (+)
    create mode 100644 app1/manifest. yaml
    create mode 100644 app2/manifest. yaml
    44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubectl apply -f manifest. yaml
    deployment . apps/appl created
    service/appl created
    ingress . networking . k8s . io/appl created

[^61]: Protocol SSH
    . Host 44.202.253.109
    Login
    Password
    Session centos-8
    Commands
    . 0\*810
    44.202.253.109
    44 202 253.109 44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl . io
    <0> all
    <a>
    Attach
    <1>
    Logs
    Cluster: roboshop . us-east-1. eksctl . io
    <1> roboshop
    <ctrl-d> Delete
    <p>
    Logs Previous \|
    User :
    terraform@roboshop . us-east-1. eksctl . io
    <2> default
    <d>
    Describe
    <shift-f>
    Port-Forward
    K9s Rev: v0 . 32.1
    <e>
    Edit
    <Z>
    Sanitize
    K8s Rev: v1 . 29.0-eks-c417bb3
    <?>
    Help
    <s>
    Shell
    CPU :
    18
    <ctrl-k> Kill
    <o>
    Show Node
    MEM :
    178
    Pods (default) \[1\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM SCPU/R CPU/L &MEM/R &MEM/L IP
    NODE
    app1-5dc65d4bbb-m717r
    .
    1/1
    Running
    0
    0
    0
    0
    0
    0
    0 192 . 168 . 11 . 130
    ip-192-

[^62]: Hi: Services
    Search
    \[Alt+S\]
    . Virginia
    joindevops
    CO
    VPC
    302 RDS
    $3
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    EFS
    25 LAM
    EC2
    Certificate Manager
    CloudFront
    Billing and Cost Management
    Images
    EC2 > Load balancers
    AMIs
    AMI Catalog
    Introducing resource map for Application Load Balancers
    Give feedback
    X
    Elastic Block Store
    Resource map is a visual representation of the relationships between load balancer resources and provides the ability to view, explore, and
    troubleshoot the architecture of your load balancer. Resource map can be viewed on the load balancers detail page. Share feedback to help
    Volumes
    us improve your experience.
    Snapshots
    Lifecycle Manager
    Load balancers (1)
    G
    Actions
    Create load balancer
    Network & Security
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Security Groups
    Q Filter load balancers
    < 1
    >
    Elastic IPs
    Placement Groups
    Name
    DNS name
    State
    VPC ID
    Availability Zones
    Type
    Key Pairs
    0
    Network Interfaces
    k8s-joindevops-b17e2...
    k8s-joindevops-b17e2e01a3-6879700...
    Provisioning.. vpc-Of54622a00c6ed9...
    2. Availability Zones
    appli
    Load Balancing
    Load Balancers
    0 load balancers selected
    X
    Target Groups

[^63]: aws
    Services
    Q Search
    \[Alt+S\]
    A
    N. Virginia
    join
    CO VPC
    305
    RDS
    $3
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    EFS
    IAM
    EC2
    Certificate Manager
    CloudFront
    Billing and Cost Management
    IP
    HTTP: 80
    HTTP1
    vpc-Of54622a00c6ed964 \[
    EC2 Dashboard
    X
    EC2 Global View
    IP address type
    Load balancer
    IPV4
    k8s-joindevops-b17e2e01a3 \[
    Events
    Console-to-Code Preview
    7
    1 0
    0 1
    Instances
    Total targets
    Healthy
    Unhealthy
    Unused
    Initial
    Draining
    Instances
    0 Anomalous
    Instance Types
    Launch Templates
    Distribution of targets by Availability Zone (AZ)
    Select values in this table to see corresponding filters applied to the Registered targets table below.
    Spot Requests
    Savings Plans
    Reserved Instances
    Targets
    Monitoring
    Health checks
    Attributes
    Tags
    Dedicated Hosts
    Capacity Reservations
    New
    Registered targets (1) Info
    Anomaly mitigation: Not applicable
    G
    Deregister
    Register targets
    Target groups route requests to individual registered targets using the protocol and port number specified. Health checks are performed on all registered targets according to the target group's health check
    Images
    settings. Anomaly detection is automatically applied to HTTP/HTTPS target groups with at least 3 healthy targets.
    AMIs
    Q Filter targets
    <
    1
    AMI Catalog
    O
    IP address
    Port
    Zone
    4
    Health status V Health status details
    Anomaly detection result
    Elastic Block Store
    Volumes
    192.168.2.23
    80
    us-east-1b
    Initial
    Target registration is i...
    Normal

[^64]: Listener rules (2) Info
    Rule limits
    G
    Actions
    Add rule
    Traffic received by the listener is routed according to the default action and any additional rules. Rules are evaluated in priority order from the lowest value to the highest value.
    O Filter rules
    0
    Name tag
    Priority Conditions (If)
    Actions (Then)
    ARN
    . HTTP Host Header is app1.daws76s.online
    Forward to target group
    AND
    . k8s-default-app 1-b9fabeee34 \[Z: 1 (100%)
    ARN
    . Path Pattern is /\*
    . Group-level stickiness: Off
    Return fixed response

[^65]: Record for daws76s.online was successfully created.
    View status
    X
    Edit record
    X
    Route 53 propagates your changes to all of the Route 53 authoritative DNS servers within
    60 seconds. Use "View status" button to check propagation status.
    Record name Info
    Hosted zone details
    Edit hosted zone
    .daws76s.online
    Keep blank to create a record for the root domain.
    Record type Info
    Records (4)
    DNSSEC signing
    Hosted zone tags (0)
    A - Routes traffic to an IPv4 address and so...
    Alias
    Records (1/4) Info
    G
    Delete record
    Import zone file
    Create record
    Route traffic to Info
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    Alias to Application and Classic Load Balancer
    Q Filter records by property or value
    Type
    Routing policy
    Alias
    US East (N. Virginia)
    <
    1
    Q dualstack.k8s-roboshop-37213adecc-1414 X
    Record ... v Type v Routin... v Differ...
    Alias
    4
    Value/Route tr
    Alias hosted zone ID: Z35SXDOTRQ7X7K
    Routing policy Info
    ns-148.awsdns-
    ns-736.awsdns-
    Simple routing
    0
    daws 76s....
    NS
    Simple
    No
    ns-1112.awsdn:
    ns-1951.awsdn:
    Evaluate target health
    Yes
    O
    daws 765....
    SOA
    Simple
    No
    ns-148.awsdns-
    \*.daws76s...
    Cancel
    SWe
    A
    Simple
    Yes
    dualstack.k8s-jc

[^66]: C
    Not secure app1.daws76s.online
    Hello, I am from APP-1

[^67]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ cd . ./app2/
    44 . 202 . 253. 109 \| 172 . 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/app2 \]$ kubectl apply -f manifest. yaml
    deployment . apps/app2 created
    service/app2 created
    ingress . networking . k8s . io/app2 created

[^68]: Listener rules (3) Info
    Rule limits
    G
    Actions
    Add rule
    Traffic received by the listener is routed according to the default action and any additional rules. Rules are evaluated in priority order from the lowest value to the highest value.
    Q Filter rules
    Name tag
    Priority Conditions (If)
    Actions (Then)
    ARN
    . HTTP Host Header is app 1.daws76s.online,
    Forward to target group
    0
    AND
    . k8s-default-app1-b9fabeee34 \[Z: 1 (100%)
    ARN
    . Path Pattern is /\*
    . Group-level stickiness: Off
    O
    . Path Pattern is /\*, AND
    Forward to target group
    2
    . HTTP Host Header is app2.daws76s.online
    . k8s-default-app.2-e9f9e529be \[Z: 1 (100%)
    ARN
    . Group-level stickiness: Off
    Return fixed response
    Last
    0
    Default
    (default)
    If no other rule applies
    . Response code: 404
    . Response body
    ARN
    . Response content type: text/plain

[^69]: C
    A Not secure app2.daws76s.online
    Hello, I am from APP-2

[^70]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| https: //github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/app2 \]$ kubectl delete -f manifest. yaml
    deployment . apps "app2" deleted

[^71]: Rules
    Tags
    Listener rules (2) Info
    Rule limits
    Actions
    Add rule
    Traffic received by the listener is routed according to the default action and any additional rules. Rules are evaluated in priority order from the lowest value to the highest value.
    Q Filter rules
    Name tag
    Priority Conditions (If)
    Actions (Then)
    ARN
    . HTTP Host Header is app 1.daws76s.online,
    Forward to target group
    Loading...
    1
    AND
    . k8s-default-app 1-b9fabeee34 \[Z: 1 (100%)
    ARN
    . Path Pattern is /\*
    . Group-level stickiness: Off
    Return fixed response
    Last
    . Response code: 404
    Loading...
    If no other rule applies
    ARN
    (default)
    . Response body
    . Response content type: text/plain

[^72]: 44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: //github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/app2 \]$ cd . ./app1/
    I
    44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubectl delete -f manifest. yaml
    deployment . apps "app1" deleted
    service "appl' deleted
    ingress . networking . k8s . io "appl' deleted

[^73]: Load balancers
    G
    Actions
    Create load balancer
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Q Filter load balancers
    <
    1
    Name
    DNS name
    State
    VPC ID
    Availability Zones
    Type
    No load balancers
    You don't have any load balancers in us-east-1
    Create load balancer

[^74]: 44 . 202 . 253. 109 \| 172 . 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubectl get pods -n kube-system
    AGE
    NAME
    READY
    STATUS
    RESTARTS
    aws-load-balancer-controller-684c7bdd6d-fgw6r
    1/1
    Running
    13m
    1/1
    Running
    13m
    aws-load-balancer-controller-684c7bdd6d-wzkns
    OOO
    65m
    aws-node-8m6z1
    2/2
    Running
    2/2
    Running
    61m
    aws-node-dxvhb
    aws-node-vkpgj
    2/2
    Running
    107m
    coredns-54d6f577c6-4jjjn
    1/1
    Running
    65m
    OOOO
    coredns-54d6f577c6-gxnz5
    1/1
    Running
    64m
    ebs-csi-controller-cc4db67f7-mfwpq
    5/5
    Running
    59m
    ebs-csi-controller-cc4db67f7-vfc9c
    5/5
    Running
    59m
    ebs-csi-node-9w4qv
    3/3
    Running
    59m
    ebs-csi-node-kj8cm
    3/3
    Running
    59m
    OOOOOO
    ebs-csi-node-swqpr
    3/3
    Running
    59m
    1/1
    Running
    65m
    kube-proxy-4b7gk
    1/1
    Running
    61m
    kube-proxy-78rm8
    kube-proxy-plrcl
    1/1
    Running
    107m
    metrics-server-6db4d75b97-46wqx
    1/1
    Running
    O
    49m
    44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    centos@ip-172-31-88-240 \~/8-ingress/appl \]$ kubectl logs -n kube-system aws-load-balancer-controller-684c7bdd6d-fgw6r

[^75]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubectl get ingress
    NAME
    CLASS
    HOSTS
    ADDRESS
    PORTS
    AGE
    app1
    <none>
    appl . daws 76s . online
    80
    2m9s
    44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: //github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubectl describe ingress appl
    Name :
    app1
    Labels :
    <none>
    Namespace :
    roboshop
    Address :
    Ingress Class:
    <none>
    Default backend:
    <default>
    Rules :
    Host
    Path Backends
    appl . daws 76s . online
    app1: 80 ()
    Annotations :
    alb . ingress . kubernetes . io/group . name: joindevops
    alb. ingress . kubernetes . io/scheme: internet-facing
    alb. ingress . kubernetes . io/tags: Environment=dev, Team=test, Project=Roboshop
    alb. ingress . kubernetes . io/target-type: ip
    Events:
    <none>
    I

[^76]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-ingress . git
    \[ centos@ip-172-31-88-240 \~/k8-ingress/appl \]$ kubectl api-resources \| grep ingress
    ingressclassparams
    elbv2 . k8s . aws/vibetal
    false
    IngressClassParams
    ingressclasses
    networking . k8s . io/v1
    false
    IngressClass
    ingresses
    ing
    networking . k8s . io/v1
    true
    Ingress

[^77]: REPOS
    k8-databases > web > ! manifest.yaml > {} spec > \[ \] rules > {} 0 > {} http
    > dockerfiles
    194
    kind: Ingress
    > helm-charts
    195
    metadata:
    k8-databases
    196
    name: web
    > admin
    197
    namespace: roboshop
    198
    > cart
    annotations :
    199
    alb. ingress . kubernetes . io/scheme: internet-facing
    > catalogue
    200
    alb. ingress . kubernetes . io/target-type: ip
    > mongodb
    201
    alb. ingress . kubernetes . io/tags: Environment=dev, Team=test, Project=Roboshop
    > mysql
    202
    alb. ingress . kubernetes . io/group. name: roboshop
    > payment
    203
    spec:
    > rabbitmq
    204
    ingressClassName : alb
    > redis
    205
    rules :
    206
    host: "roboshop . daws76s . online"
    > shipping
    207
    http:
    > user
    208
    paths :
    web
    209
    pathType: Prefix
    ! manifest.yaml
    M
    210
    path: "/"
    ! namespace.yaml
    211
    backend:
    ! sc.yaml
    212
    service:
    213
    name : web
    > k8-eksctl
    214
    port :
    > k8-ingress
    215
    number : 80
    > k8-resources

[^78]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main daa9d47\] jenkins
    1 file changed, 43 insertions (+), 1 deletion(-)

[^79]: 44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-88-240 \~/k8-databases \]$ cd web/
    44 . 202 . 253. 109 \| 172. 31.88.240 \| t2.micro \| https: //github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-88-240 \~/k8-databases/web \]$ kubectl apply -f manifest. yaml
    configmap/web created
    deployment . apps/web created
    service/web created
    horizontalpodautoscaler . autoscaling/web created
    ingress . networking . k8s . io/web created

[^80]: Load balancers (1/2)
    C
    Actions
    Create load balancer
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Q Filter load balancers
    <1>
    Name
    4
    DNS name
    State
    VPC ID
    O
    k8s-roboshop-web-dd22d41672
    k8s-roboshop-web-dd22d41672-7d743a6325e9f859.elb.us-east-1.amazonaws.com
    Provisioning.. vpc-Of54
    k8s-roboshop-37213adecc
    k8s-roboshop-37213adecc-1414566212.us-east-1.elb.amazonaws.com
    Provisioning.. vpc-Of54

[^81]: Rules
    Tags
    Listener rules (2) Info
    Rule limits
    C
    Actions
    Add rule
    Traffic received by the listener is routed according to the default action and any additional rules. Rules are evaluated in priority order from the lowest value to the highest value.
    Q Filter rules
    O
    Name tag
    Priority Conditions (if)
    Actions (Then)
    ARN
    . HTTP Host Header is
    Forward to target group
    roboshop.daws76s.online, AND
    . k8s-roboshop-web-b0Obc4fa65 \[Z: 1 (100%)
    ARN
    . Path Pattern is /\*
    . Group-level stickiness: Off
    Return fixed response
    Last
    . Response code: 404
    Default
    (default)
    If no other rule applies
    ARN
    . Response body
    . Response content type: text/plain

[^82]: Record for daws76s.online was successfully created.
    View status
    X
    Edit record
    X
    Route 53 propagates your changes to all of the Route 53 authoritative DNS servers within
    60 seconds. Use "View status" button to check propagation status.
    Record name Info
    Hosted zone details
    Edit hosted zone
    .daws76s.online
    Keep blank to create a record for the root domain.
    Record type Info
    Records (4)
    DNSSEC signing
    Hosted zone tags (0)
    A - Routes traffic to an IPv4 address and so...
    Alias
    Records (1/4) Info
    G
    Delete record
    Import zone file
    Create record
    Route traffic to Info
    Automatic mode is the current search behavior optimized for best filter results. To change modes go to settings.
    Alias to Application and Classic Load Balancer
    Q Filter records by property or value
    Type
    Routing policy
    Alias
    US East (N. Virginia)
    <
    1
    Q dualstack.k8s-roboshop-37213adecc-1414 X
    Record ... v Type v Routin... v Differ...
    Alias
    4
    Value/Route tr
    Alias hosted zone ID: Z35SXDOTRQ7X7K
    Routing policy Info
    ns-148.awsdns-
    ns-736.awsdns-
    Simple routing
    0
    daws 76s....
    NS
    Simple
    No
    ns-1112.awsdn:
    ns-1951.awsdn:
    Evaluate target health
    Yes
    O
    daws 765....
    SOA
    Simple
    No
    ns-148.awsdns-
    \*.daws76s...
    Cancel
    SWe
    A
    Simple
    Yes
    dualstack.k8s-jc

[^83]: Targets
    Monitoring
    Health checks
    Attributes
    Tags
    Registered targets (1) Info
    Anomaly mitigation: Not applicable
    C
    Deregister
    Register targets
    Target groups route requests to individual registered targets using the protocol and port number specified. Health checks are performed on all registered targets according to the target group's health check
    settings. Anomaly detection is automatically applied to HTTP/HTTPS target groups with at least 3 healthy targets.
    Q Filter targets
    <
    1
    >
    O
    IP address
    \| Port V Zone
    Health status
    Health status details
    Anomaly detection result
    192.168.2.23
    80
    us-east-1b
    Initial
    Target registration is i...
    Normal

[^84]: Pods (roboshop) \[14\]
    PF READY STATUS
    RESTARTS CPU MEM $CPU/R CPU/L &MEM/R &MEM/L IP
    NODE
    NAME
    cart-586cd88d45-75bhc
    1/1
    Running
    22
    2
    17
    8 192 . 168 .22. 73
    ip-192-168-16-178. ec2. in
    catalogue-5c9ddf8bdf-vzfkv
    1/1
    Running
    O
    24
    19
    9 192 . 168. 20.29
    ip-192-168-22-189.ec2. in
    mongodb-0
    1/1
    Running
    0
    4 164
    n/a
    n/a
    n/a
    n/a 192. 168 . 20 . 158
    ip-192-168-19-21.ec2. int
    mongodb-1
    1/1
    Running
    0
    3
    166
    n/a
    n/a
    n/a
    n/a 192 . 168. 9.86
    ip-192-168-16-178. ec2. in
    1/1
    Running
    0
    1 233
    n/a
    n/a
    n/a
    n/a 192. 168 . 10.50
    ip-192-168-19-21. ec2. int
    mysql-0
    mysql-1
    1/1
    Running
    0
    1
    230
    n/a
    n/a
    n/a
    n/a 192. 168 . 10 .104
    ip-192-168-16-178. ec2 . in
    payment-86bfb56f45-2xb8d
    1/1
    Running
    0
    1
    34
    2
    1
    27
    13 192 . 168 .22 . 104
    ip-192-168-19-21.ec2. int
    rabbitmq-0
    1/1
    Running
    0
    2
    128
    n/a
    n/a
    n/a
    n/a 192. 168 . 13.14
    ip-192-168-22-189.ec2. in
    rabbitmq-1
    1/1
    Running
    0
    2 126
    n/a
    n/a
    n/a
    n/a 192 . 168. 28 .67
    ip-192-168-19-21.ec2. int
    redis-0
    1/1
    Running
    0
    2
    n/a
    n/a
    n/a
    n/a 192. 168 . 14. 110
    ip-192-168-22-189. ec2. in
    NN
    redis-1
    1/1
    Running
    O
    n/a
    n/a
    n/a
    n/a 192. 168.23.174
    ip-192-168-19-21.ec2. int
    shipping-cc66b4699-qj 9ms
    1/1
    Running
    0
    386
    0
    0
    150
    75 192 . 168. 21 .229
    ip-192-168-22-189. ec2 . in
    user-7bd579b765-vmdqb
    1/1
    Running
    O
    25
    2
    1
    20
    10 192 . 168.18.21
    ip-192-168-19-21.ec2. int
    web-75fd9d857d-zdmbv
    .
    1/1
    Running
    0
    4
    2
    1
    6
    3 192 . 168.2.23
    ip-192-168-16-178. ec2. in

[^85]: C
    A Not secure roboshop.daws76s.online/login
    Stan's Robot Shop
    Login / Register
    Welcome to Stan's Robot Shop
    Cart
    Here you will find all of Stan's friends. Have a browse around and
    Empty
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    . Artificial
    has been built using various technologies:
    Intelligence
    . Robot
    AngularJS (1 X)
    Nginx
    NodeJS
    Java
    Python
    Golang
    PHP (Apache)
    MongoDB
    Redis
    MySQL
    When deployed into an environment monitored by Instana, these
    technology stacks will be automatically detected and monitored,
    all with minimum configuration, Every request will be traced end to
    end. Stan will keep an eye on all those metrics, events and traces
    and let you know what needs your attention.
    To find out more visit the Instana site.
    All the code is available on Github.
    anonymous-2

[^86]: F
    C
    A Not secure roboshop.daws76s.online/payment
    Stan's Robot Shop
    Login/ Register
    Review your order
    Cart
    Order placed 11465476-df6d-4e2e-b660-8a74ee082ca8
    Empty
    Thank you for your order Continue shopping
    Categories
    . Artificial
    Intelligence
    . Robot
    o C3PO
    o Eve
    o K9
    o Kryten
    o Marvin
    o Mr Data
    o R2D2
    o Robbie
    O
    Stan
    siva

[^87]: Google
    apache benchmark install centos
    X
    Videos
    Download
    Ubuntu
    Images
    Shopping
    News
    Book

[^88]: \[ centos@ip-172-31-88-240 \~ \]$ sudo yum install httpd-tools -y
    Last metadata expiration check: 1:28:50 ago on Tue 05 Mar 2024 01:57:18 AM UTC.
    Dependencies resolved.
    Package
    Architecture
    Version
    Installing:
    httpd-tools
    x86 64
    2. 4.37-62 . module e18+657+88b2113f
    Installing dependencies:
    apr
    x86 64
    1.6.3-12.e18

[^89]: Google
    ab command
    X
    Images
    Videos
    Example
    In apache
    Linux
    Shopping
    Netstat
    Not found
    News
    Apache HTTP Server
    https://httpd.apache.org > ... > Version 2.4 > Programs :
    ab - Apache HTTP server benchmarking tool
    ab is a tool for benchmarking your Apache Hypertext Transfer Protocol (HTTP) server. It is
    designed to give you an impression of how your current Apache

[^90]: 44 . 202 . 253. 109 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ ab -n 100000 -c 1000 -k http: //roboshop. daws76s. on\]
    This is ApacheBench, Version 2.3 <$Revision: 1843412 $>
    Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www. zeustech.net/
    Licensed to The Apache Software Foundation, http: //www. apache. org/
    Benchmarking roboshop . daws 76s . online (be patient)
    Completed 10000 requests
    Completed 20000 requests
    Completed 30000 requests
    Completed 40000 requests
    Completed 50000 requests
    Completed 60000 requests
    Completed 70000
    red
    uests

[^91]: Connection Times (ms)
    min mean \[+/-sd\] median
    max
    Connect:
    0
    15 74.7
    7
    1063
    Processing :
    4
    691 2484.9
    390
    60177
    Waiting:
    2
    690 2484.9
    390
    60177
    Total :
    10 705 2491.0
    400
    60671
    Percentage of the requests served within a certain time (ms)
    508
    400
    668
    596
    758
    806
    I
    80%
    900
    908
    1080
    958
    1186
    98
    1282
    998
    1407
    100%
    60671 (longest request)

[^92]: Commands
    . 0\* 8 10
    44.202.253.109
    44.202 253.109
    44.202.253.109
    Context: terraform@roboshop . us-east-1 . eksctl . io
    <0> all
    <a>
    Attach
    <1>
    Logs
    Cluster: roboshop. us-east-1. eksctl . io
    <1> kube-system
    <ctrl-d> Delete
    <p>
    Logs Previl
    User :
    terraform@roboshop . us-east-1 . eksctl . io
    <2> roboshop
    <d>
    Describe
    <shift-f>
    Port-Forwal
    K9s Rev: V0 . 32.1
    <3> default
    <e>
    Edit
    <Z>
    Sanitize
    K8s Rev: v1 . 29.0-eks-c417bb3
    <?>
    Help
    <s>
    Shell
    CPU:
    4%
    <ctrl-k> Kill
    <O>
    Show Node
    MEM:
    18%
    Pods (roboshop) \[14\]
    NAME 1
    PF READY STATUS
    RESTARTS CPU MEM CPU/R CPU/L $MEM/R &MEM/L IP
    NODE
    cart-586cd88d45-75bhc
    1/1
    Running
    0
    24
    0
    18
    9 192 . 168.22. 73
    ip-192-168-16-178. ec2 . in
    catalogue-5c9ddf8bdf-vzfkv
    1/1
    Running
    O
    1
    25
    2
    19
    9 192 . 168.20.29
    ip-192-168-22-189. ec2. in
    mongodb-0
    1/1
    Running
    0
    4 165
    n/a
    n/a
    n/a
    n/a 192 . 168 . 20 .158
    ip-192-168-19-21.ec2. int
    mongodb-1
    1/1
    Running
    0
    3 166
    n/a
    n/a
    n/a
    n/a 192 . 168.9.86
    ip-192-168-16-178. ec2. in
    mysql-0
    1/1
    Running
    0
    1 233
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.50
    ip-192-168-19-21.ec2. int
    mysql-1
    1/1
    Running
    0
    1 244
    n/a
    n/a
    n/a
    n/a 192. 168 . 10. 104
    ip-192-168-16-178.ec2 . in
    payment-86bfb56f45-2xb8d
    1/1
    Running
    0
    1
    36
    2
    1
    28
    14 192 . 168 .22 . 104
    ip-192-168-19-21.ec2. int
    rabbitmq-0
    1/1
    Running
    0
    2 128
    n/a
    n/a
    n/a
    n/a 192. 168. 13.14
    ip-192-168-22-189.ec2. in
    rabbitmq-1
    1/1
    Running
    0
    2 126
    n/a
    n/a
    n/a
    n/a 192. 168. 28.67
    ip-192-168-19-21.ec2. int
    redis-0
    1/1
    Running
    0
    2
    2
    n/a
    n/a
    n/a
    n/a 192 . 168. 14 . 110
    ip-192-168-22-189. ec2. in
    redis-1
    1/1
    Running
    0
    1
    2
    n/a
    n/a
    n/a
    n/a 192. 168.23.174
    ip-192-168-19-21.ec2. int
    shipping-cc66b4699-qj9ms
    1/1
    Running
    1 391
    0
    0
    152
    76 192 . 168.21.229
    ip-192-168-22-189.ec2. in
    user-7bd579b765-vmdqb
    1/1
    Running
    0
    1
    25
    2
    1
    20
    10 192. 168. 18.21
    ip-192-168-19-21.ec2. int
    web-75fd9d857d-zambv
    1/1
    Running
    0 100
    6
    200
    100
    101
    5 192 . 168.2.23
    ip-192-168-16-178. ec2 . in

[^93]: 44.202.253.109 44.202 253.109 44.202.253.109
    Context: terraform@roboshop . us-east-1. eksctl. io
    <0> all
    <a>
    Attach
    <1>
    Logs
    Cluster: roboshop . us-east-1 . eksctl . io
    <1> kube-system
    <ctrl-d>
    Delete
    <p>
    Logs Previl
    User:
    terraform@roboshop . us-east-1 . eksctl . io
    <2> roboshop
    <d>
    Describe
    <shift-f> Port-Forwal
    K9s Rev: v0 . 32.1
    <3> default
    <e>
    Edit
    <Z>
    Sanitize
    K8s Rev: v1 . 29.0-eks-c417bb3
    < ?>
    Help
    <s>
    Shell
    CPU:
    4%
    <ctrl-k> Kill
    <o>
    Show Node
    MEM:
    18%
    Pods (roboshop) \[17\]
    NAME
    PF READY STATUS
    RESTARTS CPU MEM SCPU/R CPU/L .MEM/R &MEM/L IP
    NODE
    cart-586cd88d45-75bhc
    1/1
    Running
    1
    24
    2
    18
    9 192 . 168 . 22. 73
    ip-192-168-16-1'
    catalogue-5c9ddf8bdf-vzfkv
    1/1
    Running
    O
    1
    25
    2
    19
    9 192 . 168.20.29
    ip-192-168-22-18
    mongodb-0
    1/1
    Running
    0
    4 165
    n/a
    n/a
    n/a
    n/a 192 . 168. 20. 158
    ip-192-168-19-2
    mongodb-1
    1/1
    Running
    0
    3 166
    n/a
    n/a
    n/a
    n/a 192 . 168 .9.86
    ip-192-168-16-1'
    mysql-0
    1/1
    Running
    0
    1 233
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.50
    ip-192-168-19-2
    mysql-1
    1/1
    Running
    0
    1 244
    n/a
    n/a
    n/a
    n/a 192 . 168 . 10.104
    ip-192-168-16-1'
    payment-86bfb56f45-2xb8d
    1/1
    Running
    0
    H
    36
    2
    1
    28
    14 192. 168.22 .104
    ip-192-168-19-2
    rabbitmq-0
    1/1
    Running
    0
    2
    128
    n/a
    n/a
    n/a
    n/a 192. 168 . 13.14
    ip-192-168-22-18
    rabbitmq-1
    1/1
    Running
    0
    2 126
    n/a
    n/a
    n/a
    n/a 192 . 168 .28. 67
    ip-192-168-19-2
    redis-0
    1/1
    Running
    0
    n/a
    n/a
    n/a
    n/a 192 . 168. 14 . 110
    ip-192-168-22-1
    NOW
    redis-1
    1/1
    Running
    n/a
    n/a
    n/a
    n/a 192. 168 . 23 .174
    ip-192-168-19-2
    shipping-cc66b4699-qj9ms
    1/1
    Running
    391
    0
    152
    76 192 . 168.21.229
    ip-192-168-22-18
    user-7bd579b765-vmdqb
    1/1
    Running
    OOOHHHN
    25
    2
    1
    20
    10 192 . 168. 18.21
    ip-192-168-19-2
    Oooooo
    web-75fd9d857d-4n41d
    1/1
    Running
    0
    0
    0
    0 192 . 168.27.119
    ip-192-168-19-2
    web-75fd9d857d-8prdz
    1/1 1
    Running
    OOO
    O
    0
    0 192 . 168 .17. 126
    ip-192-168-22-18
    web-75fd9d857d-576s8
    1/1
    Running
    0
    0
    0
    0 192 . 168 . 14. 113
    ip-192-168-16-1
    web-75fd9d857d-zambv
    1/1
    Running
    0
    19
    38
    19
    9
    4 192 . 168.2.23
    ip-192-168-16-1

