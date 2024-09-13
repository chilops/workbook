---
title: 56Day_Kubernetes
uuid: 11aa18c0-400d-11ef-b01a-26e37c279344
version: 1183
created: '2024-07-12T10:40:34+05:30'
tags:
  - kubernetes
---

\

# <mark style="background-color:#f8914d;">**Till date**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

cluster nodes created (check previous session)

![e97eb440-d40b-495e-9ec2-09c588297cc7.png|840](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/e97eb440-d40b-495e-9ec2-09c588297cc7.png) [^1]

Till date 

![3dfbf686-ae5b-43f2-ac8a-a906f7073d9a.png|336](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3dfbf686-ae5b-43f2-ac8a-a906f7073d9a.png) [^2]

\

\

# <mark style="background-color:#f8914d;">**Roboshop using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![661efce1-a39d-476b-82e5-9d02fc078b31.png|670](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/661efce1-a39d-476b-82e5-9d02fc078b31.png) [^3]

\

# <mark style="background-color:#f8914d;">**MongoDB Setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![79081f60-379f-43a9-b5f2-d1c17bccab98.png|668](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/79081f60-379f-43a9-b5f2-d1c17bccab98.png) [^4]

\

repo creation

![fc3db8bd-5d1f-4c4e-8007-6b3fdf355899.png|955.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/fc3db8bd-5d1f-4c4e-8007-6b3fdf355899.png) [^5]

\

![f35fa4de-c17f-41fb-bafc-3b2aaa587701.png|956](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f35fa4de-c17f-41fb-bafc-3b2aaa587701.png) [^6]

![21f66dc9-2318-4696-bdd9-d76ceb1fd674.png|1001.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/21f66dc9-2318-4696-bdd9-d76ceb1fd674.png) [^7]

![69047442-b1e2-4f22-994e-0df5d1823acb.png|1000.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/69047442-b1e2-4f22-994e-0df5d1823acb.png) [^8]

\

login to docker hub

![ea0ec023-1093-402f-b444-b3ed53ab1957.png|1006.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/ea0ec023-1093-402f-b444-b3ed53ab1957.png) [^9]

\

Building an image and pushing it to docker hub.

```
docker build -t joindevops/mongodb:v1 .
```

![bdc7f04b-fc33-4b5e-82de-ae29bd632528.png|1205.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/bdc7f04b-fc33-4b5e-82de-ae29bd632528.png) [^10]

```
docker images
```

![f31a7446-d48d-496d-8dbd-099a7ea75c9b.png|1079.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f31a7446-d48d-496d-8dbd-099a7ea75c9b.png) [^11]

\

```
docker push joindevops/mongodb:v1
```

![95594fbf-870b-419e-9f4a-cab2c70123ae.png|1181.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/95594fbf-870b-419e-9f4a-cab2c70123ae.png) [^12]

\

<mark>**Creating a namespace**</mark>

Every project should have separate namespace not the default namespace.

![59776a12-1c8e-4844-948b-4f5d16f9b574.png|752](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/59776a12-1c8e-4844-948b-4f5d16f9b574.png) [^13]

\

git push & pull

![fa83dd69-dc84-487b-a230-c24402bcd5dc.png|990](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/fa83dd69-dc84-487b-a230-c24402bcd5dc.png) [^14]

\

```
kubectl apply -f namespace.yaml
```

![81a42a91-3539-483b-a7c1-55720eed3d8f.png|1166.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/81a42a91-3539-483b-a7c1-55720eed3d8f.png) [^15]

\

<mark>**Now creating K8s manifest file**</mark>

\

![853f72b1-aa2b-4dc9-ad4f-38e68cec8eae.png|645](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/853f72b1-aa2b-4dc9-ad4f-38e68cec8eae.png) [^16]

\

deployment

![82ed902b-3210-4079-bca4-80dec6ad824e.png|1022.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/82ed902b-3210-4079-bca4-80dec6ad824e.png) [^17]

replica & pod

![80251a89-eb1b-454f-b72d-9ed36a15871e.png|1045.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/80251a89-eb1b-454f-b72d-9ed36a15871e.png) [^18]

clusterip

![ebb27419-3db4-4503-b656-0879f59e496f.png|1008](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/ebb27419-3db4-4503-b656-0879f59e496f.png) [^19]

\

git push & pull

![fa83dd69-dc84-487b-a230-c24402bcd5dc.png|990.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/fa83dd69-dc84-487b-a230-c24402bcd5dc.png) [^20]

\

```
kubectl apply -f manifest.yaml
```

![d7dfa0ac-2ba8-4544-89b5-c25b70270456.png|999.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d7dfa0ac-2ba8-4544-89b5-c25b70270456.png) [^21]

\

to check deployment status

```
kubectl get deployments -n roboshop
```

![36c2da22-5488-40d5-a8fe-ac69abad0a76.png|1057.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/36c2da22-5488-40d5-a8fe-ac69abad0a76.png) [^22]

\

pod status

```
kubectl get pods -n roboshop
```

![e054ac85-fa97-47ab-85ae-16dfc5f15f3c.png|1057.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/e054ac85-fa97-47ab-85ae-16dfc5f15f3c.png) [^23]

\

ClusterIP services

```
kubectl get services -n roboshop
```

![c02b1c1e-636e-4d44-ad66-31eb7c390f62.png|1107.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/c02b1c1e-636e-4d44-ad66-31eb7c390f62.png) [^24]

\

# <mark style="background-color:#f8914d;">**Kubernetes auto-namespaces -kubens**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

it will set namespace automatically 

![ff76748a-9463-47ec-91f0-1dc368d68dc3.png|1047](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/ff76748a-9463-47ec-91f0-1dc368d68dc3.png) [^25]

\

![d2dff16f-489d-4c06-8981-763a1e613eaf.png|1104](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d2dff16f-489d-4c06-8981-763a1e613eaf.png) [^26]

\

<mark>Now we no need to give namespace every time when searching for pods etc.</mark>

![d67c34a7-558c-493f-b301-83fb619d3e35.png|1234](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d67c34a7-558c-493f-b301-83fb619d3e35.png) [^27]

\

\

# <mark style="background-color:#f8914d;">**Catalogue Setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![d146fb6a-d5f3-42a8-821f-61e58a6ceea3.png|815](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d146fb6a-d5f3-42a8-821f-61e58a6ceea3.png) [^28]

\

git push & pull

![f409d789-75af-444d-8ad4-d204adfb010c.png|949.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f409d789-75af-444d-8ad4-d204adfb010c.png) [^29]

\

creating docker image

```
docker build -t joindevops/catalogue:v1 .
```

![b4387aab-3681-4f99-b230-3adc1f1ea663.png|1081.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b4387aab-3681-4f99-b230-3adc1f1ea663.png) [^30]

\

pushing image to docker hub

```
docker push joindevops/catalogue:v1
```

![62c21af4-a3e4-486f-9e0f-1a8011031d1e.png|1078.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/62c21af4-a3e4-486f-9e0f-1a8011031d1e.png) [^31]

\

<mark>manifest file K8s</mark>

Configmap

![67e91902-9d05-442d-9ea6-50787db32077.png|804](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/67e91902-9d05-442d-9ea6-50787db32077.png) [^32]

deployment & service

![2d7b0a6b-b86d-47ce-93ab-1be4ae0a07b3.png|946](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/2d7b0a6b-b86d-47ce-93ab-1be4ae0a07b3.png) [^33]

\

git push & pull

![9e33a3e7-9c26-471d-a9e8-064d3caf4401.png|1075.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/9e33a3e7-9c26-471d-a9e8-064d3caf4401.png) [^34]

\

```
kubectl apply -f manifest.yaml
```

![7864495b-8d88-4c37-b217-729933619917.png|1106.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/7864495b-8d88-4c37-b217-729933619917.png) [^35]

\

catalogue pod running now

```
kubectl get pods -n roboshop
```

![3db9f32e-a3eb-4e12-a252-a406a0b8693e.png|1023.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3db9f32e-a3eb-4e12-a252-a406a0b8693e.png) [^36]

\

To check catalogue error (there is an error - mongonetworkerror)

```
kubectl logs catalogue-79dd48d65f-d8q72 -n roboshop
```

![dfe53c1b-5685-4fd9-a22d-aa6897eac163.png|1227.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/dfe53c1b-5685-4fd9-a22d-aa6897eac163.png) [^37]

\

<mark>**Debug POD**</mark>

![2d9426ba-a7dd-4a34-bdf9-a8d3c8729b9d.png|1030.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/2d9426ba-a7dd-4a34-bdf9-a8d3c8729b9d.png) [^38]

\

git push & pull

![18a41313-c488-4ccd-a2e5-5142ff2d2ddb.png|1019](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/18a41313-c488-4ccd-a2e5-5142ff2d2ddb.png) [^39]

\

```
docker build -t joindevops/debug:v1 .
```

![1a1c45d7-a704-43ba-a64a-e607934ee63c.png|1103.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/1a1c45d7-a704-43ba-a64a-e607934ee63c.png) [^40]

\

```
docker push joindevops/debug:v1
```

![bb0fad4c-9017-49cd-a893-35bd34eafb3d.png|1205.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/bb0fad4c-9017-49cd-a893-35bd34eafb3d.png) [^41]

\

```
kubectl apply -f manifest.yaml
```

![d45993dc-b47f-4851-9925-9cde677ae906.png|1171.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d45993dc-b47f-4851-9925-9cde677ae906.png) [^42]

\

```
kubectl get pods
```

![18c49b28-c737-4587-a326-8d6f2a1ba337.png|959.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/18c49b28-c737-4587-a326-8d6f2a1ba337.png) [^43]

\

```
to check if mongodb connecting or not( its not connecting in this case)
kubectl exec -it debug --bash
telnet mongodb 27017
ping mongodb
```

![a0856780-dff2-4094-a4a0-ab7b1ac52382.png|1138.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/a0856780-dff2-4094-a4a0-ab7b1ac52382.png) [^44]

\

<mark>Because of security group issue. If we see catalogue is running in one node and mongodb is running in other node</mark>

```
kubectl get pod -o wide
```

![10da5943-161d-4d51-96d1-c6c2b43e4bb2.png|1135.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/10da5943-161d-4d51-96d1-c6c2b43e4bb2.png) [^45]

\

\

Request flow

![8a321c62-5254-4d10-a9c1-333743a9aec7.png|1059.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8a321c62-5254-4d10-a9c1-333743a9aec7.png) [^46]

\

Issue is with port no.. monogo port is 27010 but its showing 8080

![032a820f-2d09-490f-8169-935f64b11d89.png|1105.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/032a820f-2d09-490f-8169-935f64b11d89.png) [^47]

\

So deleting the pods & recreating

![5458c4dc-2317-469b-890e-ec4c20461699.png|1113.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/5458c4dc-2317-469b-890e-ec4c20461699.png) [^48]

\

mongodb

```
kubectl apply -f manifest.yaml
kubectl get svc
```

![f36fb266-f654-48db-b9b5-f04b5bfec1af.png|1096.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f36fb266-f654-48db-b9b5-f04b5bfec1af.png) [^49]

catalogue

```
kubectl apply -f manifest.yaml
kubectl get svc
```

![8b74db6c-9dae-41c1-896b-1296ba6fde18.png|1107.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8b74db6c-9dae-41c1-896b-1296ba6fde18.png) [^50]

\

To check logs

```
kubectl get pods
kubectl logs <catalogue name>
```

![8aa2e763-0f84-4ffa-930c-98ebaa91f596.png|1153.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8aa2e763-0f84-4ffa-930c-98ebaa91f596.png) [^51]

\

# <mark style="background-color:#f8914d;">**Web Setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![8b9351ba-d348-463d-a742-65fa7b0c1ed8.png|643](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8b9351ba-d348-463d-a742-65fa7b0c1ed8.png) [^52]

\

git push & pull

![0ff74de6-fed0-40c1-8f78-dd6bdc96ba94.png|919](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/0ff74de6-fed0-40c1-8f78-dd6bdc96ba94.png) [^53]

\

building docker image

```
docker build -t joindevops/web:v1 .
```

![b6729a13-af68-4ad2-900f-326d5dc12e3d.png|1074.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b6729a13-af68-4ad2-900f-326d5dc12e3d.png) [^54]

```
docker push joindevops/web:v1
```

![b5f6576c-8644-4655-aaad-3984e589a68f.png|1099.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b5f6576c-8644-4655-aaad-3984e589a68f.png) [^55]

\

**Now manifest K8s**

![563e33f8-6b82-47c4-99c8-c349adb02764.png|1025](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/563e33f8-6b82-47c4-99c8-c349adb02764.png) [^56]

\

git push & pull

![0e0e873d-ec1b-4724-91e7-374598f65a4a.png|855](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/0e0e873d-ec1b-4724-91e7-374598f65a4a.png) [^57]

\

creating pods

```
kubectl apply -f manifest.yaml
```

![76ed8353-94c3-4c21-945d-f811c4f048bc.png|1224.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/76ed8353-94c3-4c21-945d-f811c4f048bc.png) [^58]

\

```
kubectl get pods
```

![20c21855-c9c5-42d9-b602-638fb543e064.png|1134.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/20c21855-c9c5-42d9-b602-638fb543e064.png) [^59]

\

to check services

```
kubectl get svc
```

![b3bcb255-ca49-4c5b-9f46-05d6d127f52b.png|1122.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b3bcb255-ca49-4c5b-9f46-05d6d127f52b.png) [^60]

\

\

loadbalancer is unable to reach, <mark>health status - Out-of-service</mark>

![2f9a9f73-00e8-4e8f-bc54-ed1f652849ac.png|1167.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/2f9a9f73-00e8-4e8f-bc54-ed1f652849ac.png) [^61]

\

under cluster node instances SG <mark>- enabling all traffic from all ports</mark>

![ece2976c-2146-4aca-9b88-1b60f78c38ce.png|1027.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/ece2976c-2146-4aca-9b88-1b60f78c38ce.png) [^62]

![18362908-19f1-428e-8039-99e8eeb15658.png|1023.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/18362908-19f1-428e-8039-99e8eeb15658.png) [^63]

\

Now Load Balancer is healthy

![e9a39722-d914-4c8c-a38a-3a87cf8cbb5c.png|1038.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/e9a39722-d914-4c8c-a38a-3a87cf8cbb5c.png) [^64]

\

now we are able to connect 

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/2bfa14ca-dab2-48e6-8b43-d1a221c38bec.png) [^65]

\

# <mark style="background-color:#f8914d;">**Redis Setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![8e0aad72-e469-4cfb-860f-be423f0bd500.png|913](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8e0aad72-e469-4cfb-860f-be423f0bd500.png) [^66]

\

git push & pull

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/854bbd99-35fd-4b4f-8b17-52cf8a04285b.png) [^67]

\

```
kubectl apply -f manifest.yaml
```

![4704053f-2e20-461f-a8c7-1f64f215ff64.png|1097.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/4704053f-2e20-461f-a8c7-1f64f215ff64.png) [^68]

\

```
kubectl get pods
```

![9c695af0-9b09-44f2-8348-e677fb259420.png|981.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/9c695af0-9b09-44f2-8348-e677fb259420.png) [^69]

\

to check if redis port is running or not

![92ab7fc6-8d2b-4353-ae68-ffd87fc5336c.png|1073.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/92ab7fc6-8d2b-4353-ae68-ffd87fc5336c.png) [^70]

\

# <mark style="background-color:#f8914d;">**User Setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![eb8cd610-ba44-42d7-9c5c-78299a74c26a.png|918](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/eb8cd610-ba44-42d7-9c5c-78299a74c26a.png) [^71]

\

git push & pull

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/854bbd99-35fd-4b4f-8b17-52cf8a04285b.png) [^72]

\

\

Build an docker image

```
docker build -t joindevops/user:v1 .
```

![837564bd-13e2-4b13-9ba3-a19f95dad908.png|1204.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/837564bd-13e2-4b13-9ba3-a19f95dad908.png) [^73]

\

pushing to docker hub

```
docker push joindevops/user:v1
```

![d2c1e482-8faa-41c3-a085-ff514448d4fe.png|1051.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d2c1e482-8faa-41c3-a085-ff514448d4fe.png) [^74]

\

<mark>user application is dependent on redis & mongodb</mark>

\

manifest file

![d261ab67-face-4e73-957d-3cabd38d39bc.png|968](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/d261ab67-face-4e73-957d-3cabd38d39bc.png) [^75]

\

git push & pull

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/854bbd99-35fd-4b4f-8b17-52cf8a04285b.png) [^76]

\

creating pod

```
kubectl apply -f manifest.yaml
```

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/c0c1d25a-7336-465e-8444-fad4890d879e.png) [^77]

\

```
kubectl get pods
```

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/c8dc1666-bc50-4591-985f-0b3d1c712412.png) [^78]

\

user worked

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/5bb46502-770f-4787-a231-48aa1db73f61.png) [^79]

\

# <mark style="background-color:#f8914d;">**Cart Setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![374d99f9-7191-4073-82f8-06b79e50c070.png|879](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/374d99f9-7191-4073-82f8-06b79e50c070.png) [^80]

\

git push & pull

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/854bbd99-35fd-4b4f-8b17-52cf8a04285b.png) [^81]

\

\

Build an docker image

```c
docker build -t joindevops/cart:v1 .
```

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f7d2babd-2972-4c40-9708-cc3a387cb92e.png) [^82]

push image to docker hub

```
docker push joindevops/cart:v1
```

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b9e1e60e-f244-4e63-a4f1-615792d216f4.png) [^83]

\

manifest files

![c6a6a1d8-766b-4bd1-b6d1-56bbe0f2da4a.png|1074](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/c6a6a1d8-766b-4bd1-b6d1-56bbe0f2da4a.png) [^84]

\

git push & pull

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/854bbd99-35fd-4b4f-8b17-52cf8a04285b.png) [^85]

\

```
kubectl apply -f manifest.yaml
```

![1aa586a1-a591-43cd-ab7a-8e50a1cb13db.png|1079.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/1aa586a1-a591-43cd-ab7a-8e50a1cb13db.png) [^86]

\

cart is working

![57f20f5c-d6b6-4cd0-b2e2-63a2d79093b7.png|662](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/57f20f5c-d6b6-4cd0-b2e2-63a2d79093b7.png) [^87]

\

\

---

# <mark style="background-color:#f8914d;">**56Day Recap**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

![c5d2da8e-09fd-4938-8985-68fc83f26758.png|1034.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/c5d2da8e-09fd-4938-8985-68fc83f26758.png) [^88]

\

Creating namespaces & mongodb 

![f813a57d-c9dc-402d-8549-1961c5ae9585.png|1079.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f813a57d-c9dc-402d-8549-1961c5ae9585.png) [^89]

\

Kubens install & setup

![f19b7ca7-8283-4a44-9b3c-cc85f9cdae67.png|1085.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f19b7ca7-8283-4a44-9b3c-cc85f9cdae67.png) [^90]

![57bbf97b-3b0d-4c58-9810-a71e806b36ba.png|1085.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/57bbf97b-3b0d-4c58-9810-a71e806b36ba.png) [^91]

\

Redis setup

![34ec01ec-0a2e-493b-8895-daa8f2100ba4.png|1090.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/34ec01ec-0a2e-493b-8895-daa8f2100ba4.png) [^92]

\

Catalogue setup

![4900d6e4-4292-481f-963b-618935792f21.png|1093.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/4900d6e4-4292-481f-963b-618935792f21.png) [^93]

\

User setup

![7acb8faa-8486-490c-9532-73ebf3f79499.png|1094.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/7acb8faa-8486-490c-9532-73ebf3f79499.png) [^94]

\

Cart setup

![8d7a9018-532b-4757-8b2b-8c11c642caa7.png|1096.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8d7a9018-532b-4757-8b2b-8c11c642caa7.png) [^95]

\

Web setup

![6bd7c83e-4394-44e8-a1f5-d647112d7027.png|1091.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/6bd7c83e-4394-44e8-a1f5-d647112d7027.png) [^96]

\

We will get classic load balancer

```
kubectl get svc
```

![a9a53606-e0f8-4cdb-ae7f-b26c65b8bbe2.png|1097.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/a9a53606-e0f8-4cdb-ae7f-b26c65b8bbe2.png) [^97]

\

In load balancers - target instances are not healthy (out-of-service) - so we need to change SG inbound rules

![08989ef7-cd7a-4783-b34c-41e8e4de1330.png|1087.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/08989ef7-cd7a-4783-b34c-41e8e4de1330.png) [^98]

\

In instances SG we need to allow - **All traffic from all ports**

![796227da-5476-4684-9c6f-15a3b272615a.png|1083.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/796227da-5476-4684-9c6f-15a3b272615a.png) [^99]

![bf41e407-8510-41e7-9132-b84d1f2bb817.png|1078.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/bf41e407-8510-41e7-9132-b84d1f2bb817.png) [^100]

\

Now instance health is good(after changing in SG)

![3678ca50-443d-4191-aaeb-e8a08fb87a3e.png|1069.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3678ca50-443d-4191-aaeb-e8a08fb87a3e.png) [^101]

\

Now our application is working

![f72a0f73-25e2-4311-97c7-ff3bd1084b01.png|1058](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f72a0f73-25e2-4311-97c7-ff3bd1084b01.png) [^102]

\

# <mark style="background-color:#f8914d;">**Mysql setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/64da9b97-11d5-43ba-b098-9dd2916cfe58.png) [^103]

\

git push & pull

![b850c736-cf36-4b83-8105-025b4a035e52.png|1011](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b850c736-cf36-4b83-8105-025b4a035e52.png) [^104]

\

creating a docker image

```
docker build -t joindevops/mysql:v1 .
```

![b955a887-17af-4ce9-b97d-0c7e2e4aeb29.png|1024.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b955a887-17af-4ce9-b97d-0c7e2e4aeb29.png) [^105]

\

pushing docker image to docker hub

```
docker push joindevops/mysql:v1
```

![e457868b-6ef4-4b24-805e-a3025509a1bf.png|1058.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/e457868b-6ef4-4b24-805e-a3025509a1bf.png) [^106]

\

manifest for K8s

<mark>**secret**</mark> 

![a3b36f2b-6b8e-49d3-86cb-66005f381217.png|988](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/a3b36f2b-6b8e-49d3-86cb-66005f381217.png) [^107]

![3c59710a-3b7e-40ee-bf44-8d52616e6056.png|1014](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3c59710a-3b7e-40ee-bf44-8d52616e6056.png) [^108]

\

git push & pull

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/a00ad824-9d58-4071-8c66-d83f3a42fb75.png) [^109]

\

pod creation

```
kubectl apply -f manifest.yaml
```

![7d1e76eb-3d90-43d9-9597-fd04b624f232.png|1162.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/7d1e76eb-3d90-43d9-9597-fd04b624f232.png) [^110]

\

```
kubectl get pods
```

![e475f889-ecac-4a43-bd41-ee2b37d35a6b.png|1164.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/e475f889-ecac-4a43-bd41-ee2b37d35a6b.png) [^111]

\

mysql is running, Now login to mysql server

```
kubectl exec -it mysql-7f4b445856-wg15v -- bash
```

to check if mysql is working or not... its working as below.

```
mysql -u shipping -pRoboShop@1
```

![729c7bfc-df2a-4bb0-8a1d-d523095c6c8b.png|1085.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/729c7bfc-df2a-4bb0-8a1d-d523095c6c8b.png) [^112]

\

```
show databases
```

![8f24a552-641e-4162-99b7-f36718e1f65a.png|577](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/8f24a552-641e-4162-99b7-f36718e1f65a.png) [^113]

![3878c0dc-d156-4c48-967b-0ac1deb6f779.png|973](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3878c0dc-d156-4c48-967b-0ac1deb6f779.png) [^114]

# <mark style="background-color:#f8914d;">**Shipping setup using K8s**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![75811f87-fc1f-40ef-896c-602be23d0236.png|1055.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/75811f87-fc1f-40ef-896c-602be23d0236.png) [^115]

\

git push & pull

![b850c736-cf36-4b83-8105-025b4a035e52.png|1011](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b850c736-cf36-4b83-8105-025b4a035e52.png) [^116]

\

building a docker image

```
docker build -t joindevops/shipping:v1 .
```

![166cf431-bc07-4e9c-9cec-100a55bd0443.png|1117.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/166cf431-bc07-4e9c-9cec-100a55bd0443.png) [^117]

\

login to docker to push the images to docker hub

![be64264b-dfe0-4c35-9f21-6004e63a9ad5.png|1131.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/be64264b-dfe0-4c35-9f21-6004e63a9ad5.png) [^118]

\

Pushing docker image to docker hub

```
docker push joindevops/shipping:v1
```

![b21a3585-770b-4959-9d8f-736b3665f5ba.png|1133.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b21a3585-770b-4959-9d8f-736b3665f5ba.png) [^119]

\

manifest file for k8s

![be60baf3-b2c8-4c43-a20e-16d627100eca.png|1145.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/be60baf3-b2c8-4c43-a20e-16d627100eca.png) [^120]

\

git push & pull

![b850c736-cf36-4b83-8105-025b4a035e52.png|1011](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b850c736-cf36-4b83-8105-025b4a035e52.png) [^121]

\

```
kubectl apply -f manifest.yaml
```

![2abc3286-92b5-41e7-9d89-1fcefbb299f6.png|1124.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/2abc3286-92b5-41e7-9d89-1fcefbb299f6.png) [^122]

\

```
kubectl get pods
```

![b3d195ba-ddc7-4212-b67d-052f5426c285.png|1182.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/b3d195ba-ddc7-4212-b67d-052f5426c285.png) [^123]

\

checking if shipping is working properly or not

```
kubectl logs shipping-8ffd9bc47-ddscv
```

![295c8946-b9f0-47a2-9fbd-d488cf6b1e2f.png|902.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/295c8946-b9f0-47a2-9fbd-d488cf6b1e2f.png) [^124]

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/523a145b-865d-49b7-9235-c10b228b04de.png) [^125]

\

shipping is working

![](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/e9adf1cb-3fb4-4534-bee4-a4bda08d29bb.png) [^126]

![749e3203-a7aa-4b60-aae5-16996192884c.png|1057](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/749e3203-a7aa-4b60-aae5-16996192884c.png) [^127]

---

# <mark style="background-color:#f8914d;">**Payment setup using K8s (includes RabbitMQ)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

RabbitMQ manifest file

![218e17ee-9702-4950-854d-76a15f296835.png|1051.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/218e17ee-9702-4950-854d-76a15f296835.png) [^128]

\

git push & pull

![2e4ce1a3-b72a-4775-ad2c-a1ea3f3d785a.png|864](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/2e4ce1a3-b72a-4775-ad2c-a1ea3f3d785a.png) [^129]

\

RabbitMQ pod creation

```
kubectl apply -f manifest.yaml
kubectl get pods
```

![99fdb06d-3ea1-4eca-aee8-d6f8d12e1ebb.png|1062.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/99fdb06d-3ea1-4eca-aee8-d6f8d12e1ebb.png) [^130]

\

to check pod logs

```
kubectl logs rabbitmq-697sdfdfsdcx-vjdfbh
```

![5066d74a-cb09-41b1-a8a1-c877f0ed1b3b.png|1176.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/5066d74a-cb09-41b1-a8a1-c877f0ed1b3b.png) [^131]

\

Payment process starts here

![6263550e-ed00-49a8-84f3-bb0f38756cdb.png|1000.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/6263550e-ed00-49a8-84f3-bb0f38756cdb.png) [^132]

\

git push & pull

![1dc4d4b6-af05-4f8a-a525-387e6550143f.png|792](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/1dc4d4b6-af05-4f8a-a525-387e6550143f.png) [^133]

\

docker image build

```
docker build -t joindevops/payment:v1 .
```

![968f310b-4859-4342-9587-0f45e58f03c0.png|1096.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/968f310b-4859-4342-9587-0f45e58f03c0.png) [^134]

\

pushing to docker hub

```
docker push joindevops/payment:v1
```

![5cb3add7-d384-4dfb-b099-ca76b575fc78.png|1165.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/5cb3add7-d384-4dfb-b099-ca76b575fc78.png) [^135]

\

manifest file 

![9cdf459e-c81a-4615-96ce-7acbd384cb39.png|787](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/9cdf459e-c81a-4615-96ce-7acbd384cb39.png) [^136]

\

git push & pull

![1dc4d4b6-af05-4f8a-a525-387e6550143f.png|792](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/1dc4d4b6-af05-4f8a-a525-387e6550143f.png) [^137]

\

pod creation

```
kubectl apply -f manifest.yaml
```

![966ff760-c6b5-4402-8b98-736ca29a1018.png|1149.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/966ff760-c6b5-4402-8b98-736ca29a1018.png) [^138]

\

```
kubectl get pods
```

![6a499cae-e04d-45e8-8a58-59774054622f.png|1144.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/6a499cae-e04d-45e8-8a58-59774054622f.png) [^139]

\

payment page also done

![f728e975-5dfb-4f76-a844-c01ddefe0fb4.png|1151.3333740234375](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/f728e975-5dfb-4f76-a844-c01ddefe0fb4.png) [^140]

\

\

[^1]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2. micro \| null
    \[ centos@ip-172-31-93-8 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-192-168-19-220. ec2. internal
    Ready
    <none>
    7m17s
    v1 . 27.9-eks-5eOfdde
    ip-192-168-30-103.ec2 . internal
    Ready
    <none>
    7m18s
    v1 . 27.9-eks-5eOfdde
    ip-192-168-61-162. ec2 . internal
    Ready
    <none>
    7m18s
    v1. 27.9-eks-5eOfdde

[^2]: apiVersion :
    kind :
    metadata :
    name :
    labels :
    spec :
    namespaces
    pods
    configmap
    secret
    services
    clusterIP
    node Port
    LoadBalancer
    Sets
    ReplicaSet
    Deployment

[^3]: 1. image should exist, building the image
    2. configuring image through manifest yamls

[^4]: EXPLORER
    Dockerfile roboshop-docker\\mongodb
    JS user.Js
    V REPOS
    k8-roboshop > mongodb > Dockerfile > FROM
    > archieve
    1
    FROM mongo :5
    > catalogue
    2
    COPY \*. js /docker-entrypoint-initdb. d/
    > catalogue-deploy
    > dockerfiles
    > k8-eksctl
    > k8-resources
    k8-roboshop \\ mongodb -
    JS catalogue.js
    Dockerfile
    JS user.js

[^5]: E
    New repository
    Q Type to search
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    daws-76s
    k8-roboshop
    k8-roboshop is available.
    Great repository names are short and memorable. Need inspiration? How about silver-potato ?
    Description (optional)
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    P 8
    Private
    You choose who can see and commit to this repository.

[^6]: user@AshDexter-T480 MINGW64 \~
    $ cd /c/devops/daws-76s/repos/k8-roboshop/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop
    $ git init
    Initialized empty Git repository in c: /devops/daws-76s/repos/k8-roboshop/. git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git remote add origin git@github. com: daws-76s/k8-roboshop . git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main (root-commit) 9c46962\] jenkins
    3 files changed, 46 insertions (+)
    create mode 100644 mongodb /Dockerfile
    create mode 100644 mongodb/catalogue. js
    create mode 100644 mongodb /user. is

[^7]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| null
    \[ centos@ip-172-31-93-8 \~ \]$ git clone git@github. com: daws-76s/k8-roboshop. git
    Cloning into 'k8-roboshop'
    Warning: Permanently added 'github. com, 140 . 82.114.4' (ECDSA) to the list of known hosts.
    git@github. com: Permission denied (publickey) .
    fatal: Could not read from remote repository.
    Please make sure you have the correct access rights
    and the repository exists.

[^8]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| null
    \[ centos@ip-172-31-93-8 \~ \]$ git clone https: //github. com/daws-76s/k8-roboshop . git
    Cloning into 'k8-roboshop'
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (5/5), done.
    remote: Total 6 (delta 0), reused 6 (delta 0) , pack-reused 0
    Receiving objects: 100% (6/6) , done.

[^9]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github.com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop \]$ cd mongodb/
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ 1s
    catalogue. is Dockerfile user. js
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ cat Dockerfile
    FROM mongo : 5
    COPY \*. js /docker-entrypoint-initdb. d/
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ docker login
    Log in with your Docker ID or email address to push and pull images from Docker Hub. If you don
    / /hub . docker . com/ to create one.
    You can log in with your password or a Personal Access Token (PAT) . Using a limited-scope PAT gr
    r organizations using SSO. Learn more at https: / /docs . docker . com/go/access-tokens/
    Username: joindevops
    Password:
    WARNING! Your password will be stored unencrypted in /home/centos/ . docker/config . json.
    Configure a credential helper to remove this warning. See
    https : / /docs . docker . com/engine/reference/commandline/login/#credentials-store
    Login Succeeded

[^10]: 3. 95 . 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ docker build -t joindevops/mongodb: v1 .
    \[+\] Building 0.8s (5/7)
    docker : default
    \[internal\] load build definition from Dockerfile
    0. 0s
    > transferring dockerfile: 888
    0. 0s
    (internal\] load metadata for docker . 10/library/mongo:5
    0. 3s
    (auth\] library/mongo:pull token for registry-1. docker. 10
    0. 0s
    \[internal\] load . dockerignore
    0.0s
    > transferring context: 28
    0. 0s
    \[internal\] load build context
    0 . 0s
    > transferring context: 2.38kB
    0. 0s
    \[1/2\] FROM docker . io/library/mongo : 5@sha256: 2c310a955fd670e32859c12e52a682ae6fbe3937edb0b20e7721b3370bb9334f
    0 . 4s
    => resolve docker. 10/library/mongo : 50sha256: 20310a955fd670e3285901252a682ae6fbe3937edbob20e7721b3370bb9334f
    0 . 0s
    > > sha256: 20310a955fd670e3285901252a682ae6fbe3937edbob20e7721b3370bb9334f 3.00kB / 3.00kB
    0. 0s

[^11]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    joindevops/mongodb
    v1
    a103b345444d
    5 seconds ago
    697MB

[^12]: ncups . /791tho . com/ daws
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    joindevops/mongodb
    v1
    a103b345444d
    5 seconds ago
    697MB
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/8-roboshop/mongodb \]$ docker push joindevops/mongodb : v1
    The push refers to repository \[docker . io/joindevops/mongodb\]
    ce25cda98f2c: Pushing \[==
    5. 12kB
    b03600fd2e12: Layer already exists
    2f4690dcf403: Layer already exists
    9bb6a0b97a93: Layer already exists
    2c5a9bfeba37: Layer already exists
    ca3de444ae6c: Layer already exists

[^13]: V REPOS
    k8-roboshop > ! namespace.yaml > {} metadata
    > .github
    1
    apiVersion: v1
    > archieve
    kind: Namespace
    3
    > catalogue
    metadata :
    4
    name: roboshop
    > catalogue-deploy
    > dockerfiles
    > k8-eksctl
    > k8-resources
    k8-roboshop
    > mongodb
    ! namespace.yaml
    U

[^14]: 3. 95. 173. 185 \| 172.31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (5/5) , done.
    remote: Total 5 (delta 0) , reused 5 (delta 0) , pack-reused 0
    Unpacking objects: 100% (5/5) , 789 bytes \| 789.00 KiB/s, done.

[^15]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop \]$ 1s
    mongodb namespace . yaml
    3. 95. 173.185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop \]$ kubectl apply -f namespace . yaml
    namespace/roboshop created

[^16]: Image pull policy
    The imagePullPolicy for a container and the tag of the image affect when the kubelet attempts to
    pull (download) the specified image.
    Here's a list of the values you can set for imagePullpolicy and the effects these values have:
    IfNotPresent
    the image is pulled only if it is not already present locally.
    every time the kubelet launches a container, the kubelet queries the container image registry to
    resolve the name to an image digest. If the kubelet has a container image with that exact digest
    cached locally, the kubelet uses its cached image; otherwise, the kubelet pulls the image with the
    resolved digest, and uses that image to launch the container.
    Never
    the kubelet does not try fetching the image. If the image is somehow already present locally, the
    kubelet attempts to start the container; otherwise, startup fails. See pre-pulled images for more
    details.

[^17]: V REPOS
    k8-roboshop > mongodb > ! manifest.yaml > {} spec > # replicas
    > .github
    apiVersion: apps/v1
    > archieve
    2
    kind: Deployment
    3
    > catalogue
    metadata :
    4
    . name : mongodb
    > catalogue-deploy
    5
    namespace: roboshop
    > dockerfiles
    6
    labels: # these labels are deployment labels
    > k8-eksctl
    7
    app: mongodb
    > k8-resources
    8
    project: roboshop
    k8-roboshop
    19
    tier: db
    10
    mongodb
    spec :
    11
    replicas: 1
    JS catalogue.js
    12
    selector :
    Dockerfile
    13
    matchLabels: # these labels are used to find the pods
    ! manifest.yaml
    U
    14
    app: mongodb

[^18]: EXPLORER
    . . .
    erfile k8-roboshop!.
    JS user.js k8-roboshop\\..
    ! manifest.yaml U X ! namespace.yaml
    V REPOS
    k8-roboshop > mongodb > ! manifest.yaml > {} spec > {} template > {} spec > \[ \] containers > {
    > .github
    3
    metadata:
    > archieve
    10
    spec :
    > catalogue
    11
    replicas: 1
    > catalogue-deploy
    12
    selector :
    > dockerfiles
    13
    matchLabels: # these labels are used to find the pods
    14
    > k8-eksctl
    app: mongodb
    15
    project: roboshop
    > k8-resources
    16
    tier: db
    k8-roboshop
    17
    template :
    mongodb
    18
    metadata:
    JS catalogue.js
    19
    labels: # these labels are pod labels
    Dockerfile
    20
    app: mongodb
    21
    ! manifest.yaml
    U
    project: roboshop
    22
    tier: db
    JS user.js
    23
    spec :
    ! namespace.yaml
    U
    24
    containers :
    > roboshop-ansible-roles
    25
    name: mongodb
    > roboshop-ansible-roles-tf
    26
    image: joindevops/mongodb : v1
    > roboshop-docker
    27
    imagePullPolicy : Always
    28
    > roboshop-infra-dev

[^19]: > k8-eksctl
    29
    apiVersion: v1
    > k8-resources
    30
    kind: Service
    k8-roboshop
    31
    metadata:
    mongodb
    32
    name: mongodb I
    JS catalogue.js
    33
    namespace: roboshop
    Dockerfile
    34
    spec :
    35
    selector:
    ! manifest.yaml
    U
    36
    app: mongodb
    JS user.js
    37
    project: roboshop
    ! namespace.yaml
    U
    38
    tier : db
    > roboshop-ansible-roles
    39
    ports :
    > roboshop-ansible-roles-tf
    40
    -
    protocol: TCP
    > roboshop-docker
    41
    port: 27017 #service-port
    42
    > roboshop-infra-dev
    targetPort: 27017 #container-port

[^20]: 3. 95. 173. 185 \| 172.31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (5/5) , done.
    remote: Total 5 (delta 0) , reused 5 (delta 0) , pack-reused 0
    Unpacking objects: 100% (5/5) , 789 bytes \| 789.00 KiB/s, done.

[^21]: 3. 95. 173.185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ kubectl apply -f manifest. yaml
    deployment . apps/mongodb created
    service/mongodb created

[^22]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ kubectl get deployments -n roboshop
    NAME
    READY
    UP-TO-DATE
    AVAILABLE
    AGE
    mongodb
    1/1
    1
    1
    13s

[^23]: 3. 95. 173.185 \| 172.31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ kubectl get pods -n roboshop
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    mongodb-778f7b57d5-tc9gp
    1/1
    Running
    0
    24s

[^24]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ kubectl get services -n roboshop
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    mongodb
    ClusterIP
    10 . 100 .195. 163
    <none>
    27017/TCP
    39s

[^25]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ cd
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| null
    \[ centos@ip-172-31-93-8 \~ \]$ sudo git clone https: //github. com/ahmetb/kubectx /opt/kubectx
    Cloning into '/opt/kubectx' ..
    remote: Enumeratiog objects: 1502, done.
    remote: Counting objects: 100% (452/452), done.
    remote: Compressing objects: 100% (98/98) , done.
    remote: Total 1502 (delta 390) , reused 355 (delta 353) , pack-reused 1050
    Receiving objects: 100% (1502/1502) , 912.88 KiB \| 24.02 MiB/s, done.
    Resolving deltas: 100% (876/876) , done.

[^26]: 3. 95. 173. 185 \| 172. 31.93.8 \|
    t2.micro \| null
    \[ centos@ip-172-31-93-8
    \~ \]$ sudo In -s /opt/kubectx/kubens /usr/local/bin/kubens

[^27]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubens roboshop
    Context "terraform@roboshop . us-east-1. eksctl . io" modified.
    Active namespace is "roboshop" .
    3. 95. 173.185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-d8q72
    1/1
    Running
    O
    2m16s
    mongodb-778f7b57d5-tc9gp
    1/1
    Running
    11m

[^28]: V REPOS
    k8-roboshop > catalogue > Dockerfile > .
    arcnieve
    FROM node : 18. 19. 1-alpine3. 19
    > catalogue
    2
    EXPOSE 8080
    > catalogue-deploy
    3
    RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    > dockerfiles
    4
    WORKDIR /opt/server
    > k8-eksctl
    15
    RUN chown roboshop : roboshop /opt/server
    16
    USER roboshop
    > k8-resources
    17
    COPY package. json /opt/server/
    k8-roboshop
    8
    COPY server . js /opt/server/
    catalogue
    9
    RUN npm install
    Dockerfile
    U
    10
    CMD \[ "node", "server. js"j
    {} package.json -
    U
    JS server.js
    U

[^29]: 3. 95. 173. 185 \| 172.31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (6/6) , done.
    remote: Total 6 (delta 0), reused 6 (delta 0) , pack-reused 0
    Unpacking objects: 100% (6/6), 2.27 KiB \| 2.27 MiB/s, done.
    From https: / /github . com/daws-76s/k8-roboshop
    8a5blaa. . c8af89c main
    -> origin/main
    Updating 8a5blaa. . c8af89c
    Fast-forward
    catalogue/Dockerfile
    10 ++++++
    catalogue/package . ison
    20 + ++++++

[^30]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ docker build -t joindevops/catalogue:v1 .
    \[+\] Building 0.8s (5/12)
    docker : default
    \[internal\] load build definition from Dockerfile
    0. 0s
    > transferring dockerfile: 3148
    0.0s
    \[internal\] load metadata for docker . 10/library/node: 18.19.1-alpine3. 19
    0. 3a
    (auth\] library/node: pull token for registry-1. docker . 10
    0. 0s
    \[internal\] load . dockerignore
    0.0s
    >> transferring context: 28
    0. 0s
    \[1/7\] FROM docker . io/library/node: 18. 19. 1-alpine3. 19@sha256: ca9f6cb0466f9638e59e()c249d335a07c867cd50c429b5c7830ddalbed584649
    0 . 4s
    > resolve docker . io/library/node: 18.19.1-alpine3. 198sha256: ca916cb046619638e59e0c249d3352070867cd50c429b507830ddalbed584649
    0. 0s
    > > sha256 : 24d8fod7167fb06e91dc7228311105013dc042168751252817a41004770112 7. 14kB / 7. 14kB
    0 . 0s
    3256: 4abcf20661432b2d719aa$90656155c2878ca915do192ec14{{61e67fbaf8
    41MB
    . 41MB

[^31]: \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ docker push joindevops/catalogue:v1
    The push refers to repository \[docker . io/joindevops/catalogue\]
    fc5b2103d034: Pushing \[=
    14. 47MB/28 . 27MB
    ee 742c157f7e: Pushing \[
    8 . 192kB
    a9be08bf9d6e: Pushing
    3. 584KB
    al7d6bf7230b: Pushing
    2 . 56kB
    7d73c8f030f6: Pushing
    2 . 56kB
    b4aff2fb3b86: Waiting

[^32]: V REPOS
    k8-roboshop > catalogue > ! manifest.yaml >
    > archieve
    1
    apiVersion: v1
    > catalogue
    2
    kind: ConfigMap
    13
    metadata :
    > catalogue-deploy
    4
    name: catalogue
    > dockerfiles
    5
    namespace: roboshop
    > k8-eksctl
    6
    data :
    > k8-resources
    7
    MONGO: "true"
    k8-roboshop
    8
    catalogue
    9
    apiVersion: apps/v1
    10
    kind: Deployment
    Dockerfile
    11
    metadata :
    !
    manifest.yaml
    M

[^33]: REPOS
    k8-roboshop > catalogue > ! manifest.yaml > {} spec > {} selector
    > .github
    18
    spec :
    > archieve
    25
    template :
    > catalogue
    31
    spec:
    32
    containers :
    > catalogue-deploy
    33
    - name: catalogue
    > dockerfiles
    35
    imagePullPolicy: Always
    > k8-eksctl
    36
    envFrom:
    > k8-resources
    37
    - configMapRef :
    k8-roboshop
    38
    name: catalogue
    catalogue
    39
    40
    apiVersion: v1
    Dockerfile
    41
    kind: Service
    ! manifest.yaml
    M
    42
    metadata:
    \[) package.json
    43
    name: catalogue
    JS server.js
    44
    namespace: roboshop
    > debug
    45
    spec :
    > mongodb
    46
    selector:
    47
    ! namespace.yaml
    app: catalogue
    48
    project: roboshop
    > roboshop-ansible-roles
    49
    tier: app
    > roboshop-ansible-rol.
    50
    ports :
    > roboshop-docker
    51
    protocol: TCP
    > roboshop-infra-dev
    52
    port: 8080 #service-port
    OUTLINE
    53
    targetPort: 8080 #container-port

[^34]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 4 (delta 0)
    reused 4 (delta 0)
    pack-reused 0

[^35]: 3. 95. 173.185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl apply -f manifest. yaml
    configmap/catalogue created
    deployment . apps/catalogue created
    service/mongodb created

[^36]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl get pods -n roboshop
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-d8q72
    1/1
    Running
    9s
    mongodb-778f7b57d5-tc9gp
    1/1
    Running
    9m25s

[^37]: 3. 95. 173. 185 \| 172. 31. 93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl logs catalogue-79dd48d65f-d8q72 -n roboshop
    (node : 1) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monitoring engine is deprecated, and will be removed in a future versi
    n. To use the new Server Discover and Monitoring engine, pass option { useUnifiedTopology: true } to the MongoClient constructor.
    (Use node --trace-warnings . . . 'to show where the warning was created)
    { "level" : "info" , "time" : 1708914014216, "pid" :1, "hostname": "catalogue-79dd48d65f-d8q72" , "msg" : "Started on port 8080", "v" :1}
    { "level" : "error", "time" : 1708914024220, "pid" : 1, "hostname"_"catalogue-79dd48d65f-d8q72" , "msg" : "ERROR { \\"name\\": \\"MongoNetworkError\\"}", "
    " : 1}

[^38]: File Edit Selection View
    Go
    . . .
    9 repos
    EXPLORER
    . . .
    est.yaml ..\\mongodb
    ! namespace.yaml k8-roboshop
    Dockerfile .. \\debug U
    ! manifest.yaml .\\debug U X
    REPOS
    k8-roboshop > debug > ! manifest.yaml > { } spec > \[ \] containers
    > .github
    apiVersion: v1
    > archieve
    2
    kind: Pod
    3
    metadata :
    > catalogue
    4
    name : debug
    > catalogue-deploy
    15
    namespace: roboshop
    > dockerfiles
    6
    spec:
    > k8-eksctl
    7
    # list of containers
    > k8-resources
    8
    containers :
    k8-roboshop
    9
    name: debug
    10
    > catalogue
    image: joindevops/debug: v1
    11
    #here with this line port will not be opened, just for information
    debug
    12
    command: \["sleep", "100000"\]
    Dockerfile -
    U
    ! manifest.yaml -
    U

[^39]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main b6117c0\] jenkins
    2 files changed, 14 insertions (+)
    create mode 100644 debug/Dockerfile

[^40]: 3. 95. 173. 185 \| 172. 31. 93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ cd . ./debug/
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ docker build -t joindevops/debug:v1
    \[+\] Building 8.1s (5/6)
    docker : default
    \[internal\] load build definition from Dockerfile
    0. 0s
    => > transferring dockerfile: 798
    0. 0s
    \[internal\] load metadata for docker. 10/library/almalinux: 8
    O. 4s
    =>
    (auth\] library/almalinux: pull token for registry-1 . docker. io
    0. 0s

[^41]: 3. 95 . 173. 185 \| 172. 31. 93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ docker push joindevops/debug:v1
    The push refers to repository \[docker . io/joindevops/debug\]
    89c6b71ad005: Pushing \[=
    22 . 02MB/50 . 62MB
    bb077eef2bb1: Mounted from library/almalinux

[^42]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl apply -f manifest. yaml
    pod/debug created

[^43]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-g5dxx
    1/1
    Running
    115s
    debug
    1/1
    Running
    6s
    mongodb-778f7b57d5-tc9gp
    1/1
    Running
    19m

[^44]: 3. 95. 173. 185 \| 172.31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl exec -it debug -- bash
    \[root@debug /\]# telnet mongodb 27017
    Trying 10.100.210.206. ..
    ^C
    \[root@debug /\]# ping mongodb
    PING mongodb . roboshop . svc. cluster . local (10.100.210.206) 56 (84) bytes of data.

[^45]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl get pod -o wide
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    NODE
    NOMINATED NO
    ADINESS GATES
    catalogue-79dd48d65f-g5dxx
    1/1
    Running
    0
    3m33s
    192. 168 .34.221
    ip-192-168-61-162. ec2. internal
    <none>
    one>
    debug
    1/1
    Running
    0
    104s
    192 . 168 .17.173
    ip-192-168-19-220. ec2 . internal
    <none>
    one>
    mongodb-778f7b57d5-tc9gp
    1/1
    Running
    0
    21m
    192 . 168 .23. 74
    ip-192-168-19-220. ec2. internal
    <none>
    one>
    3. 95. 173. 185 \| 172. 31. 93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git

[^46]: Request
    I
    catalogue-pod --> catalouge node --> mongodb service --> mongodb node --> mongodb pod

[^47]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl get service
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    catalogue
    ClusterIP
    10 . 100 . 244 . 18
    <none>
    8080/TCP
    15m
    mongodb
    ClusterIP
    10 . 100 .210.206
    <none>
    8080/TCP
    23m
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop. git

[^48]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl delete -f . ./mongodb/manifest. yaml
    deployment . apps "mongodb" deleted
    service "mongodb" deleted
    3. 95 . 173.185 \| 172.31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ kubectl delete -f . ./catalogue/manifest. yaml
    configmap "catalogue" deleted
    deployment . apps "catalogue" deleted
    service "catalogue" deleted
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/8-roboshop/debug \]$ git pull
    Already up to date.

[^49]: 3. 95. 173.185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/debug \]$ cd . ./mongodb/
    3. 95 . 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ kubectl apply -f manifest. yaml
    deployment . apps/mongodb created
    service/mongodb created
    3 . 95 . 173. 185 \| 172.31.93.8 \| t2.micro \| https: / /github.com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    mongodb
    ClusterIP
    10 . 100 . 21 . 190
    <none>
    27017/TCP
    4s
    3. 95 . 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github.com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \] $

[^50]: 95 . 173. 185 \| 172.31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    centos@ip-172-31-93-8 \~/k8-roboshop/mongodb \]$ cd . ./catalogue/
    95 . 173. 185 \| 172.31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl apply -f manifest.yaml
    configmap/catalogue created
    deployment . apps/catalogue created
    ervice/catalogue created

[^51]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-wxt6b
    1/1
    Running
    0
    6s
    debug
    1/1
    Running
    15m
    OO
    mongodb-778f7b57d5-5wm2j
    1/1
    Running
    26s
    3. 95 . 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/catalogue \]$ kubectl logs catalogue-79dd48d65f-wxt6b
    (node : 1) \[MONGODB DRIVER\] Warning: Current Server Discovery and Monitoring engine is deprecated, and will be removed in a future version
    n. To use the new Server Discover and Monitoring engine, pass option { useUnifiedTopology: true } to the MongoClient constructor.
    (Use node --trace-warnings .
    . ' to show where the warning was created)
    { "level" : "info", "time" : 1708915567599, "pid" : 1, "hostname" : "catalogue-79dd48d65f-wxt6b" , "msg" : "Started on port 8080", "v" :1}
    { "level" : "info" , "time" : 1708915567611, "pid" : 1, "hostname": "catalogue-79dd48d65f-wxt6b" , "msg" : "MongoDB connected", "v" :1}
    3. 95. 173. 185 \| 172. 31. 93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git

[^52]: EXPLORER
    . . .
    ice.yaml k8-roboshop
    Dockerfile roboshop-docker\\web
    roboshop.conf
    REPOS
    k8-roboshop > web > @ roboshop.conf
    .github
    10
    http {
    > archieve
    48
    server {
    > catalogue
    75
    error_page
    500 502 503 504 /50x. html;
    > catalogue-deploy
    76
    location = /50x. html {
    77
    root
    > dockerfiles
    /usr/share/nginx/html;
    78
    > k8-eksctl
    79
    > k8-resources
    80
    k8-roboshop
    81
    > catalogue
    82
    > debug
    > mongodb
    web
    >
    static
    Dockerfile -
    U
    H
    @ roboshop.conf
    U

[^53]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 9e5234d\] jenkins
    31 files changed, 1428 insertions (+)
    create mode 100644 web/Dockerfile
    create mode 100644 web/roboshop . conf
    create mode 100644 web/static/cart. html

[^54]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/web \]$ docker build -t joindevops/web:v1 .
    \[+\] Building 0.7s (5/11)
    docker : default
    =>
    (internal\] load build definition from Dockerfile
    0. 0s
    > transferring dockerfile: 243B
    0. 0s
    \[internal\] load metadata for docker. 10/library/nginx: latest
    0 . 3s
    \[auth\] library/nginx :pull token for registry-1 . docker . io
    0. 0s
    (internal\] load . dockerignore
    0.0s
    > transferring context: 28
    0. 0s
    => \[1/6\] FROM docker . io/library/nginx: latest@sha256: c26ae7472d624balfafd296e73cecc4f931853088e6a9c13c0d52f6ca5865107
    0 . 3s
    =>
    resolve docker. 10/Library/nginx : latest@sha256 : c26ae7472d624baltafd296073cecc41931853088-63901300d5216ca5865107
    0 . 0s

[^55]: 3. 95. 173.185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/web \]$ docker push joindevops/web:v1
    The push refers to repository \[docker . io/joindevops/web\]
    d8e3682503a0: Pushed
    ecf5092e8fce: Pushed
    8eld9d6700c3: Pushed
    bb7cf9cc89ac: Pushed
    71179539f19f: Pushed
    61a7fb4dabcd:
    Laver already
    exists

[^56]: EXPLORER
    . . .
    amespace.yaml k8-roboshop
    Dockerfile roboshop-docker\\web
    REPOS
    k8-roboshop > web > ! manifest.yaml > {} spec > \[ \] ports > {} 0
    Lalalogue-deploy
    12
    spec :
    > dockerfiles
    19
    template :
    > k8-eksctl
    25
    spec :
    > k8-resources
    26
    containers :
    LillageFullFullly . Always
    k8-roboshop
    30
    # envFrom:
    > catalogue
    31
    # - configMapRef:
    > debug
    32
    #
    name : catalogue
    > mongodb
    33
    web
    34
    apiVersion: v1
    > static
    35
    kind: Service
    36
    metadata :
    Dockerfile
    37
    name : web
    ! manifest.yaml
    U
    38
    namespace: roboshop
    roboshop.conf
    39
    spec :
    ! namespace.yaml
    40
    type: LoadBalancer
    > roboshop-ansible-roles
    41
    selector:
    > roboshop-ansible-rol.
    42
    app: web
    43
    > roboshop-docker
    project: roboshop
    44
    tier: web
    > roboshop-infra-dev
    I
    45
    ports :
    > roboshop-infra-prod
    46
    protocol: TCP
    > roboshop-shared-libr... .
    47
    port: 80 #service-port
    48
    targetPort: 80 #container-port

[^57]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 1cb6f26\] jenkins
    1 file changed, 48 insertions (+)
    create mode 100644 web/manifest. yaml

[^58]: 3. 95. 173. 185 \| 172.31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/web \]$ kubectl apply -f manifest. yaml
    deployment . apps/web created
    service/web created

[^59]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/web \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-wxt6b
    1/1
    Running
    O
    7m44s
    debug
    1/1
    Running
    0
    23m
    mongodb-778f7b57d5-5wm2j
    1/1
    Running
    8m4s
    web-767bd4bbcf-bgr7r
    1/1
    Running
    7s

[^60]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/web \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AC
    catalogue
    ClusterIP
    10 . 100 . 221 . 184
    <none>
    8080/TCP
    7n
    50s
    mongodb
    ClusterIP
    10 . 100 . 21 . 190
    <none>
    27017/TCP
    10s
    web
    LoadBalancer
    10 . 100 .165. 179
    a9574150bbb7c4a9c800035185c634db-1567090876. us-east-1. elb. amazonaws . com
    80:32272/TCP
    13

[^61]: Elastic Block Store
    Listeners
    Network mapping
    Security
    Health checks
    Target instances
    Monitoring
    Attributes
    Tags
    Volumes
    Snapshots
    Lifecycle Manager
    Target instances (3)
    Connection draining: Off
    C
    Deregister
    Manage instances
    Instances currently registered to your load balancer are displayed. To deregister instances, select them, then choose Deregister. To register and deregister instances simultaneously, choose Manage instances.
    Network & Security
    Security Groups
    Q Filter target instances
    <
    1 >
    Elastic IPs
    O
    Instance ID
    A
    Name
    Health status
    Health status descri...
    Security groups
    Placement Groups
    Key Pairs Jim
    O
    i-0a5d313a33fb34f17
    roboshop-spot-Node
    Out-of-service
    Instance registration is...
    eks-cluster-sg-roboshop-5427
    Network Interfaces
    i-056053b5ec69f3c89
    roboshop-spot-Node
    Out-of-service
    Instance registration is...
    eks-cluster-sg-roboshop-5427
    Load Balancing
    i-060f65e8e26c3a5f8
    roboshop-spot-Node
    Out-of-service
    Instance registration is...
    eks-cluster-sg-roboshop-5427
    Load Balancers

[^62]: Details
    EC2 Dashboard
    X
    EC2 Global View
    Security group name
    Security group ID
    Description
    VPC ID
    Events
    eks-cluster-sg-roboshop-
    sg-041c87960ddf934d4
    EKS created security group
    ypc-006ef3c0623373cd4 \[
    Console-to-Code Preview
    542726848
    applied to ENI that is attached to EKS
    Control Plane master nodes, as well as
    Instances
    any managed workloads.
    Instances
    Owner
    Inbound rules count
    Outbound rules count
    Instance Types
    315069654700
    2 Permission entries
    1 Permission entry
    Launch Templates
    Spot Requests
    Savings Plans
    Inbound rules
    Outbound rules
    Tags
    Reserved Instances
    Dedicated Hosts
    Capacity Reservations
    Inbound rules (2)
    C
    Manage tags
    Edit inbound rules
    New
    Q Search
    Images
    AMIs
    Protocol
    4
    Port range
    4
    Source
    Description
    AMI Catalog
    All
    sg-Obeb057464c1df8ea / eksctl-roboshop-cluster-ClusterSharedNodeSecurityGroup-...
    Elastic Block Store
    ALL
    All
    sg-041c87960ddf934d4 / eks-cluster-sg-roboshop-542726848
    Volumes

[^63]: Security group rule ID
    Type Info
    Protocol Info
    Port range
    Source Info
    Description - optional Info
    Info
    sgr-04a 16d47093e8cfbo
    All traffic
    All
    All
    Custom
    Q
    Delete
    sg-Obeb057464c1df8ea X
    sgr-075bf840721e28412
    All traffic
    All
    All
    Custom
    Q
    Delete
    sg-041c87960ddf934d4 X
    sgr-0b78ab26fa87a5c8c
    All traffic
    All
    All
    Custom
    Q
    Delete
    sg-0b06bbc1c7a5889c0 X
    All traffic
    All
    All
    Anyw...
    Q p.0.0.0/0
    Delete
    0.0.0.0/0 X
    Add rule

[^64]: Load balancers (1/1)
    G
    Actions
    Create load balancer
    V
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Q Filter load balancers
    <
    V
    Name
    DNS name
    State
    4
    VPC ID
    Availability Zones
    Type
    a9574150bbb7c4a9c8...
    a9574150bbb7c4a9c800035185c634d...
    vpc-006ef3c0623373cd4
    2 Availability Zones
    classic
    =
    Load balancer: a9574150bbb7c4a9c800035185c634db
    X
    Instances currently registered to your load balancer are displayed. To deregister instances, select them, then choose Deregister. To register and deregister instances simultaneously, choose Manage instances.
    Q Filter target instances
    < 1 >
    O
    Instance ID
    4
    Name
    Health status
    Health status descri... v Security groups
    O
    i-0a5d313a33fb34f17
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542
    O
    i-056053b5ec69f3c89
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542
    0
    i-060f65e8e26c3a5f8
    roboshop-spot-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542

[^65]: F
    C
    A Not secure a9574150bbb7c4a9800035185c634db-1567090876.us-east-1.elb.amazonaws.com
    Stan's Robot Shop
    Login / Register
    Welcome to Stan's Robot Shop
    Cart
    Here you will find all of Stan's friends. Have a browse around and
    Empty
    see who is here.
    Categories
    This is a simple example microservices ecommerce application. It
    has been built using various technologies:
    AngularJS (1.x)
    . Nginx
    NodeJS
    Java
    Python
    .
    Golang
    PHP (Apache)
    MongoDB
    Redis
    . MySQL
    When deployed into an environment monitored by Instana, these
    technology stacks will be automatically detected and monitored,
    all with minimum configuration. Every request will be traced end to
    end. Stan will keep an eye on all those metrics, events and traces
    and let you know what needs your attention.
    To find out more visit the Instana site.
    All the code is available on Github.

[^66]: EXPLORER
    . . .
    er.js k8-roboshop\\.
    ! manifest.yaml ..\\mongodb
    !
    namespace.yaml k8-roboshop
    ! manifest.yaml
    V REPOS
    k8-roboshop > redis > ! manifest.yaml > {} spec > \[ \] ports > {} 0 > # targetPort
    > archieve
    10
    spec :
    > catalogue
    17
    template:
    23
    spec:
    > catalogue-deploy
    28
    > dockerfiles
    29
    apiVersion: v1
    > k8-eksctl
    30
    kind: Service
    > k8-resources
    31
    metadata:
    32
    name: redis
    k8-roboshop
    33
    namespace: roboshop
    > catalogue
    34
    spec :
    > debug
    35
    selector :
    > mongodb
    36
    app: redis
    v redis
    37
    project: roboshop
    ! manifest.yaml \~
    U
    38
    tier: db
    39
    >
    web
    ports:
    40
    protocol: TCP
    ! namespace.yaml
    T
    41
    port: 6379 #service-port
    > roboshop-ansible-roles
    42
    targetPort: 6379 #container-port
    > roboshop-ansible-rol.
    43
    > roboshop-docker

[^67]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add .
    git commit -m
    "jenkins"; git push origin main
    \[main 426367f\] jenkins

[^68]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/web \]$ cd . ./redis/
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/redis \]$ kubectl apply -f manifest. yaml
    deployment . apps/redis created
    service/redis created
    3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/redis \]$

[^69]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/redis \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-wxt6b
    1/1
    Running
    O
    24m
    debug
    1/1
    Running
    0
    40m
    mongodb-778f7b57d5-5wm2j
    1/1
    Running
    0
    24m
    redis-86d966bb7-lvfnn
    1/1
    Running
    5s
    web-688fccdc4c-q6121
    1/1
    Running
    2m25s

[^70]: 3. 95. 173.185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/redis \]$ kubectl exec -it debug -- bash
    \[root@debug /\]# telnet redis 6379
    Trying 10.100.74.252 ...
    Connected to redis.
    Escape character is '^\]'.

[^71]: EXPLORER
    . . .
    erfile roboshop-docker\\user M
    Dockerfile ka-roboshop\\user U X JS server.js .. \\user U
    V REPOS
    460 6 8-roboshop > user > Dockerfile > ..
    > .github
    H
    FROM node : 18. 19. 1-alpine3. 19
    > archieve
    2
    EXPOSE 8080
    3
    > catalogue
    RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    4
    WORKDIR /opt/server
    > catalogue-deploy
    5
    RUN chown roboshop: roboshop /opt/server
    > dockerfiles
    16
    USER roboshop
    > k8-eksctl
    7
    COPY package. json /opt/server/
    > k8-resources
    18
    COPY server . js /opt/server/
    k8-roboshop
    9
    RUN npm install
    10
    > catalogue
    CMD \["node", "server. js"\]
    > debug
    > mongodb
    > redis
    V user
    Dockerfile
    U
    I
    {} package.json -
    U
    JS server.js -
    U

[^72]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add .
    git commit -m
    "jenkins"; git push origin main
    \[main 426367f\] jenkins

[^73]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/user \]$ docker build -t joindevops/user:v1 .
    \[+\] Building 1.3s (11/12)
    \[internal\] load build definition from Dockerfile
    => => transferring dockerfile: 3148
    \[internal\] load metadata for docker. 10/library/node: 18.19. 1-alpine3. 19
    > \[auth\] library/node: pull token for registry-1. docker . io
    \[internal\] load . dockerignore
    => transferring context: 28

[^74]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/user \]$ docker push joindevops/user:v1
    The push refers to repository \[docker . io/joindevops/user\]
    3d9dde4beSeb: Pushing \[=
    5. 746MB/28 . 74MB
    22fb782da21c: Pushing
    11 . 78kB
    f4e49974ale3: Pushing \[
    3. 584KB
    al7d6bf7230b: Preparing
    7d73c8f030f6: Preparing
    b4aff2fb3b86: Waiting

[^75]: EXPLORER
    . .
    M
    Dockerfile k8-roboshop\\user
    JS server.js . \\user
    {} pack
    REPOS
    k8-roboshop > user > ! manifest.yaml > {} spec > {} template > {} spec
    > dockerfiles
    18
    spec :
    > k8-eksctl
    25
    template :
    LLCI .
    app
    > k8-resources
    31
    spec :
    k8-roboshop
    32
    containers :
    catalogue
    33
    name: user
    34
    Dockerfile
    image: joindevops/user : v1
    35
    imagePullPolicy: Always
    ! manifest.yaml
    36
    envFrom:
    {} package.json
    37
    - configMapRef :
    JS server.js
    38
    name: user
    > debug
    39
    > mongodb
    40
    apiVersion: v1
    41
    > redis
    kind: Service
    42
    metadata:
    user
    43
    name: user
    Dockerfile
    44
    namespace: roboshop
    ! manifest.yaml
    U
    45
    spec :
    {} package.json
    46
    selector :
    JS server.js
    47
    app: user
    > web
    48
    project: roboshop
    49
    tier: app
    ! namespace.yaml
    50
    ports :
    > roboshop-ansible-roles
    51
    protocol: TCP
    OUTLINE
    52
    port: 8080 #service-port

[^76]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add .
    git commit -m
    "jenkins"; git push origin main
    \[main 426367f\] jenkins

[^77]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/user \]$ kubectl apply -f manifest. yaml
    configmap/user created
    deployment . apps/user created
    service/user created

[^78]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/user \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    catalogue-79dd48d65f-wxt6b
    1/1
    Running
    29m
    debug
    1/1
    Running
    4 4m
    OOOO
    mongodb-778f7b57d5-5wm2j
    1/1
    Running
    29m
    redis-86d966bb7-1vinn
    1/1
    Running
    4m42s
    user-796496c69f-425js
    1/1
    Running
    4s
    web-688fccdc4c-q6121
    1/1
    Running
    O
    7m2s

[^79]: C
    A Not secure a76dd344186834a5da109f0a59438c8c-115129
    Stan's Robot Shop
    Login / Register
    Cart
    Greetings siva
    Empty
    Email - siva@jondevops.com
    Categories
    . Artificial
    Order History
    Intelligence
    Order ID Items Total
    .
    Robot
    Siva

[^80]: L
    EXPLORER
    . . .
    mongodb
    ! namespace.yaml k8-roboshop
    JS server.js .. \\cart
    Dockerfile k8-roboshop\\cart U X
    V REPOS
    k8-roboshop > cart > Dockerfile > ...
    archieve
    FROM node : 18. 19. 1-alpine3. 19
    > catalogue
    2
    EXPOSE 8080
    3
    > catalogue-deploy
    RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
    4
    WORKDIR /opt/server
    > dockerfiles
    15
    RUN chown roboshop: roboshop /opt/server
    > k8-eksctl
    6
    USER roboshop
    > k8-resources
    7
    COPY package. json /opt/server/
    k8-roboshop
    8
    COPY server . js /opt/server/
    cart
    9
    RUN npm install
    Dockerfile
    U
    10
    CMD \["node", "server . js" \]
    {} package.json
    -
    U
    JS server.js
    U

[^81]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add .
    git commit -m
    "jenkins"; git push origin main
    \[main 426367f\] jenkins

[^82]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/cart \]$ docker build -t joindevops/cart:v1 .
    \[+\] Building 0.5s (11/12)
    \[internal\] load build definition from Dockerfile
    => transferring dockerfile: 3148
    =>
    \[internal\] load metadata for docker . 10/library/node: 18. 19. 1-alpine3. 19
    (auth\] library/node: pull token for registry-1. docker . io
    \[internal\] load . dockerignore

[^83]: 3. 95. 173. 185 \| 172. 31.93.8 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/cart \]$ docker push joindevops/cart:v1
    The push refers to repository \[docker . io/joindevops/cart\]
    690ec0f776b3: Pushing \[
    24 . 13MB/33 . 78MB
    6b32191950ff: Pushing
    14 . 34KB
    226d957fb801: Pushing \[
    3. 584kB
    a17d6bf7230b: Mounted from joindevops/user
    7d73c8f030f6 :
    Mounted
    joindevops/user

[^84]: EXPLORER
    ! manifest.yaml ..\\catalogue
    {} package.json .\\cart
    manif
    REPOS
    k8-roboshop > cart > ! manifest.yaml > .
    > archieve
    1
    apiVersion: v1
    catalogue
    2
    kind: ConfigMap
    3
    > catalogue-deploy
    metadata :
    4
    name : cart
    > dockerfiles
    5
    namespace: roboshop
    > k8-eksctl
    6
    data:
    k8-resources
    7
    MONGO: "true"
    k8-roboshop
    8
    T
    cart
    9
    apiVersion: apps/v1
    Dockerfile
    10
    kind: Deployment
    11
    ! manifest.yaml
    metadata :
    U
    12
    name: cart
    \[) package.json
    13
    namespace: roboshop
    JS server.js
    14
    labels: # these labels are deployment labels
    catalogue
    15
    app: cart
    Dockerfile
    16
    project: roboshop
    ! manifest.yaml
    17
    tier : app
    18
    {} package.json
    spec :
    19
    replicas: 1
    JS server.js
    20
    selector :
    > debug
    21
    matchLabels: # these labels are used to find
    > mongodb
    22
    app: cart
    > redis
    23
    project: roboshop
    > OUTLINE
    24
    tier: app
    25
    template :

[^85]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add .
    git commit -m
    "jenkins"; git push origin main
    \[main 426367f\] jenkins

[^86]: 3. 95. 173. 185 \| 172.31.93.8 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-93-8 \~/k8-roboshop/cart \]$ kubectl apply -f manifest. yaml
    configmap/cart created
    deployment . apps/cart created
    service/cart created

[^87]: C
    A Not secure a76dd344186834a5da109f0a59438c8c-1151294800.us-east-1.elb.amazonaws.com/cart
    Stan's Robot Shop
    Login / Register
    Shopping cart for anonymous-3
    QTY
    Name Sub Total
    Cart
    Stan
    (67.00
    (67.00
    Categories
    Inc Tax
    (11.17
    . Artificial
    Total
    C67.00
    Intelligence
    Checkout
    .
    Robot
    o C3PO
    o Eve
    o
    K9
    Kryten

[^88]: 44 . 211 . 248.243 \| 172. 31. 94.116 \| t2. micro \| null
    \[ centos@ip-172-31-94-116 \~ \]$ git clone https: //github. com/daws-76s/k8-roboshop . git
    Cloning into 'k8-roboshop' . .
    remote: Enumeratiog objects: 120, done.
    remote: Counting objects: 100% (120/120) , done.
    remote: Compressing objects: 100% (104/104) , done.
    remote: Total 120 (delta 40) , reused 93 (delta 13) , pack-reused 0
    1008
    (120/120)
    09 MIR
    38 15
    MiB/s

[^89]: 44 . 211 . 248.243 \| 172 . 31 .94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop \]$ kubectl apply -f namespace . yaml
    namespace/roboshop created
    44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop \]$ cd mongodb/
    44 . 211 . 248.243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/mongodb \]$ kubectl apply -f manifest. yaml
    deployment . apps/mongodb created
    service/mongodb created

[^90]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2. micro \| null
    \[ centos@ip-172-31-94-116 \~ \]$ sudo git clone https: //github. com/ahmetb/kubectx /opt/kubectx
    Cloning into ' /opt/kubectx' .. .
    remote: Enumeratiog objects: 1502, done.
    remote: Counting objects: 100% (452/452) , done.
    remote: Compressing objects: 100% (98/98) , done.
    remote: Total 1502 (delta 390) , reused 355 (delta 353) , pack-reused 1050
    Receiving objects: 100% (1502/1502) , 912. 88 KiB \| 23.41 MiB/s, done.
    Resolving deltas: 100% (876/876), done.
    44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2. micro \| null
    \[ centos@ip-172-31-94-116 \~ \]$ sudo In -s /opt/kubectx/kubens /usr/local/bin/kubens

[^91]: 44 . 211 . 248.243 \| 172. 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop \]$ kubens roboshop
    Context "terraform@roboshop. us-east-1. eksctl. io" modified.
    Active namespace is "roboshop" .
    44 . 211 . 248.243 \| 172. 31.94.116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    mongodb-778f7b57d5-pw87m
    1/1
    Running
    0
    62s

[^92]: 44 . 211 . 248.243 \| 172. 31 . 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/redis \]$ kubectl apply -f manifest. yaml
    deployment . apps/redis created
    service/redis created

[^93]: 44 . 211 . 248. 243 \| 172. 31. 94. 116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/redis \]$ cd . ./catalogue/
    44 . 211 . 248.243 \| 172 . 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/catalogue \]$ kubectl apply -f manifest. yaml
    configmap/catalogue created
    deployment . apps/catalogue created
    service/catalogue created

[^94]: 44 . 211 . 248.243 \| 172 . 31 .94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/catalogue \]$ cd . ./user/
    44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/user \]$ kubectl apply -f manifest. yaml
    configmap/user created
    deployment . apps/user created
    service/user created

[^95]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/user \]$ cd . ./cart/
    44 . 211 . 248. 243 \| 172 . 31. 94.116 \| t2. micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/cart \]$ kubectl apply -f manifest. yaml
    configmap/cart created
    deployment . apps/cart created
    service/cart created

[^96]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos(ip-172-31-94-116 \~/k8-roboshop/cart \]$ cd . ./web/
    44 . 211 . 248.243 \| 172. 31.94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/web \]$ kubectl apply -f manifest. yaml
    configmap/web created
    deployment . apps/web created
    service/web created

[^97]: 44 . 211 . 248.243 \| 172 . 31. 94. 116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/web \]$ kubectl get svc
    NAME
    TYPE
    CLUSTER-IP
    EXTERNAL-IP
    PORT (S)
    AGE
    cart
    ClusterIP
    10 . 100 . 178.235
    <none>
    8080/TCP
    10s
    catalogue
    ClusterIP
    10. 100 . 66.83
    <none>
    8080/TCP
    29s
    mongodb
    ClusterIP
    10 . 100 . 170 . 76
    <none>
    27017/TCP
    111
    redis
    ClusterIP
    10 . 100 . 162 .54
    <none>
    6379/TCP
    37s
    user
    ClusterIP
    10 . 100 .127.251
    <none>
    8080/TCP
    22s
    web
    LoadBalancer
    10 . 100 .35.202
    a02cfbf1d0e084e5492c76413b567d00-330447210. us-east-1. elb . amazonaws . com
    80: 31095/TCP
    5s

[^98]: aws
    Services
    Q Search
    \[Alt+S\]
    4
    (?)
    N. Virginia
    joind
    CO VPC
    RDS
    $3
    Elastic Kubemetes Service
    CloudFormation
    Route 53
    BEFS
    25 LAM
    EC2
    Certificate Manager
    CloudFront
    Billing and Cost Management
    Capacity Reservations
    302cfbf Id0e084e5492c/6413656/d00-33044/210.us-east- 1.elb.amazonaws.com (A Record)
    New
    Images
    This Classic Load Balancer can be migrated to a next generation load balancer. Migration wizard uses your load balancer's
    Launch migration wizard
    X
    current configurations to create a new load balancer. Learn more
    AMIs
    AMI Catalog
    Distribution of targets by Availability Zone (AZ)
    Elastic Block Store
    For each enabled Availability Zone, you can view the number of registered instances and their current health states. Selecting any values here will apply the corresponding filter to the Target instances
    table.
    Volumes
    Snapshots
    Lifecycle Manager
    Listeners
    Network mapping
    Security
    Health checks
    Target instances
    Monitoring
    Attributes
    Tags
    Network & Security
    Security Groups
    Target instances (3)
    Connection draining: Off
    G
    Deregister
    Manage instances
    Elastic IPs
    Instances currently registered to your load balancer are displayed. To deregister instances, select them, then choose Deregister. To register and deregister instances simultaneously, choose Manage instances.
    Placement Groups
    Key Pairs
    Q Filter target instances
    < 1 >
    Network Interfaces
    O
    Instance ID
    A
    Name
    Health status
    Health status descri...
    Security groups
    Load Balancing
    i-029423fb962a887f6
    roboshop-spot-1c-Node
    Out-of-service
    Instance registration is...
    eks-cluster-sg-roboshop-5427
    Load Balancers
    O
    i-073e5a766393ed09f
    roboshop-spot-1c-Node
    Out-of-service
    Instance registration is...
    eks-cluster-sg-roboshop-5427
    Target Groups
    Trust Stores New
    i-045cbbda20c5f4540
    roboshop-spot-1c-Node
    Out-of-service
    Instance registration is...
    eks-cluster-sg-roboshop-5427

[^99]: Instances (1/7) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    V
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    < 1 >
    Name
    4
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Alarm status
    Availability Z
    roboshop-spot-Node
    i-025b25b5f267afe64
    Terminated @ @ m5.large
    View alarms +
    us-east-1c
    roboshop-spot-1c-Node
    i-029423fb962a887f6
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1c
    O
    roboshop-spot-1c-Node
    i-073e5a766393ed09f
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1c
    O
    roboshop-spot-1c-Node
    i-045cbbda20c5f4540
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1c
    O
    roboshop-spot-Node
    i-08af5aa68ad200731
    Terminated Q Q m5.large
    View alarms +
    us-east-1a
    . .... -I -.
    Instance: i-029423fb962a887f6 (roboshop-spot-1c-Node)
    X
    Security details
    IAM Role
    Owner ID
    Launch time
    eksctl-roboshop-nodegroup-spot-1c-NodeInstanceRole-
    315069654700
    Tue Feb 27 2024 07:03:34 GMT+0530 (India Standard Time)
    xDVUMcFPnnvw \[
    Security groups
    sg-05b52 1f19fdbdd13 (eks-cluster-sg-roboshop-
    542726848)

[^100]: Inbound rules Info
    Security group rule ID
    Type Info
    Protocol Info
    Port range
    Source Info
    Description - optional Info
    Info
    sgr-02da6830b3e10526a
    All traffic
    All
    All
    Custom
    Delete
    sg-Oac9b16e93aa3b0e7 X
    sgr-091e857b96d4fdd5b
    All traffic
    All
    All
    Custom
    Q
    Allow unmanaged nodes to co
    Delete
    Allow unmanaged nodes to
    sg-01486d7834175ale6 X
    communicate with control plane (all
    ports)
    sgr-Ofcb4458f960c3ccd
    All traffic
    All
    All
    Custom
    Delete
    sg-05b52cff19fdbdd13 X
    All traffic
    All
    All
    Anyw...
    Q 0.0.0.0/0
    Delete
    0.0.0.0/0 X
    Add rule

[^101]: EC2 > Load balancers
    Load balancers (1/1)
    C
    Actions
    Create load balancer
    A
    Elastic Load Balancing scales your load balancer capacity automatically in response to changes in incoming traffic.
    Q Filter load balancers
    <
    1 >
    V
    Name
    DNS name
    State
    VPC ID
    Availability Zones
    Type
    V
    a02cfbf 1doe084e549...
    a02cfbf 1doe084e5492c76413b567do0...
    vpc-0350be968a71e4...
    2 Availability Zones
    classic
    Load balancer: a02cfbf1d0e084e5492c76413b567do0
    X
    Instances currently registered to your load balancer are displayed. To deregister instances, select them, then choose Deregister. To register and deregister instances simultaneously, choose Manage instances.
    Q Filter target instances
    <
    1
    O
    Instance ID
    Name
    Health status
    Health status descri...
    Security groups
    i-029423fb962a887f6
    roboshop-spot-1c-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542
    O
    i-073e5a766393ed09f
    roboshop-spot-1c-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542
    0
    i-045cbbda20c5f4540
    roboshop-spot-1c-Node
    In-service
    Not applicable
    eks-cluster-sg-roboshop-542

[^102]: C
    A Not secure a02cfbf1d060845492c764136567d00-330447210.us-east-1.elb.amazonaws.com/cart
    Stan's Robot Shop
    Login / Register
    Shopping cart for anonymous-1
    QTY Name Sub Total
    Cart
    Stan
    E67.00
    (67.00
    Categories
    Inc Tax
    (11.17
    . Artificial
    Total
    (67.00
    Intelligence
    Checkout
    . Robot
    o C3PO
    o Eve
    o K9
    o Kryten
    o Marvin
    o Mr Data
    o R2D2
    o Robbie
    o Stan
    anonymous-1

[^103]: V REPOS
    k8-roboshop > mysql > > Dockerfile > ...
    1
    FROM mysql :5.7
    > archieve
    2
    COPY scripts/\* /docker-entrypoint-initdb. d/
    > catalogue
    > catalogue-deploy
    > dockerfiles
    > k8-eksctl
    > k8-resources
    k8-roboshop
    > cart
    > catalogue
    > debug
    > mongodb
    v mysql
    scripts
    shipping.sql -
    U
    Dockerfile
    -
    U
    > redis
    > shipping

[^104]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    On branch main
    nothing to commit, working tree clean
    Enumeratiog objects: 26, done.
    Counting objects: 100% (26/26), done.
    Delta compression using up to 8 threads

[^105]: 44 . 211 . 248.243 \| 172 . 31. 94. 116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/mysql \]$ docker build -t joindevops/mysql :v1 .
    \[+\] Building 1.3s (4/7)
    docker : defaul
    \[internal\] load build definition from Dockerfile
    0. C
    > transferring dockerfile: 968
    0.0
    \[internal\] load metadata for docker . 10/library/mysql :5. 7
    0.4
    (auth\] library/mysql : pull token for registry-1 . docker . io
    0.0
    \[internal\] load . dockerignore
    0.0
    > transferring context: 28
    0. 0
    \[internal\] load build context
    0 . 8
    => transferring context: 23. 11MB
    0 . 8
    \[1/2\] FROM docker . io/library/mysql : 5. 7@sha256: 4bc6bc963ed8443453676cae56536f4b8156d78bae03c0145cbe47c2aad73bb
    0 . 8
    resolve docker . 10/library/mysql : 5. 70sha256: 4bc6bo963e6d8443453676cae565361468156d78bae0300145cbe47c2aad73bb
    0. 0
    >sha256: dab0a802b44617303694fb17d166501de27903031ddeb28056ecf7fcabSef0da 2. 74kB / 2. 74KB
    0.0
    sha256: 5107333082872836d48ff7528ble84b9086781cc91748bbc1b8042a870d933 7. 19kB / 7. 19KB
    0.0
    -> sha256: 4bc6bo9636d8443453676cae5653614b8156d78bae0300145cbe47c2aad73bb 1. 01kB
    / 1.01KB
    0. 0

[^106]: 44 . 211 . 248.243 \| 172. 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/mysql \]$ docker push joindevops/mysql :v1
    The push refers to repository \[docker . io/joindevops/mysql\]
    73a12938fb00: Pushing \[==
    \] 11. 67MB/64 . 58MB
    441e16cac4fe: Layer already exists
    73cb62467b8f: Layer already exists
    337ec6bae222: Layer already exists
    532b66f4569d: Layer already exists
    0dge9a9ce9e4: Waiting
    4555572a6bb2: Layer already exists

[^107]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ echo -n RoboShop@1 \| base64
    Um9ib1Nob 3BAMQ==

[^108]: EXPLORER
    . . .
    anifest.yaml .. \\mongodb
    ! namespace.yaml k8-roboshop
    Dockerfile ..\\mysql
    ! manifest.yaml .. \\m
    REPOS
    k8-roboshop > mysql > ! manifest.yaml > {} data > MYSQL_DATABASE
    k8-resources
    1
    apiVersion: v1
    02-pods
    2
    kind: ConfigMap
    3
    metadata:
    ! 08-pod-config.yaml
    4
    name : mysql
    ! 09-secrets.yaml
    5
    namespace: roboshop
    ! 10-pod-secrets.yaml
    6
    data:
    > service
    7
    MYSQL_DATABASE: "cities"
    8
    > sets
    9
    apiVersion: v1
    k8-roboshop
    10
    kind: Secret
    > cart
    11
    metadata:
    > catalogue
    12
    name : mysql
    > debug
    13
    namespace: roboshop I
    > mongodb
    14
    type: Opaque
    mysql
    15
    data:
    16
    MYSQL_ROOT_PASSWORD: Um9ib1Nob3BAMQ==
    scripts
    17
    MYSQL_USER: c2hpcHBpbmc=
    shipping.sql
    18
    MYSQL_PASSWORD: Um9ib1Nob3BAMQ==
    Dockerfile
    19
    ! manifest.yaml
    -
    U
    20
    apiVersion: apps/v1
    > redis
    21
    kind: Deployment -
    > shipping
    22
    metadata:
    23
    > user
    name : mysql
    > OUTLINE
    24
    namespace: roboshop

[^109]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 7056685\] jenkins
    1 file changed, 66 insertions (+)
    create mode 100644 mysql/manifest. yam1

[^110]: 44 . 211 . 248.243 \| 172 . 31 . 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/mysql \]$ kubectl apply -f manifest. yaml
    configmap/mysql created
    secret/mysql created
    deployment . apps/mysql created
    service/mysql created

[^111]: 44 . 211 . 248 . 243 \| 172. 31. 94.116 \| t2. micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/mysql \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    cart-5fcfbccbf5-jp4nl
    1/1
    Running
    13m
    OO
    catalogue-79dd48d65f-h747p
    1/1
    Running
    14m
    mongodb-778f7b57d5-pw87m
    1/1
    Running
    15m
    mysql-7f4b445856-wg15v
    1/1
    Running
    O
    16s
    redis-86d966bb7-kmxzw
    1/1
    Running
    14m
    user-796496c69f-ztp7s
    1/1
    Running
    13m
    web-688fccdc4c-8ds62
    1/1
    Running
    13m

[^112]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/mysql \]$ kubectl exec -it mysql-7f4b445856-wg15v -- bash
    bash-4. 2# mysql -u shipping -pRoboshop@1
    mysql: \[Warning\] Using a password on the command line interface can be insecure.
    Welcome to the MySQL monitor. Commands end with ; or \\g.
    Your MySQL connection id is 9
    Server version: 5.7.44 MySQL Community Server (GPL)
    Copyright (c) 2000, 2023, Oracle and/or its affiliates.
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners .
    Type 'help; ' or ' \\h' for help. Type ' \\c' to clear the current input statement.
    mysql>

[^113]: mysql> show databases;
    No connection. Trying to reconnect...
    Connection id:
    2
    Current database: \* \* \* NONE
    \| Database
    +
    information schema
    cities
    +
    2 rows in set (0.00 sec)
    mysql>

[^114]: mysql> use cities;
    Reading table information for completion of table and column names
    You can turn off this feature to get a quicker startup with -A
    Database changed
    mysql> show tables;
    +
    Tables in cities \|
    cities
    codes
    2 rows in set (0.00 sec)
    mysql> exit

[^115]: V REPOS
    4 60 6 8-roboshop > shipping > Dockerfile > .
    > .github
    1
    > archieve
    2
    #Build
    3
    > catalogue
    4
    FROM maven AS build
    > catalogue-deploy
    15
    > dockerfiles
    6
    WORKDIR /opt/shipping
    > k8-eksctl
    7
    > k8-resources
    8
    COPY pom. xml /opt/shipping/
    k8-roboshop
    9
    RUN mvn dependency : resolve
    10
    > cart
    COPY src /opt/shipping/src/
    11
    RUN mvn package
    > catalogue
    12
    > debug
    13
    #
    mongodb
    14
    # Run
    > redis
    15
    shipping
    16
    FROM openjdk :8-jre-alpine3.9
    > src \\ main
    -
    17
    18
    EXPOSE 8080
    Dockerfile -
    U
    19
    pom.xml -
    U
    20
    WORKDIR /opt/shipping
    > user
    21
    > web
    22
    COPY --from=build /opt/shipping/target/shipping-1.0. jar shipping. jar
    ! namespace.yaml
    23
    > OUTLINE
    24
    CMD \[ "java", " -Xmn256m", " -Xmx768m", "-jar", "shipping. jar" \]

[^116]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    On branch main
    nothing to commit, working tree clean
    Enumeratiog objects: 26, done.
    Counting objects: 100% (26/26), done.
    Delta compression using up to 8 threads

[^117]: 44 . 211 . 248.243 \| 172 . 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/shipping \]$ docker build -t joindevops/shipping:v1
    \[+\] Building 0. 4s (2/3)
    docker : d
    \[internal) load build definition from Dockerfile
    transferring dockerfile; 4018
    => \[internal\] load metadata for docker . io/library/openjak: 8-jre-alpine3. 9

[^118]: 44 . 211 . 248 . 243 \| 172. 31. 94.116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/shipping \]$ docker login
    Log in with your Docker ID or email address to push and pull images from Docker Hub. If you don't have a
    / /hub . docker . com/ to create one.
    You can log in with your password or a Personal Access Token (PAT) . Using a limited-scope PAT grants bett
    r organizations using SSO. Learn more at https: / /docs . docker . com/go/access-tokens/
    Username: joindevops
    Password:

[^119]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/shipping \]$ docker push joindevops/shipping: v1
    The push refers to repository \[docker . io/joindevops/shipping\]
    5454241cfefb: Pushing \[===
    41 . 49MB
    26038c782ab2: Pushed
    edd61588d126: Layer already exists
    9b9b7f3d56a0: Layer already exists

[^120]: EXPLORER
    . . .
    amespace.yaml k8-roboshop
    Dockerfile k8-roboshop\\shipping
    pom.xml
    ! manifest.yan
    REPOS
    k8-roboshop > shipping > ! manifest.yaml > {} data > . DB_HOST
    / Ko-EKSCU
    1
    apiVersion: v1
    > k8-resources
    2
    kind: ConfigMap
    k8-roboshop
    3
    metadata:
    > cart
    4
    name: shipping
    > catalogue
    5
    namespace: roboshop
    > debug
    6
    data :
    7
    CART_ENDPOINT: "cart : 8080"
    > mongodb
    8
    DB_HOST: mysql
    > redis
    9
    shipping
    10
    apiVersion: apps/v1
    src
    11
    kind: Deployment
    Dockerfile
    12
    metadata :
    ! manifest.yaml
    U
    13
    name: shipping
    14
    pom.xml
    namespace: roboshop
    15
    labels: # these labels are deployment labels
    ) user
    16
    app: shipping
    > web
    17
    project: roboshop
    ! namespace.yaml
    18
    tier: app
    > roboshop-ansible-roles
    19
    spec:
    > roboshop-ansible-rol.
    20
    replicas: 1
    roboshop-docker
    21
    selector:
    22
    matchLabels: # these labels are used to find the pods
    > cart
    23
    app: shipping
    I
    > OUTLINE
    24
    project: roboshop
    25
    tier: app

[^121]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    On branch main
    nothing to commit, working tree clean
    Enumeratiog objects: 26, done.
    Counting objects: 100% (26/26), done.
    Delta compression using up to 8 threads

[^122]: 44 . 211 . 248. 243 \| 172 . 31. 94.116 \| t2. micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/shipping \]$ kubectl apply -f manifest. yaml
    configmap/shipping created
    deployment . apps/shipping created
    service/shipping created

[^123]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/shipping \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    cart-5fcfbccbf5-jp4nl
    1/1
    Running
    15m
    catalogue-79dd48d65f-h747p
    1/1
    Running
    15m
    mongodb-778f7b57d5-pw87m
    1/1
    Running
    16m
    mysql-7f4b445856-wg15v
    1/1
    Running
    102s
    redis-86d966bb7-kmxzw
    1/1
    Running
    15m
    shipping-8ffd9bc47-ddscv
    1/1
    Running
    4s
    user-796496c69f-ztp7s
    1/1
    Running
    15m
    web-688fccdc4c-8ds62
    1/1
    Running
    15m

[^124]: 44 . 211 . 248.243 \| 172 . 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/shipping \]$ kubectl logs shipping-8ffd9bc47-ddscv

[^125]: 2024-02
    02:07 : 41 . 885
    main\]
    w. embedded .
    TomcatWebse
    Tomcat started
    on port (s) : 8080 (http)
    with context path " '
    2024-02-27 02: 07: 41. 889 INFO 1 --- \[
    main\] DeferredRepositoryInitializationListener : Triggering deferred initialization of
    Spring Data repositories...
    2024-02-27 02: 07: 42. 745 INFO 1
    main\] DeferredRepositoryInitializationListener : Spring Data repositories initialized!
    2024-02-27 02: 07: 42 . 765
    INFO 1
    main\] c. i . r. s. ShippingServiceApplication
    :Started ShippingServiceApplication in
    10. 897 seconds (JVM running for 11. 724)

[^126]: F
    -
    C
    A Not secure a02cfbf1d04084e5492c764136567d00-330447210.us-east-1.elb.amazonaws.com/shipp
    Stan's Robot Shop
    Login/ Register
    Shipping information
    Cart
    Select country Netherlands
    65000.00
    Enter location
    Calculate
    Australia
    Categories
    Austria
    Brasil
    . Artificial
    Bulgaria
    Intelligence
    Canada
    . Robot
    Czech Republic
    Denmark
    . C3PO
    Finland
    Eve
    France
    K9
    Germany
    o Kryten
    Great Britain
    o Marvin
    Hungary
    o Mr Data
    India
    R2D2
    Italy
    o Robbie
    Japan
    Stan
    Netherlands
    Norway
    Portugal
    Romania

[^127]: F
    C
    A Not secure a02cfbf1d06084e5492c764136567d00-330447210.us-east-1.elb.amazonaws.com/payment
    Stan's Robot Shop
    Login / Register
    Review your order
    Cart
    QTY
    Name
    Sub Total
    (5446.25
    1
    Eve
    E5000.00
    Categories
    1
    shipping to India Hyderabad-Deccan C446.25
    . Artificial
    Inc Tax
    6907.71
    Intelligence
    Total
    65446.25
    . Robot
    o C3PO
    Pay Now
    o Eve
    O
    K9
    O
    Kryten
    Marvin
    o Mr Data
    o R2D2
    Robbie
    o Stan

[^128]: EXPLORER
    JS server.js ... \\cart
    Dockerfile k8-roboshop\\cart
    ! manifest.yaml ..\\redis
    V REPOS
    k8-roboshop > rabbitmq > ! manifest.yaml > {} spec > \[ \] ports > { } 0 > # targetPort
    > catalogue-deploy
    10
    spec :
    > dockerfiles
    17
    template :
    > k8-eksctl
    23
    spec :
    24
    containers :
    > k8-resources
    25
    - name: rabbitmq
    k8-roboshop
    26
    image: rabbitmq
    > cart
    27
    imagePullPolicy: Always
    > catalogue
    28
    29
    apiVersion: v1
    > debug
    30
    kind: Service
    > mongodb
    31
    metadata :
    > mysql
    32
    name: rabbitmq
    rabbitmq
    33
    namespace: roboshop
    ! manifest.yaml
    U
    34
    spec :
    > redis
    35
    selector :
    36
    > shipping
    app: rabbitmq
    37
    project: roboshop
    > user
    38
    tier: db
    > web
    39
    ports:
    ! namespace.yaml
    40
    - protocol: TCP
    > roboshop-ansible-roles
    41
    port : 5672 #service-port
    > roboshop-ansible-rol.
    42
    targetPort: 5672 #container-port
    roboshop-docker
    43

[^129]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    S git add . ; git commit -m "jenkins"; git push origin main
    \[main a03d544\] jenkins
    1 file changed, 55 insertions (+)
    create mode 100644 rabbitma/manifest. yam1

[^130]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/rabbitmq \]$ kubectl apply -f manifest. yaml
    secret/rabbitmq created
    deployment . apps/rabbitmq created
    service/rabbitmq created
    44 . 211 . 248.243 \| 172. 31. 94.116 \| t2. micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/rabbitmq \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    cart-5fcfbccbf5-jp4nl
    1/1
    Running
    22m
    catalogue-79dd48d65f-h747p
    1/1
    Running
    22m
    mongodb-778f7b57d5-pw87m
    1/1
    Running
    24m
    mysql-714b445856-wg15v
    1/1
    Running
    9m2s
    rabbitmq-697fb559c7-vinbh
    1/1
    Running
    4s
    redis-86d966bb7-kmxzw
    1/1
    Running
    22m
    shipping-8ffd9bc47-ddscv
    1/1
    Running
    7m24s
    user-796496c69f-ztp7s
    1/1
    Running
    22m
    web-688fccdc4c-d4wrv
    1/1
    Running
    5m25s

[^131]: 44 . 211 . 248.243 \| 172. 31. 94.116 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl logs nginx-deployment-5c74df6cbd-2jcd4
    Defaulted container "nginx" out of: nginx, filebeat-sidecar
    / docker-entrypoint. sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
    /docker-entrypoint. sh: Looking for shell scripts in /docker-entrypoint.d/
    /docker-entrypoint. sh: Launching /docker-entrypoint. d/10-listen-on-ipv6-by-default. sh
    10-listen-on-ipv6-by-default. sh: info: Getting the checksum of /etc/nginx/conf .d/default. conf
    10-listen-on-ipv6-by-default. sh: info: Enabled listen on IPV6 in /etc/nginx/conf . d/default. conf
    / docker-entrypoint . sh: Sourcing /docker-entrypoint. d/15-local-resolvers . envsh
    / docker-entrypoint. sh: Launching /docker-entrypoint. d/20-envsubst-on-templates . sh
    / docker-entrypoint . sh: Launching /docker-entrypoint. d/30-tune-worker-processes . sh
    / docker-entrypoint . sh: Configuration complete; ready for start up

[^132]: XJ
    File Edit Selection View Go
    . ..
    repos
    EXPLORER
    provider.tf terraform-provisioners
    Dockerfile roboshop-docker\\payment
    Dockerfile k8-roboshop\\payment U X
    V REPOS
    k8-roboshop > payment > Dockerfile > ..
    > .github
    FROM python : 3.9.18-alpine3. 19
    > archieve
    2
    3
    EXPOSE 8080
    > catalogue
    6 12
    4
    USER root
    > catalogue-deploy
    5
    WORKDIR / app
    > dockerfiles
    6
    COPY requirements . txt /app/
    > k8-eksctl
    7
    RUN apk add python3-dev build-base linux-headers pcre-dev
    > k8-resources
    8
    RUN pip install -r requirements. txt
    k8-roboshop
    9
    COPY \* . py /app/
    10
    > cart
    COPY payment . ini /app/
    11
    #CMD \["python", "payment. py" \]
    > catalogue
    2
    CMD \["uwsgi", "--ini", "payment. ini"\]
    > debug
    13
    > mongodb
    > mysql
    payment -
    Dockerfile -
    U
    payment.ini -
    U
    payment.py \~
    U
    rabbitmq.py
    U

[^133]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main f5fe9f8\] jenkins
    5 files changed, 242 insertions (+)
    create mode 100644 payment/Dockerfile
    create mode 100644 payment/payment. ini
    create mode 100644
    payment /payment py

[^134]: 44 . 211 . 248.243 \| 172 . 31 . 94. 116 \| 2.micro \| https: / /github . com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/payment \]$ docker build -t joindevops/payment: v1
    \[+\] Building 3.2s (8/12)
    docke
    =>
    (internal\] load build definition from Dockerfile
    => => transferring dockerfile: 334B
    =>
    \[internal\] load metadata for docker. 10/library/python : 3. 9. 18-alpine3. 19
    \[auth\] library/python :pull token for registry-1 . docker . io
    \[internal\] load . dockerignore

[^135]: 44 . 211 . 248.243 \| 172 . 31. 94.116 \| t2. micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/payment \]$ docker push joindevops/payment: v1
    The push refers to repository \[docker . io/joindevops/payment\]
    cOf37d526805: Pushing \[=
    2 . 56KB
    e81bd09cf5e0: Pushing
    9 . 728kB
    6210b82f94d0: Pushing
    3. 471MB/25 . 71MB
    16154fe27b1b: Pushing
    9. 908MB/339 . 1MB
    25044c979534: Pushing
    2 . 56kB
    2c5b8d63cd3e: Waiting
    4aa6agee0302: Waiting
    b8d25f9faffb .
    Waitin

[^136]: EXPLORER
    . . .
    ! manifest.yaml . \\payment U X JS serve-
    Dockerfile k8-roboshop\\cart
    REPOS
    k8-roboshop > payment > ! manifest.yaml > { } spec > {} template > {} spec > \[ \] contai
    k8-roboshop
    apiVersion: v1
    Carl
    N
    kind: Secret
    > catalogue
    3
    metadata:
    > debug
    14
    name: payment
    > mongodb
    15
    namespace: roboshop
    > mysql
    6
    type: Opaque
    7
    data:
    payment
    8
    AMOP USER: cmgib3Nob3A=
    Dockerfile
    9
    AMOP_PASS: cm9ib3Nob3AxMjM=
    ! manifest.yaml -
    U
    10
    T
    payment.ini
    11
    apiVersion: apps/v1
    payment.py
    12
    kind: Deployment
    rabbitmq.py
    13
    metadata:
    14
    requirements.txt
    name : payment
    15
    namespace: roboshop
    > rabbitmq
    16
    labels: # these labels are deployment labels
    > redis
    17
    app: payment
    > shipping
    18
    project: roboshop
    > user
    19
    tier: app
    > web
    20
    spec:
    ! namespace.yaml
    21
    replicas: 1
    22
    selector:
    > roboshop-ansible-roles
    23
    matchLabels: # these labels are used to find the pods
    > OUTLINE
    24
    app: payment

[^137]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main f5fe9f8\] jenkins
    5 files changed, 242 insertions (+)
    create mode 100644 payment/Dockerfile
    create mode 100644 payment/payment. ini
    create mode 100644
    payment /payment py

[^138]: 44 . 211 . 248. 243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/payment \]$ kubectl apply -f manifest. yaml
    secret/payment unchanged
    deployment . apps/payment created
    service/payment unchanged

[^139]: 44 . 211 . 248. 243 \| 172. 31 . 94.116 \| t2.micro \| https: //github. com/daws-76s/k8-roboshop . git
    \[ centos@ip-172-31-94-116 \~/k8-roboshop/payment \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    cart-5fcfbccbf5-jp4nl
    1/1
    Running
    28m
    catalogue-79dd48d65f-h747p
    1/1
    Running
    28m
    mongodb-778f7b57d5-pw87m
    1/1
    Running
    30m
    mysql-714b445856-wg15v
    1/1
    Running
    15m
    payment-d947f8795-kt4vj
    0/1
    ContainerCreating
    8s
    rabbitmq-697fb559c7-vinbh
    1/1
    Running
    6m12s
    redis-86d966bb7-kmxzw
    1/1
    Running
    29m
    shipping-8ffd9bc47-ddscv
    1/1
    Running
    13m
    user-796496c69f-ztp7s
    1/1
    Running
    28m
    web-688fccdc4c-d4wrv
    1/1
    Running
    11m

[^140]: C
    A Not secure a02cfbf1d060845492c764136567d00-330447210.us-east-1.elb.amazonaws.com/payment
    Stan's Robot Shop
    Login / Register
    Review your order
    Cart
    Order placed bffd57c0-7468-4f52-b619-53d23e0060ed
    Empty
    Thank you for your order Continue shopping
    Categories
    . Artificial
    Intelligence
    . Robot
    . C3PO
    O
    Eve
    o K9
    Kryten

