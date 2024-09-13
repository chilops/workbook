---
title: 55Day_Kubernetes
uuid: ab83b9de-3f3f-11ef-b6cc-26e37c279344
version: 605
created: '2024-07-11T10:10:16+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#f8914d;">**Resources in POD**<!-- {"backgroundCycleColor":"24"} --></mark>

![a05fdef4-be06-486f-8b4f-2afe0a0b6062.png|1034.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/a05fdef4-be06-486f-8b4f-2afe0a0b6062.png) [^1]

\

Restrict pods resources

![0d3593ab-d9a4-46f7-b0ad-e0a1dc0c1843.png|483](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/0d3593ab-d9a4-46f7-b0ad-e0a1dc0c1843.png) [^2]

\

![6ae7f943-7001-4e6f-af71-d23b4331e122.png|978.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/6ae7f943-7001-4e6f-af71-d23b4331e122.png) [^3]

\

git push & pull

![684ea64c-79ac-4673-8904-1ac1f1731e03.png|804](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/684ea64c-79ac-4673-8904-1ac1f1731e03.png) [^4]

\

on workstation

```
kubectl get nodes
```

![80f988b4-2b8d-4dad-a800-038baf353856.png|1055.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/80f988b4-2b8d-4dad-a800-038baf353856.png) [^5]

\

Creating pods by limiting resources

```
kubectl apply -f 06-resources.yaml
```

![32d584ab-826d-4f0d-9d46-b38c17fa1368.png|1057.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/32d584ab-826d-4f0d-9d46-b38c17fa1368.png) [^6]

\

To check if pods are running or not

```
kubectl get pods
```

![99d644fb-2fdd-4538-837e-607675f22305.png|1033.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/99d644fb-2fdd-4538-837e-607675f22305.png) [^7]

\

To see pod full details

```
kubectl describe pod hello-pod
```

![8269a4b1-cc59-441f-815f-289335d67d22.png|1019.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/8269a4b1-cc59-441f-815f-289335d67d22.png) [^8]

\

# <mark style="background-color:#f8914d;">**ConfigMap**<!-- {"backgroundCycleColor":"24"} --></mark>

Its nothing but a key value pair(to store parameters)

![65531205-596f-48fb-9e4e-1dafbc9e88b1.png|631](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/65531205-596f-48fb-9e4e-1dafbc9e88b1.png) [^9]

![393a47f2-3080-4cd0-a175-7af1a5725849.png|685](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/393a47f2-3080-4cd0-a175-7af1a5725849.png) [^10]

\

configMap.yaml

course, trainer -- key

Devops, siva -- value

![8cabad5e-df88-4216-9eac-ffb3a6f19366.png|879](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/8cabad5e-df88-4216-9eac-ffb3a6f19366.png) [^11]

\

Now defining **KeyValuePairs** in a POD

![0a919d9f-c6bc-423f-82f4-a95654868aa7.png|879.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/0a919d9f-c6bc-423f-82f4-a95654868aa7.png) [^12]

\

git push & pull

![71a67fd3-f5d6-41ec-b2f6-2d8f42a96083.png|995.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/71a67fd3-f5d6-41ec-b2f6-2d8f42a96083.png) [^13]

\

First we need to apply ConfigMap

```
kubectl apply -f 07-config-map.yaml
```

![13c09524-8ba1-460a-80b3-d82ce2bbbcb9.png|1083.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/13c09524-8ba1-460a-80b3-d82ce2bbbcb9.png) [^14]

\

```
kubectl get configmaps
```

![3c52b18d-6cd7-4940-8b63-55c206c90cbb.png|1013.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/3c52b18d-6cd7-4940-8b63-55c206c90cbb.png) [^15]

\

```
kubectl describe configmap devops-config
```

![9ff8a769-aa31-44a6-a468-d7f45e7a6feb.png|1012.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/9ff8a769-aa31-44a6-a468-d7f45e7a6feb.png) [^16]

\

Now creating POD to see if ConfigMap applies or not

```
kubectl apply -f 08-pod-config.yaml
```

![ce27ad3d-b6c0-4353-8390-66072425d220.png|967.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/ce27ad3d-b6c0-4353-8390-66072425d220.png) [^17]

\

```
kubectl get pods
```

![f8ef33b5-d181-45b3-b252-d66613c7b43d.png|1107.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/f8ef33b5-d181-45b3-b252-d66613c7b43d.png) [^18]

\

ConfigMap applied

```
kubectl exec -it config-pod -- bash
```

![68b829a2-c4a6-45b0-86b3-ea33bcc43381.png|1061.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/68b829a2-c4a6-45b0-86b3-ea33bcc43381.png) [^19]

\

other way for ConfigMap

![435943db-e440-4f91-983f-9c3c36d5909b.png|1059](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/435943db-e440-4f91-983f-9c3c36d5909b.png) [^20]

\

![fe53853d-f695-493f-b334-75226453e401.png|1001.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/fe53853d-f695-493f-b334-75226453e401.png) [^21]

\

To delete PODS

```
kubectl delete -f 08-pod-config.yaml
```

![21957f52-b498-4503-bc8d-89d2c755358a.png|1111.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/21957f52-b498-4503-bc8d-89d2c755358a.png) [^22]

\

# <mark style="background-color:#f8914d;">**Secrets**<!-- {"backgroundCycleColor":"24"} --></mark>

![56d6afb1-9df0-41fd-a91e-06c14c5410cc.png|694](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/56d6afb1-9df0-41fd-a91e-06c14c5410cc.png) [^23]

\

![](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/10632602-1d44-46bd-8692-4b1556b01352.png) [^24]

\

To decode

![](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/45289484-5201-4140-b15c-1e0ea2cff28a.png) [^25]

\

![e6f53bb0-00b9-4df9-8e75-5b6ff8f741c2.png|1062](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/e6f53bb0-00b9-4df9-8e75-5b6ff8f741c2.png) [^26]

\

![4dfb63db-e0e8-49c1-a426-7dfef2c2c57c.png|1053.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/4dfb63db-e0e8-49c1-a426-7dfef2c2c57c.png) [^27]

\

git push & pull

![4e179634-d288-4b94-8812-f9ac786f7538.png|1053.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/4e179634-d288-4b94-8812-f9ac786f7538.png) [^28]

\

```
kubectl apply -f 09-secrets.yaml
kubectl apply -f 10-pod-secrets.yaml
kubectl exec -it secret-pod -- bash
```

![e686b909-7cf7-43c8-ac59-51a779a828ba.png|1147.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/e686b909-7cf7-43c8-ac59-51a779a828ba.png) [^29]

\

# <mark style="background-color:#f8914d;">**K8s Services**<!-- {"backgroundCycleColor":"24"} --></mark>

![6655c8a3-7cbb-433e-95f8-0d4609aaed34.png|1172.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/6655c8a3-7cbb-433e-95f8-0d4609aaed34.png) [^30]

\

every POD should attach to services

![993ac4ce-c57c-4695-9aaf-786009b2e960.png|446](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/993ac4ce-c57c-4695-9aaf-786009b2e960.png) [^31]

\

# <mark style="background-color:#f8914d;">**Cluster IP service in k8**<!-- {"backgroundCycleColor":"24"} --></mark>

<mark>Purely internal to Kubernetes to communicate between PODS</mark>

![9500d76e-70cb-485a-9e38-0f640786bfe6.png|980.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/9500d76e-70cb-485a-9e38-0f640786bfe6.png) [^32]![](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/8eb5ad7f-e5c1-4bed-902e-04a42a908e78.png) [^33]

\

git push & pull

![2f9640c2-bd5d-4e0f-a37e-7a80749eeeac.png|931](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/2f9640c2-bd5d-4e0f-a37e-7a80749eeeac.png) [^34]

\

```
kubectl apply -f 01-cluster-ip.yaml
kubectl get services
```

![09167773-18a4-4f85-9beb-b17260fd8c5f.png|1140.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/09167773-18a4-4f85-9beb-b17260fd8c5f.png) [^35]

\

ClusterIP is purely internal service to communicate between PODS

```
kubectl get pods
```

![d6846215-4736-441a-8f2b-1386c5d9b6e9.png|1051.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/d6846215-4736-441a-8f2b-1386c5d9b6e9.png) [^36]

\

```
kubectl exec -it hello-pod -- bash
curl 10.100.247.249
```

![71d14cee-5eda-4482-a05e-364096de1245.png|1103.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/71d14cee-5eda-4482-a05e-364096de1245.png) [^37]

![1e9cee17-2cab-41c4-89fa-0394b50cad29.png|1102.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/1e9cee17-2cab-41c4-89fa-0394b50cad29.png) [^38]

![557a73aa-97c8-463a-b03e-37a5a856d470.png|702](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/557a73aa-97c8-463a-b03e-37a5a856d470.png) [^39]

or

![1891d849-1a5c-4d49-a106-b627a5baeaf0.png|993](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/1891d849-1a5c-4d49-a106-b627a5baeaf0.png) [^40]

\

# <mark style="background-color:#f8914d;">**NodePort service in K8**<!-- {"backgroundCycleColor":"24"} --></mark>

<mark>**You can expose PODS to outside world**</mark>

\

![ef9bca32-4124-4406-b2f4-4d835cec48b6.png|1063.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/ef9bca32-4124-4406-b2f4-4d835cec48b6.png) [^41]

\

git push & pull

![7dcd00de-689d-45fb-bbbe-98d82af862eb.png|1107.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/7dcd00de-689d-45fb-bbbe-98d82af862eb.png) [^42]

\

```
kubectl apply -f 02-node-port.yaml
kubectl get service
```

![d4d37618-f08e-4398-9ce7-1733ed8bd6e2.png|1020.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/d4d37618-f08e-4398-9ce7-1733ed8bd6e2.png) [^43]

\

<mark>**If we create NodePort then ClusterIP also by default it creates**</mark>

![c9ec92e8-247a-421c-af5f-4f884a0eb338.png|683](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c9ec92e8-247a-421c-af5f-4f884a0eb338.png) [^44]

\

Now we need to edit security group which is assigned to nodes (then only it will communicate to outside world)

![6b254106-ec1e-4a20-a500-4ae347f72939.png|973](https://images.amplenote.com/e1fadbfa-3e81-11ef-8de4-6ef34fa959ce/6b254106-ec1e-4a20-a500-4ae347f72939.png) [^45]

![639dd2fe-ed34-4033-bd15-474629c16d29.png|1112.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/639dd2fe-ed34-4033-bd15-474629c16d29.png) [^46]

\

Now its communicating to outside world ( Any node will communicate to outside world)

![0f3fd6d4-898e-4607-861b-ccc79071ad93.png|1116.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/0f3fd6d4-898e-4607-861b-ccc79071ad93.png) [^47]

![ed7066a4-b86a-4534-b147-0c1d25c5e3e5.png|1120.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/ed7066a4-b86a-4534-b147-0c1d25c5e3e5.png) [^48]

\

# <mark style="background-color:#f8914d;">**LoadBalancer service in K8**<!-- {"backgroundCycleColor":"24"} --></mark>

![7abcbb1e-bc5b-428d-ad38-126a7b7c69e1.png|938](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/7abcbb1e-bc5b-428d-ad38-126a7b7c69e1.png) [^49]

\

git push & pull

![31d51e08-a74c-4050-925a-ab7fbcf89811.png|1020.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/31d51e08-a74c-4050-925a-ab7fbcf89811.png) [^50]

\

```
kubectl apply -f 03-load-balancer.yaml
```

![5006084f-2bfe-47d4-a462-adc00a14e30d.png|1054.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/5006084f-2bfe-47d4-a462-adc00a14e30d.png) [^51]

\

```
kubectl get svc
```

![8aa46874-b16c-4fce-ad58-a90d5de8c7ac.png|1146.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/8aa46874-b16c-4fce-ad58-a90d5de8c7ac.png) [^52]

![b20aef5c-8691-4544-831c-87f475dae281.png|1147.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/b20aef5c-8691-4544-831c-87f475dae281.png) [^53]

\

load balancer targets (auto created)

![9dc41787-0f04-427c-bf77-b2c5da02f7b8.png|1138.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/9dc41787-0f04-427c-bf77-b2c5da02f7b8.png) [^54]

\

![b8d067b3-7816-4c43-b83e-61a451529a80.png|443](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/b8d067b3-7816-4c43-b83e-61a451529a80.png) [^55]

![72b70446-4bb9-42af-a007-857cd40d670a.png|852](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/72b70446-4bb9-42af-a007-857cd40d670a.png) [^56]

\

![09071afa-ff62-46ab-bebb-05664d703710.png|935.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/09071afa-ff62-46ab-bebb-05664d703710.png) [^57]

\

\

![5e153b66-655e-42af-964a-2efafa184bcd.png|1135.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/5e153b66-655e-42af-964a-2efafa184bcd.png)

\

\

# <mark style="background-color:#f8914d;">**ReplicaSet**<!-- {"backgroundCycleColor":"24"} --></mark> 

Set of Pods is ReplicaSet 

\

![68708d63-ca54-4a74-a6a2-5dc1af73805f.png|885.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/68708d63-ca54-4a74-a6a2-5dc1af73805f.png) [^58]

\

git push & pull

![e1d325b4-e034-4e4a-bc5c-091af6b1753e.png|904](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/e1d325b4-e034-4e4a-bc5c-091af6b1753e.png) [^59]

\

```
kubectl apply -f 01-replica-set.yaml
```

![6017e3f1-2df1-43f9-ba27-bc0a832d5af7.png|1190.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/6017e3f1-2df1-43f9-ba27-bc0a832d5af7.png) [^60]

\

```
Kubectl get replicaset
or 
kubectl get rs
```

![38190dff-3032-4e3a-9613-818877773eb5.png|1192](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/38190dff-3032-4e3a-9613-818877773eb5.png) [^61]

\

```
kubectl get pods
```

![7b8b4e6f-a2aa-49b5-aa18-fadccb60e518.png|1186.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/7b8b4e6f-a2aa-49b5-aa18-fadccb60e518.png) [^62]

\

we can't control random ID

![e57ac976-0970-4ac0-ae8c-f5d22d5fce2a.png|412](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/e57ac976-0970-4ac0-ae8c-f5d22d5fce2a.png) [^63]

\

<mark>ReplicaSet is not useful in changing the version of application. ReplicaSet is only used to maintain the replicas.</mark>

\

![f9319478-820d-4be2-981d-d797eaf282f5.png|321](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/f9319478-820d-4be2-981d-d797eaf282f5.png) [^64]

\

\

# <mark style="background-color:#f8914d;">**DeploymentSet**<!-- {"backgroundCycleColor":"24"} --></mark>

![c45efcdd-98a5-4307-8b6b-ab226a4c27c6.png|708](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c45efcdd-98a5-4307-8b6b-ab226a4c27c6.png) [^65]

\

![be633d83-9419-4ed6-9971-bf402d7ea9ae.png|914](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/be633d83-9419-4ed6-9971-bf402d7ea9ae.png) [^66]

\

git push & pull

![](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/83ec1b46-65f9-4152-ad55-1936e073b547.png) [^67]

\

```
kubectl apply -f 02-deployment-set.yaml
```

```
kubectl get pods
```

![17f2ad51-ebbe-4102-9e08-7036fc077123.png|1087.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/17f2ad51-ebbe-4102-9e08-7036fc077123.png) [^68]

\

```
kubectl get rs
```

![e51682aa-c75a-483c-a89a-0de838c43213.png|1101.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/e51682aa-c75a-483c-a89a-0de838c43213.png) [^69]

![5104dabe-68e5-47d2-bbc4-e927102cdb4b.png|510](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/5104dabe-68e5-47d2-bbc4-e927102cdb4b.png) [^70]

\

Now new version released and apply to production

![c9479d4d-d596-4b41-bf1d-d50a29411620.png|775](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c9479d4d-d596-4b41-bf1d-d50a29411620.png) [^71]

\

git push & pull

![da73df26-0262-41c2-8e64-a003a1fc8bc6.png|898](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/da73df26-0262-41c2-8e64-a003a1fc8bc6.png) [^72]

\

```
kubectl apply -f 02-deployment-set.yaml
kubectl get pods
```

![876fec99-d8b7-4953-877b-3e93745731d5.png|1111.3333740234375](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/876fec99-d8b7-4953-877b-3e93745731d5.png) [^73]

\

at any point of time 3 pods will run

![9a49d034-a26d-4bb3-9038-c58dd442b647.png|780](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/9a49d034-a26d-4bb3-9038-c58dd442b647.png) [^74]

\

\

DeploymentSet deletes old ReplicaSet & pods once new ReplicaSet & pods created <mark>**( This is also called ROLLING Update)**</mark>

![bfcca94f-4339-4c9b-9979-dfcf5686ac5b.png|899](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/bfcca94f-4339-4c9b-9979-dfcf5686ac5b.png) [^75]

[^1]: VM vs containerisation
    VM --> 2GB 2CPU --> resources are blocked irrespective of usage
    containerisation --> containers don't block resources, they are used dynamically
    1 VM --> roboshop containers/pods, amazon containers/pods
    traffic increased/code caused more resources to consume
    VM will be blocked by a single container
    we can restrict the resources consumed by containers...

[^2]: spec:
    containers :
    - name: app
    image: images. my-company . example/app: v4
    resources:
    requests:
    memory: "64Mi"
    cpu: "250m"
    limits :
    memory: "128Mi"
    cpu: $'500m"
    - name: log-aggregator
    image: images.my-company . example/log-aggregator: v6
    resources :
    requests:
    memory: "64Mi"
    cpu: "250m"
    limits :
    memory: "128Mi"
    cpu: "500m"

[^3]: REPOS
    k8-resources > 02-pods > ! 06-resources.yaml > {} spec > \[ \] containers > {} 0 > {} resources > {} limits >
    Lalalogue-ueploy
    1
    apiVersion: v1
    >
    concepts
    2
    kind: Pod
    > dockerfiles
    3
    metadata :
    > k8-eksctl
    4
    name: hello-pod
    k8-resources
    5
    namespace: roboshop
    > 01-namespace
    6
    spec :
    7
    02-pods
    # list of containers
    8
    containers :
    ! 01-pod.yaml
    M
    9
    - name: hello-pod
    ! 02-multi-container.yaml
    10
    image: nginx
    03-labels.yaml
    11
    #here with this line port will not be opened, just for information
    ! 04-annotations.yaml
    12
    ports :
    ! 05-env.yaml
    13
    - containerPort: 80
    14
    ! 06-resources.yaml
    U
    resources :
    15
    requests :
    > learn-git
    16
    cpu: "100m"
    > learn-jenkins
    17
    memory : "68Mi"
    > notes
    18
    limits :
    > roboshop-ansible
    19
    H
    cpu: "200m"
    > roboshop-ansible-roles
    20
    memory :
    "128Mi"

[^4]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksctl (main)
    $ cd ../k8-resources/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main Oedf15e\] jenkins
    2 files changed, 21 insertions (+)

[^5]: 44 . 211 . 173. 150 \| 172. 31.94.147 \| t2. micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-192-168-25-136. ec2. internal
    Ready
    <none>
    17m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-59-29. ec2 . internal
    Ready
    <none>
    17m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-8-178. ec2 . internal
    Ready
    <none>
    17m
    v1 .27.9-eks-5eOfdde
    44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| null
    \[ centos@ip-172-31-94-147 \~ \]$ git clone https: //github.com/daws-76s/k8-resources .git
    Cloning into 'k8-resources' . .
    remote: Enumeratiog objects: 45, done.
    remote: Counting objects: 100% (45/45) , done.
    remote: Compressing objects: 100% (30/30) , done.
    remote: Total 45 (delta 14) , reused 42 (delta 11) , pack-reused 0
    Receiving objects: 1008 (45/45) , 4. 07 KiB \| 4. 07 MiB/s, done

[^6]: 44 . 211 . 173. 150 \| 172. 31 .94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl apply -f 06-resources . yaml
    pod/hello-pod created

[^7]: 44 . 211 . 173. 150 \| 172 . 31 . 94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    0
    6s

[^8]: 44 . 211 . 173. 150 \| 172 . 31 . 94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl describe pod hello-pod
    Name :
    hello-pod
    Namespace :
    default
    Priority :
    0
    Service Account:
    default
    Node :
    ip-192-168-25-136. ec2. internal/192 . 168.25.136
    Start Time:
    Fri, 23 Feb 2024 01:59:41 +0000
    Labels :
    <none>
    Annotations :
    <none>
    Status :
    Running
    IP:
    192 . 168 . 23. 186
    IPS :
    IP: 192.168 .23. 186
    Containers :
    I
    hello-pod:
    Container ID:
    containerd: / /35192e8c58d111dbbfa7c1525a629557f54c0f27494aa8115943de94804a9103
    Image :
    nginx
    Image ID:
    docker . io/library/nginx@sha256: c26ae7472d624balfafd296e73cecc4f93f853088e6a9c13c0d52f6ca586
    Port:
    80/TCP
    Host Port:
    0/TCP
    State:
    Running
    Started:
    Fri, 23 Feb 2024 01:59: 45 +0000
    Ready :
    True
    Restart Count:
    0
    Limits :
    cpu :
    200m
    memory :
    128Mi
    Requests :
    cpu :
    100m

[^9]: configuration store
    secrets store
    C

[^10]: ConfigMaps
    A ConfigMap is an API object used to store non-confidential data in key-value pairs. Pods can
    consume ConfigMaps as environment variables, command-line arguments, or asconfiguration files
    in a volume.
    A ConfigMap allows you to decouple environment-specific configuration from your container images
    , so that your applications are easily portable.
    Caution: ConfigMap does not provide secrecy or encryption. If the data you want to store are
    confidential, use a Secret rather than a ConfigMap, or use additional (third party) tools to keep
    your data private.

[^11]: REPOS
    k8-resources > 02-pods > ! 07-config-map.yaml > {} da
    aockermes
    apiVersion: v1
    > k8-eksctl
    2
    kind: ConfigMap
    k8-resources
    3
    metadata:
    > 01-namespace
    4
    name: devops-config
    02-pods
    5
    data :
    6
    E
    08-pod-d
    course : Devops
    7
    trainer: "SivakumarReddy"
    ! 01-pod.yaml
    ! 02-multi-container.yaml
    ! 03-labels.yaml
    ! 04-annotations.yaml
    ! 05-env.yaml
    06-resources.yaml
    ! 07-config-map.yaml
    U

[^12]: V REPOS
    k8-resources > 02-pods > ! 08-pod-config.yaml > {} spec > \[ \] containers > {} 0 > \[ \]env > {} 1> {} v
    aockermes
    > k8-eksctl
    3
    metadata :
    4
    k8-resources
    name: config-pod
    15
    namespace: roboshop
    > 01-namespace
    6
    spec :
    02-pods
    7
    # list of containers
    ! 01-pod.yaml
    18
    containers :
    ! 02-multi-container.yaml
    9
    name: config-pod
    ! 03-labels.yaml
    10
    image: nginx
    ! 04-annotations.yaml
    11
    #here with this line port will not be opened, just for information
    12
    ! 05-env.yaml
    ports :
    13
    - containerPort: 80
    ! 06-resources.yaml
    14
    env :
    ! 07-config-map.yaml
    U
    15
    name: course
    ! 08-pod-config.yaml
    U
    16
    valueFrom:
    > learn-git
    17
    configMapKeyRef :
    > learn-jenkins
    18
    name: devops-config
    19
    > notes
    key: course
    20
    name: trainer
    > roboshop-ansible
    21
    valueFrom:
    > roboshop-ansible-roles
    22
    configMapKeyRef :
    > roboshop-ansible-roles-tf
    23
    name: devops-config
    > roboshop-docker
    24
    key: trainer

[^13]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 5 (delta 1), reused 5 (delta 1) , pack-reused 0

[^14]: 44 . 211 . 173. 150 \| 172. 31. 94. 147 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl apply -f 07-config-map. yaml
    configmap/devops-config created

[^15]: 44 . 211 . 173. 150 \| 172. 31.94.147 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl get configmaps
    NAME
    DATA
    AGE
    devops-config
    2
    6s
    kube-root-ca . crt
    1
    4 3m

[^16]: 44 . 211 . 173. 150 \| 172 . 31 . 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl describe configmap devops-config
    Name:
    devops-config
    Namespace :
    default
    Labels :
    <none>
    Annotations :
    <none>
    Data
    course :
    Devops
    trainer :
    SivakumarReddy
    BinaryData
    Events :
    <none>

[^17]: 44 . 211 . 173.150 \| 172. 31. 94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl apply -f 08-pod-config . yaml
    pod/config-pod created

[^18]: 44 . 211 . 173. 150 \| 172. 31. 94. 147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    config-pod
    1/1
    Running
    0
    6s
    hello-pod
    1/1
    Running
    10m

[^19]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl exec -it config-pod -- bash
    root@config-pod: /# env
    KUBERNETES SERVICE PORT HTTPS=443
    KUBERNETES SERVICE PORT=443
    HOSTNAME=config-pod
    PWD=/
    PKG RELEASE=1\~bookworm
    HOME=/ root
    KUBERNETES PORT 443 TCP=tcp: / /10 . 100 . 0 . 1: 443
    NJS VERSION=0 . 8 .3
    TERM=xterm
    SHLVL=1
    trainer=SivakumarReddy
    KUBERNETES PORT 443 TCP PROTO=tcp
    KUBERNETES PORT 443 TCP ADDR=10 . 100 .0.1
    KUBERNETES SERVICE HOST=10 . 100 .0.1
    KUBERNETES PORT=top : / /10 . 100 .0 . 1: 443
    KUBERNETES PORT 443 TCP PORT=443
    PATH=/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin
    NGINX VERSION=1 . 25 . 4
    course=Devops
    =/usr/bin/env

[^20]: 29
    spec :
    30
    # list of containers
    31
    containers :
    32
    name: config-pod-1
    33
    image: nginx
    34
    #here with this line port will not be opened, just for information
    35
    ports :
    36
    -
    containerPort: 80
    37
    envFrom :
    38
    -
    configMapRef :
    39
    name: devops-config

[^21]: 44 . 211 . 173. 150 \| 172. 31 . 94. 147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl apply -f 08-pod-config. yaml
    pod/config-pod unchanged
    pod/config-pod-1 created
    44 . 211 . 173. 150 \| 172 . 31. 94.147 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl exec -it config-pod-1 -- bash
    root@config-pod-1:/# env
    KUBERNETES SERVICE PORT HTTPS=443
    KUBERNETES SERVICE PORT=443
    HOSTNAME=config-pod-1
    PWD=/
    PKG RELEASE=1\~bookworm
    HOME=/ root
    KUBERNETES PORT 443_TCP=tcp: //10 . 100 .0.1:443
    NJS VERSION=0 . 8.3
    TERM=xterm
    SHLVL=1
    trainer=SivakumarReddy
    KUBERNETES PORT 443 TCP PROTO=top
    KUBERNETES PORT 443 TCP ADDR=10 . 100.0.1
    KUBERNETES SERVICE HOST=10 . 100 .0.1
    KUBERNETES PORT=top : / /10 . 100 . 0 .1: 443
    KUBERNETES PORT 443 TCP PORT=443
    PATH=/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin
    NGINX VERSION=1 . 25 . 4
    course=Devops
    =/usr/bin/env
    root@config-pod-1:/#

[^22]: 44 . 211 . 173. 150 \| 172. 31 .94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl delete -f 08-pod-config. yaml
    pod "config-pod" deleted
    pod "config-pod-1" deleted

[^23]: Secrets
    A Secret is an object that contains a small amount of sensitive data such as a password, a token, or a
    key. Such information might otherwise be put in a Pod specification or in a container image. Using a
    Secret means that you don't need to include confidential data in your application code.
    Because Secrets can be created independently of the Pods that use them, there is less risk of the
    Secret (and its data) being exposed during the workflow of creating, viewing, and editing Pods.
    Kubernetes, and applications that run in your cluster can also take additional precautions with
    Secrets, such as avoiding writing sensitive data to nonvolatile storage.
    Secrets are similar to ConfigMaps but are specifically intended to hold confidential data.

[^24]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ echo -n "admin" \| base64
    I
    YWR taW4=
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ echo -n "admin123" \| base64
    YWR taw4XMjM=

[^25]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    S echo -n "YWRtaW4xMjM=" \| base64 --decode
    admin123
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    S

[^26]: REPOS
    k8-resources > 02-pods > ! 09-secrets.yaml > {} data > ><
    k8-resources
    1
    apiVersion: v1
    UI-namespace
    2
    kind: Secret
    02-pods
    metadata:
    E
    10-pod-secrets.y
    4
    name: devops- secret
    ! 01-pod.yaml
    15
    type: Opaque
    ! 02-multi-container.yaml
    6
    data:
    7
    username: YWRtaW4=
    ! 03-labels.yaml
    8
    password: YWRtaW4xMjM=
    ! 04-annotations.yaml
    ! 05-env.yaml
    ! 06-resources.yaml
    ! 07-config-map.yaml
    ! 08-pod-config.yaml
    ! 09-secrets.yaml
    U

[^27]: EXPLORER
    . .
    ! 07-config-map.yaml
    ! 08-pod-config.yaml
    ! 09-secrets.yaml U
    ! 10-pod-secrets.ya
    REPOS
    k8-resources > 02-pods > ! 10-pod-secrets.yaml > {} spec > \[ \] containers > { } 0 > \[ \]envFrom > {} 0 > {}
    k8-resources
    apiVersion: v1
    UI-namespace
    2
    kind: Pod
    02-pods
    3
    metadata:
    ! 01-pod.yaml
    4
    name: secret-pod
    ! 02-multi-container.yaml
    5
    spec :
    ! 03-labels.yaml
    6
    # list of containers
    7
    ! 04-annotations.yaml
    containers :
    8
    name: secret-pod
    ! 05-env.yaml
    9
    image: nginx
    06-resources.yaml
    10
    #here with this line port will not be opened, just for information
    ! 07-config-map.yaml
    11
    ports :
    ! 08-pod-config.yaml
    12
    containerPort: 80
    ! 09-secrets.yaml
    U
    13
    envFrom :
    ! 10-pod-secrets.yaml
    14
    U
    secretRef:
    15
    name: devops-secret
    learn-git

[^28]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 5 (delta 1) , reused 5 (delta 1) , pack-reused 0
    Unpacking objects: 100% (5/5) , 652 bytes \| 652.00 KiB/s, done.
    From https: / /github. com/daws-76s/k8-resources
    e93b5b2. . b57752f main
    -> origin/main
    Updating e93b5b2. . b57752f

[^29]: 44 . 211 . 173. 150 \| 172. 31 . 94.147 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl apply -f 09-secrets . yaml
    secret/devops-secret created
    44 . 211 . 173. 150 \| 172. 31 . 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/8-resources/02-pods \]$ kubectl apply -f 10-pod-secrets . yaml
    pod/secret-pod created
    44 . 211 . 173. 150 \| 172. 31. 94. 147 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ kubectl exec -it secret-pod -- bash
    root@secret-pod: /# env
    KUBERNETES SERVICE PORT HTTPS=443
    KUBERNETES SERVICE PORT=443
    HOSTNAME=secret-pod
    PWD=/
    PKG RELEASE=1\~bookworm
    HOME=/root
    KUBERNETES PORT 443_TCP=tcp: //10 . 100 . 0 . 1: 443
    NJS VERSION=0 . 8.3
    TERM=xterm
    username=admin
    SHLVL=1
    KUBERNETES PORT 443 TCP PROTO=tcp
    KUBERNETES PORT 443_TCP ADDR=10 . 100.0.1
    password=admin123
    KUBERNETES SERVICE HOST=10 . 100 .0.1
    KUBERNETES PORT=top : / /10 . 100 .0 . 1:443
    KUBERNETES PORT 443 TCP PORT=443
    PATH=/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin
    NGINX VERSION=1 . 25 . 4

[^30]: Services
    if you want to expose pods to other applications or outside we must use services..
    1. expose to other apps or outside world
    2. load balancing
    3. service mesh
    1. Cluster IP --> purely internal to kubernets
    2. NodePort --> you can expose to outside world
    3. LoadBalancer --> you can expose to outside world

[^31]: Service
    Pod
    names as DNS

[^32]: REPOS
    k8-resources > service > ! 01-cluster-ip.yaml > {} metadata > @ name
    > .github
    1
    apiVersion: v1
    > ansible
    2
    kind: Pod
    3
    > catalogue
    metadata :
    4
    name: nginx-pod
    > catalogue-deploy
    5
    labels :
    > concepts
    6
    app: nginx
    > dockerfiles
    7
    demo: service
    > k8-eksctl
    8
    spec:
    I
    k8-resources
    9
    # list of containers
    10
    > 01-namespace
    containers :
    11
    > 02-pods
    - name : nginx-pod
    12
    image : nginx
    service
    13
    #here with this line port will not be opened, just for information
    ! 01-cluster-ip.yaml
    U
    14
    ports:
    > learn-git
    15
    - containerPort: 80
    > learn-jenkins
    16
    notes
    17
    apiVersion: v1
    18
    > roboshop-ansible
    kind: Service
    19
    metadata:
    > roboshop-ansible-roles
    20
    name: nginx-service
    > roboshop-ansible-roles-tf
    21
    spec :
    > roboshop-docker
    22
    selector :
    > roboshop-documentation
    23
    app: nginx
    > OUTLINE
    24
    demo: service

[^33]: 25
    ports :
    26
    -
    protocol: TCP
    27
    port: 80 #service-port
    28
    targetPort: 80 #container-port

[^34]: \[ centos@ip-172-31-94-147 \~/k8-resources/02-pods \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 4 (delta 0) , reused 4 (delta 0) , pack-reused 0
    Unpacking objects: 100% (4/4), 567 bytes \| 567.00 KiB/s, done.
    laitbub

[^35]: 44 . 211 . 173. 150 \| 172. 31.94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl apply -f 01-cluster-ip. yaml
    pod/nginx-pod created
    service/nginx-service created
    44 . 211 . 173. 150 \| 172. 31.94.147 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl get services
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    67m
    nginx-service
    ClusterIP
    10 . 100 .247 .249
    <none>
    80/TCP
    8s

[^36]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https : / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pol
    1/1
    Running
    0
    33m
    nginx-pod
    1/1
    Running
    26s
    secret-pod
    1/1
    Running
    12m

[^37]: 44 . 211 . 173. 150 \| 172 . 31 .94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl get services
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    67m
    nginx-service
    ClusterIP
    10. 100.247.249
    <none>
    80/TCP
    8s
    44 . 211 . 173.150 \| 172 . 31. 94. 147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    0
    33m
    nginx-pod
    1/1
    Running
    26s
    secret-pod
    1/1
    Running
    12m
    44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl exec -it hello-pod -- bash
    root@hello-pod: /# curl 10.100.247.249

[^38]: 44 . 211 . 173. 150 \| 172. 31.94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl exec -it hello-pod -- bash
    root@hello-pod: /# curl 10. 100.247.249
    <! DOCTYPE html>
    html>
    Khead>
    title>Welcome to nginx!</title>
    <style>
    html { color-scheme: light dark; }
    body { width: 35em; margin: 0 auto;
    font-family: Tahoma, Verdana, Arial, sans-serif; }
    </style>
    </head>
    body>
    Kh1>Welcome to nginx!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required. </p>
    <p>For online documentation and support please refer to
    Ka href="http://nginx. org/">nginx. org</a>.<br/>
    Commercial support is available at
    Ka href="http://nginx. com/">nginx. com</a> .</p>
    <p><em>Thank you for using nginx.</em></p>
    </body>
    </html>
    ot @hell

[^39]: pod-2
    Service
    Pod
    names as DNS
    80
    8080

[^40]: root@hello-pod: /# curl nginx-service
    <!DOCTYPE html>
    html>
    head>
    title>Welcome to nginx!</title>
    Kstyle>
    html { color-scheme: light dark; }
    body { width: 35em; margin: 0 auto;
    font-family: Tahoma, Verdana, Arial, sans-serif; }
    </style>
    </head>
    <body>
    Kh1>Welcome to nginx!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required. </p>
    <p>For online documentation and support please refer to
    ka href="http: / /nginx. org/">nginx. org</a>.<br/>
    Commercial support is available at
    ka href="http: //nginx. com/">nginx. com</a>.</p>
    <p><em>Thank you for using nginx.</em></p>
    </body>
    </html>

[^41]: EXPLORER
    . . .
    Imi
    ! 09-secrets.yaml
    ! 10-pod-secrets.yaml
    ! 01-cluster-ip.yaml
    ! 02-node-por
    V REPOS
    k8-resources > service > ! 02-node-port.yaml > {} spec > @type
    .ginup
    metadata:
    I W
    > ansible
    7
    > catalogue
    demo: service
    8
    spec :
    > catalogue-deploy
    9
    # list of containers
    > concepts
    10
    containers:
    > dockerfiles
    11
    name : nginx-nodeport
    > k8-eksctl
    12
    image: nginx
    k8-resources
    13
    #here with this line port will not be opened, just for information
    > 01-namespace
    14
    ports :
    15
    containerPort: 80
    > 02-pods
    16
    service
    17
    apiVersion: v1
    ! 01-cluster-ip.yaml
    18
    kind: Service
    ! 02-node-port.yaml
    U
    19
    metadata :
    > learn-git
    20
    name: nginx-nodeport
    > learn-jenkins
    21
    spec :
    22
    type: NodePort
    > notes
    23
    selector :
    > roboshop-ansible
    24
    app: nginx-nodeport
    > roboshop-ansible-roles
    25
    demo: service
    > roboshop-ansible-roles-tf
    26
    ports :
    > roboshop-docker
    27
    protocol: TCP
    28
    port: 80 #service-port
    OUTLINE
    29
    targetPort: 80 #container-port
    TIMELINE

[^42]: 44 . 211 . 173. 150 \| 172. 31.94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6), done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0

[^43]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    84m
    nginx-1b
    LoadBalancer
    10 . 100 . 110 . 10
    a463dc449ae5c4180b7712d27c9ad54a-639817758. us-east-1. elb. amazonaws . com
    80: 31197/TCP
    6s
    nginx-nodeport
    NodePort
    10 . 100 . 100.108
    <none>
    80: 30133/TCP
    12m
    nginx-service
    ClusterIP
    10 . 100 .247.249
    <none>
    80/TCP
    17m

[^44]: 30133
    30133
    Cluster IP
    Pod
    to
    Actor
    30133
    NADES

[^45]: Instances (4) Info
    G
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    Instance state = running
    X
    Clear filters
    >
    Name
    Instance ID
    Instance state
    Instance type v Status check
    Alarm status
    Availability
    O
    workstation-eksctl
    i-080ed32fOdd303fef
    Running Q Q
    t2.micro
    2/2 checks passed View alarms +
    us-east-1a
    roboshop-spot-Node
    i-Ofb5f6f7ed9c1b5fb
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1c
    roboshop-spot-Node
    i-03b1bafcoe23a6e2f
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1b
    roboshop-spot-Node
    i-0391793290010a63e
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1b

[^46]: Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info
    Port range
    Source Info
    Description - optional Info
    Info
    sgr-033foff61263e7d89
    All traffic
    All
    All
    Custom
    Q
    Delete
    sg-Of1fb09ff64cee43f X
    sgr-0972343e0b9886804
    All traffic
    All
    All
    Custom
    V
    Q
    Allow unmanaged nodes to co
    Delete
    Allow unmanaged nodes to
    sg-0302711604eabObed X
    communicate with control plane (all
    ports)
    All TCP
    TCP
    0 - 65535
    Anyw...
    V
    Q 0.0.0.0/0
    Delete
    0.0.0.0/0 X
    Add rule
    A Rules with source of 0.0.0.0/0 or :/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only.
    X
    Cancel
    Preview changes
    Save rules

[^47]: SecurityGroup \| EC2 \| us-e X \| SecurityGroups \| EC2 \| us. x \| roboshop \| Clusters \| Els:' x \| / k&.drawio - draw.io
    \* \| Service \| Kubernetes
    x )daws-765/k8-resources
    X
    Welcome to nginx!
    X
    A Not secure 34.229.160.13:30133
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx

[^48]: v
    Instances \| EC2 \| us-east-1
    x \| SecurityGroups \| EC2 \| us-east- x \| roboshop \| Clusters \| Elastic Ku: x \| i k8.drawio - drawjo
    x Service \| Kubernetes
    x () daws-
    A Not secure
    54.164.4.15:30133
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^49]: REPOS
    k8-resources > service > ! 03-load-balancer.yaml > { } spec > {
    anisivie
    8
    spec:
    > catalogue
    10
    containers :
    > catalogue-deploy
    11
    name: nginx-1b
    > concepts
    15
    -
    containerPort: 80
    > dockerfiles
    16
    > k8-eksctl
    17
    apiVersion: v1
    k8-resources
    18
    kind: Service
    > 01-namespace
    19
    metadata:
    20
    > 02-pods
    name: nginx-1b
    21
    spec:
    service
    22
    type: LoadBalancer
    ! 01-cluster-ip.yaml
    23
    selector :
    ! 02-node-port.yaml
    24
    app: nginx-1b
    ! 03-load-balancer.yaml
    U
    25
    demo: service
    > learn-git
    26
    ports :
    > learn-jenkins
    27
    protocol: TCP
    28
    port: 80 #service-port
    > notes
    29
    targetPort: 80 #container-port
    > roboshop-ansible

[^50]: 44 . 211 . 173. 150 \| 172 . 31 . 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4) , 603 bytes \| 603.00 KiB/s, done.
    From https: / /github. com/daws-76s/k8-resources
    0490697
    1 48abfe

[^51]: 44 . 211 . 173. 150 \| 172. 31 .94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl apply -f 03-load-balancer. yaml
    pod/nginx-1b created
    service/nginx-1b created

[^52]: 44 . 211 . 173. 150 \| 172. 31.94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources. git
    \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    kubernetes
    ClusterIP
    10 . 100 .0.1
    <none>
    443/TCP
    84m
    nginx-1b
    LoadBalancer
    10 . 100 .110 .10
    a463dc449ae5c4180b7712d27c9ad54a-639817758. us-east-1. elb. amazonaws . com
    80: 31197/TO
    6s
    nginx-nodeport
    NodePort
    10 . 100. 100.108
    <none>
    80: 30133/TC
    12m
    nginx-service
    ClusterIP
    10. 100 .247.249
    <none>
    80/TCP
    17m

[^53]: aws
    Services
    Q Search
    \[Alt+S\]
    A
    N. Virginia
    CO
    VPC
    3O RDS
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    EFS
    25 LAM
    9 EC2
    Certificate Manager
    CloudFront
    Billing and Cost Management
    Images
    EC2 > Load balancers
    AMIs
    AMI Catalog
    Load balancers (1/1)
    G
    Actions
    Create load balancer
    Elastic Block Store
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Volumes
    Q Filter load balancers
    1
    Snapshots
    Lifecycle Manager
    Name
    v
    DNS name
    State
    4
    VPC ID
    Availability Zones
    4
    Type
    Network & Security
    V
    a463dc449ae5c4180b...
    a463dc449ae5c418067712d27c9ad54...
    vpc-Occ7e88c3be717f87
    2 Availability Zones
    class
    Security Groups

[^54]: Listeners
    Network mapping
    Security
    Health checks
    Target instances
    Monitoring
    Attributes
    Tags
    Target instances (3)
    Connection draining: Off
    G
    Deregister
    Manage instances
    Instances currently registered to your load balancer are displayed. To deregister instances, select them, then choose Deregister. To register and deregister instances simultaneously, choose Manage instances.
    Q Filter target instances
    < 1
    0
    Instance ID
    Name
    4
    Health status
    V
    Health status descri...
    Security groups
    0
    hi-Ofb5f6f7ed9c1b5fb
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542
    O
    -03b1bafcoe23a6e2f
    oboshop-spot-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542
    O
    -0391793290010a63e
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-5427

[^55]: LoadBalancer
    NodePort
    Cluster IP

[^56]: 30133
    31197
    LB
    30133
    Cluster IP
    Pod
    31197
    Actor
    31197
    30133

[^57]: F
    X
    3463dc449ae5c418067712d27c9ad54a-639817758.us-east-1.elb.amazonaws.com
    Welcome to nginx!
    If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.
    For online documentation and support please refer to nginx.org.
    Commercial support is available at nginx.com.
    Thank you for using nginx.

[^58]: REPOS
    k8-resources > sets > ! 01-replica-set.yaml > @apiVersion
    > ansible
    1
    apiVersion: apps/v1
    > catalogue
    2
    kind: ReplicaSet
    3
    > catalogue-deploy
    metadata:
    4
    name : nginx-rs
    > concepts
    5
    labels :
    > dockerfiles
    6
    app: nginx
    > k8-eksctl
    7
    tier: frontend
    k8-resources
    8
    spec:
    > 01-namespace
    9
    # modify replicas according to your case
    > 02-pods
    10
    replicas: 3
    11
    selector: # . replica-set labels
    > service
    12
    matchLabels :
    V
    sets
    13
    app: nginx
    ! 01-replica-set.yaml
    U
    14
    tier: frontend
    > learn-git
    15
    template: # pod-definition
    > learn-jenkins
    16
    metadata:
    > notes
    17
    labels :
    18
    > roboshop-ansible
    app: nginx
    19
    tier: frontend
    > roboshop-ansible-roles
    20
    spec :
    > roboshop-ansible-roles-tf
    21
    containers :
    > roboshop-docker
    22
    name: nginx
    > roboshop-documentation
    23
    image: nginx
    OUTLINE
    24

[^59]: \[ centos@ip-172-31-94-147 \~/k8-resources/service \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (2/2) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1), pack-reused 0
    Unpacking objects: 100% (4/4) , 501 bytes \| 501.00 KiB/s, done.
    From https: //github. com/daws-76s/k8-resources

[^60]: 44 . 211 . 173. 150 \| 172 . 31. 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/8-resources/service \]$ cd . ./sets/
    44 . 211 . 173.150 \| 172 . 31.94. 147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl apply -f 01-replica-set. yaml
    replicaset . apps/nginx-rs created

[^61]: 44 . 211 . 173. 150 \| 172 . 31. 94.147 \| t2. micro \| https: //github. com/daws-76s/k8-resou
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl get rs
    NAME
    DESIRED
    CURRENT
    READY
    AGE
    nginx-rs
    3
    3
    5s

[^62]: 44 . 211 . 173. 150 \| 172. 31 . 94.147 \| t2. micro \| https: //github. com/daws-76s/k8-resources. git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    O
    68m
    nginx-rs-c17q2
    1/1
    Running
    0
    17s
    nginx-rs-mgdmx
    1/1
    Running
    16s
    nginx-rs-zrwhk
    1/1
    Running
    16s
    secret-pod
    1/1
    Running
    O
    46m

[^63]: nginx-rs-<random-id>

[^64]: catalogue : 1 . 0.0
    catalogue : 1 . 2 . 0

[^65]: catalogue : 1. 0.0
    catalogue : 1 . 2. 0
    cluster-ip < node-port < load-balancer
    pod < replicaset < deployment

[^66]: V REPOS
    k8-resources > sets > ! 02-deployment-set.yaml > map
    anisivie
    1
    apiversion: apps/v1
    > catalogue
    2
    kind: Deployment
    > catalogue-deploy
    3 v metadata:
    > concepts
    4
    name: nginx-deployment
    > dockerfiles
    5
    labels :
    > k8-eksctl
    6
    app: nginx
    7
    demo: deployment
    V k8-resources
    8
    V
    spec :
    > 01-namespace
    9
    .replicas: 3
    > 02-pods
    10
    V
    . selector :
    > service
    11 v
    matchLabels:
    V sets
    12
    app: nginx
    ! 01-replica-set.yaml
    13
    demo: deployment
    14
    V
    ! 02-deployment-set.yaml
    U
    template :
    15
    V
    metadata:
    > learn-git
    16
    V
    labels :
    > learn-jenkins
    17
    app: nginx
    > notes
    18
    demo: deployment
    > roboshop-ansible
    19
    spec :
    > roboshop-ansible-roles
    20
    containers :
    > roboshop-ansible-roles-tf
    21
    V
    name: nginx
    22
    image: nginx : 1. 14.2
    > roboshop-docker
    23
    V
    ports :
    > OUTLINE
    24
    - containerPort: 80

[^67]: 44 . 211. 173. 150 \| 172. 31. 94. 147 \| t2. micro \| https: //github. com/da
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0

[^68]: 44 . 211 . 173. 150 \| 172. 31.94. 147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl apply -f 02-deployment-set. yaml
    deployment . apps/nginx-deployment created
    44 . 211 . 173. 150 \| 172 . 31. 94.147 \| t2. micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    73m
    nginx-deployment-5ff5b64b7d-88jcc
    1/1
    Running
    7s
    nginx-deployment-5ff5b64b7d-g88zh
    1/1
    Running
    7s
    nginx-deployment-5ff5b64b7d-xmjig
    1/1
    Running
    7s
    nginx-rs-c17q2
    1/1
    Running
    5m42s
    nginx-rs-mgamx
    1/1
    Running
    5m41s
    oooo
    nginx-rs-zrwhk
    1/1
    Running
    5m41s
    secret-pod
    1/1
    Running
    52m

[^69]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl get rs
    NAME
    DESIRED
    CURRENT
    READY
    AGE
    nginx-deployment-5ff5b64b7d
    3
    3
    21s
    W W
    nginx-rs
    3
    W
    5m56s

[^70]: DS
    RS
    pod
    pod
    osgood

[^71]: EXPLORER
    . . .
    )2-node-port.yaml
    ! 03-load-balancer.yaml
    V REPOS
    k8-resources > sets > ! 02-deployment-set.yaml > {} spec
    anisivie
    3
    metadata:
    > catalogue
    5
    labels :
    > catalogue-deploy
    8
    spec :
    > concepts
    9
    replicas: 3
    > dockerfiles
    10
    selector:
    > k8-eksctl
    11
    matchLabels:
    k8-resources
    12
    app: nginx
    > 01-namespace
    13
    demo: deployment
    > 02-pods
    14
    template:
    15
    metadata:
    > service
    16
    labels :
    V sets
    17
    app: nginx
    ! 01-replica-set.yaml
    18
    demo: deployment
    ! 02-deployment-set.yaml
    M
    19
    spec :
    > learn-git
    20
    containers :
    > learn-jenkins
    21
    name: nginx
    22
    >
    image: nginx
    notes
    23
    ports :
    > roboshop-ansible
    I
    24
    - containerPort: 80
    > roboshop-ansible-roles
    25
    > roboshop-ansible-roles-tf

[^72]: 44 . 211 . 173. 150 \| 172. 31. 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-reso
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (1/1), done.
    remote: Total 4 (delta 3) , reused 4 (delta 3) , pack-reused 0
    Unpacking objects: 100% (4/4) , 314 bytes \| 314.00 KiB/s, done.
    From https: //github.com/daws-76s/k8-resources

[^73]: 44 . 211 . 173. 150 \| 172 . 31. 94.147 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    7 6m
    nginx-deployment-5c9bf7649d-d2t56
    0/1
    ContainerCreating
    1s
    nginx-deployment-5c9bf7649d-rwomp
    1/1
    Running
    4s
    nginx-deployment-5c9bf7649d-v51n6
    1/1
    Running
    2s
    nginx-deployment-5ff5b64b7d-g88zh
    1/1
    Running
    2m25s
    nginx-deployment-5ff5b64b7d-xmjig
    0/1
    Terminating
    2m25s
    nginx-rs-c17q2
    1/1
    Running
    8m
    nginx-rs-mgamx
    1/1
    Running
    7m59s
    nginx-rs-zrwhk
    1/1
    Running
    7m59s
    secret-pod
    1/1
    Running
    54m
    44 . 211 . 173.150 \| 172. 31. 94.147 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-147 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    0
    76m
    nginx-deployment-5c9bf 7649d-d2t56
    1/1
    Running
    0
    12s
    nginx-deployment-5c9bf7649d-rwpmp
    1/1
    Running
    15s
    nginx-deployment-5c9bf7649d-v51n6
    1/1
    Running
    13s
    nginx-rs-cl7q2
    1/1
    Running
    8m11s
    nginx-rs-mgamx
    1/1
    Running
    8m10s
    nginx-rs-zrwhk
    1/1
    Running
    8m10s
    secret-pod
    1/1
    Running
    54m

[^74]: DS
    RS
    RS-2
    pod
    pod
    pod
    pod

[^75]: DS
    RS
    RS-2
    pod
    pod
    pod
    pod
    pod
    pod

