---
title: 58Day_Kubernetes
uuid: b2c8c290-432a-11ef-b895-26e37c279344
version: 913
created: '2024-07-16T09:50:13+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#f8914d;">**External Volumes**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![643dd633-ea3b-4fae-8df4-76b26bc715f8.png|331](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/643dd633-ea3b-4fae-8df4-76b26bc715f8.png) [^1]

\

![005b8150-007b-487e-9da0-a5ea1d5d452c.png|640](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/005b8150-007b-487e-9da0-a5ea1d5d452c.png) [^2]

![b9a21dd4-adba-4eeb-898c-d398a9f9d03f.png|403](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b9a21dd4-adba-4eeb-898c-d398a9f9d03f.png) [^3]

\

![542257d8-ea59-40bf-a065-02d8402ec911.png|1126.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/542257d8-ea59-40bf-a065-02d8402ec911.png) [^4]

\

Creating a EBS volume

10gb volume created in same region us-east-1b where eks cluster nodes are present

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/1eae3ccc-624b-4565-a23b-c2efc45f279e.png) [^5]

\

Now installing EBS drivers (AWS-EBS-CSI drivers)

```
kubectl get nodes
```

```
kubectl apply -k "github.com/kuberneres-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/?ref=release-1.28"
```

![ebadeb4f-6a45-4e0e-a4a9-d003ffa1113b.png|1003.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/ebadeb4f-6a45-4e0e-a4a9-d003ffa1113b.png) [^6]

\

A proper role should be attached to EC2 instance to access EBS volume. (EC2 full access)

![5dc08937-f251-43dc-867c-ce45a8a621d3.png|962.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5dc08937-f251-43dc-867c-ce45a8a621d3.png) [^7]

\

this role helps ec2 instance to create volume, delete volume, update volume etc

![9b3739dd-3e1f-4ade-9511-50b2b4785ea3.png|967.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/9b3739dd-3e1f-4ade-9511-50b2b4785ea3.png) [^8]

\

# <mark style="background-color:#f8914d;">**Kubernetes volumes objects/resources**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

<mark>**Persistent volume - It represents the external storage**</mark>

<mark>**Persistent volume claim - pods should request volumes through PVC**</mark>

\

pod - pvc - pv - ebs

![b9bda56c-f4ec-4ce1-a7d6-8ceefd61c43e.png|586](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b9bda56c-f4ec-4ce1-a7d6-8ceefd61c43e.png) [^9]

\

# <mark style="background-color:#f8914d;">**EBS static provisioning**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

persistent volume

![43d5d192-3f61-461b-b9a0-d29ec6be70b8.png|770](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/43d5d192-3f61-461b-b9a0-d29ec6be70b8.png) [^10]

![993b5b9d-cabd-4729-a8f7-8bce8bcf0066.png|770](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/993b5b9d-cabd-4729-a8f7-8bce8bcf0066.png) [^11]

\

volume handle - we should give the volume id which we created(10Gb)

storage - 10gb or what every size we created

![273e4d45-e142-46a1-a188-67e716c0dc3f.png|1096](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/273e4d45-e142-46a1-a188-67e716c0dc3f.png) [^12]

PVC - persistent volume claim by POD

![4eb2d7f1-32a2-4370-8291-e2376243e658.png|1086.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/4eb2d7f1-32a2-4370-8291-e2376243e658.png) [^13]

\

POD creation and it claiming its volume(PV)

![413b2c77-fddd-4fe7-80cb-c3b232e239a0.png|802](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/413b2c77-fddd-4fe7-80cb-c3b232e239a0.png) [^14]

\

load balancer service to check if volume is working or not

![3f8b4cdf-67f0-4190-805c-dc5ef8f7ff9b.png|819](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/3f8b4cdf-67f0-4190-805c-dc5ef8f7ff9b.png) [^15]

\

![09d5e0c6-7d76-41fd-ba0b-8a87ac666202.png|939.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/09d5e0c6-7d76-41fd-ba0b-8a87ac666202.png) [^16]

\

<mark>**Node selectors   -- It decides where POD should create in cluster nodes, means it helps you decide in which node you can create your pod.**</mark>

\

giving labels to nodes

![8e4f0448-9376-40da-9d47-fc8606a6ccd8.png|1008](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/8e4f0448-9376-40da-9d47-fc8606a6ccd8.png) [^17]

```
kubeclt label nodes ip-192-168-43-218.ec2.internal zone=1b
kubeclt label nodes ip-192-168-52-69.ec2.internal zone=1b
```

![a7e4133e-a01d-4ff9-bce5-ac8beefcc33e.png|1007.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/a7e4133e-a01d-4ff9-bce5-ac8beefcc33e.png) [^18]

\

![2cc5f62e-05fc-4324-9373-7f466f2fcc25.png|926](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2cc5f62e-05fc-4324-9373-7f466f2fcc25.png) [^19]

\

git push & pull

![2131fb9f-566e-49a8-a9fa-2e53f9b57598.png|985.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2131fb9f-566e-49a8-a9fa-2e53f9b57598.png) [^20]

\

pod creation

```
kubectl apply -f 03-ebs-static.yaml
```

![1ac5774a-d5fd-41f8-97e2-50faa5dd994e.png|1001.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/1ac5774a-d5fd-41f8-97e2-50faa5dd994e.png) [^21]

\

```
kubectl get pod
```

![f6252412-5ca7-413c-b62c-93070ad2789e.png|1003.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/f6252412-5ca7-413c-b62c-93070ad2789e.png) [^22]

\

```
kubectl exec -it app -- bash
echo "<h1> hello from EBS static </h1>" > /usr/share/nginx/html/ebs.html
```

![feebc246-61b3-4046-8c41-629d6636da7b.png|1006.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/feebc246-61b3-4046-8c41-629d6636da7b.png) [^23]

\

```
kubectl get svc
```

![ad9e669b-3d31-4e32-8eba-578a039dbb08.png|1059.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/ad9e669b-3d31-4e32-8eba-578a039dbb08.png) [^24]

\

Allow all traffic in security group if you see health status is not **in-service**

![154cecd6-dafc-461e-8b08-dbea41b031d5.png|984.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/154cecd6-dafc-461e-8b08-dbea41b031d5.png) [^25]

\

We got the response

```
a3b305742919f4059a2a560638fac726-2083324696.us-east-1.elb.amazonaws.com/ebs.html
```

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/eac54c66-da98-489f-b062-dab4cb15adcf.png) [^26]

\

Now i am deleting the pod

```
kubectl delete pod app
```

![8e0ccade-5d06-43bb-8191-b9dc1d31020d.png|1005.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/8e0ccade-5d06-43bb-8191-b9dc1d31020d.png) [^27]

\

After deleting pod now the volume comes to available state.

![7352d1d9-2055-410e-8033-db839e3b5801.png|1000.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/7352d1d9-2055-410e-8033-db839e3b5801.png) [^28]

\

Now again i create a new POD

```
kubectl apply -f 03-ebs-static.yaml
```

![a6f592a4-d5ca-4002-99fd-153f20caf8fd.png|881.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/a6f592a4-d5ca-4002-99fd-153f20caf8fd.png) [^29]

\

now the volume came to in use

![52b16f93-cf48-4bce-83a8-4e1e6c002148.png|991.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/52b16f93-cf48-4bce-83a8-4e1e6c002148.png) [^30]

\

```
kubectl get pods
```

![00e81cec-0258-40fb-8a1f-d2177317ec4c.png|1065.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/00e81cec-0258-40fb-8a1f-d2177317ec4c.png) [^31]

\

```
kubectl get svc
```

![ad9e669b-3d31-4e32-8eba-578a039dbb08.png|1059](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/ad9e669b-3d31-4e32-8eba-578a039dbb08.png) [^32]

Old POD data is present in new POD.

```
a3b305742919f4059a2a560638fac726-2083324696.us-east-1.elb.amazonaws.com/ebs.html
```

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/8801e287-74da-4723-86bb-345dfeab205b.png) [^33]

```
kubectl delte -f 03-ebs-static.yaml
```

![08b35859-2c44-4dda-90c5-69680fc7f74f.png|981.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/08b35859-2c44-4dda-90c5-69680fc7f74f.png) [^34]

\

Delete volume manually

![f72c4ebd-6f9f-46cf-91e5-2cfc35b96993.png|922.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/f72c4ebd-6f9f-46cf-91e5-2cfc35b96993.png) [^35]

\

![c5694c35-f557-46a8-b8a6-9dcbe71558b0.png|585](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/c5694c35-f557-46a8-b8a6-9dcbe71558b0.png) [^36]

# <mark style="background-color:#f8914d;">**EBS Dynamic Provisioning**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![b57faf5c-78d2-4863-aa04-809723be00a2.png|597](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b57faf5c-78d2-4863-aa04-809723be00a2.png) [^37]

![29bf1d20-8f28-484b-9dd4-8c1f632be0f2.png|1038.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/29bf1d20-8f28-484b-9dd4-8c1f632be0f2.png) [^38]

\

Below 2 steps are common for both static & dynamic provisioning

![5fe0548f-aec0-4623-92fb-b392ef1cab72.png|1029.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5fe0548f-aec0-4623-92fb-b392ef1cab72.png) [^39]

\

\

In AWS we have two type of resources, 

1. vpc based resources

1. non-vpc based resources

\

Like we in Kubernetes we have two types of resources

1. namespaces

1. non-namespaces

![5ed999f1-b03f-40e5-aa6e-19e6a2ae55b2.png|971.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5ed999f1-b03f-40e5-aa6e-19e6a2ae55b2.png) [^40]

```
Kubectl api-resources
```

![065b82b8-8231-4a23-ab54-a5f3c6ffef74.png|1095.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/065b82b8-8231-4a23-ab54-a5f3c6ffef74.png) [^41]

\

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/c65817d7-f980-4e01-8ab7-df7bf301dc71.png) [^42]

\

git push & pull

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/00a2dc3b-e2b1-4f9f-b8e2-3f5265fc3ba8.png) [^43]

\

```
kubectl apply -f ebs-sc.yaml
```

![75022f6a-f46f-4cb7-90ba-873a11aaacbf.png|957](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/75022f6a-f46f-4cb7-90ba-873a11aaacbf.png) [^44]

\

```
kubectl get sc
```

![6e9fcb06-9f00-4836-9447-66f88f769503.png|1000.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/6e9fcb06-9f00-4836-9447-66f88f769503.png) [^45]

\

Now creating persistent volume(PV), persistent volume claim(PVC) & POD

![ff7dc19c-e6f9-4631-94e8-9d0b074f8324.png|1110](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/ff7dc19c-e6f9-4631-94e8-9d0b074f8324.png) [^46]

\

git push & pull

![45e3ebbc-b4fa-4828-ba81-93ecfa597700.png|1016](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/45e3ebbc-b4fa-4828-ba81-93ecfa597700.png) [^47]

\

```
kubectl apply -f 04-ebs-dynamic.yaml
```

![27f51974-0662-48f9-904b-ea22ba3bd04e.png|1093.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/27f51974-0662-48f9-904b-ea22ba3bd04e.png) [^48]

\

persistent volume is physical thing, where as PVC is a request

```
kubectl get pv
```

![6d26c270-d224-4880-96ea-e5aeaf9fd6b9.png|1101.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/6d26c270-d224-4880-96ea-e5aeaf9fd6b9.png) [^49]

\

```
kubectl get pods
```

![d6d77852-4c58-47cb-8a5b-5ba7eb33e6e4.png|1105.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/d6d77852-4c58-47cb-8a5b-5ba7eb33e6e4.png) [^50]

\

```
kubectl get pvc
```

![a0baedf3-df0a-4790-83b8-0db39066b578.png|1142.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/a0baedf3-df0a-4790-83b8-0db39066b578.png) [^51]

\

4gb volume created auto and came into use.

![4d74be86-d4d9-4870-815e-d0137fa17755.png|1143.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/4d74be86-d4d9-4870-815e-d0137fa17755.png) [^52]

\

Volume tags

![e277012f-fa8d-4d8e-b705-1a930ae79690.png|1121.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/e277012f-fa8d-4d8e-b705-1a930ae79690.png) [^53]

\

\

![e5f7600a-4b32-42f3-b671-ab908021382a.png|708](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/e5f7600a-4b32-42f3-b671-ab908021382a.png) [^54]

To check the storage classes & if you want not to delete use **retain** in reclaim policy 

```
kubectl get sc
```

![2593f54f-03a3-49f4-86a2-fe23b1a85e91.png|1155.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2593f54f-03a3-49f4-86a2-fe23b1a85e91.png) [^55]

\

```
kubectl delete -f -4-ebs-dynamic.yaml
```

![e44e9298-c753-4153-8100-44305b20f07a.png|1088.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/e44e9298-c753-4153-8100-44305b20f07a.png) [^56]

\

# <mark style="background-color:#f8914d;">**EFS static provisioning**<!-- {"backgroundCycleColor":"24"} --></mark>

![be0eba1c-26cb-4231-8310-6d4ddc8dc643.png|834.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/be0eba1c-26cb-4231-8310-6d4ddc8dc643.png) [^57]

\

Elastic File System like NFS, google drive 

![8500c870-0cec-4e42-8794-dadb915ebfb5.png|993.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/8500c870-0cec-4e42-8794-dadb915ebfb5.png) [^58]

\

![08b625de-9c1e-43d7-a158-0d08354f9e8c.png|600](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/08b625de-9c1e-43d7-a158-0d08354f9e8c.png) [^59]

\

![6516d427-8687-48b5-9efb-a6da2c23dd10.png|1026.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/6516d427-8687-48b5-9efb-a6da2c23dd10.png) [^60]

\

![def8a6cc-1745-4ed1-b7ac-7e2d566c3950.png|779](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/def8a6cc-1745-4ed1-b7ac-7e2d566c3950.png) [^61]

\

\

**security group in EFS**

\

![2c7f2d50-ecf4-4b19-8b36-05649aba6c74.png|1104.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2c7f2d50-ecf4-4b19-8b36-05649aba6c74.png) [^62]

![5da502cf-5ae2-407d-9f35-8aab1d4c0071.png|1143.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5da502cf-5ae2-407d-9f35-8aab1d4c0071.png) [^63]

\

<mark>**NFS port number is 2049**</mark>

\

Now allowing nodes(instances) SG to communicate with current SG with NFS port 2049

![3a8158db-0215-46ab-9192-2c6d1ca633c8.png|1058.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/3a8158db-0215-46ab-9192-2c6d1ca633c8.png) [^64]

\

Now installing drivers

![d4629b84-6b4a-40cc-8209-70580cefe1be.png|1065.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/d4629b84-6b4a-40cc-8209-70580cefe1be.png) [^65]

\

![164f3f28-f763-4212-92a2-8241306a60f9.png|1023.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/164f3f28-f763-4212-92a2-8241306a60f9.png) [^66]

```
kubectl kustomize \
"github.com/kubernetes-sigs/aws-efs-csi-driver/deploy/kubernetes/overlays/stable/ecr/?ref=release-1.7" > private-ecr-driver.yaml
```

![efbe494a-5852-4c59-bae6-25348a611e71.png|1226.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/efbe494a-5852-4c59-bae6-25348a611e71.png) [^67]

\

Installed driver now

```
kubectl apply -f private-ecr-driver.yaml
```

![648d45ce-3baa-4dbc-8438-ba1a3ed2f0b1.png|971.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/648d45ce-3baa-4dbc-8438-ba1a3ed2f0b1.png) [^68]

\

next steps

![8ac9876f-aae5-44ea-a401-bf473df7eb44.png|555](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/8ac9876f-aae5-44ea-a401-bf473df7eb44.png) [^69]

\

\

we need filesystem ID

![88b64441-d913-4a30-bde8-57ba0117baf9.png|886.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/88b64441-d913-4a30-bde8-57ba0117baf9.png) [^70]

\

change volume ID from your aws account (this persistent volume(PV))

![678522df-f442-42d8-a91d-d0493bc0f233.png|896](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/678522df-f442-42d8-a91d-d0493bc0f233.png) [^71]

\

persistent volume claim(PVC)

![b6323ad0-53d3-45cd-8678-4d00d5ee7b0c.png|877](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b6323ad0-53d3-45cd-8678-4d00d5ee7b0c.png) [^72]

\

pod & service

![2130bb8f-00f1-4549-b73a-4e5346292876.png|963](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2130bb8f-00f1-4549-b73a-4e5346292876.png) [^73]

\

git push & pull

![ff512c7b-75a2-41af-8a3d-3b19c8ecdba1.png|952.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/ff512c7b-75a2-41af-8a3d-3b19c8ecdba1.png) [^74]

\

POD creation

```
kubectl apply -f 05-efs-static.yaml
```

![aabfaff6-fcda-4738-a849-0337b0cde77f.png|1077.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/aabfaff6-fcda-4738-a849-0337b0cde77f.png) [^75]

\

```
kubectl get pods
```

![93861889-9b91-40df-839a-42f735b1225c.png|962.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/93861889-9b91-40df-839a-42f735b1225c.png) [^76]![524a8ebd-22ed-450d-a757-d75d21add7b4.png|959.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/524a8ebd-22ed-450d-a757-d75d21add7b4.png) [^77]

\

```
kubectl exec -it app -- bash
```

```html
echo "<h1> hello from EFS static </h1>" > /usr/share/nginx/html/efs.html
```

![ae375a56-b504-4570-88e5-068f5ff1149e.png|1119.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/ae375a56-b504-4570-88e5-068f5ff1149e.png) [^78]

![a9ddbc2e-4314-409a-8588-6f3d3ca8e2d7.png|969.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/a9ddbc2e-4314-409a-8588-6f3d3ca8e2d7.png) [^79]

\

```html
curl localhost/efs.html
```

![fd6b39ce-faca-41ec-b01b-437e6201803a.png|1075.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/fd6b39ce-faca-41ec-b01b-437e6201803a.png) [^80]

```
kubectl get svc
```

![cc1753e9-0bc4-48a1-9565-10bdda496348.png|1116.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/cc1753e9-0bc4-48a1-9565-10bdda496348.png) [^81]

\

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/714032de-ea08-48a4-941a-aabfaadb381b.png) [^82]

\

Now deleting the POD but data should not delete

```
kubectl delete pod app
```

![580ff927-db91-405d-b42f-c0ef943e1e7f.png|1054.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/580ff927-db91-405d-b42f-c0ef943e1e7f.png) [^83]

\

\

creating new POD to check if data comes to new pod or not

```
kubectl apply -f 05-efs-static.yaml
```

![08ac866f-1c72-4df5-99f5-53710907bb82.png|1036.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/08ac866f-1c72-4df5-99f5-53710907bb82.png) [^84]

\

so data is not deleted

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/6013e9c3-ecf0-4c3e-83ac-3f9a6b721a9e.png) [^85]

Now delete the pods 

\

\

# <mark style="background-color:#f8914d;">**EFS Dynamic provisioning**<!-- {"backgroundCycleColor":"24"} --></mark>

\

\

creating new EFS

![5a00914a-3ed5-42bd-bc80-284273c3b275.png|607](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5a00914a-3ed5-42bd-bc80-284273c3b275.png) [^86]

![cef2f37b-5566-4759-a1a5-042620b0ec64.png|959.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/cef2f37b-5566-4759-a1a5-042620b0ec64.png) [^87]

\

get Filesystem ID

![e8fe1377-1fda-4193-89d4-3a4638c01fc9.png|924](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/e8fe1377-1fda-4193-89d4-3a4638c01fc9.png) [^88]

\

storage class creation(SC)

![](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2d916269-2f79-433b-b110-d8a6db220898.png) [^89]

\

git push & pull

![2fefedb6-fa80-4640-9e50-5acdf3166298.png|851](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2fefedb6-fa80-4640-9e50-5acdf3166298.png) [^90]

\

creating storage class

```
kubectl apply -f efs-sc.yaml
kubectl get sc
```

![d7c59566-4bcb-435e-b366-2f90be88c9fc.png|992.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/d7c59566-4bcb-435e-b366-2f90be88c9fc.png) [^91]

\

multiple pods creation and check if same data is accessible by other pods

![482f42a3-0f0c-4f42-9e4f-326a70c6a791.png|911](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/482f42a3-0f0c-4f42-9e4f-326a70c6a791.png) [^92]

\

git push & pull

![b14a367d-6290-4b2b-87fb-60694f473375.png|979](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b14a367d-6290-4b2b-87fb-60694f473375.png) [^93]

\

```
kubectl apply -f 06-efs-dynamic.yaml
```

![c4121d2f-04bb-42a6-aae9-bb0e7c612358.png|1101.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/c4121d2f-04bb-42a6-aae9-bb0e7c612358.png) [^94]

\

```
kubectl get pods
```

![f408bea8-11bc-4e75-b39b-665bf744fb77.png|1186.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/f408bea8-11bc-4e75-b39b-665bf744fb77.png) [^95]

\

command when pods creating and check its exact status

```
watch kubectl get pods
```

![3c573d09-49e1-4867-bb76-a08755080d49.png|1179.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/3c573d09-49e1-4867-bb76-a08755080d49.png) [^96]

![7d5dafbc-65c4-4430-9d1b-710a4d92f8b5.png|1077.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/7d5dafbc-65c4-4430-9d1b-710a4d92f8b5.png) [^97]

\

if you don't see access point, below are troubleshoot steps

![3ce11632-65aa-44fa-baac-ad2f23885581.png|1127.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/3ce11632-65aa-44fa-baac-ad2f23885581.png) [^98]

![2b6e4588-6d8c-453a-be5c-d75d664bf413.png|1133.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/2b6e4588-6d8c-453a-be5c-d75d664bf413.png) [^99]

![1e02bc6c-aa76-4771-83e8-78c47c63af0d.png|1135.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/1e02bc6c-aa76-4771-83e8-78c47c63af0d.png) [^100]

\

giving access to cluster nodes

![33ca1739-570c-43c8-8a58-43db4c4978f3.png|1142.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/33ca1739-570c-43c8-8a58-43db4c4978f3.png) [^101]

\

\

now delete old and create new pod

![1a21ed0f-b220-4781-bb45-c00d17bd3e09.png|1155.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/1a21ed0f-b220-4781-bb45-c00d17bd3e09.png) [^102]

\

\

Now check if access points created or not in EFS.

\

![c40877c0-4711-4562-860c-a81598fc7e52.png|1090.3333740234375](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/c40877c0-4711-4562-860c-a81598fc7e52.png) [^103]

\

[^1]: 1. static provisioning
    2. dynamic provisioning

[^2]: HD, Cloud drives
    HD sits near to computer, as near as possible
    Cloud drives are network drives like NFS. .
    storage is very crucial
    static provisioning
    EBS, EFS I
    Elastic block store --> HD
    Elastic file system --> NFS

[^3]: Amazon EKS

[^4]: static
    1. first we need to create storage, either storage admin or k8 admin will create the storage
    2. we need to make this volume available to k8 cluster. we should install drivers.
    aws-ebs-csi drivers should be installed
    3. a proper role should be attached to ec2 instance to access EBS.

[^5]: vol-0956046ae862ee 1ff
    9p3
    10 GiB
    3000
    125
    2024/02/28 07:28 GMT +5:...

[^6]: 44 . 204 . 86.206 \| 172 . 31 . 92. 165 \| t2.micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-192-168-24-106. ec2 . internal
    Ready
    <none>
    17m
    v1.27.9-eks-5eOfdde
    ip-192-168-43-218.ec2 . internal
    Ready
    <none>
    17m
    v1.27.9-eks-5eOfdde
    ip-192-168-53-69. ec2 . internal
    Ready
    <none>
    17m
    v1 .27.9-eks-5eOfdde
    44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl apply -k "github. com/kubernetes-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/?ref=r
    elease-1 .28"
    serviceaccount/ebs-csi-controller-sa created
    serviceaccount/ebs-csi-node-sa created
    role . rbac . authorization. k8s . io/ebs-csi-leases-role created
    clusterrole . rbac . authorization. k8s . io/ebs-csi-node-role created
    clusterrole . rbac . authorization. k8s . io/ebs-external-attacher-role created
    clusterrole. rbac . authorization. k8s . io/ebs-external-provisioner-role created
    clusterrole . rbac . authorization . k8s . io/ebs-external-resizer-role created
    clusterrole . rbac . authorization. k8s . io/ebs-external-snapshotter-role created
    rolebinding . rbac . authorization. k8s . io/ebs-csi-leases-rolebinding created
    clusterrolebinding . rbac . authorization. k8s . io/ebs-csi-attacher-binding created
    clusterrolebinding . rbac . authorization. k8s . io/ebs-csi-node-getter-binding created
    clusterrolebinding . rbac . authorization. k8s . io/ebs-csi-provisioner-binding created
    clusterrolebinding . rbac . authorization. k8s . io/ebs-csi-resizer-binding created
    clusterrolebinding . rbac . authorization. k8s . io/ebs-csi-snapshotter-binding created
    deployment . apps/ebs-csi-controller created
    poddisruptionbudget. policy/ebs-csi-controller created
    daemonset . apps/ebs-csi-node created
    csidriver . storage . k8s . io/ebs . csi . aws . com created

[^7]: aws
    Services
    Q Search
    \[Alt+S\]
    A
    Global
    joindevop
    VPC
    303 RDS
    $3
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    EFS
    AS IAM
    EC2
    Certificate Manager
    CloudFront
    Billing and Cost Management
    Last activity
    Maximum session duration
    Identity and Access
    X
    13 minutes ago
    1 hour
    Management (IAM)
    Permissions
    Trust relationships
    Tags (6)
    Access Advisor
    Revoke sessions
    Q Search IAM
    Dashboard
    Permissions policies (4) Info
    G
    Simulate \[
    Remove
    Add permissions
    You can attach up to 10 managed policies.
    Attach policies
    Access management
    Filter by Type
    Create inline policy
    User groups
    Q Search
    All types
    <1 >
    Users
    Roles
    O
    Policy name \[Z
    Type
    Attached entities
    Policies
    0
    AmazonEC2ContainerRegistryReadOnly
    AWS managed
    Identity providers
    Account settings
    AmazonEKS_CNI Policy
    AWS managed
    1- 1- 1- 1-
    0
    AmazonEKSWorkerNodePolicy
    AWS managed
    Access reports
    Access Analyzer
    AmazonSSMManagedInstanceCore
    AWS managed
    External access
    Unused access
    Permissions boundary (not set)
    Analyzer settings

[^8]: Q ec2
    X
    All types
    29 matches
    < 1
    Policy name
    Type
    4
    Description
    O
    AmazonEC2ContainerRegistryFullAccess
    AWS managed
    Provides administrative access to Ama...
    AmazonEC2ContainerRegistryPowerUser
    AWS managed
    Provides full access to Amazon EC2 Co...
    AmazonEC2ContainerServiceAutoscaleRole
    AWS managed
    Policy to enable Task Autoscaling for A...
    0
    AmazonEC2ContainerServiceEventsRole
    AWS managed
    Policy to enable CloudWatch Events fo...
    0
    AmazonEC2ContainerServiceforEC2Role
    AWS managed
    Default policy for the Amazon EC2 Rol...
    AmazonEC2ContainerServiceRole
    AWS managed
    Default policy for Amazon ECS service ...
    AmazonEC2FullAccess
    AWS managed
    Provides full access to Amazon EC2 via...
    + AmazonEC2ReadOnlyAccess
    AWS managed
    Provides read only access to Amazon E...

[^9]: K
    Amazon EKS
    F--7
    PVC
    EBS

[^10]: Introduction
    Managing storage is a distinct problem from managing compute instances. The PersistentVolume
    subsystem provides an API for users and administrators that abstracts details of how storage is
    provided from how it is consumer To do this, we introduce two new API resources:
    PersistentVolume and PersistentVolumeClaim.

[^11]: A PersistentVolume (PV) is a piece of storage in the cluster that has been provisioned by an
    administrator or dynamically provisioned using Storage Classes. It is a resource in the cluster just
    like a node is a cluster resource. PVs are volume plugins like Volumes, but have a lifecycle
    independent of any individual Pod that uses the PV. This API object captures the details of the
    implementation of the storage, be that NFS, iSCSI, or a cloud-provider-specific storage system

[^12]: REPOS
    k8-resources > storage > ! 03-ebs-static.yaml > {} spec > {} csi > @ volumeHandle
    Lalalogue
    1
    apiVersion: v1
    > catalogue-deploy
    2
    kind: PersistentVolume
    > dockerfiles
    3
    metadata:
    > k8-eksctl
    4
    name: ebs-static
    k8-resources
    5
    spec:
    > 01-namespace
    6
    accessModes :
    7
    > 02-pods
    ReadWriteOnce #EBS volume should have readwriteonce, because it HD.
    18
    capacity:
    > service
    9
    storage: 10Gi
    sets
    csi:
    V
    storage
    11
    driver: ebs. csi. aws . com
    ! 01-emptyDir.yaml
    12
    fsType: ext4
    ! 02-hostpath.yaml
    13
    volumeHandle: vol-0956046ae862eelff
    ! 03-ebs-static.yaml -

[^13]: REPOS
    k8-resources > storage > ! 03-ebs-static.yaml > @apiVersion
    Laldiogue
    8
    capacity:
    > catalogue-deploy
    9
    storage: 10Gi
    > dockerfiles
    10
    csi:
    > k8-eksctl
    11
    driver: ebs. csi. aws . com
    k8-resources
    12
    fsType: ext4
    > 01-namespace
    13
    volumeHandle: vol-0956046ae862eelff
    14
    > 02-pods
    15
    apiVersion: v1
    > service
    16
    kind: PersistentVolumeClaim
    > sets
    17
    metadata :
    storage
    18
    name: ebs-static
    ! 01-emptyDir.yaml
    19
    spec:
    ! 02-hostpath.yaml
    20
    storageClassName : ."" .# Empty string must be explicitly set otherwise default StorageClass
    ! 03-ebs-static.yaml - U
    will be set. for static . provisioning this is empty
    21
    volumeName: ebs-static
    > k8-roboshop
    22
    accessModes :
    > roboshop-ansible-roles
    23
    ReadWriteOnce
    > roboshop-ansible-rol.
    24
    resources :
    > roboshop-docker
    25
    requests :
    > roboshop-infra-dev
    26
    storage : 5Gi

[^14]: V REPOS
    k8-resources > storage > ! 03-ebs-static.yaml > {} spec > \[ \] volumes >
    Lalalogue
    > catalogue-deploy
    27
    28
    apiVersion: v1
    > dockerfiles
    29
    kind: Pod
    > k8-eksctl
    30
    metadata:
    k8-resources
    31
    name: app
    > 01-namespace
    32
    labels:
    > 02-pods
    33
    demo: ebs-static
    > service
    34
    spec:
    35
    containers :
    > sets
    36
    name: nginx
    storage
    37
    image: nginx
    ! 01-emptyDir.yaml
    38
    volumeMounts :
    ! 02-hostpath.yaml
    39
    name: nginx-data
    ! 03-ebs-static.yaml
    U
    40
    mountPath: /usr/share/nginx/html
    > k8-roboshop
    41
    volumes :
    42
    > roboshop-ansible-roles
    name: nginx-data
    43
    persistentVolumeClaim:
    > roboshop-ansible-rol..
    44
    claimName: ebs-static
    > roboshop-docker

[^15]: REPOS
    k8-resources > storage > ! 03-ebs-static.yaml > {} spec > {} selector > > demo
    Laldivgue
    > catalogue-deploy
    35
    containers :
    > dockerfiles
    36
    - name: nginx
    37
    > k8-eksctl
    image: nginx
    38
    volumeMounts :
    k8-resources
    39
    - name: nginx-data
    > 01-namespace
    40
    mountPath: /usr/share/nginx/html
    > 02-pods
    41
    volumes :
    > service
    42
    - name: nginx-data
    43
    sets
    persistentVolumeClaim:
    44
    claimName: ebs-static
    storage
    45
    ! 01-emptyDir.yaml
    46
    apiVersion: v1
    ! 02-hostpath.yaml
    47
    kind: Service
    ! 03-ebs-static.yaml -U
    48
    metadata:
    > k8-roboshop
    49
    name: ebs-static
    > roboshop-ansible-roles
    spec :
    151
    > roboshop-ansible-rol.
    type: LoadBalancer
    521
    selector:
    > roboshop-docker
    53
    demo: ebs-static
    > roboshop-infra-dev
    54
    ports :
    I
    > roboshop-infra-prod
    55
    -
    protocol: TCP
    > roboshop-shared-libr.
    56
    port: 80 #service-port
    - -L. . .L. ...
    57
    targetPort: 80 #container-port
    > OUTLINE

[^16]: 1. when you apply, where your pod is getting created? any worker node

[^17]: 44 . 204 . 86.206 \| 172. 31 . 92.165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-192-168-24-106. ec2. internal
    Ready
    <none>
    50m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-43-218. ec2. internal
    Ready
    <none>
    50m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-53-69.ec2. internal
    Ready
    <none>
    50m
    v1.27.9-eks-5eOfdde

[^18]: 44 . 204 . 86.206 \| 172. 31 . 92.165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl label nodes ip-192-168-43-218. ec2. internal zone=1b
    node/ip-192-168-43-218. ec2. internal labeled
    44 . 204. 86.206 \| 172. 31 . 92.165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl label nodes ip-192-168-53-69. ec2. internal zone=1b
    node/ip-192-168-53-69. ec2. internal labeled

[^19]: V
    REPOS
    k8-resources > storage > ! 03-ebs-static.yaml > {} spec > {} nodeSelector > ) zo
    Lalalogue
    IlicLauaLa .
    > catalogue-deploy
    31
    name: app
    > dockerfiles
    32
    labels :
    33
    demo: ebs-static
    > k8-eksctl
    34
    spec:
    k8-resources
    35
    containers :
    > 01-namespace
    36
    name : nginx
    > 02-pods
    37
    image: nginx
    > service
    38
    volumeMounts :
    > sets
    39
    name: nginx-data
    40
    mountPath: /usr/share/nginx/html
    storage
    41
    nodeSelector:
    ! 01-emptyDir.yaml
    42
    one : 1b
    ! 02-hostpath.yaml
    43
    Volumes :
    ! 03-ebs-static.yaml - U
    44
    name: nginx-data
    > k8-roboshop
    45
    persistentVolumeClaim:
    > roboshop-ansible-roles
    46
    claimName: ebs-static

[^20]: 44 . 204 . 86.206 \| 172. 31. 92.165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ git clone https: //github. com/daws-76s/k8-resources . git
    Cloning into 'k8-resources'
    remote: Enumeratiog objects: 115, done.
    remote: Counting objects: 100% (115/115), done.
    remote: Compressing objects: 100% (80/80) , done.

[^21]: 44 . 204 . 86.206 \| 172. 31. 92.165 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources \]$ cd storage/
    44 . 204. 86.206 \| 172 . 31. 92.165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 03-ebs-static. yaml
    persistentvolume/ebs-static created
    persistentvolumeclaim/ebs-static created
    pod/app created
    service/ebs-static created

[^22]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pod
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    0/1
    Pending
    0
    5s
    44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pod
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    0
    31s

[^23]: 44 . 204. 86. 206 \| 172 . 31 . 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl exec -it app -- bash
    root@app: /# echo "<h1>Hello from EBS Static</h1>" > /usr/share/nginx/html/ebs .html
    root@app : /#

[^24]: 44 . 204. 86.206 \| 172. 31 . 92. 165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AG
    E
    ebs-static
    LoadBalancer
    10 . 100 . 196. 78
    a3b305742919f4059a2a560638fac726-2083324696. us-east-1. elb . amazonaws . com
    80 : 30189/TCP
    10
    4s
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    62
    m

[^25]: EC2 > Load balancers
    Load balancers (1/1)
    C
    Actions
    Create load balancer
    V
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Q Filter load balancers
    <
    1
    >
    Name
    4
    DNS name
    4
    State
    4
    VPC ID
    Availability Zones
    Type
    =
    Load balancer: a3b305742919f4059a2a560638fac726
    X
    Details
    Listeners
    Network mapping
    Security
    Health checks
    Target instances
    Monitoring
    Attributes
    Tags
    Target instances (3)
    Connection draining: Off
    C
    Deregister
    Manage instances
    Instances currently registered to your load balancer are displayed. To deregister instances, select them, then choose Deregister. To register and deregister instances simultaneously, choose Manage
    instances.
    Q Filter target instances
    < 1 >
    O
    Instance ID
    Name
    Health status
    Health status description
    Security g
    O
    i-0326608a1b75feelc
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluste
    0
    i-00334d3235bb816f9
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluste

[^26]: F
    C
    Not secure a3b305742919/4059a2a560638fac726-2083324696.us-east-1.elb.amazonaws.com/ebs.html
    Hello from EBS Static

[^27]: 44 . 204 .86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl delete pod app
    pod "app" deleted

[^28]: Volumes (5) Info
    C
    Actions
    Q Search
    IOPS
    V
    Throughput \| Snapshot
    Created
    Availability Zone
    V
    Volume state V Alarm status
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT+5:...
    us-east-1c
    In-use
    No alarms
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    No alarms
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    No alarms
    3000
    125
    2024/02/28 07:28 GMT+5:...
    us-east-1b
    Available
    No alarms
    100
    snap-Od6f961...
    2024/02/28 06:40 GMT +5:...
    us-east-1a
    In-use
    No alarms

[^29]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 03-ebs-static. yaml
    persistentvolume/ebs-static unchanged
    persistentvolumeclaim/ebs-static unchanged
    pod/app created
    service/ebs-static unchanged

[^30]: Volumes (5) Info
    C
    Actions
    Create volume
    Q Search
    <
    1
    Type
    v
    Size
    Sdol 4
    Throughput
    Snapshot
    v
    Created
    4
    Availability Zone
    4
    Volume state
    3d8d46cb02f
    gp3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1c
    In-use
    d11e86472c8
    gp3
    80 GIB
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    3124630a7a4
    gp3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    6ae862ee 1ff
    9p3
    10 GIB
    3000
    125
    2024/02/28 07:28 GMT+5:...
    us-east-1b
    In-use
    3547b49de41
    gp2
    10 GIB
    100
    snap-Od6f961...
    2024/02/28 06:40 GMT +5:...
    us-east-1a
    In-use

[^31]: 44 . 204 . 86.206 \| 172. 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    0
    61s

[^32]: 44 . 204. 86.206 \| 172. 31 . 92. 165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AG
    E
    ebs-static
    LoadBalancer
    10 . 100 . 196. 78
    a3b305742919f4059a2a560638fac726-2083324696. us-east-1. elb . amazonaws . com
    80 : 30189/TCP
    10
    4s
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    62
    m

[^33]: ) daws-76s/k8-resourcead balancers \| EC2 x \| eksctl-roboshop-nod x Volumes \| EC2 \| us-t x / storage drawio - dra
    F
    C
    A Not secure a3b305742919/4059a2560638fac726-2083324696.us-east-1.elb.amazonaws.com/ebs.html
    Hello from EBS Static

[^34]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl delete -f 03-ebs-static. yaml
    persistentvolume "ebs-static" deleted
    storage drawio - draw.ic - Goo_
    persistentvolumeclaim "ebs-static" deleted
    pod "app" deleted
    service "ebs-static" deleted

[^35]: Volumes (1/5) Info
    G
    Actions
    Create volume
    Q Search
    Modify volume
    Create snapshot
    -
    Name
    Volume ID
    Type Size
    IOPS
    Throughput Snapshot
    Create snapshot lifecycle policy
    roboshop-spot...
    vol-00a77f3d8d46cb02f
    gp3
    80 GIB
    3000
    125
    snap-0647
    Delete volume
    roboshop-spot...
    vol-016614d11e86472c8
    9p3
    80 GIB
    3000
    125
    snap-0647
    Attach volume
    roboshop-spot...
    vol-Of6fd43124630a7a4
    9p3
    80 GiB
    3000
    125
    snap-0647(
    Detach volume
    V
    vol-0956046ae862ee 1ff
    gp3
    10 GiB
    3000
    125
    Force detach volume
    O
    workstation-e...
    vol-00043a3547b49de41
    gp2
    10 GiB
    100
    snap-Od6fs
    Manage auto-enabled 1/O
    =
    Manage tags
    Volume ID: vol-0956046ae862ee 1ff
    Fault injection

[^36]: Static Provisioning
    Kid
    Mother
    Father
    Money
    --
    Storage
    pod
    Pod
    PVC
    PV
    Storage

[^37]: Dynamic Provisioning
    paytm
    III
    BANK ACCOUNT
    Kid
    Mother
    Father's
    Bank
    E-Wallet
    Account
    Storage
    pod

[^38]: 1. volume should be created automatically.
    2. there is another object called storageClass that can create storage dynamically based on
    the request.
    here external volume and pv would be created automatically by storageClass...

[^39]: 2. we need to make this volume available to k8 cluster. we should install drivers.
    aws-ebs-csi drivers should be installed
    3. a proper role should be attached to ec2 instance to access EBS.

[^40]: since storageClass is cluster level resource, admins should create this.
    EBS will have one storageclass cluster wide.
    I

[^41]: 44 . 204 . 86.206 \| 172 . 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl api-resources
    NAME
    SHORTNAMES
    APIVERSION
    NAMESPACED
    KIND
    bindings
    v1
    true
    Binding
    componentstatuses
    CS
    v1
    false
    ComponentStatus
    configmaps
    cm
    v1
    true
    ConfigMap
    endpoints
    ep
    v1
    true
    Endpoints
    events
    ev
    v1
    true
    Event
    limitranges
    limits
    v1
    true
    LimitRange
    namespaces
    ns
    v1
    false
    Namespace

[^42]: V REPOS
    k8-resources > storage > ! ebs-sc.yaml > volumeBindingMode
    aockermies
    apiVersion: storage. k8s . io/v1
    > k8-eksctl
    2
    kind: StorageClass
    k8-resources
    P
    metadata:
    > 01-namespace
    4
    name: ebs-sc
    > 02-pods
    5
    provisioner: ebs . csi. aws. com
    6
    volumeBindingMode: WaitForFirstConsumer
    > service
    > sets
    storage -
    I
    ! 01-emptyDir.yaml
    ! 02-hostpath.yaml
    ! 03-ebs-static.yaml
    ! 04-ebs-dynamic.ya... U
    ! ebs-sc.yaml -
    U

[^43]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main ald8d6c\] jenkins
    2 files changed, 8 insertions (+)
    create mode. 100644 storage /04-ebs

[^44]: 44 . 204. 86.206 \| 172 . 31.92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f ebs-sc. yaml
    storageclass . storage . k8s . io/ebs-sc created
    44 . 204. 86.206 \| 172 . 31. 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$

[^45]: 44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get sc
    NAME
    PROVISIONER
    RECLAIMPOLICY
    VOLUMEBINDINGMODE
    ALLOWVOLUMEEXPANSION
    AGE
    ebs-sc
    ebs . csi . aws . com
    Delete
    WaitForFirstConsumer
    false
    6s
    gp2 (default)
    kubernetes . io/aws-ebs
    Delete
    WaitForFirstConsumer
    false
    7 4m

[^46]: V REPOS
    k8-resources > storage > ! 04-ebs-dynamic.yaml > {} spec > {} resources
    aockermes
    apiVersion: v1
    > k8-eksctl
    N
    kind: PersistentVolumeClaim
    k8-resources
    3
    metadata :
    > 01-namespace
    4
    name: ebs-dynamic
    > 02-pods
    5
    spec :
    6
    > service
    accessModes :
    7
    -
    ReadWriteOnce
    > sets
    8
    storageClassName: ebs-sc
    storage
    9
    resources :
    ! 01-emptyDir.yaml
    10
    requests :
    I
    ! 02-hostpath.yaml
    11
    storage: AGi
    ! 03-ebs-static.yaml
    12
    ! 04-ebs-dynamic.ya... M
    13
    apiVersion: v1
    14
    ! ebs-sc.yaml
    kind: Pod
    15
    metadata:
    > k8-roboshop
    16
    name : app
    > roboshop-ansible-roles
    17
    labels :
    > roboshop-ansible-rol..
    18
    demo: ebs-dynamic
    > roboshop-docker
    19
    spec :
    > roboshop-infra-dev
    20
    containers:
    > roboshop-infra-prod
    21
    name : nginx
    22
    image: nginx
    > roboshop-shared-libr... .
    23
    volumeMounts :
    OUTLINE
    24
    - name: nginx-data
    25
    untPath:
    /usr/ share/nginx/html

[^47]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main d9f4542\] jenkins
    1 file changed, 43 insertions (+), 1 deletion(-)

[^48]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 04-ebs-dynamic. yaml
    persistentvolumeclaim/ebs-dynamic created
    pod/app created
    service/ebs-dynamic created

[^49]: 44 . 204 . 86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pv
    NAME
    CAPACITY
    ACCESS MODES
    RECLAIM POLICY
    STATUS
    CLAIM
    STORAGECLASS
    R
    SON
    AGE
    pvc-8b535ab2-a700-48bf-a86c-4b95e4cla405
    4Gi
    RWO
    Delete
    Bound
    default/ebs-dynamic
    ebs-sc
    5s

[^50]: 44 . 204 . 86.206 \| 172. 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    0
    23s

[^51]: 44 . 204. 86.206 \| 172 . 31 . 92. 165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources. git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pvc
    NAME
    STATUS
    VOLUME
    CAPACITY
    ACCESS MODES
    STORAGECLASS
    AGE
    ebs-dynamic
    Bound
    pvc-8b535ab2-a700-48bf-a86c-4b95e4cla405
    4Gi
    RWO
    ebs-sc
    28s

[^52]: Volumes (1/5) Info
    C
    Actions
    Create volume
    Q Search
    1 >
    Size
    IOPS
    Throughput Snapshot
    Created
    Availability Zone
    Volume state v Alarm status
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1c
    In-use
    No alarms
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    No alarms
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    No alarms
    4 GIB
    3000
    125
    2024/02/28 08:10 GMT+5:...
    us-east-1b
    In-use
    No alarms
    10 GiB
    100
    snap-Od6f961...
    2024/02/28 06:40 GMT +5:...
    us-east-1a
    In-use
    No alarms

[^53]: Volumes (1/5) Info
    C
    Actions
    Create volume
    Q Search
    <
    1 >
    1OPS
    Throughput Snapshot
    Created
    Availability Zone
    Volume state V Alarm status
    Attached r
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT+5:...
    us-east-1c
    In-use
    No alarms
    +
    i-0326608
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT+5:...
    us-east-1b
    In-use
    No alarms
    +
    i-02709b6
    3000
    125
    snap-0647d32...
    2024/02/28 06:59 GMT +5:...
    us-east-1b
    In-use
    No alarms
    +
    i-00334d3
    3000
    125
    2024/02/28 08:10 GMT+5:...
    us-east-1b
    In-use
    No alarms
    +
    i-00334d3
    100
    snap-Od6f961...
    2024/02/28 06:40 GMT +5:...
    us-east-1a
    In-use
    No alarms
    +
    i-02a55bc
    Volume ID: vol-0421e8c10a8108651
    O X
    Tags
    Manage tags
    Q Filter tags
    <
    1
    >
    Key
    Value
    ebs.csi.aws.com/cluster
    true
    kubernetes.io/created-for/pvc/name
    ebs-dynamic
    kubernetes.io/created-for/pv/name
    pvc-86535ab2-a700-48bf-a86c-4695e4c1a405
    CSIVolumeName
    pvc-86535ab2-a700-48bf-a86c-4695e4c1a405
    kubernetes.io/created-for/pvc/namespace
    default

[^54]: Reclaim policy
    PersistentVolumes that are dynamically created by a StorageClass will have the reclaim policy
    specified in the reclaimPolicy field of the class, which can be either Delete or Retain . If no
    reclaimPolicy is specified when a StorageClass object is created, it will default to Delete .
    PersistentVolumes that are created manually and managed via a StorageClass will have whatever
    reclaim policy they were assigned at creation.

[^55]: 44 . 204 . 86.206 \| 172 . 31. 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get sc
    NAME
    PROVISIONER
    RECLAIMPOLICY
    VOLUMEBINDINGMODE
    ALLOWVOLUMEEXPANSION
    AGE
    ebs-sc
    ebs . csi . aws . com
    Delete
    WaitForFirstConsumer
    false
    6s
    gp2 (default)
    kubernetes . io/aws-ebs
    Delete
    WaitForFirstConsumer
    false
    74m

[^56]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl delete -f 04-ebs-dynamic. yaml
    persistentvolumeclaim "ebs-dynamic" deleted
    pod "app" deleted
    service "ebs-dynamic" deleted

[^57]: EFS static
    1. create EFS filesystem
    2. edit the security group, so that it will allow port 2049 from worker nodes.
    3. we should have drivers installed

[^58]: Elastic File System
    X
    @Introducing Amazon EFS Archive
    Amazon Elastic File System (EFS) now offers a new Archive storage class, which is cost-optimized for long-lived data that is accessed only a few times per year or less. To use
    Archive, choose one of the available "Transition into Archive" options in the Lifecycle Management section when creating or updating your EFS file system. Learn more about the
    File systems
    Archive storage class. \[
    Access points
    Amazon EFS > File systems
    AWS Backup \[Z
    File systems (0)
    C
    View details
    Delete
    Create file system
    AWS DataSync \[Z
    AWS Transfer \[Z
    Q Filter by property values
    ( 1 >
    Documentation \[Z
    File
    Encrypte
    Total size V
    Size in
    Size in
    Provisioned
    Name
    system ID
    Standard
    Size in IA
    D
    d
    Archive
    Throughput
    (MiB/s)
    No resources
    Create file system

[^59]: Create file system
    X
    Create an EFS file system with recommended settings. Learn more
    Name - optional
    Name your file system.
    efs-static
    Name can include letters, numbers, and +-=._:/ symbols, up to 256 characters.
    Virtual Private Cloud (VPC)
    Choose the VPC where you want EC2 instances to connect to your file system.
    vpc-Od691bd66cd34d941
    eksctl-roboshop-cluster/VPC
    vpc-Od01c720a468ee47e
    eksctl-roboshop-cluster/VPC
    vpc-03dae0a05234cdf34
    default
    vpc-Od691bd66cd34d941
    eksctl-roboshop-cluster/VPC
    V

[^60]: Elastic File System
    X
    File system (fs-016a860b 1f7383cac) is creating.
    Notifications 0 0 01 1
    V
    File systems
    Amazon EFS > File systems
    Access points
    File systems (1)
    C
    View details
    Delete
    Create file system
    AWS Backup \[
    Q Filter by property values
    < 1 >
    AWS DataSync \[
    AWS Transfer \[Z
    Size in
    Provisioned
    File
    Name
    Encrypte
    Size in
    Total size V
    4
    system ID
    d
    Standard
    Size in IA
    Archive
    Throughput
    Documentation \[
    (MiB/s)
    fs-
    O
    efs-static
    016a860b1f
    Encrypte
    O Bytes
    0 Bytes
    0 Bytes
    O Bytes
    d
    7383cac

[^61]: Quotas for Amazon EFS file systems
    The following quotas are specific to Amazon EFS file systems.
    Resource
    Quota
    File name length, in bytes
    255
    Symbolic link (symlink) length, in bytes
    4,080
    Number of hard links to a file
    177
    Size of a single file
    52,673,613,135,872 bytes (47.9 TiB)
    Number of levels for directory depth
    1,000
    Number of locks on a single file across all instances and users
    512
    Character limit for each file system policy
    20,000
    "Number of file operations per second for General Purpose mode
    250,000

[^62]: Elastic File System
    X
    Lifecycle management
    File system state
    Transition into Infrequent Access (IA):30 day(s) since last access
    Available
    Transition into Archive: 90 day(s) since last access
    File systems
    DNS name
    Transition into Standard: None
    Access points
    fs-016a860b1f7383cac. efs. us-east-1. amazonaws . com
    Availability zone
    Regional
    Replication overwrite protection
    AWS Backup \[
    Enabled
    AWS DataSync \[Z
    AWS Transfer \[Z
    Metered size
    Monitoring
    Tags
    File system policy
    Access points
    Network
    Replication
    Documentation
    Network
    C
    Manage
    Availability zone
    Mount target ID
    Subnet ID
    Mount target state
    IP address
    Network interface ID
    Security groups
    fsmt-
    subnet-
    Available
    192.168.62.1
    eni-
    sg
    us-east-1b
    0397c7bd5d2950a
    012253c044
    De8f825b4dce909
    72
    883148b
    06fb95422c8c3d957
    3b
    17 (default)
    fsmt-
    subnet-
    sg
    Oae08f55cb8e24ee
    0982b1d872
    Available
    192.168.5.10
    us-east-1c
    eni-Of9cbbaf8d2470fd1
    De8f825b4dce909
    4
    9fa 1coa
    2
    11 (default)

[^63]: Security Groups (1/1) Info
    C
    Actions
    Export security groups to CSV
    Create security group
    Q Find resources by attribute or tag
    sg-0e8f825b4dce90911
    X
    Clear filters
    < 1 >
    V
    Name
    Security group ID
    Security group name
    sg-0e8f825b4dce90911
    default
    Inbound rules (1)
    C
    Manage tags
    Edit inbound rules
    Q Search
    < 1 >
    O
    Name
    Security group rule ID
    IP version
    Type
    Protocol
    Port rang
    sgr-Oadoeac 149eb5dddb
    All traffic
    All
    All

[^64]: VPC > Security Groups > sg-0e8f825b4dce90911 - default > Edit inbound rules
    Edit inbound rules info
    Inbound rules control the incoming traffic that's allowed to reach the instance.
    Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info Port range
    Source Info
    Description - optional Info
    Info
    sgr-Oadoeac 149eb5dddb
    All traffic
    All
    Custom
    Q
    Delete
    sg-0e8f825b4dce90911 X
    NFS
    TCP
    2049
    Custom
    Q sg-097e0c932414e847 X
    Delete
    sg-097e0c932414e8470 X
    Add rule
    Cancel
    Preview changes
    Save rules

[^65]: -
    C
    github.com/kubernetes-sigs/aws-efs-csi-driver
    DO README
    Code of conduct . Apache-2.0 license . Security
    \[ Manifest (private registry) \]
    If you want to download the image with a manifest, we recommend first trying these steps to pull secured images
    from the private Amazon ECR registry.
    To install the driver using images stored in the private Amazon ECR registry
    1. Download the manifest. Replace release-X.X with your desired branch. We recommend using the latest
    released version. For a list of active branches, see Branches.
    NS-efs-csi-driver/deploy/kubernetes/overlays/stable/ecr/?ref=release-1.X" > private-ecr-driver.yaml

[^66]: E
    kubernetes-sigs / aws-efs-csi-driver
    Q Type to search
    <> Code
    Issues 67 13 Pull requests 45
    Actions Projects @ Security \~ Insights
    Branches
    Overview
    Active
    Stale All
    Q Search branches.
    Branch
    Updated
    Check status
    Behind Ahead
    Pull reque
    gh-pages
    3 weeks ago
    V 3/3
    888 58
    release-1.7 0 0
    3 weeks ago
    V 1/1
    310 259
    I

[^67]: 44 . 204 . 86. 206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ cd
    44 . 204 . 86. 206 \| 172. 31. 92. 165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl kustomize \\
    "github . com/kubernetes-sigs/aws-efs-csi-driver/deploy/kubernetes/overlays/stable/ecr/?ref=release-1. 7" > private-ecr-driver. yaml
    # Warning: 'bases' is deprecated. Please use 'resources' instead. Run 'kustomize edit fix' to update your Kustomization automatically.
    44 . 204 . 86.206 \| 172. 31 . 92.165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ 1s
    k8-eksctl k8-resources private-ecr-driver . yaml

[^68]: 44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ 1s
    k8-eksctl k8-resources private-ecr-driver. yaml
    44 . 204. 86.206 \| 172. 31. 92.165 \| t2. micro \| null
    \[ centos@ip-172-31-92-165 \~ \]$ kubectl apply -f private-ecr-driver . yaml
    serviceaccount/efs-csi-controller-sa created
    serviceaccount/efs-csi-node-sa created
    clusterrole. rbac . authorization. k8s . io/efs-csi-external-provisioner-role created
    clusterrole . rbac . authorization. k8s . io/efs-csi-external-provisioner-role-describe-secrets created
    clusterrole . rbac . authorization . k8s . io/efs-csi-node-role created
    rolebinding . rbac . authorization . k8s . io/efs-csi-provisioner-binding-describe-secrets created
    clusterrolebinding . rbac . authorization. k8s . io/efs-csi-node-binding created
    clusterrolebinding . rbac . authorization. k8s . io/efs-csi-provisioner-binding created
    deployment . apps/efs-csi-controller created
    daemonset . apps/efs-csi-node created
    csidriver . storage . k8s . io/efs . csi . aws . com configured

[^69]: give ec2 roles efs full access
    4. create pv
    5. create pvc
    6. use pvc in the pod

[^70]: Elastic File System
    X
    Introducing Amazon EFS Archive
    X
    Amazon Elastic File System (EFS) now offers a new Archive storage class, which is cost-optimized for long-lived data that is accessed only a few times per year or less. To use
    Archive, choose one of the available "Transition into Archive" options in the Lifecycle Management section when creating or updating your EFS file system. Learn more about
    File systems
    the Archive storage class. \[
    Access points
    Amazon EFS > File systems > fs-016a860b1f7383cac
    AWS Backup \[Z
    efs-static (fs-016a860b1f7383cac)
    Delete
    Attach
    AWS DataSync \[Z
    AWS Transfer \[
    General
    Edit
    Documentation
    Performance mode
    Automatic backups
    General Purpose
    Enabled
    Throughput mode
    Encrypted
    Elastic
    54a35926-6e16-49da-b06d-eac2a96898fd (aws/elasticfilesystem)
    Lifecycle management
    File system state

[^71]: V REPOS
    k8-resources > storage > ! 05-efs-static.yaml > {} spec > {} csi > @ volumeHandle
    / uockermes
    1
    apiVersion: v1
    > k8-eksctl
    2
    kind: PersistentVolume
    k8-resources
    3
    metadata:
    > 01-namespace
    14
    name: efs-static
    > 02-pods
    5
    spec:
    > service
    16
    capacity:
    17
    storage: 5Gi
    > sets
    8
    volumeMode: Filesystem
    V
    storage
    9
    accessModes :
    ! 01-emptyDir.yaml
    10
    ReadWriteOnce -
    ! 02-hostpath.yaml
    11
    storageClassName : " "
    ! 03-ebs-static.yaml
    12
    persistentVolumeReclaimPolicy: Retain
    ! 04-ebs-dynamic.yaml
    13
    csi :
    ! 05-efs-static.yaml - U
    14
    driver: efs. csi.aws . com -
    15
    volumeHandle: fs-016a86061f7383cac
    ! ebs-sc.yaml
    k8-roboshop

[^72]: V REPOS
    k8-resources > storage > ! 05-efs-static.yaml > {} spec > volumeName
    aockermes
    > k8-eksctl
    7
    storage: 5Gi
    8
    k8-resources
    volumeMode: Filesystem
    9
    accessModes :
    > 01-namespace
    10
    - ReadWriteOnce
    > 02-pods
    11
    storageClassName : ""
    > service
    12
    persistentVolumeReclaimPolicy: Retain
    > sets
    13
    csi :
    storage
    14
    driver: efs. csi. aws . com
    15
    ! 01-emptyDir.yaml
    volumeHandle: fs-016a860b1f7383cac
    16
    ! 02-hostpath.yaml
    17
    apiVersion: v1
    ! 03-ebs-static.yaml
    18
    kind: PersistentVolumeClaim
    ! 04-ebs-dynamic.yaml
    19
    metadata:
    ! 05-efs-static.yaml
    U
    20
    name: efs-static
    ! ebs-sc.yaml
    21
    spec :
    k8-roboshop
    22
    accessModes :
    23
    ReadWriteOnce
    > cart
    24
    storageClassName : " "
    > catalogue
    25
    volumeName: efs-static
    > debug
    26
    resources :
    > mongodb
    27
    requests :
    > mysql
    28
    storage: 5Gi

[^73]: aockermes
    apiVersion: v1
    > k8-eksctl
    31
    kind: Pod
    k8-resources
    32
    metadata:
    > 01-namespace
    33
    name : app
    > 02-pods
    34
    labels :
    > service
    35
    demo: efs-static
    36
    ) sets
    spec :
    37
    containers :
    storage
    38
    name: nginx
    ! 01-emptyDir.yaml
    39
    image: nginx
    ! 02-hostpath.yaml
    40
    volumeMounts :
    ! 03-ebs-static.yaml
    41
    name: nginx-data
    ! 04-ebs-dynamic.yaml
    42
    mountPath: /usr/share/nginx/html
    ! 05-efs-static.yaml
    U
    43
    nodeSelector :
    44
    zone: 1b
    ! ebs-sc.yaml
    45
    volumes :
    k8-roboshop
    46
    name : nginx-data
    > cart
    47
    persistentVolumeClaim:
    > catalogue
    48
    claimName: ebs-static
    > debug
    49
    > mongodb
    50
    apiVersion: v1
    51
    kind: Service
    > mysql
    52
    metadata :
    OUTLINE
    53
    name: ebs-static

[^74]: 44 . 204. 86.206 \| 172. 31 . 92.165 \| t2. micro \| null
    \[ centos(ip-172-31-92-165 \~ \]$ cd k8-resources/storage/
    44 . 204 . 86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 4 (delta 2) , reused 4 (delta 2) , pack-reused 0
    Unpacking objects: 100% (4/4) , 733 bytes \| 733.00 KiB/s, done.
    From https: / /github. com/daws-76s/k8-resources

[^75]: 44 . 204 . 86.206 \| 172. 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 05-efs-static. yaml
    persistentvolume/efs-static created
    persistentvolumeclaim/efs-static created
    pod/app created
    service/efs-static created

[^76]: 44 . 204 . 86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    0/1
    Pending
    0
    5s
    44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    0/1
    ContainerCreating
    0
    7s

[^77]: 44 . 204 . 86. 206 \| 172. 31 . 92.165 \| t2. micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    0
    15s

[^78]: 44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl exec -it app -- bash
    root@app: /# echo "<h1>Hello from EFS static</h1>" > efs.html
    root@app : /#

[^79]: </html>
    root@app: /# echo "<h1>Hello from EFS static</h1>"> /usr/share\~nginx/html/efs.html
    root@app : /#

[^80]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl exec -it app -- bash
    root@app: /# echo "<h1>Hello from EFS static</h1>">efs. html
    root@app: /# curl localhost/efs.html
    <html>
    <head><title>404 Not Found</title></head>
    <body>
    <center><h1>404 Not Found</h1></center>
    <hr><center>nginx/1 . 25.4</center>
    </body>
    </html>

[^81]: 44 . 204 . 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    GE
    efs-static
    LoadBalancer
    10 . 100 . 174 .211
    abd851863f5a440a29225a0f175da93e-1426859459. us-east-1. elb. amazonaws . com
    80 : 31251/TCP
    9s
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    0 7m

[^82]: ->
    C
    Not secure abd851863f53440a29225a0f175da93-1426859459.us-east-1.elb.amazonaws.com/efs.html
    Hello from EFS static

[^83]: 44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl delete pod app
    pod "app" deleted

[^84]: 44 . 204 . 86. 206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 05-efs-static. yaml
    persistentvolume/efs-static configured
    persistentvolumeclaim/efs-static unchanged
    pod/app created
    service/efs-static unchanged

[^85]: F
    C
    Not secure abd85186315a440a2922530f175da93e-1426859459.us-east-1.elb.amazonaws.com/efs.html
    Hello from EFS static

[^86]: Create file system
    X
    Create an EFS file system with recommended settings. Learn more \[
    Name - optional
    Name your file system.
    efs-dynamic
    Name can include letters, numbers, and +-=._:/ symbols, up to 256 characters.
    Virtual Private Cloud (VPC)
    Choose the VPC where you want EC2 instances to connect to your file system.
    vpc-Od01c720a468ee47e
    eksctl-roboshop-cluster/VPC
    Cancel
    Customize
    Create

[^87]: Elastic File System
    X
    File system (fs-0715ef3ca61bfe431) is available.
    Notifications 0 0 1 01 0
    V
    File systems
    Access points
    Amazon EFS > File systems
    File systems (2)
    C
    View details
    Delete
    Create file system
    AWS Backup \[
    AWS DataSync \[
    Q Filter by property values
    ( 1 >
    AWS Transfer \[Z
    Provisioned
    File
    D
    4
    Total size V
    Size in
    Name
    A
    Encrypte
    Size in
    V
    V
    V
    Documentation
    system ID
    d
    Standard
    Size in IA
    Archive
    Throughput
    (MiB/s)
    fs-
    O
    efs-dynamic
    Encrypte
    0715ef3ca6
    d
    6.00 KiB
    6.00 KiB
    O Bytes
    O Bytes
    1bfe431

[^88]: Amazon EFS > File systems > fs-0715ef3ca61bfe431
    efs-dynamic (fs-0715ef3ca61bfe431)
    General
    Performance mode
    Automatic backups
    General Purpose
    Enabling

[^89]: REPOS
    k8-resources > storage > ! efs-sc.yaml > {} parameters
    k8-resources
    kind: StorageClass
    UC-pous
    2
    apiVersion: storage . k8s . io/v1
    > service
    3
    metadata :
    > sets
    4
    name: efs-sc-roboshop
    storage
    5
    provisioner: efs. csi. aws . com
    ! 01-emptyDir.yaml
    16
    parameters :
    17
    ! 02-hostpath.yaml
    provisioningMode: efs-ap
    8
    fileSystemId: fs-0715ef3ca61bfe431
    ! 03-ebs-static.yaml
    9
    directoryPerms : "700"
    ! 04-ebs-dynamic.yaml
    10
    gidRangeStart: "1000"
    # optional
    ! 05-efs-static.yaml
    11
    gidRangeEnd: "2000"
    #
    optional
    ! 06-efs-dynamic.yaml U
    12
    basePath: "/roboshop"
    #
    optional
    ! ebs-sc.yaml
    ! efs-sc.yaml
    U
    k8-roboshop
    > cart

[^90]: 44 . 204 . 86.206 \| 172 . 31.92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources. git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 5 (delta 2) , reused 5 (delta 2) , pack-reused 0
    Unpacking objects: 100% (5/5), 560 bytes \| 560.00 KiB/s, done.
    From https: //github. com/daws-76s/k8-resources
    08a6bbe. . f5887ed main
    -> origin/main
    Jpdating 08a6bbe. . 15887ed

[^91]: 44 . 204 . 86.206 \| 172. 31 . 92. 165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f efs-sc. yaml
    storageclass . storage . k8s . io/efs-sc-roboshop created
    44 . 204 . 86.206 \| 172. 31. 92. 165 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get sc
    NAME
    PROVISIONER
    RECLAIMPOLICY
    VOLUMEBINDINGMODE
    ALLOWVOLUMEEXPANSION
    AGE
    ebs-sc
    ebs . csi . aws . com
    Delete
    WaitForFirstConsumer
    false
    39m
    efs-sc-roboshop
    efs . csi . aws . com
    Delete
    Immediate
    false
    4s
    gp2 (default)
    kubernetes . io/aws-ebs
    Delete
    WaitForFirstConsumer
    false
    113m

[^92]: EXPLORER
    . . .
    :h.yaml
    ! 03-ebs-static.yaml
    ! 04-ebs-dynamic.yaml
    ! O
    REPOS
    k8-resources > storage > ! 06-efs-dynamic.yaml > {} spec > {} selector
    k8-resources
    27
    metadata:
    > 01-namespace
    28
    labels :
    > 02-pods
    29
    app: nginx
    30
    demo: efs-dynamic
    > service
    31
    spec :
    sets
    32
    containers :
    ! 01-replica-set.yaml
    33
    name: nginx
    ! 02-deployment-set.yaml
    34
    image: nginx
    storage
    35
    ports :
    01-emptyDir.yaml
    36
    - containerPort : 80
    02-hostpath.yaml
    37
    38
    apiVersion: v1
    03-ebs-static.yaml
    39
    kind: Service
    04-ebs-dynamic.yaml
    40
    metadata :
    ! 05-efs-static.yaml
    41
    name: efs-dynamic
    ! 06-efs-dynamic.ya... M
    42
    spec:
    ! ebs-sc.yaml
    43
    type: LoadBalancer
    ! efs-sc.yaml
    44
    selector :
    45
    > k8-roboshop
    demo: efs-dynamic
    46
    ports :
    > roboshop-ansible-roles
    47
    protocol: TCP
    > roboshop-ansible-rol.. .
    48
    port: 80 #service-port
    > roboshop-docker
    49
    targetPort: 80 #container-port
    OUTLINE

[^93]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 1cfalee\] jenkins
    1 file changed, 49 insertions (+)

[^94]: 44 . 204. 86.206 \| 172 . 31 . 92.165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 06-efs-dynamic. yaml
    persistentvolumeclaim/efs-dynamic created
    deployment . apps/efs-dynamic created
    service/efs-dynamic created

[^95]: 44 . 204 . 86. 206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    7m26s
    efs-dynamic-718969969f-5qs99
    1/1
    Running
    20s
    OOOO
    efs-dynamic-718969969f-sctfk
    1/1
    Running
    19s
    efs-dynamic-718969969f-xn87j
    1/1
    Running
    19s

[^96]: 44 . 204 . 86.206 \| 172. 31. 92.165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ watch kubectl get pods

[^97]: Every 2. 0s: kubectl get pods
    ip-172-31-92-165. ec2 . internal: Wed Feb
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    0
    9m5s
    efs-dynamic-75c9965b56-2jxp4
    0/1
    Pending
    17s
    0/1
    Pending
    OOO
    efs-dynamic-75c9965b56-87b9t
    17s
    efs-dynamic-75c9965b56-ts8f2
    0/1
    Pending
    17s

[^98]: 44 . 204 . 86.206 \| 172 . 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ watch kubectl get pods
    44 . 204 . 86.206 \| 172. 31. 92.165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pv
    NAME
    CAPACITY
    ACCESS MODES
    RECLAIM POLICY
    STATUS
    CLAIM
    STORAGECLASS
    REASON
    AGE
    efs-static
    5Gi
    RWO
    Retain
    Bound
    default/efs-static
    12m
    44 . 204 . 86.206 \| 172. 31. 92.165 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    app
    1/1
    Running
    0
    9m 36s
    efs-dynamic-7509965656-2jkp4
    0/1
    Pending
    48s
    efs-dynamic-75c9965b56-87b9t
    0/1
    Pending
    OOO
    48s
    efs-dynamic-75c9965b56-ts8f2
    0/1
    Pending
    48s
    44 . 204 . 86.206 \| 172 . 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl describe pod efs-dynamic-75c9965656-2jxp4

[^99]: / var/run/secrets/kubernetes . io/serviceaccount from kube-api-access-jbqqj (ro)
    Conditions :
    Type
    Status
    PodScheduled
    False
    Volumes :
    nginx-data:
    Type :
    PersistentVolumeClaim (a reference to a PersistentVolumeClaim in the same namespace)
    ClaimName :
    efs-dynamic
    ReadOnly :
    false
    kube-api-access-jbqqj :
    Type :
    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds :
    3607
    ConfigMapName :
    kube-root-ca . crt
    ConfigMapOptional :
    <nil>
    DownwardAPI :
    true
    Qos Class:
    BestEffort
    Node-Selectors :
    <none>
    Tolerations :
    node . kubernetes . io/not-ready : NoExecute op=Exists for 300s
    node . kubernetes . io/unreachable : NoExecute op=Exists for 300s
    Events:
    Type
    Reason
    Age
    From
    Message
    Warning
    FailedScheduling 61s
    default-scheduler 0/3 nodes are available: pod has unbound immediate PersistentVolumeClaims. preem
    tion: 0/3 nodes are available: 3 Preemption is not helpful for scheduling.

[^100]: 44 . 204. 86.206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl describe pvc efs-dynamic
    Name :
    efs-dynamic
    Namespace :
    default
    StorageClass :
    efs-sc-roboshop
    Status :
    Pending
    Volume :
    Labels :
    <none>
    Annotations :
    volume . beta . kubernetes . io/storage-provisioner: efs . csi . aws . com
    volume . kubernetes . io/storage-provisioner: efs . csi . aws . com
    Finalizers :
    \[kubernetes . io/pvc-protection\]
    Capacity :
    Access Modes:
    VolumeMode :
    Filesystem
    Used By:
    efs-dynamic
    Events :
    Type
    Reason
    Age
    From
    Message
    Normal
    Provisioning
    24s (x8 over 2m32s)
    efs . csi . aws. com efs-csi-controller-589ffc6b5b-g9j47_1f50a102-2ae2-499c-b9e9-e245
    89b4fc29
    External provisioner is provisioning volume for claim "default/efs-dynamic"
    Warning ProvisioningFailed
    24s (x8 over 2m32s)
    efs . csi . aws. com efs-csi-controller-589ffc6b5b-g9j47_1f50a102-2ae2-499c-b9e9-e245
    89b4fc29
    failed to provision volume with StorageClass "efs-sc-roboshop": rpc error: code = Unauthenticated desc = Access Denied. Pleas
    e ensure you have the right AWS permissions: Access denied
    T
    Normal
    ExternalProvisioning 13s (x11 over 2m32s) persistentvolume-controller
    waiting for a volume to be created, either by external provisioner "efs. csi. aws. com" or manually created by system administra
    tor

[^101]: Current permissions policies (5)
    Other permissions policies (1/908)
    C
    Filter by Type
    Q elasticf
    X
    All types
    7 matches
    <
    -
    Policy name
    A Type
    Description
    O
    AmazonDocDBElasticFullAccess
    AWS managed
    Provides full access to Amazon Docum...
    +
    AmazonElasticFileSystemClientFullAccess
    AWS managed
    Provides root client access to an Amaz...
    O
    AmazonElasticFileSystemClientReadOnlyAccess
    AWS managed
    Provides read only client access to an ...
    AmazonElasticFileSystemClientReadWriteAccess
    AWS managed
    Provides read and write client access t...
    AmazonElasticFileSystemFullAccess
    AWS managed
    Provides full access to Amazon EFS via...
    O
    + AmazonElasticFileSystemReadOnlyAccess
    AWS managed
    Provides read only access to Amazon E...
    + AmazonElasticFileSystemsUtils
    AWS managed
    Allows customers to use AWS Systems ...
    Cancel
    Add permissions

[^102]: 44 . 204 . 86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl delete -f 06-efs-dynamic. yaml
    persistentvolumeclaim "efs-dynamic" deleted
    pod "efs-dynamic" deleted
    service "efs-dynamic" deleted
    44 . 204. 86.206 \| 172. 31. 92.165 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl apply -f 06-efs-dynamic. yaml
    persistentvolumeclaim/efs-dynamic created
    pod/efs-dynamic created
    service/efs-dynamic created
    44 . 204. 86. 206 \| 172 . 31 . 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pvc
    NAME
    STATUS
    VOLUME
    CAPACITY
    ACCESS MODES
    STORAGECLASS
    AGE
    efs-dynamic
    Bound
    pvc-c2998e9d-6c68-49bd-9b74-2055e3b5da 7a
    5Gi
    RWX
    efs-sc-roboshop
    4s
    44 . 204.86.206 \| 172. 31. 92.165 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-92-165 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    efs-dynamic
    1/1
    Running
    0
    9s

[^103]: Elastic File System
    X
    General Purpose
    Enabled
    Throughput mode
    Encrypted
    File systems
    Elastic
    54a35926-6e16-49da-b06d-eac2a96898fd (aws/elasticfilesystem)
    Access points
    Lifecycle management
    File system state
    Transition into Infrequent Access (IA): 30 day(s) since last access
    Available
    Transition into Archive: 90 day(s) since last access
    AWS Backup \[
    DNS name
    Transition into Standard: None
    AWS DataSync \[
    Availability zone
    fs-0715ef3ca61bfe431. efs. us-east-1. amazonaws . com
    AWS Transfer \[Z
    Regional
    Replication overwrite protection
    Enabled
    Documentation
    Metered size
    Monitoring
    Tags
    File system policy
    Access points
    Network
    Replication
    Access points (1)
    G
    View details
    Delete
    Create access point
    Q Search access points by name or ID
    < 1 >
    Name
    Access point ID
    Path
    POSIX user
    Creation info
    State
    O
    fsap-Ofc048d66fd58683d
    /roboshop/pvc-c29...
    1000 : 1000
    1000 : 1000 (700)
    Available

