---
title: 63Day_Kubernetes
uuid: 602cceb4-48a2-11ef-bf57-26e37c279344
version: 1032
created: '2024-07-23T08:49:30+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#F8914D;">**K8 Cluster creation using terraform**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![88d372c0-b6a9-4552-b6c6-3fb5bb051292.png|667](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/88d372c0-b6a9-4552-b6c6-3fb5bb051292.png) [^1]

\

terraform code to create k8 cluster.

![f7b63b17-d6bc-4e0f-bd63-7d440012d7aa.png|1017](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/f7b63b17-d6bc-4e0f-bd63-7d440012d7aa.png) [^2]

\

Before k8 upgrade **Blue** is used and after upgrade **Green** is used.

 ![650dada2-ba5a-45c0-a5d1-3a89c6839a02.png|1009.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/650dada2-ba5a-45c0-a5d1-3a89c6839a02.png) [^3]

\

Using the k8 cluster created.

![5216a589-26a6-40c9-aa64-6cf30b824c55.png|741](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/5216a589-26a6-40c9-aa64-6cf30b824c55.png) [^4]

\

Now I want to update kubeconfig

```
aws eks update-kubeconfig --region us-east-1 --name roboshop-tf
```

![e7899133-95fb-4626-9518-b01afb0de625.png|1181.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/e7899133-95fb-4626-9518-b01afb0de625.png) [^5]

\

Now nodes are running...

```
Kubectl get nodes
```

![edc69339-e9b1-4dbd-a8cd-edc84eb07edd.png|1012](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/edc69339-e9b1-4dbd-a8cd-edc84eb07edd.png) [^6]

\

Nodes are running and marked as blue before upgrading.

![bdb22d4a-7a24-4560-b12d-2a7238a0e963.png|1138.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/bdb22d4a-7a24-4560-b12d-2a7238a0e963.png) [^7]

\

\

# <mark style="background-color:#F8914D;">**Taints & tolerations**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

<mark>**Taint**</mark> = paint   --> it's nothing but polluting. Ex. paint an 100rs note, if done we can't use it further that node.

\

If i taint a node, then by default scheduler can't schedule POD on that node. 

\

Few projects they add their own nodes to Eks cluster (for security reasons), they won't allow PODS of other projects. Then they taint the nodes.

\

![c0379b6a-58cf-4a92-b731-905ef9ac0bae.png|656](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/c0379b6a-58cf-4a92-b731-905ef9ac0bae.png) [^8]

\

<mark>**Tolerations**</mark> is an excuse, PODS specific to that project can have tolerations(excuses).  <mark>**(PODS will create node tainted node if we use toleration)**</mark>

\

**Taint a node**

```
kubectl get nodes
kubectl taint nodes <nodename> project=<projectname>:NoSchedule
```

![fd9fafce-486f-4534-9c1d-5bd96ea23227.png|1081.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/fd9fafce-486f-4534-9c1d-5bd96ea23227.png) [^9]

\

creating a POD to check in which node POD is creating... Obesely POD will create in Node2 since node1 is tained. 

![2f149cb7-d909-428a-9e2d-3e6b4e5208f9.png|1078](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/2f149cb7-d909-428a-9e2d-3e6b4e5208f9.png) [^10]

\

git push & pull

![7d3c57ba-8a05-4eb8-b95b-c8691ad547d9.png|1076.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/7d3c57ba-8a05-4eb8-b95b-c8691ad547d9.png) [^11]

\

![fedd6175-7cc9-4455-a456-987884c22592.png|1078.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/fedd6175-7cc9-4455-a456-987884c22592.png) [^12]

\

POD creation

```
cd selectors/
kubectl apply -f 01-taint-toleration.yaml
```

![0eabdb83-a9f5-4fb0-bfd4-52009ff3d422.png|1081.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/0eabdb83-a9f5-4fb0-bfd4-52009ff3d422.png) [^13]

\

POD created in Node2 but not in Node1

```
Kubectl get pods -o wide
```

![317d71e4-a8e0-46ac-8dfb-caad50a8f82e.png|1176.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/317d71e4-a8e0-46ac-8dfb-caad50a8f82e.png) [^14]

\

deleting a POD

```
kubectl delete -f 01-taint-toleration.yaml
```

![879ae541-9e57-4322-a674-91032b7ee10b.png|1178.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/879ae541-9e57-4322-a674-91032b7ee10b.png) [^15]

\

\

<mark>**Now checking the tolerations (PODS will create node tainted node if we use toleration)**</mark>

![54f27208-39b6-4e6b-a435-b365ecfd53fc.png|798](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/54f27208-39b6-4e6b-a435-b365ecfd53fc.png) [^16]

![a8d6a944-120b-4214-bbe9-3189691a0710.png|1018.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/a8d6a944-120b-4214-bbe9-3189691a0710.png) [^17]

\

git push & pull

![609e64ac-6d6b-485e-948f-0e56b03172a3.png|1016](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/609e64ac-6d6b-485e-948f-0e56b03172a3.png) [^18]

\

![609e64ac-6d6b-485e-948f-0e56b03172a3.png|1016](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/609e64ac-6d6b-485e-948f-0e56b03172a3.png) [^19]

\

POD created in node1 since we used toleration.

```
cd selectors/
kubectl apply -f 01-taint-toleration.yaml
kubectl get pods
kubectl get pods -o wide
```

![210db5de-b809-4762-8344-ffdd598a023f.png|1058.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/210db5de-b809-4762-8344-ffdd598a023f.png) [^20]

\

untainted a node

```
kubectl taint nodes <nodename> project=<projectname>:NoSchedule-
```

![f58223af-81e3-44c4-863c-cf14660e715f.png|1143.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/f58223af-81e3-44c4-863c-cf14660e715f.png) [^21]

\

deleting a taint pod

```
kubectl delete -f 01-taint-toleration.yaml
```

![38419f3d-0ec8-48ea-83e6-6c78249939c0.png|1128.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/38419f3d-0ec8-48ea-83e6-6c78249939c0.png) [^22]

\

# <mark style="background-color:#F8914D;">**Affinity & Anti-Affinity**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![63a84892-40c1-4091-bc22-345fb856345c.png|677](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/63a84892-40c1-4091-bc22-345fb856345c.png) [^23]

\

![2ab0d18d-8217-477d-8b1d-131388930336.png|711](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/2ab0d18d-8217-477d-8b1d-131388930336.png) [^24]

\

![9caa8a29-4557-49ea-a533-3b3df2faeab4.png|944.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/9caa8a29-4557-49ea-a533-3b3df2faeab4.png) [^25]

\

\

## <mark>**Affinity (LOVE)**</mark>

**Firstly, I need to label the nodes...**

```
kubectl get nodes
kubectl nodes <node ip> project=roboshop
```

![bd61e112-5732-48b2-a8a6-a0034b2ba98f.png|1043.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/bd61e112-5732-48b2-a8a6-a0034b2ba98f.png) [^26]

\

**Affinity** means **LOVE...**

\

![6e0cece2-3fe5-4dbe-b314-ddbd66499ead.png|1032](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/6e0cece2-3fe5-4dbe-b314-ddbd66499ead.png) [^27]

\

git push & pull

![36a56f7b-20e2-4513-8eec-a062a8ad15c2.png|946](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/36a56f7b-20e2-4513-8eec-a062a8ad15c2.png) [^28]

\

it will be in pending state only, why because scheduler is not able to find the matching node as per our requirements.

```
kubectl apply -f 02-node-affinity.yaml
kubectl get pods
```

![8c0979c8-fca1-4f0b-acec-2ba5a016292b.png|1000.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/8c0979c8-fca1-4f0b-acec-2ba5a016292b.png) [^29]

\

**describe** cmd in k9s

![4f44235b-d178-436b-9b8a-bcbb6a3d6127.png|998.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/4f44235b-d178-436b-9b8a-bcbb6a3d6127.png) [^30]

\

deleting the node

```
kubectl delete -f 02-node-affinity.yaml
kubectl get pods
```

![5a3c9681-d234-4f4b-96e9-e867b0bc00e7.png|1099.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/5a3c9681-d234-4f4b-96e9-e867b0bc00e7.png) [^31]

\

now i am giving correct value as **roboshop**.

![b6a95b03-e501-47bc-9b27-8f128264e205.png|993](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/b6a95b03-e501-47bc-9b27-8f128264e205.png) [^32]

\

git push & pull 

![36a56f7b-20e2-4513-8eec-a062a8ad15c2.png|795](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/36a56f7b-20e2-4513-8eec-a062a8ad15c2.png) [^33]

\

```
kubectl apply -f 02-node-affinity.yaml
kubectl get pods
```

![2782fb1e-3210-4742-ae23-c0b8c4c0d316.png|1119.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/2782fb1e-3210-4742-ae23-c0b8c4c0d316.png) [^34]

\

Now POD is running state

![678049a2-7428-4876-a9c1-801fec5571ac.png|1058.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/678049a2-7428-4876-a9c1-801fec5571ac.png) [^35]

\

\

\

## <mark>**Anti-Affinity (hate)**</mark>

**Now i am labeling second node as amazon**

```
kubectl label nodes <node IP> project=amazon
```

![cd268dae-b007-4e98-a1e0-01fd42791007.png|914.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/cd268dae-b007-4e98-a1e0-01fd42791007.png) [^36]

\

for anti-affinity we use operator as **NotIn**

![551adca5-af6f-4573-bf6d-c3111a550aaf.png|1005](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/551adca5-af6f-4573-bf6d-c3111a550aaf.png) [^37]

\

git push & pull

![130aaa87-5e0c-43a5-805f-4f65facb9b58.png|768](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/130aaa87-5e0c-43a5-805f-4f65facb9b58.png) [^38]

\

```
kubectl apply -f 03-node-affinity.yaml
kubectl get pods
```

![bb8cfadc-114c-44dc-a668-9b9f321e8d3f.png|1113.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/bb8cfadc-114c-44dc-a668-9b9f321e8d3f.png) [^39]

\

Now POD create in second node where label is Amazon. **Anti-Affinity is exactly opposite.**

![4e6d9225-9c92-454a-b73c-06c4158c59fe.png|1206.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/4e6d9225-9c92-454a-b73c-06c4158c59fe.png) [^40]

\

## <mark>**Weight in Affinity**</mark>

In node-affinity, weights can be assigned to prioritize which nodes are preferred during pod scheduling in Kubernetes.

![88fcd001-7101-4ece-856f-d2d79e79c912.png|413](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/88fcd001-7101-4ece-856f-d2d79e79c912.png) [^41]

\

as the weight 50 is more than weight 1, then it should prefer 50 and creates in **roboshop** label

![62eef445-8d21-4113-8764-86a799e3b7b4.png|1104.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/62eef445-8d21-4113-8764-86a799e3b7b4.png) [^42]

\

git push & pull.

![9ab9c789-d334-4e2a-959f-896fd415e9dc.png|1106](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/9ab9c789-d334-4e2a-959f-896fd415e9dc.png) [^43]

\

```
kubectl apply -f 04-affinity-weight.yaml
```

![f7276412-6460-405e-bc51-1f7ac492b48f.png|1108.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/f7276412-6460-405e-bc51-1f7ac492b48f.png) [^44]

\

its running in **roboshop** label where weight is 50 high.

![e35458ae-6ec7-4586-b229-fe8aa553f7bb.png|1211.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/e35458ae-6ec7-4586-b229-fe8aa553f7bb.png) [^45]

\

deleting pods

```
kubectl delete -f 04-affinity-weight.yaml
kubectl delete -f 03-node-anti-affinity.yaml
kubectl delete -f 02-node-affinity.yaml
```

![78bb6ab9-2cc3-44fe-995a-b4d789c708ff.png|1134.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/78bb6ab9-2cc3-44fe-995a-b4d789c708ff.png) [^46]

![e1d6528b-33e7-4bda-b127-9bcf07c441fb.png|1134.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/e1d6528b-33e7-4bda-b127-9bcf07c441fb.png) [^47]

\

\

## <mark>**POD level Affinity**</mark>

POD1 is running, POD2 likes POD1. So POD2 wants to run where POD1 is running.

\

creating POD1

![92021c86-78dd-4b55-ac86-358f5d584a3d.png|1070.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/92021c86-78dd-4b55-ac86-358f5d584a3d.png) [^48]

\

git push & pull

![52092a9a-dead-4a0f-b08c-35e05678d733.png|929](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/52092a9a-dead-4a0f-b08c-35e05678d733.png) [^49]

\

```
kubectl apply -f 05-pod-affinity.yaml
```

![98051e68-37a6-450f-b884-9051ebf03091.png|1108.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/98051e68-37a6-450f-b884-9051ebf03091.png) [^50]

\

**apply POD level affinity**

requiredDuringSchedulingIgnoreDuringExecution: --> this is hard rule

![dd5d3f42-d68a-4568-b60a-e0e716017f6b.png|963](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/dd5d3f42-d68a-4568-b60a-e0e716017f6b.png) [^51]

\

git push & pull

![d99c72e2-e1e0-4b01-8037-1ad7d10197f7.png|958](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/d99c72e2-e1e0-4b01-8037-1ad7d10197f7.png) [^52]

\

```
kubectl apply -f 05-pod-affinity.yaml
```

![8525346e-d03f-400f-9ddc-3e9cf92ace06.png|1022.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/8525346e-d03f-400f-9ddc-3e9cf92ace06.png) [^53]

\

Now POD2 is also running where POD1 is running.

![aeaa4859-44f8-4704-a092-9379232f6f83.png|1042.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/aeaa4859-44f8-4704-a092-9379232f6f83.png) [^54]

\

\

## <mark>**POD level Anti-Affinity**</mark>

POD1 is running node1, POD2 runs where POD1 is not running i.e node2. 

\

\

## <mark>**Use-cases**</mark>

![2e9835e8-b6cc-47ec-b757-7ec3d6d58f99.png|633](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/2e9835e8-b6cc-47ec-b757-7ec3d6d58f99.png) [^55]

![49dc2f5e-1628-4f24-841d-9367d22749b3.png|440](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/49dc2f5e-1628-4f24-841d-9367d22749b3.png) [^56]

![97745f23-840c-43f9-b601-f684e78c8a14.png|1060.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/97745f23-840c-43f9-b601-f684e78c8a14.png) [^57]

\

![a3f36f09-94f7-4a93-9a18-dfeecea8c3c4.png|990.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/a3f36f09-94f7-4a93-9a18-dfeecea8c3c4.png) [^58]

\

![abe89b2a-49f1-419c-8f2b-584f61abb5e2.png|1024](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/abe89b2a-49f1-419c-8f2b-584f61abb5e2.png) [^59]

\

git push & pull

![69fc255f-268b-466f-a856-8419bbd969b4.png|889](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/69fc255f-268b-466f-a856-8419bbd969b4.png) [^60]

\

This is for database

```
kubectl apply -f 06-use-case.yaml
```

![18ceb081-0f60-43e7-a785-960b06e4c35b.png|1057.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/18ceb081-0f60-43e7-a785-960b06e4c35b.png) [^61]

\

updated code to create web-server pods

![f0d212d2-2069-448a-8c6e-bc40075ce996.png|957](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/f0d212d2-2069-448a-8c6e-bc40075ce996.png) [^62]

\

git push & pull

![c97f42c5-19c8-45e0-96c8-80cdd7b8d6ad.png|955](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/c97f42c5-19c8-45e0-96c8-80cdd7b8d6ad.png) [^63]

\

```
kubectl apply -f 06-use-case.yaml
```

![6334e3fa-9292-4d72-9444-04ee125db3a5.png|1097.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/6334e3fa-9292-4d72-9444-04ee125db3a5.png) [^64]

\

If you observe now redis is running in two different nodes... likewise webserver also running in two different nodes.

![31d8de24-aa9b-4b47-8b7e-60d20e55070b.png|1122.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/31d8de24-aa9b-4b47-8b7e-60d20e55070b.png) [^65]

![afb49679-2f03-40de-a382-53270bc5e0da.png|358](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/afb49679-2f03-40de-a382-53270bc5e0da.png) [^66]

\

\

\

\

\

\

\

\

\

---

# <mark style="background-color:#F8914D;">**K8 Cluster upgrade**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Currently version 1.27 is running

![523a4c4b-13f4-453d-bb6d-84f51dc3d020.png|875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/523a4c4b-13f4-453d-bb6d-84f51dc3d020.png) [^67]

\

Blue node group is running

![fcacc5c8-0d65-4802-8aab-90df2ae527ef.png|951.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/fcacc5c8-0d65-4802-8aab-90df2ae527ef.png) [^68]

\

<mark>**Upgrade steps**</mark>

![2046a2aa-38fa-4a39-be20-753cd4c2d6a8.png|952.6666870117188](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/2046a2aa-38fa-4a39-be20-753cd4c2d6a8.png) [^69]

\

uncommenting

![86d0fc60-c07e-465f-9ffd-646260cb0451.png|1090.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/86d0fc60-c07e-465f-9ffd-646260cb0451.png) [^70]

\

```
terraform fmt
cd 02-eks/
terraform fmt
```

![66be0c8c-4758-4e4e-b99e-4cb58505e48a.png|1093](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/66be0c8c-4758-4e4e-b99e-4cb58505e48a.png) [^71]

\

```
terraform plan
```

![125a374b-2a59-45cc-b80b-a4f58f53ebb3.png|1098.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/125a374b-2a59-45cc-b80b-a4f58f53ebb3.png) [^72]

\

```
terraform apply -auto-approve
```

![544f36b9-39ea-4b1c-9c9f-536b17769a29.png|1095](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/544f36b9-39ea-4b1c-9c9f-536b17769a29.png) [^73]

\

New nodes created & k8 cluster

![c69009b6-d133-4d1b-b8f4-060f3586fe50.png|1170.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/c69009b6-d133-4d1b-b8f4-060f3586fe50.png) [^74]

\

Now tainting the new nodes which are recently created. this will stop create pods in new nodes

```
kubectl taint node <node IP> project=roboshop:NoExecute
```

![758201c1-6f5c-43e8-aacf-7f30c29e90df.png|1038.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/758201c1-6f5c-43e8-aacf-7f30c29e90df.png) [^75]

\

Already PODS are running in old nodes

![22dc3af7-eda0-4c71-845d-3571e7c8012d.png|1072.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/22dc3af7-eda0-4c71-845d-3571e7c8012d.png) [^76]

\

creating a PODS which will create in OLD Nodes.

![a543e2c2-aada-432c-8505-e538a271db4a.png|971](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/a543e2c2-aada-432c-8505-e538a271db4a.png) [^77]

\

git push and pull

```
git add . ; git commit -m "upgrade"; git push origin main
```

![9ada3882-79fe-4825-98ba-a34f21dcf275.png|801](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/9ada3882-79fe-4825-98ba-a34f21dcf275.png) [^78]

\

```
kubectl apply -f service.yaml
```

![95749c04-2a39-45a4-9ff3-4d015f5faba2.png|1044.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/95749c04-2a39-45a4-9ff3-4d015f5faba2.png) [^79]

![22dc3af7-eda0-4c71-845d-3571e7c8012d.png|1072](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/22dc3af7-eda0-4c71-845d-3571e7c8012d.png) [^80]

\

<mark>**Now upgrade the control plane -- From 1.27 to 1.28**</mark>

\

We will do it from console only.

![4ff7c5d4-5c26-4557-a97d-78de840df0e0.png|1076.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/4ff7c5d4-5c26-4557-a97d-78de840df0e0.png) [^81]

\

![03c6e92b-e88e-42a5-bba1-4c927af92224.png|718](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/03c6e92b-e88e-42a5-bba1-4c927af92224.png) [^82]

\

Even upgrade is going on we are able to access the PODS etc...

![cec48794-ff89-43ce-a516-59971328abee.png|1085.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/cec48794-ff89-43ce-a516-59971328abee.png) [^83]

\

\

**Master is updated to 1.28 from 1.27**

![f073fc66-ddd4-4442-8d4b-0fa8c14dbeb2.png|1100.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/f073fc66-ddd4-4442-8d4b-0fa8c14dbeb2.png) [^84]

\

\

Now node group will display to upgrade

Old is blue.

new is green. --- I only upgrade green.

![11a0933b-ccce-4619-a437-0912b6d8b116.png|1064.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/11a0933b-ccce-4619-a437-0912b6d8b116.png) [^85]

\

Now the two nodes in the node group will upgrade in same time.

![86ea6c5f-33b4-4356-8635-1e063d0e2991.png|767](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/86ea6c5f-33b4-4356-8635-1e063d0e2991.png) [^86]

\

Now the new node group is with 1.28 version

![4ae4006e-63c4-40d4-9707-a24509db67cf.png|1086.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/4ae4006e-63c4-40d4-9707-a24509db67cf.png) [^87]

\

you can see versions here also

![238362a8-7054-48d7-8aec-d923f85f5f6f.png|1063.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/238362a8-7054-48d7-8aec-d923f85f5f6f.png) [^88]

\

\

<mark>**Now taint the blue node group.**</mark> (which is with old version)

```
kubectl taint node <node IP> project=roboshop:NoSchedule
```

![b3530444-54b3-4207-89a4-3582ea078b69.png|1050.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/b3530444-54b3-4207-89a4-3582ea078b69.png) [^89]

\

<mark>**untaint the new nodes**</mark> (which is new version, as i tainted earlier) (after upgrading new nodes IP changed)

\

<mark>**Draining the old nodes ( Now all the PODS etc move to new nodes) drain both nodes in same way.**</mark>

```
kubectl drain --ignore-daemonsets <old node IP> --force --delete-emptydir-data
```

![a65b11d8-5afb-4266-90f6-543e66160200.png|1196.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/a65b11d8-5afb-4266-90f6-543e66160200.png) [^90]

\

**If you observe PODS will move to new nodes from old nodes.**

![4cdbdd03-d511-4362-bbcf-3dd151375112.png|1166.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/4cdbdd03-d511-4362-bbcf-3dd151375112.png) [^91]

\

All PODS are running in new Nodes now

![fa4031f1-c9c3-4b31-99c2-66f3d34633c9.png|1206.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/fa4031f1-c9c3-4b31-99c2-66f3d34633c9.png) [^92]

\

\

Now commenting blue one

update the version here from 1.27 to 1.28

![](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/dd01654d-2735-497c-a385-6d75e484e72d.png) [^93]

![9641e9db-ed5a-44e6-88a5-c4f7c0d59c5d.png|1100.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/9641e9db-ed5a-44e6-88a5-c4f7c0d59c5d.png) [^94]

\

blue related will be destroyed

```
terraform plan
```

![1cc3ca05-423a-46bf-8998-f90ad608267a.png|1121.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/1cc3ca05-423a-46bf-8998-f90ad608267a.png) [^95]

\

once this step is done... Cluster upgrade is completed.

```
terraform apply -auto-approve
```

![5e8a8727-862a-42fe-8e75-1aa015dc6e2e.png|1132.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/5e8a8727-862a-42fe-8e75-1aa015dc6e2e.png) [^96]

\

blue node group will be deleted

![fb408221-12b5-44c9-8963-1896a363b64e.png|1091.666748046875](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/fb408221-12b5-44c9-8963-1896a363b64e.png) [^97]

\

\

[^1]: AWS Account
    VPC
    EKS Cluster
    53
    Amazon Route
    Amazon
    53
    EKS
    Ingress
    Controller

[^2]: EXPLORER
    main.tf terraform-aws-eks\\02-sg X
    main.tf ..\\03-eks
    main.tf ..\\01-vpc
    data.tf ... \\03-eks
    pa
    REPOS
    terraform-aws-eks > 02-sg > main.tf
    > roboshop-ansible-roles-tf
    29
    resource "aws_security_group_rule" "cluster_node" {
    > roboshop-docker
    36
    > roboshop-infra-dev
    37
    > roboshop-infra-prod
    38
    # node is accepting traffic from master on all ports
    > roboshop-shared-library
    39
    resource "aws_security_group_rule" "node_cluster" {
    40
    > roboshop-terraform
    source_security_group_id = module. cluster . sg_id
    41
    type
    = "ingress"
    terraform-aws-eks
    42
    from_port
    = 0
    > 01-vpc
    43
    to_port
    = 65535
    02-sg
    44
    protocol
    =
    "tcp"
    > .terraform
    45
    security_group_id
    = module . node . sg_id
    E.terraform.lock.hcl
    46
    data.tf
    47
    I
    48
    # nodes are accepting traffic on ephemeral ports from ingress controller
    main.tf
    49
    resource "aws_security_group_rule" "node_ingress" {
    parameters.tf
    50
    source_security_group_id = module . ingress . sg_id
    provider.tf
    51
    type
    = "ingress"
    variables.tf
    52
    from_port
    = 30000
    > 03-eks
    53
    to_port
    = 32767
    > terraform-aws-security-group
    54
    protocol
    "tcp"
    55
    security_group_id
    = module . node . sg_id
    > terraform-aws-vpc
    56
    > terraform-modules

[^3]: EXPLORER
    main.tf terraform-aws-eks\\02-sg
    main.tf ..\\03-eks X
    main.tf .. \\01-vpc
    data.tf ..\\03-eks
    paran
    REPOS
    terraform-aws-eks > 03-eks > main.tf
    > roboshop-docker
    1
    module "eks" {
    > roboshop-infra-dev
    17
    create_node_security_group = false
    > roboshop-infra-prod
    18
    node_security_group_id
    = local. node_sg_id
    19
    > roboshop-shared-library
    20
    # the user which you used to create cluster will get admin access
    > roboshop-terraform
    21
    enable_cluster_creator_admin_permissions = true
    terraform-aws-eks
    22
    > 01-vpc
    23
    # EKS Managed Node Group(s)
    > 02-sg
    24
    eks_managed_node_group_defaults = {
    03-eks
    25
    instance_types = \["mi. large", "m5. large", "man. large", "m5zn. large" \]
    > .terraform
    26
    27
    E.terraform.lock.hel
    28
    eks_managed_node_groups = {
    data.tf
    29
    blue = {
    locals.tf
    30
    min_size
    = 2
    main.tf
    31
    max_size
    = 10
    parameters.tf
    32
    desired_size = 2
    provider.tf
    33
    capacity_type = "SPOT"
    34
    variables.tf
    iam_role_additional_policies = {
    35
    AmazonEBSCSIDriverPolicy
    = "arn: aws : iam: : aws : policy/service-role/Amazon
    > terraform-aws-security-group
    36
    AmazonElasticFileSystemFullAccess = "arn: aws : iam: : aws : policy/AmazonElasticFilesys
    > terraform-aws-vpc
    37
    > terraform-modules
    38
    39
    > OUTLINE
    # green = {
    40
    #
    min size

[^4]: Commands
    54.85.180.74
    54 . 85 . 180 . 74 \| 172.31.88.240 \| t2.micro \| null
    \[ centoslip-172-31-88-240 \~ \]$ 0

[^5]: 54 . 85. 180. 74 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ aws eks update-kubeconfig --region us-east-1 --name roboshop-tf
    Updated context arn: aws : eks: us-east-1: 315069654700: cluster/roboshop-tf in /home/centos/. kube/config

[^6]: 54 . 85 . 180.74 \| 172. 31. 88 .240 \| t2. micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-33. ec2 . internal
    Ready
    <none>
    38m
    v1 . 27.9-eks-5eOfdde
    ip-10-0-12-172. ec2 . internal
    Ready
    <none>
    4 7m
    v1 . 27.9-eks-5eOfdde

[^7]: Instances (3) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    Instance state = running
    X
    Clear filters
    <
    1
    >
    Name
    Instance ID
    Instance state
    Instance type v Status check
    Alarm status
    Availability Zor
    blue
    i-008fd5bd306a03f56
    Running Q Q
    m5zn.large
    2/2 checks passed View alarms +
    us-east-1b
    O
    blue
    i-057a4a5647ea98be3
    Running Q Q
    m5zn.large
    2/2 checks passed View alarms +
    us-east-1a
    workstation-eksctl
    i-006b269d1b577ca59
    Running Q Q
    t2.micro
    2/2 checks passed View alarms +
    us-east-1a

[^8]: NoExecute
    This affects pods that are already running on the node as follows:
    . Pods that do not tolerate the taint are evicted immediately
    . Pods that tolerate the taint without specifying tolerationSeconds in their toleration
    specification remain bound forever
    . Pods that tolerate the taint with a specified tolerationSeconds remain bound for the
    specified amount of time. After that time elapses, the node lifecycle controller evicts the
    Pods from the node.
    NoSchedule
    No new Pods will be scheduled on the tainted node unless they have a matching toleration. Pods
    currently running on the node are not evicted.

[^9]: 54 . 85 . 180.74 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-33. ec2 . internal
    Ready
    <none>
    38m
    v1 . 27.9-eks-5eOfdde
    ip-10-0-12-172. ec2 . internal
    Ready
    <none>
    4 7m
    v1. 27.9-eks-5eOfdde
    54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ kubectl taint nodes ip-10-0-11-33. ec2. internal project=roboshop: NoSchedule
    node/ip-10-0-11-33. ec2. internal tainted

[^10]: EXPLORER
    . . .
    rovider.tf ...\\01-vpc
    main.tf terraform-aws-eks\\02-sg
    main.tf ..\\03-eks
    ! 01-taint-toleration.yaml
    V REPOS
    k8-resources > selectors > ! 01-taint-toleration.yaml > {} spec > \[ \] containers > {} 0 > \[ \] ports > {} 0 > # cont
    > catalogue
    1
    apiVersion: v1
    > catalogue-deploy
    2
    kind: Pod
    3
    > dockerfiles
    metadata:
    14
    name: taint-pod
    > helm-charts
    5
    spec :
    > k8-databases
    6
    # list of containers
    > k8-eksctl
    7
    containers :
    > k8-ingress
    8
    name: hello-pod
    k8-resources
    9
    image: nginx
    10
    > 01-namespace
    #here with this line port will not be opened, just for information
    11
    > 02-pods
    ports :
    12
    - containerPort: 80 I
    selectors
    ! 01-taint-toleration.yaml
    U

[^11]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-eks/03-eks
    $ cd . ./. ./k8-resources/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 0824f2a\] jenkins
    1 file changed, 12 insertions (+)
    create mode 100644 selectors/01-taint-toleration. yam1

[^12]: 54 . 85 . 180.74 \| 172. 31. 88.240 \| t2.micro \| null
    \[ centos@ip-172-31-88-240 \~ \]$ git clone https: //github. com/daws-76s/k8-resources . git
    Cloning into 'k8-resources' .
    remote: Enumeratiog objects: 161, done.
    remote: Counting objects: 100% (161/161) , done.
    remote: Compressing objects: 100% (113/113) , done.
    remote: Total 161 (delta 72), reused 126 (delta 37) , pack-reused 0
    Receiving objects: 100% (161/161), 16.35 KiB \| 4. 09 MiB/s, done.

[^13]: 54 . 85 . 180. 74 \| 172. 31 .88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources \]$ cd selectors/
    54 . 85. 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 01-taint-toleration. yaml
    pod/taint-pod created

[^14]: 54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl get pods -o wide
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    IP
    NODE
    NOMINATED NODE
    READINESS GATES
    taint-pod
    1/1
    Running
    6s
    10 . 0 . 12 . 101
    ip-10-0-12-172. ec2 . internal
    <none>
    <none>

[^15]: 54 . 85 . 180.74 \| 172. 31 . 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl delete -f 01-taint-toleration. yaml
    pod "taint-pod" deleted

[^16]: You specify a toleration for a pod in the PodSpec. Both of the following tolerations "match" the taint
    created by the kubectl taint line above, and thus a pod with either toleration would be able to
    schedule onto

[^17]: V REPOS
    k8-resources > selectors > ! 01-taint-toleration.yaml > {} spec > \[ \] tolerations > {} 0 > @ operator
    > catalogue
    1
    apiVersion: v1
    > catalogue-deploy
    2
    kind: Pod
    > dockerfiles
    3
    metadata:
    4
    name: taint-pod
    > helm-charts
    5
    spec :
    > k8-databases
    6
    # list of containers
    > k8-eksctl
    7
    containers :
    > k8-ingress
    8
    - name: hello-pod
    k8-resources
    9
    image: nginx
    10
    > 01-namespace
    #here with this line port will not be opened, just for information
    11
    > 02-pods
    ports:
    12
    - containerPort: 80
    selectors
    13
    tolerations :
    ! 01-taint-toleration.yaml
    M
    14
    key: "project"
    > service
    15
    operator: "Exists"
    > sets
    16
    effect: "NoSchedule"

[^18]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 14835cc\] jenkins
    1 file changed.
    5 insertions (+). 1 deletion(-)

[^19]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 14835cc\] jenkins
    1 file changed.
    5 insertions (+). 1 deletion(-)

[^20]: 54 . 85 . 180. 74 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 01-taint-toleration. yaml
    pod/taint-pod created
    54 . 85 . 180.74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    taint-pod
    1/1
    Running
    0
    5s
    54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl get pods -o wide
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    IP
    NODE
    NOMINATED NODE
    READINESS GATES
    taint-pod
    1/1
    Running
    0
    8s
    10 . 0. 11 .209
    ip-10-10-11-33. ec2 . internal
    <none>
    <none>
    54 . 85. 180.74 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$

[^21]: 54 . 85 . 180. 74 \| 172. 31. 88.240 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl taint nodes ip-10-0-11-33. ec2. internal project=roboshop : NoSchedule-
    node/ip-10-0-11-33. ec2. internal untainted

[^22]: 54 . 85. 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos(ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl delete -f 01-taint-toleration. yaml
    pod "taint-pod" deleted

[^23]: Affinity and anti-affinity
    nodeSelector is the simplest way to constrain Pods to nodes with specific labels. Affinity and anti-
    affinity expands the types of constraints you can define. Some of the benefits of affinity and anti-
    affinity include:
    . The affinity/anti-affinity language is more expressive. nodeSelector only selects nodes with all
    the specified labels. Affinity/anti-affinity gives you more control over the selection logic.
    . You can indicate that a rule is soft or preferred, so that the scheduler still schedules the Pod
    even if it can't find a matching node.
    . You can constrain a Pod using labels on other Pods running on the node (or other topological
    domain), instead of just node labels, which allows you to define rules for which Pods can be co-
    located on a node.
    The affinity feature consists of two types of affinity:
    . Node affinity functions like the nodeSelector field but is more expressive and allows you to
    specify soft rules.
    . Inter-pod affinity/anti-affinity allows you to constrain Pods against labels on other Pods.
    Node affinity
    Node affinity is conceptually similar to nodeSelector , allowing you to constrain which nodes your
    Pod can be scheduled on based on node labels. There are two types of node affinity:
    requiredDuring!SchedulingIgnoredDuringExecution : The scheduler can't schedule the Pod unless
    the rule is met. This functions like nodeSelector , but with a more expressive syntax.
    . preferredDuringSchedulingIgnoredDuringExecution : The scheduler tries to find a node that meets
    the rule. If a matching node is not available, the scheduler still schedules the Pod.

[^24]: Note: In the preceding types, IgnoredDuringExecution means that if the node labels change after
    Kubernetes schedules the Pod, the Pod continues to run

[^25]: requiredDuringSchedulingIgnoredDuringExecution
    schedule --> hard rule, while scheduling also labels should be matched
    execute
    preferredDuringSchedulingIgnoredDuringExecution

[^26]: 54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos(ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-33. ec2 . internal
    Ready
    <none>
    56m
    v1 . 27.9-eks-5eOfdde
    ip-10-0-12-172. ec2. internal
    Ready
    <none>
    65m
    v1. 27.9-eks-5eOfdde
    54 . 85. 180. 74 \| 172. 31 . 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/8-resources/selectors \]$ kubectl label nodes ip-10-0-11-33. ec2. internal project=roboshop
    node/ip-10-0-11-33. ec2 . internal labeled

[^27]: REPOS
    rces > selectors > ! 02-node-affinity.yaml > {} spec > {} affinity > {} nodeAffinity > {} require
    Lalalogue
    H
    apiVersion: v1
    > catalogue-deploy
    12
    kind: Pod
    > dockerfiles
    3
    metadata:
    > helm-charts
    4
    name: with-node-affinity
    > k8-databases
    5
    spec :
    > k8-eksctl
    6
    affinity :
    7
    nodeAffinity :
    > k8-ingress
    18
    requiredDuringSchedulingIgnoredDuringExecution:
    V k8-resources
    19
    nodeSelectorTerms :
    > 01-namespace
    10
    - ImatchExpressions :
    > 02-pods
    11
    - key: project
    selectors
    12
    operator: In
    ! 01-taint-toleration.yaml
    13
    values :
    14
    ! 02-node-affinity.yaml -
    U
    roboshop1
    15
    containers:
    > service
    16
    name: with-node-affinity
    > sets
    17
    image: nginx
    > storage
    > k8-roboshop

[^28]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main codaac7\] jenkins
    1 file changed, 17 insertions (+)
    create mode 100644 selectors/02-no

[^29]: 54 . 85 . 180. 74 \| 172. 31 . 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 02-node-affinity . yaml
    pod/with-node-affinity created
    54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    with-node-affinity
    0/1
    Pending
    0
    4s

[^30]: Commands
    . 0#910
    54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn: aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <C>
    Copy
    Cluster: arn: aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <e>
    Edit
    User:
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <n>
    Next Match
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <shift-n>
    Prev Match
    K8s Rev: v1.27.9-eks-5eOfdde
    <r>
    Toggle Auto-Refresh
    CPU :
    n/a
    <f>
    Toggle Fullscreen
    MEM :
    n/a
    Describe (default/with-node-affinity)
    /var/run/secrets/kubernetes . io/serviceaccount from kube-api-access-vxdx2 (ro)
    Conditions :
    Type
    Status
    PodScheduled
    False
    Volumes :
    kube-api-access-vxdx2 :
    Type:
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
    Warning FailedScheduling 43s
    default-scheduler 0/2 nodes are available: 2 node (s) didn't match Pod's node affinity/selector.
    preemption: 0/2 nodes are available: 2 Preemption is not helpful for scheduling. .
    <pod>
    <describe>

[^31]: 54 . 85. 180.74 \| 172. 31. 88 .240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl delete -f 02-node-affinity . yaml
    pod "with-node-affinity" deleted

[^32]: REPOS
    ty > { } requiredDuringSchedulingignoredDuringExecution > \[ \] nodeSelectorTerms > {} 0 > \[ \] matchExpressions
    Catalogue
    1
    apiVersion: v1
    > catalogue-deploy
    2
    kind: Pod
    > dockerfiles
    3
    metadata:
    > helm-charts
    14
    name: with-node-affinity
    > k8-databases
    5
    spec :
    > k8-eksctl
    6
    affinity :
    > k8-ingress
    7
    nodeAffinity :
    8
    requiredDuringSchedulingIgnoredDuringExecution:
    k8-resources
    19
    nodeSelectorTerms :
    > 01-namespace
    10
    - matchExpressions :
    > 02-pods
    11
    key: project
    selectors
    12
    operator: In
    ! 01-taint-toleration.yaml
    13
    values :
    ! 02-node-affinity.yaml
    14
    -
    roboshop
    I
    15
    containers :
    > service
    16
    name: with-node-affinity
    > sets
    17
    image: nginx
    > storage
    > k8-roboshop

[^33]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main codaac7\] jenkins
    1 file changed, 17 insertions (+)
    create mode 100644 selectors/02-no

[^34]: 54 . 85 . 180.74 \| 172. 31 .88.240 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 02-node-affinity . yaml
    pod/with-node-affinity created

[^35]: 54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn: aws : eks : us-east-1: 315069654700: cluster/roboshop-tf
    <0> all
    <a>
    Attach
    ...
    Cluster: arn: aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <1> default
    <ctri-d> Delete
    <p>
    User :
    arn : aws : eks : us-east-1: 315069654700: cluster/roboshop-tf
    <d>
    Describe
    <shifl
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1 .27.9-eks-5eOfdde
    < ? >
    Help
    <s>
    CPU :
    n/a
    <ctrl-k> Kill
    <O>
    MEM:
    n/a
    Pods (default) \[1\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    with-node-affinity
    1/1
    Running
    0 10 . 0. 11 . 141
    ip-10-0-11-33. ec2 . internal
    I

[^36]: 54 . 85. 180.74 \| 172. 31. 88 .240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl label nodes ip-10-0-12-172. ec2. internal project=amazon
    node/ip-10-0-12-172. ec2 . internal labeled

[^37]: V REPOS
    Affinity > {} requiredDuringSchedulingIgnoredDuringExecution > \[ \] nodeSelectorTerms > {} 0 > \[ \]n
    Lalalogue-deploy
    1
    apiVersion: v1
    > dockerfiles
    2
    kind: Pod
    > helm-charts
    3
    metadata:
    > k8-databases
    14
    name: with-node-anti-affinity
    > k8-eksctl
    5
    spec :
    > k8-ingress
    16
    affinity :
    7
    k8-resources
    nodeAffinity:
    8
    requiredDuringSchedulingIgnoredDuringExecution:
    > 01-namespace
    9
    nodeSelectorTerms :
    > 02-pods
    10
    matchExpressions :
    selectors
    11
    key: project
    ! 01-taint-toleration.yaml
    12
    operator: NotIn
    ! 02-node-affinity.yaml
    13
    values:
    14
    ! 03-node-anti-affinity.yaml -
    roboshop
    15
    containers :
    > service
    16
    - name: with-node-anti-affinity
    > sets
    17
    image: nginx
    I
    > storage

[^38]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources
    $ git add
    . ; git commit -m "jenkins"; git push origin main
    \[main 291a518\] jenkins
    1 file changed, 17 insertions (+)
    create mode 100644 selectors/03-node-anti-affinity. yam1

[^39]: 54 . 85. 180. 74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 03-node-anti-affinity . yaml
    pod/with-node-anti-affinity created

[^40]: i Protocol SSH
    . Host 54.85.180.74
    Login
    Password
    Session centos-8
    . O X
    Commands
    54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn: aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <0> all
    <a>
    Attach
    <1>
    ...
    Cluster: arn: aws : eks : us-east-1: 315069654700: cluster/roboshop-tf
    <1> default
    <ctrl-d> Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <d>
    Describe
    <shif\|
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1.27.9-eks-5e0fdde
    < ?>
    Help
    <s>
    CPU :
    n/a
    <ctrl-k> Kill
    <O>
    MEM:
    n/a
    Pods (default) \[2\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    with-node-affinity
    1/1
    Running
    0 10 . 0. 11 . 141
    ip-10-0-11-33. ec2 . internal
    3m5s
    with-node-anti-affinity
    1/1
    Running
    0 10.0 . 12 . 136
    ip-10-0-12-172. ec2. internal
    6s

[^41]: linux
    preferredDuringSchedulingIgnoredDuringExecution:
    - weight: 1
    preference:
    matchExpressions :
    - key: label-1
    operator : In
    values:
    - key-1
    weight: 50
    preference:
    natchExpressions:
    - key: label-2
    operator: In
    values:
    key-2
    containers:
    - name: with-node-affinity
    image: registry.k8s. io/pause:2.0

[^42]: REPOS
    's > selectors > ! 04-affinity-weight.yaml > {} spec > {} affinity > {} nodeAffinity > \[ \] preferr
    aockerines
    1
    apiVersion: v1
    > helm-charts
    2
    kind: Pod
    > k8-databases
    3
    metadata :
    > k8-eksctl
    4
    name: with-affinity-anti-affinity
    > k8-ingress
    5
    spec:
    V k8-resources
    6
    affinity:
    7
    > 01-namespace
    nodeAffinity :
    8
    preferredDuringSchedulingIgnoredDuringExecution :
    > 02-pods
    9
    - weight: 1
    selectors
    10
    preference :
    01-taint-toleration.yaml
    11
    matchExpressions :
    02-node-affinity.yaml
    12
    key: project
    ! 03-node-anti-affinity.yaml
    13
    operator: In
    14
    ! 04-affinity-weight.yaml
    U
    values :
    15
    amazon
    > service
    16
    weight : 50
    > sets
    17
    preference :
    > storage
    18
    matchExpressions :
    > k8-roboshop
    19
    - key: project
    > roboshop-ansible-roles
    20
    operator : In
    > roboshop-ansible-roles-tf
    21
    values :
    22
    roboshop
    > roboshop-docker
    23
    containers :
    J ...
    OUTLINE
    24
    - name: with-node-affinity
    25
    TIMELINE
    image: registry . k8s . io/pause: 2.0

[^43]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 404a750\] jenkins
    1 file changed, 25 insertions (+)
    create mode 100644 selectors/04-affinity-weight. yam1

[^44]: 54 . 85. 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 04-affinity-weight. yaml
    pod/with-affinity-anti-affinity created

[^45]: 54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn : aws : eks : us-east-1: 315069654700 : cluster/roboshop-tf
    <0> all
    <a>
    Attach
    Cluster: arn: aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <1> default
    <ctrl-d>
    Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <d>
    Describe
    <shifl
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1.27.9-eks-5eOfdde
    < ?>
    Help
    KS>
    CPU:
    n/a
    <ctrl-k> Kill
    <o>
    MEM:
    n/a
    Pods (default) \[3\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    with-affinity-anti-affinity
    1/1
    Running
    0 10 .0.11.80
    lip-10-0-11-33. ec2 . internal
    8s
    with-node-affinity
    1/1
    Running
    0 10 . 0. 11 . 141
    ip-10-0-11-33. ec2 . internal
    4m51s
    with-node-anti-affinity
    1/1
    Running
    0 10. 0. 12 . 136
    ip-10-0-12-172. ec2 . internal
    112s

[^46]: 54 . 85 . 180.74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl delete -f 04-affinity-weight. yaml
    pod "with-affinity-anti-affinity" deleted
    54 . 85. 180.74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl delete -f 03-node-anti-affinity . yaml
    pod "with-node-anti-affinity" deleted

[^47]: 54 . 85. 180.74 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl delete -f 02-node-affinity . yaml
    pod "with-node-affinity" deleted

[^48]: REPOS
    k8-resources > selectors > ! 05-pod-affinity.yaml > {} spec > \[ \] containers > {} 0 > \[ \] ports > {} 0 > #
    neilI-criarts
    H
    apiVersion: v1
    > k8-databases
    2
    kind: Pod
    > k8-eksctl
    3
    metadata:
    > k8-ingress
    4
    name: affinity-pod-1
    k8-resources
    15
    spec :
    > 01-namespace
    6
    # list of containers
    7
    > 02-pods
    containers :
    8
    - name: hello-pod
    selectors
    9
    image: nginx
    ! 01-taint-toleration.yaml
    10
    #here with this line port will not be opened, just for information
    ! 02-node-affinity.yaml
    11
    ports :
    ! 03-node-anti-affinity.yaml
    12
    - containerPort : 80
    ! 04-affinity-weight.yaml
    ! 05-pod-affinity.yaml
    U

[^49]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main ed4bcb2\] jenkins
    1 file changed, 12 insertions (+)
    create mode 100644 selectors/05-pod-affinity. yaml

[^50]: 54 . 85 . 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. dom/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 05-pod-affinity . yaml
    pod/affinity-pod-1 created

[^51]: VREPOS
    k8-resources > selectors > ! 05-pod-affinity.yaml > {} metadata > name
    neill-criarts
    5
    spec:
    > k8-databases
    7
    containers :
    > k8-eksctl
    8
    - name: hello-pod
    > k8-ingress
    12
    - containerPort: 80
    k8-resources
    13
    > 01-namespace
    14
    apiVersion: v1
    > 02-pods
    15
    kind: Pod
    selectors
    16
    metadata:
    17
    ! 01-taint-toleration.yaml
    name: affinity-pod-2
    18
    spec :
    ! 02-node-affinity.yaml
    19
    affinity:
    03-node-anti-affinity.yaml
    20
    podAffinity :
    ! 04-affinity-weight.yaml
    21
    requiredDuringSchedulingIgnoredDuringExecution:
    ! 05-pod-affinity.yaml
    M
    22
    labelSelector :
    > service
    23
    matchExpressions :
    24
    > sets
    - key: name
    25
    operator: InI
    > storage
    26
    values :
    > k8-roboshop
    27
    - affinity-pod-1
    > roboshop-ansible-roles
    28
    topologyKey : topology . kubernetes . io/zone
    > roboshop-ansible-roles-tf
    29
    containers :
    > roboshop-docker
    30
    name: with-pod-affinity
    31
    image: nginx

[^52]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 2cd8759\] jenkins
    1 file changed, 20 insertions (+), 1 deletion(-)

[^53]: 54 . 85. 180. 74 \| 172. 31.88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 05-pod-affinity. yaml
    pod/affinity-pod-1 unchanged
    pod/affinity-pod-2 created

[^54]: 54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <0> all
    <a>
    Attach
    <1>
    Cluster: arn: aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <1> default
    <ctrl-d> Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <d>
    Describe
    <shif\|
    K9s Rev: V0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1 . 27.9-eks-5eOfdde
    <?>
    Help
    <S>
    CPU :
    n/a
    <ctrl-k> Kill
    <0>
    MEM :
    n/a
    Pods (default) \[2\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    A
    affinity-pod-1
    1/1
    Running
    0 10 .0.11 . 175
    ip-10-0-11-33. ec2. internal
    4
    affinity-pod-2
    1/1
    Running
    0 10 .0.11. 163
    ip-10-0-11-33. ec2 . internal

[^55]: Creating the two preceding Deployments results in the following cluster layout, where each web
    server is co-located with a cache, on three separate nodes.
    node-1
    node-2
    node-3
    webserver-1 webserver-2 webserver-3
    cache-1
    cache-2
    cache-3

[^56]: NODE-1
    NODE-1
    web-app
    Cache
    NODE-2
    NODE-2
    web-app
    Cache

[^57]: 2 replicas, anti-affinity
    Ist replica --> it will select node-1
    2nd replica --> it should not select node-1 because of anti-affinity

[^58]: redis
    Ist replica --> it will select node-1
    2nd replica --> it should not select node-1 because of anti-affinity
    web-store
    pod-1
    anti-affinity --> Ist pod will select any node i.e node-1.
    go and select where app : store is running
    pod-2
    anti-affinity --> because of anti-affinity on replica-1, it goes to node-2

[^59]: V REPOS
    k8-resources > selectors > ! 06-use-case.yaml > {} spec > {} template > {} spec > {} affinity > {} podAntiAffinity > \[
    Ko-ualabases
    5
    spec :
    > k8-eksctl
    10
    template :
    > k8-ingress
    11
    metadata:
    k8-resources
    13
    app: store
    > 01-namespace
    14
    spec :
    15
    > 02-pods
    affinity :
    16
    podAntiAffinity :
    selectors
    17
    requiredDuringSchedulingIgnoredDuringExecution :
    ! 01-taint-toleration.yaml
    18
    labelSelector :
    02-node-affinity.yaml
    19
    matchExpressions :
    03-node-anti-affinity.yaml
    20
    - key: app
    04-affinity-weight.yaml
    21
    operator: In
    22
    ! 05-pod-affinity.yaml
    values :
    23
    store
    ! 06-use-case.yaml
    U
    24
    topologykey: "kubernetes . io/hostname"
    > service
    25
    containers :
    ) sets
    26
    - name: redis-server
    > storage
    27
    image: redis : 3. 2-alpine
    > k8-roboshop

[^60]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main la9fc3c\] jenkins
    1 file changed, 27 insertions (+)
    create mode 100644 selectors/06-use-case. yaml

[^61]: 54 . 85. 180. 74 \| 172. 31 . 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 06-use-case . yaml
    deployment . apps/redis-cache created

[^62]: V REPOS
    spec > { } affinity > { } podAffinity > \[ \] requiredDuringSchedulingignoredDuringExecution > {} 0 > {} labelSelect
    Ko-ualabases
    LO
    > k8-eksctl
    29
    apiVersion: apps/v1
    > k8-ingress
    30
    kind: Deployment
    31
    k8-resources
    metadata:
    32
    name: web-server
    > 01-namespace
    33
    spec :
    > 02-pods
    34
    selector:
    selectors
    35
    matchLabels :
    01-taint-toleration.yaml
    36
    app: web-store
    ! 02-node-affinity.yaml
    37
    replicas: 2
    03-node-anti-affinity.yaml
    38
    template :
    39
    ! 04-affinity-weight.yaml
    metadata:
    40
    labels :
    ! 05-pod-affinity.yaml
    41
    app: web-store
    ! 06-use-case.yaml
    M
    42
    spec :
    > service
    43
    affinity :
    >
    sets
    44
    podAntiAffinity :
    > storage
    45
    requiredDuringSchedulingIgnoredDuringExecution :
    46
    > k8-roboshop
    - labelSelector:
    47
    matchExpressions :
    > roboshop-ansible-roles
    48
    key : app
    > roboshop-ansible-roles-tf
    I
    49
    operator: In
    > roboshop-docker
    50
    values :
    :..L..- J.. .
    51
    - web-store
    > OUTLINE
    52
    topologyKey: "kubernetes . io/hostname"

[^63]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 82e0b6e\] jenkins
    1 file changed, 39 insertions (+), 1 deletion(-)

[^64]: 54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ kubectl apply -f 06-use-case. yaml
    deployment . apps/redis-cache unchanged
    deployment . apps/web-server created

[^65]: Protocol SSH
    Host 54.85.180.74
    Login
    Password
    Session centos-8
    . OX
    Commands
    54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <0> all
    <a>
    Attach
    <1>
    Cluster: arn: aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <1> default
    <ctrl-d>
    Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <d>
    Describe
    <shif \|
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1.27.9-eks-5eOfdde
    <? >
    Help
    <s>
    CPU :
    n/a
    <ctrl-k> Kill
    <0>
    MEM :
    n/a
    Pods (default) \[6\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    affinity-pod-1
    1/1
    Running
    0 10 . 0 . 11 . 175
    ip-10-0-11-33. ec2 . internal
    10m
    affinity-pod-2
    1/1
    Running
    0 10 . 0. 11.163
    ip-10-0-11-33. ec2. internal
    10m
    redis-cache-674d5b9968-21rvc
    1/1
    Running
    0 10 .0. 11. 47
    ip-10-0-11-33. ec2. internal
    3m40s
    redis-cache-674d5b9968-c17d8
    1/1
    Running
    0 10 .0. 12. 161
    ip-10-0-12-172. ec2 . internal
    3m40s
    web-server-588fb58cd-vpn4f
    1/1
    Running
    0 10.0. 11. 209
    ip-10-0-11-33. ec2. internal
    10s
    web-server-588fb58cd-z8jon
    1/1
    Running
    0 10. 0.12. 60
    ip-10-0-12-172. ec2. internal I
    10s

[^66]: NODE-1
    NODE-1
    love
    web-app
    Cache
    hate
    hate
    NODE-2
    NODE-2
    love
    web-app
    Cache

[^67]: Amazon Elastic
    X
    EKS > Clusters
    Kubernetes Service
    New Kubernetes versions are available for 1 cluster.
    X
    Clusters New
    Amazon EKS Anywhere
    Clusters (1) Info
    C
    Delete
    Add cluster
    Enterprise Subscriptions New
    Q Filter clusters
    <
    1
    Related services
    Amazon ECR
    Cluster name
    Status
    4
    Kubernetes version
    V
    Support type
    Provider
    AWS Batch
    O
    roboshop-tf
    Active
    1.27 Update now
    A Standard support until July 24, 2024
    EKS

[^68]: Node groups (1) Info
    Edit
    Delete
    Add node group
    Group name
    Desired size
    AMI release version
    4
    Launch template
    Status
    D
    O
    blue-2024030801304934670000000q
    2
    1.27.9-20240227
    blue-2024030801304730040000000c (1)
    Active

[^69]: you can announce no create/update of applications, no releases or changes
    blue --> green
    1. create a seperate node group called green
    2. we need to taint new nodes
    3. upgrade control plane to 1. 28
    4. upgrade green node group to 1. 28
    5. taint blue nodes so that new pods will not be scheduled
    6. untaint green
    7. cordon/drain the blue nodes. ..

[^70]: EXPLORER
    main.tf ..\\03-eks X
    ! 01-taint-toleration.yaml
    ! 02-node-affinity.yaml
    ! 03-node-anti-affinity.yaml
    REPOS
    terraform-aws-eks > 03-eks > main.tf
    > k8-ingress
    1
    module "eks" {
    > k8-resources
    28
    eks_managed_node_groups = {
    > k8-roboshop
    29
    blue = {
    33
    > roboshop-ansible-roles
    capacity_type = "SPOT"
    34
    iam_role_additional_policies = {
    > roboshop-ansible-roles-tf
    35
    AmazonEBSCSIDriverPolicy
    = "arn : aws : iam: : aws : policy/service-role/Amazon
    > roboshop-docker
    36
    AmazonElasticFileSystemFullAccess = "arn: aws : iam: : aws : policy/AmazonElasticFileSys
    > roboshop-infra-dev
    37
    > roboshop-infra-prod
    38
    > roboshop-shared-library
    39
    green = {
    40
    > roboshop-terraform
    min_size
    = 1
    41
    max_size
    = 10
    terraform-aws-eks
    42
    desired_size = 1
    > 01-vpc
    43
    capacity_type = "SPOT"
    > 02-sg
    44
    iam_role_additional_policies = {
    03-eks
    45
    AmazonEBSCSIDriverPolicy = "arn: aws : iam: : aws : policy/service-role/AmazonEBSCSIDriverPc
    > .terraform
    46
    AmazonElasticFileSystemFullAccess = "arn: aws : iam: : aws : policy/AmazonElasticFileSystem
    47
    E.terraform.lock.hcl
    }
    48
    data.tf
    49
    locals.tf
    50
    main.tf
    51
    parameters.tf
    52
    tags = var . common_tags
    OUTLINE
    53

[^71]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-eks
    $ terraform fmt
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s /repos/terraform-aws-eks
    $ cd 03-eks/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-eks/03-eks
    $ terraform fmt
    main . tf
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-eks/03-eks
    $

[^72]: user@AshDexter-T480 MINGW64 /c/devops/ daws-76s/repos/terraform-aws-eks/03-eks
    $ terraform plan
    Acquiring state lock. This may take a few moments. . .
    data . aws_vpc . default: Reading. . .
    data . aws_ssm_parameter . vpc_id: Reading. .
    data . aws_ssm_parameter . node_sg_id: Reading. . .
    data . aws_ssm_parameter . private_subnet_ids: Reading. . .
    module. eks . module. eks_managed_node_group \["green"\]. data. aws_caller_identity. current: Reading. . .
    module. eks . data. aws_iam_policy_document . assume_role_policy \[0\] : Reading. . .
    data. aws_ssm_parameter . cluster_sg_id: Reading. . .
    module. eks . data. aws_caller_identity . current: Reading. . .
    module. eks. data. aws_partition . current: Reading. .
    module. eks . module. eks_managed_node_group \["blue"\]. data. aws_caller_identity . current: Reading. . .
    module. eks . data. aws_partition. current: Read complete after Os \[id=aws\]
    module. eks. data. aws_iam_policy_document. assume_role_policy \[0\]: Read complete after Os \[id=2764486067\]

[^73]: user@AshDexter-T480 MINGW64 /c/devops /daws-76s/repos/terraform-aws-eks/03-eks
    $ terraform apply
    -auto-approve

[^74]: 54 . 85 . 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-157. ec2. internal
    Ready
    <none>
    76s
    v1 . 27.9-eks-5eOfdde
    ip-10-0-11-33. ec2. internal
    Ready
    <none>
    8 9m
    v1. 27.9-eks-5eOfdde
    ip-10-0-12-184. ec2 . internal
    Ready
    <none>
    72s
    v1 . 27.9-eks-5eOfdde
    ip-10-0-12-40. ec2. internal
    Ready
    <none>
    6m13s
    v1 . 27.9-eks-5eOfdde

[^75]: 54 . 85. 180.74 \| 172. 31. 88.240 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-157. ec2. internal
    Ready
    <none>
    76s
    v1 . 27.9-eks-5eOfdde
    ip-10-0-11-33. ec2 . internal
    Ready
    <none>
    89m
    v1 .27.9-eks-5eOfdde
    lip-10-0-12-184. ec2 . internal
    Ready
    <none>
    72s
    v1 . 27.9-eks-5eOfdde
    ip-10-0-12-40. ec2 . internal
    Ready
    <none>
    6m13s
    v1 . 27.9-eks-5eOfdde
    54 . 85. 180.74 \| 172. 31. 88 .240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl taint node ip-10-0-11-157. ec2 . internal project=roboshop : NoExecute
    node/ip-10-0-11-157. ec2. internal tainted
    I
    54 . 85. 180.74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl taint node ip-10-0-12-184.ec2 . internal project=roboshop : NoExecute
    node/ip-10-0-12-184. ec2. internal tainted

[^76]: Context: arn: aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <0> all
    <a>
    Attach
    <1>
    Cluster:
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <1> default
    <ctrl-d> Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <d>
    Describe
    <shifl
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1 . 27.9-eks-5e0fdde
    <?>
    Help
    <s>
    CPU :
    n/a
    <ctrl-k> Kill
    <o>
    MEM :
    n/a
    Pods (default) \[8\]
    NAME
    PF
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    affinity-pod-1
    1/1
    Running
    0 10 . 0. 11 . 175
    ip-10-0-11-33. ec2 . internal
    20m
    affinity-pod-2
    1/1
    Running
    0 10 . 0. 11 . 163
    ip-10-0-11-33. ec2. internal
    20m
    nginx-deployment-86d976d8bd-s7xzg
    1/1
    Running
    0 10 .0. 11 . 80
    ip-10-0-11-33. ec2 . internal
    48s
    nginx-deployment-86d976d8bd-x15fr
    1/1
    Running
    0 10 .0. 12 . 160
    ip-10-0-12-40. ec2 . internal
    26s
    redis-cache-674d59968-21rvc
    1/1
    Running
    0 10 . 0 . 11 . 47
    ip-10-0-11-33. ec2 . internal
    13m
    redis-cache-674d5b99b8-gh75q
    1/1
    Running
    0 10 . 0. 12 . 48
    ip-10-0-12-40.ec2 . internal
    6m27s
    web-server-588fb58cd-8kz4m
    1/1
    Running
    0 10 .0.12. 94
    ip-10-0-12-40. ec2 . internal
    6m27s
    web-server-588fb58cd-vpn4f
    1/1
    Running
    0 10. 0. 11. 209
    ip-10-0-11-33. ec2 . internal
    10m

[^77]: EXPLORER
    ! 01-replica-set.yaml
    ! service.yaml .. \\upgrade U X ! 02-deployment-set.yaml
    V REPOS
    k8-resources > upgrade > ! service.yaml > {} spec > # replicas
    > k8-databases
    8
    spec :
    > k8-eksctl
    selector:
    > k8-ingress
    11
    matchLabels:
    k8-resources
    12
    app: nginx
    13
    > 01-namespace
    demo: deployment
    14
    template:
    > 02-pods
    15
    metadata:
    > selectors
    16
    labels :
    > service
    app: nginx
    > sets
    demo: deployment
    > storage
    spec :
    upgrade
    containers :
    17
    name: nginx
    ! service.yaml
    U
    image: nginx
    > k8-roboshop
    ports :
    > roboshop-ansible-roles
    14
    - containerPort: 80
    > roboshop-ansible-roles-tf
    15
    > roboshop-docker
    26
    apiVersion: v1
    > roboshop-infra-dev
    17
    kind: Service
    28
    > roboshop-infra-prod
    metadata :
    29
    name: nginx-service
    I
    > roboshop-shared-library
    spec :
    > roboshop-terraform
    selector :
    > OUTLINE
    32
    app: nginx

[^78]: user@AshDexter-T480 MINGW64 \~
    $ cd /c/devops/daws-76s/repos/k8-resources/upgrade/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources/upgrade (main
    $ cd /c/devops/daws-76s/repos/k8-resources/upgrade/AC
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources/upgrade (main
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main a79942f\] jenkins
    1 file changed, 37 insertions (+)
    create mode 100644 upgrade/service. yam

[^79]: 54 . 85. 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/selectors \]$ cd . ./upgrade/
    54 . 85. 180. 74 \| 172. 31. 88.240 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl apply -f service. yaml
    deployment . apps/nginx-deployment created
    service/nginx-service created

[^80]: Context: arn: aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <0> all
    <a>
    Attach
    <1>
    Cluster:
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <1> default
    <ctrl-d> Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <d>
    Describe
    <shifl
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <z>
    K8s Rev: v1 . 27.9-eks-5e0fdde
    <?>
    Help
    <s>
    CPU :
    n/a
    <ctrl-k> Kill
    <o>
    MEM :
    n/a
    Pods (default) \[8\]
    NAME
    PF
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    affinity-pod-1
    1/1
    Running
    0 10 . 0. 11 . 175
    ip-10-0-11-33. ec2 . internal
    20m
    affinity-pod-2
    1/1
    Running
    0 10 . 0. 11 . 163
    ip-10-0-11-33. ec2. internal
    20m
    nginx-deployment-86d976d8bd-s7xzg
    1/1
    Running
    0 10 .0. 11 . 80
    ip-10-0-11-33. ec2 . internal
    48s
    nginx-deployment-86d976d8bd-x15fr
    1/1
    Running
    0 10 .0. 12 . 160
    ip-10-0-12-40. ec2 . internal
    26s
    redis-cache-674d59968-21rvc
    1/1
    Running
    0 10 . 0 . 11 . 47
    ip-10-0-11-33. ec2 . internal
    13m
    redis-cache-674d5b99b8-gh75q
    1/1
    Running
    0 10 . 0. 12 . 48
    ip-10-0-12-40.ec2 . internal
    6m27s
    web-server-588fb58cd-8kz4m
    1/1
    Running
    0 10 .0.12. 94
    ip-10-0-12-40. ec2 . internal
    6m27s
    web-server-588fb58cd-vpn4f
    1/1
    Running
    0 10. 0. 11. 209
    ip-10-0-11-33. ec2 . internal
    10m

[^81]: EKS > Clusters
    New Kubernetes versions are available for 1 cluster.
    X
    Clusters (1) Info
    C
    Delete
    Add cluster
    Q Filter clusters
    <
    1 >
    Cluster name
    Status
    D
    Kubernetes version
    Support type
    v
    Provider
    O
    roboshop-tf
    Active
    1.27 Update now
    A Standard support until July 24, 2024
    EKS

[^82]: ers
    Info
    Update cluster version: roboshop-tf
    X
    9 clusters
    Kubernetes version
    Cluster nar
    Select Kubernetes version for this cluster.
    1.28
    roboshop -t
    f until
    1.29
    VERSION.DISABLED_DESC. 1.29
    1.28
    V
    Available update
    1.27
    Currently installed
    Callcet
    opuate

[^83]: K8s Rev: v1 . 27.9-eks-5e0fdde
    <?>
    Help
    <s>
    CPU :
    n/a
    <ctrl-k> Kill
    <O>
    MEM :
    n/a
    Pods (default) \[8\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    affinity-pod-1
    1/1
    Running
    0 10 . 0. 11 . 175
    ip-10-0-11-33. ec2 . internal
    23m
    affinity-pod-2
    1/1
    Running
    0 10 .0. 11. 163
    ip-10-0-11-33. ec2. internal
    23m
    nginx-deployment-86d976d8bd-s7xzg
    1/1
    Running
    0 10 . 0. 11 .80
    ip-10-0-11-33. ec2 . internal
    3m22s
    nginx-deployment-86d976d8bd-x15fr
    1/1
    Running
    0 10 . 0 . 12 . 160
    ip-10-0-12-40. ec2 . internal
    3m
    redis-cache-674d5b998-21rvc
    1/1
    Running
    0 10 . 0 . 11. 47
    ip-10-0-11-33. ec2. internal
    16m
    redis-cache-674d5b9968-gh75q
    1/1
    Running
    0 10 . 0. 12 . 48
    ip-10-0-12-40. ec2 . internal
    9m1s
    web-server-588fb58cd-8kz4m
    1/1
    I Running
    0 10 .0. 12 .94
    ip-10-0-12-40. ec2 . internal
    9m1s
    web-server-588fb58cd-vpn4f
    1/1
    Running
    0 10 .0. 11. 209
    ip-10-0-11-33. ec2 . internal
    12m

[^84]: EKS > Clusters
    New Kubernetes versions are available for 1 cluster.
    X
    Clusters (1) Info
    C
    Delete
    Add cluster
    Q Filter clusters
    <
    1
    Cluster name
    Status
    4
    Kubernetes version
    Support type
    4
    Provider
    O
    roboshop-tf
    Active
    1.28 Update now
    Standard support until November 26, 2024
    EKS

[^85]: Node groups (2) Info
    Edit
    Delete
    Add node group
    Group name
    Desired size
    AMI release version
    4
    Launch template
    Status
    O
    blue-2024030801304934670000000e
    2
    1.27.9-20240227 Update now
    blue-2024030801304730040000000c (1)
    Active
    O
    green-20240308030725422600000009
    2
    1.27.9-20240227 Update now
    green-20240308030723740400000007 (1)
    Active

[^86]: Update node group version: green-
    X
    Cre
    20240308030725422600000009
    Update node group version
    Update your node group AMI release version to the latest available version for your 1.28 cluster.
    Change launch template version
    Change your node group to use a different launch template version.
    Update strategy
    oups
    Select how to update this node group.
    Force update
    roup nam
    lunch t
    be-20240
    A This option does not respect pod disruption budgets and it forces node
    ue-202
    een-202
    restarts. Choosing this option may disrupt running applications.
    een-20
    Learn more
    profile
    AMI release version notes
    ofile nan
    Cancel
    Update

[^87]: Node groups (2) Info
    Edit
    Delete
    Add node group
    Group name
    Desired size
    AMI release version
    A
    Launch template
    Status
    4
    O
    blue-2024030801304934670000000e
    2
    1.27.9-20240227 Update now
    blue-2024030801304730040000000c (1)
    Active
    O
    green-20240308030725422600000009
    2
    1.28.5-20240227
    green-20240308030723740400000007 (1)
    Active

[^88]: 54 . 85 . 180. 74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-247.ec2. internal
    Ready
    <none>
    7m34s
    v1 . 28.5-eks-5e0fdde
    ip-10-0-11-33. ec2\[. internal
    Ready
    <none>
    112m
    v1 . 27.9-eks-5eOfdde
    ip-10-0-12-119. ec2. internal
    Ready
    <none>
    7m35s
    v1 . 28.5-eks-5eOfdde
    ip-10-0-12-40. ec2. internal
    Ready
    <none>
    29m
    v1 . 27.9-eks-5eOfdde

[^89]: 54 . 85 . 180. 74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-10-0-11-247. ec2 . internal
    Ready
    <none>
    7m34s
    v1 . 28.5-eks-5eOfdde
    ip-10-0-11-33. ec2. internal
    Ready
    <none>
    112m
    v1. 27.9-eks-5eOfdde
    ip-10-0-12-119. ec2 . internal
    Ready
    <none>
    7m35s
    v1 . 28.5-eks-5eOfdde
    ip-10-0-12-40. ec2. internal
    Ready
    <none>
    29m
    v1 . 27.9-eks-5eOfdde
    54 . 85. 180. 74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl taint node ip-10-0-11-33. ec2. internal project=roboshop : NoSchedule
    node/ip-10-0-11-33. ec2 . internal tainted
    54 . 85 . 180. 74 \| 172. 31 . 88 .240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl taint, node ip-10-0-12-40. ec2. internal project=roboshop : NoSchedule
    node/ip-10-0-12-40. ec2. internal tainted

[^90]: 54 . 85 . 180. 74 \| 172. 31. 88.240 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centosdip-172-31-88-240 \~/k8-resources/upgrade \]$ kubectl drain --ignore-daemonsets ip-10-0-11-33. ec2. internal --force --delete-empty
    dir-data
    node/ip-10-0-11-33. ec2 . internal already cordoned
    Warning: ignoring DaemonSet-managed Pods: kube-system/aws-node-fwtql, kube-system/kube-proxy-p4qdn; deleting Pods that declare no contr
    oller: default/affinity-pod-1, default/affinity-pod-2
    evicting pod kube-system/coredns-d9b6d6c7d-z7ddv
    evicting pod default/affinity-pod-1
    evicting pod default/affinity-pod-2
    evicting pod default/nginx-deployment-86d976d8bd-s7xzg
    evicting pod default/redis-cache-674d5b9968-21rvc

[^91]: CPU :
    n/a
    <ctrl-k> Kill
    <O>
    MEM:
    n/a
    Pods (default) \[11\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    affinity-pod-1
    0/ 14
    Terminatinga
    0 n/ a4
    ip-10-0-11-33 . ec2 . internal
    affinity-pod-2
    0/14
    TerminatingA
    0 n/aA
    ip-10-0-11-33. ec2. internal
    4 6m
    nginx-deployment-86d976d8bd-s7xzg
    0/14
    TerminatingA
    0 n/a4
    ip-10-0-11-33. ec2 . internal
    27m
    nginx-deployment-86d976d8bd-t19ns
    0/1
    ContainerCreating
    0 n/a
    ip-10-0-11-247. ec2 . internal
    1s
    nginx-deployment-86d976d8bd-x15fr
    1/1
    Running
    0 10.0. 12 . 160
    ip-10-0-12-40. ec2 . internal
    26m
    redis-cache-674d5b9968-21rvc
    0/14
    TerminatingA
    I
    0 n/a4
    ip-10-0-11-33. ec2. internal
    40m
    redis-cache-674d5b9968-gh75q
    1/1
    Running
    0 10 . 0 .12 . 48
    ip-10-0-12-40. ec2 . internal
    32m
    redis-cache-674d5b99b8-zq74w
    0/1
    ContainerCreating
    0 n/a
    ip-10-0-11-247. ec2 . internal
    Is
    web-server-588fb58cd-8kz4m
    1/1
    Running
    0 10. 0. 12 . 94
    ip-10-0-12-40. ec2 . internal
    32m
    web-server-588fb58cd-n7mh7
    0/1
    Pending
    0 n/a
    n/a
    1s
    web-server-588fb58cd-vpn4f
    0/14
    TerminatingA
    0 n/a4
    ip-10-0-11-33. ec2 . internal
    36m

[^92]: 54.85.180.74 54.85.180.74 54.85.180.74
    Context: arn : aws : eks : us-east-1 : 315069654700: cluster/roboshop-tf
    <0> all
    Ka>
    Attach
    Cluster:
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <1> default
    <ctrl-d>
    Delete
    <p>
    User :
    arn : aws : eks : us-east-1 : 315069654700 : cluster/roboshop-tf
    <d>
    Describe
    <shifl
    K9s Rev: v0 . 32.1 4 v0 . 32.3
    <e>
    Edit
    <Z>
    K8s Rev: v1 .28.5-eks-5e0fdde
    <?>
    Help
    <S>
    CPU :
    n/a
    <ctrl-k> Kill
    <O>
    MEM :
    n/a
    Pods (default) \[6\]
    NAME
    PE
    READY
    STATUS
    RESTARTS IP
    NODE
    AGE
    nginx-deployment-86d976d8bd-t19ns
    1/1
    Running
    0 10 . 0 . 11 . 18
    ip-10-0-11-247. ec2 . internal
    9s
    nginx-deployment-86d976d8bd-x15fr
    1/1
    Running
    0 10 . 0 . 12 . 160
    ip-10-0-12-40.ec2 . internal
    27m
    redis-cache-674d5b99b8-gh 75q
    1/1
    Running
    0 10 . 0 . 12 . 48
    ip-10-0-12-40. ec2 . internal
    33m
    redis-cache-674d5b9968-zq74w
    1/1
    Running
    0 10 .0. 11 .96
    ip-10-0-11-247.ec2. internal
    9s
    web-server-588fb58cd-8kz4m
    1/1
    Running
    0 10 . 0 . 12 . 94
    ip-10-0-12-40. ec2 . internal
    33m
    web-server-588fb58cd-n7mh7
    1/1
    Running
    0 10 . 0 . 11 . 225
    ip-10-0-11-247. ec2. internal
    9s

[^93]: cluster_name
    "roboshop-tf"
    cluster_version = "1.28"

[^94]: EXPLORER
    . . .
    main.tf roboshop-infra-prod\\..
    provider.tf .. \\01-vpc
    main.tf terraform-aws-eks\\02-sg
    main.tf .. \\03-eks X
    V REPOS
    terraform-aws-eks > 03-eks > main.tf
    > k8-resources
    1
    module "eks" {
    17
    > k8-roboshop
    create_node_security_group = false
    18
    node_security_group_id
    = local . node_sg_id
    > roboshop-ansible-roles
    19
    > roboshop-ansible-roles-tf
    20
    # the user which you used to create cluster will get admin access
    > roboshop-docker
    21
    enable_cluster_creator_admin_permissions = true
    > roboshop-infra-dev
    22
    > roboshop-infra-prod
    23
    # EKS Managed Node Group(s)
    24
    > roboshop-shared-library
    eks_managed_node_group_defaults = {
    25
    instance_types = \["m6i. large", "m5. large", "man. large", "m5zn. large" \]
    > roboshop-terraform
    26
    terraform-aws-eks
    27
    > 01-vpc
    28
    eks_managed_node_groups = {
    > 02-sg
    29
    # blue = {
    03-eks
    30
    #
    min_size
    = 2
    31
    #
    max_size
    = 10
    > .terraform
    32
    #
    desired_size = 2
    E.terraform.lock.hcl
    33
    #
    capacity_type = "SPOT"
    data.tf
    34
    #
    iam_role_additional_policies = {
    locals.tf
    35
    E#
    AmazonEBSCSIDriverPolicy
    = "arn: aws : iam: : aws : policy/service-role/Amazc
    main.tf
    36
    #
    AmazonElasticFileSystemFullAccess = "arn: aws : iam: : aws : policy/AmazonElasticFiles
    parameters.tf
    37
    #
    ider.tf
    38
    #

[^95]: I
    # module . eks. module. eks_managed_node_group \["blue"\] . aws_iam_role_policy_attachment. this \["arn : aws : iam: : aws : policy/AmazonEKS_CNI_Policy"\] will be
    estroyed
    # (because module . eks . module . eks_managed_node_group \["blue"\] is not in configuration)
    resource "aws_iam_role_policy_attachment" "this" {
    id
    = "blue-eks-node-group-20240308011906642700000001-20240308011909816700000007" -> null
    policy_arn =
    "arn : aws : iam: : aws : policy/AmazonEKS_CNI_Policy" -> null
    role
    = "blue-eks-node-group-20240308011906642700000001" -> null
    # module . eks . module. eks_managed_node_group \["blue"\] . aws_launch_template. this\[0\] will be destroyed
    #
    (because module . eks . module . eks_managed_node_group \["blue"\] is not in configuration)

[^96]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-eks/03-eks
    $ terraform apply -auto-approve
    Acquiring state lock. This may take a few moments.. .
    data. aws_ssm_parameter . vpc_id: Reading. . .
    data. aws_ssm_parameter . cluster_sg_id: Reading. . .
    data . aws_vpc . default: Reading. . .
    module. eks . data. aws_partition. current: Reading. . .
    data . aws_ssm_parameter . private_subnet_ids: Reading. . .
    module. eks . module. eks_managed_node_group \["green"\]. data. aws_caller_identity . current: Reading. . .
    module . eks . module. kms . data. aws_caller_identity . current \[0\] : Reading. . .
    data. aws_ssm_parameter . node_sg_id: Reading. . .
    module. eks. data. aws_iam_policy_document. assume_role_policy \[0\] : Reading. . .
    module. eks. data. aws_caller_identity . current: Reading. ..
    module. eks . data. aws_partition . current: Read complete after Os \[id=aws\]
    module . eks . module. kms . data. aws_partition . current \[0\]: Reading. . .
    module. eks . data. aws_iam_policy_document . assume_role_policy \[0\]: Read complete after Os \[id=2764486067\]
    module . eks . module. kms . data. aws_partition. current \[0\]: Read complete after Os \[id=aws\]

[^97]: Node groups (2) Info
    Edit
    Delete
    Add node group
    Group name
    Desired size
    AMI release version
    Launch template
    4
    Status V
    O
    blue-2024030801304934670000000e
    N
    1.27.920240227 Update now
    blue-2024030801304730040000000c (1)
    Active
    O
    green-20240308030725422600000009
    2
    1.28.5-20240227
    green-20240308030723740400000007 (1)
    Active

