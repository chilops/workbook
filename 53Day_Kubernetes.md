---
title: 53Day_Kubernetes
uuid: 3bc33404-3aa7-11ef-8e08-6ef34fa959ce
version: 837
created: '2024-07-05T13:48:58+05:30'
---

# <mark style="background-color:#f8914d;">**Docker Disadvantages**<!-- {"backgroundCycleColor":"24"} --></mark> 

![272239aa-6f8b-49d3-af12-5a28650234a8.png|995](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/272239aa-6f8b-49d3-af12-5a28650234a8.png) [^1]

\

# <mark>**Container Orchestrator**</mark><!-- {"collapsed":true} -->

---

![2d045dc5-72a0-4641-9fa8-01df6d8d62ed.png|672](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/2d045dc5-72a0-4641-9fa8-01df6d8d62ed.png) [^2]

\

# <mark>**Kubernetes Introduction**</mark>

Kubernetes is a popular orchestration tool. Kubernetes is responsible to run and manage the containers.

![dd832416-c67d-4da6-b940-c671b29585dc.png|756](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/dd832416-c67d-4da6-b940-c671b29585dc.png) [^3]

\

<mark>**Kubernetes Architecture**</mark>

![a245a596-822f-475a-9eb5-ab066b8a5a3b.png|437](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/a245a596-822f-475a-9eb5-ab066b8a5a3b.png) [^4]

\

\

# <mark>**Minikube**</mark>

It's a single node cluster. (Master & Node are same) It is just to practice few K8(Kubernetes) resources.

\

<mark>**Installing Minikube using terraform**</mark>

![ff79eab6-847e-48d8-a561-a6181c0d4736.png|742](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/ff79eab6-847e-48d8-a561-a6181c0d4736.png) [^5]

![4c0baf11-e68f-42b7-ba30-fde5525b027c.png|814.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/4c0baf11-e68f-42b7-ba30-fde5525b027c.png) [^6]

\

![c1917dc2-2a33-4381-9bbc-41167748133f.png|944.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/c1917dc2-2a33-4381-9bbc-41167748133f.png) [^7]

\

```
terraform init
```

![b072b834-9331-4627-bf2c-e695b8511d7b.png|809](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/b072b834-9331-4627-bf2c-e695b8511d7b.png) [^8]

\

```
terraform plan
terraform apply -auto-approve
```

![c9dae868-ded5-4dfc-a9c4-6fd969bc3078.png|908](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/c9dae868-ded5-4dfc-a9c4-6fd969bc3078.png) [^9]

\

\

Minikube instance created  (Minikube cluster server)

![1fbf98dc-d49c-44be-805f-dc5187b62378.png|955.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/1fbf98dc-d49c-44be-805f-dc5187b62378.png) [^10]

\

connecting to instance (Minikube cluster server)

```
ssh -i ~/.ssh/daws-76s centos@54.226.177.167
```

![fd9d0ba4-17c0-4c76-824d-eb671e51f500.png|1051](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/fd9d0ba4-17c0-4c76-824d-eb671e51f500.png) [^11]

\

\

after sometime if you see kubeconfig files are created

![4ba634d2-7017-426f-9720-1b304a5a07f5.png|1134.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/4ba634d2-7017-426f-9720-1b304a5a07f5.png) [^12]

![65042c64-250a-4874-a58e-1c61a6421c3f.png|831](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/65042c64-250a-4874-a58e-1c61a6421c3f.png) [^13]

\

```
kubectl
```

![e87a9dd5-6f14-4c5a-b269-b350bc45b613.png|479](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/e87a9dd5-6f14-4c5a-b269-b350bc45b613.png)

![e94a9d89-0d7c-41ee-8293-5401c87a88f3.png|798](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/e94a9d89-0d7c-41ee-8293-5401c87a88f3.png) [^14]

\

![fc001972-4d08-4ca0-85f5-dc8847c395d4.png|894](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/fc001972-4d08-4ca0-85f5-dc8847c395d4.png) [^15]

\

```
kubectl get nodes
```

![eed6b7fa-d84d-48c5-92fa-07d3ba29d7d6.png|1133.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/eed6b7fa-d84d-48c5-92fa-07d3ba29d7d6.png) [^16]

\

\

now creating .kube file and moving the data

```
ls -la
```

```
mkdir .kube
```

```
cp kubeconfig .kube/config
```

![99b9212b-d5c1-4f94-b527-2ed973d275c7.png|871](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/99b9212b-d5c1-4f94-b527-2ed973d275c7.png) [^17]

\

to cross check

![6571d3f1-9672-4f47-9bb4-4b59bf63a7ab.png|818](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/6571d3f1-9672-4f47-9bb4-4b59bf63a7ab.png) [^18]

\

```
cat config
```

![8bae5498-4077-427a-878c-1466d7426c71.png|967.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8bae5498-4077-427a-878c-1466d7426c71.png) [^19]

\

it works now

```
kubectl get nodes
```

![4d9bce5f-9291-4157-afe2-2400fd7deba6.png|1080](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/4d9bce5f-9291-4157-afe2-2400fd7deba6.png) [^20]

docker.sh

![86b7778a-b706-42f9-b946-fb54ab6e9714.png|918.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/86b7778a-b706-42f9-b946-fb54ab6e9714.png) [^21]

\

```
terraform init
terraform plan
terraform apply -auto-approve
```

![8084654d-deef-4a4f-841c-834b53d84ccc.png|1019](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8084654d-deef-4a4f-841c-834b53d84ccc.png) [^22]

\

Workstation created

![7099b75e-e6d1-4b8b-97ab-2fcef8e54641.png|1016.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/7099b75e-e6d1-4b8b-97ab-2fcef8e54641.png) [^23]

\

to check logs weather docker is installing or not.

```
sudo tail -f /var/log/cloud-init-output.log
```

![bf8d375a-039e-417d-a931-374f42f162f2.png|1100.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/bf8d375a-039e-417d-a931-374f42f162f2.png) [^24]

\

once completed exit and login again..

```
docker ps
```

![4f608b5d-e856-4478-8334-93143d3f81e4.png|1094](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/4f608b5d-e856-4478-8334-93143d3f81e4.png) [^25]

\

<mark>Installing kubectl on workstation server</mark>

![93038375-8647-4c61-a7f5-823f9174f9bf.png|918.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/93038375-8647-4c61-a7f5-823f9174f9bf.png) [^26]

\

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt) /bin/linux/amd64/kubectl"
```

![83048889-8d02-4a53-bac3-cfc51631914f.png|1191.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/83048889-8d02-4a53-bac3-cfc51631914f.png) [^27]

\

<mark>this command may not require</mark>

\

![f1cadb9f-99d3-4b36-abfe-faf42832f5be.png|780](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/f1cadb9f-99d3-4b36-abfe-faf42832f5be.png) [^28]

\

```
chmod +x kubectl
```

![a6408c97-8cde-44d4-93c4-7fccf653f58e.png|889](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/a6408c97-8cde-44d4-93c4-7fccf653f58e.png) [^29]

\

```
sudo mv kubectl /usr/local/bin/kubectl
```

![0eea5c53-2daf-4c8f-957c-d38e90de4944.png|1085](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/0eea5c53-2daf-4c8f-957c-d38e90de4944.png) [^30]

\

```
kubectl
```

![efa69fc5-b6dd-4522-879c-f604a5de04c2.png|973.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/efa69fc5-b6dd-4522-879c-f604a5de04c2.png) [^31]

\

to check the current version

```
kubectl version --client
```

![e7bf28f4-9680-41bd-84b0-fb10e9e58f56.png|860](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/e7bf28f4-9680-41bd-84b0-fb10e9e58f56.png) [^32]

\

<mark>**Copy authentication file from master**</mark>

To connect to server we should have authentication file

\

copy from (Minikube cluster server) to workstation server 

```
cat kubeconfig
```

![](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/c5a75075-9027-4587-9114-10197d099be4.png) [^33]![d6d7da36-2c4a-4253-89bd-24c097db0530.png|1008](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/d6d7da36-2c4a-4253-89bd-24c097db0530.png) [^34]

\

Now paste it on workstation server

```
vim .kube/config
```

![](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/be81ecff-90b0-4f42-9903-c442ab8bc2e3.png) [^35]

![0a0ce7da-7008-4982-8032-5fae3b0f7495.png|1093.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/0a0ce7da-7008-4982-8032-5fae3b0f7495.png) [^36]

\

Now we connected to cluster (it will show all the nodes)

```
kubectl get nodes
```

![98961014-6a79-47be-a7f6-44486ccfa7c8.png|992](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/98961014-6a79-47be-a7f6-44486ccfa7c8.png) [^37]

\

# <mark>**Namespace (Kubernetes resource)**</mark>

![75a9b45c-b5bc-4658-81cc-c7bdff70c8b3.png|1067.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/75a9b45c-b5bc-4658-81cc-c7bdff70c8b3.png) [^38]

\

namespace.yaml

![8f19e3a9-1d8c-49f8-8501-51ae36bfbe37.png|864](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8f19e3a9-1d8c-49f8-8501-51ae36bfbe37.png) [^39]

\

<mark>**Now push to github & pull to docker host and then apply to Kubernetes cluster server.**</mark>

\

create a repo

![352b8111-35c7-48f0-a7f7-afdcef2871d2.png|881.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/352b8111-35c7-48f0-a7f7-afdcef2871d2.png) [^40]

\

\

![d090d0c8-eb5f-470f-b792-bf412d654e73.png|924](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/d090d0c8-eb5f-470f-b792-bf412d654e73.png) [^41]

\

![0b2c35c9-c123-451b-8ac1-ee2f8c576931.png|843](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/0b2c35c9-c123-451b-8ac1-ee2f8c576931.png) [^42]

\

cloning on workstation server (docker host)

![c15b6f13-d1b9-491a-a70d-22de514db0f9.png|1044.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/c15b6f13-d1b9-491a-a70d-22de514db0f9.png) [^43]

![f8b2a015-3a29-4e6f-9706-10ab6208cf26.png|1065.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/f8b2a015-3a29-4e6f-9706-10ab6208cf26.png) [^44]

\

creating resources

```
kubectl create -f namespace.yaml
```

![54a6dadb-1b0c-4b9e-a0db-0996553e8520.png|1071.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/54a6dadb-1b0c-4b9e-a0db-0996553e8520.png) [^45]

\

It will show all namespaces in the system

```
kubectl get namespaces
```

![55f60a26-67a9-43e2-bfd4-1c80641b0a18.png|1160.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/55f60a26-67a9-43e2-bfd4-1c80641b0a18.png) [^46]

\

If i try to create again.. getting an error

```
kubectl create -f namespace.yaml
```

![f4a45553-0dcf-47a3-8424-630d23fafbcb.png|1191.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/f4a45553-0dcf-47a3-8424-630d23fafbcb.png) [^47]

\

Deleting a resource

```
kubectl delete -f namespace.yaml
```

![923b5ec7-0b8f-4fae-9e8a-45ac443e774f.png|1159.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/923b5ec7-0b8f-4fae-9e8a-45ac443e774f.png) [^48]

\

we don't use create mostly, we use apply instead of create. (we can use multiple times)

```
kubectl apply-f namespace.yaml
```

![acac0c3f-9a7b-4eb9-90ed-671132c67735.png|1078.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/acac0c3f-9a7b-4eb9-90ed-671132c67735.png) [^49]

\

![0bab90e2-412d-46e6-8417-05f57e707739.png|1059.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/0bab90e2-412d-46e6-8417-05f57e707739.png) [^50]

\

# <mark>**PODS -**</mark>In Kubernetes a pod is a space where your containers will run.

![00d911e8-1633-4dbd-a782-8f4e643a7982.png|373.3333435058594](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/00d911e8-1633-4dbd-a782-8f4e643a7982.png) [^51]

\

It a smallest deployable unit in Kubernetes (POD same as container)

\

![88429c85-5a28-4c56-9630-15106d0015d2.png|971.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/88429c85-5a28-4c56-9630-15106d0015d2.png) [^52]

\

We create a **manifest file** to create the pod.

Its a basic RAW syntax to create pod

![a8fd2518-bff2-431c-a6a8-4dec13bf8dcf.png|877](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/a8fd2518-bff2-431c-a6a8-4dec13bf8dcf.png) [^53]

\

git push

![5695c8e0-8ae3-4962-a95f-ba98b99ed662.png|914](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/5695c8e0-8ae3-4962-a95f-ba98b99ed662.png) [^54]

\

git pull

![fdcc70fd-ca87-4b42-afe1-043fc7d0bbf0.png|915.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/fdcc70fd-ca87-4b42-afe1-043fc7d0bbf0.png) [^55]

\

To create a POD (its going to create in default namespace)

```
kubectl apply -f 01-pod.yaml
```

To check PODS

```
kubectl get pods
```

![6d14ea4c-e81f-4a35-930b-901f4219f9e2.png|1143.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/6d14ea4c-e81f-4a35-930b-901f4219f9e2.png) [^56]

\

```
kubectl get namespaces
or 
kubectl get ns
```

![5276d5bc-d801-4909-b7c6-8defbbbbc65a.png|1013.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/5276d5bc-d801-4909-b7c6-8defbbbbc65a.png) [^57]

\

Deleting POD

```
kubectl delete -f 01-pod.yaml
```

![fb1def6d-de86-475f-adcd-f67e36d848e3.png|1133.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/fb1def6d-de86-475f-adcd-f67e36d848e3.png) [^58]

\

<mark>If you want to create in specific namespace give as below ( nginx image is pulling from Docker)</mark>

![474c95a2-dbef-4f38-ac8d-e376477d828b.png|800](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/474c95a2-dbef-4f38-ac8d-e376477d828b.png) [^59]

\

git push & pull

![b74946fa-a7bf-431d-b37e-b344d66c093d.png|688](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/b74946fa-a7bf-431d-b37e-b344d66c093d.png) [^60]

![b649d4b0-2825-42d6-b332-e6b2e8370e61.png|861.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/b649d4b0-2825-42d6-b332-e6b2e8370e61.png) [^61]

\

creating a POD

```
kubectl apply -f 01-pod.yaml
```

![aedfe8ef-9121-4a92-99c4-06bf0ced808f.png|1102.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/aedfe8ef-9121-4a92-99c4-06bf0ced808f.png) [^62]

\

```c
kubectl get pod               --> you can't see in default namespace, as its created in roboshop namespace
```

```
kubectl get pods -n roboshop
```

![da66964b-856f-4807-b8bc-91dd7126ead7.png|1073.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/da66964b-856f-4807-b8bc-91dd7126ead7.png) [^63]

\

# <mark>**Why multiple containers i a POD**</mark>

![8db0ae92-3b52-4882-bdd6-7fa16398847c.png|554](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8db0ae92-3b52-4882-bdd6-7fa16398847c.png) [^64]![7e183e96-9aea-475d-9c0a-6cfb14804169.png|301](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/7e183e96-9aea-475d-9c0a-6cfb14804169.png) [^65]

\

multiple containers

![5837fbcd-fd30-47fa-a9cc-0831a09d5f0c.png|855](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/5837fbcd-fd30-47fa-a9cc-0831a09d5f0c.png) [^66]

\

git push & pull

![4415cba5-7215-4d81-8be6-331721bb8354.png|793](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/4415cba5-7215-4d81-8be6-331721bb8354.png) [^67]

\

```
kubectl apply -f 02-multi-container.yaml
kubectl get pods
```

![37af3b17-29ea-4b2c-b37e-e2e57038d0fe.png|909.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/37af3b17-29ea-4b2c-b37e-e2e57038d0fe.png) [^68]

\

To Login a container

```
kubectl exec -it multi-container -c almalinux -- bash
```

![c4eeb4f3-986d-483d-9755-78eed537ea0e.png|926.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/c4eeb4f3-986d-483d-9755-78eed537ea0e.png) [^69]

\

<mark>**Containers in the same POD can share the same network & storage spaces**</mark>

so here it communicating with other container(Nginx) where nginx is running as shown below.

![e6142227-290a-4b53-baa9-03c0d66efea5.png|1077.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/e6142227-290a-4b53-baa9-03c0d66efea5.png) [^70]

\

# <mark>**Labels  - Its for filterations**</mark>

By using labels(key value pairs) we can attach to other containers. It has more advantages in K8.

![](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/5827cf0f-f56d-4cbb-8072-12f6246a4333.png) [^71]

\

![df1d3d48-bfe5-49bf-998c-b14f22789a1e.png|1051.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/df1d3d48-bfe5-49bf-998c-b14f22789a1e.png) [^72]

\

git push & pull

![67f590e6-d91b-4f6a-9b76-61affc824833.png|936](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/67f590e6-d91b-4f6a-9b76-61affc824833.png) [^73]

\

```
kubectl apply -f 03-labels.yaml
kubectl get pods
```

![5f4cc16f-a3b4-49be-8411-6597dcfb5d83.png|1176.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/5f4cc16f-a3b4-49be-8411-6597dcfb5d83.png) [^74]

\

To see more information about PODS

```
kubectl describe pod label-demo
```

![fdef1ca0-d61f-4ff8-9ea1-aab697618a05.png|1010.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/fdef1ca0-d61f-4ff8-9ea1-aab697618a05.png) [^75]

![693830ca-abaa-4a32-a2d1-68b1ca65640c.png|1123.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/693830ca-abaa-4a32-a2d1-68b1ca65640c.png) [^76]

\

# <mark>**Annotations**</mark>

![8197b075-444c-4d0c-a358-29b7cb86f750.png|856.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8197b075-444c-4d0c-a358-29b7cb86f750.png) [^77]

\

![07872d12-4c7a-4698-83aa-1d03ad6841f6.png|1004.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/07872d12-4c7a-4698-83aa-1d03ad6841f6.png) [^78]

\

git push & pull

![dd327a7c-9b99-4158-af45-91251011d4f6.png|772](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/dd327a7c-9b99-4158-af45-91251011d4f6.png) [^79]

\

```
kubectl apply -f 04-annotations.yaml
```

![7245028a-e3a4-4177-a7e3-5575beecf4d2.png|1129.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/7245028a-e3a4-4177-a7e3-5575beecf4d2.png) [^80]

\

```
kubectl get pods
```

![f5d8c9f2-1510-45d4-a20f-2161f7c49bcb.png|1145.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/f5d8c9f2-1510-45d4-a20f-2161f7c49bcb.png) [^81]

\

```
kubectl describe pod annotations
```

![7209f8d4-7e55-42fe-9eec-a1fa29bf5469.png|1106.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/7209f8d4-7e55-42fe-9eec-a1fa29bf5469.png) [^82]

\

![ad124751-b492-450e-a05f-080c98c18d69.png|650](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/ad124751-b492-450e-a05f-080c98c18d69.png) [^83]

\

# <mark>**Kubernetes Environment**</mark>

![1dc61f8d-a2ba-42de-b5e8-28d478ddd716.png|904.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/1dc61f8d-a2ba-42de-b5e8-28d478ddd716.png) [^84]

\

git push & pull

![dc4ea878-dddb-4a6a-86fc-bc41ea69babc.png|996.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/dc4ea878-dddb-4a6a-86fc-bc41ea69babc.png) [^85]

\

```
kubectl apply -f 05-env.yaml
```

![20c7854c-3610-4e4a-b4cf-3687e74b9d7f.png|1141.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/20c7854c-3610-4e4a-b4cf-3687e74b9d7f.png) [^86]

\

```
kubectl exec -it envar-demo -- bash
env
```

![33ead773-bd9e-4ba6-a469-55cce3af4be8.png|1065.3333740234375](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/33ead773-bd9e-4ba6-a469-55cce3af4be8.png) [^87]

[^1]: 1. we have a docker host where all containers are running
    what if docker host crash? we lose all containers
    even we use docker volumes, data is still in the host, so we lost data as well
    2. what if traffic increases/decreases? are our containers scalable
    3. even we have multiple containers to balance the load? who is the LB here?
    4. what if some container crashes? can docker make it available again?
    5. what about configurations and secrets? where to store them?
    6. what if we have multiple hosts running with containers
    I

[^2]: we need some orchestrator?
    kubernetes is popular container orchestration tool.

[^3]: Docker Host
    X
    Dockerfiles
    kubectl
    docker
    push
    Manifests
    manifest
    Build the images
    Kubernetes

[^4]: Node
    Master
    Node
    Node

[^5]: X
    github.com/scholzj/terraform-aws-minikube
    Terraform
    Registry
    Q Search all resources
    B
    minikube
    Version
    aws provider
    Terraform module for single node Kubernetes instance bootstrapped using kubeadm
    Published February 18, 2024 by scholzj
    Source Code: github.com/scholzj/terraform-aws-minikube (report an issue)

[^6]: C
    25 github.com/scholzj/terraform-aws-minikube
    E
    scholzj / terraform-aws-minikube
    Q Type to searc
    <> Code
    O Issues 2 17 Pull requests 1 Actions Projects @ Security \~ Insights
    terraform-aws-minikube Public
    Watch 4
    & master -
    & 4 Branches 93 Tags
    Q Go to file
    t
    Add file
    <> Code
    scholzj Update to Kubernetes 1.29.2 + Ingress add-on update
    359ad66 . 2 days ago 206 Commits
    addons
    Update Ingress addon
    2 days ago
    aws-cloud-provider
    Add AWS cloud provider
    10 months ago
    calico
    Update addons
    4 months ago
    examples
    Update to Kubernetes 1.24.1
    2 years ago
    scripts
    Update to Kubernetes 1.29.0
    2 months ago
    template
    Replace token generator with the token module
    7 years ago
    O .gitignore
    Update to Kubernetes 1.25.0
    2 years ago

[^7]: EXPLORER
    . .
    jipping
    docker-compose.yaml
    provider.tf terraform-aws-minikube
    minikube.tf X provider.tf terr. \[\]
    V REPOS
    terraform-aws-minikube > minikube.tf
    > roboshop-documentation
    1
    module "minikube" {
    N
    > roboshop-infra-dev
    source = "github. com/scholzj/terraform-aws-minikube"
    > roboshop-infra-prod
    3
    4
    aws_region
    = "us-east-1".
    > roboshop-shared-library
    5
    cluster_name = "roboshop"
    > roboshop-shell
    6
    aws_instance_type = "t3.medium"
    > roboshop-terraform
    7
    ssh_public_key = "\~/. ssh/daws-76s.pub"
    -
    > shell-script
    8
    aws_subnet_id = "subnet-0ea509ad4cba242d7" #replace your default subnet id
    > students-interview-questions
    9
    # by default centos7 will be used
    > terraform
    10
    #ami_image_id = "ami-b81dbfc5"
    11
    hosted_zone = "daws76s .online"
    v terraform-aws-minikube
    12
    hosted_zone_private = false
    minikube.tf
    13
    provider.tf
    14
    tags = {
    > terraform-aws-security-group
    15
    Application = "Minikube"
    > terraform-aws-vpc
    16
    > terraform-modules
    17
    18
    > terraform-multi-env
    addons = \[
    19
    "https://raw.githubusercontent.com/scholzj/terraform-aws-minikube/master/addons/stc
    > terraform-provisioners
    20
    "https://raw.githubusercontent. com/scholzj/terraform-aws-minikube/master/addons/hec
    > terraform-roboshop-app
    21
    "https://raw.githubusercontent . com/scholzj/terraform-aws-minikube/master/addons/das
    > user
    22
    "https://raw. githubusercontent . com/scholzj/terraform-aws-minikube/master/addons/ext
    > user-deploy
    23

[^8]: user@AshDexter-T480 MINGW64 \~
    $ cd /c/devops/daws-76s/repos/terraform-aws-mini kube/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-minikube
    $ terraform init
    Initializing the backend. ..

[^9]: Plan: 12 to add, 0 to change, 0 to destroy.
    Warning: Argument is deprecated
    with module . minikube. aws_eip . minikube,
    on . terraform\\modules\\minikube\\main. of line 152, in resource "aws_eip" "minikube":
    152:
    vpc = true
    use domain attribute instead
    (and one more similar warning elsewhere)
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock. This may take a few moments. . .
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-minikube
    $ terraform apply -auto-approve

[^10]: Instances (1/1) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    < 1 >
    V
    Name _
    4
    Instance ID
    Instance state
    Instance type v Status check
    Alarm status
    Availability Zo
    roboshop
    i-089123d205977d94b
    Running Q Q
    t3.medium
    2/2 checks passed View alarms +
    us-east-1a
    Instance: i-089123d205977d94b (roboshop)
    @ X
    Details
    Status and alarms New
    Monitoring
    Security
    Networking
    Storage
    Tags
    Instance summary Info
    Instance ID
    Public IPv4 address
    Private IPv4 addresses
    i-089123d205977d94b (roboshop)
    54.226.177.167 \|open address \[
    172.31.86.230
    IPv6 address
    Instance state
    Public IPV4 DNS
    Running
    ec2-54-226-177-167.compute-1.amazonaws.com \|open

[^11]: user@AshDexter-T480 MINGW64 \~
    S ssh -i \~/. ssh/daws-76s centos@54 . 226. 177 . 167
    The authenticity of host '54.226.177.167 (54.226.177.167)' can't be established.
    ED25519 key fingerprint is SHA256:7sBXNe88ctKzoqAc6iu0/waPF79GOC+M97+7/38L9ZM.
    This key is not known by any other names.
    Are you sure you want to continue connecting (yes/no/\[fingerprint\])? yes
    Warning: Permanently added '54. 226.177. 167' (ED25519) to the list of known hosts.
    \[centos@ip-172-31-86-230 \~\]$ \|

[^12]: kubeconfig --> is the files contains authentication information to connect kubernetes cluster
    kubectl
    to
    I
    onnect kubernetes
    luster

[^13]: \[centos@ip-172-31-86-230 \~\]$ 1s -1
    total 16
    rw-
    1 centos centos 5552 Feb 21 02:16 kubeconfig
    rw-
    1 centos centos 5543 Feb 21 02:16 kubeconfig_ip
    \[centos@ip-172-31-86-230 \~\]$

[^14]: drain
    Drain node in preparation for maintenance
    taint
    Update the taints on one or more nodes
    Troubleshooting and Debugging Commands:
    describe
    Show details of a specific resource or group of resources
    logs
    Print the logs for a container in a pod
    attach
    Attach to a running container
    exec
    Execute a command in a container
    port-forward
    Forward one or more local ports to a pod
    proxy
    Run a proxy to the Kubernetes API server
    cp
    Copy files and directories to and from containers
    auth
    Inspect authorization
    debug
    Create debugging sessions for troubleshooting workloads and no
    events
    List events
    Advanced Commands :
    diff
    Diff the live version against a would-be applied version
    apply
    Apply a configuration to a resource by file name or stdin
    patch
    Update fields of a resource

[^15]: kubectl will check automatically a file
    \~/ . kube/config

[^16]: \[centos@ip-172-31-86-230 \~\]$ kubectl get nodes
    E0221 02:24: 14. 719825 13726 memcache . go:265\] couldn't get current server API group list: Get "http://localhost: 8080/api?timeout=32s": dial tcp
    : :1\]:8080: connect: connection refused
    E0221 02: 24: 14. 720483 13726 memcache . go:265\] couldn't get current server API group list: Get "http://localhost: 8080/api?timeout=32s": dial tcp
    : :1\]:8080: connect: connection refused
    E0221 02 :24 : 14 . 722095
    13726 memcache . go:265\] couldn't get current server API group list: Get "http://localhost: 8080/api?timeout=32s": dial tcp
    : :1\]:8080: connect: connection refused
    E0221 02: 24: 14. 722604 13726 memcache . go:265\] couldn't get current server API group list: Get "http://localhost: 8080/api?timeout=32s": dial tcp
    : :1\] :8080: connect: connection refused
    E0221 02: 24: 14. 730972 13726 memcache . go:265\] couldn't get current server API group list: Get "http://localhost: 8080/api?timeout=32s": dial tcp
    : :1\]:8080: connect: connection refused
    The connection to the server localhost: 8080 was refused - did you specify the right host or port?
    \[centos@ip-172-31-86-230 \~\]$

[^17]: \[centos@ip-172-31-86-230 \~\]$ 1s -1
    total 16
    rw-
    1 centos centos 5552 Feb 21 02:16 kubeconfig
    - rw-
    1 centos centos 5543 Feb 21 02:16 kubeconfig_ip
    \[centos@ip-172-31-86-230 \~\]$ 1s -la
    total 28
    drwx - -- -
    3 centos centos 113 Feb 21 02:16
    drwxr-xr-x.
    3 root
    root
    20 Feb 21 02:12
    -rw-r- -r--.
    1 centos centos
    18 Nov 24 2021 .bash_logout
    -rw-r--r- -
    1 centos centos
    193 Nov 24 2021 . bash_profile
    -rw-r--r--.
    1 centos centos
    231 Nov 24 2021 . bashrc
    -rw-
    1 centos centos 5552 Feb 21 02:16 kubeconfig
    rw-
    1 centos centos 5543 Feb 21 02:16 kubeconfig_ip
    drwx-
    2 centos centos
    29 Feb 21 02:12 . ssh
    \[centos@ip-172-31-86-230 \~\]$ mkdir . kube
    \[centos@ip-172-31-86-230 \~\]$ cp kubeconfig . /kube/config
    cp: cannot create regular file './kube/config' : No such file or directory
    \[centos@ip-172-31-86-230 \~\]$ cp kubeconfig . kube/config
    \[centos@ip-172-31-86-230 \~\]$

[^18]: \[centos@ip-172-31-86-230 \~\]$ 1s -la
    total 28
    drwx
    4 centos centos
    126 Feb 21 02:24
    drwxr-xr-x.
    3 root
    root
    20 Feb 21 02:12
    -rw-r--r--.
    1 centos centos
    18 Nov 24
    2021 . bash_logout
    rw-r--r--.
    1 centos centos
    193 Nov 24
    2021 . bash_profile
    -rw-r--r--.
    1 centos centos
    231 Nov 24
    2021 . bashrc
    drwxrwxr-x.
    2 centos centos
    20 Feb 21 02:24 . kube
    - rw-
    1 centos centos 5552 Feb 21 02:16 kubeconfig
    rw
    1 centos centos 5543 Feb 21 02:16 kubeconfig_ip
    drwx
    2 centos centos
    29 Feb 21 02:12 . ssh
    \[centos@ip-172-31-86-230 \~\]$ cd . kube/
    \[centos@ip-172-31-86-230 . kube\]$ 1s -1
    total 8
    rw- - - ---
    1 centos centos 5552 Feb 21 02:24 config
    \[centos@ip-172-31-86-230 . kube\] $

[^19]: clusters :
    cluster:
    certificate-authority-data: LSOtLS1CRUdJTiBDRVJUSUZJQOFURSOtLSOtCk1JSURCVENDQWUyZOF 3SU
    JFROEXVUUKQXNS2EzVmlaWEp1W1hSbGN6QWVGdzBSTKRBeUlqRXdNakE1TWpGYUZ3MHpOREFSTVRnd01qRTBNakZh
    U3FHUO1 i MORRRUJBUVVBQTRJQKR 3QXdnZOVLCKFVSUJBUUNuaVFrVnhES 3FSVGNHUG5tbWRZMHQ4R 3pi SHZLTG1pVz
    FUdHZibi9WMZU4QZRLTHVVWVhCaHpFVOXSCVRhSZRJNVRPUWk1Q1pkNDZVNTZJYQpVcFFSS2tkTHC1YZZQTWVTYm9PM
    N3UxCnpUaGhVbndCOTMOeEpTZZY1TW9DM3 3DR3dXSDV3ZUVi YUVZYVJ6NFFLejY2c11ScTh4TOhVMnB5CHNPVK1Fd21
    FTNV1pc2VmcEhRCVE3TKRTbK9DSKxFUApXaGINa 1A421NhQzdpejBvdGW2TDRBSmJKdotkQWdNQKFBR2pXVEJYTUEOF
    TUIWROEXVWREZ1FXQKJRNTNhVZBWWT1TenNOSV1ONONwdDZPQ11Zakp6QVYKQmdovkhSRUVEakFNZ2dwcmRXSmxjbT
    p 3djAOYWdWUkhodw42onA4U2p 5NVczbudTomRqakR jKZBEME15M2YOUOFHK2wvS jdYMnZCcOFXCHZ1VUNOUWdMCkov
    MK 1noXVhVKUSUTdCdFpUTHJONUsKZTRDRnBYSVZhV1VnVmFOS25zc2Rqc 3MrU1FiMCtiNONDMHh4NmRXR2Q5cTJjbk
    32WGdacFJVei9DUTZuz2 1msOd5YkxTN2d5MUJOYU11T3FSdGhoTOR6Ck1mSS9Yc 1F4REISNTdNSnRWZ1dKQ01abmoOr
    UjBBbWWOOWRZCiOtLSOtRUSEIENFU1RJRK1DQVRFLSOtLSOK
    server: https://roboshop . daws76s . online : 6443
    name: kubernetes
    contexts :
    context:
    cluster: kubernetes
    user: admin
    name: admin@kubernetes
    current-context: admin@kubernetes
    kind: Config
    preferences: {}
    users:
    name : admin
    user :

[^20]: \[centos@ip-172-31-86-230 \~\]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-172-31-86-230. ec2. internal
    Ready
    control-plane
    11m
    v1. 29 . 2
    \[centos@ip-172-31-86-230 \~\]$ \|

[^21]: EXPLORER
    . . .
    compose.yaml
    provider.tf terraform-aws-minikube
    minikube.tf
    REPOS
    terraform-aws-minikube > $ docker.sh
    > roboshop-infra-dev
    48
    > roboshop-infra-prod
    49
    systemctl enable docker
    > roboshop-shared-library
    50
    > roboshop-shell
    51
    VALIDATE $? "Enabled docker"
    > roboshop-terraform
    52
    53
    shell-script
    usermod -aG docker centos
    54
    > students-interview-questions
    55
    VALIDATE $? "added centos user to docker group"
    > terraform
    56
    terraform-aws-minikube
    57
    > .terraform
    58
    echo -e "$R Logout and login again $N"
    E .terraform.lock.hcl
    $ docker.sh

[^22]: Plan: 2 to add, 0 to change, 0 to destroy.
    Warning: Argument is deprecated
    with module. minikube. aws_eip. minikube,
    on . terraform\\modules \\minikube \\main. tf line 152, in resource "aws_eip" "minikube":
    152:
    vpc = true
    use domain attribute instead
    (and one more similar warning elsewhere)
    Note: You didn't use the -out option to save this plan, so Terraform can't
    guarantee to take exactly these actions if you run "terraform apply" now.
    Releasing state lock. This may take a few moments. . .
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-mini kube
    $ terraform apply -auto-approve

[^23]: Instances (1/2) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    4
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    <
    1 >
    Name
    4
    Instance ID
    Instance state
    V
    Instance type
    V
    Status check
    Alarm status
    Availability
    0
    roboshop
    i-089123d205977d94b
    Running Q Q
    t3.medium
    2/2 checks passed View alarms +
    us-east-1a
    workstation
    i-06434c1cacf1243cc
    Pending Q Q
    t2.micro
    View alarms +
    us-east-1a
    =
    Instance: i-06434c1cacf1243cc (workstation)
    O X
    Details
    Status and alarms New
    Monitoring
    Security
    Networking
    Storage
    Tags
    Instance summary Info
    Instance ID
    Public IPv4 address
    Private IPv4 addresses
    i-06434c1cacf1243cc (workstation)
    3.84.15.55 \|open address \[
    172.31.89.100
    IPv6 address
    Instance state
    Public IPV4 DNS
    Pending
    ec2-3-84-15-55.compute-1.amazonaws.com \|open
    address

[^24]: Customized Commands available in this Image:
    1. labauto
    2. disable-auto-shutdown / enable-auto-shutdown
    3. set-hostname
    Last login: Tue Jan 16 13:13:26 2024 from 4. 213.0.213
    3. 84 . 15. 55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ sudo tail -f /var/log/cloud-init-output . log
    lo. +\*.
    - \[SHA256\] --
    Cloud-init v. 23.4-1.e18 running 'modules: config' at Wed, 21 Feb 2024 02:28:25 +0000. Up 28.93 seconds.
    2024-02-21 02:28:25, 875 - util . py \[WARNING\] : Running module set-passwords (<module 'cloudinit. config. cc_s
    thon3 . 6/site-packages/cloudinit/config/cc_set_passwords .py'>) failed
    Cloud-init v. 23.4-1.e18 running 'modules: final' at Wed, 21 Feb 2024 02:28:26 +0000. Up 29.95 seconds.
    2024-02-21 02:28:26, 898 - modules . py \[WARNING\] : Could not find module named cc_refresh rmc_and interface
    interface', 'cloudinit. config.cc_refresh rmc_and interface' \])
    /var/lib/cloud/instance/scripts/part-001: line 13: /tmp//var/lib/cloud/instance/scripts/part-001-2024-02
    or directory
    You are root user
    Centos Stream 8 - AppStream
    39 MB/S \|
    27 MB
    00: 00
    Centos Stream 8
    BaseOS
    24 MB/S \|
    10 MB
    00:00

[^25]: 3. 84 . 15. 55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    3. 84. 15. 55 \| 172. 31. 89.100 \| t2.micro \| null

[^26]: F
    C
    kubernetes.io/docs/tasks/tools/install-kubectl-linux/
    kubernetes
    Documentation Kubernetes Blog Training Par
    Install kubectl binary with curl on Linux
    Q Search this site
    1. Download the latest release with the command:
    Documentation
    Getting started
    x86-64
    ARM64
    > Concepts
    . Tasks
    curl -LO "https://dl.k8s. io/release/$(curl -L -s https://dl.k8s.io/release/stable.
    Install Tools
    Install and Set Up kubectl on
    Linux
    Install and Set Up kubectl on
    macOS
    Note:
    Install and Set Up kubectl on
    To download a specific version, replace the $(curl -L -s
    Windows
    https://dl.k8s.io/release/stable. txt) portion of the command with the specific version.

[^27]: 3. 84 . 15.55 \| 172 . 31. 89. 100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$
    curl -LO "https: //dl . k8s . io/release/$ (curl -L -s https: //dl . k8s . io/release/stable. txt) /bin/linux/amd6
    4/kubectl"
    8 Total
    8 Received $ Xferd
    Average Speed
    Time
    Time
    Time
    Current
    Dload
    Upload
    Total
    Spent
    Left
    Speed
    100
    138
    100
    138
    0
    2936
    0
    2936
    100 47 . 4M
    100 47 . 4M
    O
    0
    112M
    0
    135M
    3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| null

[^28]: 3. Install kubectl
    sudo install -o root -g root -m 0755 kubect\] /usr/local/bin/kubect\]

[^29]: 3. 84 . 15. 55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ chmod +x kubectl
    3. 84 . 15. 55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ 1s -1
    total 48540
    -rwxrwxr-x 1 centos centos 49704960 Feb 21 02:30 kubectl

[^30]: 3. 84 . 15. 55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos(ip-172-31-89-100 \~ \]$ sudo mv kubectl /usr/local/bin/kubectl

[^31]: 3.84.15.55
    events
    List events
    Advanced Commands :
    diff
    Diff the live version against a would-be applied version
    apply
    Apply a configuration to a resource by file name or stdin
    patch
    Update fields of a resource
    replace
    Replace a resource by file name or stdin
    wait
    Experimental: Wait for a specific condition on one or many resources
    kustomize
    Build a kustomization target from a directory or URL
    Settings Commands :
    label
    Update the labels on a resource
    annotate
    Update the annotations on a resource
    pletion
    Output shell completion code for the
    spe
    (bash
    zsh

[^32]: 3. 84 . 15.55 \| 172. 31.89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ kubectl version --client
    Client Version: v1 . 29.2
    Kustomize Version: v5.0.4-0. 20230601165947-6ce0bf390ce3

[^33]: user@AshDexter-T480 MINGW64
    $ ssh -i \~/. ssh/daws-76s centos@54 . 226. 177 . 167
    \[centos@ip-172-31-86-230 \~\]$ cat kubeconfigu
    cat: kubeconfigu: No such file or directory
    \[centos@ip-172-31-86-230 \~\]$ cat kubeconfig

[^34]: UjBBbWWOOWRZCiOtLSOtRUSEIENFU1RJRK1DQVRFLSOtLSOK
    server: https://roboshop . daws76s . online : 6443
    name: kubernetes
    contexts :
    context:
    cluster: kubernetes
    user: admin
    name: admin@kubernetes
    current-context: admin@kubernetes
    kind: config
    preferences: {}
    users :
    name : admin
    user:
    client-certificate-data: LSOtLS1CRUdJTiBDRVJUSUZJQOFURSOtLSOtCk13SUMVVENDQWVXZOF3s
    OEXVUUKQXhNS2EzVmlaWEp1W1hSbGN6QWVGdzBSTKRBeUlqRXdNakE1TWpGYUZ3MH1OVEFTWpBd01qRTFOVG>
    CQVFFRKFBTONBUThBTU1JQKNnSONBUUVBCj IrRGVLeEZPRUdnL2Zock5vVOFuSkdpbFRuQm9CSVAyRVFHQVcy
    kdwsTK2Q3BUbVcOSXh 5dmFZM2tVQW1HNXFSNTZZdE1ZTC8ZMORqUjBDNHBFTgpFdTRJbZI1MV13VVRKdjIVQUk
    TCkh jaDJMSGFTQ110Ui9wwktwoncxY1hBb 1BpcVg3TG90QKVEbjRRTEw3dFBHc 1VxSFpmCUZCRHK4QOR4citX
    alle Sen\\7V/HpAd3dTWan

[^35]: 3. 84. 15.55 \| 172. 31. 89.100 \| t2. micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ vim .kube/config

[^36]: 3.84.15.55
    name: admin
    user:
    client-certificate-data: LSOtLS1CRUdJTiBDRVJUSUZJQOFURSOtLSOtCk1JSUMVVENDQWVXZOF3SUJ
    dGVEVUTUJFROExVUUKQXhNS2EzVmlaWEplWlhsbGN6QWVGdzB5TRBeUlqRXdNakE1TWpGYUZ3MHLOVEF5TWpBdo
    UJJakFOQudrcWhraUc5dzBCQVFFRKFBTONBUThBTU1JQkNnSONBUUVBCj IrRGVLeEZPRUdnL2Zock5vV0FuSkdpb
    SVVLeWkKQnU3bU9YQUM1VDY1S2RXUVRWTkdwSTK2Q3BUbVcOSXh5dmFZM2tVQW1HNXFSNTZZdE1ZTC8zMORqUjBD
    6bj ZwZGpyaGdUNE03VINIVWPON3JiVG9KRm9MeGU5ZnNTCkhjaDJMSGFTQ110Ui9WWktwoncxY1hBblBpcVg3TG9
    k2WUpnc301d21nTERtV3NubHNEM3oyUitRZOU4bDJmUGRtTWp30nlwoUVqT1puRFQraUR5SnVZVHp4d3dIWgpreW
    05WSFE4QkFmOEVCQUIDQmFBdOV3WURWUjBsCkJBd3dDZ11JS3dZQkJRVUhBd013REFZRFZSMERBUUgvQkFJdOFEQ
    dDZPQ11zdkp6QU5CZ2txaGtpRz13MEJBUXNGQUFPQOFRRUFEOF1Lb31Vd3VEM1AIM05UblFpYwpTSORwTExqTHdk
    LdWOyUzVuejhKR2xnSOJRZWVaCjFqQV10dTZOa0Zkdj JobXNCWUNjcVIZOTFXclpGSEV1YlhaOWxNek9pT2RFZOs
    c3UjExS21FCINYUGplsjhLSEZWU3pQcowajlsejVUelZ6K1RHUFMyQ1ZuQ2Z3awolNVIrbUNsNExHomRXTTU2dG
    05WSFE4QkFmOEVCQUIDQmFBdOV3WURWUjBsCkJBd3dDZ11JS3dZQkJRVUhBd013REFZRFZSMFRBUUgvQkFJdOFEQ
    dDZPQ11zdkp6QU5cz2txaGtpRz13MEJBUXNGQUFPOOFRRUFEOF1Lb31Vd VEM1A1M05UblFpYwpTSORwTExqTHdk

[^37]: 3. 84. 15.55 \| 172. 31. 89. 100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-172-31-86-230. ec2. internal
    Ready
    control-plane
    18m
    v1 . 29 . 2
    3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$

[^38]: Namespace --> it is like a project in your kubernetes cluster to provision your project
    resources. it is isolated
    every resource is YAML. ..a basic syntax is
    apiVersion :
    kind: # what kind of resource you are creating
    metadata:
    name :
    I

[^39]: EXPLORER
    minikube.tf
    workstation.tf
    !
    namespace.yaml X $ docker.sh
    REPOS
    k8-resources > 01-namespace > ! namespace.yaml > @ metadata
    > .github
    apiVersion: v1
    > ansible
    2
    kind: Namespace
    I
    3
    > catalogue
    metadata:
    4
    name: roboshop
    > catalogue-deploy
    > concepts
    > dockerfiles
    k8-resources \\ 01-namespace
    ! namespace.yaml

[^40]: F
    C
    github.com/new
    E
    New repository
    Q Type to search
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository,
    Required fields are marked with an asterisk (\*).
    Owner \*
    Repository name \*
    - daws-76s
    k8-resources
    k8-resources is available.
    Great repository names are short and memorable. Need inspiration? How about sturdy-rotary-phone ?
    Description (optional)
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    Private

[^41]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/terraform-aws-minikube
    $ cd . ./k8-resources/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources
    $ git init
    Initialized empty Git repository in C: /devops/daws-76s/repos/k8-resources/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git remote add origin git@github . com: daws-76s/k8-resources . git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    S

[^42]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main (root-commit) 822f6a5\] jenkins
    1 file changed, 4 insertions(+)
    create mode 100644 01-namespace/namespace . yam1

[^43]: 3. 84. 15.55 \| 172. 31. 89. 100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ git clone https: //github. com/daws-76s/k8-resources. git
    Cloning into 'k8-resources' .
    remote: Enumeratiog objects: 4, done.
    remote: Counting objects: 100% (4/4) , done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 4 (delta 0) , reused 4 (delta 0) , pack-reused 0
    Receiving objects: 100% (4/4) , done.
    3. 84. 15.55 \| 172. 31. 89.100 \| t2.micro \| null
    \[ centos@ip-172-31-89-100 \~ \]$ cd k8-resources/
    3. 84 . 15.55 \| 172 . 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources \]$ cd 01-namespace/

[^44]: 3. 84 . 15.55 \| 172 . 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ 1s -1
    total 4
    -rw-rw-r-- 1 centos centos 57 Feb 21 02:38 namespace. yaml

[^45]: 3. 84 . 15. 55 \| 172 . 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ kubectl create -f namespace. yaml
    namespace/roboshop created
    3. 84. 15.55 \| 172. 31.89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$

[^46]: 3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ kubectl get namespaces
    NAME
    STATUS
    AGE
    calico
    Active
    25m
    calico-system
    Active
    24m
    default
    Active
    25m
    kube-node-lease
    Active
    25m
    kube-public
    Active
    25m
    kube-system
    Active
    25m
    roboshop
    Active
    21s

[^47]: 3. 84 . 15. 55 \| 172. 31 . 89. 100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ kubectl create -f namespace . yaml
    Error from server (AlreadyExists) : error when creating "namespace. yaml": namespaces "roboshop" already exists

[^48]: 3. 84 . 15. 55 \| 172 . 31 . 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ kubectl delete -f namespace. yaml
    namespace "roboshop" deleted
    3. 84 . 15. 55 \| 172 . 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$

[^49]: 3. 84 . 15. 55 \| 172 . 31. 89.100 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ kubectl apply -f namespace. yaml
    namespace/roboshop created
    3. 84 . 15. 55 \| 172. 31. 89. 100 \| t2.micro \| https: //github.com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ kubectl apply -f namespace. yaml
    namespace/roboshop unchanged

[^50]: kubectl create -f <your. yaml> --> create resources, if you use this once again, you get error
    kubectl apply -f <your. yaml> --> if not created it will create, if you use again any changes
    it will update or it will say unchanged.
    kubectl delete -f yamlfile. yaml --> delete the resources
    kubectl get namespaces --> will get all namespaces in cluster
    kubectl get nodes

[^51]: B
    B
    B
    B
    SUCK ALAA
    Heathrow
    ULTra'
    Heathrow
    better
    ULTra
    210
    207

[^52]: pod vs container
    a pod can contain multiple containers, it is the smallest thing in kuberenetes

[^53]: File Edit Selection View Go
    . . .
    9 repos
    EXPLORER
    . .
    minikube.tf
    workstation.tf
    ! namespace.yaml
    ! 01-pod.yaml U X
    REPOS
    k8-resources > 02-pods > ! 01-pod.yaml > @apiVersion
    > .github
    apiVersion: v1
    > ansible
    2
    kind: Pod
    metadata:
    > catalogue
    8 12
    14
    name: hello-pod
    > catalogue-deploy
    5
    spec :
    > concepts
    16
    # list of containers
    > dockerfiles
    17
    containers :
    k8-resources
    18
    . name: hello-pod
    01-namespace
    9
    image: nginx
    I
    10
    ports:
    ! namespace.yaml
    11
    - containerPort: 80
    02-pods
    ! 01-pod.yaml
    U
    > learn-git

[^54]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 66410b0\] jenkins
    1 file changed, 11 insertions (+)
    create mode 100644 02-pods/01-pod. yam1

[^55]: 3. 84. 15. 55 \| 172. 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/01-namespace \]$ git pull
    remote: Enumeratiog objects: 5, done.
    remote: Counting objects: 100% (5/5) , done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 4 (delta 0) , reused 4 (delta 0), pack-reused 0
    Unpacking objects: 1008 (4/4), 411 bytes \| 411.00 KiB/s, done.

[^56]: 3. 84 . 15.55 \| 172 . 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ 1s
    01-pod . yaml
    3. 84 . 15. 55 \| 172. 31. 89. 100 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl apply -f 01-pod. yaml
    pod/hello-pod created
    3. 84. 15. 55 \| 172. 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos(ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    13s

[^57]: 3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get ns
    NAME
    STATUS
    AGE
    calico
    Active
    35m
    calico-system
    Active
    34m
    default
    Active
    35m
    kube-node-lease
    Active
    35m
    kube-public
    Active
    35m
    kube-system
    Active
    35m
    roboshop
    Active
    9m16s

[^58]: 3. 84. 15. 55 \| 172 . 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl delete -f 01-pod. yaml
    pod "hello-pod" deleted

[^59]: EXPLORER
    minikube.tf
    workstation.tf
    ! namespace.yaml
    ! 01-pod.ya
    V REPOS
    k8-resources > 02-pods > ! 01-pod.yaml > {} metadata > namespace
    > .github
    apiVersion: v1
    > ansible
    2
    kind: Pod
    3
    metadata:
    > catalogue
    14
    name: hello-pod
    > catalogue-deploy
    I
    5
    namespace: roboshop
    > concepts
    6
    spec:
    > dockerfiles
    # list of containers
    k8-resources
    18
    containers :
    01-namespace
    9
    name: hello-pod
    10
    ! namespace.yaml
    image: nginx
    11
    ports :
    02-pods
    12
    - containerPort: 80
    ! 01-pod.yaml
    M
    > learn-git
    > learn-jenkins
    > notes

[^60]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add
    . ; git commit -m "jenkins"; git push origin main
    \[main 4b557ff\] jenkins
    1 file changed, 1 insertion (+)

[^61]: 3. 84 . 15. 55 \| 172. 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7), done.

[^62]: 3. 84 . 15.55 \| 172 . 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl apply -f 01-pod. yaml
    pod/hello-pod created

[^63]: 3. 84. 15. 55 \| 172. 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    No resources found in default namespace.
    3. 84 . 15.55 \| 172 . 31 . 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods -n roboshop
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    hello-pod
    1/1
    Running
    0
    17s

[^64]: POD
    IP address
    catalogue
    ELK
    CONT1
    CONT2
    sidecar
    proxy
    init containers
    N/W and storage

[^65]: One Call
    Harth
    HAYLEY
    MITCHELLS
    ENOR
    One CAR

[^66]: EXPLORER
    . . .
    kube.tf
    workstation.tf
    ! namespace.yaml
    REPOS
    k8-resources > 02-pods > ! 02-multi-container.yaml > {} spe
    > .github
    apiVersion: v1
    > ansible
    Z
    kind: Pod
    3
    > catalogue
    metadata:
    4
    name: multi-container
    > catalogue-deploy
    15
    spec :
    > concepts
    16
    # list of containers
    > dockerfiles
    7
    containers :
    k8-resources
    8
    name: nginx
    01-namespace
    9
    image: nginx
    ! namespace.yaml
    ports :
    - containerPort: 80
    02-pods
    name: almalinux
    ! 01-pod.yaml
    13
    image: almalinux: 8
    ! 02-multi-container.yaml
    U
    14
    command: \["sleep", "300"\]

[^67]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main
    S git add . ; git commit -m "jenkins"; git push origin main
    \[main 571a5b4\] jenkins
    1 file changed, 14 insertions (+)
    create mode 100644 02-pods/02-multi-container . yam1

[^68]: \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl apply -f 02-multi-container. yaml
    pod/multi-container created
    3. 84 . 15.55 \| 172 . 31. 89.100 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    multi-container
    0/2
    ContainerCreating
    5s
    3. 84. 15.55 \| 172. 31. 89.100 \| t2.micro \| https: / /github.com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    multi-container
    0/2
    ContainerCreating
    0
    7s
    3. 84 . 15.55 \| 172. 31.89. 100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    multi-container
    2/2
    Running
    0
    10s

[^69]: 3. 84 . 15.55 \| 172. 31.89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl exec -it multi-container -c almalinux -- bash
    \[root@multi-container /\]#

[^70]: 3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl exec -it multi-container -c almalinux -- bash
    \[root@multi-container /\]# curl localhost
    <!DOCTYPE html>
    <html>
    Khead>
    <title>Welcome to nginx!</title>
    Kstyle>
    html { color-scheme: light dark; }
    body { width: 35em; margin: 0 auto;
    font-family: Tahoma, Verdana, Arial, sans-serif; }
    </style>
    K/head>
    <body>
    hi>Welcome to nginx!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required. </p>

[^71]: apiversion: v1
    kind: Pod
    metadata:
    name: label-demo
    labels:
    qvironment: production
    app: nginx

[^72]: EXPLORER
    . . .
    ition.tf
    ! namespace.yaml
    ! 01-pod.yaml
    ! 02-multi-container.yaml
    V REPOS
    k8-resources > 02-pods > ! 03-labels.yaml > {} metadata > {} labels > .) Trainer
    1
    apiVersion: v1
    > ansible
    2
    kind: Pod
    > catalogue
    3
    metadata:
    > catalogue-deploy
    4
    name: label-demo
    > concepts
    15
    labels:
    > dockerfiles
    6
    course: Devops
    7
    Trainer: "SivakumarReddy"
    k8-resources
    8
    spec:
    01-namespace
    9
    # list of containers
    ! namespace.yaml
    10
    containers:
    02-pods
    11
    - name: hello-pod
    ! 01-pod.yaml
    12
    image: nginx
    ! 02-multi-container.yaml
    13
    ports :
    14
    - containerPort: 80
    ! 03-labels.yaml

[^73]: 3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources.g
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 4 (delta 0) , reused 4 (delta 0) , pack-reused 0
    Unpacking objects: 100% (4/4), 526 bytes \| 526.00 KiB/s, done.
    From https: //github . com/daws-76s/k8-resources
    571a5b4 . . 54f0e3c main
    -> origin/main
    Updating 571a5b4. . 54f0e3c

[^74]: 3. 84 . 15.55 \| 172 . 31. 89. 100 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl apply -f 03-labels. yaml
    pod/label-demo created
    3. 84 . 15.55 \| 172. 31. 89. 100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    label-demo
    1/1
    Running
    O
    4s
    multi-container
    2/2
    Running
    1 (3s ago)
    5m10s

[^75]: \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl describe pod label-demo
    Name:
    label-demo
    Namespace :
    default
    Priority :
    O
    Service Account:
    default
    Node :
    ip-172-31-86-230. ec2. internal/172 . 31 . 86.230
    Start Time:
    Wed, 21 Feb 2024 03:12:11 +0000
    Labels :
    Trainer=SivakumarReddy
    course=Devops
    Annotations :
    cni . projectcalico . org/containerID: 88af27d66d51acbd467daca2d2e55e8b73c844103f3f
    cni . projectcalico. org/podIP: 192. 168. 199.133/32
    cni . projectcalico. org/podIPs: 192. 168. 199.133/32
    Status :
    Running
    IP :
    192 . 168 . 199.133
    IPS :

[^76]: 3.84.15.55
    Environment:
    <none>
    Mounts :
    /var/run/secrets/kubernetes . io/serviceaccount from kube-api-access-7fzqs (ro)
    Conditions :
    Type
    Status
    PodReadyToStartContainers
    True
    Initialized
    True
    Ready
    True
    ContainersReady
    True
    PodScheduled
    True
    Volumes :
    kube-api-access-7fzqs :
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
    Tolerations:
    node . kubernetes . io/not-ready : NoExecute op=Exists for 300s
    node . kubernetes . io/unreachable : NoExecute op=Exists for 300s
    Events :
    Type
    Reason
    Age
    From
    Message
    Normal
    Scheduled
    19s
    default-scheduler Successfully assigned default/label-demo to ip-172-31-86-230.ec2.internal
    Normal
    Pulling
    18s
    kubelet
    Pulling image "nginx"
    Normal
    Pulled
    18s
    kubelet
    Successfully pulled image "nginx" in 167ms (167ms including waiting)
    Normal
    Created
    18s
    kubelet
    Created container hello-pod
    Normal
    Started
    18s
    kubelet
    Started container hello-pod
    3. 84. 15.55 \| 172 . 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$

[^77]: labels vs annotaions
    - -------
    labels --> have some limitation on the length and charecters of key and values
    annotaions --> no limit on length and special charecters also can be used...
    labels are used to select other kubernetes resources.
    annotaions are used to select external resources to kubernetes.

[^78]: V REPOS
    k8-resources > 02-pods > ! 04-annotations.yaml > {} metadata > {} annotations > < co
    anisibie
    1
    apiVersion: v1
    > catalogue
    2
    kind: Pod
    > catalogue-deploy
    3
    metadata :
    > concepts
    4
    name: annotations
    > dockerfiles
    5
    labels :
    6
    k8-resources
    course: Devops
    7
    Trainer: "SivakumarReddy"
    01-namespace
    8
    annotations :
    ! namespace.yaml
    9
    com . roboshop . training . duration: "120 hours"
    02-pods
    10
    jenkins . url: "https://jenkins. com/roboshop/catalogue#45"
    ! 01-pod.yaml
    11
    spec:
    ! 02-multi-container.yaml
    12
    # list of containers
    ! 03-labels.yaml
    13
    containers :
    14
    ! 04-annotations.yaml
    M
    name: hello-pod
    15
    image: nginx
    > learn-git
    16
    ports :
    > learn-jenkins
    17
    - containerPort: 80

[^79]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main cala20f\] jenkins
    1 file changed, 17 insertions (+)
    create mode 100644 02-pods/04-annotations . yam1

[^80]: 3. 84 . 15.55 \| 172. 31. 89. 100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl apply -f 04-annotations. yaml
    pod/annotations created
    3. 84 . 15. 55 \| 172. 31. 89. 100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$

[^81]: 3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    annotations
    1/1
    Running
    7s
    label-demo
    1/1
    Running
    NOO
    5m41s
    multi-container
    2/2
    Running
    2 (39s ago)
    10m

[^82]: 3. 84 . 15.55 \| 172. 31. 89.100 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl describe pod annotations
    Name :
    annotations
    Namespace:
    default
    Priority:
    0
    Service Account:
    default
    Node :
    ip-172-31-86-230. ec2 . internal/172 . 31. 86.230
    Start Time:
    Wed, 21 Feb 2024 03:17:45 +0000
    Labels :
    Trainer=SivakumarReddy
    course=Devops
    Annotations :
    cni . projectcalico. org/containerID: bic92deed8b80ce2c3857f2f484146a82f962d3116637e715ce32533d309ef4f
    cni . projectcalico. org/podIP: 192. 168. 199.134/32
    cni . projectcalico . org/podIPs: 192 . 168 . 199.134/32
    com . roboshop . training . duration: 120 hours
    jenkins . url: https://jenkins . com/roboshop/catalogue#45
    Status :
    Running
    IP:
    192 . 168 . 199 .134
    IPS :
    IP: 192. 168 .199 .134
    Containers :
    hello-pod:
    Container ID:
    containerd: //24a9fe62fc6926fcc872d5613de30f78ecc7cb3430bc0c9b8f8d2c6e797731ad
    Image :
    nginx
    Image ID:
    docker . io/library/nginx@sha256: c26ae7472d624balfafd296e73cecc4f93f853088e6a9c13c0d52f6ca5865107
    Port:
    80/TCP

[^83]: Kubernetes Labels
    Kubernetes Annotations
    Attach identifying metadata to objects.
    Hold non-identifying metadata
    Primary use
    Help select, group, or filter Kubernetes
    that third-party tools and clients
    case
    objects
    can retrieve
    Short, long, structured, and
    Metadata type
    Short and unstructured
    Winstructured
    Used in
    Yes
    No
    operating?
    Both the name (up to 63 characters
    Name is required and must be 63
    Character set
    long) and prefix (up to 253 characters
    characters or less.
    and syntax
    long) are required
    Prefix is optional

[^84]: EXPLORER
    yaml
    ! 02-multi-container.yaml
    ! 03-labels.yaml
    0
    V REPOS
    k8-resources > 02-pods > ! 05-env.yaml > {} spec > \[ \] containers >
    Lalalogue
    1
    apiVersion: v1
    > catalogue-deploy
    2
    kind: Pod
    > concepts
    13
    metadata :
    > dockerfiles
    4
    name: envar -demo
    k8-resources
    5
    labels :
    01-namespace
    6
    purpose: demonstrate-envars
    7
    spec:
    namespace.yaml
    8
    containers :
    v 02-pods
    9
    -
    name: envar-demo-container
    ! 01-pod.yaml
    10
    image: nginx
    ! 02-multi-container.yaml
    env:
    ! 03-labels.yaml
    -
    name: DEMO_GREETING
    ! 04-annotations.yaml
    value: "Hello from the environment"
    ! 05-env.yaml
    U
    name : DEMO_FAREWELL
    15
    value: "Such a sweet sorrow"
    > learn-git
    16
    learn-jenkins

[^85]: 3. 84 . 15. 55 \| 172 . 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (3/3) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4) , 514 bytes \| 514.00 KiB/s, done.
    From https: / /github. com/daws-76s/k8-resources
    Oef0le9. . 6a46782
    main
    -> origin/main

[^86]: 3. 84 . 15.55 \| 172. 31. 89. 100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl apply -f 05-env. yaml
    pod/envar-demo created

[^87]: 3. 84. 15. 55 \| 172. 31. 89.100 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-100 \~/k8-resources/02-pods \]$ kubectl exec -it envar-demo -- bash
    root@envar-demo : /# env
    KUBERNETES SERVICE PORT HTTPS=443
    KUBERNETES SERVICE PORT=443
    HOSTNAME=envar-demo
    DEMO FAREWELL=Such a sweet sorrow
    PWD=/
    PKG RELEASE=1\~bookworm
    HOME=/ root
    KUBERNETES PORT 443 TCP=tcp : / /10 . 96 . 0 . 1: 443
    NJS VERSION=0 . 8. 3
    TERM=xterm
    SHLVL=1
    KUBERNETES PORT 443 TCP PROTO=tcp
    KUBERNETES PORT 443 TCP ADDR=10 . 96.0.1
    KUBERNETES SERVICE HOST=10 .96 .0.1
    KUBERNETES PORT=top : / /10 . 96 . 0 .1: 443
    KUBERNETES PORT 443 TCP PORT=443
    PATH=/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin
    NGINX VERSION=1 . 25 . 4
    DEMO GREETING-Hello from the environment
    =/usr/bin/env

