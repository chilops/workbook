---
title: 59Day_Kubernetes
uuid: 5d3dae66-43fd-11ef-8f52-6ef34fa959ce
version: 1044
created: '2024-07-17T10:58:14+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#f8914d;">**HELM Charts**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

What HELM do is keeping all the constant values separate and values which are going to change will maintain separately.

\

![ea2bb69a-0e63-4a35-a288-11d3873196e0.png|618](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ea2bb69a-0e63-4a35-a288-11d3873196e0.png) [^1]

\

# <mark style="background-color:#f8914d;">**Templatize the Kubernetes manifests**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![f7daaaf3-c4b2-45be-9583-f4431c4d9f22.png|1000.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/f7daaaf3-c4b2-45be-9583-f4431c4d9f22.png) [^2]

![a50dafba-521f-4291-b524-18c4ccec241b.png|1001.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a50dafba-521f-4291-b524-18c4ccec241b.png) [^3]

\

<mark>**Installing HELM**</mark>

\

![344d74fa-d0ce-4500-b0b1-51a306887a16.png|993.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/344d74fa-d0ce-4500-b0b1-51a306887a16.png) [^4]

\

```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

![3b3a1360-9736-4cc7-8750-b4ea0665d55f.png|1031.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3b3a1360-9736-4cc7-8750-b4ea0665d55f.png) [^5]

![689ad1e2-d49b-43de-a258-fdcb21edc344.png|647](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/689ad1e2-d49b-43de-a258-fdcb21edc344.png) [^6]

\

```
helm version
```

![a2d3b8a8-0f1d-4093-a509-faacb5130a48.png|1047.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a2d3b8a8-0f1d-4093-a509-faacb5130a48.png) [^7]

\

<mark>**HELM charts structure**</mark>

![9cdaee51-f376-454c-a053-79939741ca14.png|1046.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/9cdaee51-f376-454c-a053-79939741ca14.png) [^8]

\

<mark>**Chart.yaml** is the first file</mark>

![8d5e2b46-dd00-4e86-bbc9-94e11174d7aa.png|1043.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/8d5e2b46-dd00-4e86-bbc9-94e11174d7aa.png) [^9]

\

![cd4a7cc9-9c2a-484e-a522-e5a124854061.png|1005](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/cd4a7cc9-9c2a-484e-a522-e5a124854061.png) [^10]

\

Chart.yaml

![3768fd3a-7173-4a65-af61-54cfc9dead38.png|959](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3768fd3a-7173-4a65-af61-54cfc9dead38.png) [^11]

\

<mark>**templates** is the second required folder (what Kubernetes resources we are using those we should keep it here)</mark>

deployment.yaml

![39d3bbc7-3798-464d-aec6-9118252b1bb5.png|964](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/39d3bbc7-3798-464d-aec6-9118252b1bb5.png) [^12]

\

service.yaml

![bf2558d7-8213-416c-b5cd-32009b78b9d1.png|838](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/bf2558d7-8213-416c-b5cd-32009b78b9d1.png) [^13]

\

<mark>**HELM Commands**</mark>

![573a3e10-82a5-4080-b972-519ebd18d297.png|1135.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/573a3e10-82a5-4080-b972-519ebd18d297.png) [^14]

\

repo creation for helm

![936de267-0a0b-4ab6-85ca-27bbe83988f9.png|1135.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/936de267-0a0b-4ab6-85ca-27bbe83988f9.png) [^15]

\

![803ae956-3aff-45a7-8404-f6721e7373d1.png|1023](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/803ae956-3aff-45a7-8404-f6721e7373d1.png) [^16]

![f3d80d23-88a6-4abb-8f6a-1d6fa3980d52.png|1025](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/f3d80d23-88a6-4abb-8f6a-1d6fa3980d52.png) [^17]

\

![82bbfa19-c602-4191-96bc-a9d6cbe6864a.png|1141.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/82bbfa19-c602-4191-96bc-a9d6cbe6864a.png) [^18]

\

```
helm install nginx .
```

![02d19590-b884-48c2-a73b-3ff1758235da.png|1178.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/02d19590-b884-48c2-a73b-3ff1758235da.png) [^19]

\

```
helm list
```

![c59327f4-3cf6-4575-850f-e0f36a6cb477.png|1205.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c59327f4-3cf6-4575-850f-e0f36a6cb477.png) [^20]

\

<mark>**HELM Values**</mark>

values.yaml

![6eccd6bd-6cd9-46dd-baf2-04830e87f48d.png|777](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/6eccd6bd-6cd9-46dd-baf2-04830e87f48d.png) [^21]

\

changing the version

![44ec3239-ec6a-426b-9dab-09b3ffa19803.png|891](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/44ec3239-ec6a-426b-9dab-09b3ffa19803.png) [^22]

\

git push & pull

![84d4bb06-0813-4948-bf3a-1163a836b1b2.png|971](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/84d4bb06-0813-4948-bf3a-1163a836b1b2.png) [^23]

\

```
helm upgrade nginx .
```

![b17c0277-32eb-4a7c-a3b7-85624e9e26d2.png|1143.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/b17c0277-32eb-4a7c-a3b7-85624e9e26d2.png) [^24]

\

```
kubectl get pods
```

![10d6525a-a1ef-4e88-9706-3d91c3694d44.png|1151.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/10d6525a-a1ef-4e88-9706-3d91c3694d44.png) [^25]

\

\

to see how many times we deployed and upgraded

```
helm list
helm history nginx
```

![e4199316-4e0b-4fc0-af0b-089df075b814.png|1193.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/e4199316-4e0b-4fc0-af0b-089df075b814.png) [^26]

\

We can do rollback if upgraded app version is not running well. (how fast we are doing rollback is important) then we will not loose the business

```
helm rollback nginx
kubectl get pods
```

![90e9fcb0-c749-4708-809d-d50d70b567e9.png|1205.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/90e9fcb0-c749-4708-809d-d50d70b567e9.png) [^27]

\

\

Rollback completed with in seconds (it goes 1 version back)

```
helm history nginx
```

![ff1b79d5-669e-46a7-b93e-213386abcb45.png|1203.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ff1b79d5-669e-46a7-b93e-213386abcb45.png) [^28]

\

\

**If you want to rollback particular version (out of 10 versions)**

```
helm rollback nginx 2
kubectl get pods
```

![408000a7-0a49-4fe7-8a35-0b7151feba6f.png|1123.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/408000a7-0a49-4fe7-8a35-0b7151feba6f.png) [^29]

\

To see the values present

```
helm show values .
```

![a3f32f70-eac1-409e-83e0-19a1079825ff.png|1140](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a3f32f70-eac1-409e-83e0-19a1079825ff.png) [^30]

\

helm setting the values through command line ( changing replicas from 3 to 10)

```
helm upgrade nginx --set deployment.replicas=10
```

![7c7aa31c-e3d2-4087-882e-b826855539e5.png|1149.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/7c7aa31c-e3d2-4087-882e-b826855539e5.png) [^31]

\

```
kubectl get pods
```

![be4dd722-6426-4f11-a39c-45f384c07603.png|1197.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/be4dd722-6426-4f11-a39c-45f384c07603.png) [^32]

\

# <mark style="background-color:#f8914d;">**HELM Package manager for Kubernetes**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

![3a56b93d-3469-471d-bc0a-3c3a314ef9b9.png|970.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3a56b93d-3469-471d-bc0a-3c3a314ef9b9.png) [^33]

\

for example if we need to install EBS drivers

we need to add helm repos

![08b90351-ff24-4c90-b19a-43eae7d16de3.png|1222.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/08b90351-ff24-4c90-b19a-43eae7d16de3.png) [^34]

\

Adding helm repo

```
helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
```

![070e11cb-e43e-46c4-9c7f-2d40282b659d.png|1245.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/070e11cb-e43e-46c4-9c7f-2d40282b659d.png) [^35]

\

To see helm repos 

```
helm repo list
```

![c2c1835c-2989-41f7-a757-daef24434c56.png|1248.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c2c1835c-2989-41f7-a757-daef24434c56.png) [^36]

\

to get latest repo updates

```
helm repo update
```

![5fe0dc99-c506-4aca-9e75-790651cf5b00.png|1254.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/5fe0dc99-c506-4aca-9e75-790651cf5b00.png) [^37]

\

Installing csi drivers

```
helm upgrade --install aws-ebs-csi-driver --namespace kube-system aws-ebs-csi-driver/aws-ebs-csi-driver
```

![5b5ae242-6a48-4da1-96d7-01c531437580.png|1255.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/5b5ae242-6a48-4da1-96d7-01c531437580.png) [^38]

\

```
helm list -n kube-system
```

![2683b215-5f88-45fd-aaad-638f94112470.png|1253.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/2683b215-5f88-45fd-aaad-638f94112470.png) [^39]

\

To uninstall

```
helm uninstall aws-ebs-csi-driver -n kube-system
helm list -n kube-system
```

![70f1c973-6d90-4405-bcf5-3f366f68fa78.png|1253.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/70f1c973-6d90-4405-bcf5-3f366f68fa78.png) [^40]

![70624a75-1f0c-4c9d-93d3-894990db68cd.png|1257.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/70624a75-1f0c-4c9d-93d3-894990db68cd.png) [^41]

\

To install applications in kubernetes helm is so useful

![b0cf8b36-205f-4b49-a1e2-bd18a600a95a.png|1270.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/b0cf8b36-205f-4b49-a1e2-bd18a600a95a.png) [^42]

\

```
helm uninstall nginx
```

![](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/98d92c94-4a2d-4557-8b72-eb2bf975db13.png) [^43]

```
kubectl get pods
```

![d5c5c096-c87e-45d0-aced-8b02387e6eec.png|1188.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/d5c5c096-c87e-45d0-aced-8b02387e6eec.png) [^44]

\

\

# <mark style="background-color:#f8914d;">**Stateful Sets**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![8a8907c0-1dc2-4408-ad31-d3974508c17b.png|918](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/8a8907c0-1dc2-4408-ad31-d3974508c17b.png) [^45]

\

\

StatefulSet is little complex

![](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/713fabd9-240a-4bc3-b366-120ca9a8c205.png) [^46]

\

![06281f0d-2c71-4463-aebc-89eae23ef908.png|1203.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/06281f0d-2c71-4463-aebc-89eae23ef908.png) [^47]

![c8de25ca-2cb0-466b-8e95-ee71221c4e10.png|720](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c8de25ca-2cb0-466b-8e95-ee71221c4e10.png) [^48]

\

<mark>Q: Difference between StatefulSet & Deployment?</mark>

![52c80428-f3bd-4b6b-998f-cc70a98c4037.png|613](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/52c80428-f3bd-4b6b-998f-cc70a98c4037.png) [^49]

![6a44b1ba-cfc4-4c47-9372-4c26b906ebf9.png|407](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/6a44b1ba-cfc4-4c47-9372-4c26b906ebf9.png) [^50]

\

![3a4f9681-807b-4fd7-8e76-1dbdd56e89d0.png|719](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3a4f9681-807b-4fd7-8e76-1dbdd56e89d0.png) [^51]

1. <mark>**Install CSI drivers**</mark>


  ```
  helm upgrade --install aws-ebs-csi-driver --namespace kube-system aws-ebs-csi-driver/aws-ebs-csi-driver
  ```

![309a5c4d-564b-49ce-b51c-ecd2937f56db.png|1153.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/309a5c4d-564b-49ce-b51c-ecd2937f56db.png) [^52]

\

<mark>**2 . provide IAM role to EC2 instance**</mark> 

![73d98345-18eb-44d9-aacf-0d781fbd0768.png|1010.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/73d98345-18eb-44d9-aacf-0d781fbd0768.png) [^53]

\

![cf944f33-edf4-483f-9c01-ae25b73274cc.png|1081.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/cf944f33-edf4-483f-9c01-ae25b73274cc.png) [^54]

\

<mark>**3 . Installing the storage class**</mark>

![3a68ff29-edaa-4850-88fb-987153acc952.png|1045.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3a68ff29-edaa-4850-88fb-987153acc952.png) [^55]

\

```
kubectl apply -f ebs-sc.yaml
kubectl get sc
```

![1e763f11-f1bd-49d6-a3d1-b531decb11db.png|1135.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/1e763f11-f1bd-49d6-a3d1-b531decb11db.png) [^56]

\

Now creating StatefulSet 

![4ee99d17-cd99-430d-9121-744912a96d5a.png|1098](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/4ee99d17-cd99-430d-9121-744912a96d5a.png) [^57]

\

git push & pull

![8411dbc3-c4e1-403f-8b72-6df37d12cdae.png|1126.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/8411dbc3-c4e1-403f-8b72-6df37d12cdae.png) [^58]

\

```
kubectl apply -f 03-statefulset.yaml
```

![2a50d003-cada-4433-831e-30b35df1a7a1.png|1133.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/2a50d003-cada-4433-831e-30b35df1a7a1.png) [^59]

\

<mark>**In StatefulSet one by one pods will create(not all at a time)**</mark>

```
kubectl get pods
kubectl get pv
```

![12ff1bce-d1b3-4e03-bace-d4439c252d0f.png|1130.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/12ff1bce-d1b3-4e03-bace-d4439c252d0f.png) [^60]

![a482c540-8bd8-4d0b-b185-3dbcd97cd9e7.png|1121.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a482c540-8bd8-4d0b-b185-3dbcd97cd9e7.png) [^61]

![7342570b-c2ab-41bd-87a6-b23e7b9cc574.png|1132.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/7342570b-c2ab-41bd-87a6-b23e7b9cc574.png) [^62]

\

Now each POD will have each volume in  StatefulSet

![1bfa5f01-b362-4ee4-b6b5-eabb2d001899.png|1182.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/1bfa5f01-b362-4ee4-b6b5-eabb2d001899.png) [^63]

\

# <mark style="background-color:#F8914D;">**Headless service**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

<mark>**Headless service is used for stateful applications,**</mark> **when you pick headless service instead of single IP address you will get all PODS IP address in same cluster. So that it is easy for replica to communicate with other replicas.**

![f6969b5a-9560-4389-b46e-4b70a60c304d.png|610](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/f6969b5a-9560-4389-b46e-4b70a60c304d.png) [^64]

\

Running deployment.yaml (to show difference between StatefulSet(headless) & deployment)

```
kubectl apply -f 02-deployment-set.yaml
```

![85ebfb3a-f61a-4da3-aecd-9bfe3f1f375b.png|1162.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/85ebfb3a-f61a-4da3-aecd-9bfe3f1f375b.png) [^65]

\

<mark>its getting a random name</mark>

```
kubectl get pods
```

![2a666277-6890-4220-944e-836ab12ee7ee.png|1208.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/2a666277-6890-4220-944e-836ab12ee7ee.png) [^66]

\

<mark>For normal deployment we have ClusterIP but for StatefulSet we don't have ClusterIP(None)</mark>

```
kubectl get svc
```

![a4a6502e-153a-4325-b955-58a94c1bf793.png|1182.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a4a6502e-153a-4325-b955-58a94c1bf793.png) [^67]

\

**to check why... we creating a debug pod**

```
kubectl apply -f ../02-pods/03-labels.yaml
```

![e3234a87-6c34-4dcc-b75d-49869419d385.png|1182.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/e3234a87-6c34-4dcc-b75d-49869419d385.png) [^68]

\

```
kubectl exec -it label-demo -- bash
nslookp
apt update
apt install bind9-utils
apt install dnsutils
```

![636725f5-9689-482b-b1ff-7bd45812a9a8.png|1203.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/636725f5-9689-482b-b1ff-7bd45812a9a8.png) [^69]

![969a58da-e7b2-4a24-a890-6d3d9358eba6.png|777](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/969a58da-e7b2-4a24-a890-6d3d9358eba6.png) [^70]

![b4a9ca2f-1713-465e-8289-f64baaddefcd.png|1073](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/b4a9ca2f-1713-465e-8289-f64baaddefcd.png) [^71]

\

Now if i give nslookup nginx service -- this is the nginx server IP address

```
nslookup nginx-service
```

![8d0bf305-4d44-46fa-a37a-4a18da63e36d.png|1045.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/8d0bf305-4d44-46fa-a37a-4a18da63e36d.png) [^72]

\

```
nslookup nginx
```

![21507c1b-f561-4c6b-9d8b-b786493d29b3.png|633](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/21507c1b-f561-4c6b-9d8b-b786493d29b3.png) [^73]

\

it can communicate with background DB's

```
kubectl get pods -o wide
```

![fc9ff832-014b-44fe-ac9d-cd7047b79588.png|1127.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/fc9ff832-014b-44fe-ac9d-cd7047b79588.png) [^74]

![917fc8a8-cd91-43b4-a995-f03dbc3409af.png|650](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/917fc8a8-cd91-43b4-a995-f03dbc3409af.png) [^75]

\

Just if i delete StatefulSet

```
kubectl delete -f 03-statefulset.yaml
```

![ec14f357-2f70-4451-9a2c-0b2c1c012a50.png|1108.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ec14f357-2f70-4451-9a2c-0b2c1c012a50.png) [^76]

\

the pods will delete in reverse order

```
watch kubectl get pods
```

![c75efe1d-8b65-46f7-a038-4639d5c66d5c.png|1167.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c75efe1d-8b65-46f7-a038-4639d5c66d5c.png) [^77]

\

In StatefulSet PV & volumes wont delete( so that we can use the data present in the volumes for new pods)

```
kubectl get pv
kubectl get pvc
```

![037be0e3-683d-44fd-9d75-2fcb96596c5c.png|1150.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/037be0e3-683d-44fd-9d75-2fcb96596c5c.png) [^78]

![a197a8ea-d1a6-44b2-a7f7-90337da022b5.png|1149.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a197a8ea-d1a6-44b2-a7f7-90337da022b5.png) [^79]

\

\

If we create new pods now these pods will stick to above volumes

```
kubectl apply -f 03-statefulset.yaml
kubectl get pods
```

![92ef970a-a0b4-456d-9473-a4989d8df755.png|1151.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/92ef970a-a0b4-456d-9473-a4989d8df755.png) [^80]

\

![3bbe1378-0f42-46f5-874b-9580805137af.png|1054.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3bbe1378-0f42-46f5-874b-9580805137af.png) [^81]

\

Now to delete pods and PVC (if you delete PVC then PV also auto delete )

```
kubectl delete -f 03-statefulset.yaml
kubectl get pvc
kubectl delete pvc www-web-0 www-web-1 www-web-2
```

![3f4e3adf-398e-4d0b-9a96-787a3d0e012b.png|1167.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3f4e3adf-398e-4d0b-9a96-787a3d0e012b.png) [^82]

\

now volumes also deleted

![f46ac1a9-73a5-420e-aea8-60f2ba6c86bb.png|1170.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/f46ac1a9-73a5-420e-aea8-60f2ba6c86bb.png) [^83]

\

\

# <mark style="background-color:#F8914D;">**DB's using StatefulSet (MongoDB)**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

mongodb

![6d5f1624-ba3e-4bf5-af9d-1dee6af530f4.png|916](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/6d5f1624-ba3e-4bf5-af9d-1dee6af530f4.png) [^84]

\

statefulset.yaml  (image joindevops should change to your docker login)

![a8a8cbea-80ee-4bd7-b6ec-ec9d6c97c9ac.png|1047](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a8a8cbea-80ee-4bd7-b6ec-ec9d6c97c9ac.png) [^85]

\

\

![c21a4836-f42e-438b-89a2-01faa516b261.png|888](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c21a4836-f42e-438b-89a2-01faa516b261.png) [^86]

\

repo creation

![c50a5690-7fe6-41b0-a97f-a7735d806a16.png|1067.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c50a5690-7fe6-41b0-a97f-a7735d806a16.png) [^87]

![](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/60ec6931-4fe3-40a2-9fee-d5cf4648b223.png) [^88]

![](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/0db8bd0e-792c-4628-8eea-3b1818dddf30.png) [^89]

\

![f1ddd1b5-4189-480c-9f2a-40f63de47b49.png|1188.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/f1ddd1b5-4189-480c-9f2a-40f63de47b49.png) [^90]

\

\

![7dc4c88b-1b31-4f77-a394-a7f1c2b28fe9.png|1176.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/7dc4c88b-1b31-4f77-a394-a7f1c2b28fe9.png) [^91]

\

```
helm install mongodb .
```

![12bb587f-6ebb-40c0-9dcc-7f7c1f1c00e7.png|1047.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/12bb587f-6ebb-40c0-9dcc-7f7c1f1c00e7.png) [^92]

```
helm list
```

![e4717512-b142-4508-a143-2778293152cb.png|1133.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/e4717512-b142-4508-a143-2778293152cb.png) [^93]

\

one by one pods created

```
kubectl get pods
```

![f36b59cf-9c5a-4b66-8296-dd228374a5f9.png|1163.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/f36b59cf-9c5a-4b66-8296-dd228374a5f9.png) [^94]

\

Now delete pods

```
helm uninstall mongodb
```

![4d66c15a-5feb-41c5-beea-4992c93b243d.png|1172.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/4d66c15a-5feb-41c5-beea-4992c93b243d.png) [^95]

\

but PVC and volumes wont delete

```
kubectl get pvc
```

![8ce626ad-6e60-477e-81c3-fd2a1175e074.png|1165.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/8ce626ad-6e60-477e-81c3-fd2a1175e074.png) [^96]

\

we need to delete manually

```
kubectl delete pvc mongodb-web-0 monogodb-web-1
```

![ae5ad23e-5799-4f68-acaa-d750a269cda4.png|1215.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ae5ad23e-5799-4f68-acaa-d750a269cda4.png) [^97]

\

\

Installing mongodb pods again

```
helm install mongodb .
```

![c9c1d213-f611-42eb-a7e0-d4865a7fbcf0.png|1213.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/c9c1d213-f611-42eb-a7e0-d4865a7fbcf0.png) [^98]

\

```
kubectl get pods
kubectl logs -f mongodb-0
```

![3525e77e-b393-4039-a0bf-541c2a095e68.png|1262.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/3525e77e-b393-4039-a0bf-541c2a095e68.png) [^99]

![ff9aef4d-305b-493b-963a-d66e03108f0c.png|1255.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ff9aef4d-305b-493b-963a-d66e03108f0c.png) [^100]

\

new volumes created ( check tags also)

![5197783f-b4b8-464e-94fb-8c2b113e4d12.png|1173.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/5197783f-b4b8-464e-94fb-8c2b113e4d12.png) [^101]

\

now increasing the replicas count to 3

![48c08af0-6e92-456e-b0cc-ee990c91d97f.png|899](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/48c08af0-6e92-456e-b0cc-ee990c91d97f.png) [^102]

\

git push & pull

![ff935d6b-419f-4fee-8bc9-9f3c82238a9c.png|1138.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ff935d6b-419f-4fee-8bc9-9f3c82238a9c.png) [^103]

\

new pod creating

```
helm upgrade mongodb .
kubectl get pods
```

![afa8d64b-cac3-420d-9b66-8676bd561fa5.png|1175.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/afa8d64b-cac3-420d-9b66-8676bd561fa5.png) [^104]

![d2b127b0-6309-4d96-a0f7-1583ac053d8b.png|1181.3333740234375](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/d2b127b0-6309-4d96-a0f7-1583ac053d8b.png) [^105]

\

\

<mark>**Keeping DB's in kubernetes is not recommended,  (DB teams upgrades is difficult for DB's , end customer data(DB)we should not keep in kubernetes)**</mark>

<mark>**In any interview if they ask if your MYSQL & other DB are running in Kubernetes? tell them NO**</mark>

![abffda7e-44b9-4a57-8aa8-741b9bc0e2d4.png|717](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/abffda7e-44b9-4a57-8aa8-741b9bc0e2d4.png) [^106]

[^1]: Helm Charts
    1. templatise the kubernetes manifests
    2. package manager for kubernetes

[^2]: daws-763/k8-eksctl
    x \| @ Clusters \| Elastic Kubernetes Sei X
    Helm
    + > C \* helm.sh
    Home
    Docs
    Charts
    Blog
    Community
    English v
    Ge
    What is Helm?
    Helm helps you manage Kubernetes applications - Helm Charts help you
    Manage Complexity
    define, install, and upgrade even the most complex Kubernetes application.
    Charts describe even the most complex apps, provide repeatable
    application installation, and serve as a single point of authority.
    Charts are easy to create, version, share, and publish - so start using Helm and stop the
    copy-and-paste.
    Easy Updates
    Helm is a graduated project in the CNCE and is maintained by the Helm community
    Take the pain out of updates with in-place upgrades and custom
    hooks .
    Learn more :
    . Helm Architecture
    Simple Sharing
    Charts are easy to version, share, and host on public or private servers.
    Quick Start Guide
    Video: An Introduction to Helm
    Rollbacks
    Use helm rollback to roll back to an older version of a release with
    ease.

[^3]: helm.sh/docs/intro/quickstart/
    HELM Docs
    Home
    Docs
    Charts
    Blog
    Community
    English v
    Search.. .
    Docs Home
    Quickstart Guide
    Introduction
    Quickstart Guide
    Installing Helm
    Using Helm
    This guide covers how you can quickly get started using Helm.
    Cheat Sheet
    How - To
    Topics
    Prerequisites
    Best Practices
    The following prerequisites are required for a successful and properly secured use of Helm.
    Chart Template
    Guide
    1. A Kubernetes cluster
    I
    Helm Commands
    2. Deciding what security configurations to apply to your installation, if any
    Community
    3. Installing and configuring Helm.
    Frequently Asked
    Questions
    Glossary
    Install Kubernetes or have access to a cluster
    . You must have Kubernetes installed. For the latest release of Helm, we recommend the latest stable release of Kubernetes, which in
    Contribute to Docs
    most cases is the second-latest minor release.

[^4]: C
    helm.sh/docs/intro/install/
    HELM Docs
    Home
    Docs
    Charts
    Blog
    Community
    3. Find the helm binary in the unpacked directory, and move it to its desired destination ( my linux-amd64/helm /usr/local/bin/helm )
    Search. . .
    From there, you should be able to run the client and add the stable repo : helm help .
    Docs Home
    Introduction
    Note: Helm automated tests are performed for Linux AMD64 only during CircleCi builds and releases. Testing of other OSes are
    Quickstart Guide
    the responsibility of the community requesting Helm for the OS in question.
    Installing Helm
    Using Helm
    Cheat Sheet
    From Script
    How - To
    Topics
    Helm now has an installer script that will automatically grab the latest version of Helm and install it locally .
    Best Practices
    You can fetch that script, and then execute it locally. It's well documented so that you can read through it and understand what
    Chart Template
    Guide
    it is doing before you run it.
    Helm Commands
    Community
    curl -fsSL -o get_helm. sh https:/raw.githubusercontent . com/helm/helm/main/scripts/get-helm-3
    $ chmod 700 get_helm. sh
    Frequently Asked
    $ ./get_helm. sh
    Questions
    Glossary

[^5]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ kubectl get nodes
    NAME
    STATUS
    ROLES
    AGE
    VERSION
    ip-192-168-0-225. ec2 . internal
    Ready
    <none>
    35m
    v1.27.9-eks-5eOfdde
    ip-192-168-11-177. ec2. internal
    Ready
    <none>
    35m
    v1 . 27.9-eks-5eOfdde
    ip-192-168-41-2. ec2. internal
    Ready
    <none>
    35m
    v1.27.9-eks-5eOfdde
    54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| null
    \[ centos(ip-172-31-89-51 \~ \]$ curl -fsSL -o get_helm. sh https: //raw. githubusercontent. com/helm/helm/main/scripts/get-helm-3
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2. micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$

[^6]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ chmod 700 get helm. sh
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ ./get helm. sh
    Downloading https://get. helm. sh/helm-v3.14.2-linux-amd64 . tar .gz
    Verifying checksum. .. Done.
    Preparing to install helm into /usr/local/bin
    helm installed into /usr/local/bin/helm

[^7]: 54 . 234 . 195. 42 \| 172. 31 . 89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ helm version
    version . BuildInfo (Version: "v3.14.2", GitCommit: "c309b6fOff63856811846ce18f3bdc93d2b4d54b", GitTreeState: "clean", GoVersion: "gol .21.7"}

[^8]: + - C # helm.sh/docs/topics/charts/
    Charts
    Bearch. . .
    Q
    Helm uses a packaging format called charts. A chart is a collection of files that describe a related set of Kubernetes resources.
    Docs Home
    A single chart might be used to deploy something simple, like a memcached pod, or something complex, like a full web app
    Introduction
    stack with HTTP servers, databases, caches, and so on.
    How - To
    Topics
    Charts are created as files laid out in a particular directory tree. They can be packaged into versioned archives to be deployed.
    Charts
    Chart Hooks
    If you want to download and look at the files for a published chart, without installing it, you can do so with helm pull
    Chart Tests
    Library Charts
    chartrepo/ chartname .
    Helm Provenance And
    Integrity
    This document explains the chart format, and provides basic guidance for building charts with Helm.
    The Chart Repository Guide
    Use OCI-Based Registries
    Helm Architecture
    Advanced Helm Techniques
    Kubernetes Distribution
    The Chart File Structure
    Guide
    Role-Based Access Control
    A chart is organized as a collection of files inside of a directory. The directory name is the name of the chart (without versioning
    The Helm Plugins Guide
    Migrating Helm V2 To V3
    information). Thus, a chart describing WordPress would be stored in a wordpress/ directory.
    Deprecated Kubernetes
    APIs
    Inside of this directory, Helm will expect a structure that matches this:
    Helm Version Support

[^9]: The Chart File Structure
    A chart is organized as a collection of files inside of a directory. The directory name is the name of the chart (without versioning
    information). Thus, a chart describing WordPress would be stored in a wordpress/ directory.
    Inside of this directory, Helm will expect a structure that matches this:
    wordpress/
    Chart. yaal
    # A YAML file containing information about the chart
    LICENSE
    # OPTIONAL: A plain text file containing the license for the chart
    README . md
    # OPTIONAL: A human-readable README file
    values . yaml
    # The default configuration values for this chart
    values . schema. json # OPTIONAL: A JSON Schema for imposing a structure on the values. yaml file
    charts/
    # A directory containing any charts upon which this chart depends.
    crds/
    # Custom Resource Definitions
    templates/
    # A directory of templates that, when combined with values,
    # will generate valid Kubernetes manifest files.
    templates/NOTES. txt # OPTIONAL: A plain text file containing short usage notes

[^10]: The Chart . yam1 File
    The Chart. yanks file is required for a chart. It contains the following fields:
    apiVersion: The chart API version (required)
    name: The name of the chart (required)
    version: A SemVer 2 version (required)
    kubeVersion: A SemVer range of compatible Kubernetes versions (optional)
    description: A single-sentence description of this project (optional)
    type: The type of the chart (optional)
    keywords:
    - A list of keywords about this project (optional)
    home: The URL of this projects home page (optional)
    sources :
    - A list of URLs to source code for this project (optional)
    dependencies: # A List of the chart requirements (optional)

[^11]: EXPLORER
    ! manifest.yaml . \\cart
    ! Chart.yaml X
    Dockerfile roboshop-docker\\user M
    D
    REPOS
    helm-charts > ! Chart.yaml >@appVersion
    > .github
    Helm Chart.yaml - The Chart.yaml file is required for a chart (chart.json)
    > archieve
    apiVersion: v1
    2
    name: nginx
    > catalogue
    3
    version: 0.0.1 # this the chart version
    > catalogue-deploy
    4
    description: this is the customised helm chart for nginx
    > dockerfiles
    5
    appVersion: 1.0.0
    helm-charts \~
    ! Chart.yaml

[^12]: V REPOS
    helm-charts > templates > ! deployment.yaml > {} spec > {} template > {} spec > \[ \] containers > {} 0 > \[ \]
    > .github
    apiVersion: apps/v1
    > archieve
    2
    kind: Deployment
    3
    > catalogue
    metadata:
    14
    name: nginx
    > catalogue-deploy
    5
    labels :
    > dockerfiles
    6
    app: nginx
    helm-charts
    7
    demo: helm
    templates \~
    8
    spec:
    ! deployment.yaml -
    19
    replicas: 3
    ! Chart.yaml
    10
    selector:
    11
    matchLabels :
    > k8-eksctl
    12
    app: nginx
    k8-resources
    13
    demo: helm
    > 01-namespace
    14
    template:
    > 02-pods
    15
    metadata:
    > service
    16
    labels :
    > sets
    17
    app: nginx
    I
    18
    demo: helm
    > storage
    19
    spec :
    > k8-roboshop
    20
    containers :
    > roboshop-ansible-roles
    21
    name: nginx
    > roboshop-ansible-rol..
    22
    image: nginx
    > roboshop-docker
    23
    ports :
    > OUTLINE
    24
    - containerPort: 80

[^13]: REPOS
    helm-charts > templates > ! service.yaml > {} spec > @type
    helm-charts
    1
    apiVersion: v1
    templates
    2
    kind: Service
    ! deployment.yaml
    3
    metadata:
    ! service.yaml -
    14
    name: nginx
    5
    ! Chart.yaml
    spec :
    16
    type: LoadBalancer
    > k8-eksctl
    7
    selector :
    k8-resources
    18
    app: nginx
    > 01-namespace
    19
    demo: helm
    > 02-pods
    10
    ports :
    V
    service
    11
    protocol: TCP
    ! 01-cluster-ip.yaml
    12
    port: 80 #service-port
    13
    targetPort: 80 #container-port
    ! 02-node-port.yaml
    ! 03-load-balancer.yaml

[^14]: helm.sh/docs/intro/cheatsheet/
    HELM Docs
    Home
    Docs
    Charts
    Blog
    Community
    English v
    Chart Management
    Search. . .
    Docs Home
    helm create <name>
    # Creates a chart directory along with the common files and directories used in a chart.
    Introduction
    helm package <chart-path>
    # Packages a chart into a versioned chart archive file.
    helm lint <chart>
    # Run tests to examine a chart and identify possible issues:
    Quickstart Guide
    helm show all <chart>
    # Inspect a chart and list its contents:
    Installing Helm
    helm show values <chart>
    # Displays the contents of the values. yaml file
    Using Helm
    helm pull <chart>
    # Download/pull chart
    Cheat Sheet
    helm pull <chart> --untar=true
    # If set to true, will untar the chart after downloading it
    helm pull <chart> --verify
    # Verify the package before using it
    How - To
    helm pull <chart> --version <number>
    # Default-latest is used, specify a version constraint for the chart version to use
    helm dependency list <chart>
    # Display a list of a chart's dependencies:
    Topics
    Best Practices
    Chart Template
    Guide
    Helm Commands
    Install and Uninstall Apps
    Community
    Frequently Asked
    helm install <name> <chart>
    # Install the chart with a name
    Questions
    helm Install <name> <chart> --namespace <namespace>
    # Install the chart in a specific namespace
    Glossary
    helm install <name> <chart> --set keyl=vall, key2=va12 # Set values on the command Line (can specify multiple or separate values with commas)
    helm install <name> <chart> --values <yaml-file/url> # Install the chart with your specified values
    helm install <name> <chart> --dry-run --debug
    # Run a test installation to validate chart (p)
    helm install <name> <chart> --verify
    # Verify the package before using it
    helm install <name> <chart> --dependency-update
    # update dependencies if they are missing before installing the chart
    helm uninstall <name>
    # Uninstall a release
    Contribute to Docs

[^15]: C github.com/new
    E
    New repository
    Q Type to search
    +
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere?
    Import a repository.
    Required fields are marked with an asterisk (").
    Owner \*
    Repository name \*
    daws-76s
    helm-charts
    helm-charts is available.
    Great repository names are short and memorable. Need inspiration? How about expert-enigma ?
    Description (optional)
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    O
    Private
    You choose who can see and commit to this repository.

[^16]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-eksct1 (main)
    $ cd . ./helm-charts/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/helm-charts
    $ git init
    Initialized empty Git repository in C: /devops/daws-76s/repos/helm-charts/.git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/helm-charts (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/helm-charts (main)
    $ git remote add origin git@github. com: daws-76s/helm-charts . git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/helm-charts (main)
    S

[^17]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/helm-charts (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main (root-commit) 24bac05\] jenkins
    3 files changed, 42 insertions (+)
    create mode 100644 Chart. yam1

[^18]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ git clone https: //github. com/daws-76s/helm-charts. git
    Cloning into 'helm-charts' ..
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6), done.
    remote: Compressing objects: 100% (6/6), done.
    remote: Total 6 (delta 0) , reused 6 (delta 0) , pack-reused 0
    1008
    (6 / 6)

[^19]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ 1s
    Chart . yaml templates
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2. micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm install nginx .
    NAME: nginx
    LAST DEPLOYED: Thu Feb 29 02:07:21 2024
    NAMESPACE: default
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^20]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https://github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm list
    NAME
    NAME SPACE
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    nginx
    default
    2024-02-29 02:07:21. 680353391 +0000 UTC deployed
    nginx-0 .0.1
    1.0.0

[^21]: EXPLORER
    ! values.yaml U X
    Dockerfile roboshop-docker\\user M
    Dock
    V REPOS
    helm-charts > ! values.yaml > {} deployment
    > .github
    1 deployment :
    > archieve
    2
    replicas: 3
    3
    > catalogue
    imageVersion: mainline-alpine3. 18-per1
    > catalogue-deploy
    > dockerfiles
    helm-charts
    > templates
    ! Chart.yaml
    ! values.yam/ -
    U

[^22]: EXPLORER
    ! Chart.yaml X
    ! values.yaml
    Dockerfile roboshop-docker\\user M
    D
    REPOS
    helm-charts > ! Chart.yaml > @ version
    .github
    Helm Chart.yaml - The Chart.yaml file is required for a chart (chart.json)
    1
    > archieve
    apiVersion: v1
    2
    name: nginx
    > catalogue
    3
    -version: 0.0.2 # this the chart version
    > catalogue-deploy
    4
    description: this is the customised helm chart for nginx
    > dockerfiles
    5
    appVersion: 1.0.0
    helm-charts
    > templates
    ! Chart.yaml

[^23]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/helm-charts (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main 3fbbage\] jenkins
    2 files changed, 5 insertions (+) , 2 deletions(-)

[^24]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm upgrade nginx
    Release "nginx" has been upgraded. Happy Helming!
    NAME: nginx
    LAST DEPLOYED: Thu Feb 29 02:12:51 2024
    NAMESPACE: default
    STATUS: deployed
    REVISION: 2
    TEST SUITE: None

[^25]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts .git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-67f7bf8874-52ndj
    0/1
    ContainerCreating
    1s
    nginx-67f7bf8874-f5zqw
    1/1
    Running
    4s
    OoOO
    nginx-67f7bf8874-t6wpl
    1/1
    Running
    7s
    nginx-c4f66fc45-6nk8q
    1/1
    Running
    5m36s
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-67f7bf8874-52ndj
    1/1
    Running
    12s
    nginx-67f7bf8874-f5zqw
    1/1
    Running
    15s
    nginx-67f7bf8874-t6wpl
    1/1
    Running
    18s

[^26]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm list
    NAME
    NAMESPACE
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    nginx
    default
    2
    2024-02-29 02:12: 51 . 396645743 +0000 UTC deployed
    nginx-0 . 0.2
    1.0.1
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2. micro \| https: //github. com/daws-76s/helm-charts .git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm history nginx
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    DESCRIPTION
    Thu Feb 29 02:07:21 2024
    superseded
    nginx-0 .0.1
    1.0.0
    Install complete
    Thu Feb 29 02:12:51 2024
    deployed
    nginx-0.0.2
    1.0.1
    Upgrade complete

[^27]: 54 . 234 . 195. 42 \| 172 . 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm rollback nginx
    Rollback was a success! Happy Helming!
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-c4f66fc45-dcmlb
    1/1
    Running
    0
    nginx-c4f66fc45-jf5p8
    1/1
    Running
    O
    3s
    nginx-c4f66fc45-msmdr
    1/1
    Running
    0
    5s

[^28]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm history nginx
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    DESCRIPTION
    Thu Feb 29 02:07:21 2024
    superseded
    nginx-0 .0.1
    1.0.0
    Install complete
    Thu Feb 29 02:12:51 2024
    superseded
    nginx-0 . 0.2
    1.0.1
    Upgrade complete
    Thu Feb 29 02:26:19 2024
    deployed
    nginx-0 . 0.1
    1.0.0
    Rollback to

[^29]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm history nginx
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    DESCRIPTION
    Thu Feb 29 02:07:21 2024
    superseded
    nginx-0 . 0.1
    1.0.0
    Install complete
    Thu Feb 29 02:12:51 2024
    superseded
    nginx-0 . 0.2
    1.0.1
    Upgrade complete
    w
    Thu Feb 29 02:26:19 2024
    deployed
    nginx-0 . 0.1
    1.0.0
    Rollback to 1
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm rollback nginx 2
    Rollback was a success! Happy Helming!
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-67f7bf8874-1k52x
    1/1
    Running
    2s
    nginx-67f7bf8874-tt68h
    1/1
    Running
    3s
    nginx-67f7bf8874-zngcw
    0/1
    ContainerCreating
    1s
    nginx-c4f66fc45-domlb
    0/1
    Terminating
    49s
    nginx-c4f66fc45-jf5p8
    1/1
    Running
    48s
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-67f7bf8874-1k52x
    1/1
    Running
    0
    7s
    nginx-67f7bf8874-tt68h
    1/1
    Running
    0
    8s
    nginx-67f7bf8874-zngcw
    1/1
    Running
    0
    6s

[^30]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2. micro \| https: / /github. com/daws-76s/helm-charts .git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm show values .
    deployment:
    replicas : 3
    imageVersion: mainline-alpine3. 18-perl

[^31]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm upgrade nginx --set deployment. replicas=10
    Release "nginx" has been upgraded. Happy Helming!
    NAME: nginx
    LAST DEPLOYED: Thu Feb 29 02:30:12 2024
    NAMESPACE: default
    STATUS: deployed
    REVISION: 6
    TEST SUITE: None

[^32]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts .git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-67f7bf8874-2ftxr
    1/1
    Running
    5s
    nginx-67f7bf8874-b8n95
    1/1
    Running
    5s
    nginx-67f7bf8874-g7ncx
    1/1
    Running
    O
    5s
    nginx-67f7bf8874-kd7p4
    1/1
    Running
    5s
    nginx-67f7bf8874-1k52x
    1/1
    Running
    3m10s
    nginx-67f7bf8874-mp47q
    1/1
    Running
    5s
    nginx-67f7bf8874-pdjjv
    1/1
    Running
    5s
    nginx-67f7bf8874-tt68h
    1/1
    Running
    3m11s
    nginx-67f7bf8874-zngcw
    1/1
    Running
    3m9s
    nginx-67f7bf8874-zpd7w
    1/1
    Running
    5s

[^33]: yum install nginx -y
    yum is getting the package from internet and installing it in VM. ..
    1. image is already in public
    2. helm have some public repos to configure the image through manifest files...

[^34]: EBS drivers
    1. add helm repo --> kubernetes resource files
    helm repo add aws-ebs-csi-driver https : / /kubernetes-sigs. github . io/aws-ebs-csi-driver
    2. helm repo update
    3. helm upgrade --install aws-ebs-csi-driver --namespace kube-system aws-ebs-csi-driver/aws-ebs
    helm install nginx

[^35]: 54 . 234 . 195 . 42 \| 172. 31. 89.51 \| t2.micro
    \| https://github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts
    \]$ helm repo add aws-ebs-csi-driver https: //kubernetes-sigs . github. io/aws-ebs-csi-driver
    'aws-ebs-csi-driver" has been added to your repositories

[^36]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github.com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm repo list
    NAME
    URL
    aws-ebs-csi-driver
    https: //kubernetes-sigs . github . io/aws-ebs-csi-driver

[^37]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm repo update
    Hang tight while we grab the latest from your chart repositories...
    . . Successfully got an update from the "aws-ebs-csi-driver" chart repository
    Update Complete. Happy Helming!

[^38]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts .git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm upgrade --install aws-ebs-csi-driver --namespace kube-system aws-ebs-csi-driver/aws-ebs
    csi-driver
    Release "aws-ebs-csi-driver" does not exist. Installing it now.
    NAME: aws-ebs-csi-driver
    LAST DEPLOYED: Thu Feb 29 02:21: 40 2024
    NAMESPACE: kube-system
    STATUS: deployed
    REVISION: 1
    NOTES :
    To verify that aws-ebs-csi-driver has started, run:
    kubectl get pod -n kube-system -1 "app. kubernetes . io/name=aws-ebs-csi-driver, app. kubernetes . io/instance=aws-ebs-csi-driver"
    NOTE: The \[CSI Snapshotter\] (https: / /github. com/kubernetes-csi/external-snapshotter) controller and CRDs will no longer be installed as
    part of this chart and moving forward will be a prerequisite of using the snap shotting functionality.
    WARNING: Upgrading the EBS CSI Driver Helm chart with --reuse-values will no longer be supported in a future release. For more informat
    ion, see https: //github. com/kubernetes-sigs/aws-ebs-csi-driver/issues/1864

[^39]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm list
    NAME
    NAMESPACE
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    nginx
    default
    2024-02-29 02:12: 51 . 396645743 +0000 UTC deployed
    nginx-0 . 0.2
    1.0.1
    54. 234. 195. 42 \| 172. 31.89.51 \| t2. micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm list -n kube-system
    NAME
    NAME SPACE
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    aws-ebs-csi-driver
    kube-system
    2024-02-29 02:21 : 40 . 394267222 +0000 UTC deployed
    aws-ebs-csi-driver-2 . 2
    . 1
    1 . 28.0

[^40]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts .git
    \[ centos(ip-172-31-89-51 \~/helm-charts \]$ helm uninstall aws-ebs-csi-driver -n kube-system
    release "aws-ebs-csi-driver" uninstalled

[^41]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm list -n kube-system
    NAME
    NAMESPACE
    REVISION
    UPDATED STATUS
    CHART
    APP VERSION

[^42]: F
    > C \* artifacthub.io/packages/search?ts_query_web=nginx&sort=relevance&page=1
    ?
    O Artifact HUB
    Q nginx
    X
    DOCS STATS SIGN UP
    SIGN IN
    1 - 20 of 207 results for 'nginx"
    Sort:
    Relevance
    Show: 20
    FILTERS
    \* 77 Helm chart
    \* 2 X Falco rules
    nginx
    NGINX
    Nginx
    in Bitnami @ Bitnami
    Updated 7 days ago
    In Falco @ Security Hub
    Updated 3 years ago
    Official
    Version 15.12.2
    Version 1.0.0
    verified publishers
    NGINX Open Source is a web server that can be also used as a reverse proxy, load balancer, and HTTP cache. Rec...
    Falco rules for securing Nginx
    CNCF
    A Networking
    KIND
    \[Containers images (3)
    Falco rules (2)
    \* 1 5 Helm chart
    \* 1 # Helm chart
    Helm charts (187)
    nginx
    nginx
    Updated 3 years ago
    Updated a year ago
    KCL modules (s)
    It Mirantis @ Mirantis Public Helm Charts
    joaquinito2051 @ Bitnami for Azure Kubernetes Service
    Version 0.1.0
    Version 13.2.12
    Krew kubectl plugins (2)
    A NGINX Docker Community based Helm chart for Kubernetes
    NGINX Open Source is a web server that can be also used as a reverse proxy, load balancer, and HTTP cache. Rec..
    KubeArmor policies (1)
    Kyverno policies (5)
    Networking
    Networking
    OLM operators (2)

[^43]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/helm-charts.git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm uninstall nginx
    release "nginx" uninstalled

[^44]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ kubectl get pods
    No resources found in default namespace.

[^45]: statefulset --> used to create stateful applications in kubernetes
    deployment --> used to create stateless applications in kubernetes

[^46]: Using StatefulSets
    StatefulSets are valuable for applications that require one or more of the following.
    Stable, unique network identifiers.
    Stable, persistent storage.
    Ordered, graceful deployment and scaling.
    .
    Ordered, automated rolling updates.

[^47]: nodes inside stateful applications should have static hostnames to communicate with other
    nodes
    stateful applications should follow orderly provisioning as well as terminaetel
    statefulset applications will have headless service..

[^48]: createUser
    user created
    NODE-1
    master
    NODE-2
    NODE-3

[^49]: StatefulSet
    Deployment
    Used to deploy stateful applications
    Used to deploy stateless applications
    Pods created by StatefulSets have unique
    Pods created by Deployment have
    names which remain constant across
    dynamic, random names and numbers
    application rescheduling.
    that change across application
    rescheduling.
    Its Pods are created in sequential order
    Its Pods are created and deleted
    and deleted in reverse, sequential order.
    randomly.
    Its Pods are not interchangeable and
    Its Pods are interchangeable and do not
    maintain their identities after restarts.
    maintain their identities after restarts.
    It does not allow shared volume. Thus,
    It allows shared volume via Volume and
    each Pod replica has its own sticky
    PersistentVolumeClaim across all of the
    Volume and PersistentVolumeClaim.
    Pod replicas.
    plication is complex
    Replication is easier

[^50]: Deployment vs. StatefulSet vs. DaemonSet
    Deployment
    StatefulSet
    DaemonSet
    pod-c3
    pod-a9
    pod-a7d
    pod.RSC
    pod-O
    pod-1
    pod-ju
    pod-1d

[^51]: 1. install drivers
    2. provide IAM role access to ec2
    3. install storage class

[^52]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ helm upgrade --install aws-ebs-csi-driver --namespace kube-system aws-ebs-csi-driver/aws-ebs
    csi-driver
    Release "aws-ebs-csi-driver" does not exist. Installing it now.
    NAME: aws-ebs-csi-driver
    LAST DEPLOYED: Thu Feb 29 02:44:11 2024
    NAMESPACE: kube-system
    STATUS: deployed
    REVISION: 1
    NOTES :
    To verify that aws-ebs-csi-driver has started, run:
    kubectl get pod -n kube-system -1 "app. kubernetes . io/name=aws-ebs-csi-driver, app . kubernetes . io/instance=aws-ebs-csi-driver"
    NOTE: The \[CSI Snapshotter\] (https: //github. com/kubernetes-csi/external-snapshotter) controller and CRDs will no longer be installed as
    part of this chart and moving forward will be a prerequisite of using the snap shotting functionality.
    WARNING: Upgrading the EBS CSI Driver Helm chart with --reuse-values will no longer be supported in a future release. For more informat
    ion, see https: //github. com/kubernetes-sigs/aws-ebs-csi-driver/issues/1864

[^53]: Instances (1/4) Info
    G
    Connect
    Instance state
    Actions
    V
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    <
    1 >
    -
    Name _
    A
    Instance ID
    Instance state
    Instance type
    4
    Status check
    Alarm status
    Availability Z
    workstation-eksctl
    i-Obed9036a58f89c3
    Running Q Q
    t2.micro
    2/2 checks passed View alarms +
    us-east-1a
    roboshop-spot-Node
    i-Oca69801e0673f691
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1c
    roboshop-spot-Node
    i-Oca48ae895f3343a0
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    US-east-1f
    roboshop-spot-Node
    i-035877dd7ba026160
    Running Q Q
    m5.large
    2/2 checks passed View alarms +
    us-east-1f
    Instance: i-035877dd7ba026160 (roboshop-spot-Node)
    X
    Details
    Status and alarms New Monitoring Security
    Networking
    Storage
    Tags
    Instance summary Info
    Instance ID
    Public IPv4 address
    Private IPv4 addresses
    i-035877dd7ba026160 (roboshop-spot-Node)
    5 44.192.38.11 \|open address \[
    192.168.11.177
    192.168.4.221
    IPv6 address
    Instance state
    Public IPV4 DNS
    Running
    ec2-44-192-38-11.compute-1.amazonaws.com \|open
    address \[

[^54]: IAM > Roles > eksctl-roboshop-nodegroup-spot-NodeInstanceRole-ZEDOoGt08ErE > Add permissions
    Attach policy to eksctl-roboshop-nodegroup-spot-NodeInstanceRole-ZEDOoGt08ErE
    Current permissions policies (4)
    Other permissions policies (1/909)
    C
    Filter by Type
    Q ebs
    X
    All types
    2 matches
    <
    1
    Policy name
    Type
    Description
    AmazonEBSCSIDriverPolicy
    AWS managed
    IAM Policy that allows the CSI driver serv...
    + ROSAAmazonEBSCSIDriverOperatorPolicy
    AWS managed
    Allows the OpenShift Amazon EBS Cont...
    Cancel
    Add permissions

[^55]: 54. 234. 195.42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/helm-charts . git
    \[ centos@ip-172-31-89-51 \~/helm-charts \]$ cd
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2. micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ git clone https: //github. com/daws-76s/k8-resources . git
    Cloning into 'k8-resources' .
    remote: Enumeratiog objects: 149, done.
    remote: Counting objects: 100% (149/149) , done.
    remote: Compressing objects: 100% (104/104) , done.
    remote: Total 149 (delta 65) , reused 118 (delta 34) , pack-reused 0
    Receiving objects: 100% (149/149) , 14.94 KiB \| 3.73 MiB/s, done.
    Resolving deltas: 100% (65/65) , done.
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ cd k8-resources/
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources \]$ cd storage/
    54 . 234. 195.42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/storage \]$ cat ebs-sc. yaml
    apiVersion: storage . k8s . io/v1
    kind: StorageClass
    metadata :
    name: ebs-sc
    provisioner: ebs . csi . aws . com
    volumeBindingMode: WaitForFirstConsumer

[^56]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-51 \~/k8-resources/storage \]$ kubectl apply -f ebs-sc. yaml
    storageclass . storage . k8s . io/ebs-sc created
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/storage \]$ kubectl get sc
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
    5s
    gp2 (default)
    kubernetes . io/aws-ebs
    Delete
    WaitForFirstConsumer
    false
    93m

[^57]: EXPLORER
    ! 03-statefulset.yaml U X ! deploymerrywww
    ! service.yaml
    Dockerfile roboshop-docker\\mongodb
    REPOS
    k8-resources > sets > ! 03-statefulset.yaml > {} spec > { } selector > {} matchLabels
    > helm-charts
    apiVersion: apps/v1
    kind: StatefulSet
    > k8-eksctl
    3
    metadata:
    k8-resources
    4
    name: web
    > 01-namespace
    5
    spec :
    > 02-pods
    6
    selector:
    > service
    7
    matchLabels :
    8
    V sets
    app: nginx # has to match . spec . template . metadata . labels
    9
    serviceName: "nginx"
    ! 01-replica-set.yaml
    10
    replicas: 3 # by default is 1
    ! 02-deployment-set.yaml
    11
    minReadySeconds: 10 # by default is 0
    ! 03-statefulset.yaml -U
    12
    template:
    > storage
    13
    metadata:
    k8-roboshop
    14
    labels :
    > roboshop-ansible-roles
    15
    app: nginx # has to match . spec. selector . matchLabels
    16
    spec :
    > roboshop-ansible-rol.
    17
    terminationGracePeriodSeconds : 10
    > roboshop-docker
    18
    containers :
    > roboshop-infra-dev
    19
    name: nginx
    > roboshop-infra-prod
    20
    image: registry . k8s . io/nginx-slim:0.8
    > roboshop-shared-libr... .
    21
    ports :
    > roboshop-terraform
    22
    containerPort : 80
    23
    > terraform-aws-security-aro
    name: web
    OUTLINE
    24
    volumeMounts :

[^58]: 54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: //github.com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/storage \]$ git pull
    remote: Enumeratiog objects: 6, done.
    remote: Counting objects: 100% (6/6) , done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 100% (4/4) , 801 bytes \| 801.00 KiB/s, done.
    htt
    Waithub
    -76s/K8

[^59]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/storage \]$ cd . ./sets/
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl apply -f 03-statefulset . yaml
    statefulset . apps/web created
    service/nginx created

[^60]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pv
    NAME
    CAPACITY
    ACCESS MODES
    RECLAIM POLICY
    STATUS
    CLAIM
    STORAGECLASS
    REA
    N
    AGE
    pvc-862bb960-d73e-464b-a09a-d06e9d4006c5
    1Gi
    RWO
    Delete
    Bound
    default/www-web-0
    ebs-sc
    2s
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    web-0
    1/1
    Running
    0
    12s
    54. 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    web-0
    1/1
    Running
    0
    15s

[^61]: 54 . 234 . 195.42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-51 \~/8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    web-0
    1/1
    Running
    24s
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    web--0
    1/1
    Running
    31s
    web-1
    0/1
    Pending
    Os

[^62]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github.com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    web-0
    1/1
    Running
    0
    64s
    web-1
    1/1
    Running
    33s
    web-2
    0/1
    Pending
    3s

[^63]: Volumes (7) Info
    G
    Actions
    Create volume
    Q Search
    <
    O
    Name
    Volume ID
    V
    Type
    4
    Size
    V
    IOPS
    V
    Throughput
    Snapshot
    V
    Created
    O
    vol-0493abf87db44ecb4
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:18 GMT+5:...
    vol-Od8c35c0a4c402d58
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:18 GMT +5:...
    vol-07aad8d7ea7b31ba2
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:19 GMT +5:...

[^64]: Why Stateful Applications in K8s
    need a headless service
    Chamsedine Mansouri . Follow
    3 min read . May 8, 2020
    50
    Q
    ...
    Through out the years, Kubernetes had the reputation of being most suited
    for stateless applications, and that is wrong. The open-source project
    focused heavily in its recent versions on running stateful apps with ease on
    the orchestration platform. By stateful applications, we mean
    (micro-)services that save data into a persistent storage, for use by clients,
    servers or other services. For instance, a Mysql host in KSs or a more cloud
    native apps like Cassandra and MongoDB with master and slaves and hard-
    logic stuff.

[^65]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ cd . ./sets/
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ 1s
    01-replica-set . yaml 02-deployment-set . yam1 03-statefulset. yaml
    54 . 234 . 195.42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl apply -f 02-deployment-set. yaml
    deployment . apps/nginx-deployment created

[^66]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    4s
    nginx-deployment-86d976d8bd-75gbh
    1/1
    Running
    4s
    nginx-deployment-86d976d8bd-t99g1
    1/1
    Running
    4s
    Oooooo
    web-0
    1/1
    Running
    2m44s
    web-1
    1/1
    Running
    2m13s
    web-2
    1/1
    Running
    103s

[^67]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get svc
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
    99m
    nginx
    ClusterIP
    Norle
    <none>
    80/TCP
    3m35s
    nginx-service
    ClusterIP
    10 . 100.233.29
    <none>
    80/TCP
    3s

[^68]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl apply -f . ./02-pods/03-labels. yaml
    pod/label-demo created
    54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    label-demo
    1/1
    Running
    0
    4s
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    112s
    nginx-deployment-86d976d8bd-75gbh
    1/1
    Running
    112s
    nginx-deployment-86d976d8bd-t99gl
    1/1
    Running
    112s
    web-0
    1/1
    Running
    4m32s
    web-1
    1/1
    Running
    4m1s
    web-2
    1/1
    Running
    3m31s

[^69]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl exec -it label-demo -- bash
    root@label-demo : /# nslookup
    bash: nslookup: command not found
    root@label-demo : /# apt update
    Get: 1 http://deb. debian. org/debian bookworm InRelease \[151 kB\]
    Get:2 http://deb. debian. org/debian bookworm-updates InRelease \[55.4 kB\]
    Get: 3 http://deb . debian. org/debian-security bookworm-security InRelease \[48.0 kB\]
    Get: 4 http://deb . debian. org/debian bookworm/main amd64 Packages \[8786 kB\]

[^70]: root@label-demo: /# apt install install bind9-utils
    Reading package lists. .. Done
    Building dependency tree. . . Done
    Reading state information. .. Done
    E: Unable to locate package install
    rootdlabel-demo : /# clea

[^71]: root@label-demo: /# apt install dnsutils
    Reading package lists. . . Done
    Building dependency tree. . . Done
    Reading state information. .. Done
    The following additional packages will be installed:
    bind9-dnsutils bind9-host bind9-libs libfstrm0 libjemalloc2 libjson-c5 li
    Suggested packages :
    mmdb-bin
    The following NEW packages will be installed:
    bind9-dnsutils bind9-host bind9-libs dnsutils libfstrm0 libjemalloc2 libj
    0 upgraded, 11 newly installed, 0 to remove and 0 not upgraded.
    Need to get 2964 kB of archives.

[^72]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get svc
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
    101m
    nginx
    ClusterIP
    None
    <none>
    80/TCP
    6m8s
    nginx-service
    ClusterIP
    10. 100.233.29
    <none>
    80/TCP
    2m36s
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl exec -it label-demo -- bash
    root@label-demo : /# nslookup nginx-service
    Server :
    10 . 100 . 0 . 10
    Address :
    10 . 100 . 0. 10#53
    Name :
    nginx-service . default. svc . cluster . local
    Address: 10. 100.233.29

[^73]: root@label-demo : /# nslookup nginx
    Server:
    10 . 100 .0 . 10
    Address :
    10 . 100 .0. 10#53
    Name :
    nginx . default . svc . cluster . local
    Address: 192 . 168 . 9.84
    Name :
    nginx . default. svc. cluster . local
    Address: 192 . 168 . 15. 75
    Name :
    nginx . default . svc. cluster . local
    Address: 192 . 168 . 41 . 103
    Name :
    nginx . default. svc. cluster . local
    Address: 192 . 168 . 46.200
    Name:
    nginx . default . svc . cluster . local
    Address: 192 . 168 . 3. 125
    Name :
    nginx . default . svc . cluster . local
    Address: 192 . 168 . 6.106

[^74]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods -o wide
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    IP
    NODE
    NOMINATED
    DE
    READINESS GATES
    label-demo
    1/1
    Running
    0
    2m38s
    192 . 168 .21.247
    ip-192-168-11-177. ec2 . internal
    <none>
    <none>
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    0
    4m26s
    192 . 168 . 3.125
    ip-192-168-11-177. ec2. internal
    <none>
    <none>
    nginx-deployment-86d976d8bd-75gbh
    1/1
    Running
    0
    4m26s
    192 . 168 .6.106
    ip-192-168-0-225. ec2 . internal
    <none>
    <none>
    nginx-deployment-86d976d8bd-t99g1
    1/1
    Running
    0
    4m26s
    192 . 168 . 41 . 103
    ip-192-168-41-2. ec2 . internal
    <none>
    <none>
    web-0
    1/1
    Running
    0
    7m6s
    192 . 168 . 15.75
    ip-192-168-11-177. ec2 . internal
    <none>
    <none>
    web-1
    1/1
    Running
    0
    6m35s
    192 . 168 . 46.200
    ip-192-168-41-2. ec2 . internal
    <none>
    <none>
    web-2
    1/1
    Running
    0
    6m5s
    192 . 168 .9.84
    ip-192-168-0-225. ec2. internal
    <none>
    <none>

[^75]: createUser
    user created
    NODE-1
    master
    NODE-2
    NODE-3
    My SQL

[^76]: 54 . 234 . 195. 42 \| 172. 31.89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl delete -f 03-statefulset. yaml
    statefulset. apps "web" deleted
    service "nginx" deleted

[^77]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ watch kubectl get pods

[^78]: 54 . 234. 195.42 \| 172. 31. 89.51 \| t2. micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pv
    NAME
    CAPACITY
    ACCESS MODES
    RECLAIM POLICY
    STATUS
    CLAIM
    STORAGECLASS
    R
    AGE
    pvc-862bb960-d73e-464b-a09a-d06e9d4006c5
    1Gi
    RWO
    Delete
    Bound
    default/www-web-0
    ebs-sc
    11m
    pvc-9230c87a-689a-449c-a26b-1038c69a1332
    1Gi
    RWO
    Delete
    Bound
    default/www-web-1
    ebs-sc
    11m
    pvc-cea871d0-b9a9-4310-bf3c-ad61laa729c0
    1Gi
    RWO
    Delete
    Bound
    default/www-web-2
    ebs-sc
    10m
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pvc
    NAME
    STATUS
    VOLUME
    CAPACITY
    ACCESS MODES
    STORAGECLASS
    AGE
    www-web-0
    Bound
    pvc-862bb960-d73e-464b-a09a-d06e9d4006c5
    1Gi
    RWO
    ebs-sc
    1 1m
    www-web-1
    Bound
    pvc-9230c87a-689a-449c-a26b-1038c69a1332
    1Gi
    RWO
    ebs-sc
    11m
    www-web-2
    Bound
    pvc-cea871d0-b9a9-4310-bf3c-ad61laa729c0
    1Gi
    RWO
    ebs-sc
    10m

[^79]: Volumes (7) Info
    C
    Actions
    Create volume
    Q Search
    < 1 >
    v Type
    Size
    Sdol 4
    A
    Throughput \| Snapshot
    Created
    V
    Availability Zone
    Volume state
    Ala
    lecb4
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:18 GMT+5:...
    us-east-1c
    Available
    No
    2d58
    9p3
    1 GIB
    3000
    125
    2024/02/29 08:18 GMT +5:...
    us-east-1f
    Available
    No
    $1ba2
    gp3
    1 GiB
    3000
    125
    2024/02/29 08:19 GMT+5:...
    us-east-1f
    Available
    No

[^80]: 54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github.com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl apply -f 03-statefulset. yaml
    statefulset . apps/web created
    service/nginx created
    54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    label-demo
    1/1
    Running
    7m56s
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    9m44s
    nginx-deployment-86d976d8bd-75gbh
    1/1
    Running
    9m 44s
    nginx-deployment-86d976d8bd-t99gl
    1/1
    Running
    9m44s
    web-0
    0/1
    ContainerCreating
    11s

[^81]: Volumes (1/7) Info
    C
    Actions
    Create volume
    Q Search
    < 1 >
    -
    Name
    Volume ID
    Type V Size
    IOPS
    Throughput \|Snapshot
    Created
    vol-0493abf87db44ecb4
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:18 GMT +5:...
    V
    vol-Od8c35c0a4c402d58
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:18 GMT+5:...
    0
    vol-07aad8d7ea7b31ba2
    gp3
    1 GiB
    3000
    125
    2024/02/29 08:19 GMT+5:...
    roboshop-spot...
    vol-08bbc3ba2842a80be
    9p3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT +5:...
    roboshop-spot...
    vol-017f5693b2ae74a94
    gp3
    80 GIB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT +5:...
    roboshop-spot...
    vol-Oc5508135c55de05d
    gp3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT +5:...
    =
    Volume ID: vol-0d8c35c0a4c402d58
    X
    Tags
    Manage tags
    Q Filter tags
    <
    1 >
    Key
    Value
    CSIVolumeName
    pvc-862bb960-d73e-464b-a09a-d06e9d4006c5
    ebs.csi.aws.com/cluster
    wfue
    kubernetes.io/created-fo...
    www-web-o
    kubernetes.io/created-fo...
    default
    kubernetes.io/created-fo...
    pvc-862bb960-d73e-464b-a09a-d06e9d4006c5

[^82]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl delete -f 03-statefulset. yaml
    statefulset . apps "web" deleted
    service "nginx" deleted
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl get pvc
    NAME
    STATUS
    VOLUME
    CAPACITY
    ACCESS MODES
    STORAGECLASS
    AGE
    www-web-0
    Bound
    pvc-862bb960-d73e-464b-a09a-d06e9d4006c5
    1Gi
    RWO
    ebs-sc
    13m
    www-web-1
    Bound
    pvc-9230c87a-689a-449c-a26b-1038c69a1332
    1Gi
    RWO
    ebs-sc
    13m
    www-web-2
    Bound
    pvc-cea871d0-b9a9-4310-bf3c-ad61laa729c0
    1Gi
    RWO
    ebs-sc
    12m
    54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ kubectl delete pvc www-web-0 www-web-1 www-web-2
    persistentvolumeclaim "www-web-0" deleted
    persistentvolumeclaim "www-web-1" deleted
    persistentvolumeclaim "www-web-2" deleted

[^83]: Volumes (4) Info
    C
    Actions
    Create volume
    A
    Q Search
    < 1 >
    Name
    Volume ID
    Type
    Size
    V IOPS
    Throughput \| Snapshot
    Created
    O
    roboshop-spot...
    vol-08bbc3ba2842a80be
    gp3
    80 GIB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT+5:...
    roboshop-spot...
    vol-017f5693b2ae74a94
    gp3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT+5:...
    O
    roboshop-spot...
    vol-0c5508135c55de05d
    9p3
    80 GIB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT +5:...
    workstation-e...
    vol-00b8c59bbeb3da50f
    9p2
    10 GIB
    100
    snap-Od6f961...
    2024/02/29 06:31 GMT +5:...

[^84]: REPOS
    k8-databases > mongodb > ! Chart.yaml > @ description
    > .github
    Helm Chart.yaml - The Chart.yaml file is required for a chart (chart.json)
    > archieve
    1
    apiVersion: v1
    2
    name: mongodb
    > catalogue
    3
    version: 0.0.2 # this the chart version
    > catalogue-deploy
    4
    description: this is the customised helm chart for mongodb
    > dockerfiles
    5
    appVersion: v1
    > helm-charts
    k8-databases \\ mongodb -
    templates -
    ! Chart.yaml -
    ! values.yaml

[^85]: REPOS
    k8-databases > mongodb > templates > ! statefulset.yaml > { } spec > { } template > { } spec > \[ \]containers > { } 0 > .)image
    > catalogue-deploy
    12
    app: mongodb
    > dockerfiles
    13
    project: roboshop
    14
    tier: db
    > helm-charts
    15
    serviceName: "nginx"
    k8-databases \\ mongodb
    16
    replicas: 1 # by default is 1
    templates
    17
    template:
    ! service.yaml
    18
    metadata:
    ! statefulset.yaml -
    19
    labels :
    ! Chart.yaml
    20
    app: mongodb
    21
    ! values.yaml
    project: roboshop
    22
    tier: db
    > k8-eksctl
    23
    spec :
    > k8-resources
    24
    containers :
    > k8-roboshop
    25
    - name: mongodb
    > roboshop-ansible-roles
    26
    image: "joindevops/mongodb: {{ . Values . statefulset. imageVersion }}"\|I
    > roboshop-ansible-rol..
    27
    ports :
    28
    > roboshop-docker
    containerPort: 80
    29
    name : web
    > roboshop-infra-dev
    30
    volumeMounts :
    > roboshop-infra-prod
    31
    name : www
    > roboshop-shared-libr.
    32
    mountPath: /usr/share/nginx/html
    > roboshop-terraform
    33
    volumeClaimTemplates :
    ) torraform.awe-coruritu-arn
    34
    metadata:
    OUTLINE

[^86]: V REPOS
    k8-databases > mongodb > ! values.yaml > {} stat
    > .github
    statefulset: I
    > archieve
    2
    replicas: 2
    3
    imageVersion: v1
    > catalogue
    > catalogue-deploy
    > dockerfiles
    > helm-charts
    k8-databases \\ mong...
    templates
    ! service.yaml
    ! statefulset.yaml
    ! Chart.yaml
    ! values.yaml
    M

[^87]: C
    github.com/new
    E
    New repository
    Q Type to search
    Create a new repository
    A repository contains all project files, including the revision history. Already have a project repository elsewhere
    Import a repository.
    Required fields are marked with an asterisk (").
    Owner \*
    Repository name \*
    daws-76s
    k8-databases
    k8-databases is available.
    Great repository names are short and memorable. Need inspiration? How about supreme-octo-sniffle ?
    Description (optional)
    O
    Public
    Anyone on the internet can see this repository. You choose who can commit.
    O
    Private
    You choose who can see and commit to this repository.

[^88]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ cd .. /k8-databases/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases
    S git init
    Initialized empty Git repository in C: /devops/daws-76s/repos/k8-databases/. git/
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (master)
    $ git branch -M main
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git remote add origin git@github. com: daws-76s/k8-databases. git
    user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    S

[^89]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-databases (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    \[main (root-commit) aa75322\] jenkins
    4 files changed, 61 insertions (+)
    create mode 100644 mongodb /Chart. yam1
    create mode 100644 mongodb/templates/service . yam1

[^90]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-89-51 \~/k8-resources/sets \]$ cd
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ git clone https: //github. com/daws-76s/k8-databases . git
    Cloning into 'k8-databases' .
    remote: Enumeratiog objects: 8, done.
    remote: Counting objects: 100% (8/8) , done.
    remote: Compressing objects: 100% (6/6) , done.
    remote: Total 8 (delta 0) , reused 8 (delta 0) , pack-reused 0
    Receiving objects: 100% (8/8) , done.

[^91]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| null
    \[ centos@ip-172-31-89-51 \~ \]$ cd k8-databases/
    54 . 234 . 195. 42 \| 172.31. 89.51 \| t2.micro \| https: //github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases \]$ cd mongodb/

[^92]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ helm install mongodb
    NAME : mongodb
    LAST DEPLOYED: Thu Feb 29 03:17:29 2024
    NAMESPACE: default
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^93]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: //github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ helm list
    NAME
    NAMESPACE
    REVISION
    UPDATED
    STATUS
    CHART
    APP VERSION
    mongodb default
    2024-02-29 03:17:29.2803859 +0000 UTC
    deployed
    mongodb-0 . 0 .2
    v1

[^94]: 54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    label-demo
    1/1
    Running
    25m
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    26m
    nginx-deployment-86d976d8bd-75gbh
    1/1
    Running
    26m
    OooOoo
    nginx-deployment-86d976d8bd-t99gl
    1/1
    Running
    26m
    web-0
    1/1
    Running
    32s
    web-1
    0/1
    ContainerCreating
    11s

[^95]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ helm uninstall mongodb
    release "mongodb" uninstalled

[^96]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ kubectl get pvc
    NAME
    STATUS
    VOLUME
    CAPACITY
    ACCESS MODES
    STORAGECLASS
    AGE
    mongodb-web-0
    Bound
    pvc-ea237046-61fa-4960-818a-51cf6903f024
    1Gi
    RWO
    ebs-sc
    59s
    mongodb-web-1
    Bound
    pvc-20e188a0-8987-499f-9486-144214d91f4b
    1Gi
    RWO
    ebs-sc
    38s

[^97]: 54 . 234 . 195. 42 \| 172 . 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ kubectl delete pvc mongodb-web-0 mongodb-web-1
    persistentvolumeclaim "mongodb-web-0" deleted
    persistentvolumeclaim "mongodb-web-1" deleted

[^98]: 54 . 234 . 195. 42 \| 172. 31.89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ helm install mongodb
    NAME: mongodb
    LAST DEPLOYED: Thu Feb 29 03:19:11 2024
    NAMESPACE: default
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None

[^99]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    label-demo
    1/1
    Running
    0
    26m
    mongodb-0
    0/1
    Pending
    0
    5s
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    0
    28m
    nginx-deployment-86d976d8bd-75gbh
    1/1
    Running
    28m
    O O
    nginx-deployment-86d976d8bd-t99gl
    1/1
    Running
    28m
    54 . 234. 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ kubectl logs -f mongodb-0

[^100]: {"t": {"$date" : "2024-02-29T03: 19:27. 115+00:00"} , "s" : "I", "c": "REPL",
    "id" : 6015317, "ctx" :"initandlisten", "msg" : "Setting new config
    ration state", "attr": {"newState" : "ConfigReplicationDisabled", "oldState" : "ConfigPreStart"}}
    {"t": {"$date" : "2024-02-29T03: 19:27. 117+00:00"}, "s" : "I",
    "C" : "NETWORK"
    "id" : 23015,
    "ctx" : "listener" , "msg" : "Listening on", "attr" : ("
    ddress" : "/tmp/mongodb-27017. sock"}}
    {"t": {"$date" : "2024-02-29T03 : 19:27. 117+00:00"}, "s" : "I", "c" : "NETWORK",
    "id" : 23015,
    "ctx" : "listener" , "msg": "Listening on", "attr": {"
    ddress" : "0.0.0.0"}}
    {"t": {"$date" : "2024-02-29T03: 19:27. 117+00:00"}, "s" : "I",
    "C" : "NETWORK",
    "id" : 23016,
    "ctx" : "listener", "msg" : "Waiting for connections
    "attr" : {"port" :27017, "ssl" : "off"}}

[^101]: Volumes (1/6) Info
    C
    Actions
    Create volume
    Q Search
    < 1 >
    -
    Name
    Volume ID
    Type V Size
    Sdol 4
    Throughput V Snapshot
    Created
    vol-0895f4bc76ba3bafa
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:49 GMT +5:...
    V
    vol-020cf95b1bOfbe548
    gp3
    1 GIB
    3000
    125
    2024/02/29 08:49 GMT+5:...
    O
    roboshop-spot...
    vol-08bbc3ba2842a80be
    gp3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT+5:...
    roboshop-spot...
    vol-017f5b93b2ae74a94
    gp3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT+5:...
    O
    roboshop-spot...
    vol-0c5508135c55de05d
    9p3
    80 GiB
    3000
    125
    snap-0647d32...
    2024/02/29 06:50 GMT +5:...
    workstation-e...
    vol-00b8c59bbeb3da50f
    9p2
    10 GiB
    100
    snap-Od6f961...
    2024/02/29 06:31 GMT +5:...
    Volume ID: vol-020cf95b 1bOfbe548
    X
    Tags
    Manage tags
    Q Filter tags
    <
    1 >
    Key
    Value
    kubernete...
    pvc-98755748-2919-4933-bff4-86912116e63d
    kubernete...
    mongodb-mongodb-1
    ebs.csi.aws...
    true
    kubernete...
    default
    CSIVolume...
    pvc-98755748-29d9-4933-bff4-86912116e63d

[^102]: stateruiset.yami
    service.yami ... \\mong
    REPOS
    k8-databases > mongodb > ! values.yaml > {}
    > .github
    1
    statefulset :
    > archieve
    2
    replicas: 3
    3
    > catalogue
    imageVersion: v1
    > catalogue-deploy
    > dockerfiles
    > helm-charts
    k8-databases \\ mongodb
    templates
    ! service.yaml
    ! statefulset.yaml
    ! Chart.yaml
    ! values.yaml

[^103]: 54 . 234 . 195. 42 \| 172. 31. 89.51 \| t2.micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ git pull
    remote: Enumeratiog objects: 7, done.
    remote: Counting objects: 100% (7/7) , done.
    remote: Compressing objects: 100% (1/1) , done.
    remote: Total 4 (delta 1) , reused 4 (delta 1) , pack-reused 0
    Unpacking objects: 1008 (4/4)
    313 bytes
    313.00 KiB/s. done

[^104]: 54. 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ helm upgrade mongodb
    Release "mongodb" has been upgraded. Happy Helming!
    NAME : mongodb
    LAST DEPLOYED: Thu Feb 29 03:20:29 2024
    NAMESPACE: default
    STATUS: deployed
    REVISION: 2
    TEST SUITE: None
    54 . 234. 195. 42 \| 172. 31.89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-databases . git

[^105]: 54 . 234. 195. 42 \| 172. 31.89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-databases . git
    \[ centos@ip-172-31-89-51 \~/k8-databases/mongodb \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    label-demo
    1/1
    Running
    0
    27m
    mongodb-0
    1/1
    Running
    0
    82s
    mongodb-1
    1/1
    Running
    0
    68s
    mongodb-1
    0/1
    Pending
    0
    4s
    nginx-deployment-86d976d8bd-6bk91
    1/1
    Running
    0
    29m

[^106]: Does my database have
    Kubernetes friendly features
    NO
    YES
    Is there an operator or
    Is the database workload
    project to help
    ES
    Kubernetes friendly?
    NO
    YES
    How much Ops workload
    How much Ops workload
    is acceptable?
    is acceptable?
    I'll manage it
    Not much
    Not much
    I'll manage it
    Run it on a
    Use a fully
    Run it on a
    VM
    managed DB
    Kubernetes

