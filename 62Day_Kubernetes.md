---
title: 62Day_Kubernetes
uuid: ddc6c490-47dc-11ef-8674-6ef34fa959ce
version: 587
created: '2024-07-22T09:15:40+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#F8914D;">**Kubernetes Architecture**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

\

**Good site for Kubernetes architecture** --> [Kubernetes - Architecture - GeeksforGeeks][^1] 

 

![ec3a5fd7-4efd-44c6-87f6-0dac586c8cd7.png|561](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/ec3a5fd7-4efd-44c6-87f6-0dac586c8cd7.png) [^2]

![853f71a6-9f7f-4d98-aed0-bac93b5cd734.png|797](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/853f71a6-9f7f-4d98-aed0-bac93b5cd734.png) [^3]

- Master Node is nothing but control plane.

- Cluster Nodes

- **Kubectl** --> command line to connect k8 cluster nodes.

\

<mark>**Control plane components:**</mark>

- **Kube-APIserver**  --> It responds to kubectl commands. Ex: **kubectl get pods** --> This command first it goes to kube-APIserver, Kube-APIserver generally validates authentication & authorization.  This is the front face for the Kubernetes control plane.

- Kube-Apiserver is designed to scale horizontally -- It scales by deploying more instances. You can run several instances of kube-apiserver and balance traffic between those instances.

- Getting information is done by kube-APIserver and creating resources kube-apiserver will handover that request to scheduler. 

- **Kube-Scheduler -->** Control plane component that watches for newly created pods with no assigned node and It will decide which node to create the POD, based on few factors.

- It will take few considerations to create POD or resources. Based on node-labels, node-selectors, taints and tolerations and Affinity, Anti-Affinity.

- **etcd -**-> Entire data corresponds to Kubernetes cluster (it's like a database) ... Like information of ConfigMap, Secrets. If this corrupts then there is no way to get the data from Kubernetes. 

- ![7ca7cc2b-980c-422c-a2c4-0515c3a25d2b.png|674](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/7ca7cc2b-980c-422c-a2c4-0515c3a25d2b.png) [^4]

- **Kube-Controller-Manager -->** Control plane component that runs controller processes.

- ![81b65005-7703-4962-a824-c7e062c2a44e.png|993.6666870117188](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/81b65005-7703-4962-a824-c7e062c2a44e.png) [^5]

\

<mark>**Worker Node Components:**</mark>

**Kubelet -->** components that makes sure nodes are connected to control plane.

**Kube-proxy -->** Responsible to forward the requests from services to PODS.

**Container Runtime -->** A runtime that can run any images to Containers.

\

\

# <mark style="background-color:#F8914D;">**Deployment strategies: **<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Total 6 deployment strategies - few are zero downtime, few are legacy.

[Six Strategies for Application Deployment - The New Stack](https://thenewstack.io/deployment-strategies/)   --> It has good information 

\

<mark>**Rolling update (Ramped):**</mark> 

- If 4 PODS are running, now we are planning to upgrade Application then 1 new POD will come to running stage and 1 old POD will be terminated. same for other PODS. Its one of the zero downtime deployment strategies.

- Pros:

    - Easy to setup.

    - Version is slowly released across instances.

    - convenient for stateful applications that can handle rebalancing of the data.

- cons:

    - Rollout/Rollback can take time.

    - Supporting multiple API's is hard.

    - No control over traffic.

\

<mark>**Blue/Green: **</mark>

- 4 current pods are running, 4 new set pods will run...

- We will test current version, if everything is fine... we will change the DNS records.

- Target group --> old version

- Another target group --> pointing to new version VM's

- We will update the rule, to send requests to new target group...

    - blue --> running version

    - green --> new version

    - green will become blue if everything is good.

- Pros:

    - Instant rollout/rollback.

    - Avoid versioning issue, the entire application state is changed in one go.

- Cons:

    - Expensive as it requires double the resources.

    - Proper test of the entire platform should be done before releasing the production.

    - Handling stateful applications can be hard.

\

<mark>**Canary:**</mark>

- Version B is released to a subset of users, then proceed to a full rollout.

- Ex: WhatsApp releases its new version to Singapore country(small population) and get the feedback and if all looks good it releases to big population countries like India etc...  

- Pros:

    - version released for a subset of users.

    - convenient for error rate and performance monitoring.

    - fast rollback.

- cons:

    - slow rollout. 

\

<mark>**A/B testing:**</mark> 

It's similar to canary, Version B is released to a subset of users under specific conditions.

\

<mark>**Shadow:**</mark> 

- Version B receives real-world traffic alongside version A and doesn't impact the response.

- It sends new version to few random users, if no impact it will roll out to other users.

\

<mark>**Recreate:**</mark> 

- Version A is terminated then version B is rolled out. 

- This will have downtime.

- Pros:

    - Easy to setup.

    - Application state entirely renewed.

- Cons:

    - High impact on the user, expect downtime that depends on both shutdown and boot duration of the application.

\

# <mark style="background-color:#F8914D;">**EKS Upgrade using Blue/green:**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![b516011f-340f-45ee-a4b2-17d99ee76fb6.png|1090.666748046875](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/b516011f-340f-45ee-a4b2-17d99ee76fb6.png) [^6]

\

\

\

\

\

\

\

\

\

\

\

\

[^1]: [Kubernetes - Architecture - GeeksforGeeks](https://www.geeksforgeeks.org/kubernetes-architecture/)

    Kubernetes Architecture

[^2]: incoming requests to the system
    outgoing requests from the system

[^3]: Worker Node
    Kubelet
    Kube-Proxy
    Kubectl
    Master Node
    Pod
    Pod
    Docker
    API Server
    Controller-
    Scheduler
    Manager
    Kubelet
    Kube-Proxy
    etcd
    Pod
    Pod
    Docker

[^4]: Consistent and highly-available key value store used as Kubernetes' backing store for all cluster
    data.
    If your Kubernetes cluster uses etcd as its backing store, make sure you have a back up plan for the
    data.

[^5]: kube-controller-manager
    I
    node control --> Responsible for noticing and responding when nodes go down.
    Job controller --> controlls the jobs. create pods, once pod complete their task job
    controller will mark it as completed.
    replication controller --> it makes sure requested number of replicas are always running.
    EndpointSlice controller --> makes sure the endpoints are created for services.

[^6]: 3 nodes --> 1.27
    upgrade master node --> you can't deploy new applications. but existing applications will
    run. we will announce downtime.
    we will create another node group --> 1.29 --> green
    we will slowly drain the nodes. for example old-node-1 is drained and other old nodes are
    tainted. then pods will automatically come up into new nodes.. .
    we will old node group. ..

