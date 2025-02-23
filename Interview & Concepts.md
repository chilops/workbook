---
title: Interview & Concepts
uuid: 0729dc16-5479-11ef-a2e2-0663d8339c46
version: 7823
created: '2024-08-07T10:23:45+05:30'
tags:
  - interview
---

\

\

# <mark style="background-color:#F3DE6C;">**Tell Me about yourself**<!-- {"backgroundCycleColor":"14"} --></mark><!-- {"collapsed":true} -->

1\*\*\*

My name is Satya Chilukuri, 

I'm originally from Andhra Pradesh and have been living in Bangalore for the past five years. 

\

I completed my MCA at Andhra University and have more than 9 years of experience in IT, working in different roles and technologies. 

\

2\*\*\*

I joined TCS in 2019, I work at TCS as a AWS solution architect and Kubernetes administrator, I manage several projects independently, which includes one internal and two for external clients (e-commerce). 

\

I’ve spent the last five years exploring various technologies and working with different teams. Before TCS, I worked at companies like SIFY, Verizon, and AT&T.

\

TCS allowed me to work with cloud and DevOps tools like AWS, Kubernetes, and Terraform. 

\

3\*\*\*

And I also work with the Center of Excellence team (CoE), engaging with different clients to understand their on-premises infra and running POCs based on their requirements.

I helped to set up AWS cloud infrastructure using Infrastructure as Code tools like Terraform, and we maintain custom Terraform modules. 

\

4\*\*\*

For the past two years, I’ve been working as a Kubernetes administrator, using AWS EKS for deployments. 

We manage legacy applications (apps) on VMs and also, we have autoscaling in place for both VMs and EKS clusters. 

\

5\*\*\*

Our tech stack consists of:

- **Docker:** We use it to create and manage container images, and deploy them with Amazon ECS and EKS for scalable container management within AWS.

- **GitHub/Bitbucket:** These are our version control tools, with GitHub Enterprise integrated into our own infrastructure.

- **SonarQube:** We use it for code scanning. Though AWS CodeGuru can be a partial alternative, SonarQube is still used for its broader language support and can be set up on AWS using EC2 or a pre-configured instance.

- **Nexus and AWS CodeArtifact:** These tools are used for uploading and managing artifacts.

- **Jenkins:** Our CI/CD tool for automating builds, testing, and deployment. AWS alternatives include CodePipeline for automating the CI/CD process and CodeBuild for building and testing code.

- **Terraform -- Infra as a code.**

- **Ansible playbooks for Infra.**

- **Shell scripts** - automate repetitive tasks, such as file management, backups, and system monitoring.

\

8\*\*\*

As a key member of the COE team, I help in bringing projects to TCS. We focus on finding ways to migrate monolithic applications to microservices and aim to lower project costs by automating the infrastructure as much as we can by using tools like Ansible and shell scripts after the applications go live.

\

9\*\*\*

Although I initially wanted to start my career as a Linux administrator, but I began as a storage administrator.

For the first five years, I managed SAN storage arrays like EMC, Hitachi, PURE, and NetApp, along with backup tools such as NetBackup, Clumio, and TSM. 

\

I gained valuable infrastructure knowledge during my one-year experience working in a **datacenter**, where I learned a lot and developed essential skills.

\

10\*\*\*

I have done **3 certifications.** 

\-One is Storage related certification - **EMC ISM V3**

\-Other 2 are on Azure certifications - **Azure fundamentals (AZ-900, AZ-104)**

\

11\*\*\*

The primary reason I'm exploring new opportunities is for salary growth. Over the past 5 years at TCS, I've gained valuable experience and learned a lot, but my only regret is that my salary hasn't kept pace with industry standards. As for my career growth, I'm very happy with the diverse skills I've developed and excited to continue learning new things in the future.

\

# 

# <mark style="background-color:#F8914D;">**Kubernetes**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![88d372c0-b6a9-4552-b6c6-3fb5bb051292.png|667](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/88d372c0-b6a9-4552-b6c6-3fb5bb051292.png) [^1]

### **1Q. What is Kubernetes and Architecture?**<!-- {"collapsed":true} -->

**Good site for Kubernetes architecture** --> [Kubernetes - Architecture - GeeksforGeeks][^2] 

\

Kubernetes is popular container orchestration tool.  It is responsible to run and manage the containers.

Kubernetes helps to manage & automate the deployment, scaling and management of containerized applications.

\

- Kubernetes is like a well-organized team.

- The Master Node is the Manager, making big decisions.

- The Worker Nodes are the team members, doing the actual work.

- Master Node is the 'brain' of kubernetes.

    - It has key parts like:

    - **API server** - connects everything.

    - **Scheduler** - Decides where to run tasks.

    - **Controller Manager** - Keeps everything working smoothly.

    - **ETCD** - Stores all the data securely.

**How they work together:**

- The master nodes give instructions to the worker nodes.

- Worker nodes follow these instructions to run the apps.

- This teamwork helps apps running reliably, even if something breaks.

**Why this setup?**

- Kubernetes architecture makes managing apps easier!

- It's scalable (can grow as you need).

- It's resilient (keeps running smoothly even if parts fail)

- It's perfect for complex systems.

\

![dea7bce9-efe4-4793-8f46-e4dd89a71829.png|763](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/dea7bce9-efe4-4793-8f46-e4dd89a71829.png) [^3]

\

**The Control Plane Node: The Brain -** This is where the decision-making happens. Every Kubernetes cluster has one or more control plane nodes that oversee everything in the cluster.

\

**API Server (**`api`**)**:  Think of it as the front desk of Kubernetes. Every `kubectl` command or internal component interaction goes through the API server. It validates your requests and routes them to the right place.

\

**Controller Manager (**`c-m`**)**: The automation genius. If your app's desired state (like 3 replicas) doesn’t match reality, the controller manager steps in to create, delete, or update resources.

\

**Scheduler (**`sched`**)**: New pod? Cool. The scheduler finds the best worker node for it, considering factors like resources, affinity, and taints. It's all about optimal placement.

\

**etcd**: The brain's memory. This is a highly consistent key-value store that keeps track of everything in the cluster. If etcd is down, Kubernetes forgets the cluster's state.

\

**kubelet on Control Plane**: Just like on worker nodes, the kubelet on the control plane ensures containers running here are healthy and up to date.

\

**Worker Node: The Muscles -** While the control plane is busy planning and deciding, the worker nodes do the **actual work**.

\

**kubelet**: The node's manager. It takes orders from the API server and ensures that containers (running inside pods) are healthy and doing what they're supposed to. It’s like the node's personal assistant.

\

**Kube-proxy (**`k-proxy`**)**: Handles networking. It ensures every pod can talk to other pods and services inside (and sometimes outside) the cluster. It uses **iptables** or similar tools to manage network rules.

\

**Container Runtime**: This is what runs the actual containers. Whether it’s Docker, containerd, or CRI-O, it’s all about keeping your apps alive and isolated.

\

**Pods and Containers**: Pods are the smallest deployable units in Kubernetes. Each pod wraps one or more containers and shares networking and storage. The containers inside do the heavy lifting—running your application code.

\

\

**Control plane components (master Node):**

1. **kube-apiserver:** The kube-apiserver connects to the Kubernetes API and helps to perform all the administrative tasks given by the user and stores the cluster state in `etcd` key-value store after all the executions are done. It is the front end on Kube control plane. It is scaled horizontally i.e. it scales by increasing the number of instances.

1. **etcd:** etcd is a highly reliable and distributed key-value store which is used to store the data regarding cluster state. It can be part of the master node or can be external in which case the master node connects to it.

1. **kube-scheduler:** The scheduler is responsible for scheduling and assigning pods (a group of one or more containers) to specific nodes in the cluster based on resource requirements and constraints.

1. **kube-controller-manager:**  Controllers manage pods. They take the desired state in the form of controller objects and maintain it.  **Replication Controller** and ReplicaSets select pods based on labels and maintain the desired number of copies of pods.  **Deployment** internally uses ReplicaSet to maintain replicas and maintain the desired state at any point in time. **DaemonSets** are used to run one pod per node. **StatefulSets** are used to run stateful applications.

1. **Cloud-controller-manager:** It is responsible for interacting with underlying cloud provider and managing resources specific to that cloud platform.

\

**Node Components:**

1. **kubelet: `kubelet`** is a worker node component that runs on every worker node in a cluster and is used to communicate with the master node. It runs containers inside a `pod` according to `pod-spec`.

1. **kube-proxy:** It is a kubernetes network proxy service that runs on every node, it is used to connect the application to the external world/environment. Instead of directly connecting to the pods to interact with the application `Services` are used.

1. **Container Runtime:** Every container must have a container runtime; it is used to run and maintain containers in a node. Container runtime are tools or software that are used to create and run containers. Eg: dockers and rkt.

![c5aff5bd-4310-4b18-90a6-ab651d685467.jpg|819.9884643554688](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/c5aff5bd-4310-4b18-90a6-ab651d685467.jpg) [^4]

\

**Cluster:** Collection of machines

**Master Node:** Manages and coordinates the cluster.

**Worker Nodes:** Run the application.

**PODS:** Groups of containers.

**Services:** Network access for pods.

**Volumes:** Persistent data storage.

**ConfigMaps/Secrets:** Manage configuration and sensitive data.

\

\

- Kubernetes run across a cluster node.

- Using Kubernetes different nodes can communicate with each other.

- Kubernetes is an open-source platform also, this is widely used in industries.

- Kubernetes takes care of scaling and failover for your application running on the container.

\

![8aa8d1a2-d1f6-4a69-a069-c92f08d2e213.jpg|871.9791870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8aa8d1a2-d1f6-4a69-a069-c92f08d2e213.jpg) [^5]

![3dfbf686-ae5b-43f2-ac8a-a906f7073d9a.png|336](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3dfbf686-ae5b-43f2-ac8a-a906f7073d9a.png) [^6]

\

### **2Q. What are Kubernetes Pods?**<!-- {"collapsed":true} -->

- It a smallest deployable unit in Kubernetes (POD same as container). It contains one or more applications in a container. 

- PODS are temporary - If one fails, Kubernetes auto-creates a new one to keep things running smoothly.

- PODS are the workers in your Kubernetes cluster.

    - Have a unique IP address for easy communication.

    - Use storage volumes as needed.

    - Carry configuration info for container operations.

    - Most pods have one container, but some team up a few to get the jobs done.

![11eae365-e37e-4a4d-b439-599e393dc26b.png|665.0000610351562](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/11eae365-e37e-4a4d-b439-599e393dc26b.png) [^7]

**Benefits:**

- Multiple containers in a pod communicate easily via localhost.

- Simplify data sharing.

- Start containers for tasks before the main application runs.

- Scale automatically based on demand.

- Pods make scaling and communication a breeze.

![00d911e8-1633-4dbd-a782-8f4e643a7982.png|373](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/00d911e8-1633-4dbd-a782-8f4e643a7982.png) [^8]

**How PODS communicate:**

- Each POD gets a dynamic unique IP.

- Inside a POD, containers chat via localhost. pods talk to each other using cluster-private IPs, no extra setup needed.

- This seamless communication keeps your cluster running like a well-oiled machine.

 

### **3Q. What is the difference between eksctl and kubectl?**<!-- {"collapsed":true} -->

`eksctl` and `kubectl` are both command-line tools related to Kubernetes, but they serve different purposes and operate at different levels of abstraction:

\

1\. **eksctl**

- **Purpose**: `eksctl` is a command-line tool specifically designed to create, manage, and interact with Amazon EKS (Elastic Kubernetes Service) clusters. It's a high-level tool that simplifies the process of setting up and maintaining Kubernetes clusters on AWS.

- **Usage**:

    - **Cluster Management**: `eksctl` is used to create, delete, and manage EKS clusters on AWS. For example, you can use it to create a new cluster with a single command.

    - **Node Management**: It can also manage node groups within an EKS cluster, allowing you to easily scale your cluster.

![af91c856-7e69-461e-bf61-bb5884e2c088.png|797.9977416992188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/af91c856-7e69-461e-bf61-bb5884e2c088.png) [^9]

\

2\. **kubectl**

- **Purpose**: `kubectl` is the standard command-line tool used to interact with Kubernetes clusters, regardless of where they are hosted (AWS, Google Cloud, on-premises, etc.). It allows you to control and manage Kubernetes resources.

- **Usage**:

    - **Resource Management**: `kubectl` is used to manage Kubernetes resources like pods, deployments, services, and more. It operates at the level of Kubernetes objects and configurations.

    - **Cluster Interaction**: Once your Kubernetes cluster is up and running (regardless of how it was created), `kubectl` is used to interact with it by applying configurations, inspecting resources, and troubleshooting.

![7ea83e25-a5de-443d-a6b4-d5a9d2a19390.png|803.9931030273438](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/7ea83e25-a5de-443d-a6b4-d5a9d2a19390.png) [^10]

```
kubectl get nodes
```

**Summary**

- **`eksctl`** is primarily used for setting up and managing EKS clusters on AWS.

- **`kubectl`** is used for interacting with Kubernetes resources within any Kubernetes cluster, including those created by `eksctl`.

You would typically use `eksctl` to set up an EKS cluster and then use `kubectl` to manage the workloads and resources within that cluster.

\

\

### **4Q. Namespace (Kubernetes resource)**<!-- {"collapsed":true} -->

Namespace --> it is like a project in your Kubernetes cluster to provision your project resources. it is isolated

Every resource is YAML.

\

In Kubernetes, a **namespace** is like a separate workspace or environment within your Kubernetes cluster.

\

**Why Use Namespaces:**

- **Organizing Resources**: Imagine you have a big company with different teams (like development, testing, and production). Each team needs its own space to work without interfering with others. In Kubernetes, namespaces create these separate spaces.

- **Avoiding Conflicts**: If two teams want to name their applications the same, namespaces ensure there’s no conflict because each application is in its own namespace.

- **Resource Isolation**: Namespaces can help you control resources (like CPU and memory) for each team or project, making sure one doesn’t take more than its fair share.

**How It Works**

- **Default Namespace**: When you create something in Kubernetes and don’t specify a namespace, it goes into the `default` namespace.

- **Creating a Namespace**: You can create your own namespaces for different projects or teams.

- **Using a Namespace**: When you work with resources, you can specify which namespace they belong to.

**Example**

- **Without Namespaces**:

    - If you have two apps named "frontend" and "backend," both would be in the same space, and you can only have one of each.

- **With Namespaces**:

    - You can have a "frontend" app in a `dev` namespace and another "frontend" app in a `prod` namespace. They won’t interfere with each other because they’re in different spaces.

```
apiVersion :
kind: # what kind of resource you are creating
metadata:
name :
```

![8f19e3a9-1d8c-49f8-8501-51ae36bfbe37.png|864](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8f19e3a9-1d8c-49f8-8501-51ae36bfbe37.png) [^11]

### **5Q. Can multiple containers run in a POD?**<!-- {"collapsed":true} -->

![8db0ae92-3b52-4882-bdd6-7fa16398847c.png|554](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8db0ae92-3b52-4882-bdd6-7fa16398847c.png) [^12]

Multiple containers in a Pod are used when there's a need for close coordination, shared resources, or sidecar functionalities that complement the main application running in the Pod.

\

In Kubernetes, a **Pod** is the smallest deployable unit and can contain one or more containers. There are several reasons why you might have multiple containers in a single Pod:

1. **Tight Coupling**: When containers need to work closely together, they are often placed in the same Pod. For example, you might have one container serving an application and another container logging data for that application. They share the same network namespace and can easily communicate via `localhost`.

1. **Shared Resources**: Containers within the same Pod share the same storage volumes and can access the same files. This is useful if you have multiple containers that need to access the same data, such as a web server and a file processing service.

1. **Sidecar Pattern**: A common use case for multiple containers in a Pod is the sidecar pattern, where one container adds functionality to the main container. For example, you might have a sidecar container handling log collection, monitoring, or injecting security configurations.

1. **Ambassador Pattern**: This pattern involves one container acting as a proxy or ambassador to the outside world for another container. This can be useful for services that need to interact with legacy systems or external APIs.

1. **Adapter Pattern**: Sometimes, a container is used to modify or adapt the output of another container before it is consumed by the main application. For instance, a container could transform data from one format to another, making it easier for the main application to consume.

1. **Shared Namespace**: Containers in the same Pod share the same network namespace, meaning they can communicate with each other using `localhost`. This is useful for closely related processes that need to be aware of each other's presence without exposing services to the external network.

\

### **6Q. <mark>Annotations in Kubernetes?</mark>**<!-- {"collapsed":true} -->

![8197b075-444c-4d0c-a358-29b7cb86f750.png|856](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8197b075-444c-4d0c-a358-29b7cb86f750.png) [^13]

\

```
kubectl describe pod <POD Name>
```

![0f4aef69-4086-41be-87ee-0f413469a86e.png|1156.2037353515625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/0f4aef69-4086-41be-87ee-0f413469a86e.png) [^14]

\

![ad124751-b492-450e-a05f-080c98c18d69.png|550.9838256835938](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/ad124751-b492-450e-a05f-080c98c18d69.png) [^15]

### **7Q. How resources used in Kubernetes?**<!-- {"collapsed":true} -->

![a05fdef4-be06-486f-8b4f-2afe0a0b6062.png|1034](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/a05fdef4-be06-486f-8b4f-2afe0a0b6062.png) [^16]

\

Restrict POD resources:

![0d3593ab-d9a4-46f7-b0ad-e0a1dc0c1843.png|483](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/0d3593ab-d9a4-46f7-b0ad-e0a1dc0c1843.png) [^17]

\

### **8Q. What are ConfigMap in Kubernetes?** It's nothing but a key value pair (to store environment parameters)<!-- {"collapsed":true} -->

A **ConfigMap** is a way to store configuration data for applications running in a Kubernetes cluster. It's like a dictionary or a set of instructions that your applications can read and follow. Instead of **hard coding** the configuration settings directly into your app, you store them separately in a ConfigMap. This makes it easy to change the settings without having to modify the application code.

\

For example, you might use a ConfigMap to store database connection strings, API keys, or environment-specific settings. The app can then read these settings at runtime and use them accordingly.

\

ConfigMaps are especially useful when you need to configure applications in different environments (e.g., development, staging, production) without altering the application itself.

\

### **9Q. What are Secrets in Kubernetes?**<!-- {"collapsed":true} -->

In Kubernetes, a **Secret** is used to store sensitive information, such as passwords, tokens, and keys. Unlike ConfigMaps, which store non-sensitive data, Secrets are specifically designed to keep your important information secure and encrypted.

\

For example, if your application needs to connect to a database, you can use a Secret to store the database password. This way, the password isn't hard-coded into your application, and it's protected from being exposed.

\

In a nutshell, Secrets help keep your sensitive data safe and separate from your application code.

\

Secrets help keep your application’s sensitive data secure, reducing the risk of exposing confidential information.

\

### **10Q. Kubernetes services? (cluster IP, node port, load balancer)**<!-- {"collapsed":true} -->

![6655c8a3-7cbb-433e-95f8-0d4609aaed34.png|1028.9814453125](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/6655c8a3-7cbb-433e-95f8-0d4609aaed34.png) [^18]

\

Every POD should attach to services

![993ac4ce-c57c-4695-9aaf-786009b2e960.png|446](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/993ac4ce-c57c-4695-9aaf-786009b2e960.png) [^19]

\

- **Types**: Different types of services include `ClusterIP` (internal access), `NodePort` (external access via a node's IP), `LoadBalancer` (external access with a cloud provider's load balancer), and `ExternalName` (maps the service to an external DNS name).

- **Purpose**: Provides a stable network identity (IP and DNS name) to a group of Pods, even if the underlying Pods change (e.g., due to scaling).

- **Load Balancing**: Distributes traffic among the Pods in the service, ensuring high availability and reliability.

Services make it easy to expose your application within and outside the cluster while managing load balancing and service discovery.

\

```
kubectl get service
```

\

### **11Q. What is ClusterIP service in Kubernetes?**<!-- {"collapsed":true} -->

A **ClusterIP** service in Kubernetes is the default type of service that provides internal access to your application within the Kubernetes cluster. It exposes the service on a stable internal IP address, which can only be accessed from within the cluster.

Here’s a brief overview:

- **Internal Access**: Only accessible within the Kubernetes cluster; not exposed to the external network.

- **Use Case**: Ideal for internal communication between microservices within the cluster, like databases or backend services that don’t need to be accessed directly by users.

- **IP Address**: Automatically assigned an IP address by Kubernetes that is used by other services or Pods within the cluster to reach the service.

ClusterIP services are essential for managing internal traffic within your Kubernetes environment, ensuring that services can communicate with each other securely and efficiently.

\

### **12Q. What is NodePort service in Kubernetes?**<!-- {"collapsed":true} -->

A **NodePort** service in Kubernetes exposes your service on each Node's IP address at a static port. This allows external access to your service from outside the Kubernetes cluster, making it possible to communicate with the service directly through the node's IP and the specified port.

Here’s a brief overview:

- **External Access**: Exposes the service on a specific port on each Node in the cluster, allowing external traffic to reach the service.

- **Port Range**: The port number is typically chosen from a range of 30000-32767, though you can specify a custom port within this range.

- **Access Method**: You can access the service using `<NodeIP>:<NodePort>`, where `NodeIP` is the IP address of any Node in the cluster, and `NodePort` is the port number allocated by Kubernetes.

NodePort services are useful when you need to expose a service to external users or applications without using a cloud provider’s load balancer. However, it’s more rudimentary compared to the `LoadBalancer` service, as it relies on the node’s IP and port for access.

\

<mark>**If we create NodePort then ClusterIP also by default it creates**</mark>

![c9ec92e8-247a-421c-af5f-4f884a0eb338.png|683](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c9ec92e8-247a-421c-af5f-4f884a0eb338.png) [^20]

\

### **13Q. What is Load Balancer service in Kubernetes?**<!-- {"collapsed":true} -->

A **LoadBalancer** service in Kubernetes automatically provisions an external load balancer to expose your service to the internet or an external network. This service type is primarily used in cloud environments where the cloud provider can allocate a load balancer to route traffic to the Kubernetes service.

Here’s a brief overview:

- **External Access**: Exposes the service to external clients, making it accessible from outside the Kubernetes cluster.

- **Automatic Provisioning**: When you create a LoadBalancer service, Kubernetes interacts with the cloud provider (e.g., AWS, GCP, Azure) to automatically create a load balancer and configure it to forward traffic to the Kubernetes service.

- **Load Distribution**: Distributes incoming traffic across the Pods associated with the service, ensuring even load distribution and improving fault tolerance.

- **Public IP**: The service is assigned a public IP address by the cloud provider, which external clients can use to access the service.

LoadBalancer services are ideal for applications that need to be exposed to the internet or external users, as they provide a managed and scalable way to handle incoming traffic.

\

![b8d067b3-7816-4c43-b83e-61a451529a80.png|378.9930419921875](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/b8d067b3-7816-4c43-b83e-61a451529a80.png) [^21]

![72b70446-4bb9-42af-a007-857cd40d670a.png|852](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/72b70446-4bb9-42af-a007-857cd40d670a.png) [^22]

\

\

### **14Q. Explain ReplicaSet in Kubernetes? & ReplicaSet Vs Replication Controllers?**<!-- {"collapsed":true} -->

In Kubernetes, a ReplicaSet ensures that a specified number of identical copies (replicas) of a pod are running at any given time. Imagine you have an important application, and you want to make sure that there are always exactly three instances of it running. A ReplicaSet will keep an eye on these instances and make sure there are always three. If one of them fails or gets deleted, the ReplicaSet will automatically create a new one to replace it.

\

In essence, ReplicaSets help maintain high availability and scalability of your applications.

\

<mark>ReplicaSet is not useful in changing the version of application. ReplicaSet is only used to maintain the replicas.</mark>

\

**Replication Controller (RC):**

- It ensures that a specified number of pod replicas are running at any given time.

- It helps in scaling up or down and ensures availability.

- It's considered an older resource and doesn't support new features like set-based label selectors.

**ReplicaSet (RS):**

- It's the next-generation version of Replication Controller.

- It offers the same basic functionality of ensuring a specified number of pod replicas.

- It supports new features like set-based label selectors, which allows for more complex and flexible selection of pods.

So, in short, a ReplicaSet is an improved version of a Replication Controller with more flexibility and newer features. Think of it as an upgraded model!

\

### **15Q. Explain Deployment in Kubernetes?**<!-- {"collapsed":true} -->

A **Deployment** in Kubernetes is a higher-level idea that manages a group of Pods and their ReplicaSets. It provides a declarative way to manage application updates, scaling, and rollbacks, making it easier to maintain the desired state of an application.

Here’s a brief overview:

- **Manages ReplicaSets**: A Deployment manages ReplicaSets, which in turn manage the Pods. When you create or update a Deployment, Kubernetes ensures the appropriate ReplicaSet is created or updated accordingly.

- **Rolling Updates**: Deployments support rolling updates, meaning they can gradually replace old Pods with new ones without downtime. This allows for seamless updates to your application.

- **Rollback**: If something goes wrong during an update, you can roll back to a previous version. Kubernetes keeps track of the history of Deployments, making it easy to revert to a stable state.

- **Scaling**: You can scale the number of Pods in a Deployment up or down with a simple command. This can be done manually or automatically using Horizontal Pod Autoscaling.

- **Self-Healing**: Deployments ensure that the specified number of Pods are always running. If a Pod fails, Kubernetes automatically creates a new one to replace it.

Deployments are essential for managing the lifecycle of applications in Kubernetes, providing robust features for deployment strategies, scaling, and maintaining high availability.

\

![c45efcdd-98a5-4307-8b6b-ab226a4c27c6.png|708](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c45efcdd-98a5-4307-8b6b-ab226a4c27c6.png) [^23]

![5104dabe-68e5-47d2-bbc4-e927102cdb4b.png|510](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/5104dabe-68e5-47d2-bbc4-e927102cdb4b.png) [^24]

\

At any point of time 3 pods will run

![9a49d034-a26d-4bb3-9038-c58dd442b647.png|780](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/9a49d034-a26d-4bb3-9038-c58dd442b647.png) [^25]

\

DeploymentSet deletes old ReplicaSet & pods once new ReplicaSet & pods created <mark>**(This is also called ROLLING Update)**</mark>

![bfcca94f-4339-4c9b-9979-dfcf5686ac5b.png|899](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/bfcca94f-4339-4c9b-9979-dfcf5686ac5b.png) [^26]

### **16Q. What is stateless & what is stateful in k8?**<!-- {"collapsed":true} -->

In Kubernetes (K8s), the terms **stateless** and **stateful** refer to how applications or services manage their data and how they handle scaling, failure recovery, and deployment.

\

![352acef9-ebe1-4283-8947-fbc5fc41d444.png|1025](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/352acef9-ebe1-4283-8947-fbc5fc41d444.png) [^27]

\

<mark>**mysql, redis, mongodb & RabbitMQ are stateful applications**</mark>

![2186b359-ba99-4e05-b8d4-f107e780930f.png|1081](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/2186b359-ba99-4e05-b8d4-f107e780930f.png) [^28]

\

**Stateless in Kubernetes**

- **Definition:** In Kubernetes, a stateless application does not retain any data or state between different requests or sessions. Each pod can be replaced, scaled up, or down without any concern for data persistence.

- **Usage:** Stateless applications are often used for web servers, API servers, or microservices that don't need to keep any session or state information.

- **Examples:**

    - **Deployment:** In K8s, you usually deploy stateless applications using a `Deployment`. This controller ensures that the specified number of pod replicas are running and can handle scaling and updates without data loss concerns.

- **Advantages:**

    - Easy to scale horizontally by adding more pods.

    - Simplified deployment and management.

    - High availability, as new pods can easily replace failed ones.

**Stateful in Kubernetes**

- **Definition:** **A StatefulSet** in Kubernetes is used to manage and maintain the deployment and scaling of a set of pods, ensuring each one has a unique, stable network identity and persistent storage. This is useful for applications that require stable and predictable pod names or persistent storage, like databases or other stateful applications.

For example, if you're running a database that needs to keep data even if the pod is restarted or rescheduled, a StatefulSet makes sure that data is not lost and that each pod is uniquely identifiable.

- **Usage:** Stateful applications are often used for databases, message queues, or any service that needs to keep track of state information, such as user sessions, transactions, or data persistence.

- **Examples:**

    - **StatefulSet:** In K8s, `StatefulSet` is used to manage stateful applications. Unlike `Deployment`, `StatefulSet` ensures that pods are created in a specific order, have stable network identifiers, and are attached to persistent storage volumes that survive even if the pod is deleted.

    - **Persistent Volumes (PV):** Stateful applications typically use Persistent Volumes to store data that needs to survive pod restarts or rescheduling.

- **Advantages:**

    - Data persistence is guaranteed, even if individual pods fail or are rescheduled.

    - Stable network identity and persistent storage allow for reliable recovery and data integrity.

    - Suitable for scenarios where the order of operations and unique identities matter, like databases.

**Summary**

- **Stateless:** Ideal for applications that do not need to retain data between sessions. Uses `Deployment` in Kubernetes for scaling and management.

- **Stateful:** Necessary for applications that require data persistence and state retention. Uses `StatefulSet` in Kubernetes to manage pod identities, storage, and order of deployment.

This differentiation is crucial in designing and deploying applications in a Kubernetes environment, as it influences how you handle scaling, storage, and disaster recovery.

\

\

### <mark style="background-color:#FFFFFF;">**17Q. Storage - k8 Volumes?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

![0bc6b573-e304-4511-95c7-d19a09fb6c05.png|381](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/0bc6b573-e304-4511-95c7-d19a09fb6c05.png) [^29]

\

Data is getting stored in EC2 worker nodes...

**pods are ephemeral (temporary), nodes are also ephemeral.**

![edcb2482-d1d8-403f-a01c-e43cf54c20ac.png|319.9884033203125](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/edcb2482-d1d8-403f-a01c-e43cf54c20ac.png) [^30]

![9a1b0a0b-6209-4f87-9fac-8b10f347d28a.png|604](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/9a1b0a0b-6209-4f87-9fac-8b10f347d28a.png) [^31]

\

\

\

### **18Q. What is `emptyDir` in K8?**<!-- {"collapsed":true} -->

Certainly! An `emptyDir` is one of the simplest types of volumes in Kubernetes. It's like a blank folder that gets created when a pod starts, and it's there for temporary storage during the life of that pod. Once the pod is deleted, this folder and its data are also deleted.

\

So, imagine you have a temporary workspace or scratchpad for a task—`emptyDir` is essentially that. It’s especially useful when you need to share data between containers running in the same pod.

\

![5ebaf4a8-0679-4ec9-9c17-8516a56bcc3a.png|731.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5ebaf4a8-0679-4ec9-9c17-8516a56bcc3a.png) [^32]

\

**Considerations:**

- **Non-Persistence:** If your application needs to retain data even if the pod is rescheduled, `emptyDir` is not the right choice. For persistent data, you would use persistent volumes (PVs).

- **Node Affinity:** Since the data is tied to the specific node where the pod is running, if the pod is moved to another node, the data in `emptyDir` is lost.

In summary, `emptyDir` is a useful volume type in Kubernetes for scenarios requiring temporary, non-persistent storage that is local to the node.

\

\

### **19Q. What is filebeat in K8?**<!-- {"collapsed":true} -->

Certainly! Running Filebeat under Kubernetes allows you to collect logs from your applications and nodes within the Kubernetes cluster and send them to a central location for analysis.

Here's a simplified overview:

1. **Deploy Filebeat as a DaemonSet**: This ensures that Filebeat runs on each node in your Kubernetes cluster, collecting logs from all the pods and containers running on those nodes.

1. **Configuration**: You'll configure Filebeat to specify which log files to collect (e.g., container logs) and where to send these logs (e.g., Elasticsearch or Logstash).

1. **Centralized Logging**: Once configured, Filebeat will continuously collect and forward logs to your specified central location. This helps in monitoring and troubleshooting applications running in your Kubernetes cluster.

In essence, think of Filebeat as a diligent log collector for each node in your Kubernetes cluster, ensuring all logs are gathered and sent to a central place for easy access and analysis.

\

![24771776-6b11-4c59-805e-ee98edda90f3.png|770.9837646484375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/24771776-6b11-4c59-805e-ee98edda90f3.png) [^33]

\

**Advantages of Using Filebeat in Kubernetes:**

- **Centralized Logging:** Aggregates logs from all nodes and pods, providing a unified view of logs across the entire cluster.

- **Lightweight:** Filebeat is designed to be lightweight and efficient, consuming minimal resources on each node.

- **Scalability:** Automatically scales with the cluster by using a DaemonSet.

- **Kubernetes Metadata:** Enriches logs with valuable Kubernetes metadata, enabling more powerful search and filtering capabilities.

**Considerations:**

- **Log Volume:** Depending on the number of pods and their verbosity, the log volume can be significant. Ensure your Elasticsearch or other log storage can handle the load.

- **Security:** Consider securing the communication between Filebeat and Elasticsearch, especially in production environments, using TLS and authentication.

Filebeat, when deployed in Kubernetes, provides a robust solution for log aggregation, enabling effective monitoring and troubleshooting across your entire cluster.

\

\

### **20Q. <mark style="background-color:#FFFFFF;">What is DeamonSet & Fluentd in k8?<!-- {"backgroundCycleColor":"11"} --></mark>   DaemonSet Vs Deployment?**

DeamonSet will make sure a POD runs in each and every worker node. If you delete one worker node a POD in it will delete and if we add new worker node to a cluster, then DeamonSet will automatically create POD. (when you create POD, it will create 3 pods in 3 cluster nodes).

<mark style="background-color:#F8914D;">**DeamonSet**<!-- {"backgroundCycleColor":"24"} --></mark> <mark>**- It will make sure a pod runs in each and every node.**</mark> <mark style="background-color:#F8914D;">**Fluentd**<!-- {"backgroundCycleColor":"24"} --></mark> <mark>**will be deployed as DeamonSet that can access the underlying host logs and send them to ELK.**</mark>

\

- Both Deployments and DaemonSets are similar to each other. Both take responsibility of managing Pods and try to maintain the desired state.

- Use Deployments for Stateless Services (front ends), where scaling up and down won't affect Application's functionality.

- Use DaemonSets when it is essential to run pods on each node (or some nodes), and they have to start before any other pods.

### **21Q. External volumes in K8? (PV, PVC)**<!-- {"collapsed":true} -->

- Kubernetes Pods are mortals. They get destroyed and recreated over and over again. However, data stored by the database is critical, and we can't afford to lose that.

- So, volumes come to the rescue. Volumes are external to pods and they remain intact over pod's life cycle.

-  Sometimes it is necessary to share data among pods. Volumes can be used for this purpose.

\

<mark>**Persistent volume - It represents the external storage**</mark>

<mark>**Persistent volume claim - pods should request volumes through PVC**</mark>

\

pod - pvc - pv - ebs

![b9bda56c-f4ec-4ce1-a7d6-8ceefd61c43e.png|448.9930419921875](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b9bda56c-f4ec-4ce1-a7d6-8ceefd61c43e.png) [^34]

**Types of External Volumes in Kubernetes:**

1. **PersistentVolume (PV):**  Certainly! In Kubernetes, a **Persistent Volume (PV)** is a piece of storage in the cluster that has been provisioned by an administrator or dynamically created using Storage Classes. It’s like a storage unit that can hold data for a long time, even if the pod that uses it is deleted.

Here's a simple breakdown:

1. **Creation**: The PV is created and exists in the cluster.

1. **Claiming**: Applications or users request storage by creating a Persistent Volume Claim (PVC). Think of this as a request or a ticket to use a storage unit.

1. **Binding**: The PVC is matched with an appropriate PV.

1. **Usage**: The application uses the PV to store data.

1. **Retention**: Even if the pod using the PV is deleted, the data in the PV remains.

In essence, a PV is like a long-term storage locker that keeps your data safe and accessible, regardless of what happens to the applications using it.

\

1. **PersistentVolumeClaim (PVC)**: This is a request for storage by a user. It is a claim to a PV. Pods can use PVCs as a volume source to store data externally. In Kubernetes, a **Persistent Volume Claim (PVC)** is like a request ticket for storage.<!-- {"offset":1} -->

Here's how it works in simple terms:

1. **Request**: When an application needs storage, it creates a PVC. This is like saying, "I need a storage unit of this size and type."

1. **Match**: The PVC is then matched with an available Persistent Volume (PV) that meets the requested criteria.

1. **Use**: Once matched, the application can use this storage to save its data.

Think of a PVC as a formal way for applications to ask for storage space in a Kubernetes cluster.

\

![cb75eced-2676-47c5-84fc-b0fc10a2a006.png|780.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/cb75eced-2676-47c5-84fc-b0fc10a2a006.png) [^35]

![29084767-fe1a-4941-9f39-45bda4602f70.png|779.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/29084767-fe1a-4941-9f39-45bda4602f70.png) [^36]

\

**Key Points:**

- **Retention Policies**: PVs have a `persistentVolumeReclaimPolicy` which determines what happens to the PV after its PVC is deleted (e.g., Retain, Delete, or Recycle).

- **Access Modes**: These define how the volume can be mounted (e.g., ReadWriteOnce, ReadOnlyMany, ReadWriteMany).

- **Dynamic Provisioning**: You can configure dynamic provisioning using StorageClass, where PVCs automatically trigger the creation of a new PV.

External volumes in Kubernetes are critical for stateful applications that require data persistence, and they integrate well with various storage systems, both on-premises and in the cloud.

\

### **21.5Q. Kubernetes Internal Volumes?**<!-- {"collapsed":true} -->

- Kubernetes, by default, provides volumes associated with pods, but they get destroyed as soon as the pods get destroyed.

- To solve this issue, different kind of volumes came into picture which outlives a pod's life cycle.

### **22Q. Static provisioning vs dynamic provisioning in k8?**<!-- {"collapsed":true} -->

In Kubernetes, **static provisioning** and **dynamic provisioning** are two approaches to managing Persistent Volumes (PVs) for persistent storage in a cluster. They differ primarily in how the storage resources are allocated and bound to Persistent Volume Claims (PVCs).

\

<mark style="background-color:#F3DE6C;">**Static Provisioning:**<!-- {"backgroundCycleColor":"14"} --></mark>

**Static provisioning** is a manual process where an administrator creates Persistent Volumes (PVs) ahead of time. These PVs are available for users to claim through Persistent Volume Claims (PVCs).

![c5694c35-f557-46a8-b8a6-9dcbe71558b0.png|405](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/c5694c35-f557-46a8-b8a6-9dcbe71558b0.png) [^37]

Here's a simple breakdown:

1. **Administrator Creates PVs**: An administrator manually creates and defines PVs in advance. These PVs specify the storage details, like size and type.

1. **PVCs Request PVs**: When an application needs storage, it creates a Persistent Volume Claim (PVC) to request storage.

1. **Matching**: The PVC is matched with one of the pre-created PVs that meet its requirements.

1. **Binding**: Once matched, the PVC is bound to the PV, and the application can use the storage.

Think of static provisioning as preparing a bunch of storage units ahead of time, ready to be claimed and used by applications when needed.

\

<mark style="background-color:#F3DE6C;">**Dynamic Provisioning**<!-- {"backgroundCycleColor":"14"} --></mark>

**Dynamic provisioning** automates the creation of Persistent Volumes (PVs) when a Persistent Volume Claim (PVC) is made. This approach uses **StorageClasses** to define the parameters for provisioning storage dynamically.

![b57faf5c-78d2-4863-aa04-809723be00a2.png|453.9814758300781](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b57faf5c-78d2-4863-aa04-809723be00a2.png) [^38]

Here's a simplified breakdown:

1. **Storage Class**: An administrator defines a Storage Class, which specifies the type of storage (e.g., fast, standard) and the provisioner (the component that creates the storage).

1. **PVC Request**: When an application needs storage, it creates a Persistent Volume Claim (PVC) and specifies the desired Storage Class.

1. **Automatic Provisioning**: Kubernetes dynamically provisions a PV that matches the PVC requirements using the specified Storage Class.

1. **Binding**: The PVC is automatically bound to the newly created PV, and the application can use the storage.

Think of dynamic provisioning as an on-demand service where storage units are created automatically whenever an application requests them, without manual intervention.

\

![542257d8-ea59-40bf-a065-02d8402ec911.png|1126](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/542257d8-ea59-40bf-a065-02d8402ec911.png) [^39]

\

Dynamic

![29bf1d20-8f28-484b-9dd4-8c1f632be0f2.png|1038](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/29bf1d20-8f28-484b-9dd4-8c1f632be0f2.png) [^40]

\

Below 2 steps are common for both static & dynamic provisioning

![5fe0548f-aec0-4623-92fb-b392ef1cab72.png|1029](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5fe0548f-aec0-4623-92fb-b392ef1cab72.png) [^41]

\

### **23Q. What are helm charts and how it's useful in Kubernetes?**<!-- {"collapsed":true} -->

What HELM do is keeping all the constant values separate and values which are going to change will maintain separately.

![ea2bb69a-0e63-4a35-a288-11d3873196e0.png|512.9976806640625](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ea2bb69a-0e63-4a35-a288-11d3873196e0.png) [^42]

Helm charts are like *templates* for Kubernetes applications. They help you package, manage, and deploy complex applications in a simple way. Instead of writing long configuration files for each service or app, Helm uses charts to automate the setup, making it easy to install, update, or roll back applications in Kubernetes. It saves time and reduces errors.

\

**Helm Charts** are like package managers (e.g., apt or yum) but for Kubernetes. They help you define, install, and upgrade complex Kubernetes applications in a simple, reusable way.

\

**How is it useful?**

- It automates the deployment of applications.

- Simplifies managing Kubernetes YAML files (like services, deployments, etc.).

- Makes it easy to version and roll back releases.

**Example:**

Imagine you want to deploy a web app with a database in Kubernetes. Instead of manually creating YAML files for the app, service, and database, you can use a Helm Chart.

![01499fc4-e090-4f0a-9126-139825c15920.png|970.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/01499fc4-e090-4f0a-9126-139825c15920.png) [^43]

\

\

### **24Q. Explain StatefulSet in Kubernetes?**

A **StatefulSet** in Kubernetes is used to manage stateful applications. Unlike Deployments (which are used for stateless apps), StatefulSets ensure that each pod has a unique, stable identity and persistent storage.

\

**Key Features:**

1. **Stable Network ID**: Each pod gets a stable DNS name (like `pod-0`, `pod-1`), which doesn’t change when the pod is restarted.

1. **Persistent Storage**: Each pod gets its own persistent volume, which stays the same even if the pod is deleted or recreated.

1. **Ordered Scaling**: Pods are created and terminated in an ordered, sequential manner.

**Example:**

Here’s a basic example of a StatefulSet managing a simple app:

![84a797e8-4eda-4a07-a32b-bea1579b13cb.png|834.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/84a797e8-4eda-4a07-a32b-bea1579b13cb.png) [^44]

**StatefulSet** creates 3 pods, each with a unique identity (like `web-0`, `web-1`, `web-2`).

Each pod gets its own persistent storage (`1Gi` each) using a `volumeClaimTemplate`.

\

**Now each POD will have each volume in  StatefulSet**

In StatefulSet PV & volumes won't delete (so that we can use the data present in the volumes for new pods)

### **25Q. Headless service in Kubernetes?**<!-- {"collapsed":true} -->

<mark>**Headless service is used for stateful applications,**</mark> **when you pick headless service instead of single IP address you will get all PODS IP address in same cluster. So that it is easy for replica to communicate with other replicas.**

\

<mark>For normal deployment we have ClusterIP but for StatefulSet we don't have ClusterIP(None)</mark>

![a4a6502e-153a-4325-b955-58a94c1bf793.png|1004.9884033203125](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a4a6502e-153a-4325-b955-58a94c1bf793.png) [^45]

\

it can communicate with background DB's

![917fc8a8-cd91-43b4-a995-f03dbc3409af.png|550](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/917fc8a8-cd91-43b4-a995-f03dbc3409af.png) [^46]

\

A **Headless Service** in Kubernetes is a service without a cluster IP. Instead of load-balancing requests across a set of pods, it allows direct communication with individual pod IPs. This is useful for stateful applications where you need to communicate with specific pods (like in a **StatefulSet**).

\

**Key Features:**

1. **No Load Balancing**: It doesn't distribute traffic across pods but returns the IP addresses of all the matching pods.

1. **Direct Pod Access**: Clients can connect to specific pods by their DNS names (e.g., `pod-0.my-service.namespace.svc.cluster.local`).

1. **DNS Resolution**: Each pod gets its own DNS entry, which helps in identifying and connecting to a specific pod.

**Example:**

A headless service looks like this:

![b64407a0-7b31-4b3d-9a26-219438efbd68.png|800.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b64407a0-7b31-4b3d-9a26-219438efbd68.png) [^47]

In this example:

- The service doesn’t have a `clusterIP`.

- It’s used to route traffic directly to pods by their individual DNS names rather than through a single service IP.

This is particularly useful for stateful apps where each pod has its own identity, such as databases or replicated services.

\

<mark>**Keeping DB's in Kubernetes is not recommended, (DB teams upgrades is difficult for DB's, end customer data (DB)we should not keep in Kubernetes)**</mark>

<mark>**In any interview if they ask if your MYSQL & other DB are running in Kubernetes? tell them NO**</mark>

\

### **26Q. RBAC in Kubernetes?**<!-- {"collapsed":true} -->

**RBAC (Role-Based Access Control)** in Kubernetes is used to control who can perform specific actions on resources (like pods, services, etc.) within a cluster. It allows you to define **roles** and **permissions** for different users or applications.

\

**Key Concepts:**

1. **Role**: Defines a set of permissions (e.g., can create pods, can delete services).

1. **RoleBinding**: Assigns a role to a user or group, granting them the permissions defined in the role.

1. **ClusterRole**: Similar to Role but applies cluster-wide (not just in a specific namespace).

1. **ClusterRoleBinding**: Binds a ClusterRole to a user or group cluster wide.

**Simple Example:**

Let’s say we want to give a user named `dev-user` permission to create pods in the `dev` namespace.

1\. **Role**: Define what actions are allowed.

![94798b8e-e33d-4a38-ab53-89d7a648d7b2.png|694.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/94798b8e-e33d-4a38-ab53-89d7a648d7b2.png) [^48]

\

**Explanation:**

- The **Role** `pod-creator` allows creating pods in the `dev` namespace.

- The **RoleBinding** ties this role to `dev-user`, giving them the ability to create pods in that namespace.

This helps control access in a fine-grained, secure manner within Kubernetes clusters.

\

![1e850338-a0f3-4bec-80d4-774363ee0d43.png|399](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/1e850338-a0f3-4bec-80d4-774363ee0d43.png) [^49]

![cf6c20fa-fca5-482a-b7c3-e20974863024.png|506](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/cf6c20fa-fca5-482a-b7c3-e20974863024.png) [^50]

\

for trainees

![e0694915-9639-46fe-9446-baf5eab6f59d.png|765.995361328125](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/e0694915-9639-46fe-9446-baf5eab6f59d.png) [^51]

\

![ddbed138-cd4e-4b1d-bf9e-f5a94b1f9078.png|302](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/ddbed138-cd4e-4b1d-bf9e-f5a94b1f9078.png) [^52]

\

Authentication - For TCS gate entry we have entry access

Authorization - We have ODC access to particular project, not for all ODC's

\

![17d36f9c-f911-43aa-9523-e9a34a3d22e5.png|862](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/17d36f9c-f911-43aa-9523-e9a34a3d22e5.png) [^53]

If we are using on-premises then we use Microsoft AD

CyberArk

\

\

\

### **27Q. Horizontal POD Autoscaling (HPA) in Kubernetes?**<!-- {"collapsed":true} -->

![5c519f72-3c1d-4e9d-b21b-577e20a06022.png|1200](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/5c519f72-3c1d-4e9d-b21b-577e20a06022.png) [^54]

![07363199-4af8-4fb5-b44e-2400528d949d.png|731](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/07363199-4af8-4fb5-b44e-2400528d949d.png) [^55]

\

**Horizontal Pod Autoscaling (HPA)** in Kubernetes automatically adjusts the number of pod replicas in a deployment, replica set, or stateful set based on observed resource usage (like CPU or memory) or custom metrics. It ensures that your application scales up when demand increases and scales down when the load decreases.

\

**How HPA Works:**

- **Monitors Resource Usage**: HPA checks metrics (like CPU utilization).

- **Adjusts Pod Count**: Based on predefined thresholds, it increases or decreases the number of running pods to maintain the desired performance.

**Example:**

Let's create an HPA for a deployment that scales based on CPU usage.

1\. **Deployment** (for the application):

![b05cf16d-00a4-444a-8146-cd580c28d25e.png|627.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b05cf16d-00a4-444a-8146-cd580c28d25e.png) [^56]

\

2\. **HPA** (to autoscale based on CPU):

![6422a658-b332-4283-ba49-7f06543ecebf.png|707.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/6422a658-b332-4283-ba49-7f06543ecebf.png) [^57]

\

**Explanation:**

- The **Deployment** starts with 2 replicas of `my-app`.

- The **HPA** monitors the CPU usage of the `my-app` pods. If CPU utilization exceeds 50%, more pods are created (up to 10). If the load drops, pods will be reduced (down to 2).

This ensures efficient resource usage, allowing the app to handle varying workloads without manual intervention.

![7ec1e1a8-af81-45af-a965-2fc120f694ea.png|896.99072265625](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/7ec1e1a8-af81-45af-a965-2fc120f694ea.png) [^58]

### <mark style="background-color:#FFFFFF;">**28Q.Horizontal scaling vs vertical scaling?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

**Vertical scaling** - We can increase CPU, RAM, HD

**Horizontal scaling** - Increases no of PODS based of traffic

![3a502df7-46e8-41ba-ac05-3516f74ad48c.png|631](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/3a502df7-46e8-41ba-ac05-3516f74ad48c.png) [^59]

### **29Q. Ingress controller in K8?**<!-- {"collapsed":true} -->

**You might wonder while we already have `LoadBalancer` as service type, why do we even need Ingress?**

1. Well, if you want to expose more than one `service` to the internet, If you use service type `LoadBalancer`, Your cloud provider will create one load balancer for each service, and that's too expensive.

1. So we use ingress as a wrapper to those services and use only one cloud load balancer.

1. Ingress sits between service and Internet and redirects every request to service based on ingress rules.

![91b54575-7b03-4d32-b1f6-81f810d1cc64.png|585.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/91b54575-7b03-4d32-b1f6-81f810d1cc64.png) [^60]

\

An **Ingress Controller** in Kubernetes is like a traffic director that manages external access to your services within a Kubernetes cluster. It routes incoming requests from outside the cluster to the appropriate services inside the cluster based on rules you define.

\

**Example:**

Imagine you have two services in your Kubernetes cluster:

1. A web application (`web-app-service`)

1. An API service (`api-service`)

You want users to access these services using the same domain, but with different paths:

- `http://yourdomain.com/app` should go to `web-app-service`

- `http://yourdomain.com/api` should go to `api-service`

Here's how you can set this up with an Ingress Controller:

1. **Deploy an Ingress Controller** (e.g., NGINX Ingress Controller) in your Kubernetes cluster.

1. **Create an Ingress Resource** with rules to route traffic to the appropriate services.

Here's a simple Ingress Resource YAML configuration:

![717f4861-ba40-42e1-bc5d-044fb56cc4fc.png|709.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/717f4861-ba40-42e1-bc5d-044fb56cc4fc.png) [^61]

\

In this example, the Ingress Controller will route requests to

`http://yourdomain.com/app` to the `web-app-service`, and requests to 

`http://yourdomain.com/api` to the `api-service`.

It's like having a smart receptionist who directs callers to the right department based on the number they dial.

\

**Key Points:**

- **Ingress** is like a map that tells the system where the traffic should go.

- **Ingress Controller** is the engine that makes the routing happen.

- Without an Ingress Controller, an Ingress resource alone won’t do anything.

\

![ffd1731d-4432-46c7-a3ea-aafe071363c0.png|1180](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ffd1731d-4432-46c7-a3ea-aafe071363c0.png) [^62]

\

### <mark style="background-color:#FFFFFF;">**30Q. Deployment strategies in K8?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

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

\

### **31Q. <mark style="background-color:#FFFFFF;">EKS Upgrade using Blue/green?<!-- {"backgroundCycleColor":"11"} --></mark>**<!-- {"collapsed":true} -->

![b516011f-340f-45ee-a4b2-17d99ee76fb6.png|1090](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/b516011f-340f-45ee-a4b2-17d99ee76fb6.png) [^63]

\

### **32Q. Taints & tolerations in k8?**<!-- {"collapsed":true} -->

In Kubernetes, **Taints** and **Tolerations** are mechanisms used to control how **Pods** are scheduled to **Nodes**. They allow you to ensure that certain pods are either kept away from or are allowed on specific nodes.

\

**1. Taints (applied to Nodes)**

A **Taint** is applied to a node, marking it as unsuitable for some pods unless the pod has a matching **toleration**. Taints effectively say, "Don't schedule pods here unless they can tolerate this taint."

- **Taint structure**: `key=value:effect`

    - `key`: A label or reason for the taint.

    - `value`: A value to explain the condition.

    - `effect`: What will happen if the pod doesn’t tolerate the taint (e.g., `NoSchedule`, `PreferNoSchedule`, `NoExecute`).

**Example of adding a taint to a node:**

```
kubectl taint nodes <node-name> key=value:NoSchedule
```

This will prevent any pods that don't tolerate the `key=value` taint from being scheduled on this node.

\

**Effects of taints:**

- `NoSchedule`: Pods that don’t tolerate this taint will not be scheduled on the node.

- `PreferNoSchedule`: Kubernetes will try to avoid scheduling pods that don’t tolerate the taint, but it’s not guaranteed.

- `NoExecute`: Existing pods that don’t tolerate this taint will be evicted, and new pods won’t be scheduled.

\

**2. Tolerations (applied to Pods)**

A **Toleration** is applied to a pod, allowing it to be scheduled on nodes that have matching taints. It’s like saying, "This pod can handle the condition described by the taint."

\

Example of a toleration in a pod spec:

![588b55ad-33d5-49bf-8097-1a8b408dd865.png|803.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/588b55ad-33d5-49bf-8097-1a8b408dd865.png) [^64]

\

This allows the pod to tolerate the `key=value:NoSchedule` taint and be scheduled on nodes with that taint.

\

**Taints and Tolerations in Action:**

- **Scenario 1: Reserve Nodes for Specific Workloads** You can taint certain nodes to ensure only specific workloads (like GPU-intensive jobs) are scheduled there. Only pods with matching tolerations can run on those nodes.

    - **Taint** the node: `kubectl taint nodes gpu-node gpu=true:NoSchedule`

    - **Tolerate** it in the pod spec:

![92902108-ecfc-4949-a8c1-ae2be66625ad.png|747.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/92902108-ecfc-4949-a8c1-ae2be66625ad.png) [^65]

\

**Scenario 2: Evict Pods Under Certain Conditions** If a node is undergoing maintenance or is in a bad state, you can taint it with `NoExecute`. Any pod without a matching toleration will be evicted.

```
kubectl taint nodes <node-name> maintenance=true:NoExecute
```

- Any pod not tolerating `maintenance=true` will be evicted immediately.

**Key Concepts:**

- **Taints** are applied to nodes to repel pods.

- **Tolerations** are applied to pods to allow them to tolerate (and be scheduled on) nodes with specific taints.

By using taints and tolerations, you can fine-tune how workloads are distributed across your Kubernetes nodes.

### **33Q. affinity and anti-affinity in k8?**<!-- {"collapsed":true} -->

In Kubernetes, **Affinity** and **Anti-Affinity** are mechanisms used to influence how **Pods** are scheduled on nodes based on node or pod characteristics. These allow for better control over the placement of pods, either to keep them together or apart for performance, reliability, or resource management purposes.

\

1\. **Affinity**

**Affinity** rules specify that a pod should be scheduled **on the same node** or close to other pods or nodes with certain labels or characteristics. This can improve performance by reducing network latency or optimizing resource usage.

There are two types of affinity in Kubernetes:

- **Node Affinity**: Controls which nodes a pod can be scheduled on, based on labels applied to nodes.

- **Pod Affinity**: Controls which pods a pod should be scheduled near (on the same node or within the same topology domain like a region or zone).

**Node Affinity**

Node affinity allows you to schedule a pod on a specific set of nodes based on their labels.

Example: Node Affinity

In this example, we want to ensure that a pod runs only on nodes labeled as `disktype=ssd`.

![2f3d91be-d3be-4ff8-904d-98a32130fb73.png|801.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/2f3d91be-d3be-4ff8-904d-98a32130fb73.png) [^66]

- **`requiredDuringSchedulingIgnoredDuringExecution`**: This means the scheduler must place the pod on a node that meets the affinity rules, but once the pod is running, any changes to the node (like removing the label) won’t affect the pod.

There is also **`preferredDuringSchedulingIgnoredDuringExecution`**, which gives preference to certain nodes but doesn’t strictly require it.

\

**Pod Affinity**

Pod affinity allows a pod to be scheduled on the same node or in the same zone as other pods that match specific labels. It’s useful when you want pods to be co-located to reduce network latency or improve communication between them.

\

Example: Pod Affinity

In this example, the pod will be scheduled near other pods with the label `app=my-app`.

![ef8f275b-4b45-4be9-9c87-f1d657209189.png|685](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ef8f275b-4b45-4be9-9c87-f1d657209189.png) [^67]

\

- **`topologyKey`**: Defines the scope of the affinity rule (e.g., `kubernetes.io/hostname` for same node, `failure-domain.beta.kubernetes.io/zone` for same zone).

This ensures the pod is scheduled on the same node as other pods with the `app=my-app` label.

\

2\. **Anti-Affinity**

**Anti-Affinity** rules specify that a pod should **not be scheduled** near other pods with certain characteristics. This helps with spreading out pods to avoid overloading a single node, zone, or other failure domains. It’s commonly used for high availability.

\

**Pod Anti-Affinity**

Pod anti-affinity ensures that pods with certain labels are **not scheduled on the same node** (or within the same zone, rack, etc.). This is useful for ensuring that replicas of an application are spread out for redundancy.

\

Example: Pod Anti-Affinity

In this example, we want to prevent two pods with the label `app=my-app` from being scheduled on the same node:

![02f0c7dc-c70b-44ce-b0bc-f86b915a6bec.png|720](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/02f0c7dc-c70b-44ce-b0bc-f86b915a6bec.png) [^68]

**Key Concepts**:

- **Node Affinity**: Controls pod placement based on node labels.

    - Example use: Schedule pods only on nodes with SSDs or GPU resources.

- **Pod Affinity**: Controls pod placement based on the presence of other pods.

    - Example use: Schedule pods that need to communicate closely on the same node (e.g., for performance).

- **Pod Anti-Affinity**: Ensures that certain pods are not scheduled together to increase reliability and availability.

    - Example use: Spread replicas of the same application across different nodes to avoid single points of failure.

These rules provide fine-grained control over pod scheduling, helping optimize performance, reliability, and resource utilization in Kubernetes clusters.

### **34Q. explain Prometheus monitoring tool for k8?**<!-- {"collapsed":true} -->

**Prometheus** is a powerful open-source monitoring and alerting toolkit designed for reliability and scalability. When used in Kubernetes, Prometheus can monitor the cluster and its components, as well as the applications running inside it. Prometheus collects and stores metrics, performs queries, and triggers alerts based on specified conditions.

\

Key Concepts of Prometheus in Kubernetes:

1. **Metrics Collection**: Prometheus collects metrics from various components in the Kubernetes cluster, such as the API server, nodes, and applications. Metrics include data like CPU usage, memory consumption, disk I/O, and more.

1. **Service Discovery**: Prometheus uses Kubernetes' service discovery mechanisms to dynamically find the components to monitor. It automatically discovers pods, nodes, services, and endpoints based on labels.

1. **Data Storage**: Prometheus stores metrics in a time-series database. Metrics are stored in key-value pairs with a timestamp. This makes it easy to query historical data and analyze trends.

1. **PromQL (Prometheus Query Language)**: This is the query language used by Prometheus to perform real-time queries on the collected metrics. You can use PromQL to extract specific metrics, create graphs, or generate custom alerts.

1. **Alerting**: Prometheus can trigger alerts when certain conditions are met (e.g., when a pod exceeds a certain CPU usage threshold). It integrates with **Alertmanager**, which can send notifications through channels like Slack, email, or PagerDuty.

1. **Visualization**: Prometheus integrates with **Grafana**, a popular tool for creating dashboards. With Grafana, you can visualize the metrics collected by Prometheus, create custom dashboards, and monitor the health of your Kubernetes cluster.

\

### **35Q. Kubernetes Networking?**<!-- {"collapsed":true} -->

-  Kube DNS makes an entry whenever a new service is created, thus helping name resolution.

-  Ingress in Kubernetes can be used as a wrapper for services.

-  It is recommended to create ingress if you are planning to expose more than one service to the Internet.

-  Use Ingress with Service type=LoadBalancer, so that it'll help you create only one Load Balancer even though you have multiple Services to expose.

\

### **36Q. Labels vs Selectors?**<!-- {"collapsed":true} -->

**Labels**:

- **Definition**: Labels are key-value pairs attached to Kubernetes objects, like pods.

- **Purpose**: They help identify, organize, and categorize resources.

- **Example**: `app: frontend`, `env: production`.

**Selectors**:

- **Definition**: Selectors are queries or filters used to identify and group resources based on their labels.

- **Purpose**: They enable you to manage and select a specific set of resources that match certain criteria.

- **Example**: A label selector could be `app: frontend` to select all pods with this label, or a set-based selector like `env in (production, staging)` to select pods with `env` as either `production` or `staging`.

In short:

- **Labels** are attributes you assign to objects.

- **Selectors** are used to filter and group objects based on those labels.

# <mark style="background-color:#F8914D;">**Kubernetes scenario-based questions**<!-- {"backgroundCycleColor":"24"} --></mark>

### **1Q. Understanding Kubernetes CreateContainerError?**<!-- {"collapsed":true} -->

**CreateContainerConfigError vs. CreateContainerError**

While these two errors may sound alike, they happen at different stages in the container lifecycle:

\

**CreateContainerConfigError:** This happens when something is wrong with your Pod’s configuration. Think of it as a setup issue that stops the container from being created.

**CreateContainerError:** This occurs later, during the actual creation of the container. The setup might be correct, but the container fails to start for other reasons.

\

**CreateContainerError:**

You can detect the error by running the kubectl get pods command:

![b4c6540a-c62f-4fba-b90d-216292076007.png|726.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b4c6540a-c62f-4fba-b90d-216292076007.png) [^69]

\

When starting a container, Kubernetes goes through the initialization process, where it pulls the image, allocates resources, and mounts volumes. If any of these steps fail, Kubernetes triggers a`CreateContainerError`.

![809093d9-93d8-4bbc-9dd2-de6985b7b455.png|694.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/809093d9-93d8-4bbc-9dd2-de6985b7b455.png) [^70]

\

**Common Causes for CreateContainerError:**

![2e8241b7-cc6a-4a8d-b60b-a4edfaa2f60c.png|701.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/2e8241b7-cc6a-4a8d-b60b-a4edfaa2f60c.png) [^71]

\

**How to Troubleshoot CreateContainerError:**

**1. Inspect Pod Details**

Start by inspecting the Pod to get detailed insights into the container creation failure:

\

```
kubectl describe pod techops-examples
```

\

We can see that the container is in the “**Waiting**” state with the reason listed as`CreateContainerError`

![acfd78f7-d238-4b82-8241-7c487dc11571.png|668.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/acfd78f7-d238-4b82-8241-7c487dc11571.png) [^72]

\

**2. Retrieve Logs**

Use the following command to check the logs of the Pod’s container and find more details on why the container failed to start:

```
kubectl logs techops-examples
```

If the container has not yet been created, you may see an error indicating that there are no logs available.

\

\

**3. Analyze Recent Pod Events**

Use the `kubectl get events`command to view recent events related to the Pod and identify any specific reasons for the`CreateContainerError`.

```
kubectl get events --field-selector involvedObject.name=techops-examples
```

**Example Output:**

![bd525f04-69f3-44a3-a940-d74591459815.png|819.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/bd525f04-69f3-44a3-a940-d74591459815.png) [^73]

**4. Validate Resource Availability**

Check if there are enough resources available (CPU and memory) on the node to run the container. Use:

```
kubectl top nodes
```

\

**Fixing CreateContainerError:**

\

**1. Fix Image Issues**

If the image specified is incorrect, ensure the correct image is pulled by providing a valid image name and tag:

![24dd3cef-d551-4a1d-b3eb-30fbdd1f9a60.png|813.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/24dd3cef-d551-4a1d-b3eb-30fbdd1f9a60.png) [^74]

If the error is caused by a missing command, add a valid entrypoint to the image.

\

**2. Adjust Resource Requests**

If the container is failing due to insufficient resources, adjust the resource requests and limits in the Pod configuration to fit the available resources on the node:

![f4050c46-c4b0-4382-b821-927d878298c4.png|730](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/f4050c46-c4b0-4382-b821-927d878298c4.png) [^75]

\

**3. Correct Volume Mounts**

If the issue is with missing or misconfigured volumes, verify that the correct PersistentVolumeClaim (PVC) is available and referenced properly:

![6a7f8e34-0409-4c3f-8a79-0ab94b96be14.png|718.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/6a7f8e34-0409-4c3f-8a79-0ab94b96be14.png) [^76]

in this example, ensure that the`data-pvc`exists in the namespace and that it is correctly configured.

\

**4. Check Container Runtime**

If there is a problem with the container runtime, review the kubelet logs on the node where the Pod is scheduled. Run the following command on the node:

```
sudo journalctl -u kubelet
```

Look for errors related to the container runtime and restart the kubelet or runtime service if needed.

\

**Running into a CreateContainerError can be frustrating, but it usually comes down to checking your image, resources, volume mounts, and runtime environment.**

\

### **2Q. Kubernetes RunContainerError Explained?**<!-- {"collapsed":true} -->

The `RunContainerError` indicates that the container couldn’t initiate. When you see this error, it means the application inside hasn’t started because the container itself encountered a failure before it could begin loading the application.

![5118e85b-6c3c-4421-9f7a-41cbd2b049b7.png|650.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5118e85b-6c3c-4421-9f7a-41cbd2b049b7.png) [^77]

\

| |
|-|
|If your pod status shows `RunContainerError`, it’s often due to:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^78]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**How to Fix RunContainerError:**

| |
|-|
|**1. Check Pod Events for Detailed Errors**<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Start by describing the Pod to check for specific error events.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Look for any error messages in the "Message" field, such as `permission denied`, `file not found`, or `invalid command`.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|In the below example, the error `permission denied` indicates a file permission issue with `/app/start.sh`.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![a98cfcf5-8cfe-43f7-9ae2-f954a4d931b4.png|633.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/a98cfcf5-8cfe-43f7-9ae2-f954a4d931b4.png) [^79]

\

**2. Inspect Container Logs**

| |
|-|
|If the container started briefly before failing, check logs for any application-specific error messages.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|If you see errors like `Permission denied` or `Command not found`, it points to issues with permissions or command configurations in the container.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![7608df8f-9c50-41e2-9f27-a9b7a3571279.png|692.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/7608df8f-9c50-41e2-9f27-a9b7a3571279.png) [^80]

\

**3. Verify Volume Mounts**

| |
|-|
|Check that any referenced [ConfigMaps](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdbRfElTkEucsYD3-2FZPpJ40M8P3zPoA4P7N0U2-2Fgj-2BQi3Dfk5sqTdlXGZpkgqnNu9I1dZKPlTDjn8PuOm-2FznXXh-2FfgO5H0tMfzGx-2F0KgRiTqw4CrCVmYo957m2nsr7PB2D0SmYaPi38yfawXTjxCI5Lthj22BIBVXHxG7Xy5g9PJFwtmDrdVgTSWjtTEVUiGiCXEiN8OQRdqBX65DiqmEbctx8atqo5Wmn2CSmE4huKO1gUyGGIXBmMC77m0cGaMV6s9ioV6ghEVT8ujfSM3ew-2Fy116y_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BjaHND7Q7q19Gr09UT2PH623IlOraGpalaZyo7O9i1vNUpSj2Q1S2Gm4tqK0yRj1iTBQxsF038mbPzbdRjmBY9gAO9C2lLLeVopA0WnFtTIlZ-2F7AGTIfhpS4Ja5kpRLyU2v74gtHzPlVJLUjJypRhbHT3i8kc7jftzT9LzmzxEwBlNJ-2FFFIaVOwUuttMpjdp525qknjte2-2BvHsynaN5IEXMP1Yh0tEgceLsdkCODUbFmgb6Wyk-2FQmzbUbVIktlJK3LTtkEvWc3IrP8C-2BkaDDeAelpjLnE8J9rvVa05OPvo2gCDByzFe0PKyndMqAu8AtHHBZrTlZeLAFtFuUQWOnAmMCKkaTECA5ksqsVZbsClcyiXkwjuoAk4YtD47ItfoQO), [Secrets](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdbRfElTkEucsYD3-2FZPpJ40MPz982QMXOC7JR-2FXrbemaZP-2FDcUzYLS1-2F3Yz8eYp0In-2BG3GUKflPUshloMldYhsJz6NJkAtzLiKdSYzsY3WcXhLBrmVDrWGU3wTC8CzkEDcFJUY-2FNwsaDBt18yFKrCdBqxNmVZu6Y-2BauVOeUQdxIo4NcXpZYEUvE-2FHdoGxSlHawX4imR8UvQdHKqTqR0oxF2IGbNNNJrF7gcrFJnE8sacDl7E-2BmrJ6i9gYrHTMCR5qYI-3DAbzg_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BjaHND7Q7q19Gr09UT2PH623IlOraGpalaZyo7O9i1vNUpSj2Q1S2Gm4tqK0yRj1iTBQxsF038mbPzbdRjmBY9gAO9C2lLLeVopA0WnFtTIlZ-2F7AGTIfhpS4Ja5kpRLyU2v74gtHzPlVJLUjJypRhbHT3i8kc7jftzT9LzmzxEwBlNJ-2FFFIaVOwUuttMpjdp525qknjte2-2BvHsynaN5IEXMP1Yh0tEgceLsdkCODUbFn0Uy1MdOvYnWtqSJa3T7vSLuf3j5wO4mPSmOvu7FzvZ5MFI327d4YHAzluaGjkZyUl1bMSgtGzIkNwTW8EiXbZ6ys8yGhwvzgIPujlRMTMO-2BuyaJMQx2NndF8Z7C8dyH96obigxVORIOGdkiyAwQpn), or [PersistentVolumes](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdYDEG2O23DlumNLJfc0FLzXH9beJrChUX4OMD-2B21aD-2Byw8PaBOExu32p4Wzhpp2hxM1-2FlK-2Fp8DNjoWg9xb2QN9BOS67B-2BhQlI-2BBVGP53WDk3Y2U1F6gdU6-2FFk5i-2FWxAlZrl1RObgyysNXWw-2B-2BWEqm2oBghrG3X8Txbr-2FXZJWblU7PLZRzW5p2v-2FAq1NikNpWXbIWzl-2F26byL-2BglKOre-2BnlUZHQu55FKlhjjZQMdfBHvzNQzqHNo-2BYGbufcpcg8q2YfBzblYJZQmdl1V5ABbtUJOL8ik_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BjaHND7Q7q19Gr09UT2PH623IlOraGpalaZyo7O9i1vNUpSj2Q1S2Gm4tqK0yRj1iTBQxsF038mbPzbdRjmBY9gAO9C2lLLeVopA0WnFtTIlZ-2F7AGTIfhpS4Ja5kpRLyU2v74gtHzPlVJLUjJypRhbHT3i8kc7jftzT9LzmzxEwBlNJ-2FFFIaVOwUuttMpjdp525qknjte2-2BvHsynaN5IEXMP1Yh0tEgceLsdkCODUbFnUU1pS7OIfB-2BEe-2BCc98-2BtxUbdFFF01aGY8k4MAQPIoSOpcMPm7pQaaTHHNLpwojJzSTfKlnFJ8rVh6VJgg1tP80Zxl8ysWNDDhA7Keb0RULaAFqqCBj7rSc9i0TL16bXoqLoXUm5KhLBwrCJ6zGvze) are correctly defined and available.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|If you receive `Error from server (NotFound)`, the ConfigMap or Secret is missing, causing `RunContainerError`.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![b01b1c1d-5355-4d1f-84f7-b6c11ebb973e.png|680](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b01b1c1d-5355-4d1f-84f7-b6c11ebb973e.png) [^81]

\

**4. Check Commands and Entrypoints**

| |
|-|
|Verify the [command and args](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3Yicjdb4DpoM7ZkYT1-2FkIgchkXU9dleIRSN6Sh1rqT1-2FthM7FhDoHe50NjkVX-2BjMdje2TPy5DCjETfTTbzwaOPy3VmiJuAfTJK975qdpFu80-2FlT9OO1DELEZpGgdwcnBcCMezJ62HvvokopVF7Tm5W2kBgNrHu5CJSJzRprsu8BHygSPMUsvY9juE0cW8jojYM9EuoFhs95FusVzDo7inb2fLEPem25A8clvFgaEpdsrX36yIEybUr34n97ZrSSjG-2FXxLoy22v-2F7Y9-2F6HjoBldRP1Ed-2FLu4VJQsD9RxxpTO6V2LBzRjaeKIVhYfGNqb0ntM457U-3DezwJ_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BjaHND7Q7q19Gr09UT2PH623IlOraGpalaZyo7O9i1vNUpSj2Q1S2Gm4tqK0yRj1iTBQxsF038mbPzbdRjmBY9gAO9C2lLLeVopA0WnFtTIlZ-2F7AGTIfhpS4Ja5kpRLyU2v74gtHzPlVJLUjJypRhbHT3i8kc7jftzT9LzmzxEwBlNJ-2FFFIaVOwUuttMpjdp525qknjte2-2BvHsynaN5IEXMP1Yh0tEgceLsdkCODUbFkRqqVe8-2BrkEjsEWK3SGdzT5aQNktZ4RcueAaY6Ufvi-2F0TlDoF2R-2FOzUO4YjWQFlfhiEJ9PaUBgqPsgaRUJQvGZFFgV13HM58I0r36nhq8TKd-2FvDuT0m1ggayBUZnf0BeMUXY-2BiFMvMqV1ajplJRVhe) fields in your Pod’s specification. If these commands or paths are incorrect, the container won’t start.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Ensure the command path (`/app/start.sh` in this example) exists within the container and has the correct permissions.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![b34df2d7-c557-4299-b687-50a5c25c643e.png|695.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b34df2d7-c557-4299-b687-50a5c25c643e.png) [^82]

\

**5. Inspect Security Contexts**

| |
|-|
|Check if the [security context](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3Yicjdb4sqbS4heXKapxSw6rcQmh9FbGAvtrnwcn95Bd8R63rTKG3QJN8b-2B7xFhRFZC76aYU6bbUwszKaxdjqZyDH9L-2FG-2BUaELvstbS5VvN2dhvmsIhREJfwUCAvk5pomz9sKmesK4BTIMt3sKkc0YwKD1tPLmZN71Z3mHBbCK9j6cxSL961agGHxGFKJBJLygbmUhgIUCI6UXc0mIleONKWMYPa2qPJQaRVNRDNc3OF7t1S-2B0PTi22YevE2r1WcfkeytrpHPtKMMRTabqg-2FP5tFnV7s8k6X593deMedwTCGE9LAEg-3D-3D-YgL_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BjaHND7Q7q19Gr09UT2PH623IlOraGpalaZyo7O9i1vNUpSj2Q1S2Gm4tqK0yRj1iTBQxsF038mbPzbdRjmBY9gAO9C2lLLeVopA0WnFtTIlZ-2F7AGTIfhpS4Ja5kpRLyU2v74gtHzPlVJLUjJypRhbHT3i8kc7jftzT9LzmzxEwBlNJ-2FFFIaVOwUuttMpjdp525qknjte2-2BvHsynaN5IEXMP1Yh0tEgceLsdkCODUbFl8mE3IgqFjAkjZAtwUmX8GHbsPv9JYRDlw2peRxAPvcxzWwoHYtbA9cEyyBgpkri3jFHCGEQqxaMCVR7nc4IftKiQdsCg3pC6jbBS-2F-2Fi5awezkpK0ceUnrQxZVWTwaYlQTU3H-2BbQwJ19Dd-2B3dXSm2u) is properly configured in pod.yaml, as incorrect user/group settings can lead to permissions errors.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Verify that runAsUser and runAsGroup match the requirements of your container image.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![d83ecb17-fc70-46a1-9f1c-1f1ca5246110.png|714.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d83ecb17-fc70-46a1-9f1c-1f1ca5246110.png) [^83]

\

**6. Validate Image Permissions**

Some images require specific permissions to start. If needed, adjust the Pod’s [serviceAccount](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdZUwwC8V9-2F5EnOng-2FLvtGW7rvgCYnuk2rwqOCv6rO8tlwe8fiE8-2B3fh24Q2pKwcwsz1esvnL2AcKw4HCHX-2FB2DvkTbv78n-2BL0SAbCvTIZdHuUaWe-2BQnSLVbS-2FX9p1WhF3lcT8kYMTGvnsb2dnPF6UKSHc1znDO9l-2F07lDUim4XM40Bn1MeuivEn4O0lelIcVk1bUzdzCcvzNaXRaQ4DyUQpBBel3SvOu2YBsyNer4B6HjYn3rFbmKNoh7hQL6UJsdjedwJqK7OMJvjPOFpxNXXVvZTG_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BjaHND7Q7q19Gr09UT2PH623IlOraGpalaZyo7O9i1vNUpSj2Q1S2Gm4tqK0yRj1iTBQxsF038mbPzbdRjmBY9gAO9C2lLLeVopA0WnFtTIlZ-2F7AGTIfhpS4Ja5kpRLyU2v74gtHzPlVJLUjJypRhbHT3i8kc7jftzT9LzmzxEwBlNJ-2FFFIaVOwUuttMpjdp525qknjte2-2BvHsynaN5IEXMP1Yh0tEgceLsdkCODUbFmtXV-2BJuTqVdlnX3gpy6GQltXa5zlq8Id5zA8hdtIhtBOA3YO-2FVhSY4mtzuRvLyvWE-2F-2BvC8MbdllArzocq0nLP8BicNTmsYt4lEpPsjLuktTHUSxXgS-2F6FT57kbVOXJxLnczhDoOgJBXjriX5bclu-2FU) or security settings to meet these requirements.

\

**7. Check File and Directory Permissions**

| |
|-|
|If the error message includes “permission denied,” ensure that the relevant files and directories have the correct permissions.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|The file should have executable permissions (e.g., -rwxr-xr-x).<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![86babf8f-fb75-44d5-8fde-f94225c204f4.png|752.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/86babf8f-fb75-44d5-8fde-f94225c204f4.png) [^84]

### **3Q. Kubernetes Security Contexts Simplified?**<!-- {"collapsed":true} -->

- Kubernetes security contexts play a vital role in shaping the way your containers interact with their environment.

- They dictate critical settings, such as user privileges, filesystem access, and process controls, ensuring that containers run with the right level of isolation and security.

- Whether applied at the pod or container level, these contexts can drastically change the behavior of your applications.

- To keep things simple, let's break this down into three scenarios: pod-level, container-level, and a mix of both.

![9bada6e7-381d-413e-a8ae-7ea106c6c01c.png|707.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/9bada6e7-381d-413e-a8ae-7ea106c6c01c.png) [^85]

| |
|-|
|**Key Best Practices Settings To Know:**<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^86]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**Pod-Level Example:** In this case, all containers inherit security settings from the pod's security context. Everything here is applied uniformly, meaning both the app and log containers share the same security settings. Quick, easy, and straightforward.

![b9524fa4-a540-42d2-8843-f3d8c7f6b3a3.png|280.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b9524fa4-a540-42d2-8843-f3d8c7f6b3a3.png) [^87]

\

\

**Container-Level Example:** When you need more control, container-level security contexts allow you to tailor settings for each container.

Notice how the log-container has a different runAsUser and a custom Seccomp profile. This approach gives you fine-grained control, allowing different containers to operate under distinct security rules within the same pod.

![923462f1-3422-42ef-a016-814103a42c28.png|493.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/923462f1-3422-42ef-a016-814103a42c28.png) [^88]

\

**Pod + Container Level Example:** The hybrid approach lets you set defaults at the pod level, but containers can still override those defaults if needed.

Here, the app-container overrides the runAsUser field from the pod, but all other settings, like allowPrivilegeEscalation and readOnlyRootFilesystem, stick to the pod-level defaults. This provides flexibility without complicating the configuration.

![ace9f179-fa71-4169-8138-eac23a23f1d6.png|602.0023193359375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ace9f179-fa71-4169-8138-eac23a23f1d6.png) [^89]

\

**Overview of all Security Context settings and default values discussed so far.**

![f4a4dc38-b3ab-4ad8-97bf-525267a7c47e.png|762.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/f4a4dc38-b3ab-4ad8-97bf-525267a7c47e.png) [^90]

\

**In short, the security context is where Kubernetes gives you the power to control the safety of your workloads, whether you need broad or fine-tuned security across pods and containers.**

\

### **4Q. Epic K8s Tools for Solid Security Posture?**<!-- {"collapsed":true} -->

Kubernetes simplifies building and deploying apps via containerization, but securing your pods and containers is a different challenge.

\

Kubernetes provides basic IP-based security for each pod, but securing your clusters requires more—network policies, access policies for individual pods, RBAC, namespace access policies, and so on.

\

However, many open-source tools and plugins can help manage these issues.

![](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5d72e34d-e30e-42e4-8470-128ad7b8d0f8.png) [^91]

\

**1.** [**Kube bench**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CwTg6WbK-2FgHXZZ2BsztZCENRn0hssy9y-2F-2F7hs08pD3-2BFxGTE4QWgFqu-2FOisOexTCYnbSFaPgjidgR6fUnuU8NeJIahbej-2FIGutSETVnXgy1HASCRPqGlQ0tkbQNUShSwpXeuPtQOxuxEh-2B3kETVe5b0k-2FXFHiFxo7cCmZ-2FIABh8IVuX-2Fct4vnwZJ82rKTyfK-2FNqWMn-2BDnaBShG0QvOm5B9FCav-2BBNfKx7BVhmvt7gHDEd6TEijJ71iRPqHvs1bVnlcjeUWNOuUFhq9F76hb1ldI-3DgcSG_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VViTgmnxd8uhDRDxtcmSb1fmwnAhUQ7bAoikaeQkbV4RrXQScdLa-2BKTQLtCfI7kDiWTyK0JJGiUPYu-2Brt4l6IJvKun5Oa1dmj3nMSDK0PSzRli-2B5-2BWG-2F84-2B53XZ1FeNL8xp-2FH2gxS-2F1a6OWhm4fRozDH) 

| |
|-|
|[Kube-bench](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CwTg6WbK-2FgHXZZ2BsztZCENRn0hssy9y-2F-2F7hs08pD3-2BFxGTE4QWgFqu-2FOisOexTCYnbSFaPgjidgR6fUnuU8NeJIahbej-2FIGutSETVnXgy1HASCRPqGlQ0tkbQNUShSwpXeuPtQOxuxEh-2B3kETVe5b0k-2FXFHiFxo7cCmZ-2FIABh8IVuX-2Fct4vnwZJ82rKTyfK-2FPwAsySsKgPVOa7MV0VLP65xhORbxmY-2BrGM6eVcp6nAyqk03rVGLpmzLYR3psFEepTsEShxgRMc64y-2BbAhddDrw-3DFpzM_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVhCrn4i7VPbFmn5bScvDNDXtViyr5WoWzlnSGich-2BwU0Mn2ZcTZbkayXmipvwWHG88RrZw-2FjATrGPJU08OJlzGDbBKto930lvQhLLC9U-2F4syC8cXNxGyyGMB5tRVRVBySsIT2nrnBEWSktjQZdMesBQ) is a tool that checks Kubernetes clusters for compliance with security best practices, based on the [CIS Kubernetes Benchmark](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cy8xgPB1oBLVbka1cCA8FslnZK520O8vjZBKEzLVZMK4e91LknEUGCZliVIIUXjvpJ8dFPWaDIBT7e9M2icynvDx-2BdrYYGPhckmr-2F8tqkTNlLxB-2BeNxG2vm8GCn-2FgSir5gwCbNy-2FMn4RQiAJggbwvWfgBMCQnMzobmLvi-2BmELD36DCj3JFlnI-2B6KXKHUmm1Qk6Kva14KYeQRTt4q4D92STBBUnQ199fCNrqvI2oHPkRqDt9MguXiFRzRzxeVu0dgmX6jP8bUaGrT63V-2FaNDdCvI-3Dbxed_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVj4rjEWEVRTNr52yokOLrP4oTFXQwA-2BLwGJy-2BYDD-2BiuBONbjWudhQi92UW9jaZglykt3-2FGZjJweZqGOJl8W01FQbtFEXbH18Npfu-2BIiYOxZMJJlmLmCFkodqfpAQErAnavlqHckeA6eI0Ux5Wgyt5Ok). It helps identify vulnerabilities and misconfigs, providing detailed reports for remediation.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^92]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**2.** [**Stern**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2F-2Fm9oD-2FrmORlH5RUAG14B1FMrkpIOITbOMOcqBfe4FgiCjh377CVETLlSa-2FHytFK93iYLM00V4MHGgIvcB8xCK7x8TbbLMiP7gv6k1u45He8Ciel-2BmH6wj6tyljNnOgBL6uqgK9sNhOWzO1eqYbvtLB64v8yRQs17zC6iQTNeUhYuiYEU8oLMGD3blEHez9iNQdW8DfOIyKsZrTwLDJwzKcCFPckSKdC28sRxeErYmhItBq8smOU3373t6bmLVW6A-3D-3DzFp5_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVhiDV43PwBCQIbcXaip75-2FvH1GeKToPfyKU7RHQ7PoPDXFZ8A9K8iJDzvk3-2BAMWxeYmWBiYW1ogBZaXeclXs-2Fr0b0Pl4M1MkNXS3fm4fH8kCsMLnnCLpB3L2t1xmQ6Z-2FLB6ChpHz6-2F1LN6q-2FJ-2FIFIIU) 

| |
|-|
|[Stern](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2F-2Fm9oD-2FrmORlH5RUAG14B1FMrkpIOITbOMOcqBfe4FgiCjh377CVETLlSa-2FHytFK93iYLM00V4MHGgIvcB8xCK7x8TbbLMiP7gv6k1u45He8Ciel-2BmH6wj6tyljNnOgBL6uqgK9sNhOWzO1eqYbvtLB64v8yRQs17zC6iQTNeUhkmGcPRB89ZCDSxxSiQXyfEZFK-2FT-2ByqKKttQKGoVetS7Gffzch7e1KSKGLlGjp74abCJlAClZzSFjcl9rfH9nvw-3D-3D-bPj_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVjHufM-2BPrxUMpJV1hpI1JI-2FHfrd8-2FW6yITQBtNMRqBnihF-2BDC6EGUx8B81O7bTQTMlDt6EYXHclS55jwTabzC3o2B6NPdRewkQkPNZZrEzKgdPPBswG7ZMqnVhxchYSAGgqbm3UydRhe6kfZTer27xw) allows you to tail multiple pods and containers in Kubernetes, with color-coded log results for faster debugging.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^93]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**3.** [**Kubescore**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cyl7hHvn9qaayFE6A26mG7elv2Xnt12LOEyIIH7BKQiZwGaYBROpz9T2EObYmAzP-2FbOvipLNaGiJQ12ZP49s3jolx1ZjwjTRE-2F3Y2KDJlfWx6WMo3deYqFH-2Bp5IdDiK7k-2B6aM734-2B6Nh-2BT9Q-2BWyfZXUffLE-2FJq4yUDhJoCaVSOY1KJ-2B4QkOcsb53njWVJWQEDQY57gsHNdYe4ltmQqX5kD6HrAr1y96GYSQl8g4Dn3-2Baol-2FppA4OLD9HAPo4LwNwKg-3D-3DOaLH_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVj7JkBwqNZf2LVLHp8ac4oJqKo-2F2bn9ipKUdOWJJAypHnNgiR1sGqZnplGDFIw1KAhipEfhSW7AoZ-2BCgFI4yv5XuiSKZ2DE5ChpvY1Skm0TjCPC5y3wMjimHZI3eTmoBk9iapzPVQ52sBiiYdZkdpsh) 

| |
|-|
|[Kube-score](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cyl7hHvn9qaayFE6A26mG7elv2Xnt12LOEyIIH7BKQiZwGaYBROpz9T2EObYmAzP-2FbOvipLNaGiJQ12ZP49s3jolx1ZjwjTRE-2F3Y2KDJlfWx6WMo3deYqFH-2Bp5IdDiK7k-2B6aM734-2B6Nh-2BT9Q-2BWyfZXUffLE-2FJq4yUDhJoCaVSOY1KJ-2B4QkOcsb53njWVJWQEDbyG4Y7oYpZ3xTWz5KaWR7D22-2FdVOt7GPvAAZpHuscbnNpeV8izxIp1jDvagfW4UXA-3D-3DnwD2_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVjhGMJrK5SUbDKkBxeVH6jGnp2Gp6rGwVnf0ztmo1TSAiDDtr6Mh2cIGdKMm5YedS8mvMh3WIiyctVPkSohfnUcxonvcByytF6N08P6BGUHZf7G2Jpnor5c412X7xO-2B-2BhwVJVQUfASHdDYi-2FhsqPDO-2B) is a tool that performs static code analysis of your Kubernetes object definitions, checking them against best practices to ensure proper configurations.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^94]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**4.** [**Kubiscan**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C9BQDmNYwKjko-2BhTEs7dI3jmPP2YcZf9G8LFRZdUaI9OrMWN0J0kMZ-2BI-2BgWVd-2FgV0eT23Ox2ISND9aSja2paBeoiwu-2BhLaB7BpXF3ZYs8hKaIcfsI05CjlzTfd-2FpM8w8v3-2Bm-2B4zmZgB-2B3VekRtg7nFYwrcXsSH2kTIn-2BjIDnbbaxNUALBRZvAhrnuaQTg3H9nJUnwRmaY6YwSgwMLqI5Lq77LSUadTl27PRoyzyuBsO-2F8CdtQvJzHNTCaW0EA-2BEKog-3D-3DlVcS_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVhGuJ9EGLUR65XFLdjj40-2BfsuLG1GWibJ8DgvjnrIHiW5N-2F9NGKVqKZXP7lHGB0Rjv-2FWmxbqQkOdgvHuXIAAGvy-2Bil-2BjkRdmPzSBouKsT87BbyU3TKMcHwoBaW-2B9ddOKg3tRtmkzUKLXoVPNc5hXNkD) 

| |
|-|
|[KubiScan](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C9BQDmNYwKjko-2BhTEs7dI3jmPP2YcZf9G8LFRZdUaI9OrMWN0J0kMZ-2BI-2BgWVd-2FgV0eT23Ox2ISND9aSja2paBeoiwu-2BhLaB7BpXF3ZYs8hKaIcfsI05CjlzTfd-2FpM8w8v3-2Bm-2B4zmZgB-2B3VekRtg7nFYwrcXsSH2kTIn-2BjIDnbbaxNUALBRZvAhrnuaQTg3H9nDxO16PRNezRsRXjBM0ZwCer4moMcWuQSt11oF5-2FZU9w8cSLo6kIlOAXZdmdrSMDIg-3D-3DlKhd_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVj-2B9pZleMlTPSM7kqbIXFUleWKApXONd52y7fg7f7DJF-2BpvtYVMQu1z7mWKa2mecB9J9RJ26pAISh99ek2OigRonyEzHxiwd1GAjAmYdrUOYzjh9CwIKUsTfLfj6U5L9-2BPg0hvsI7fRe4hDURBsX7bb) is a tool for scanning Kubernetes clusters for risky permissions in the RBAC authorization model.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^95]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**5.** [Rakkess](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C6-2Fq5ob0uCCfdx0ogv-2FXbyMJPc2FUSAh-2BBmru4NxD5BmI9BWkdzOqRJxGLxNpw8z9JSTfINBq4qCGS9pXD1xQ2SFGMcUlynjyzvvECl9mUEGoWRo-2BGDKmJ3N82bVZdS6YwazqmUlAtC94PwYOV9AFpsdm0aHeG4pohSyyJ91Q1g3mK-2FYGn5E6FeWb0VHMZDznfIDiZnVV47iEjmOb-2FPrzqNq9apnEgZjIBrsYL3moLdmvqON7ak7qv2yduYkpKM8i6kpFkmgqZ9y46vrqX5IosY-3DnDli_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVhRKQzXLRs7uReLk-2F05EJcyNkrJJmwWgGjSYC0qKeiK39m8Uy26ZFPtYrjfyylAiGP-2BzE-2FKNGh-2FVufOXHDTccwlLPJFpNFS7IGgamylYc4Cz4atUAB5Oe3u97ZpfVsnz6GRRV0yT-2FS-2Fo1iNHuDXRTrM) 

| |
|-|
|[Rakkess](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C6-2Fq5ob0uCCfdx0ogv-2FXbyMJPc2FUSAh-2BBmru4NxD5BmI9BWkdzOqRJxGLxNpw8z9JSTfINBq4qCGS9pXD1xQ2SFGMcUlynjyzvvECl9mUEGoWRo-2BGDKmJ3N82bVZdS6YwazqmUlAtC94PwYOV9AFpsdm0aHeG4pohSyyJ91Q1g3mK-2FYGn5E6FeWb0VHMZDznYdQ-2BQrF-2F2sO9PsfSxMm61nR92taP055cNaYowfflqMRV5dDbGqK-2BlMc9HrGuj2YArWMWvn8-2BSyxoCrmbqJdnUo-3DSkW__uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B7YB7gnhmXey-2FPVRuvGrvMVMRM6kb-2FSAO-2BTF2n-2BZmMTd2mvJ6vXNfQK3HKF8rDXHj6ZFcr-2Fa2a3yZgyeTi31JYgq7bIjG8QGMARkNk1-2BorCJgf4I3MDlHF-2F4DIu5jyA6kWqzzRQ9YZSz69UDcgAzNk3g2JlgxTEEtDSXePt6FERC2WZR49p3NdsfeEoh7sjlPk6-2FUOs0IpEEUQSRkpns-2BfJwJjkhPEzUcpg6kbsd3VVi0jjhfiLQxyS2UeHliPCf6a2UjXaF8hYh1HLtiJLtsDNws1AnrEURqHhkRpxHNCwcM-2BGwIs9Ck9iyVB89R6wkz11k8XhdY3tyOXYLPMAiIxKDjXlsDixwAH8-2FjPig74XbGoSigRinr-2B27UnnFqLbzy) is a kubectl plugin designed to show an access matrix for Kubernetes server resources, helping visualize and audit permissions.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^96]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
 

\

### **5Q. KubeConfig Bloat Problem and Remedy?**<!-- {"collapsed":true} -->

| |
|-|
|As someone who works with multiple Kubernetes clusters, managing the KubeConfig file quickly becomes difficult. Common issues include:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^97]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Over time, this leads to a bloated KubeConfig file, making it harder to manage clusters.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**What is a KubeConfig File?**  -- A KubeConfig file holds information about clusters, users, and contexts, allowing Kubernetes to manage connections and enable easy interaction across environments.

\

**Breakdown of a KubeConfig File:**

\

**Clusters**: Contains the details of Kubernetes clusters, such as the API server endpoint and the cluster's Certificate Authority (CA).

![8cc35641-dd1b-4145-bcc0-68d6c694308e.png|657.0023193359375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8cc35641-dd1b-4145-bcc0-68d6c694308e.png) [^98]

\

**Users**: Stores credentials (tokens or certificates) for authenticating the clusters.

![d749f5c7-3496-4279-9767-03ad3bed3ab0.png|657.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d749f5c7-3496-4279-9767-03ad3bed3ab0.png) [^99]

\

**Contexts**: Links a user to a specific cluster, helping you switch between environments.

![aa60f378-b267-4a05-b9ca-c92c54500659.png|593.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/aa60f378-b267-4a05-b9ca-c92c54500659.png) [^100]

\

**Current Context**: Specifies which user-cluster combination is currently active.

![4ffecec7-29f9-47c2-8425-9b996b50754e.png|610](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4ffecec7-29f9-47c2-8425-9b996b50754e.png) [^101]

\

**Managing the KubeConfig File with Kubectl**

| |
|-|
|You can use kubectl to manage the KubeConfig file.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Here are some useful commands:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
**View the KubeConfig:**

```
kubectl config view
```

\

**Switch to a different context:**

```
kubectl config use-context techopsexamples-context
```

\

**Add a new cluster:**

| |
|-|
|[^102]<!-- {"cell":{"align":"left","color":"#2D2D2D","colwidth":952}} -->|
\

**Add a new user:**

| |
|-|
|[^103]<!-- {"cell":{"align":"left","color":"#2D2D2D","colwidth":1050}} -->|
\

**KubeConfig Bloat Problem**

- Creating many short-lived clusters bloats your KubeConfig file with old data.

- References to deleted clusters, unused users, and irrelevant contexts remain, making it harder to manage necessary configurations.

**Existing Solutions** There are a few ways to keep your KubeConfig file tidy, but they have limitations:

- Manual Edits: You can remove entries, but it's slow and error-prone.

- Splitting Files: Organizes configurations but complicates switching between them.

- Custom Scripts: Automates cleanup, but requires regular updates and may not adapt to changing setups.

\

**Better Solution:  KubeTidy,** a tool built to automatically remove outdated clusters, users, and contexts from your KubeConfig file.

KubeTidy keeps only relevant entries, simplifying management, and backs up your file automatically.

It works on PowerShell (Windows/Linux/macOS) or as a krew plugin with Krew (Linux/macOS).

\

![4465bf85-d86d-47c4-89e9-4c220fe07d12.png|767.0023193359375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4465bf85-d86d-47c4-89e9-4c220fe07d12.png) [^104]

### **6Q. Hidden Risk of Relying on Labels in Kubernetes Security?**<!-- {"collapsed":true} -->

- A while ago, a client approached me with a request to optimize the network security of their Kubernetes cluster.

- They had a complex architecture with microservices talking to each other, and they were using NetworkPolicy to control communication.

- However, despite their policies, they were seeing some unintended traffic flows that left them concerned.

- Upon investigation, I noticed that their policies were built around pod labels.

\

Here’s an example (modified the identity) of what they had in place:

![a80bea33-4fa2-411b-a3c9-4c4c61fe2c1f.png|597.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/a80bea33-4fa2-411b-a3c9-4c4c61fe2c1f.png) [^105]

\

| |
|-|
|The intention was clear: only pods with the `role: admin` label could access the `techops-examples-db` pod.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|On closer inspection, I noticed potential issues:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^106]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
| |
|-|
|After discussing the concerns with the client, I asked if they were using Istio.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|They were already using [Istio for traffic management](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cx-2BGz5yyFcqlBtRLQ47sHx11-2B0zlutjJ6gBgAxA7ULVBAvWh7TWRVD-2FIk7AE2tGwig-2BlxOxn47IiB7aRCsiCRgHSKjcaCGWEZQm634vod0K5llHEJJ-2FCreq-2B4BQLLRaO9nkNanUAYMWj36-2FXrWqMkEjCM68MolWkH70JvNOnJc0-2B88pKtSgD-2Bs6jlP0XJHz31iilTYFmVJBHoKZSijKyaYXJNEbZbWnqFGpGCtL9hEL8V-2Bur1hzPrEJO1L0Njg4i7fokCuHfTkWJwQkMXD3FZ1Z7vP9Td2Ovvo4cj95jGZsFe0mx9RygqFohfTEolJhOlw-3D-3DFXvU_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BVO5mwDXbWjHPGnf9FjYVNN-2BSwZtosE-2BQTCcBL3x0JyKwx5QjuGvNSnldMFctCzDc1yuijTzO0UaRMIZQbOPBylxhqxsF6gCZrUIqmY-2FIeFh834e1Hr4ndG0cGyxRkVNaAIrNdPpolkrT5LNweW36ZyWXmPblpi8RERCfA9YsYtyxS6H3gVt7L0ICL79qXViophlVSQFN-2FwdDzD5wGhO7EmpIGVrDiuL1TGuYjc61-2FDDXVpzO4S3oOOf7qj6M98-2BcJXCGZEIYBdPzHKDVeyEu-2F43LfEicw4EeTUPekvDOaMcsqM7SCIHr-2BwNRx3tT9UscctShZW1kQY7ct4FJLJqxH5CLT-2ByYSk6tQj8n66HK9QNmFJ9c9Ue9AACjfBGXc-2BFl) but hadn’t considered it for network security.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|This presented a good opportunity !<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**Leveraging the Existing Setup:** 

\

We switched from pod labels to ServiceAccounts for more secure access control.

**Here’s how the updated policy looks like:**

![bc8bca7b-2e61-4ba7-879a-df006b0aa0ff.png|680](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/bc8bca7b-2e61-4ba7-879a-df006b0aa0ff.png) [^107]

Now, only pods associated with the admin-service-account could access the techops-examples-db.

\

This was more reliable, as ServiceAccounts offer secure identity without relying on easily altered or misconfigured labels.

\

**Why It Worked Better?**

- **Tighter Control:** ServiceAccounts eliminated the risk of unauthorized access via label changes by tying access to pod identity.

- **Built-In Security:** Network traffic is encrypted with TLS, preserving identity across clusters and environments.

- **No New Tools:** The client was already using Istio, so no additional deployment was needed.

If you're using Kubernetes and relying on labels for access control, consider alternatives for better security and scalability.

\

\

\

\

### **7Q. How is a Pod Deleted - Behind the Scenes Breakdown?**<!-- {"collapsed":true} -->

**When we run `kubectl delete pod` , the confirmation message pops up saying the pod is deleted(if all good)**

![996a9a69-59ac-4dd9-a869-86b198f24f42.png|687.9744873046875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/996a9a69-59ac-4dd9-a869-86b198f24f42.png) [^108]

\

**Wondered, what happens behind the scenes?**

| |
|-|
|**Before diving into pod deletion behind the scenes, you should know the basics.**<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[**SIGTERM**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2BfGWP6zl8DtxLSNnIjLUdlwT4APeJJl-2FpGyz8QHH9kMcSH-2FqHyCNhKViYLCobVS4sPwkWd-2Ffon-2Bl28Mo5BfkNK119-2BWhJdxqtVY4okMlyyJGgTT6L8veF-2BeyM312ry9tw5tT01Vlj7dvELlit1pYPeryzNvYPJ0LGLZQe3YRoF2F9xKn02hvd-2BASGtCcD-2BKKLrkvRGvlBpy8-2FGdNZ-2FA-2FZj-2BNcb4J88umFL2kiKLHg4dVa-2FaRULyqIFrsfeblBx3gRjmTs1HwJoa3r5xyprYgyimt8KyR8iHxOghk2gsptIFkhF3-2FJUzC3TuDUoTn10M3g-3D-3D1AKa_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2Bhm7fWhqzTkhc4fVyV1crKgWNixU42sHokG0RTeE7ZqwwlTtqm1Oc62cbXO8cmjfjcM5blRDQSLlGMaDFpop0z4csZ50pqqKOqZpUyACR-2Ff6ycSCWp3hwQ5uM0ntsSe5KgW2VfXdqv-2Fn2xWHN-2Fqf-2F6CGOYSsiIheVW62QFqemPGhaf0xUoUqstJTG-2FOJTvkS18fWuW9ZG2BL31n7ufVokGbI-2BqCck4GpQKrrRArYPlJ3LQpcR7FrWqp4BnpK1e50q1a72UjxRH5jm82px-2Bkas20F2-2F58NvjUtTSmKsujPFKvWyNers8MaE3lvferlafu5YPjcRpw4k5zeTvQgxg8qqPo31J3DXiCshwt8dvcYj2sf1FzIW-2FOb5KOzasGQXxyU)**: Requests a graceful shutdown, allowing the program to finish tasks and clean up. In Kubernetes, pods get time to exit cleanly.**<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[**SIGKILL**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2BfGWP6zl8DtxLSNnIjLUdlwT4APeJJl-2FpGyz8QHH9kMcSH-2FqHyCNhKViYLCobVS4sPwkWd-2Ffon-2Bl28Mo5BfkNK119-2BWhJdxqtVY4okMlyyJGgTT6L8veF-2BeyM312ry9tw5tT01Vlj7dvELlit1pYPeryzNvYPJ0LGLZQe3YRoF2F9xKn02hvd-2BASGtCcD-2BKKLrkvRGvlBpy8-2FGdNZ-2FA-2FZj-2BNcb4J88umFL2kiKLHg4dVa-2FaRULyqIFrsfeblBx3gScAGCARFBeH4kCvvBHwzMlRg3slD1O3Gyyd2bk0570dP-2B2pxinhQvGFD1B6NgbKsg-3D-3DFAJm_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2Bhm7fWhqzTkhc4fVyV1crKgWNixU42sHokG0RTeE7ZqwwlTtqm1Oc62cbXO8cmjfjcM5blRDQSLlGMaDFpop0z4csZ50pqqKOqZpUyACR-2Ff6ycSCWp3hwQ5uM0ntsSe5KgW2VfXdqv-2Fn2xWHN-2Fqf-2F6CGOYSsiIheVW62QFqemPGhaf0xUoUqstJTG-2FOJTvkS18fWuW9ZG2BL31n7ufVokGbI-2BqCck4GpQKrrRArYPlJ3m28ywSrVCFsApc4Hnr-2BbnUS6nY8OEeq4M0lE2Jwz5Vti1otWSFkNfJAXlNveGvYxmxMlJTVeSTYi3HFsGHn6va7hNVgIDvDy51KRwaf9rxo5-2Bw-2BMYJpY6BXFIyYDaQwdIXXm9MHWnk7FTtKE9UrWw)**: Forces an immediate stop, with no cleanup. If a pod doesn't shut down in time after SIGTERM, Kubernetes sends SIGKILL to terminate it.**<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**In short,**

- **SIGTERM allows for cleanup.**

- **SIGKILL stops everything instantly.**

**Pod Deletion - Behind the Scenes:**

![d0f91bfa-1d07-4af6-be87-6538f296dd74.png|793.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d0f91bfa-1d07-4af6-be87-6538f296dd74.png) [^109]

\

![7e8526ff-0d01-456e-ad03-45a1c97b50c2.png|800.9837646484375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/7e8526ff-0d01-456e-ad03-45a1c97b50c2.png) [^110]

\

\

\

### **8Q. How to Fix Kubernetes Node Disk Pressure?**<!-- {"collapsed":true} -->

Imagine you deploy an application, but after a few days, it starts throwing warnings like this:

![55ae4769-73f7-466e-974b-ea79a7e789a4.png|692.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/55ae4769-73f7-466e-974b-ea79a7e789a4.png) [^111]

\

Your application slows, pods get evicted, and new ones fail to schedule. This common error in Kubernetes is known as **Node Disk Pressure**, and if left unchecked, it can severely impact application performance.

\

**What is Kubernetes Node Disk Pressure?**

| |
|-|
|Node Disk Pressure occurs when a node’s filesystem is under strain due to low available disk space or inodes.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Kubernetes automatically detects these low resource conditions and sets a `NodeHasDiskPressure` status.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|This status signals that the node has insufficient disk resources for further scheduling, evicting non-critical pods to prevent critical system disruptions.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**How to Check Kubernetes Node Disk Pressure:**

```
kubectl describe node [node-name]
```

```
kubectl top nodes
```

Look for any nodes with the condition type `DiskPressure` and status `True`. In the output, focus on the `Conditions` section. Here’s an example where **techops-node2** is experiencing disk pressure:

\

***techops-node2 Ready worker 14d v1.28.1 DiskPressure=True,MemoryPressure=False,PIDPressure=False,Ready=True***

\

This shows overall CPU, memory, and disk usage for each node, helping you pinpoint where Disk Pressure is affecting your nodes.

\

**Why Should You Care About Node Disk Pressure?**

Ignoring Disk Pressure can lead to various issues:

1. **Pod Eviction**: Kubernetes evicts lower-priority pods to free up disk space, which can cause disruptions in non-critical workloads.

1. **Scheduling Failures**: New workloads may not deploy if nodes are in a Disk Pressure state.

1. **Performance Degradation**: Insufficient disk space impacts node performance and can lead to application latency.

\

**How to Fix Kubernetes Node Disk Pressure**

| |
|-|
|Here are some strategies to address Disk Pressure:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|**Clean Up Disk Space:** Clear out unused images and containers, which can take up significant space.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|**Increase Node Disk Size:** If your nodes are in a cloud environment, consider resizing disks. In AWS, for instance - Increase the EBS volume size.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|**Move Logs and Data to Separate Disks:** If your node frequently generates large logs, consider mounting a separate disk for log storage to keep system space free.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

![85687600-bf8f-4e8b-97b7-af2b88c48c58.png|756.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/85687600-bf8f-4e8b-97b7-af2b88c48c58.png) [^112]

\

**Monitor with Alerts:** Use Prometheus or another monitoring tool to set up alerts when disk usage exceeds a threshold. This proactive approach helps you intervene before Disk Pressure arises.

\

\

### **9Q. How Adidas Cut Kubernetes Costs by 50%?**<!-- {"collapsed":true} -->

More and more organizations are taking concrete actions to reduce infra costs, and Adidas is no different.

\

Before looking into how they cut down Kubernetes costs, let’s understand the critical elements adapted by them:

\

| |
|-|
|[Karpenter](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C8iJO1UfYC-2B0OWAY2fEIdj5qylzJOe-2F-2FaVpipl9dkioiD0qrSbnfor8VdD9r7-2FUh3Edk6RBpbEboM2gZnJr4GmsyWElt12abIzv6KZJI7nCLfiYG6k59SJdv29kpL8Nf0wLiPa1DAHfb54tJjasXacDQkSsfxYJeYR0JWFETmEwB5ZgexnbAz21m7YaRNYqhVgkmIAKdpSt4bSjH5Rj7Z-2BEThcwWThBya2lcdVUjS6c-2BXQ67_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsEJL7I0Lz7SKf-2FCseuGhzXiM5o3kVbmM8XaPOxSOSXjUQc4lzGYHlLXDsL7kAVogw353ccX-2FvVpy1V6rtfke6FTRVXk13UQ5i09kEfs-2FnszW8JpKeL4RruL7qYHTxTHiDEUHksMOu6O5vsVd8LlOPrV) - a Kubernetes autoscaler that dynamically provisions and scales resources, optimizing EC2 usage with spot instances to reduce costs.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^113]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![9cceb4ca-d750-45f0-be0d-e24cc862f059.png|733.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/9cceb4ca-d750-45f0-be0d-e24cc862f059.png) [^114]

| |
|-|
|[Kyverno](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C5G-2BwwjHE7ohUGxrRvXOIM5VP2F1nuB1Ioe6nCiDKVTJcBmLGMN8jVNLMkpNTqi1-2BzZrx71RkucYSh4dFrPl0q6Yl6Lz9-2BVlIEQOR60I1Y7CGIUOUzcf8ZnHGr3pYdpch4nzJaGHHaPjcwFxzRH0Hj-2BAZj54YUZy-2BaDeiwyzkA2ZiMneyI7f1FlM4U7eKqLq-2F3LVmDn2yGTiPUxiwphglQr4RushszuMNwOiU59-2FhNMrCyPbMGNAMbo4AwH2-2FcPOXg-3D-3DqNlz_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsHnHFkJ7B0fXKj6LPdQNspi7uZBkllapXH24kKqBalw1TvO62W-2FqgzZLXG8nUD1HZZs9x-2BPsbPQbiobBIR8LpG1V-2FJn6lDqLFRdbBSIZDPh-2Bx-2B09xZoMBqYKCbi3ifR69o2lJhXPszWD6nsrzBEFdjj) - a Kubernetes policy engine that automates and enforces resource configurations for compliance across clusters.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^115]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![a5d86b74-3509-4972-a6b7-6d603680c2c1.png|646.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/a5d86b74-3509-4972-a6b7-6d603680c2c1.png) [^116]

\

**Adidas First Approach: Get Cheaper EC2 instances**

| |
|-|
|To reduce EC2 costs, they implemented Karpenter, that adjusted node counts based on application demand.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Karpenter perfroms [consolidation](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CwftbTBq1N-2Fh1B50MYrOvjZaleDJag6svUrePAL8Hr3cCF-2FGsDHcZu3vgYmrw4gtwfwFyHZ8Yq9YJPUsATeCcegROfKgkQB3nvfbnj3W8IFC7ZPjhFx-2BbASjZqDeWi300wW46LCvt8Tz3TPzeI9HnCyFWKSyWkwJf7X9SnZwnuMzHJjPxLIX0l0odO6Bnfh8DecxP03fduH9qVMHZhQedlb2gKz8RvKH-2FOu3Uf8r4zgh2V3IVD9nqFThCXE0-2BfOlqQtfNem1thEpXU8zqUHpvWs2JrKyocMkiF0Q95Ic0yq7Qnhh_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsEVqZLF8cs23cRWiXBa0OwulPh7jd3GhCUpxqyx1BtIwusg026pvhZZ6yPPh4VfANUgx21VQv5XGvp14p6-2FEpCOaK-2B-2BUnXCBwEH-2B98M-2B0hjNqGrmiJG834wMw-2BFy1zhiB4ImWXuGuOzoD56lm0MWCU2) by selecting the most suitable instance types and sizes to maximize node efficiency, removed underutilized nodes, and shifted workloads to smaller, cost-effective instances whenever possible.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Another leveraged key feature was [Karpenter’s use of spot instances](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C35HjHOakFqRqdvI3px7fyQL81ROjNsdWO5oF9dji8aj8T-2BlULpZm70pj6-2B-2BK9eTaF9YYv-2B5cKsiZo9RYMm5etmmoxwwW4kxaHlu0jc-2BnIzo8PIygKLkoptA6OooNtC-2BFpalfbvw0fKN2vhKWWGSuXIqMZXmR5-2Ft6O7xnpbJwZxXbRdrOv1ZnWAgDmg-2F1bCu0716uJuoyvuTHdM2EE5bL29Z7MhFeZpnxUo6rMpAoj0gSic0IsTAjFlYJlW86yXOHEzM5o-2Bo5ajBgGua-2BMX3k3nw-2BHXDLU8VIs4IHPui1fUBaHK6fF-2FNCJXiGbMwaCDmYA-3D-3DWl8g_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsF57WDw-2B-2BkaVu-2B0rdVpeGj80s8Qov7CzYyYh5nV9sfz5ILgqj60LlZfPqPtb1y7C8LLRlNfcIkbxjjm6bfF-2BRLgbAYNTXhi-2BfXm7Q33sQagFht70v03O44fjNRVmlVgwNj47me5s5nrNprRtTtC5hL-2B) - AWS’s lower-cost, unused compute capacity.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Karpenter identified spot instances with the lowest price and minimal interruption risk.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

\

**Adidas Second Approach: Creating VPAs automatically**

| |
|-|
|They improved resource utilization by automating [Vertical Pod Autoscalers (VPAs)](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C9s8b8-2B6ply-2FJJJMprvshVN18cQ7x3yDiE8tNu7CVNv6ZZQYmIK44JrC-2FzydjERTSWDkzGxy67PMkwrOMtyl-2BVfkmLaz8irTQjHp9-2BYyLiVC7j3RXZTJxBabswiM5WGcMzvkpZeLT0M-2BSxBiC-2B3PHjvd8IH1Qz-2BGwMsAUN-2F9x1nO-2Btjw6Cnh83nplBNGoni9msOl4jMi-2FnyGzumMhOYyjChDCUaSLvsJtwGEfZE9pWUyqrptEXuqNotiBKj4Twdn6HU-2FeO-2BtYlk7zDO5-2B-2F1Bh57gdhM1941NuHNCc0tw-2BVBYSP6l-2FyTXwdvj-2BdCxnMzf3g-3D-3DFaOU_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsHiMq4EQZOABJ-2BaLe7YNrCJWSEo-2BmpVrMt-2BuKRgu8fBy9zse6c8nChf2v8EAmThgDA2qvYdAy04PUFAFToJqCdta-2ByRBRVEzimbceRnNeHWSG-2B7nOjGFsplMsw8Q9vXEi3DALEZNrh6NuPkvRFxCwp0) for workloads in development and staging clusters.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|This included optimizing container requests and limits, and adjusting replica counts when applications were idle.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Typically used for application security, **Kyverno** was already part of their setup.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Although using a security tool for VPA creation might seem unconventional, it proved highly effective in this context.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

Kyverno automatically generated VPAs for each new Deployment, StatefulSet, or DaemonSet by checking:

1. If the resource already had an HPA or VPA.

1. If VPA creation was allowed for that resource and namespace via a specific label.

\

**Adidas Third Approach: Scaling down in non-office hours**

To reduce compute hours, costs, and CO₂ footprint, they decreased app replicas during non-office hours using [kube-downscaler](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C1xmoW8uVUdhQZDUHG95TrT5U-2FkT2lu61sccssPrakjv-2Ff6BvGiiUfxE16jtMjrTFDBdqfzGxwfLtDXh5rN2TgRq2gdGoEc9GZOUHk-2BAeiwoJSDnVKpJriXZLIX-2FEvmx3jgNdIXdw4qPPzt20Ma1r5O9Vmd-2F-2BJ1O9z5f8VMSZzKvtoSIQYsYcgZhpJvEB95sBdJp-2BPRqoyegp-2FBrtnRpBc9vWiQ0xGRhnzqvbkXRxkML9ohXhPNzWfTeNSJ-2BZlVOBIouCRXQqX0uwGz5P5D6r4Q-3DEBfk_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsEuhH6BkcEFmP6j-2FWicFdCvPWl1tnMSEEKwqVVchFGocaMYWKkEd1YYSSzHxt-2B-2FKC8icz745JH9dyuJa6rP4DHBppvco8ZqObJQeDSzd0f5KviDAZht-2FgrtQTGPdG1gRhYw-2BxV6jRMtpGvwh1C2XouQ) to scale applications based on a set schedule using annotations, like:

![6a243ea6-b0d2-42df-a7da-c724c3cb41ee.png|715.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/6a243ea6-b0d2-42df-a7da-c724c3cb41ee.png) [^117]

\

In this example, the app scales down to 1 replica during nights (7 pm to 8 am) and on weekends.

By default, apps scale to 1 replica, with options to set 0 replicas, adjust timing, or opt out. For apps with an HPA, scaling to 0 replicas requires annotation on the Deployment or StatefulSet instead of the HPA.

\

**Adidas Fourth Approach: Scaling based on external metrics**

- Resource metrics may not fully capture app load, and HPAs can’t scale to 0 replicas as 0 pod apps don’t generate metrics.

- To address this, they used KEDA (Kubernetes Event-driven Autoscaling), which scales apps using external metrics from sources like Prometheus and Kafka, enabling scaling to 0 replicas with independent metrics (e.g., Kafka consumer lag).

- Custom metrics also allow HPA and VPA to work simultaneously, supporting vertical scaling on resource metrics and horizontal scaling on external metrics.

\

**Adidas Final Challenge: Underutilized nodes due to restrictive PDBs**

| |
|-|
|They found many half-empty nodes remained due to restrictive [Pod Disruption Budgets (PDBs)](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdaJGgK4bYnY90M69FT-2FT1homPMxui65hIxS-2FKQJUO4rhggMsXq2ij298fst4CHArfG1vdKWv2Cv9qNPev1-2FDYcZeS7hYtccgc9qhEZv5PdsFPUJbXnYh4BelhkXdIQeEXGuy2K80-2B2cmqPav7ss1tYlQrTlVKKLGCVNLv6jWGDo0pZ8v9CuwipKWf-2BlAOdkaCTOGmW2syLCfMdBaSB9lpppx4tVPXc8467xTsMHKsvdFG6uaNe-2BTcBek0f0otA-2FfxLStqXKnfU1umUaHsDzXJRjoLW4W-2FzY94wjlzZDSE6CPw-3D-3DJ85G_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BKoUdPlZ2JxZ6u1MiVTFmuDoGtV3Gj7jzuZ5guEW58BZ1Pv1vviQ8AUqUzonopjYe3qLvw9s9UwB82GusnE-2Fkh7chD85dkg2epvQYikRJGqzP-2BOu7-2BkrHZ9aSFlaRjkwVHwTZn59wqJnjiIvDaFQIO8gtNr0t0oOyQh5raOcyiXvqRE9ic0hRQHAjshX9aMRcZ8NvRXwu1sHvzcl-2Flr3w0oFutQk8Xo9FurgojgqICsG04aMWQ-2FldnoXAv4rUFSkS9aQg7fUnBx85nRWi3gfVk3Ks86NoWp06n0R7sZGTR-2Bvd5SACj5M59bqqbNb6eImsO17QuFYHtZvET8VeC83vXNOYTom0ltlwVgNHDjczh9YpThzPWVwj7ozX-2BK4ehg-2Bl) preventing Karpenter from removing underutilized nodes.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|To solve this, they created a Kyverno policy to ensure:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^118]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|A cleanup policy also runs twice daily to remove undetected problematic PDBs, though it’s advised not to run this during cluster upgrades.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|And they cut down Kubernetes costs by 50% in totality.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

\

### **10Q. Kubernetes Operator vs Helm - Which One to Choose?**<!-- {"collapsed":true} -->

| |
|-|
|Kubernetes Operators and Helm charts often seem like interchangeable for application deployment, but they serve distinct purposes.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|While Helm focuses on templated app installation, Operators enable more sophisticated, lifecycle-aware management.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**What is a Kubernetes Operator?** In Kubernetes, an operator is an automated way to manage complex applications using custom resources.

It combines two key components:

![5625a783-a105-4c37-b410-ace332a39d70.png|704.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5625a783-a105-4c37-b410-ace332a39d70.png) [^119]

\

| |
|-|
|Let’s take a simple example Use Case: PostgreSQL Database Operator<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Imagine setting up a highly available PostgreSQL database.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|With an Operator, you can automate scaling, backup, and failover with just a few configuration settings, without manually configuring these tasks every time.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![02b1a509-fd86-4b3a-9fcd-ee879a63886d.png|667.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/02b1a509-fd86-4b3a-9fcd-ee879a63886d.png) [^120]

\

Check out [OperatorHub](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cz36d-2BvJhR9D-2FRgO87aCmkHyqzF8u29k-2FOMqdIC8HrauF2gpiWAYWZky2UGW3LtgiLym-2FK6ynuhoYKoi-2FGQckRVgQp-2FmHgw65htOGzGWXeMt1wZJ9i-2BC3U1rNw3Ul5TpL4Zz8EQtkxrXfuET3VSsPELMccIfZLleltWCWCFMujo6P4kDdXWkcPVOTiwhSU8RHS1kzswgWolwAgjqVILYrCRTHwetAPhOidxq6wM2uLS0FKFgM2bDMKOWc1WM9hv0Cw-3D-3DYYvq_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BuCxzNX-2FgaNeL06Xkn-2B6WoOuIPiapeyTee4sSFqzg-2BkV1cvA4IUNoNTlbjhyExZeW4cS4NAe-2BXvPMDL27Qlip0zQkz7798cAZjqDzfIgNg6idvSsvOwD10gEAb4sJyybzzg3ZpSuBHcGJUUTtSKh4RW1igg8msc-2FcJhji1KTiPdvn2yxbigZiAaPa-2FnZvSjmVwF3r0BHH-2F8-2F-2BnxZhiWehzii8Pj4XBcC1aDCE-2B9tXhe9dzTsSA1Oz6by5oKZ95cRT7wmQLr24nqtCMqK5kyyker3FncJnTnhSlvYensqtvxcOP8G7CXb-2B-2BLF14aFOfOBezep3AZqhhT4CAgquK-2BZTFWF1NNc-2FQitz0l1rj6ulsZs8I1bWT8BdrvyjBK-2BZE9Ep) for awesome and complex Kubernetes operator examples.

\

**What is a Helm Chart?**  A Helm chart is a package format that bundles Kubernetes resources to deploy applications in a repeatable manner.

![78ae8926-9490-403c-890b-c1f2af280cf6.png|832.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/78ae8926-9490-403c-890b-c1f2af280cf6.png) [^121]

\

[Bitnami GitHub repo](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C3WaWmO5QGfwQ-2FaUcZzhfxu-2FKVx0XTFn7UR1DoE8rXJKG9GYG8acr98KWG-2FI7K7YjW8nscEcvG3usINz6MEMVqug-2FWH6UFBwRnrn-2Fev7TIz9sA6b92J-2BXI-2BDsX1v-2FqdNBdSZr7qgnpEPLiatHDTSdgt0EIkoxWVlugaw6LwuRKEGAYk6nyN-2FgPy5N58508v1BbARhBfxgHkEJ1JiV5xAN4zQtdERt5XG6cI5MB7SDQzQ0FXKfuWqayYt2edwAJpEqWJA45fz7h5c-2BpL7SLwuy7M-3D77Jc_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BuCxzNX-2FgaNeL06Xkn-2B6WoOuIPiapeyTee4sSFqzg-2BkV1cvA4IUNoNTlbjhyExZeW4cS4NAe-2BXvPMDL27Qlip0zQkz7798cAZjqDzfIgNg6idvSsvOwD10gEAb4sJyybzzg3ZpSuBHcGJUUTtSKh4RW1igg8msc-2FcJhji1KTiPdvn2yxbigZiAaPa-2FnZvSjmVwF3r0BHH-2F8-2F-2BnxZhiWehzii8Pj4XBcC1aDCE-2B9tXhe-2Bw9Q9dJgP6b5o8-2BUsieEYVGUMmu4lYqIkDrXwi6Gbj0cuLSObfUoceCl-2FdoqKc-2BOBUFOkD91R1VDQetnGqFXfoeySjerclzASK00ggAMRvVSEQesr3U0NcBVDrNiLv5aP006PjZlFi04zF38tUf50q) is a good source of Helm chart examples.

\

**Example of a Chart Dependency:**

![2e6ee87d-f432-4095-acee-a0be600ff2f6.png|666.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/2e6ee87d-f432-4095-acee-a0be600ff2f6.png) [^122]

**Helm Chart Workflow:**

1. **Prepare a values.yaml** with default configuration or custom values.

1. **Run** `helm install` to deploy the chart, which renders the templates with values and creates Kubernetes resources.

1. **Post-install:** NOTES.txt displays useful info, and values can be easily overridden for updates.

| |
|-|
|This structure makes Helm charts powerful and modular, promoting reusability and configurability for Kubernetes application management.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Here are the key differences to be considered before picking the one to choose.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![dce0b784-c7a8-4a2c-919e-9ca87ed4f393.png|756.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/dce0b784-c7a8-4a2c-919e-9ca87ed4f393.png) [^123]

### **11Q.** **Understanding Kubernetes Logs - A Comprehensive Guide?**<!-- {"collapsed":true} -->

| |
|-|
|Not every day you would be setting up clusters; however, there is a huge possibility that every day you would be involved in the operational and troubleshooting aspects of Kubernetes.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Understand the logs plays a crucial role in any K8S practitioner's life.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|You can’t miss it or skip it.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|I broke down the typical Kubernetes logs directory for easy understanding.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

Like other directories, you can park the application logs under '/var/log/', which can further be organized by 'namespace’ and provide insights into the internal statuses of your application.

They are especially valuable for troubleshooting issues and tracking cluster events.

\

![8ec01cd8-ab08-4881-82d3-e9c64ac6f837.png|815.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8ec01cd8-ab08-4881-82d3-e9c64ac6f837.png) [^124]

\

\

![](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/84fce0bf-255a-4675-bd21-6f83bb89dccf.png) [^125]

\

The log directory structure is quite straightforward; rather than spending time going through each one, let’s talk about ‘cluster-level logging’—a less discussed and crucial aspect.

\

**Cluster-level logging architectures:**

Kubernetes natively doesn’t provide log storage, so cluster-level logging requires independent dedicated backend storage and lifecycle for logs, separate from nodes, pods, and containers.

**Here are a few options:**

- Run a logging agent on each node to collect logs.

- Add a sidecar container in the application pod specifically for logging.

- Send logs directly from the application to a logging backend.

![8ec67009-dc03-4a36-aa67-94bc208973cd.png|778.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8ec67009-dc03-4a36-aa67-94bc208973cd.png) [^126]

![](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/e8658e0f-2e62-42be-943f-4f8067cc187b.png) [^127]

\

![777cefa1-704d-40bd-bfc0-f75d872eb1e8.png|817.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/777cefa1-704d-40bd-bfc0-f75d872eb1e8.png) [^128]

\

\

### **12Q. Conventional Vs Kubernetes CI/CD Pipelines?**<!-- {"collapsed":true} -->

| |
|-|
|With more teams looking to adopt Kubernetes, it’s essential to understand how its CI/CD pipeline model differs from traditional setups.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Kubernetes brings distinct paradigms that impact everything from artifact handling to deployment strategies.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
Here’s a structured path to guide you through the transition.

\

![b7863e05-32f5-44d7-b327-ce31bef0e986.png|759.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b7863e05-32f5-44d7-b327-ce31bef0e986.png) [^129]

\

1\. **Understanding the Differences in CI/CD Pipelines**

- **Artifact Handling**: Traditional pipelines store build artifacts (binaries) in repositories like Artifactory, while Kubernetes CI/CD pipelines use container images stored in registries (e.g., DockerHub, ECR), requiring robust image management.

- **Configuration as Code**: Kubernetes relies on YAML files for defining pods, services, and deployments, allowing version-controlled infrastructure and deployment configurations, ensuring consistency across environments.

- **Deployment Strategies**: Conventional pipelines are often linear, whereas Kubernetes enables advanced deployment techniques like Blue-Green and Canary for controlled rollouts.

\

2\. **Core Concepts to Master in Kubernetes CI/CD**

- **Immutability of Containers**: In Kubernetes, containers should be once, tested, and then deployed consistently across environments. Each environment pulls the same image, ensuring reliability. Adopting this approach requires container security and compliance checks to happen at build time.

- **Environment Parity with Namespaces and Clusters**: Kubernetes enables environment parity more easily than traditional methods. Use **namespaces** within clusters to mimic different environments without duplicating resources, making for a cleaner, more scalable setup.

\

3\. **Implementing Kubernetes-Specific Deployment Strategies**

- **Blue-Green Deployments**: Run two environments (Blue and Green) side-by-side, where Blue serves production traffic and Green deploys new updates. Once Green passes all tests, it starts serving traffic, reducing downtime and risk.

![8e06b6f1-647d-48c5-a772-fb9f653ce2ab.png|624.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8e06b6f1-647d-48c5-a772-fb9f653ce2ab.png) [^130]

\

- **Canary Deployments**: Gradually roll out updates to a subset of users before full deployment. Kubernetes supports Canary with service mesh tools like [Istio](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cx-2BGz5yyFcqlBtRLQ47sHx3-2FgXUCZaWfGsSP-2FnmpoICdqb1Q4XNwnvFxRidtHVR1rtw4rYIr0rXOsCd9j0rUKhiSVwwp3iQ-2Fv-2BzjQZrLMoOYbQX-2FZXPMUP1kf2K190h1rJwyjoEKW5a9fC1Z-2FUxDDHlE1Bd4SuqiYwRWup-2FxdPb0SMnIWH6MnHtR-2BMtvSPuNh3jXtqHFkmfTXIAmYzSGrY1IkfjBLQxwo0G0-2FgjncRQxrAC7k7ZCnmLwHbk-2BCuftoA-3D-3DkMTc_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxNma8-2BKF9nBPtH3NBLK1Wq-2BDrxjsLVWntvLdsrl2Jt3qwzYiHnbh3dyUmeBoqKz3sbrKHxt0y8Kh7OZk8r5bAT-2FILABmMlwISh9JbDShNefe87o2gUEelzGDzDZnl9pOsfWFKz8n9QS4UR1h5oz88Xn) or by configuring traffic splitting, allowing rapid rollback if issues arise.

![cc86cf89-b556-4e63-b5df-f12380575321.png|585.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/cc86cf89-b556-4e63-b5df-f12380575321.png) [^131]

\

- **Rolling Updates**: Kubernetes’ native [Rolling Update](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdbhUeKwCnmS-2FQ5xebZXfpsmmqIQuJfQjZBxNjfc9RMsSjQohbayhuTDK9QqBcXebAalkdFdgGoTQJoslAP8zuw-2Boa63xaiNmj16weAD0a9JRNDc3NR0N5hTNPG0H4u7pHJb9fUydhjaNoOfpUfKOnpr-2F6TrJdM6VQ2j6hvjb-2B4grrGpKKDtOOnSMlFuz-2FpBSw6Zgu1wZWLCSAVTOtjWvRZKxMrYtelBGd6Arb8VPx08yfP-2FtjI-2FLHjDMsHe70k30b-2FnOUfEBrZP2F3ZSc-2B4n-2BwQqUg-2F2K2U6lQ7QheDySOOwA-3D-3DrP3L_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxPT4jOO4rGAmJU482hcq-2BKU0fdUGjfCm950cP-2BF2z1qKYIqhHaf5k2eRLwsX3I1CYqw-2FPOQ3EudBhPrXgjH2-2Bm4h59FTte-2BJcAFM7oFXhzp-2FEqIFCQ8OoHOoJq0lON8YTLI0LB4s2FJH2Ej0ZYq5n1Z) feature deploys new versions incrementally, maintaining availability. It’s ideal for low-impact changes and provides in-built rollback options.

![6680f0dd-2bf4-41d5-b0f4-e384890a68e4.png|633.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/6680f0dd-2bf4-41d5-b0f4-e384890a68e4.png) [^132]

\

4\. **Automating and Managing Configurations**

- **Helm and Kustomize**: Manage Kubernetes configurations with tools like [Helm](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C4J-2BDfOQsLh-2B2xTpRl3OW2SaVjZsz1duCjKhwECctGw3sphu8HH7Sr-2FjmzlHsCH7RkI9OOoXiqMkOiwoCcYeu5PdI5giGmfp8UjIcQPfX3W6x49IiAR07ABf-2Fmi4BQUSwseuPKujpq-2B14KPoI3FfqXsRWUbClwGnREi2dPV6ZJVX3pzpagX-2BGaJDQL6aILQXACob2j0eVbekzWFF8IJEaT5E2cFusXVw3s04qFmqbdQ80EG9_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxOVBffS0DQrGLtC9Siw-2FZiiQjbG3zwh3S6uIkeXQVDtXhUgCo736sZrTEyYl7FxxVTqFFuAi2QjWyXEL7m1WNR5wrADIKAlv1GWR0gD7dMbbvLln9qSkCqNCJALc4hsDySOUeq0N4j2SYS9fJG1-2Fvpm) (for templating) and [Kustomize](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2Bqtlf5pcUq-2B-2BU1DQEjd1csk5nGTw0Uqr5mRAYugQNKDTHMPr294hQiCVfIH31FWtJtDp0LxrkYd8NKgltMCtE2wubBayO27oK-2BfmubIgsPO9b1pFIEukic4cdupqQ2-2FISI8if0vYw1lVutzZswaOOewuZy5gTgL-2BKpEGpve-2BUXBRDY49NFWYcC5k5A8-2BSWeii7Wewc2ns8flqbIepq3ecacRmqVTxsjdrLKEzZ1lf1SVrwq2eIM9HjYOTbCA0h8Jg-3D-3DO_rE_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxPurKmkd3Gya-2FeQLDUMH3agM-2FgLM5Az5vKqBj5JagM4HAxMEV4KtgBgE5kh8RMZZIfPSptcyVe8aUG39d5e2PwhRCpoZZsZ-2FQ-2F7qEWOY8OMpbK-2FffBnSegBkJzyOnJ4Fyr-2Bas0-2FNnWwA2mhcEE3ya1x) (for overlay configurations). They simplify version control of YAML files, manage secrets, and handle environment-specific differences, reducing configuration drift across environments.

- **GitOps Approach**: Tools like [ArgoCD](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C5dF0phCImwMqgMwHUfCg-2BAgE7mcU4VQDMH8KX-2Bw6b7SKL8vq7vfsbpRka8lESUIWvisIF2WG1xLDDjYsg8EmA7-2BAPv-2BlinPeycfijTgtiKlkIl-2FWqVL5-2FeKO4zCosZ2mu2RBp3W6kMHvfgsTrGWMLjNq6u-2FrAizNBpO7zmsZ0bW7KZXdYdN5ds0vndyzJRSZLxw-2BlKhv5q873On8Pma9bl1eKiu45vALojI9hIIjTb4-2BAwNVRZOTb2BXoSMgXM13-2FTaHpzqY8heGDIn6Yx7YN8-3DDkWe_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxOmJJJ06Lo6rhMFyy2iOEmeNonj9ql1TTPSln8pHZ-2BS-2FUK512GLon9s-2BnxUcYZuZrW5KvlRX-2Bh4PM312zK2geQQpUpdTDqIbXYUxmxtklf9gT-2FN-2FKVEmmbxQypj2uLdF25NWZbetFVUXukyajBk4vfj) and [FluxCD](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2F26rPVZ1LidtAe1gufQM-2FQOgmKSzsioVAW4bvvI9gLPAu61dFlFLAlVFnttycyyzJ1kajjvJ2-2F6JdBF5sbrQ8YU3sP9O6QQiNoXoLMDa0nR52v9Qbkl-2Ft2K2I7Je-2BaZqwwedeD2pGIh8s4-2Bl55m92xCniJPEip9VDzXIVT-2BTU5hywyZAvm1rTawvbgxL2KmuoMFfXDIPWH6CJXASw5d282iR8L42Wd9BysYTNZi265apOHpDZcKLYzGsE4j1vWtaQ-3D-3Dad8C_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxO1XUyBLufwOH3n3jrt-2BAxtKelHrWe4bZfhxsWlBQnwXI1Rp4O6m61lJlp-2Bjxh-2Fxxg6ScHY4QlisXCwP2gum4bRMfxCWHizJ-2B0ASc0uYIBQgfx2qydH4StP208RSEqOi3v0r0mdCQsrPBbdLqYlY7fh) allow you to implement GitOps, where the entire infrastructure state is versioned in Git and automatically applied to clusters. This method ensures that your production environment always reflects the state defined in Git.

\

5\. **Best Practices for Kubernetes CI/CD Success**

| |
|-|
|[^133]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Kubernetes CI/CD may seem complex at first, but mastering these practices will give your team the edge in managing cloud-native applications.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

\

\

### **13Q.** **pod.yaml File Structure Breakdown?**<!-- {"collapsed":true} -->

| |
|-|
|In Kubernetes, the `pod.yaml` file is the backbone of your pod deployment.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|It’s a declarative configuration file that defines **how your application containers should run** and interact with the cluster.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**What does it control?**

- Container images, ports, environment variables, and resource limits.

- Mounting volumes and handling pod-level security.

- Scheduling, tolerations, and advanced probes for health checks.

**Where is it located?**

| |
|-|
|While `pod.yaml` is typically custom-created for applications, these files are often versioned in repositories alongside Helm charts or GitOps workflows.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Let’s start with **the basic structure of a** `pod.yaml` and break down its key elements.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8f827836-8607-4ea6-bb6c-138ba646d08f.png) [^134]

\

**Metadata:** Defines the pod name and organizational labels like `app` and `tier`. These labels help selectors identify and target pods effectively.

**Spec Section:**

- **Containers:** Specifies container images, ports, and environment variables.

- **Volumes and VolumeMounts:** Handle data persistence and configuration through external ConfigMaps or Secrets.

- **Restart Policy:** Dictates how Kubernetes handles pod restarts (`Always`, `OnFailure`, `Never`).

\

**Crucial Elements and Red Flags**

![72.png|40.99536895751953](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f6a9/72.png) **Misaligned Labels:** Labels (`app`, `tier`) must align with services or deployments targeting this pod.

\

![72.png|43.9930534362793](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f6a9/72.png) **Missing Resource Limits:** Not defining `resources.requests` and `resources.limits` can lead to cluster instability.

\

| |
|-|
|This basic structure forms the foundation of any `pod.yaml` file.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Now, let’s explore more advanced configurations.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**Probes -**Probes ensure that Kubernetes knows whether your container is healthy and ready to serve traffic.

- **Liveness Probe:** Checks if the container is still running (e.g., `/healthz` endpoint).

- **Readiness Probe:** Ensures the container is ready to accept traffic (e.g., `/ready` endpoint).

![fdc0432a-d5f0-4902-b788-7f97a0a7e279.png|644.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/fdc0432a-d5f0-4902-b788-7f97a0a7e279.png) [^135]

\

**Why they’re crucial:** Without probes, Kubernetes might assume a pod is healthy and route traffic to it even when it’s not ready, leading to downtime or errors.

\

| |
|-|
|**Pro Tip:** Define probes tailored to your application endpoints, and test their configurations in staging before deploying to production.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**Affinity -** Node and pod affinity control **where your pods are scheduled**, improving resource utilization and workload performance.

![2bc1b87e-67b4-49b3-848f-d6150eec758c.png|647.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/2bc1b87e-67b4-49b3-848f-d6150eec758c.png) [^136]

\

- **Hard rules:** `requiredDuringSchedulingIgnoredDuringExecution` enforces pod placement on specific nodes (e.g., `zone=us-west-1a`).

- **Soft preferences:** `preferredDuringSchedulingIgnoredDuringExecution` prioritizes placement but doesn’t enforce it strictly.

### **14Q. When Microservices Architecture Becomes a Bad Idea?**<!-- {"collapsed":true} -->

| |
|-|
|One cannot take away these debates from a DevOps and Cloud engineer's lives:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^137]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
As a matter of context, let’s pick “microservices” for today.

| |
|-|
|If I have to explain the difference in one line:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^138]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![c2527f90-2676-403f-a09b-1bc351bbc260.png|601.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/c2527f90-2676-403f-a09b-1bc351bbc260.png) [^139]

\

\

Microservices can revolutionize how you build and scale systems - but only when used in the right context.

\

![d248e193-2e38-42e9-aa64-59d7db8f5a0c.png|737.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d248e193-2e38-42e9-aa64-59d7db8f5a0c.png) [^140]

\

| |
|-|
|There are two ways to fix the sprawl:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^141]<!-- {"cell":{"align":"left","color":"#2A2A2A"}} -->|
|[^142]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^143]<!-- {"cell":{"align":"left","color":"#2A2A2A"}} -->|
|[^144]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

### **15Q. Kubernetes Upgrades - How Not to Mess Up?**<!-- {"collapsed":true} -->

You may have heard about the Reddit Kubernetes upgrade horror story, [a 314 minute outage caused by a version upgrade from 1.23 to 1.24](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C8fpeW9KkaPPkqhTX6q7le3PR1HRWjuusSSJxYvQCONZ2Dd8CHnQH7FtnUHCbJOjmcrZ5oiOAoATBq5TElIneTvr-2FeDf5-2Fc1nRoVXz3ZyuAf-2FfrfzG8L95j-2BE2ljZg-2FdeArplndAECsWQs0oPUB4pN-2BLWkzcofjQ5i3n2vT-2BpHFQhw1s4mzgrfAreesJYP-2B9wWbNa-2FRv6Ynt-2BkY32SAs-2FGohuYfZ-2Fx4OzlpnoFIrxnU6IqiW-2BYVFvSsgnOCriqT8Zp00ehIJ33M7qdZxw7YUPbLucwft2lmjYhMe9mTX25yeoTUShEfHu0D3e7o2GyAO9w-3D-3DJORK_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7rroCvR-2F8ybf-2BuiRAjLXtBkQkCF8qzCHm70OJ9vbY4z3bMsKwTAfOwGCuamUqZnKaIU8dyeG1W0eLtG7NxBfJasY8UJWGfnnArkE6-2BGnbk9T63S4iMjF-2B7PJNvg0FjiPF-2BBplyGbvkfzhFi5kEN2qXIm).

\

| |
|-|
|Whether you're running a startup's first cluster or managing production at scale, no one is immune to upgrade challenges.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Kubernetes releases move fast, and the N-2 support policy means staying on top of upgrades is critical.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Minor version timelines can quickly leave your cluster unsupported if upgrades are delayed.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![1318e5e8-dd88-43c6-b8b2-a7bd3f17676b.png|600.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/1318e5e8-dd88-43c6-b8b2-a7bd3f17676b.png) [^145]

\

Kubernetes upgrade documentation provides details about the technical steps for upgrading.

\

![bcdc790e-82ba-4a76-9aea-314e24c96b6f.png|675.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/bcdc790e-82ba-4a76-9aea-314e24c96b6f.png) [^146]

\

**Phase 1: PLAN**

- **DEV → Latest Kubernetes version** to catch early issues and test breaking changes.

- **STAGING → DEV - 1 minor version** to nail compatibility and smooth the path to production.

- **PROD → Close to STAGING** for simplified workflows and reduced upgrade risks.

- **YAMLs → Per environment via** [**Kustomize**](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C0Zzd-2B3vAxUug6lHBuUaq59O0mqB7G7K1-2FU7sZ65fkNIFs1KebTof8aFN2-2BWtpzcPCpklerJLyc9K7sZK1rxBK-2FlkhXdEtwpc6Lza4ciTPM9-2F20fMn7yHc3jJ2m8q-2BAUIjSroyQ7MkMO9mrd3LC0D1Rcw-2B4TXMbqpU9QgdaXST5p1ahMlYroHDfOAeUf6vA2-2FHkZ6e-2FHBXZ2Y6w1LZU9HMW1AvOIj0fA-2FL9ikafHWry-2B7XBk_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7rpsWWI28oJepeb7SpZ-2FkZ5TERkCsR7uzr7HOBBA4APj3YGvIrzSveSz-2FwvyC7EbTlryD2bcs7yZljzBJ31Rah3F9vlvOBb6VPgWNz0rBIKF95tqH9gU-2Fs4k3GOJJoI5BQ2iEI5Ou6dnmrB3EsuH8P-2F4) to handle configuration differences.

- **Testing Time → 2 weeks in staging, 1 month in dev** for minor versions before production rollout.

\

**Phase 2: PREPARE**

- Add [Kubernetes EOL and release dates](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2B1La3f41mg88J3w-2BIbHxD-2F-2Br9t6Wx0t8J0SRHUWK0nNKO11yp6GWDQN68P9sj7FWcuxDNI7ssif4XpPExAGtIvRnsXsQbRxXQmtG7qJRbha-2BiGqFpWsNfNZbq72ocWQStyqOkLEYNK3mLvS6b-2BKQdJZrDhOlLPqvSuh6OVBW-2FYqvAnKC3f3-2B0CsS3ZfO0KB84e4DxMpFcrTle0gflOydr7oN1Wpz-2BSuhCi6KC-2B5joPOjq-2BPl9umNac-2BSRD6B5nIBQ-3D-3DMrqs_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7rrbRfzVhRc6Ul7YJGDB0JjfTo2BxBdZUs0zqyu7c3K8MQMJmjqwbTzWCJVFKm-2B3J-2Fkh1nFXVPqPw3-2B4jDvnMluLGK-2BwP5XuMu9aGUy-2Fuv-2Fd49J1tIh0FmiGv9-2FwGptqL-2BK7Cf-2Bm3EzrYsvReNd7M1Vm) to your calendar to stay on top of timelines.

- Upgrade dev with a new cluster once the target version reaches patch `.2`.

- Keep the old dev cluster as a fallback while monitoring the new one for issues.

- Upgrade staging to one minor version behind dev; a new cluster is optional.

\

**Phase 3: ACT**

- Use [Pluto to check for deprecated or removed API](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C3JtHWzwN1JQmVOFFU-2FJli3ZcPSLhgPgXlPpJDrAic4khWinBiwd3MJhqRbNwK5XBA25JFUsNuT5I-2BYrgNdV1iAvtyGf1UK6OOkbQX4jWkmZLLYirRz8Fzl6LZ0y1dORMQ5x8pdSdOTPHSIruOSNUoEywjwLfN6Jr6BvRp2zrsZ9MVREAdFTuvtM39wFs02jgK7j6ec8fnOhN4NmgF-2Fv0EnKedxJyn17SWCvB6xzKCRJUcDr-2FWXPzvyWv4wKBfA3bA-3D-3DpXWE_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7roHTPdlUJVdKTeX-2FuofiugveZ0xelVf5-2Fjd0N2D-2BZbHCIAdtbE9KpZyIQAeoZdMA8zuLO3jFqSPlACnqCDqYegjFjMEFa-2BySN4K1utUuCpJ3r9Bj4i8zf5h3RDowkj5m-2FOdv9qRkI5sOG0566zt-2BktH) paths in configs and Helm charts.

- Check [Helm releases with Nova](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C3JtHWzwN1JQmVOFFU-2FJli3osjf5nECEgc06ys9Y5D36KGDu5iLLqWEfzedUGpaQQAjJt-2FzrRMqPuToOJG8rzXJkJSrhYxhhN5cZWQ7VnFK7lNpATwiQBqiKUEcUQchyRVejReE70kpNoSH7nOqMqJjelk-2BHWw7K4NbDmXcFSnYkqGIObBTak8DpJArVd3bIozQy8IXisM0wPOodcRLSVjvEFh7gloXN32Zz5XNELu44YH2xh9iR9DX-2Ba7RrO-2FCAGA-3D-3DMczc_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7rryWe1Fw4Z9UAWNSBnOAId6m0VE3dkWHM5inl26yGIE4CLAWkvhwlax0AcH5uF42fZ648LwSbUI10g75hNZ7Vnw0Ru1sijgXNIRqbeFOzu7YW-2B1ILLDtxlUd56Z9UB0beqAWpZnBJDYIpLWCLbQeUFc) to confirm CNIs, CoreDNS, and other dependencies are compatible.

- Take a [snapshot of etcd with Velero](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzeYeP5baQuGSGdiXmO-2FbKGK8FF0ATksRoR5peNut-2BENp36MIFqV4-2Fy9b-2BvnuiQuaZiigsrgLfPMCCbl7JKNC6dM-2Bvi096BNqz6yMolyOjybZalX41sL73gjLjCQJ4evMTT6DWRNMmbhFWx-2BlcMb4ayzUtoi2T-2FivneR-2FUUEZgQjYwzxLCiKzOaTk1aN5ERTx8RI7i7m-2FNAxw63rKXUyCdww5KT1OfiWDP2rsCI3yLPcpr00QQKLLx56EkNCk25Tgg-3D-3DMZGu_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7ro7UP9eehAWtfLnt-2BOq6EcRDVm52pKHfM5GTo3fsifIcbBArY5CsmLElFpE2SEYv4JVQJsEoQ9NWAwvvREkamNAv0Ji07ayEQA9rEHmYl12HvPhUpoL54XQ9wHL-2FdI89j0ghAp2P41t9v4XaPfyLrxA) to safeguard critical data and enable disaster recovery.

- Monitor the upgrade progress and [cluster health visually using Lens](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C4lAJV8et3iq-2Bc2DzMbCw-2BHH0cP7NmzCKPBHORNqLJvJS4nSdmsYKFvS73GkhVegB05czdmbQtk41Diunt21xdGRICtb6PX3W2t-2BaZDjn5RXUXaBy-2B3UUksmnTyP3gA6n1hCmSQbU-2FJzvE-2BWHdUzwypbctWqBPCVFn8CRHjusQJo-2BO-2BYddV14iJOYI4wVJVnJ1ECMbKbx5-2BSryS4wZKaycMF22tJIvcR8R2W1HBd7FDbLNrp_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7rrMiwkcsPrGS3r-2B3R03a0xkL2jc1P2-2Fs-2Bk1o9-2ByjBmWBrwLcCnYnGUFMGzsS2EB0dnuJFG-2BIcdml5Tzv-2F6G-2BEvZ8-2BwWciG98geU8FYolLsWq1kL-2BdMIJwgMvt3wNL8k696PnMDhFa3hg-2Fpj2oj6Qw12).

- Follow [Kubernetes upgrade documentation](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdZpm-2BHEHiy-2FRur25prjkyHRhhFeXYhw1AYqS6Rw6oVMtkEOAwCTHa0EEwH9-2BTkUBLSweXf3l3MQWGayfg5i8R2ZlXYcD4Dr8KE77z1lrzUkX1b9IycIwF-2Fu5udWDZuI9b6T4tkAmu26YQA-2B3HaEp42rcc69RXWmb7Wca9u7TzLYY4tJHz0ZBTFmj8QukFRZN6ar5DyKqGDWi4tTIFSxgq-2BnYXJP-2BRp-2BMcc8WzNOIyWhUwecDPWaxREuo95MOBBapnr6iVntXrv9cy0TbvS7LfR1iT0k_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7rrYo6LYl0QcskqqdKVbJ-2BG-2BulM-2BiMszdxi71dzRfyxqbsqVTJmnIUUR6iJ-2BcqY0jxs-2FnvcIpC9p-2BODg5vr0cHr3C63DWl2521ijxYRCrrsI0VOPnEhhaUpYbwXL-2Fd0vuIwrzdNlc0EIAlyrhwMiPE47) to upgrade the control plane and nodes sequentially.

- [Reboot nodes safely and automatically post-upgrade using Kured](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzfwVxrf6MFx46a1U9YQWmHFqF0rwpNKwvpsZc9vhRPUxAxwaJQzIDN2qG3PscFfOsMhBDj1nirdFio-2BSogzBec13dLbeM6Ley032CmQ8sHZr70xtNkRKsLDulaaFionV5CStHaNeZsEzVscceH87MRd1XCse4G1cVbwpy-2F7B1rs-2BXEtG-2BtUC5kWOsopb7kZhU6prp8iQhnKWCySQ2YI7P-2B4PaMDLQz-2FwSAGwXsk7ZqzL-Ie_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BujwJjgij-2FTSVhkujAO8yBNQZtz99NamnVf4EcX-2BhcHlqVurQCAw5oahYAOWFFs-2BRaTAXPF9KS53Dd4SqVdmUsWtz3YDL23H8-2B2ZjuiM6q5R8zzzz2txJo1edeVwTsCb-2FIarhsMfcc1nbfi2aGJ4RwRHd-2BkVhjUfLRRqEbx2wjFSP7-2FhteuoqUdbiUlJh59r1Uu61ckgiqCwRSrOoFPg4k7MHhwCawgb9VYY6G4fe7roNDtUHHHb30P1RJgDE8Kik0zvvO2bb3-2Bu58AXmGAfz0ImIwaqKKOmcqesUgmdr9xT-2F-2BDKoA1keHZNzFO3cssdOPr2VO4yx-2Bbk6HgizCyN3ZSlPiSHekHU5EbLCappQV6-2F8YsDJJB3kmR-2FmzoQ2VPsI) to apply OS updates.

\

**Worthy TLDR:**

| |
|-|
|**Can we skip minor versions and upgrade directly to the latest Kubernetes release?**<br />No, upgrades must follow minor versions sequentially.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|**How often should we upgrade Kubernetes to stay secure and supported?**<br />Every 12–14 months to stay within the N-2 support window.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|**Is it better to upgrade an existing cluster or create a new one and migrate workloads?**<br />For clusters behind by more than two versions, starting fresh is often easier.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

### **16Q. How Karpenter Feature Gates Helped on Black Friday?**<!-- {"collapsed":true} -->

| |
|-|
|My Black Friday experience this time is with an e-commerce platform, handling the typical objective: scaling quickly under heavy traffic while keeping costs low.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|We all know Karpenter is a great Kubernetes cluster autoscaler, designed to help dynamically manage workloads by provisioning nodes tailored to your requirements<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

![](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/cbd9e8b6-3b4c-48ef-a87d-034504fc4165.png) [^147]

\

And these were the challenges staring at me:

- Traffic could skyrocket at any moment, requiring immediate node scaling without delays.

- We heavily relied on Spot Instances. These instances could be reclaimed at any time, creating potential downtime.

- Over time, some nodes in the cluster could drift from their intended configurations, resulting in wasted resources.

- High workloads could stress some nodes to failure, requiring quick detection and repairs.

\

To tackle these challenges, I enabled three powerful Karpenter Feature Gates:

- **SpotToSpotConsolidation**:\
Migrates workloads from at-risk spot instances to more stable, cost-effective options before termination.

- **Drift**:\
Automatically detects misaligned or underutilized nodes and replaces them to maintain efficiency.

- **NodeRepair**:\
Automatically detects unhealthy nodes and repairs or replaces them without manual intervention.

- \

**Implementation:**

\

![d09bac4a-35ae-4390-a62b-8d9ef93a9d1f.png|647.0023193359375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d09bac4a-35ae-4390-a62b-8d9ef93a9d1f.png) [^148]

![4ba4fc00-5b1f-4eb3-b1e4-c8ce32d4f1b6.png|682.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4ba4fc00-5b1f-4eb3-b1e4-c8ce32d4f1b6.png) [^149]

\

**This configuration ensures:**

- Spot Instances are prioritized for cost savings.

- Instances match workload requirements.

- Empty nodes are terminated after 30 secs.

- SpotToSpotConsolidation is enabled via the consolidation.enabled parameter.

**Note**: We already configured and deployed Helm with the **Drift** and **NodeRepair** feature gates enabled. These parameters work automatically in the background and don’t need to be added to the Provisioner file.

\

![3d063d90-8306-428d-83f6-6d6cd628a51e.png|629.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/3d063d90-8306-428d-83f6-6d6cd628a51e.png) [^150]

\

\

### **17Q.** **Improving Kubernetes Latency with External Traffic Policy and Session Affinity?**<!-- {"collapsed":true} -->

When dealing with Kubernetes Services, achieving optimal performance often requires fine-tuning configurations.

\

In the basket of Kubernetes service configurations, you should know:

| |
|-|
|**External Traffic Policy:** Controls whether client IP is kept when traffic reaches your service.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|**Session Affinity:** Keeps a client connected to the same pod each time.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|And you can lower the latency with these settings.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
![59ea504f-6604-4ddb-94a9-abbea758885a.png|628.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/59ea504f-6604-4ddb-94a9-abbea758885a.png) [^151]

\

**1. externalTrafficPolicy: Local**

| |
|-|
|By default, it is set to Cluster, meaning traffic can be forwarded to any node, even if the pod doesn't exist on that node.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|This behavior introduces an additional network hop, increasing latency and losing the original client IP.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|By setting **externalTrafficPolicy to Local**, only nodes that host the service’s pods will receive external traffic.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**2. sessionAffinity: ClientIP**

By default, it is set to None, meaning that requests from a single client may be distributed randomly across all pods.

This behavior is ideal for stateless applications but can create challenges for the applications that depend on maintaining user sessions.

\

By configuring **sessionAffinity as ClientIP**, all requests from the same client IP address are directed to the same pod.

\

**When to Avoid**

| |
|-|
|[^152]<!-- {"cell":{"align":"left","color":"#2A2A2A"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) When cluster wide load balancing across all nodes is more important than latency.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) When the pods for your service are sparsely distributed across a subset of nodes, causing uneven load.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^153]<!-- {"cell":{"align":"left","color":"#2A2A2A"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) When you’re running stateless applications that don’t depend on session persistence.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) When a small number of clients generate a high volume of traffic, risking overloading a single pod.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) When your application relies on dynamic scaling, as session affinity can complicate traffic distribution.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

\

**Additional Considerations**

While configuring externalTrafficPolicy: Local and sessionAffinity: ClientIP improves service performance and user experience, a broader optimization strategy is needed to address stability and scalability.

\

**1. Node Placement Matters**

![21d37805-c5cf-428e-89b8-5c1e7ab01825.png|625.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/21d37805-c5cf-428e-89b8-5c1e7ab01825.png) [^154]

This setup ensures pods are spread across nodes, especially useful in high traffic applications like content delivery systems, where traffic must be evenly distributed to reduce load imbalances.

\

**2. Resource Requests and Limits**

Prevent resource contention by setting resource requests and limits in your deployment.

![4224bd40-5c70-41ca-90f2-6e68b797c32c.png|643.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4224bd40-5c70-41ca-90f2-6e68b797c32c.png) [^155]

This is particularly valuable for applications like payment gateways, where individual user sessions may generate significant resource load.

\

**3. Combine Network Policies for Security**

\

![95d1c1d6-92ad-4a4d-b3ff-1f0c1f2f280b.png|665.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/95d1c1d6-92ad-4a4d-b3ff-1f0c1f2f280b.png) [^156]

\

This is critical for applications like admin portals or private APIs where access needs to be restricted to specific IP ranges.

The attempt here is to know the options and understand the implications, but not a generalization.

\

\

### **18Q. How to Manage Secrets in CI/CD Pipelines?**<!-- {"collapsed":true} -->

Imagine your CI/CD pipeline is compromised.

![f5cd8e06-03de-4658-8f49-2c187b265afa.png|609.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/f5cd8e06-03de-4658-8f49-2c187b265afa.png) [^157]

\

Definitely, everyone picks the first choice (in a very true sense)

\

But when you read about incidents like the [Codecov breach that exposed secrets from environment variables in 1000s of enterprise pipelines](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C9dDmaCHGwpAGdgGKrVQm3SUePh0AYf-2FpJBa4yZV3aC6arXNzuzgtoV3KGIDEi7pleEMXC-2Bg5LBr7KBKoCOEt8B2WHHatWlKGsFk58ZaDu7fkENIZNy9idZY3lWolOdKaQl9rYy3nEzdm-2BS0hnVOU5QspIyBPdovWAXibdbAx3WGqNKY-2B32yiQ5i-2BMjYMYjSVbi39IVhbFTiqeVgNvtJoZ6K9iGQHYFN2Pm6TsWrwR4b79ibYQc-2BXJo6VZfSeyVrU6A4Nj0v53UzWkxYyqN-2BTgY-3D1zHj_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dvicMXETCzmY-2F5EiUq7a5sWBm-2FZ66pBSQIfLKfz4yArF40-2BZSkiLdfRvXKybNwgqt7b024N6GhmrlaHDAjvHSJqngHv092V3WkBGbJo-2FJ0s-2FdlwQlir6hW7oEy1fZalmYUFT2n8J3lyTcUfGFn1hipVjcIa3gQiZChnaOBmE9mzxvVDJQA-2BcPoNv7LwZsvk45vYJ3RGsBgRF99g5jAS6rDWAh6AMu5oKLQ-2BirlaTINo-2FecUbH1k3c4DN1zJfF-2F9d64jcu6HAad0i0jH-2BOeOH17blZm-2FfQubflq7EPCzNnPaSW-2FclkPfLkrErAh6zEt-2B3b2Eus7paePkhb6FzSnAAx6MWniwbQbc0a-2F562JC7j-2BDLksP0Nv85frSIXOzRn2lCSDzrrx1NP10VnjtZwrLwatFjn2G7iZnkpcE74EfnOzONdlac-2BcRKqWfOgjng69v4Oc5gFwyjmCp33GZqadjJf-2BRoP39cKZOL4F4rSkQlDhSs), we come to terms with the fact that, despite good intentions, this can happen to anyone.

\

Every engineer using CI/CD, regardless of their role, should read through and understand the [OWASP’s TOP 10 CI/CD Security Risks report](https://link.mail.beehiiv.com/ls/click?upn=u001.I5O8xwjn2EsC38CD0Ry7Ltx66i7FM50IZpQDlkiEibde527WXtWn-2BswkQ9FkMIpZzJhIJzrbA-2Bxfhw3wOmRKCdvHSmPPe8P9k3WXj6MeG8X6RnAJOTd7MC29SI6Fj1IDwOlbqQaCz2Tuyn3Ci-2FTd70QEG8-2B-2FXgr7cHGGqAPK83tbhNp8od2UIIyR2XwEynSSvpdPaDq9DRvM0u28C3Rj52dLJrNje0YUBzS2hCQQdR4KJEXSISNWTU7w95BfZnZAk97bttUbCGVI6UYP-2BQn3GLDBCQksFIUT7uv-2BhnAQG4lYzVlAkbUYp0wWNQdTdNPUGbmHslGq8VL6-2BHRS-2BoV-2BuWSGWLBpwv32s79vwIhuZJpI0OctflD8xxMKB7UYPO-2BjiOUt_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dvicMXETCzmY-2F5EiUq7a5sWBm-2FZ66pBSQIfLKfz4yArF40-2BZSkiLdfRvXKybNwgqt7b024N6GhmrlaHDAjvHSJqngHv092V3WkBGbJo-2FJ0s-2FdlwQlir6hW7oEy1fZalmYUFT2n8J3lyTcUfGFn1hipVjcIa3gQiZChnaOBmE9mzxvVDJQA-2BcPoNv7LwZsvk45vYJ3RGsBgRF99g5jAS6rDWAh6AMu5oKLQ-2BirlaTINo-2FecUbH1k3c4DN1zJfF-2F9d64jcu6HAad0i0jH-2BOeOH17blZm-2FfQubflq7EPCzNnPaSW-2FclkPfLkrErAh6zEt-2B3b2Eus7paePkhb6FzSnAAx6MWniwbQbc0a-2F562JC7j-2BDL0yKiqUopzOIhvwPIijn0l-2B58WiXWcGWtXcgSVgaqlOWFzgzAMZjewnPvqj28AmFXkKLTeP027hzFOCy0AifhxTp3YK8rdDgGQqc0DGI4L5dF90a73SdCNibovn-2BHbjpI) - this knowledge can solidify your SecOps expertise.

![8d89a8ea-8799-4c58-8a15-afe5d09fa320.png|685.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8d89a8ea-8799-4c58-8a15-afe5d09fa320.png) [^158]

\

**Actionable Insights to Improve Secrets Management Adoption**

\

**1. 12-Factor App Config Principle  -** Make up the mindset from the [Twelve-Factor App manifesto](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C7qNKvpAZcrvvJLX9Qs-2BpegGGDPHA9dyoh3RehD26zzDAPGYAnTUhHZ6Nq2DGNab8J2qUQ7-2F3Q5rkNcg0P2MTNgTJ2HdLIAwLntEGfM83VaRdYxfAq75GtBWQ0kfJ32bDgdLupw0wzCaAMb9dIxoQeEm08QxeiBFrSRZVi0nzpPkbYnYEZU75DCyhaaesSUjQk1cTPHWKXH3iH40g-2Fh-2FhULQ0FHc-2BxjtDOlFhgM6W12iS-2B0lTnxoA-2Fm615nBvqqhTw-3D-3D0TNx_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dvicMXETCzmY-2F5EiUq7a5sWBm-2FZ66pBSQIfLKfz4yArF40-2BZSkiLdfRvXKybNwgqt7b024N6GhmrlaHDAjvHSJqngHv092V3WkBGbJo-2FJ0s-2FdlwQlir6hW7oEy1fZalmYUFT2n8J3lyTcUfGFn1hipVjcIa3gQiZChnaOBmE9mzxvVDJQA-2BcPoNv7LwZsvk45vYJ3RGsBgRF99g5jAS6rDWAh6AMu5oKLQ-2BirlaTINo-2FecUbH1k3c4DN1zJfF-2F9d64jcu6HAad0i0jH-2BOeOH17blZm-2FfQubflq7EPCzNnPaSW-2FclkPfLkrErAh6zEt-2B3b2Eus7paePkhb6FzSnAAx6MWniwbQbc0a-2F562JC7j-2BDL0kxyz58y3-2FeRY7lTlczG-2ByynieEOfXps-2Bah-2BjLpTRMmShJgROfX-2Fu10kurI-2FcDjur1HxBvHnaM4-2Bt4XdBq2her3-2BUxyGqrm99grcFrKFD9cRC8-2FMxpjiufQ2kdBBQAK5) that configurations and secrets belong in environment variables. This practice keeps them easy to update between deployments and ensures your application remains clean and portable.

\

**2. Never Store Secrets in Plain Text -** Whether in your code, config files, or CI/CD pipeline definitions. If you can easily read it, so can anyone who gets access. Sure, you *can* define secrets directly in [GitHub Actions variables within the workflow YAML](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CxGpxcIONq9GvrPSiYzNLrF5NO8qWt50VICd4gqBEOtCNYl8hYhHDIdmzFM-2ByI5Rk4fI2dq5U2-2BHCll6RydqOxiyfv5pPtWEuY8bxiPjLm-2F3iLnCfFCHhC6vFe1e-2Fp-2BpKanAlcTPuJ33F39LyHr2EafBHKyHhBd2K-2FNK4afyGb-2FX5QwmM8c-2FupbXg8hdLTwv9VvzKZjcPWSUdwX5jqDRtWgaVJumjrC2JMoFJ0xMBReCyz6ZfPG-2B3-2BdWEjGz9yIAJQka8-2FZkkFXM7F49uUSwSsVfzD9-2ByAX-2F0RSUTNfEZUgV1WNhL8ZcDS1rdNs8lbSY1XzEUO0ogL9xO-2FKFf9VG8Pvg4O269gUkJ4PvyJFh9Xc5S9mIbrw9F02bPnBLAeNSbbF-2Fao3qFhjvz3KLY-2BftoA-2BJvbKLQk-2FPdZVGNsWTb7SZ4rfpaBnLg4ASDxphadPrjBBHdiEoTnTwnT-2BqvQT7d7Y-3DfCZc_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dvicMXETCzmY-2F5EiUq7a5sWBm-2FZ66pBSQIfLKfz4yArF40-2BZSkiLdfRvXKybNwgqt7b024N6GhmrlaHDAjvHSJqngHv092V3WkBGbJo-2FJ0s-2FdlwQlir6hW7oEy1fZalmYUFT2n8J3lyTcUfGFn1hipVjcIa3gQiZChnaOBmE9mzxvVDJQA-2BcPoNv7LwZsvk45vYJ3RGsBgRF99g5jAS6rDWAh6AMu5oKLQ-2BirlaTINo-2FecUbH1k3c4DN1zJfF-2F9d64jcu6HAad0i0jH-2BOeOH17blZm-2FfQubflq7EPCzNnPaSW-2FclkPfLkrErAh6zEt-2B3b2Eus7paePkhb6FzSnAAx6MWniwbQbc0a-2F562JC7j-2BDLokUHuoZJyKfNfOVx2AnCLl6WdHJZWBoRwe49lpLrKucp86vgofXGYCj0xAqgR6cWHZ45bBEB8Aw3Og5LAaVar6VP3sQ7R7C7p3p7MCxEbSZZidb-2Bt-2FQqt1ebJqwNCJ6P), but just because you can doesn’t mean you should.

\

**3. Use Encrypted Secrets -** Stop passing secrets directly in pipeline scripts. Instead, use encrypted secrets offered by CI tools like GitHub. It [securely encrypts secrets in the repository](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CxGpxcIONq9GvrPSiYzNLrHTSanKDV4v-2FRnHGWNbOtgFlwPLbGFNHOKQ3dR-2FgdnZpV8hUpRLyqKn3QNd41gCvHI2yJFTYxGEfXrPoZ5L8hffqjfYs5uwqEneuvMc3dDXq6-2F6Jnx8EB62ktZuNA-2Bo2VkXv4t1VTHLovgi0miZWwpxFApoIqJsug200vQPGu9NUk2ps5XyUlUm91U88ERQgs-2BhuMXOcfB0vPJiat7275slyl8FRq9OGM8OS7nzj5xtq0-2BeFHxeJ0s5t4yy8iISv7Ekvjlp5znBToSzzsjc-2BOx57TGYlSR-2FJmAfAczgewiOH7fIrImZSAQTzMOB58LIEKW-2BsIT7xUF3QnY5RFDGmVU-2BvoHV_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dvicMXETCzmY-2F5EiUq7a5sWBm-2FZ66pBSQIfLKfz4yArF40-2BZSkiLdfRvXKybNwgqt7b024N6GhmrlaHDAjvHSJqngHv092V3WkBGbJo-2FJ0s-2FdlwQlir6hW7oEy1fZalmYUFT2n8J3lyTcUfGFn1hipVjcIa3gQiZChnaOBmE9mzxvVDJQA-2BcPoNv7LwZsvk45vYJ3RGsBgRF99g5jAS6rDWAh6AMu5oKLQ-2BirlaTINo-2FecUbH1k3c4DN1zJfF-2F9d64jcu6HAad0i0jH-2BOeOH17blZm-2FfQubflq7EPCzNnPaSW-2FclkPfLkrErAh6zEt-2B3b2Eus7paePkhb6FzSnAAx6MWniwbQbc0a-2F562JC7j-2BDLIOl4SHhC-2BK8A9Hsz60jSLUuuTGxciqp9ifxdd2Q4pl6JsDjV7vdWbgVaXnp-2BIeNRkahu5LEfVVEOcTUlEGl-2FacAItCQQojtf8n8ksEnRKhSb2nwNKWHZLo42E3ntaKwj) and ensures they’re not exposed to runners during job execution.This is a no-brainer and takes minutes to set up.

\

**4. Regularly Rotate Secrets -** Change your secrets often. It's one of the easiest ways to keep them secure and prevent misuse.

\

**5. Give Least Privilege Access -** Only grant access to users and roles that need it. The less exposure, the safer your secrets.

![152d3d46-480d-4eac-8562-53a6ca92f7e2.png|615](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/152d3d46-480d-4eac-8562-53a6ca92f7e2.png) [^159]

\

**6. Centralize Secrets Management -** 

| |
|-|
|Some popular tools include:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^160]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

Personally, I’d go with HashiCorp Vault because:

- It works great across cloud and hybrid setups.

- It creates dynamic secrets that expire automatically.

- You can control exactly who gets access to what.

- It comes with cool extras like secret leasing and audit logs.

![e205198a-c274-44a2-b61e-5fc12904c7c7.png|761.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/e205198a-c274-44a2-b61e-5fc12904c7c7.png) [^161]

\

**Check out these guides to level up your secrets management with Vault:** [Retrieving CI/CD Secrets from Vault](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C9U6nSZtuHeYkIkvB2HvA1qEVPbCHXQ42mWEbKTA6BhAWh0UNSo7HpIgNttw8qWQkD-2FT24x4-2F2R2swRQiPd9UjFjtUrhq5vU9hn6SfJ25oHfZuk3DxU6fF0cgaKKBT28fpW5C4NA68QKweTf3YsZA-2B9KEaM3sFspSWCZqEy5YJRe7ePn2e7nkWpXljZ8weDm9r0enbAaGBDZvMBOCayFQ14LQ8BVuBJ2-2FNrQP1X4xrWjzHW6kdzfbhTg9Sb3Xv2c-2B8qjwAWZnDUc6HkFsvRVb1IXAtuAybNVcl9VK-2BI1MI98vJViI5TjtHwirFy7qwrBoA-3D-3DDrbv_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dvicMXETCzmY-2F5EiUq7a5sWBm-2FZ66pBSQIfLKfz4yArF40-2BZSkiLdfRvXKybNwgqt7b024N6GhmrlaHDAjvHSJqngHv092V3WkBGbJo-2FJ0s-2FdlwQlir6hW7oEy1fZalmYUFT2n8J3lyTcUfGFn1hipVjcIa3gQiZChnaOBmE9mzxvVDJQA-2BcPoNv7LwZsvk45vYJ3RGsBgRF99g5jAS6rDWAh6AMu5oKLQ-2BirlaTINo-2FecUbH1k3c4DN1zJfF-2F9d64jcu6HAad0i0jH-2BOeOH17blZm-2FfQubflq7EPCzNnPaSW-2FclkPfLkrErAh6zEt-2B3b2Eus7paePkhb6FzSnAAx6MWniwbQbc0a-2F562JC7j-2BDLtXtXsDL0LrnSfxxEkT-2FkXhwwavbixRfyNDA-2FrSlx8lKk3SrFSyI0Xhn7UuXxZ7zX0hyIv57sUiFXjjA-2FzLmK6G7rTxBn6agG-2FuPNvXLUelw0Zh7RbBOB3OQx6xrYCL8y) 

\

Step-by-step guide on securely fetching secrets from Vault in your CI/CD pipelines.

\

### **19Q. How to Structure Your Kubernetes Project?**<!-- {"collapsed":true} -->

Application designs, infra-architectures, and project structures are subjective decisions, and everyone has their own way, and even systems demand certain specifics – agreed!

\

Having said that, I strongly believe any design decision shouldn't be about NOW, rather about scalability, longevity, and futureproofing.

\

The **DRY (Don't Repeat Yourself)** Principle is one such crucial aspect that plays a significant role in this.

\

Every engineer should read the crisp version of [The Pragmatic Programmer by David Thomas and Andrew Hunt](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7Cw0bC4JBGf9sxQp5yej7tv7hmpfNZbHrQQe8Eh5vn4b8VZHtZB2uBqyKalWybirrWlqAYi4GKjxzykFMCfoKvyCsIE7yWpStnFpg3B1yN7ot6OIni1ei3h2p5cUdjLIf7-2BUGoFFnmetvDNihUTIyPTR1jeMLVedAARAWztXcXlpn-2FDvgpwehka-2FubjiB9njkOGynlL4-2BKv7SWCXK28TEYbCiWRWz7RtMc9gyAGr9qVRm-2B-2B00Pe0BBNbebGhRIhYDLf4Xo73aIE3vHwvWeshMqfk-3DqbMN_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dpQCP0tV75SJUQXvrYLErh-2FUmxKhafDLDkKtA-2Bb0PfX7d241iQ2Dd1cssLecJ9RdrAbOTnO6-2FNtiBaquaEsrMFv-2BpTRgddPIGmpjIed2gnyOHmRR34WQ4awbW-2FB0x2fJG-2BlmedkiH4Gy-2B6xqowDNIHnIdxh6A0VY70nINxBMPWrVhzUU0uHlkzsKMP8vA0X5sVmtpwmx9kuWsh-2BKVdKYniZZDnIzZ4to-2BvfKYofu5nVFrweHsEnocF5kklHQWa8XkmmCKCXnnwFjqC6WiGQ4GUJfVksX9YQN9MyxYZe-2FsMXe0sk6WEZZqswaPLw4MsmlbJLg3GIqvI8Ry028onpYduvsu84zWtCq5fPgrgLeAmKq97tOA45n-2B-2Bh9zskSIFKgHsOwd-2FfnATKEbhXQSNSIVJ-2FUwEV7VjL4vNhdcD1O4QOiCrNn8ao4VHmeMDEd1bDrrv8v-2BE2hfmsJTScEmTdP-2FI3jOZDOzgx18QbQVGeUizWs) - This helps to enhance your understanding to design scalable and less redundant systems.

\

In line with the DRY principle, here’s a directory structure you can adopt to organize your Kubernetes project for clarity, scalability, and operational efficiency.

\

![fc6f78eb-9f09-49a7-a022-317cf6493243.png|765](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/fc6f78eb-9f09-49a7-a022-317cf6493243.png) [^162]

\

**base/:**  Contains shared Kubernetes manifests that apply across all environments.

Example: deployment.yaml defines the core application deployment (image, ports, labels) used in every environment.

\

**overlays/:** Environment-specific configurations using Kustomize overlays.

Subdirectories like dev/, prod/, and staging/ override base/ configurations as needed.

\

**helm/:** Optional directory for Helm charts to template Kubernetes manifests.

Includes values.yaml (shared settings) and environment-specific values (e.g., dev-values.yaml).

\

Useful for teams preferring Helm over Kustomize.

\

To the parent directory, you can even add:

\

**apps/** - to host multiple application specific files.

**scripts/** - to host automation scripts like deploying, rolling back, and cleaning up resources

\

**How to Deploy to a Specific Environment:**

\

**Using Kustomize:** For deploying resources to a specific environment, you can apply the relevant overlay directory:

```
kubectl apply -k overlays/dev/
```

\

**Using Helm:** Specify the appropriate values file:

```
helm install techops-app ./helm -f ./helm/values/dev-values.yaml
```

\

**Verifying the Deployment:** After deployment, ensure the resources are correctly applied:

```
kubectl get all -n <namespace>
kubectl describe deployment <techops-app> -n <namespace>
```

\

**Things To Consider**

| |
|-|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) Deploy environment specific resources in their own namespaces to avoid conflicts.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) Adopt GitOps tools like ArgoCD or Flux for automated deployments.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) Encrypt secrets using tools like Sealed Secrets; avoid plain YAML files.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|![72.png\|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4cc/72.png) Maintain balance between shared and environment-specific configurations; avoid redundant directories.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

\

\

### **20Q. Why Did My Kubernetes Pod Stop Abruptly?**<!-- {"collapsed":true} -->

Our Pod is running along, doing its job, and then suddenly - it stops. No graceful shutdown, no clear reason. It’s frustrating.

![91080ce3-a65b-4751-ac5b-989dfa0d2b60.png|682.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/91080ce3-a65b-4751-ac5b-989dfa0d2b60.png) [^163]

\

In fact, more or less, we’re ready for the frequent and obvious ones like:

- Pod stops with 'Evicted' when disk pressure hits the node.

- Pod stops with 'OOMKilled' when the node runs out of memory.

- Pod stops with 'CrashLoopBackOff' when it keeps failing to start.

- Pod stops with 'ImagePullBackOff' when it can’t fetch the container image.

One of the clients reached out a while back for a consultation to solve this recurring issue.

**In a cluster, a critical Pod running a multi-threaded app intermittently failed without clear logs. It vanished as 'Failed' with a blank reason, while other Pods on the node seemed fine - until they weren’t.**

\

**What happened behind this mess-up?**

- Application spawned subprocesses without cleanup, leaving zombie processes behind.

- These zombies accumulated, exhausting all available PIDs on the node.

- Kubernetes couldn’t allocate PIDs for new Pods, causing abrupt failures.

- Basic processes like the pause container couldn’t start, resulting in Pod terminations with unclear logs.

\

[Process ID Limits and Reservations](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdZaKFD6FsJYNUzAK9P-2BJfRbHaflKzEcOk1p430UCPHrtBwPCQTfcgWTfDX2dUlmkarL1O3gzkES93LSdFWeKEJBTYHw-2BZt0R-2B8QtaK8Zs4o4sipqBQpN3euJ-2Fw1MhXYuG3cUwBp7WAJmG4Zp8cbYF1y4zBbCdhLYY2YYVh7gUByqkJBTk-2B5wUFuMux84kM9hTgGtNQD-2BLuuZrBA2CWNFlvwB5LuXDq53tuOZTKK8B-2BPgY9-2FrxT6PNarJt0oFtpofvk-3D3HQL_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dv-2FIcE5Ei-2FC10CK37pnA5fJ-2Bae21pWRhDZFR1RySWPKYR0KEkc6in-2BfnoeWDHRDIGsYD0eoIrJaRnees0OidpOKA4SRYnqqCxC7ioMx9PZ41IAbM2QFfkzlpRhna2pdci0Tqf6nA-2Bvs-2BMdB7kCZlcTj7byFdCT5uOdkJiBNtde3QWFUTlDilGmSbBIkl3OWV2l-2F1vSW20bnGLXDqLKTA3FkZ4j2JMso2sKT5Mfy2OtzKwLy1Nq8vRr-2FCgDL5-2BRQKvpLXn3xwj8UEBVoQk1h1WrcQC57U-2BrN2TyVAEMHD0aYpjarevrdZS8vcCYjMzY8OZvnNwtIzLC1-2BgnFbUriLbBAjBcAXfmZ5hYMLkkwUrv0NR8gvY5ay80di-2BgL7V0cchwd8kSshPqLwdfSuv1p9ZKYiyaGxRkmCtfhSJMJn-2BH7KfcUvC9G6btPHmpLZYHsg23jGIiFR8GlboWYILhVCgfa8j-2B00Y1T-2B6AQuHSWvZ8Sc) is a fantastic guide to help you understand PID exhaustion in Kubernetes.

\

This wasn’t a straightforward problem, but here’s how we cracked it:

\

**1. Analyzing the Node State -** SSH’ed into the node hosting the failing Pods and checked the available PIDs:

```
cat /proc/sys/kernel/pid_max
```

\

This showed a max limit of 32,768 PIDs.

\

Running processes (`ps aux \| wc -l`) revealed that nearly all PIDs were in use.

\

**2. Inspecting Zombie Processes -** looked for zombie processes (`stat` status `Z`):

```
ps -e -o pid,ppid,stat,cmd | grep 'Z'
```

Hundreds of zombie processes were tied to the legacy application.

\

**3. Identifying the Offending Pod -** Cross-referenced the zombie process PIDs with Pod logs to identify the application responsible for spawning these processes.

\

**4. Correlating with Kubernetes Events -** Ran `kubectl describe node <node-name>` to confirm `PIDPressure`. Kubernetes marked the node as unhealthy due to PID exhaustion.

\

**The Fix:**

- Increased node PID limit temporarily (`sysctl -w kernel.pid_max=4194304`).

- Fixed application to handle child processes and clean up zombies with s6-overlay.

- Isolated the legacy app to a dedicated node pool to protect other workloads.

\

OfCourse, this could have been completely avoided.

- Use a [process supervisor like s6-overlay](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzibIgOwVlkkU2sTwSQjf9NQxvOZGwwe-2B0zX9bnD7Bo-2BEdS5zUUv8V-2FC39XpWxhORM3dQi7GE15y-2F7Zxt-2F0Uw1-2BTIG8pPf75BkpRQHoiRMqC3HkZ8Xt-2FgtdM8IuIRzTnQ8Ui2XhAq8z7vOdirgPtQcWLN5oel-2BOO3ybu-2B9ORVdao-2Fw93QEKP0Ay62GNJHVAZhj6VBNv6m6Aw-2FaidRo1nbKhBkLJe-2BUlcC8FI2ODe45QalYuXb91Tgr-2FB683RJQ0y-2B2f15xXbOzv4PVC7lTDFUiU-3DhG9p_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7dv-2FIcE5Ei-2FC10CK37pnA5fJ-2Bae21pWRhDZFR1RySWPKYR0KEkc6in-2BfnoeWDHRDIGsYD0eoIrJaRnees0OidpOKA4SRYnqqCxC7ioMx9PZ41IAbM2QFfkzlpRhna2pdci0Tqf6nA-2Bvs-2BMdB7kCZlcTj7byFdCT5uOdkJiBNtde3QWFUTlDilGmSbBIkl3OWV2l-2F1vSW20bnGLXDqLKTA3FkZ4j2JMso2sKT5Mfy2OtzKwLy1Nq8vRr-2FCgDL5-2BRQKvpLXn3xwj8UEBVoQk1h1WrcQC57U-2BrN2TyVAEMHD0aYpjarevrdZS8vcCYjMzY8OZvnNwtIzLC1-2BgnFbUriLbBAjBcAXfmZ5hYMLkkwUrv0Ns638HoDsN1kcpxKeKSyvVqyEi-2BLGTuVFEBtAf-2BCf7GBeq7EmFhXgA4FUWDFz3atZrYXDzrReNcSCSofVrSImG07q4D4FestWryaE2JxG2vbSRcggU4Bf34hNEQeWeC0B) in containerized environments to manage child processes effectively.

- Low-density nodes can also hit PID exhaustion. Monitor `PIDPressure` with`kubectl get nodes -o wide`

\

### **21Q.** **Why Should You Design Pods for Stateless Applications?**<!-- {"collapsed":true} -->

| |
|-|
|Yes, you can run stateful workloads in a Kubernetes pod.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|But it’s not the recommended practice for most modern application designs.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|No one can deny that strong fundamentals in proven design patterns help design scalable, low-overhead applications<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

[Top 10 must-know Kubernetes design patterns](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2F-2F5hMzbqAH2PqBGWzp9yHkNFrNwFxynZMLxjL5sd5GQtI0As28PTPDtDi3aPIaWKsmJd4ShVbaZLahVKXSEKIxASws9ykrhp0ZG7Myf1XymQOzEEdpNVFH2SrdiQCAguLoZuFrWAa2iaR9D0g6QMGAFgLo1T99pjclVMo-2F-2B2gpTGr9PhJeNJZMY8KM2rsb2B2vR-2FJHInFNfGeHWVpnGAjxjjjCLlfLGtsjyR65suMha6Li-2FFhXnhFJcrg7W65-2B90bLxFu-2B0vHIMR3U-2F5rhIB0xC5NiPXwhreGhpLsYB05qoFQeOSfyMcKV8tvXDeZlGQu0m5ufeZbn1DATwzdBKBnw-3DyWi2_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7drSWBzbcRq5b6at72wQ5aaR0fgguLjZ28hY7pZTh8BMfdTNevh8z3kr-2BwzuG4FzYcokiFl-2B9TLoQStDclusyZpou0kbgamp9vnXJ2DyoVqnWv640yqdSwjDo5w-2BzepA-2B-2BaS6tuwyKQg8TJQ-2B4fj0pond40gi96-2B3p5qiZ6ln-2FwrrhYG3ZahzTHTe8doAsr6in248LU1U7gyFxTMQFVSnSkWhj8ZcgLaJg3iq-2F3-2BkhLLKQSqaHjlzCKJ7DyNfHiKKjwlq-2FVHorljbbVd8x8e6m1Q3BD-2Fuq14wwS-2BaoZISlbH-2Bt8gqgIOMTlDwl4N4OkeUcGLs38F29UDHv9f1y9yzYAVpfZ9-2FdYX0hqonCaJ1lZdJLdWl1-2Fuhx3ptW9J4RqoUIh-2BPUszJs8gxmT2tUirvMiivzVetpqWFZOaJFLQY4FauAwjkVjWTsE55SzzhXNyd5dHhrNX-2BeKPDwB8owblS9a3vtWpZo9MIuco9YJ5BpuqU) from Red Hat is a must-read, I can say, for every Kubernetes pro to strengthen and expand their design skills.

\

![](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/72ebad4c-aa8c-4aef-a80f-f9c3e9acdf06.png) [^164]

\

**Imagine These Scenarios** 

- You’re running a **MySQL database** directly in a Kubernetes pod, and a node failure causes the pod to restart. The data isn’t persisted because there’s no Persistent Volume attached.

- A team runs a **stateful file service** in pods with no redundancy or StatefulSet management. A pod reschedule causes inconsistent file storage across nodes.

- Your **application state** is tightly bound to pod memory. Scaling out creates duplicate or out-of-sync data across instances.

\

These scenarios are very common and can happen to any system.

\

**Why Design Stateless Pods?**

**1. Pods are Ephemeral -**Kubernetes treats pods as ephemeral. They can be terminated, rescheduled, or restarted at any time. Stateless design ensures no critical data loss.

\

**Example:** If a pod running a web server fails, Kubernetes quickly recreates it, and the request state is handled by an external load balancer or session store.

\

**2. Scaling Becomes Effortless -** Stateless applications can be horizontally scaled without concerns about shared state or data conflicts.

\

**Scenario:** A stateless NGINX deployment can scale up seamlessly to serve more HTTP traffic without worrying about session persistence.

\

**3. Clean Failure Recovery - Example:** In a Redis-backed API, failed pods reconnect to Redis without any loss of application state.

\

**Example:** In a Redis-backed API, failed pods reconnect to Redis without any loss of application state.

\

**4. Portability Across Nodes -** Stateless pods are portable and can be rescheduled on any node without configuration drift or dependencies.

\

**Scenario:** Kubernetes can move your pod to a different node during maintenance without breaking the application.

\

**What Happens When Pods are Stateful?  -** Running stateful workloads inside pods **violates core Kubernetes principles** like disposability and scalability:

- Pods storing data locally lose critical state.

- Stateful workloads cannot scale out horizontally without tight coordination.

- Data storage consumes extra pod resources, degrading performance.

- \

When stateful designs are unavoidable, carefully evaluate the trade-offs and proceed with caution:

| |
|-|
|[Handle Shutdown Gracefully](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C-2BkqbmB8ZQsEpP94vsfkyOv8KJ574G0wuUqYDNsKG8NSHgij0stq9S3jqcJXCU-2BX5gGJG6HDPmFUVj7OTMhUzToS5xcLABZYgd34U9KD-2FHY26aWOg-2Fl-2FXkl-2BiyvAjtyYweyjwZRooUMzD2gzoUgxFqjK1tbWOQB9wQnVUkjJ6E4mR4XZ-2BFH6lOlRMTxg86ar8WgViwiIzugcESjJ3WztVXtKb35XuAtAm7FCtD4idA-2BWnb-2F5KTKZdLnooLlGXfPoortxhPQ7ZGSBTcTQvMLb4JQ-3Djr9o_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7drSWBzbcRq5b6at72wQ5aaR0fgguLjZ28hY7pZTh8BMfdTNevh8z3kr-2BwzuG4FzYcokiFl-2B9TLoQStDclusyZpou0kbgamp9vnXJ2DyoVqnWv640yqdSwjDo5w-2BzepA-2B-2BaS6tuwyKQg8TJQ-2B4fj0pond40gi96-2B3p5qiZ6ln-2FwrrhYG3ZahzTHTe8doAsr6in248LU1U7gyFxTMQFVSnSkWhj8ZcgLaJg3iq-2F3-2BkhLLKQSqaHjlzCKJ7DyNfHiKKjwlq-2FVHorljbbVd8x8e6m1Q3BD-2Fuq14wwS-2BaoZISlbH-2Bt8gqgIOMTlDwl4N4OkeUcGLs38F29UDHv9f1y9yzYAVpfZ9-2FdYX0hqonCaJ1lZdJDIaMVhMQwF0SSa0xm4MCvm2sKJ9maPV7nwPg6A-2FOt16-2B7Hm4ktA9z0ujkplEKS4mCD2Q2MUcpvc2jIHCqYJ7LueOeTP1-2BxFIW1AiNxnICw-2B4k4EWGJjuMH4g1R3qwhXw), use `PreStop` hooks and SIGTERM signals to flush data and cleanly shut down stateful workloads before pod termination.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[Deploy stateful workloads with StatefulSets](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3YicjdaJGgK4bYnY90M69FT-2FT1ho1lwpofHw4fkOXm38oi0016OEXgAe-2BFIU9YHcuda2mtAZIQj8-2FW5nU4CaYGLj-2FY37Gtv713b3-2BBBviO8XeJvYYwd4MMWD8dfInqQL9i1bJr27QA6pbGCso7yFsw2nti1Xn-2BvhmPpdrIrPS8i2sLfqxHqEAzGqoV-2BTDCTmgKAAbLK35VEpNMvC1AQtFff2I0i27la6X8-2FRKW0voLtOzHuTwztqFDtax-2FximvRr8XYMGFvpxxuu5Zlxd9JofSoiIX94bS-2FUA-2FlkDbcrg0xDODusRQ-3D-3DIPJ8_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7drSWBzbcRq5b6at72wQ5aaR0fgguLjZ28hY7pZTh8BMfdTNevh8z3kr-2BwzuG4FzYcokiFl-2B9TLoQStDclusyZpou0kbgamp9vnXJ2DyoVqnWv640yqdSwjDo5w-2BzepA-2B-2BaS6tuwyKQg8TJQ-2B4fj0pond40gi96-2B3p5qiZ6ln-2FwrrhYG3ZahzTHTe8doAsr6in248LU1U7gyFxTMQFVSnSkWhj8ZcgLaJg3iq-2F3-2BkhLLKQSqaHjlzCKJ7DyNfHiKKjwlq-2FVHorljbbVd8x8e6m1Q3BD-2Fuq14wwS-2BaoZISlbH-2Bt8gqgIOMTlDwl4N4OkeUcGLs38F29UDHv9f1y9yzYAVpfZ9-2FdYX0hqonCaJ1lZdJFNo59sK8vTV0HXfm6iDua7KYxiw-2ByfCTyq-2FPApr0l5n7RMzm9df9LcLYH7lY6qC1-2B-2BAztm4dn1C4O-2BpTBVHV-2FkDhy7sugc2xzdGw0PbUqqlt3QdSiYyBKhyt98qQSkDu) to ensure stable network identities, predictable pod behavior, and persistent storage.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[Configure a Pod to Use PersistentVolumes](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3Yicjdb4sqbS4heXKapxSw6rcQmh9FbGAvtrnwcn95Bd8R63raCCX35f4Ukx9TYXCldMYigPAICGM6IJ9lGz4-2BwmIt6Xp2iNvoxBzYcXe4p-2F4IRZBMgvRsusd2p8UriZx4nVgndeN52mwUnm2Hm94oG89fmjAu9ypWnTdAj9cKcU-2Bl2rMsEGo2tOdRCU29lJVa-2Bei7xprMJjwEXJCsnbuhyRSMPamKRrBereT8v1Ek7REWdqF6tpKSb8g6cXwR8uP4F-2Bi-2BueqgL-2Bcj9uTdxe7LpZS9xZ4EoTofzDreYAeNHS5tM7zMoqwtrYEnf-2FdWhavswIOtlQ5h9fFDkSC1Fg5BHaCXm3_irh_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7drSWBzbcRq5b6at72wQ5aaR0fgguLjZ28hY7pZTh8BMfdTNevh8z3kr-2BwzuG4FzYcokiFl-2B9TLoQStDclusyZpou0kbgamp9vnXJ2DyoVqnWv640yqdSwjDo5w-2BzepA-2B-2BaS6tuwyKQg8TJQ-2B4fj0pond40gi96-2B3p5qiZ6ln-2FwrrhYG3ZahzTHTe8doAsr6in248LU1U7gyFxTMQFVSnSkWhj8ZcgLaJg3iq-2F3-2BkhLLKQSqaHjlzCKJ7DyNfHiKKjwlq-2FVHorljbbVd8x8e6m1Q3BD-2Fuq14wwS-2BaoZISlbH-2Bt8gqgIOMTlDwl4N4OkeUcGLs38F29UDHv9f1y9yzYAVpfZ9-2FdYX0hqonCaJ1lZdJlVsbWM-2FcuhbScMxSGUeEYDWCFXfw9FY1ypgpKq0ovW1Oi24zdk1mRvDtHItD4RY6HuXOGvmB-2BblYxIwEfW4APc-2FzY-2FZIY9t1i2Mb-2Bv9onEldI9WRzK-2FoOF8X64nicLg4) and Storage Classes to provide durable storage that survives pod restarts and node failures.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[Implement Health Checks](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3Yicjdb4sqbS4heXKapxSw6rcQmh9FbGAvtrnwcn95Bd8R63rWHKSFwQmLQz2FzRFvHHCQ28ZupFJHT6rksIfbff9krtC1zms86V3Dpw00FELltvn32cDkWVSkoG7HSObAzlgLCFRYcZm8F91G8RZ0VE-2B2YYhyUJ6CKTQMLTi1N6eV6-2BDkXPpuJw6rFB-2FLAvqiKahRd69-2Bx16i29CGnBfPuod7cvVAhPVT8gFLUKNg1jkegQ9vqeF3gPxorhwPeHCPebwvbamDodLUwydlE-2Bds8WRR3CPyn-2BhtfMNJLBaDl85rzk0XJpzwOgRmI6M1h185ex3ecP3cz-2FaBnAAYSeWWdEX6Toz--s_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BLsuK6uKRxcZUpXDm1yN7drSWBzbcRq5b6at72wQ5aaR0fgguLjZ28hY7pZTh8BMfdTNevh8z3kr-2BwzuG4FzYcokiFl-2B9TLoQStDclusyZpou0kbgamp9vnXJ2DyoVqnWv640yqdSwjDo5w-2BzepA-2B-2BaS6tuwyKQg8TJQ-2B4fj0pond40gi96-2B3p5qiZ6ln-2FwrrhYG3ZahzTHTe8doAsr6in248LU1U7gyFxTMQFVSnSkWhj8ZcgLaJg3iq-2F3-2BkhLLKQSqaHjlzCKJ7DyNfHiKKjwlq-2FVHorljbbVd8x8e6m1Q3BD-2Fuq14wwS-2BaoZISlbH-2Bt8gqgIOMTlDwl4N4OkeUcGLs38F29UDHv9f1y9yzYAVpfZ9-2FdYX0hqonCaJ1lZdJwJuOckXYBPWj9isDoq7I-2FV8ptdWAufFYM2x6MutsmInfozAdehMuyMjaY-2FlBIBWYJZK7IvQjTrCCDNxJ-2FwDpNJQvb72y5Lpz6LHGRLkcOCvh-2FKK8ZyLAtOrQZn-2Bh4Lom), add `readiness` and `liveness` probes to detect unresponsive pods early and maintain application stability.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
Try to design your kubernetes app to run **stateless** for better isolation, scalability, and resource efficiency.

\

\

### **22Q. Should You Use Ephemeral Containers in Production Environments or Not?**<!-- {"collapsed":true} -->

| |
|-|
|For someone new, ephemeral containers are a Kubernetes feature introduced in v1.16 (graduated in v1.25), primarily designed to assist with debugging live Pods.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Unlike normal containers, they’re not defined in the Pod spec upfront but are dynamically injected at runtime into an already running Pod.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|This ability makes them incredibly powerful for operational tasks like debugging.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**Key Features of Ephemeral Containers**

- Short-lived, transient containers.

- Easily injected into running Pods with `kubectl debug`.

- Share the same namespace and network as the main containers.

- Do not interfere with the Pod's lifecycle.

![efbba94f-ae85-4501-8f61-81f8b516f2c5.png|710](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/efbba94f-ae85-4501-8f61-81f8b516f2c5.png) [^165]

But it also raises questions about their suitability in production environments.

\

While it is true:

- **They** don’t require Pod restarts; they avoid downtime and application interruptions.

-  **Debugging** occurs in a dedicated container, protecting the application from accidental side effects.

- **You** can tailor ephemeral containers with preloaded tools to suit the troubleshooting needs (e.g., network sniffers, performance profilers).

- **They’re** only injected when needed and disappear after the issue is resolved.

\

Here - The Risks and Caveats of Using Ephemeral Containers

- **No Restart Guarantee** - meaning they are not ideal for persistent workflows.

- **Security Concerns** - can introduce vulnerabilities by exposing namespaces or sensitive data.

\

![72.png|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/2705/72.png) **Use Them When:**

- Debugging critical live systems where you need isolation.

- Running diagnostics without modifying existing application containers.

- Temporarily inspecting environments or workloads.

\

![72.png|40](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f6ab/72.png) **Avoid Them When:**

- Long-term fixes or monitoring tasks are needed.

- The debugging process risks sensitive production workloads.

- Your team lacks proper access controls for ephemeral containers.

**Hands-On Guide to Ephemeral Containers:**

![d49a97fc-bf97-4b16-b826-1e1883d82b35.png|564.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d49a97fc-bf97-4b16-b826-1e1883d82b35.png) [^166]

\

Refer to this guide, [debugging with an Ephemeral Debug Container](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzoEMTHGsgc5RDOw3Yicjdb1YWOmFGloYDUvxpXgkr-2BQymKW9CHNnGvRk1yI4AVvHlNnG9qHA-2FrArQpny5-2BkE5alcgCVa5ksPSchRP391mtkS2LBpO-2FxU0qSIJalYET0DRmAMuJ3hJ4S2TwW-2BuGOR5tulsL-2BiZwkbfVumdqnkrB1E21lSApmYQljpr43H1sZD-2BhVNih3VTJqNr8qBvfyxjy25Um-2BDDp1P7AwoMBvjkChrtnXdwekavSqfFWGE6gD-2FbhE4eCBWMmyf3prOTZ6vn6xeDde6CXfC0tiEUPSqfAlkSFNVShynJFOdojxwZbmmhaIBiUo4ERjAKZP0HMF6GiTrI6Qh8uAp0fl40TEb4WzJ6eeoxIn2INkp-2F8ghc5GVg-3D-3DZzcM_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BX0gpWRKe-2BDgz-2BUnM2HmnqcDlJnWmkQNy-2F9bmfGA8r-2BrAFIF5xcvZHvpkLU4K1U6yhsB6ShaoE2sRUKW4QmNvj37xh3HFyQ-2B7GAwntvwIVk8PxZexkQMrhVgS2XVn2f-2Bxfr5jBtI23xmWck6Rsw4iBpXMRfd3jGVqMZPnyqkFrU1B-2BZMl6fAI0YG4c2hr3tUts4IXIM0B47WOM4uAtEU7u7uAJXGlqqGynGuERQQo9bKqtAs4E3UnLuXZ6vEbOmYIaoDDpzWbwrUZM6WEYK10EcuGmdMYDK-2BJZoM6wdbb09E-2FrTuL-2BlgOgzLzj-2B0-2Fjvz1VkJdEcFLgRWfHofJ06y3xp-2FrDreOX1KcrdDxv-2F-2BCxOtaBMgbd0aO4-2BL6ooc-2FbxhX), to enhance your expertise on this topic.

\

\

### **23Q.** **Kubernetes Autoscaling - HPA vs VPA vs KEDA?**<!-- {"collapsed":true} -->

![f4da599c-c8ad-43c0-924d-77de5dc736d7.png|906.0879516601562](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/f4da599c-c8ad-43c0-924d-77de5dc736d7.png) [^167]

\

**1. Horizontal Pod Autoscaler (HPA):** HPA is the default choice for scaling Kubernetes workloads horizontally by adding or removing pods based on resource utilization or custom metrics.

- Continuously monitors metrics like CPU, memory, or custom metrics (e.g., request rates).

- Adjusts the **number of pod replicas** in a deployment based on predefined thresholds.

- Formula: `desiredReplicas = ceil(currentReplicas \* (currentMetricValue / targetValue))`.

\

**2. Vertical Pod Autoscaler (VPA):** VPA optimizes pod resource requests (CPU and memory) by learning from historical and real-time usage patterns.

- Analyzes resource utilization and suggests or directly applies changes to resource requests/limits.

- Modes:

    - **Auto**: Automatically applies resource recommendations.

    - **Initial**: Sets resource requests at pod creation only.

    - **Off**: Provides recommendations without applying changes.

\

**3. Kubernetes Event-Driven Autoscaling (KEDA):** KEDA extends autoscaling to handle event-driven workloads by scaling deployments based on external triggers like message queues, HTTP requests, or custom metrics.

- Integrates with external systems (e.g., Kafka, RabbitMQ) to fetch metrics and decide scaling.

- Uses `ScaledObjects` to define scaling rules and event sources.

| |
|-|
|For many workloads, a **hybrid approach** works best:<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^168]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
### **24Q.** **Optimizing Kubernetes Costs with Pod Disruption Budgets?**<!-- {"collapsed":true} -->

![84cbeb83-b2fb-44c6-8bdb-0d2f2aa22955.png|841.0994873046875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/84cbeb83-b2fb-44c6-8bdb-0d2f2aa22955.png) [^169]

\

| |
|-|
|However, it is easier said than done. "Right-sizing" involves a lot of measurements, techniques, and optimizations, making it a deep and vast subject.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|Let’s zoom into Pod Disruption Budgets (PDBs) in the Kubernetes cost optimization context.<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**Why Do They Matter?** PDBs ensure high availability during disruptions by defining the minimum number of pods that must remain available during maintenance or scaling events.

\

**But here’s the hidden cost**: Misconfigured PDBs can lead to over-provisioning, where unnecessary compute resources are reserved to meet overly conservative thresholds.

Optimizing PDBs, therefore, becomes critical in cost-saving strategies.

\

**Key Steps to Optimize PDBs for Cost Efficiency**

\

**1. Audit Your Workload Patterns**: Analyze pod lifecycles, scaling events, and traffic patterns using tools like **kubectl top pods** or Prometheus.

```
kubectl top pods --namespace=techops-prod
```

Check CPU and memory utilization trends to understand actual resource demands.

\

**2. Set Realistic PDB Thresholds:** Instead of blanket thresholds, tailor PDBs for different workloads.

```
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata:
  name: techops-pdb
spec:
  minAvailable: 70%
```

Use percentage-based thresholds (`minAvailable: 70%`) for dynamic workloads.

\

**3. Integrate with Horizontal Pod Autoscaler:**  Ensure PDBs align with HPA policies to avoid conflicts.

Example HPA:

```
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: example-hpa
spec:
  minReplicas: 2
  maxReplicas: 10
  metrics:
  - type: Resource
    resource:
      name: cpu
      targetAverageUtilization: 75
```

\

**4. Test Disruption Scenarios:** Use `kubectl drain` commands to simulate node maintenance and validate PDB behavior.

```
kubectl drain <node-name> --ignore-daemonsets --delete-emptydir-data
```

\

### **25Q.** **Kubernetes Deployment Strategies?**<!-- {"collapsed":true} -->

![11d4c853-3727-47c2-995d-e9e3b38b9d10.png|777.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/11d4c853-3727-47c2-995d-e9e3b38b9d10.png) [^170]

\

**1. Recreate:** Completely shuts down the old version before deploying the new one.

This approach is straightforward and resource efficient since it only runs one version of the application at a time.

**Caution:** Causes downtime, so avoid using it for production critical workloads.

\

**2. Rolling Update:** Gradually replaces old pods with new ones while keeping the application live, ensuring continuous availability.

This is ideal for stateless applications or services where zero downtime is critical, with the added benefit of built in rollback capabilities if issues arise.

**Caution:** Errors in the new version can propagate across all pods if not validated first.

\

**3. Blue Green:** Deploys the new version (green) alongside the current version (blue) and switches all traffic to the new version after validation.

This strategy is ideal for high stakes updates, as it allows seamless rollbacks while maintaining a stable fallback environment.

**Caution:** Requires double the resources temporarily, increasing operational costs.

\

**4. Canary:** Introduces the new version to a small subset of users first, gradually expanding its rollout based on successful performance.

This approach minimizes risk by limiting exposure to potential issues, making it a great fit for high-risk updates or performance validations.

**Caution:** Requires strong monitoring and traffic control systems to succeed.

\

**5. Shadow:** Mirrors live user traffic to the new version without affecting the production environment, enabling validation of changes under real world conditions.

This strategy is excellent for testing new versions without impacting users, especially when verifying system performance or stability.

**Caution:** Not suitable for applications involving database changes or stateful workloads.

\

**6. A/B Testing:** Splits traffic between two versions to compare performance, user experience, or feature adoption in real time.

This method is perfect for data driven decision making in feature rollouts, as it provides valuable insights into user behavior and feature impact.

**Caution:** Requires advanced traffic splitting tools and precise monitoring to analyze outcomes.

\

Also, keep in mind that strategies not implemented correctly bleed money and require significant manual effort to optimize Kubernetes workloads for the best possible costs.

\

\

### **26Q.** **Kubernetes POD Troubleshooting Tactics?**<!-- {"collapsed":true} -->

![d84d44ba-aedc-42c1-a4dc-b6be9066c84c.png|802.0949096679688](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d84d44ba-aedc-42c1-a4dc-b6be9066c84c.png) [^171]

\

**1. Check Logs**

```
kubectl logs <pod_name>
```

If your pod has multiple containers, specify one:

```
kubectl logs <pod_name> -c <container_name>
```

\

**2. Analyze Pod Status**

```
kubectl get pod <pod_name>
```

Look at the *STATUS* column.

If it shows *CrashLoopBackOff, ImagePullBackOff, or ErrImagePull*, you have clear hints on what to check next.

\

**3. Describe Pod**

```
kubectl describe pod <pod_name>
```

Look for warning events, scheduling failures, and container state details.

\

**4. Verify Pod Configuration**

A misconfigured pod can cause all sorts of issues. Review its YAML configuration.

```
kubectl get pod <pod_name> -o yaml
```

Check environment variables, resource limits, image versions, and volumes.

\

**5. Check Events**

Kubernetes events provide historical context on failures.

```
kubectl get events --sort-by=.metadata.creationTimestamp
```

Pay attention to events like *FailedScheduling, ImagePullBackOff, or OOMKilled*

\

**6. Validate Container Images**

Ensure your container images are correct and available:

Check if the image tag exists.

```
kubectl get pod <pod_name> -o jsonpath='{.spec.containers[*].image}'
```

Try pulling the image manually.

```
docker pull <image_name>
```

\

**7. Restart Pod** 

Sometimes, instead of deleting the pod, restarting the deployment helps.

```
kubectl rollout restart deployment/<deployment_name>
```

\

**8. Review Service Dependencies**

Pods may fail if dependent services are unavailable. Check the relevant services.

```
kubectl get svc
```

Ensure services are resolving correctly.

```
nslookup <service_name>
```

\

**9. Check Network Connectivity**

If your pod can’t communicate with another service, test connectivity.

| |
|-|
|[^172]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^173]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
|[^174]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
\

**10. Inspect Resource Usage**

If your pod is OOMKilled or throttled, check resource usage.

```
kubectl top pod <pod_name>
```

Compare with defined limits.

\

Following this structured approach, you save time, avoid frustration, and debug with confidence!

### **27Q. Kubernetes pods are ephemerals?**<!-- {"collapsed":true} -->

Yes, Kubernetes pods are considered ephemeral. This means they are designed to be temporary and can be created and destroyed as needed. Pods can be replaced or rescheduled by Kubernetes, especially in response to changes in the cluster, such as node failures or scaling events.

### **28Q. Kubernetes pod.yaml Practical Usage Guide?**<!-- {"collapsed":true} -->

Kubernetes Pods are the fundamental building blocks of containerized applications, and the pod.yaml file is how we define and control them.

Here I’ve broken down the structure of a pod.yaml for a simplified understanding.

![5d0774a7-fa56-4384-9df7-003a2873a697.png|796.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5d0774a7-fa56-4384-9df7-003a2873a697.png) [^175]

\

Simply writing a pod.yaml isn’t enough - understanding how to apply, modify, and optimize it can save you from unnecessary troubleshooting, resource wastage, and deployment issues.

\

Understand these pointers to get the most out of pod.yaml.

\

**1. Applying and Managing pod.yaml**

\

```
kubectl apply -f pod.yaml → Deploy a Pod
```

```
kubectl delete -f pod.yaml → Remove it
```

```
kubectl get pods, kubectl describe pod <pod-name> → Inspect
```

\

**2. Editing and Updating a Running Pod**

```
kubectl edit pod <pod-name> → Live editing (some changes require recreation)
```

```
kubectl apply -f pod.yaml → Updates only changed fields while preserving state
```

```
kubectl replace --force -f pod.yaml → Deletes and recreates the resource (disruptive)
```

\

\

**3. Dry Run and Validate Before Deployment**

```
kubectl apply --dry-run=client -f pod.yaml → Test changes without applying
```

```
kubectl apply --validate=true -f pod.yaml → Catch schema errors
```

\

**4. Defining Resource Requests and Limits**

Avoid OOMKills by setting:

```
resources:
  requests:
    cpu: "100m"
    memory: "256Mi"
  limits:
    cpu: "500m"
    memory: "512Mi"
```

\

**5. Prevent unnecessary downtime by PodDisruptionBudget (PDB)**

```
kind: PodDisruptionBudget
spec:
  minAvailable: 1
```

\

**6. Using Liveness, Readiness, and Startup Probes**

Auto restart failed Pods using:

```
livenessProbe:
  httpGet:
    path: /healthz
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 10
```

\

Your pod.yaml isn’t just a static definition, it's a powerful tool.

Mastering it means less debugging, fewer outages, and smoother deployments.

\

![0c594f54-bcab-4f5c-80b6-81ea7b8e454b.png|756.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/0c594f54-bcab-4f5c-80b6-81ea7b8e454b.png) [^176]


---

### **29Q. Understanding Kubernetes etcd Locks?**

Ever had a cluster where everything suddenly felt sluggish?

\

Deployments hang, API calls timeout, and you’re left staring at a screen wondering if someone secretly unplugged your control plane?

\

More often than not, the culprit is etcd, and more specifically, how Kubernetes interacts with it.

\

We all know [etcd](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzyhdsX8J13JBCFfY6ai45T0kEsIcyXTaf48aoGPByjyurAmK-2BuEO6bgRF7JVXXqOMf5zKa7sLUJea1I-2Brt-2BzNnhpykhVpY4ykcZvtQy7LPCfslSfS6iq2OSbd9m4-2B8PqSC5wqfKhdDPPXx7MvfD9K5F5t09W-2BQ7nzFoVYejiTkjvwBmKqj6F6l6ANpClEv1u38TBbE2GDj-2FzYroOFRIgguaDm2L6WYmpzd6EOmUyeCnSAGK_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B3zF895KVSqOzTn4PsahIY2xLLJp-2BAYS6U6FGRoS4qm8U3zaRobRDh2bjnJoE-2FgoOPltB8jgSE6Sd27n6A1VZWFLH-2BohhM-2BGzZmjm-2FljDCiUlAar83rtDIAd2xyGdeJC8X2haxCevfQhWq7Mqk4ftz83-2FS7ytUQ1ALZZ2ZfUDUsdk2iFX5OAZYVlWDThrg9d62LsmyMvKa7GYvUT6fNMpCMSLORMszXcoN43pKVgPbraLXHe1UMxdxFmGgEXrxsx8aE2rWIjsIfI16JwdQn-2FyHV1Xgn32YkcCtEVeFi4NLDmV70M-2BNHJV8LDBXIXDxwsX6j63yqc1-2BYkarETEEx7gnGIKJhWEPaw3JIAhf6SJ8CqUYAu-2FarlyYlhlyP38xOrS) is the brain of Kubernetes. It stores all the cluster state - nodes, pods, configs, secrets, and everything in between.

\

When you **kubectl apply** something, Kubernetes **updates etcd**.

The API server constantly reads and writes to etcd, making it the most critical component of your cluster.

\

If etcd slows down or goes down, your cluster feels it immediately.

\

Requests pile up, API operations fail, and even a simple pod reschedule can take forever. That’s where locking comes into play.

\

Let’s talk about etcd locks - a tool that can prevent disasters but, if misused, can also cause bottlenecks.

\

**Why Use etcd Locking?**

Imagine two processes (let’s say two controllers) trying to update the same resource in etcd at the same time.

\

Race conditions can lead to **inconsistent state** - one process overwrites another’s update, leaving your cluster in a weird half applied state.

\

**Locking prevents this.** It ensures only **one** process at a time gets to modify a key, avoiding conflicts and data corruption.

\

**How to Use etcd Locking**

etcd provides a lease based locking mechanism.

\

Here’s how it works:

1. Create a lease: Attach a TTL (time-to-live) to it.

1. Acquire a lock using the lease: This ensures only one holder at a time.

1. Operate on etcd keys safely.

1. Release the lock when done.

Example using etcdctl:

```
# Step 1: Create a lease with 10 second TTL
lease_id=$(etcdctl lease grant 10 | awk '{print $2}')

# Step 2: Acquire a lock using that lease
etcdctl lock --lease=$lease_id my-lock-key

# Step 3: Perform operations safely
etcdctl put my-key "some-data"

#Step 4: Release the lock (automatically expires if not renewed)
etcdctl lease revoke $lease_id
```

\

In a Kubernetes controller, you’d use a similar approach programmatically via the [etcd client library](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7CzbFPvG-2FoyHn3V-2FSAC4Jdh-2FqM0xww9K-2BaJP3e3cF7wOXO5I7RqKFlppaXmERaCXLJ7oZQHeGOm9obSv7fXMA37OqbeRe6hHB83fL6SxEh1rmGTDooSEzqZegxM9-2FDompdMFiBiUmQAN6sqHcnYTlKZ5yyer3YPE0GkY8qs3IKc2fIof4hcMZtT-2Bloak9Sn5Irab6bLerycLkm5mTrWe-2B00g2OvwI8Yepjh5S9u9Icfwh2P6BQbzaYG98lYkUFLsrBQ-3D-3Dqrvr_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2B3zF895KVSqOzTn4PsahIY2xLLJp-2BAYS6U6FGRoS4qm8U3zaRobRDh2bjnJoE-2FgoOPltB8jgSE6Sd27n6A1VZWFLH-2BohhM-2BGzZmjm-2FljDCiUlAar83rtDIAd2xyGdeJC8X2haxCevfQhWq7Mqk4ftz83-2FS7ytUQ1ALZZ2ZfUDUsdk2iFX5OAZYVlWDThrg9d62LsmyMvKa7GYvUT6fNMpCMSLORMszXcoN43pKVgPbraXTaettDAGZSjdXYGetCR1E8t83E1y4UNj7ieVktrHPlFwzgJOgNlSIq0UY8Mb4VhcGVmx3wHTpx5eNc5yXM-2Bi1UxquUnJZHU9hUNEXyPsLhmBNUnchlr7Anesba-2FUmopC0SxXkfitnB6XUmW4xBVO).

\

**When & Where to Use etcd Locking**

**Use it when:** 

- You have multiple controllers competing for the same resource.

- You need leader election in a custom operator.

- You want to **ensure atomic updates** in etcd.

- You’re writing data intensive workloads (e.g., storing pod metrics, events, etc.).

\

**Avoid it when:**

- You’re doing read heavy operations (locks add latency).

- The process holding the lock may fail often (leases expire, causing unintended behavior).

- You can achieve the same outcome with Kubernetes **leases** (e.g., leader election in controllers).

\

**The Caution Zone**

If multiple processes compete for a lock, delays stack up fast.

- If a process holding a lock crashes, the lease eventually expires. But if it restarts and reclaims it too soon, you might end up with a split brain scenario.

- A misconfigured TTL or failure to release locks can stall the system.

- etcd is **not a high throughput database**. Overuse of locks can lead to slowdowns in cluster operations.

\

# <mark style="background-color:#F8914D;">**Docker**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### **1Q. What is docker containerization?**<!-- {"collapsed":true} -->

- Containers are isolated from each other & System resources are shared.

- Containers uses resources based on demand & it does not use resources as VM's.

- Boot time is very less - Within seconds applications are available.

- Docker images are immutable Images ([it means they are **read-only** and cannot be altered once created](https://aws.amazon.com/compare/the-difference-between-docker-images-and-containers/)[1](https://aws.amazon.com/compare/the-difference-between-docker-images-and-containers/). Any modifications to an image result in the creation of a new version.)

- \

- Docker Image = Base OS (5mb to 250mb) + Application run time + Created users + Created a directory + Installed Application = Max 500MB.

- \

- We are moving Applications from monolithic to Microservices.

- \

- Microservices --> completely independent application which is 10/5MB. We don't need a VM to run a microservice. Containers are best approach. 

\

**Scenario:**

- Also Imagine, we crafted the perfect project on our laptop, do that code in production and then it doesn't work same. Oops, it worked on my machine, (Joke) hey but we can't ship our laptop to every customer.

- Docker is a magic box; Docker pack your application & all its friends like libraries and dependencies into single container. Now we can ship our containers (entire environment) to another system. So, with Docker our code runs same on our desktop or in cloud.

- **Set up once, run anywhere. No more drama it worked on my machine.**

- **Portability:** Containers runs in any place - our laptop, a testing server, a massive cloud environment.

- **Consistency:** Every container starts from same blueprint, quarantining an application always runs the same, no matter where it's deployed.

- **Efficiency:** Shares resources with the underlying system.

- **Agility:** Spin up new containers rapidly. Need to remodel? update a container and all copies immediately reflect the change.

\

\

![2020-06-17-19_02_38-M01_CKA_Docker_Overview_ed1-PowerPoint.png|572](https://k21academy.com/wp-content/uploads/2020/06/2020-06-17-19_02_38-M01_CKA_Docker_Overview_ed1-PowerPoint.png)

![Docker-Storage-Networking.png|748](https://k21academy.com/wp-content/uploads/2020/06/Docker-Storage-Networking.png)

\

### **2Q. Explain Docker Architecture?**<!-- {"collapsed":true} -->

- Docker is a tool that makes it easier to develop, deploy, and run applications by using containers. In simple terms, think of Docker as a way to package up your application with everything it needs (like code, libraries, and settings) into a "container." 

- This container can then run on any computer that has Docker installed, and it will work exactly the same way, no matter where it's run.

**### Key Components of Docker Architecture:**

1\. **Docker Engine:** Responsible for running and managing containers. Consists of daemon, REST API and CLI. It has two main components: 

       - **Docker Daemon**:  A background service that handles everything Docker-related. It manages containers, Images and more.

       **- Docker CLI:** The command-line interface that users interact with to manage Docker resources (like running a container, pulling an image, etc.).

2\. **Docker Images:** A read-only template that contains the application code, libraries, and dependencies needed to run your app. Images are the blueprint for containers.

3\. **Docker Containers:** These are instances of Docker images. When you run an image, it becomes a container. Containers are lightweight and can be easily started or stopped.

4\. **Docker Hub:** A cloud-based registry service where you can find Docker images created by others or share your own. It's like a marketplace for Docker images.

5\. **Docker Compose:** A tool that allows you to define and manage multi-container Docker applications. You describe the services that make up your app in a YAML file, and Docker Compose takes care of running them together.

6\. **Docker Networking:** Manages how containers communicate with each other and with the outside world. Docker sets up a default network for containers, but you can create custom networks too.

7\. **Docker Volumes**: These are storage units that allow containers to store data persistently, even after they are stopped or removed. Volumes are used to store the data that you want to keep even if the container is deleted.

In summary, Docker packages your application into containers that can run consistently across different environments, simplifying the deployment process and making it easier to manage software dependencies.

\

![44426863-22cb-4fa9-94ed-210806476f0c.jpg|687](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/44426863-22cb-4fa9-94ed-210806476f0c.jpg)

\

**Docker Architecture:**

![ebd1905b-1ed5-41df-8080-97dafa09b97d.jpg|649](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ebd1905b-1ed5-41df-8080-97dafa09b97d.jpg) [^177]

![f0df8362-a561-4f7f-b23a-1ef74337cb30.png|937](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f0df8362-a561-4f7f-b23a-1ef74337cb30.png) [^178]

\

### **3Q. Docker Best practices?**<!-- {"collapsed":true} -->

1. Always use official and verified docker images as a base image.

1. Use specific docker image versions.

1. Use small-sized official images.

1. Optimize caching for image layers when building an image.

1. Use a .dockerignore file.

1. Make use of multi-stage builds.

1. Use the least privileged user. Never build images with root privileges. 

1. Scan your images for Security Vulnerabilities.

\

### **4Q. Problems before Docker?**<!-- {"collapsed":true} -->

**Inconsistent Environment:** It works on my machine? That's because different computers can have different setups.

**Complex Dependency Management:** Apps need various libraries and tools to run, which can be a hassle to manage.

**Deployment Challanges:** Different environments might have different settings which could lead to problems when moving your app from development to production.

\

### **5Q. What is Docker port forwarding, and why is it important?**<!-- {"collapsed":true} -->

Docker port forwarding allows you to expose ports from your Docker container to your host machine. This is important for accessing services running inside a container from outside the container (A website accessing from outside using nginx web server(container), such as when you want to access a web application or database running inside Docker.

\

### **6Q. How do you expose a port in Docker?**<!-- {"collapsed":true} -->

You can expose a port in Docker using the `-p` or `--publish` flag when running a container. For example, `docker run -p 8080:80 myimage` maps port 80 in the container to port 8080 on the host.

\

\

### **7Q. What is the difference between the `-p` and `-P` options in Docker?**<!-- {"collapsed":true} -->

The `-p` option allows you to specify a custom port mapping (e.g., `-p 8080:80`), while the `-P` option automatically maps any exposed ports in the Dockerfile to random ports on the host.

\

\

### **8Q. How do you forward multiple ports in a Docker container?**<!-- {"collapsed":true} -->

You can forward multiple ports by using the `-p` flag multiple times. For example, `docker run -p 8080:80 -p 8443:443 myimage` forwards both port 80 and port 443 from the container to ports 8080 and 8443 on the host, respectively.

\

### **9Q. Can you explain how Docker networking works in relation to port forwarding?**<!-- {"collapsed":true} -->

Docker creates an isolated network for each container. By default, Docker containers communicate over a bridge network, which allows them to talk to each other without exposing ports externally. Port forwarding is used to expose specific ports of a container to the host’s network, making them accessible outside the Docker network.

\

\

### **10Q. How would you troubleshoot if a Docker container's port is not accessible from the host?**<!-- {"collapsed":true} -->

- Check if the port is correctly exposed using `docker ps`.

- Ensure there’s no firewall blocking the port on the host.

- Verify the service inside the container is running and listening on the correct port.

- Check if the container’s network mode might be restricting access (e.g., `host` network mode bypasses port forwarding).

\

### **11Q. What is the impact of Docker’s host network mode on port forwarding?**<!-- {"collapsed":true} -->

In `host` network mode, the container shares the network namespace with the host, meaning there is no need for port forwarding since the container's ports are directly accessible on the host’s network interface.

\

\

### **12Q. How does Docker handle port-forwarding in Swarm mode?**<!-- {"collapsed":true} -->

In Docker Swarm mode, services are distributed across nodes, and Docker uses a routing mesh to ensure that requests to published ports are routed to the appropriate container, regardless of which node it is running on. This abstracts away the complexity of port forwarding from individual nodes.

\

\

### **13Q. Can you describe a scenario where port forwarding might cause security concerns?**<!-- {"collapsed":true} -->

Exposing container ports to the outside world can lead to security vulnerabilities, especially if the service inside the container is not secured. It’s important to control access through firewalls and possibly restrict binding to localhost (`-p 127.0.0.1:8080:80`) if the service should only be accessible internally.

\

\

### **14Q. How would you handle port collisions when running multiple Docker containers?** <!-- {"collapsed":true} -->

To avoid port collisions, ensure that each container’s exposed port on the host is unique. This can be managed by assigning different host ports to each container or using a load balancer or reverse proxy to manage traffic to multiple containers using the same port inside the container.

\

\

### **15Q. What is Docker Inspect?**<!-- {"collapsed":true} -->

`docker inspect` is a Docker command used to retrieve detailed information about Docker objects, such as containers, images, networks, and volumes.

This command outputs the object’s configuration and state in JSON format, providing in-depth details that are useful for troubleshooting, monitoring, and understanding how a Docker object is set up.

\

Common Use Cases of `docker inspect`:

1. **Inspect a Container:**

    1. Command: `docker inspect <container_id or container_name>`

    1. Usage: Retrieve details about the container, such as its environment variables, network settings, volume mounts, and the current status (running, exited, etc.).

1. **Inspect an Image:**

    1. Command: `docker inspect <image_id or image_name>`

    1. Usage: Get details about the image, including its layers, the command used to create it, environment variables, and other metadata.

1. **Inspect a Network:**

    1. Command: `docker inspect <network_id or network_name>`

    1. Usage: See the network’s configuration, including connected containers, IP addresses, and subnet settings.

1. **Inspect a Volume:**

    1. Command: `docker inspect <volume_name>`

    1. Usage: Obtain information about the volume, such as its mount point, driver, and usage details.

\

### **16Q. What is docker File?**<!-- {"collapsed":true} -->

\

**Docker File** -- A declarative way of creating our own image...

\

A **Dockerfile** is a text file that contains a series of instructions to build a Docker image. It is essentially a script that automates the creation of Docker images by specifying the base image, software packages to be installed, environment variables, commands to run, and other configuration details.

\

**Key Instructions in a Dockerfile:**

- **`FROM`**: Specifies the base image to use (e.g., `FROM ubuntu:20.04`). It's the first instruction.

- **`RUN`**: Executes commands in the shell inside the image, typically used for installing packages (e.g., `RUN apt-get update && apt-get install -y nginx`).

- **`COPY` or `ADD`**: Copies files from the host into the image (e.g., `COPY . /app`).

- **`CMD`**: Specifies the default command to run when a container starts (e.g., `CMD \["nginx", "-g", "daemon off;"\]`).

- **`ENTRYPOINT`**: Similar to `CMD`, but used to configure a container that will run as an executable.

- **`EXPOSE`**: Informs Docker that the container listens on specific network ports at runtime (e.g., `EXPOSE 80`).

- **`ENV`**: Sets environment variables (e.g., `ENV APP_HOME /app`).

- **`WORKDIR`**: Sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions that follow (e.g., `WORKDIR /app`).

![c2450288-cd5c-4578-b50e-f88311cdc101.png|548](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/c2450288-cd5c-4578-b50e-f88311cdc101.png) [^179]

\

\

### **17Q. What is Docker Image?**<!-- {"collapsed":true} -->

**Docker Image** = Base OS (5MB-250MB) + application run time + created users + created a directory + installed application = max 500MB = immutable image = can take from DEV to PROD

\

A **Docker image** is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, environment variables, and configuration files. Docker images are the building blocks of Docker containers; they are used to create containers that can be deployed and run consistently across different environments.

Key Characteristics of a Docker Image:

- **Immutable**: Once built, a Docker image is immutable, meaning it cannot be changed. Any changes would require creating a new image.

- **Layered**: Docker images are composed of multiple layers, each representing a stage in the image's build process. These layers are cached, which makes image building efficient by reusing layers that haven’t changed.

- **Portable**: Docker images can be shared and run on any system that has Docker installed, making them highly portable and consistent across development, testing, and production environments.

- **Versioned**: Images can be versioned using tags, typically in the format `name:tag` (e.g., `nginx:1.19`, `node:14-alpine`).

**How Docker Images are Created:**

Docker images are usually created using a **Dockerfile**. When you run the `docker build` command with a Dockerfile, Docker reads the instructions in the file and creates an image layer by layer. Each command in the Dockerfile (like `RUN`, `COPY`, etc.) creates a new layer on top of the previous one.

Example Workflow:

1. **Write a Dockerfile**: Define the steps to set up your environment and install your application.

1. **Build the Image**: Use the `docker build` command to create an image from the Dockerfile.

1. **Run the Image**: Use the `docker run` command to create and start a container from the image.

**Example of a Docker Image:**

If you write a Dockerfile to set up a Node.js application, you might use the `node:14` base image. When you build the image, Docker would create a new image layer that includes Node.js, your application code, and any dependencies. This image can then be shared, deployed, and run on any system with Docker.

\

**Use Cases for Docker Images:**

- **Application Deployment**: Package an application with all its dependencies into a single image, ensuring consistent behavior across different environments.

- **Continuous Integration/Continuous Deployment (CI/CD)**: Automate the creation and deployment of images as part of a CI/CD pipeline.

- **Microservices**: Each microservice can be packaged into its own Docker image, allowing for independent development, testing, and deployment.

Docker images are a core concept in Docker, enabling the reproducible, scalable, and efficient deployment of applications.

\

\

### **18Q. what does RUN command do in Docker?**<!-- {"collapsed":true} -->

The `RUN` command in a Dockerfile is used to execute a command or series of commands during the image build process. It allows you to install packages, set up the environment, or perform any tasks that are needed for your application to run.

\

Each `RUN` command creates a new layer in the Docker image. This is important because it means that the results of the `RUN` command are saved in the image and can be reused in containers that are created from that image.

\

\

### **19Q. What is difference between RUN & CMD in docker?**<!-- {"collapsed":true} -->

RUN   --> Runs at the time of Image creation/building from Dockerfile

CMD  --> Runs at the time Container creation

systemctl commands will not work in containers

Ex:

![55d24192-8c42-46ab-8482-7ef33191568d.png|459](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/55d24192-8c42-46ab-8482-7ef33191568d.png) [^180]

\

\

### **20Q. what is Entrypoint?**<!-- {"collapsed":true} -->

- The `ENTRYPOINT` instruction in a Dockerfile specifies the command that will always be executed when a container starts. Unlike the `CMD` instruction, which can be easily overridden by passing a different command at runtime, `ENTRYPOINT` is designed to configure a container to run as an executable, making it more difficult to override without using the `--entrypoint` flag.

**When to Use `ENTRYPOINT`**

- **Use `ENTRYPOINT`** when you want to enforce a particular command to run as the primary process of the container, and you want this command to be consistent across all uses of the container.

- **Use `CMD`** to provide default arguments to the `ENTRYPOINT` command or when you want to allow users to override the command easily.

\

\

### **21Q. CMD vs Entrypoint?**<!-- {"collapsed":true} -->

`CMD` and `ENTRYPOINT` are both instructions in a Dockerfile that define what command should be executed when a container starts. However, they serve slightly different purposes and are used in different scenarios.

\

**`CMD`**

- **Purpose**: Specifies the default command to run when a container starts. It provides defaults for an executing container.

- **Override**: The command specified in `CMD` can be overridden by passing a command as an argument to `docker run`.

\

**`ENTRYPOINT`**

- **Purpose**: Configures a container to run as an executable. It specifies the command that always runs when the container starts.

- **Override**: The `ENTRYPOINT` command is not overridden by arguments passed to `docker run`, unless the `--entrypoint` flag is used.

\

**Using `CMD` and `ENTRYPOINT` Together**

- **Default Arguments**: When `ENTRYPOINT` is defined, `CMD` is often used to provide default arguments to the `ENTRYPOINT` command.

![9d618288-e8f1-4aea-966b-5b5ddd178b7f.png|817](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/9d618288-e8f1-4aea-966b-5b5ddd178b7f.png) [^181]

\

**Key Differences**

- **Override Behavior**: `CMD` can be easily overridden by passing command-line arguments to `docker run`. `ENTRYPOINT` cannot be easily overridden and is intended to run as the main command.

- **Use Case**: Use `ENTRYPOINT` when you want to define the main command for your container and don't want it easily overridden. Use `CMD` for default arguments to `ENTRYPOINT` or as the main command when you want it to be easily overridden.

\

### **22Q. what is expose instruction in docker?**<!-- {"collapsed":true} -->

The `EXPOSE` instruction in a Dockerfile is used to indicate that the container will listen on a specified network port at runtime. This instruction serves as a form of documentation for anyone who uses the image, letting them know which ports the application inside the container is intended to use. However, `EXPOSE` does not actually publish the port on the host; it just defines the port that the container will use.

\

If we want to see which port that docker image is using... then we can use expose instruction (this is only for information purpose only).

\

### **23Q. what is ENV instruction in Docker?**<!-- {"collapsed":true} -->

The `ENV` instruction in a Dockerfile is used to set environment variables inside a Docker container. These environment variables can be used by the applications running inside the container or can modify the behavior of commands within the Dockerfile itself.

\

![ec0a5176-60e3-47e5-8268-e54e70a110bd.png|740](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ec0a5176-60e3-47e5-8268-e54e70a110bd.png) [^182]

\

\

### **24Q. what is ARG instruction in docker?**<!-- {"collapsed":true} -->

The `ARG` instruction in a Dockerfile defines a build-time variable that users can pass to the Docker build process to customize the image creation. Unlike environment variables set with `ENV`, `ARG` variables are not persisted in the final image, meaning they are only available during the image build process.

![5785c489-6979-4915-aa3d-6f86755636df.png|501](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5785c489-6979-4915-aa3d-6f86755636df.png) [^183]

\

![1e612a2c-e321-45bf-9e1b-9a3cdbb2232a.png|1058.666748046875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/1e612a2c-e321-45bf-9e1b-9a3cdbb2232a.png) [^184]

**Key Points**

- **Scope**: The `ARG` variable is only available from the point it is defined in the Dockerfile. It can be referenced in subsequent `RUN`, `ENV`, and other Dockerfile instructions.

- **No Persistence**: Unlike environment variables set with `ENV`, `ARG` variables are not available in the running container, only during the build process.

- **Default Values**: If a default value is provided, and no override is passed during the build, the default value will be used.

**Practical Use Cases**

- **Customization**: Use `ARG` to customize the image build process, such as specifying different base images, versions of software to install, or configurations to apply.

- **Security**: Since `ARG` values are not persisted in the final image, they can be used for sensitive data that should not be exposed in the image, such as API keys or tokens used during the build process.

\

\

### **25Q. ARG vs ENV popular interview question?**<!-- {"collapsed":true} -->

Use `ARG` for build-time configuration that doesn’t need to persist in the image, such as setting a specific version of a dependency.

Use `ENV` for runtime configuration that needs to be accessible by the application or scripts running inside the container.

\

\

### **26Q. COPY vs ADD popular interview question?**<!-- {"collapsed":true} -->

Both are used to copy the files from local to image... but ADD have 2 extra capabilities

1\. It can directly download files from internet

2\. It can directly untar the tar files

\

\

### **27Q. User Instruction in Docker?**<!-- {"collapsed":true} -->

we should not use docker container with root users. if you do so its a security leakage and anyone can get the complete storage access.

\

\

### **28Q. What is WORKDIR in Docker?**<!-- {"collapsed":true} -->

The `WORKDIR` instruction in a Dockerfile sets the working directory for any subsequent `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions. It establishes the directory in which commands will be run, files will be copied, and scripts will execute.

\

**Key Points**

- **Path Creation**: If the specified directory doesn't exist, Docker will create it.

- **Context Switching**: The `WORKDIR` instruction allows you to change the working directory, making it easy to structure commands that depend on specific directories.

- **Inheritance**: Once set, the `WORKDIR` applies to all subsequent instructions in the Dockerfile unless it's changed again with another `WORKDIR` instruction.

![e42233b1-5bf4-419b-b6bb-6c003346a390.png|867](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/e42233b1-5bf4-419b-b6bb-6c003346a390.png) [^185]

In this example:

- `WORKDIR /usr/src/app`: Sets `/usr/src/app` as the working directory.

- `COPY . .`: Copies the contents of the current directory on the host into `/usr/src/app` in the container because the working directory has been set to `/usr/src/app`.

- `RUN make /usr/src/app`: Executes the `make` command in the `/usr/src/app` directory.

- `CMD \["./app"\]`: Executes the `./app` executable in the `/usr/src/app` directory when the container starts.

\

**Multiple `WORKDIR` Instructions:**

You can use multiple `WORKDIR` instructions in a Dockerfile to change the working directory at different stages.

![e3fbe365-916f-434b-9716-aa02a444aab2.png|914](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/e3fbe365-916f-434b-9716-aa02a444aab2.png) [^186]

\

**Best Practices**

- **Relative Paths**: If you use a relative path in `WORKDIR`, it's relative to the previous `WORKDIR`.

- **Consistency**: Use `WORKDIR` to keep your Dockerfile organized and make commands easier to understand, especially when working with multiple directories.

**Benefits**

- **Readability**: Makes the Dockerfile easier to read by clearly indicating where commands will be executed.

- **Efficiency**: Avoids repeating directory paths in multiple instructions, reducing errors and making the Dockerfile more concise.

### **29Q. ONBUILD Instruction in Docker?**<!-- {"collapsed":true} -->

The `ONBUILD` instruction in a Dockerfile is used to specify a command that will be executed when a child image is built from the image that contains the `ONBUILD` instruction. Essentially, it sets up a trigger for the next image build to perform a particular action.

\

**How It Works**

- **Parent Image**: The `ONBUILD` instruction is defined in a base or parent image Dockerfile. This instruction will not be executed when building the base image itself but will be triggered when another Dockerfile uses this base image.

- **Child Image**: When a child image is built from the parent image, any `ONBUILD` instructions specified in the parent image are executed during the build process of the child image.

![4cf8595d-8026-460d-b31d-5a74ccd15dce.png|659](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4cf8595d-8026-460d-b31d-5a74ccd15dce.png) [^187]

\

![148c59f4-b295-4462-8351-72a017d88e36.png|721](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/148c59f4-b295-4462-8351-72a017d88e36.png) [^188]

\

**Parent image creation**

![d8ff6b60-1a8a-4437-9a96-d9da70737a08.png|905.6666870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d8ff6b60-1a8a-4437-9a96-d9da70737a08.png) [^189]

\

**Child image creation (uses parent image)**

![dc473c62-9c60-4b8d-a003-c7d1c0a381f6.png|924.6666870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/dc473c62-9c60-4b8d-a003-c7d1c0a381f6.png) [^190]

\

![89ce30a6-6752-423e-aa95-571c7953700e.png|1024.666748046875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/89ce30a6-6752-423e-aa95-571c7953700e.png) [^191]

### **30Q. What is Docker Networking?**<!-- {"collapsed":true} -->

<mark style="background-color:#FFE0DC;">**Container cannot communicate each other through if they use docker default network**<!-- {"backgroundCycleColor":"1"} --></mark>

\

In docker we have two types of networking

1. host

1. bridge

In docker we use bridge networking, by default docker will create bridge networking

\

ROBOSHOP or any other project can create its own network.

\

<mark>**How to create network?**</mark> we should not use docker default network, we should create our own network

```
docker network create <network name>
docker inspect <container ID> | grep IPAddress
```

\

roboshop network got created(by default its a bridge network)

\

### **31Q. What is Docker compose?**

Docker compose will make it easy to maintain the docker containers.

\

Docker Compose is a tool that allows you to define and manage multi-container Docker applications. Instead of manually running each container with individual `docker run` commands, you can use Docker Compose to describe your entire application in a simple YAML file called `docker-compose.yml`

\

In this file `docker-compose.yml`, you specify the services (containers), networks, and volumes your application needs. Then, with a single command (`docker-compose up`), you can start all the containers together, making it easier to manage complex applications.

\

Compose works in all environments, production, staging, development, testing, as well as Cl workflows. It also has commands for managing the whole lifecycle of your application:

- Start, stop, and rebuild services

- View the status of running services

- Stream the log output of running services

- Run a one-off command on a service

```
docker compose up -d
docker compose down
```

![9439ccf9-04f0-42eb-9904-1e069f89aa22.png|817.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/9439ccf9-04f0-42eb-9904-1e069f89aa22.png) [^192]

\

| |
|-|
|**Key Features:**<!-- {"cell":{"align":"left","color":"#2A2A2A"}} -->|
|[^193]<!-- {"cell":{"align":"left","color":"#2D2D2D"}} -->|
### **32Q. Docker best practices?**<!-- {"collapsed":true} -->

1\. use official images

2\. reduce image size by using bare minimum OS like alpine, disto, core os, etc.

3\. use multi stage builds I

4\. use docker volumes to persist the data

5\. use custom network to isolate containers from other projects

\

### <mark style="background-color:#FFFFFF;">**33Q. What is multistage builds in Docker?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

It mainly used in java application, For usually java applications we will get the JAR file as Build, we will use one stage to build the JAR file. Now we will copy the jar file into another stage(build) where we will have only the JDK & JRE environment. so that we can reduce the image size. We don't need Maven in run time environment. 

\

![887e52ec-a93f-4954-9922-7166a678fc53.png|768](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/887e52ec-a93f-4954-9922-7166a678fc53.png) [^194]

![6d3c3f51-7c71-4e4d-b455-1cf214832864.png|740](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/6d3c3f51-7c71-4e4d-b455-1cf214832864.png) [^195]

### **34Q. Docker Volumes?**<!-- {"collapsed":true} -->

when you remove docker container, what happens to data? Containers ephemeral/temporary, data by default will be deleted...

Once we kill the docker container.. volume data will be auto deleted.For any stateful applications or databases we need to have the data....

\

Docker volumes are two types

1. Unnamed Volumes - <mark>**- generally we don't use this**</mark>

1. Names Volumes    --Just as we create networks, we can also create Docker volumes.

```
docker volume
docker volume create <volumename>
docker volume create nginx
docker volume inspect nginx
docker run -d -p 80:80 -v nginx:/usr/share/nginx/html nginx
```

### **35Q. Docker Layers - How docker works?**<!-- {"collapsed":true} -->

- **Layers in Docker** are like building blocks that make up a Docker image. Each layer represents a change or instruction in the Dockerfile (a script that contains commands to assemble an image).

- When you build a Docker image, Docker reads the `Dockerfile` line by line. Each command creates a new layer on top of the previous one.

How Layers Work

1. **Base Layer**:

    1. The first line in the `Dockerfile` usually specifies the base image (like `FROM ubuntu:20.04`), which forms the base layer. This layer contains a minimal operating system.

1. **Additional Layers**:

    1. Each subsequent command in the `Dockerfile` (like `RUN apt-get update`, `COPY . /app`, or `ENV VAR=value`) creates a new layer.

    1. ![11370cc3-a33f-46d5-8d26-820bad5c5736.png|810.9954223632812](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/11370cc3-a33f-46d5-8d26-820bad5c5736.png) [^196]

    1. These layers stack on top of each other, forming the final image.

**Layer Caching**:

Docker caches layers, meaning if a layer hasn’t changed, Docker uses the cached version instead of rebuilding it. This speeds up builds by reusing unchanged layers.

**Layer Reuse**:

Multiple images can share layers. For example, if two images use the same base image and run similar commands, Docker will reuse those common layers, saving space.

\

**Advantages of Layers**

- **Efficiency**: Layers allow Docker to build images quickly by reusing unchanged layers.

- **Modularity**: Each layer is independent, so changes to one layer don’t affect others unless they depend on it.

- **Storage Savings**: Since layers are shared across images, storage is used more efficiently.

![004e11a5-a365-4fae-aa33-5831c74207f4.png|891.9907836914062](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/004e11a5-a365-4fae-aa33-5831c74207f4.png) [^197]

\

### **36Q. Docker disadvantages?**<!-- {"collapsed":true} -->

![272239aa-6f8b-49d3-af12-5a28650234a8.png|995](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/272239aa-6f8b-49d3-af12-5a28650234a8.png) [^198]


---

# <mark style="background-color:#F8914D;">**GIT**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### **1Q. Explain GIT in simple words?**

Git is like a diary for your code. Imagine you're writing a book, and every time you make changes, you save a copy. Git lets you track these changes, go back to any version you saved, and even work with others on the same book without messing up each other's work.

It helps you:

1. **Save Versions:** Every time you make changes, you can save a "snapshot" or version of your code.

1. **Go Back in Time:** If you make a mistake, you can go back to any previous version.

1. **Collaborate:** If you're working with others, Git helps merge everyone's changes smoothly.

It's a tool that keeps your code organized and helps you manage changes efficiently.

![003d69a0-f8c0-4480-aba5-a5b6249d0714.jpg|526.9791870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/003d69a0-f8c0-4480-aba5-a5b6249d0714.jpg) [^199]

\

\

### **2Q. What is Git, and why is it useful?**

**Answer:** Git is a distributed version control system that allows multiple developers to track changes in source code during software development. It’s useful because it helps manage code changes, enables collaboration, and keeps a history of all modifications, allowing you to revert to earlier versions if necessary.

\

\

### **3Q. Explain the difference between Git and GitHub.**

**Answer:** Git is a version control system that runs locally on your computer, allowing you to track changes in your code. GitHub is a cloud-based hosting service for Git repositories that enables developers to store their code online and collaborate with others.

\

\

### **4Q. What is a repository in Git?**

**Answer:** A repository (or repo) is a directory that contains all the project files and the history of changes made to those files. It includes all the commits, branches, and tags associated with a project.

\

\

### **5Q. What is the difference between `git clone` and `git fork`?**

**Answer:** `git clone` creates a local copy of an existing repository from a remote source, while `forking` is a process on GitHub or similar platforms that creates a copy of someone else's repository under your GitHub account, allowing you to make changes without affecting the original repository.

\

### **6Q. How do you initialize a Git repository in a directory?**

**Answer:** You can initialize a Git repository in a directory by navigating to that directory in your terminal and running the command `git init`.

\

\

### **7Q. Explain the difference between `git add`, `git commit`, and `git push`.**

**Answer:** `git add` stages changes, preparing them for a commit. `git commit` saves the staged changes in the repository's history. `git push` uploads the committed changes from your local repository to a remote repository.

\

### **8Q. What is a commit, and what information does it contain?**

**Answer:** A commit is a snapshot of the project's state at a particular point in time. It contains the author’s identity, a commit message describing the changes, and references to the previous commit(s), along with the changes themselves.

\

### **9Q. What is the purpose of a branch in Git?**

**Answer:** A branch allows you to work on different features or fixes independently from the main codebase. Each branch is an isolated environment, enabling parallel development without affecting the stable version.

\

\

### **10Q. How do you create a new branch and switch to it?**

**Answer:** You can create a new branch using `git branch branch_name` and switch to it using `git checkout branch_name`. Alternatively, you can create and switch to a new branch in one step using `git checkout -b branch_name`.

\

\

### **11Q. How do you merge branches in Git?**

**Answer:** To merge a branch into your current branch, you use the command `git merge branch_name`. This will integrate the changes from `branch_name` into your current branch.

![230c4b3b-730f-4e9c-8c80-b2fd7508322c.png|345.9953918457031](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/230c4b3b-730f-4e9c-8c80-b2fd7508322c.png) [^200]

\

### **12Q. What is the difference between `git merge` and `git rebase`?**

**Answer:**   Merge preservers history, rebase Restructure history.   when in doubt just merge, Never use rebase on public branches.

![7d1a98b2-c7f3-4d01-aed3-847eedf56113.jpg|483.9930725097656](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/7d1a98b2-c7f3-4d01-aed3-847eedf56113.jpg) [^201]

\

**Merge:**

- **Combines branches**: Takes the changes from one branch and merges them into another.

- **Preserves history**: Keeps the history of both branches intact, so you can see all the individual commits.

- **Creates a new commit**: After merging, Git creates a new commit to signify that the branches have been merged.

*Example*: Imagine you have a main branch and a feature branch. When you merge, the main branch gets the changes from the feature branch, and Git shows that a merge happened.

\

### **Rebase:**

- **Reapplies commits**: Takes the commits from one branch and applies them on top of another branch, as if they were made in sequence.

- **Simplifies history**: The commit history becomes linear, without merge commits, making it cleaner.

- **No new commit**: Instead of a merge commit, it rewrites the commit history.

*Example*: If you rebase a feature branch onto the main branch, it looks like you made all the feature branch's changes directly on top of the main branch, making the history look like one straight line.

\

### **When to use what:**

- **Merge**: Use it when you want to keep a complete history and clearly see how and when branches diverged and came together.

- **Rebase**: Use it when you prefer a cleaner, linear history without extra merge commits, especially for long-running branches.

\

\

### <mark style="background-color:#F8D616;">**13Q. FastForward Merge** in bitbucket not in GitHub? convey in any interview we use FastForward merge in our projects and using bitbucket.<!-- {"backgroundCycleColor":"25"} --></mark>

![what-is-a-fast-forward.gif|672.9977416992188](https://bitbucket.org/blog/wp-content/uploads/2018/06/what-is-a-fast-forward.gif)

A **fast-forward merge** in Git is like moving a bookmark forward in a book.

\

**Imagine**:

- You have two branches: `main` and `feature`.

- The `main` branch is like a bookmark in a book, marking where you are currently.

- The `feature` branch is some new changes you made.

**What happens in a fast-forward merge:**

- If the `main` branch hasn't moved since you created the `feature` branch (meaning no new changes have been added to `main`), Git can simply move the `main` branch's "bookmark" forward to the latest commit in the `feature` branch.

- This means there's no need to create a new commit to combine the branches—it's like fast-forwarding a video; you just jump ahead to the new point.

**Result**:

- The history stays clean and linear, as if all the changes were made directly in the `main` branch.

In short, a fast-forward merge is a way of integrating changes that keeps the history simple and straightforward, without adding extra commits.

![18602b10-a3f0-4b23-8959-6fda153ed2fe.png|339.9884338378906](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/18602b10-a3f0-4b23-8959-6fda153ed2fe.png) [^202]

\

\

### **14Q. How do you resolve a merge conflict in Git?**

**Answer:** When a merge conflict occurs, Git will mark the conflict in the affected files. You need to open the files, manually resolve the conflicts, and then mark the conflicts as resolved using `git add`. Finally, you commit the resolution with `git commit`.

\

![3f6023a2-9f9e-4a40-81bf-64f4c060dc6d.jpg|752.9977416992188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/3f6023a2-9f9e-4a40-81bf-64f4c060dc6d.jpg) [^203]

### **15Q. Explain the difference between `git pull` and `git fetch`.**

**Answer:** `git fetch` downloads changes from a remote repository but doesn’t merge them into your working directory, allowing you to review them first. `git pull` does both: it fetches changes and automatically merges them into your current branch.

\

\

### **16Q. What is the difference between `git reset` and `git revert`?**

**Answer:** `git reset` moves the HEAD to a previous commit, effectively undoing all commits after that point. `git revert` creates a new commit that undoes the changes of a specific commit, preserving the commit history.

\

\

### **17Q. How can you see the history of commits in a repository?**

**Answer:** You can see the commit history using the command `git log`. This will display a list of commits in reverse chronological order.

\

\

### **18Q. What does `git stash` do, and how do you apply a stash?**

**Answer:** `git stash` temporarily saves changes that are not ready to be committed, allowing you to work on something else. You can apply the stash later using `git stash apply`.

\

\

### **19Q. How do you undo a commit that has already been pushed to a remote repository?**

**Answer:** You can undo a commit by using `git revert commit_hash`. This will create a new commit that reverses the changes introduced by the specified commit.

\

### 

### **20Q. What are Git hooks, and how are they used?**

**Answer:** Git hooks are scripts that run automatically in response to certain events in a Git repository, like commits or merges. They can be used to enforce coding standards, run tests, or perform other automated tasks before or after certain Git operations.

\

### 

### **21Q. How do you rebase a feature branch onto another branch?**

**Answer:** You can rebase a feature branch onto another branch by checking out the feature branch and running `git rebase branch_name`. This will replay the commits from the feature branch onto the head of `branch_name`.

\

\

### **22Q. What is the purpose of a `.gitignore` file?**

**Answer:** A `.gitignore` file specifies intentionally untracked files that Git should ignore. This includes files generated during the build process, sensitive files, or environment-specific configurations.

\

\

### **23Q. What is the difference between `git pull --rebase` and `git pull`?**

**Answer:** `git pull --rebase` fetches changes from the remote repository and then rebases your current branch onto the fetched changes, creating a linear history. `git pull` merges the changes into your current branch, which may create a merge commit.

\

\

### **24Q. Explain the concept of `reflog` and how you can use it to recover from mistakes.**

**Answer:** `reflog` is a record of all the changes made to the tips of branches and other references in your repository. It allows you to recover commits and branches that may have been deleted or reset.

\

\

### **25Q. How do you squash commits, and why would you want to do that?**

**Answer:** You can squash commits using `git rebase -i` (interactive rebase). Squashing combines multiple commits into one, which helps to clean up the commit history before merging into the main branch.

\

\

### **26Q. What are Git tags, and how do they differ from branches?**

**Answer:** Tags are pointers to specific commits, often used to mark releases. Unlike branches, tags do not change or move with new commits. They serve as fixed points in the commit history.

\

### 

### **27Q. What is Git bisect, and how can it be used to find a bug?**

**Answer:** `git bisect` is a binary search tool that helps you find the commit that introduced a bug by automatically checking out and testing commits between a known good and bad commit.

\

\

### **28Q. How do you set up a remote tracking branch?**

**Answer:** You can set up a remote tracking branch by using `git checkout -b branch_name origin/branch_name`. This creates a local branch that tracks the remote branch.

### 

\

### **29Q. How would you handle a situation where two developers have made conflicting changes to the same file?**

**Answer:** I would first pull the latest changes from the remote repository, resolve the merge conflicts by editing the file, and then commit the resolved changes. Communication with the other developer is also crucial to ensure both parties understand the changes.

\

\

### **30Q. You accidentally committed sensitive information (like passwords) to a public repository. What steps would you take to remove it?**

**Answer:** I would use `git filter-branch` or `git filter-repo` to remove the sensitive information from the entire commit history, and then force-push the changes using `git push --force`.

\

\

\

\


---

# <mark style="background-color:#F8914D;">**Terraform**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### **1Q. What is Terraform? Why is it used?**

1. **Answer**: Terraform is an open-source Infrastructure as Code (IaC) tool developed by HashiCorp. It allows users to define, provision, and manage infrastructure using declarative configuration files. Terraform can be used to manage infrastructure across various cloud providers (e.g., AWS, Azure, GCP) and on-premise data centers.<!-- {"indent":1} -->

\

### **2Q. How does Terraform differ from other Infrastructure as Code (IaC) tools like AWS CloudFormation or Ansible?**

1. **Answer**:<!-- {"indent":1} -->

    1. Terraform is multi-cloud and supports a wide range of providers, while CloudFormation is specific to AWS.<!-- {"indent":2} -->

        1. Terraform uses a declarative approach to define infrastructure, while Ansible can be both imperative and declarative.

        1. Terraform stores state and keeps track of changes, while Ansible doesn’t maintain state.

\

### **3Q. What is a provider in Terraform? Can you name a few common ones?**

1. **Answer**: A provider in Terraform is a plugin that enables Terraform to manage and interact with APIs from cloud platforms or services. Common providers include AWS, Azure, Google Cloud, Kubernetes, and GitHub.<!-- {"indent":1} -->

\

### **4Q. What are the different stages of a Terraform workflow?**

1. **Answer**:<!-- {"indent":1} -->

    1. `terraform init`: Initializes the working directory and downloads necessary provider plugins.<!-- {"indent":2} -->

        1. `terraform plan`: Creates an execution plan showing what actions Terraform will take.

        1. `terraform apply`: Executes the actions defined in the plan to modify the infrastructure.

        1. `terraform destroy`: Removes all resources defined by the Terraform configuration.

\

### **5Q. How does Terraform handle state, and why is it important?**

1. **Answer**: Terraform uses a state file (`terraform.tfstate`) to keep track of the infrastructure it manages. This state file ensures that Terraform knows the current status of resources, allowing it to make informed changes without disrupting existing infrastructure.<!-- {"indent":1} -->

\

### **6Q. Explain the purpose of the `terraform.tfstate` file.**

1. **Answer**: The `terraform.tfstate` file stores the mapping between Terraform resources and the real-world infrastructure. It is used to determine changes during `terraform plan` and `terraform apply` commands.<!-- {"indent":1} -->

\

### **7Q. What is the `main.tf` file in Terraform?**

1. **Answer**: The `main.tf` file typically contains the primary configuration code for Terraform. It defines the resources, modules, and providers that will be deployed.<!-- {"indent":1} -->

\

### **8Q. What is the purpose of `variables.tf` and `outputs.tf`?**

1. **Answer**:<!-- {"indent":1} -->

    1. `variables.tf` is used to define input variables, allowing dynamic configuration.<!-- {"indent":2} -->

        1. `outputs.tf` is used to define output values that display information about resources after the configuration has been applied.

\

### **9Q. What are the advantages of using Terraform over manually provisioning infrastructure?**

1. **Answer**: Terraform automates infrastructure provisioning, ensuring consistency, scalability, and reproducibility. It reduces human errors, supports version control, and enables infrastructure to be managed like code.<!-- {"indent":1} -->

\

\

### **10Q. What are the pros and cons of local vs. remote state storage?**

**Answer**:

**Local state** is simple and fast but can cause issues with team collaboration.

**Remote state** (e.g., S3, Azure Blob Storage) allows collaboration and provides state locking but adds complexity and requires network connectivity.

\

\

### **11Q. How does Terraform ensure that your state is up-to-date with your actual infrastructure?**

**Answer**: Terraform refreshes the state by comparing the actual infrastructure to the state file during the `terraform plan` and `terraform apply` phases. Any detected changes are highlighted in the plan.

\

\

### **12Q. What is state locking in Terraform, and why is it important?**

**Answer**: State locking prevents concurrent operations on the same state file, which helps avoid conflicts and data corruption. Remote backends like S3 with DynamoDB can enable state locking.

\

\

### **13Q. What are some best practices for managing Terraform state?**

**Answer**:

Use remote backends for state storage.

Enable state locking.

Version control the state file.

Avoid manual modifications of the state file.

\

\

### **14Q. Explain the concept of a “module” in Terraform.**

**Answer**: A module is a reusable set of Terraform configurations. It allows you to group resources and use them across different projects. This helps maintain consistency and reduces code duplication.

\

\

### **15Q. How do you define and use variables in Terraform?**

**Answer**: Variables are defined using the `variable` keyword in a `.tf` file. They can be assigned values through environment variables, `.tfvars` files, or command-line arguments. 

Example:

![4e26c5e4-57da-4ba3-9b17-af04970e258f.png|762.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4e26c5e4-57da-4ba3-9b17-af04970e258f.png) [^204]

\

### **16Q. What is the difference between input variables and output values?**

**Answer**: Input variables are used to pass dynamic values into Terraform configurations, whereas output values provide information about resources after the infrastructure is provisioned.

\

\

### **17Q. How do you share variables between different modules?**

**Answer**: Variables can be passed from one module to another by defining them as outputs in one module and referencing them as input variables in another module.

\

\

### 18Q. **What are Terraform providers, and how do they work?**

**Answer:**\
Providers are plugins that allow Terraform to interact with cloud platforms, SaaS, or other APIs. Terraform uses providers to manage resources (e.g., AWS, Azure). Providers are declared in configuration files and automatically downloaded during initialization.

\

### 19Q. **What are the different components of Terraform?**

**Answer:**

- **Providers:** Plugins that allow interaction with platforms.

- **Resources:** Infrastructure components like VMs, databases.

- **Modules:** Reusable containers for resources.

- **State:** A file to track infrastructure.

- **Data Sources:** To retrieve or compute information.

\

### 20Q. **How does Terraform manage state?**

**Answer:**\
Terraform uses a state file (`terraform.tfstate`) to map real infrastructure to configurations. The state is crucial for determining changes to resources and improving performance. State can be stored locally or remotely (e.g., S3), enabling collaboration.

\

### 21Q.**What is a Terraform module and why is it important?**

**Answer:**\
A Terraform module is a reusable collection of resources. It helps with code reuse and standardization. Modules can be local or pulled from remote repositories like the Terraform Registry.

\

### 22Q. **Explain the difference between `terraform apply` and `terraform plan`.**

**Answer:**

- **`terraform plan`:** Shows a preview of what changes Terraform will make, without applying them.

- **`terraform apply`:** Executes the changes and provisions the infrastructure as per the plan.

\

### 23Q.**What is the purpose of `terraform init`?**

**Answer:**\
`terraform init` initializes the working directory, downloads required providers, and prepares the backend configuration. This is the first step before any other command like `plan` or `apply`.

\

\

### 24Q. **What are backends in Terraform? Why are they used?**

**Answer:**\
Backends determine where and how state is stored (locally or remotely). Remote backends, such as S3 or Consul, help in collaboration and state locking, avoiding conflicts in teams.

\

\

### 25Q. **What is a Terraform workspace?**

**Answer:**\
Workspaces allow management of multiple environments using the same configuration, with each workspace having its own state file. This helps in separating environments like dev, staging, and production.

\

\

### 26Q. **How does Terraform handle resource dependencies?**

**Answer:**\
Terraform automatically creates a dependency graph based on resource configurations. You can explicitly define dependencies using `depends_on`, ensuring resources are created in the correct order.

\

\

### 27Q. **What is `terraform import` and when would you use it?**

**Answer:**\
`terraform import` brings existing infrastructure under Terraform management without destroying it. This is useful for managing resources created outside of Terraform.

\

\

### 28Q. **What are the best practices when using Terraform?**

**Answer:**

- Use modules for reusable infrastructure.

- Store state remotely and securely.

- Follow least privilege principles for roles managing Terraform.

- Use variables and outputs for flexibility.

- Use `terraform fmt` for formatting.

- Version control Terraform configurations.

\

### 29Q. **What is the `terraform taint` command used for?**

**Answer:**\
The `terraform taint` command marks a resource as needing recreation during the next apply. It forces Terraform to destroy and recreate the specified resource.

\

\

### 30Q. **How do you handle sensitive data in Terraform?**

**Answer:**\
Sensitive data should be managed with care:

- Use environment variables to store sensitive information.

- Mark outputs as sensitive (`sensitive = true`).

- Use tools like HashiCorp Vault or cloud secrets managers.

\

### 31Q. **How do you manage multiple environments in Terraform?**

**Answer:**\
You can manage multiple environments using workspaces or variable files (`\*.tfvars`). Modules can also help by providing reusable infrastructure with environment-specific configurations.

\


---

# <mark style="background-color:#F8914D;">**Scenario based questions**<!-- {"backgroundCycleColor":"24"} --></mark> <!-- {"collapsed":true} -->

### 1. What is DevOps?

 - Answer: DevOps is a culture and set of practices that bring together software development (Dev) and IT operations (Ops) to shorten the development lifecycle while delivering high-quality software. It emphasizes collaboration, automation, continuous integration, and continuous delivery (CI/CD).

\

\

### 2. What tools are commonly used in DevOps?

 - Answer: Some popular DevOps tools include:

 **- CI/CD:** Jenkins, GitLab CI, CircleCI

 **- Configuration Management:** Ansible, Puppet, Chef

 **- Containers:** Docker, Kubernetes

 **- Monitoring:** Prometheus, Grafana, Nagios

\

\

### 3. What is Continuous Integration (CI)?

 - Answer: Continuous Integration is a practice where developers frequently merge their code changes into a central repository, after which automated builds and tests are run. This helps in identifying and fixing bugs early in the development process.

\

\

### 4. Explain Infrastructure as Code (IaC).

 - Answer: IaC is the practice of managing and provisioning computing infrastructure through machine-readable configuration files, rather than physical hardware configuration or interactive configuration tools. Tools like Terraform and AWS CloudFormation are commonly used.

\

\

### 5. What is the role of a DevOps engineer?

 - Answer: A DevOps engineer is responsible for bridging the gap between development and operations teams by automating processes, improving the efficiency of the software development lifecycle, ensuring smooth deployment, and maintaining the infrastructure.

\

\

### 6. What is Docker, and why is it used in DevOps?

 -Answer: Docker is a containerization platform that packages applications and their dependencies into containers, allowing them to run consistently across different environments. It's used in DevOps for its scalability, portability, and efficiency in deploying microservices.

\

\

### 7. Can you explain the concept of Continuous Delivery (CD)?

 - Answer: Continuous Delivery is the practice of automatically preparing code changes for release to production. This means every change is built, tested, and then automatically prepared for a release, making the release process quick and less error-prone.

\

\

### 8. How do you monitor and maintain system performance in a DevOps environment?

 - Answer: Monitoring is crucial in a DevOps environment. Tools like Prometheus, Grafana, and Nagios are used to monitor system performance. Monitoring involves tracking metrics like CPU usage, memory usage, error rates, and application performance to ensure the system is functioning optimally.

\

\

### 9. What is GitOps, and how does it relate to DevOps?

 - Answer: GitOps is a practice that uses Git as the single source of truth for declarative infrastructure and application deployment. In a DevOps environment, GitOps automates the process of application deployment, monitoring, and management, ensuring consistency and transparency across environments.

\

\

### 10. How do you implement Continuous Testing in a CI/CD pipeline?

 - Answer: Continuous Testing involves integrating automated tests at every stage of the CI/CD pipeline. This can be achieved by:

 - **Unit Testing:** Ensuring code quality at the developer level.

 - **Integration Testing:** Validating the interaction between components.

 - **End-to-End Testing:** Simulating user journeys.

 - **Performance Testing:** Assessing system performance under load.

 Automated tools like Jenkins, Selenium, and JUnit are commonly used to incorporate these tests seamlessly into the pipeline.

\

\

### 11. What is the difference between Blue-Green Deployment and Canary Deployment?

\- Answer: - **Blue-Green Deployment:** Involves running two identical production environments, one active (Blue) and one idle (Green). New versions of the application are deployed in the idle environment, and once validated, traffic is switched from the active environment to the new one.

 - **Canary Deployment**: Gradually rolls out a new version to a small subset of users before a full deployment. If no issues are detected, the deployment is gradually expanded to all users.

\

\

### 12. Explain the concept of Immutable Infrastructure.

 - Answer: Immutable Infrastructure is a design principle where servers or systems are never modified after they're deployed. Instead of updating an existing server, a new server is provisioned with the updated configuration. This approach reduces the chances of configuration drift and ensures consistency across environments.

\

\

### 13. How do you ensure high availability and scalability in a cloud environment?

 - Answer: High availability and scalability can be ensured through:

 **- Load Balancing:** Distributing traffic across multiple servers.

 **- Auto-Scaling:** Automatically adjusting the number of instances based on traffic demand.

 **- Redundancy:** Implementing multiple instances across different regions or availability zones.

 **- Fault Tolerance:** Ensuring the system can continue functioning even if one component fails.

\

\

### 14. What is the concept of "Shift Left" in DevOps?

 - Answer: "Shift Left" refers to the practice of incorporating testing, security, and quality checks earlier in the software development lifecycle. By moving these activities "left" on the timeline (closer to the coding phase), issues can be identified and resolved sooner, reducing the risk of problems in later stages. This approach is key to improving overall quality and efficiency in a DevOps environment.

\

\

### 15. How do you manage and monitor microservices in production?

 - Answer: Managing and monitoring microservices involves several practices:

 **- Service Discovery:** Tools like Consul or Eureka help microservices discover and communicate with each other.

 **- Centralized Logging:**Tools like ELK Stack (Elasticsearch, Logstash, Kibana) aggregate logs from different services.

 **- Distributed Tracing:** Jaeger or Zipkin help trace requests across services to diagnose issues.

 **- Metrics Monitoring:** Prometheus, coupled with Grafana, provides insights into performance metrics.

\

\

### 16. What is the role of Service Mesh in a microservices architecture?

 - Answer:A Service Mesh is a dedicated infrastructure layer that manages service-to-service communication within a microservices architecture. It handles tasks such as load balancing, service discovery, retries, timeouts, and security. Popular service mesh tools include Istio and Linkerd, which provide visibility and control over the communication between microservices.

\

\

### 17. Explain Chaos Engineering and its importance in DevOps.

 - Answer: Chaos Engineering is the practice of intentionally introducing failures into a system to test its resilience. By simulating unexpected conditions (like server crashes or network failures), teams can identify weaknesses and improve the system's ability to withstand disruptions. Tools like Chaos Monkey and Gremlin are commonly used for this purpose.

\

\

### 18. How do you implement security in a CI/CD pipeline?

 - Answer: Implementing security in a CI/CD pipeline involves:

 **- Static Application Security Testing (SAST):** Scanning code for vulnerabilities during the development phase using tools like SonarQube.

 **- Dynamic Application Security Testing (DAST):** Testing running applications for vulnerabilities using tools like OWASP ZAP.

 **- Dependency Scanning:** Checking third-party libraries for known vulnerabilities with tools like Snyk.

\

\

### 19. What is the Twelve-Factor App methodology?

 - Answer: The Twelve-Factor App is a set of best practices for building modern, scalable, and maintainable web applications. These principles cover aspects like configuration management, dependency management, and port binding.

\

\

### 20. What are Microservices, and why are they important in DevOps?

 - Answer: Microservices are a software architecture style that structures an application as a collection of loosely coupled services. Each service is independent and can be deployed, scaled, and maintained individually. In DevOps, microservices enable rapid development, testing, and deployment, aligning perfectly with the CI/CD pipeline.

\

\

### 21. What is the role of Kubernetes in DevOps?

 - Answer: Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. It plays a crucial role in DevOps by:

 - Automating deployments and rollbacks.

 - Managing containerized applications across different environments.

 - Ensuring efficient resource utilization and scaling.

\

\

### 22. How do you implement observability in a DevOps environment?

 - Answer: Observability involves monitoring and analyzing the health and performance of a system. It can be implemented through:

 **- Logging:** Capturing and analyzing logs using tools like ELK Stack.

 **- Metrics:** Tracking system performance with Prometheus.

 **- Tracing:** Monitoring request flows through services using Jaeger or Zipkin.

 Observability helps in identifying issues proactively and improves system reliability.

\

\

### 23. Can you explain the concept of Configuration Management?

 - Answer: Configuration Management involves maintaining consistency in system performance by managing the configuration of servers, software, and infrastructure. Tools like Ansible, Puppet, and Chef automate the process, ensuring that configurations are consistent across all environments and can be easily replicated or rolled back if needed.

\

\

### 24. How do you handle secrets management in DevOps?

 - Answer: Secrets management involves securely storing and managing sensitive data like passwords, API keys, and certificates. Best practices include:

 - Using tools like HashiCorp Vault, AWS Secrets Manager, or Kubernetes Secrets.

 - Encrypting secrets at rest and in transit.

 - Implementing access controls to restrict who can access the secrets.

\

\

### 25. How would you design a scalable logging system?

Answer: 

To design a scalable logging system:

**- Log Collection:** Use distributed log collectors (e.g., Fluentd, Logstash) on each server to gather logs.

**- Storage:** Store logs in a distributed, scalable database like Elasticsearch.

**- Processing:** Implement a message queue (e.g., Kafka) to handle the high throughput of logs.

**- Querying and Analysis:** Use Kibana or Grafana to visualize and analyze logs, ensuring that the system can handle a large volume of data.

\

\

### 26. How do you design a system to handle millions of concurrent users?

Answer:

\- Load Balancing: Use load balancers (e.g., NGINX, HAProxy) to distribute traffic across multiple servers.

\- Horizontal Scaling: Scale out by adding more servers rather than scaling up a single server.

\- Database Sharding: Split the database into smaller, more manageable pieces to handle large volumes of data.

\- Caching: Implement caching mechanisms (e.g., Redis, Memcached) to reduce database load.

\

\

### 27. How would you design a content delivery network (CDN)?

Answer:

**- Edge Servers:** Deploy a network of edge servers globally to cache content close to users.

**- Load Distribution:** Use DNS-based load balancing to direct users to the nearest edge server.

**- Content Invalidation:** Implement mechanisms to refresh cached content when it changes.

**- Security:** Integrate security features like DDoS protection and SSL/TLS encryption.

\

\

### 28. Explain the design of a microservices architecture.

Answer:

**- Service Separation:** Break down the application into independent services, each responsible for a specific functionality.

**- API Gateway:** Use an API Gateway to manage communication between clients and microservices.

**- Service Discovery:** Implement service discovery (e.g., Consul, Eureka) to locate and manage services dynamically.

**- Resilience:** Use circuit breakers and retries to handle failures gracefully.

\

\

29\. How would you design a real-time chat application?

Answer:

**- WebSockets:** Use WebSockets to maintain an open connection between the client and server for real-time communication.

**- Message Broker:** Implement a message broker (e.g., RabbitMQ) to manage the delivery of messages between users.

**- Storage:** Store chat history in a scalable NoSQL database like MongoDB.

**- Security:** Ensure secure communication with SSL/TLS and user authentication.

\

\

### 30. How do you design a high availability system?

Answer:

\- Redundancy

\- Failover Mechanisms

\- Health Checks

\- Data Replication

\

\

### 31. What is Docker, and how does it work?

 - Answer: Docker is an open-source platform that automates the deployment of applications inside lightweight containers. Containers provide a consistent environment from development to production, ensuring that applications run the same, regardless of where they're deployed. Docker uses OS-level virtualization to run software in isolated environments.

\

\

### 32. What is the difference between a Docker image and a container?

 - Answer: A Docker image is a read-only template that contains the application code, libraries, and dependencies needed to run an application. A container is a running instance of an image. Containers are created from images and can be started, stopped, and deleted independently of the image.

\

\

### 33. How do you create a Docker container from an image?

 - Answer: You can create a Docker container from an image using the following command:

```
 docker run -d --name <container_name> <image_name>
```

 The \`-d\` flag runs the container in detached mode, meaning it runs in the background.

\

\

###  34. What is a Dockerfile, and how is it used?

 - Answer: A Dockerfile is a text file that contains a series of instructions to create a Docker image. It automates the image creation process. You can build an image from a Dockerfile using:

```
 docker build -t <image_name> .
```

 The \`-t\` flag tags the image with a name.

\

\

### 35. Explain Docker Compose and its uses.

 - Answer: Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you can use a YAML file to define the services, networks, and volumes required for an application. You can start all services defined in the YAML file using:

```
 docker-compose up -d
```

\

 

### 36. How do you monitor and manage Docker containers in a production environment?

 - Answer: Monitoring and managing Docker containers can be done using tools like Docker Swarm, Kubernetes, or third-party monitoring tools like Prometheus and Grafana. These tools allow you to scale, manage, and monitor containers effectively in a production environment.

\

\

### 37. What is Kubernetes, and why is it important in DevOps?

 - Answer: Kubernetes is an open-source platform designed to automate deploying, scaling, and managing containerized applications. It’s crucial in DevOps for its ability to manage containerized workloads and services, facilitating both declarative configuration and automation.

\

\

### 38. Explain the architecture of Kubernetes.

 - Answer: Kubernetes architecture consists of a Master Node and Worker Nodes. The Master Node controls the cluster, managing workloads and communication. It includes components like the API Server, Scheduler, Controller Manager, and etcd. Worker Nodes host the application and contain the Kubelet, Kube Proxy, and container runtime (e.g., Docker).

\

\

### 39. What are Pods in Kubernetes?

 - Answer: Pods are the smallest deployable units in Kubernetes. A Pod encapsulates one or more containers, storage resources, a unique network IP, and options that govern how the containers should run. Pods are ephemeral, and each new Pod gets a new IP address.

\

\

### 40. How does Kubernetes handle networking?

 - Answer: Kubernetes provides a flat network space where all Pods can communicate with each other, and it supports different network models like ClusterIP, NodePort, and LoadBalancer for service discovery and external access. Kubernetes networking is typically implemented using a CNI (Container Network Interface) plugin.

\

\

### 41. What is a Kubernetes Service, and how does it differ from a Pod?

 - Answer: A Service in Kubernetes is an abstraction that defines a logical set of Pods and a policy by which to access them. While Pods have a lifespan, Services provide a stable network endpoint, enabling load balancing and scaling.

\

\

### 42. Explain the purpose of ConfigMaps and Secrets in Kubernetes.

 - Answer: ConfigMaps are used to pass non-sensitive configuration data into your Pods, whereas Secrets are used to manage sensitive data like passwords or API keys. Both ConfigMaps and Secrets allow you to separate configuration data from container images, making your applications more portable and secure.

\

\

### 43. What is a Kubernetes Namespace?

 - Answer: A Namespace in Kubernetes is a way to divide cluster resources between multiple users (via resource quota). Namespaces provide a mechanism to isolate groups of resources within a single cluster, aiding in organization and security.

\

\

### 44. What is CI/CD, and why is it important?

Answer: CI/CD stands for Continuous Integration and Continuous Deployment/Delivery. CI automates the testing and integration of code changes, ensuring early detection of bugs. CD automates the deployment process, reducing time to market and increasing the frequency of releases.

\

\

### 45. What are the key differences between Continuous Delivery and Continuous Deployment?

Answer: Continuous Delivery ensures that every change is tested and ready for deployment, but the deployment is manual. Continuous Deployment goes a step further by automating the deployment process, ensuring every change is automatically deployed to production.

\

\

###  46. How do you handle rollback in a CI/CD pipeline?

Answer: Rollback strategies can include using version control to revert to a previous commit, maintaining backups of previous releases, or implementing blue-green deployments where traffic can be switched back to the previous version if a deployment fails.

\

\

###  47. Explain Blue-Green Deployment and its benefits.

Answer: Blue-Green Deployment involves running two identical production environments (Blue and Green). At any time, only one (say, Blue) serves live production traffic. New releases are deployed to the Green environment. Once tested, traffic is switched to Green, ensuring zero downtime. If issues arise, traffic can be switched back to Blue.

\

\

###  48. What tools do you use for CI/CD, and why?

Answer: Common CI/CD tools include Jenkins, [Razorops, Inc.](https://www.linkedin.com/company/razorops/) [GitLab](https://www.linkedin.com/company/gitlab-com/) CI, CircleCI, and GitHub Actions. The choice of tool depends on the specific requirements, such as integration with version control systems, ease of use, scalability, and support for various plugins.

\

\

###  49. How do you ensure security in a CI/CD pipeline?

Answer: Security can be ensured by incorporating static code analysis (SAST), dynamic application security testing (DAST), secret management tools, and ensuring that only authorized personnel can trigger deployments. Additionally, automating security checks within the CI/CD pipeline helps identify vulnerabilities early.

\

\

###  50. What is Canary Deployment, and how does it work?

Answer: Canary Deployment involves gradually rolling out a new version to a small subset of users before a full release. This approach helps identify potential issues in a controlled environment, allowing for a quick rollback if problems are detected.

\

\

### 51. What is Jenkins?

Jenkins is an open-source automation server that helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery (CI/CD).

\

\

###  52. How does Jenkins achieve Continuous Integration?

Jenkins automates the process of building and testing code every time a developer commits changes to version control. It pulls the latest code, builds it, and runs tests to ensure no bugs have been introduced, providing immediate feedback to the developers.

\

\

###  53. Explain Jenkins Pipeline and its advantages.

A Jenkins Pipeline is a suite of plugins that supports implementing and integrating continuous delivery pipelines. It allows defining the entire CI/CD process through code, making it easier to maintain, version, and review. Pipelines can be configured using a Jenkinsfile, allowing code review and versioning of the pipeline itself.

\

\

###  54. What is the difference between Declarative and Scripted Pipeline in Jenkins?

**- Declarative Pipeline:** Provides a more structured and simplified syntax, making it easier to read and write.

**- Scripted Pipeline:** Offers more flexibility and is written in Groovy. It’s less restrictive and more suitable for complex logic and workflows.

\

\

###  55. How do you secure Jenkins?

Securing Jenkins involves several steps:

\- Enable security in the Jenkins settings.

\- Use Role-Based Access Control (RBAC) to manage permissions.

\- Regularly update Jenkins and plugins.

\- Implement security features like SSL and enable authentication.

\

\

###  56. How does Jenkins handle parallel execution of jobs?

Jenkins supports parallel execution using its Pipeline feature. You can define stages in the pipeline that can run in parallel using the \`parallel\` directive, allowing multiple jobs or parts of the same job to run simultaneously.

\

\

###  57. What are Jenkins agents, and how are they utilized?

Agents in Jenkins are machines that are set up to execute jobs. They can be physical machines, VMs, or containers. By distributing the workload across multiple agents, Jenkins can efficiently manage and execute multiple jobs concurrently.

\

\

### 58. What is Terraform, and how does it work? 

Terraform is an open-source Infrastructure as Code tool created by HashiCorp. It allows you to define and provision data center infrastructure using a high-level configuration language. Terraform works by using a declarative configuration file where you define your desired infrastructure state, which it then uses to create an execution plan to reach that state, applying it through a series of API calls.

\

\

### 59. How do Terraform modules work? 

Modules in Terraform are self-contained packages of Terraform configurations that are managed as a group. They help in reusing the infrastructure code, making it modular and easier to manage. You can call these modules in your configuration, passing different variables as needed, which allows you to maintain consistency and reduce duplication.

\

\

### 60. Explain the purpose of the Terraform state file (\`terraform.tfstate\`). 

The Terraform state file tracks the state of the infrastructure managed by Terraform. It stores information about your infrastructure and helps Terraform understand what changes need to be made to achieve the desired state. It’s critical to manage this file properly, as any corruption can lead to inconsistencies in your infrastructure.

\

\

### 61. How do you handle sensitive data in Terraform? 

Handling sensitive data, such as API keys or passwords, is crucial in Terraform. Terraform allows you to use environment variables, external secret management systems (like AWS Secrets Manager or HashiCorp Vault), or the \`sensitive\` attribute to manage sensitive information securely.

\

\

### 62. What is the difference between \`terraform plan\` and \`terraform apply\`? 

\`terraform plan\` is a command that allows you to preview the changes that Terraform would make to your infrastructure. It shows you a detailed execution plan but does not apply any changes. \`terraform apply\` applies the changes required to reach the desired state of the configuration, as defined in the execution plan.

\

\

### 63. How does Terraform handle dependencies between resources? 

Terraform automatically handles dependencies between resources based on the configuration. For example, if one resource depends on another, Terraform understands the dependency from the configuration and ensures that the dependent resource is created after its prerequisite resource.

\

\

### 64. What is the role of monitoring in DevOps? 

Monitoring is essential in DevOps for maintaining system performance, detecting issues, and ensuring high availability. It involves tracking various metrics, such as CPU usage, memory consumption, and application performance, to provide insights into the health of the system and proactively address potential problems.

\

\

### 65. What are the key components of a monitoring system? 

Key components of a monitoring system include:

**- Metrics Collection:** Gathering data on various system and application metrics.

**- Storage:** Storing collected metrics for historical analysis and trend identification.

**- Visualization:** Displaying metrics in dashboards for easy interpretation.

**- Alerting:** Notifying stakeholders of any issues or threshold breaches.

**- Analysis:** Analyzing metrics to understand performance trends and identify anomalies.

\

\

### 66. What is the difference between metrics and logs? 

**- Metrics:** Quantitative data points that represent performance aspects, such as CPU usage, response time, or request rates. Metrics are typically time-series data and are used to track trends and set thresholds.

**- Logs:** Detailed records of events, transactions, or errors. Logs provide a granular view of system activity and can be used for debugging and detailed investigation.

\

\

### 67. What tools are commonly used for monitoring in a DevOps environment? 

Common monitoring tools include:

**- Prometheus:** An open-source monitoring and alerting toolkit designed for reliability and scalability.

**- Grafana:** A visualization tool that integrates with various data sources, including Prometheus, to create dashboards and visualizations.

**- Nagios:** A monitoring system that provides comprehensive monitoring of systems, networks, and infrastructure.

**- Datadog:** A cloud-based monitoring and analytics platform that offers real-time visibility into application performance and infrastructure health.

**- Zabbix:** An open-source monitoring tool for network, server, and application performance.

\

\

### 68. What is an alerting system, and how does it work?

An alerting system monitors metrics and triggers notifications when predefined thresholds are exceeded or anomalies are detected. Alerts can be configured to send notifications via email, SMS, or integration with communication platforms like Slack. Proper alerting helps teams respond quickly to potential issues and minimize downtime.

\

\

### 69. What is Ansible, and how does it work? 

Ansible is an open-source automation tool used for configuration management, application deployment, and task automation. It uses a declarative language to describe the desired state of your systems, which it then applies through SSH or other remote protocols. Ansible operates in a push-based model where the control node sends commands to the managed nodes.

\

\

### 70. What are Ansible playbooks, and how do they work? 

Ansible playbooks are YAML files that define a series of tasks to be executed on remote machines. They describe the desired state of the system and include tasks, variables, and roles. Playbooks are executed by Ansible to ensure that systems are configured according to the specifications defined in the playbook.

\

\

### 71. How do Ansible roles work? 

Roles in Ansible are a way to organize and reuse playbook code. A role encapsulates a set of tasks, variables, templates, and handlers in a structured way, allowing you to manage configurations modularly. Roles can be included in playbooks to apply a specific configuration or set of tasks to hosts.

\

\

### 72. What is the difference between \`ansible\` and \`ansible-playbook\` commands? 

The \`ansible\` command is used for executing ad-hoc commands on managed nodes. For example, it can be used to check system information or perform a quick task. The \`ansible-playbook\` command is used to run playbooks, which define a series of tasks to be applied to managed nodes in a structured manner.

\

\

### 73. Explain the concept of Ansible inventory. 

Ansible inventory is a file or script that lists the hosts and groups of hosts that Ansible manages. It defines the machines to be managed and can include variables specific to those hosts. The inventory can be static (a simple file) or dynamic (generated by a script or a service).

\

\

### 74. How does Ansible handle variables? 

Ansible handles variables in several ways: 

**- Playbook variables:** Defined directly within playbooks.

**- Inventory variables:** Defined in the inventory file or as host/group variables.

**- Variable files:** Stored in separate YAML files and included in playbooks.

**- Environment variables:** Used for sensitive or environment-specific data.

\

\

### 74. What is Ansible Vault, and why is it used? 

Ansible Vault is a feature that allows you to encrypt sensitive data, such as passwords or API keys, within Ansible files. It provides a way to keep sensitive information secure while still being able to include it in playbooks and other configuration files.

# <mark style="background-color:#F8914D;">**Jenkins's**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### **1Q. <mark style="background-color:#FFFFFF;">Jenkins Free Style - Its nothing but everything you do it in UI<!-- {"backgroundCycleColor":"11"} --></mark> <mark style="background-color:#F8D616;">(No one using freestyle now)<!-- {"backgroundCycleColor":"25"} --></mark>**

<mark style="color:#000000;">Anything we can run in Jenkins are Job (job is nothing but it has some work to do). Free style we can do it in UI and we don't know who made the changes and its very difficult to restore back to normal stage. Because of this we are not using freestyle now a days everyone using pipeline.<!-- {"cycleColor":"55"} --></mark>

\

### **2Q. What is Jenkins?**

Jenkins is an open-source automation server used for continuous integration and continuous delivery (CI/CD). It helps automate parts of software development related to building, testing, and deploying.

\

### **3Q. How does Jenkins achieve continuous integration?**

Jenkins automates the process of integrating code changes from multiple contributors by building and testing them continuously. It pulls code from version control systems, runs tests, and provides feedback to developers.

\

### **4Q. What are Jenkins Pipelines?**

Jenkins Pipelines are a suite of plugins that support implementing and integrating continuous delivery pipelines into Jenkins. They allow defining a series of steps in code, usually in a `Jenkinsfile`.

\

### **5Q. How do you configure a Jenkins job?**

You configure a Jenkins job by defining the source code repository, build triggers, build steps, and post-build actions through the Jenkins UI or by using a `Jenkinsfile` for pipeline jobs.

\

\

### **6Q. What are Jenkins agents/nodes?**

Jenkins agents (also called nodes) are machines that perform the tasks specified in the pipelines. They can be the same machine as the Jenkins controller (master) or separate machines.

\

### **7Q. How do you handle credentials in Jenkins securely?**

Jenkins provides a Credentials plugin to store and manage credentials securely. These credentials can be used in pipelines without exposing sensitive data.

\

### **8Q. How does Jenkins integrate with Docker?**

Jenkins can build Docker images, run Docker containers as build agents, and even execute pipeline steps within Docker containers. You can define this in your `Jenkinsfile` using the Docker Pipeline plugin.

\

### **9Q. How can you scale Jenkins for a large project or team?**

You can scale Jenkins by using multiple agents/nodes, implementing master-slave architecture, utilizing Jenkins Distributed Builds, and using tools like Kubernetes for managing Jenkins workloads.

\

\

### **10Q. What is Blue Ocean in Jenkins?**

Blue Ocean is a modern, user-friendly interface for Jenkins, designed to simplify the job and pipeline creation process and provide a more intuitive view of continuous delivery pipelines.

\

\

### **11Q. How can you set up Jenkins for continuous deployment?**

Configure your Jenkins pipeline to deploy code automatically after passing tests. Use plugins or scripts to deploy to environments like Kubernetes, AWS, or Docker Swarm.

\

\

### **12Q. What are Jenkins Shared Libraries?**

Shared Libraries in Jenkins allow you to define common functions and steps in a centralized repository and use them across multiple pipelines, promoting code reuse and standardization.

\

\

### **13Q. What is the role of Jenkins in a DevOps environment?**

Jenkins automates and orchestrates the software delivery pipeline, providing continuous integration, continuous delivery, and continuous deployment, which are key practices in DevOps.

\

### **14Q. How would you troubleshoot a failing Jenkins job?**

Check the console output for errors, review job configurations, inspect the environment and agent logs, and use plugins like Pipeline Stage View or the Blue Ocean interface for more details.

\

\

### **15Q. Can you list different types of triggers available in Jenkins?**

- Common triggers include:

    - Poll SCM

    - Build Periodically

    - Webhooks (e.g., GitHub, GitLab)   -- we use webhook, when any changes in git repo it will trigger build and runs Jenkins job.

    - Upstream/Downstream Jobs

    - Post-commit Hooks

\

### **16Q. What is a webhook in the context of Jenkins?**

- A webhook is a way for external services (like GitHub or GitLab) to send automated notifications to Jenkins when certain events occur, such as code pushes. This allows Jenkins to trigger builds or pipelines in response to these events.

\

### **17Q. What is a build trigger in Jenkins?**

Build triggers in Jenkins are mechanisms that automatically start a job or pipeline based on specific events or schedules. They eliminate the need for manual builds and help in continuous integration.

\

### **18Q. How do you configure a webhook in Jenkins for a GitHub repository?**

- To configure a webhook:

- In GitHub, navigate to the repository settings.

- Go to the "Webhooks" section and add a new webhook.

- Enter the Jenkins webhook URL (e.g., `http://<jenkins-url>/github-webhook/`).

- Select the events you want to trigger the webhook (e.g., push events).

- Save the webhook configuration.

- Ensure that the Jenkins job or pipeline is configured to respond to the webhook.

\

### **19Q. What is the difference between "Poll SCM" and using a webhook in Jenkins?**

- **Poll SCM** periodically checks the source control for changes at specified intervals, triggering a build if changes are detected. It may lead to unnecessary load if polling too frequently.

- **Webhooks** push notifications directly to Jenkins whenever a change occurs, triggering an immediate build without the need for polling, making it more efficient and responsive.

\

### **20Q. How would you set up a Jenkins pipeline to be triggered by a GitHub webhook?**

- To set up a pipeline:

- Create or configure a Jenkins pipeline job.

- Ensure the job is connected to the appropriate GitHub repository.

- In the job configuration, enable the "GitHub hook trigger for GITScm polling" option.

- Configure the webhook in GitHub as described earlier.

- Save the pipeline configuration and push a change to the repository to test the webhook trigger.

\

### **21Q. How would you troubleshoot a Jenkins webhook that is not triggering a build?**

- **Webhook configuration** in the external service (e.g., GitHub) to ensure the correct URL and events are selected.<!-- {"indent":1} -->

    - **Jenkins logs** for any errors related to webhook processing.

    - **Network connectivity** between the external service and Jenkins.

    - **Job configuration** in Jenkins to ensure it is set up to respond to webhooks.

    - **Security settings** in Jenkins that might block incoming requests.

\

### **22Q. What are the security considerations when using webhooks in Jenkins?**

- **Secret tokens:** Use secret tokens to ensure that only legitimate sources can trigger the webhook.

- **Jenkins CSRF Protection:** Ensure CSRF protection is enabled in Jenkins.

- **IP whitelisting:** Restrict incoming webhook requests to trusted IP addresses.

- **Secure Jenkins URL:** Use HTTPS for Jenkins to prevent interception of webhook requests.

\

### **23Q. What is a Multibranch Pipeline in Jenkins?**

1. A Multibranch Pipeline in Jenkins automatically creates a pipeline for each branch in a repository. It allows for different branches to have their own pipeline configurations defined by `Jenkinsfile` stored in the respective branch.<!-- {"indent":1} -->

\

### **24Q. How do you create a Multibranch Pipeline in Jenkins?**

1. To create a Multibranch Pipeline:<!-- {"indent":1} -->

    1. Go to Jenkins Dashboard and click on "New Item."

    1. Select "Multibranch Pipeline" and give it a name.

    1. Configure the pipeline by adding the source repository (e.g., Git, GitHub).

    1. Define the branch discovery strategy to include/exclude branches.

    1. Save the configuration, and Jenkins will scan the repository to create pipelines for each branch with a `Jenkinsfile`.

\

### **25Q. What is the advantage of using a Multibranch Pipeline over a regular pipeline?**

1. Multibranch Pipelines provide automatic branch detection and management, allowing each branch to have its own pipeline configuration. This is particularly useful for managing feature branches, pull requests, and different environments, without manually configuring each one.<!-- {"indent":1} -->

\

### **26Q. How does Jenkins detect new branches in a Multibranch Pipeline?**

1. Jenkins periodically scans the source code repository for new branches. When a new branch with a `Jenkinsfile` is detected, Jenkins automatically creates a pipeline for it. The scan interval can be configured in the Multibranch Pipeline settings.<!-- {"indent":1} -->

\

### **27Q. Can you run different stages or steps for different branches in a Multibranch Pipeline?**

- Yes, you can define conditional logic in the `Jenkinsfile` to run different stages or steps depending on the branch name. For example:

![dfd3192f-0960-4088-84d7-02b9f3cb9bd4.png|687](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/dfd3192f-0960-4088-84d7-02b9f3cb9bd4.png) [^205]

\

### **28Q. How do you handle pipeline failures for feature branches in a Multibranch Pipeline?**

1. Handle failures by configuring Jenkins to send notifications (e.g., email, Slack) to the relevant team members. You can also set up automated rollback mechanisms, or use pipeline stages to ensure that failures in feature branches do not affect the main branch.<!-- {"indent":1} -->

\

### **29Q. Describe a scenario where a Multibranch Pipeline would be essential for a project.**

1. A Multibranch Pipeline is essential in a project where multiple developers are working on different feature branches simultaneously. It allows each branch to have its own CI/CD pipeline, ensuring that code changes are tested and validated independently before merging into the main branch.<!-- {"indent":1} -->

\

### **30Q. How would you deal with pipeline configuration changes across multiple branches in a Multibranch Pipeline?**

1. To deal with configuration changes, you can:<!-- {"indent":1} -->

    1. Ensure that the `Jenkinsfile` in each branch is updated with the new configuration.<!-- {"indent":2} -->

        1. Use a shared library for common pipeline logic to minimize duplication across branches.

        1. Communicate and enforce a policy for updating `Jenkinsfile` across branches to ensure consistency.

\

**Others**

### **1Q. What are the types of Jenkins pipelines?**

**Declarative Pipeline:** A more recent feature that simplifies pipeline creation using a structured, easy-to-read syntax.

**Scripted Pipeline:** Uses Groovy code, providing more control but with added complexity.

\

\

### **2Q. How would you migrate Jenkins jobs from one server to another?**

You can migrate jobs by copying job configurations, plugins, and necessary files or using the Jenkins Job Import plugin. Alternatively, you can use Jenkins Configuration as Code (JCasC) to migrate configurations.

\

### **3Q**. **Can you give an example of a real-world use case where you would use Jenkins webhooks?**

- In a continuous deployment pipeline, you could use a webhook to trigger a Jenkins build whenever a new commit is pushed to the `main` branch. This build could run tests and deploy the application automatically to a staging environment, enabling rapid feedback and deployment cycles.

\

### **4Q. Describe a situation where using "Poll SCM" might be preferred over a webhook.**

- "Poll SCM" might be preferred if the external service does not support webhooks or if you want to aggregate changes over a period of time rather than triggering builds on every commit. It's also useful in environments where you have more control over Jenkins than the external service.

\

### **5Q. How would you ensure that a Jenkins job only triggers for specific events using webhooks?**

- You can control this by configuring the webhook in the external service to only send notifications for specific events (e.g., only push events, or only pull requests). In Jenkins, you can further refine the trigger conditions by adding logic in your pipeline script to check for specific criteria (e.g., branch name, commit message).

### 

### **6Q. How does the `Jenkinsfile` in a Multibranch Pipeline differ from a regular pipeline?**

- The `Jenkinsfile` in a Multibranch Pipeline is branch-specific, meaning each branch can have its own `Jenkinsfile` with unique configurations. This allows for customized pipeline workflows for different branches, whereas a regular pipeline has a single `Jenkinsfile` for all builds.

\

### **7Q.** **How do you manage pull requests in a Multibranch Pipeline?**

1. Jenkins can automatically detect and create pipelines for pull requests by configuring branch source plugins like GitHub Branch Source or Bitbucket Branch Source. These plugins allow Jenkins to treat pull requests as branches, running the pipeline and reporting status back to the SCM.<!-- {"indent":1} -->

\

**8Q. What are branch sources and branch source strategies in a Multibranch Pipeline?**

1. **Branch Sources**: Define where Jenkins should look for branches (e.g., GitHub, Bitbucket, Git).<!-- {"indent":1} -->

    1. **Branch Source Strategies**: Control which branches Jenkins should discover and build. Strategies include:

        1. Discover all branches.

        1. Discover branches that are also filed as a pull request.

        1. Exclude branches that are filed as a pull request.

        1. Customize using regex or other criteria.

\

### **9Q. How do you customize the scan frequency for branches in a Multibranch Pipeline?**

1. The scan frequency can be customized in the Multibranch Pipeline job configuration under "Scan Multibranch Pipeline Triggers." You can set a cron schedule for how often Jenkins should scan for new branches or changes to existing branches.<!-- {"indent":1} -->

\

### **10Q. How would you set up a Multibranch Pipeline to handle different environments (e.g., dev, staging, production)?**

1. You can set up different branches for each environment, each with its own `Jenkinsfile`. For example:<!-- {"indent":1} -->

    1. `dev` branch has a `Jenkinsfile` with stages for building and deploying to the development environment.<!-- {"indent":2} -->

        1. `staging` branch has a `Jenkinsfile` for deploying to a staging environment.

        1. `master` or `production` branch has a `Jenkinsfile` for deploying to production.

        1. Alternatively, you can use branch naming conventions and conditionals in a single `Jenkinsfile` to handle different environments.

\

\

\


---

# <mark style="background-color:#F8914D;">**ECR (Elastic Container Registry) - other option for Docker HUB to store docker images.**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### 

### **1Q. What is AWS ECR?**

1. Amazon Elastic Container Registry (ECR) is a fully managed Docker container registry that allows developers to store, manage, and deploy Docker container images. It is integrated with Amazon ECS, EKS, and other AWS services, providing a secure and scalable environment for containerized applications.<!-- {"indent":1} -->

\

### **2Q. How do you push a Docker image to AWS ECR?**

1. To push a Docker image to ECR:<!-- {"indent":1} -->

    1. Authenticate Docker to your Amazon ECR registry using `aws ecr get-login-password`.

    1. Build your Docker image using `docker build`.

    1. Tag the Docker image with the ECR repository URI.

    1. Push the tagged image to the ECR repository using `docker push`.

\

### **3Q. What is the difference between AWS ECR and Docker Hub?**

1. AWS ECR is a managed service by Amazon that integrates with other AWS services, offering features like IAM-based access control and lifecycle policies. Docker Hub is a public registry for Docker images, with the option for private repositories. ECR is preferred for AWS-centric workflows due to its integration with AWS IAM and other services.<!-- {"indent":1} -->

### 

### **4Q. How do you authenticate to AWS ECR from a CI/CD pipeline?**

1. Authentication to AWS ECR in a CI/CD pipeline can be achieved by:<!-- {"indent":1} -->

    1. Using IAM roles or AWS credentials stored in a secure place (like AWS Secrets Manager or Jenkins credentials).

    1. Running the command `aws ecr get-login-password` to retrieve a password and then passing it to Docker for authentication.

    1. For ECS/EKS integrations, IAM roles for service accounts (IRSA) or task roles can be used to grant permissions.

\

### **5Q. What are lifecycle policies in AWS ECR?**

1. Lifecycle policies in ECR allow you to define rules that automatically remove unused or old Docker images from the repository. This helps in managing storage costs and keeping the repository clean.<!-- {"indent":1} -->

\

### **6Q. How does AWS ECR integrate with Amazon ECS and EKS?**

1. AWS ECR is integrated with Amazon ECS and EKS, allowing these services to pull container images directly from ECR. You can specify the ECR image URI in the ECS task definitions or Kubernetes manifests, and the services will handle the authentication and pulling of images.<!-- {"indent":1} -->

\

### **7Q. How do you manage access to ECR repositories?**

1. Access to ECR repositories is managed using AWS Identity and Access Management (IAM). You can create IAM policies that specify which actions are allowed (e.g., push, pull) and which users or roles have access to the repositories. Additionally, ECR supports resource-based policies to control access.<!-- {"indent":1} -->

### 

### **8Q. How would you set up cross-account access to an ECR repository?**

1. To set up cross-account access:<!-- {"indent":1} -->

    1. In the source account, add a resource-based policy to the ECR repository allowing the target account to access it.

    1. In the target account, use IAM roles or policies to allow users or services to authenticate to the ECR repository in the source account.

    1. Use `aws ecr get-login-password --registry-ids <source-account-id>` to authenticate from the target account.

\

### **9Q. What are the benefits of using immutable tags in AWS ECR?**

1. Immutable tags prevent overwriting of Docker images that have been pushed with the same tag. This ensures that once an image is pushed, it cannot be changed, providing consistency and reliability for deployments.<!-- {"indent":1} -->

\

### **10Q. How would you handle large-scale Docker image storage in ECR?**

1. For large-scale storage:<!-- {"indent":1} -->

    1. Implement lifecycle policies to automatically delete unused or older images.<!-- {"indent":2} -->

        1. Use Amazon S3 for storing large layers that are common across many images, as ECR natively stores image layers in S3.

        1. Monitor storage usage and set up alerts using AWS CloudWatch to manage repository sizes and costs.

### 

### **11Q. How would you troubleshoot issues where ECS or EKS is unable to pull an image from ECR?**

1. Troubleshoot by:<!-- {"indent":1} -->

    1. Checking IAM roles and policies to ensure the ECS task or EKS service has permission to pull from ECR.<!-- {"indent":2} -->

        1. Verifying the image URI and tag in the task definition or Kubernetes manifest.

        1. Ensuring that the ECR repository exists, and the image is correctly pushed.

        1. Reviewing CloudWatch logs for ECS or Kubernetes events for any specific errors.

        1. Checking VPC endpoints if pulling from a private ECR repository.

\

### **12Q. Describe a scenario where you would use AWS ECR public repositories instead of private ones.**

1. Use ECR public repositories if you need to distribute container images broadly without requiring authentication, similar to Docker Hub. This is useful for open-source projects, sharing base images, or distributing tools and utilities.<!-- {"indent":1} -->

\

### **13Q. How would you integrate AWS ECR with a CI/CD pipeline for automated Docker builds and deployments?**

1. Integrate by:<!-- {"indent":1} -->

    1. Setting up a pipeline (e.g., using Jenkins, AWS CodePipeline) that builds Docker images after code changes.<!-- {"indent":2} -->

        1. Authenticating the pipeline to ECR and pushing the image using `docker push`.

        1. Using triggers to deploy the new image to an ECS or EKS cluster automatically.

        1. Implementing stages in the pipeline to run tests, security scans, and approvals before deploying.

\


---

# <mark style="background-color:#F8914D;">**DevOps tools**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

1\. Git : [https://git-scm.com/docs](https://git-scm.com/docs) 

🔗 Source Code Management:

1\. Git : [https://git-scm.com/docs](https://git-scm.com/docs) 

2\. GitHub: [https://docs.github.com/en](https://docs.github.com/en) 

3\. Bitbucket: [https://lnkd.in/dA2PcM_w](https://lnkd.in/dA2PcM_w) 

1\. ServiceNow: [https://lnkd.in/d69yubJF](https://lnkd.in/d69yubJF) 

\

📋 Ticketing Tools:

1\. ServiceNow: [https://lnkd.in/d69yubJF](https://lnkd.in/d69yubJF) 

2\. Jira: [https://lnkd.in/dD_WcXFQ](https://lnkd.in/dD_WcXFQ) 

1\. AWS: [https://lnkd.in/dMa9XpMa](https://lnkd.in/dMa9XpMa) 

3\. Trello: [https://trello.com/guide](https://trello.com/guide) 

\

☁️ Public Cloud Platforms:

1\. AWS: [https://lnkd.in/dMa9XpMa](https://lnkd.in/dMa9XpMa) 

1\. Docker: [https://docs.docker.com/](https://docs.docker.com/) 

2\. Azure: [https://lnkd.in/dBsJtZHy](https://lnkd.in/dBsJtZHy) 

3\. GCP: [https://lnkd.in/d3hmN-Jr](https://lnkd.in/d3hmN-Jr) 

\

📦 Containerization & Orchestration:

1\. Terraform: [https://lnkd.in/dM46h2_D](https://lnkd.in/dM46h2_D) 

1\. Docker: [https://docs.docker.com/](https://docs.docker.com/) 

2\. Kubernetes: [https://lnkd.in/dZXfQEqW](https://lnkd.in/dZXfQEqW) 

3\. Mesos: [https://lnkd.in/dqzvzJhY](https://lnkd.in/dqzvzJhY) 

\

1\. Selenium: [https://lnkd.in/dTnFN8bT](https://lnkd.in/dTnFN8bT) 

🚀 Deployment Tools:

1\. Terraform: [https://lnkd.in/dM46h2_D](https://lnkd.in/dM46h2_D) 

2\. Octopus: [https://octopus.com/docs](https://octopus.com/docs) 

3\. Heroku: [https://lnkd.in/dCDuwvcj](https://lnkd.in/dCDuwvcj) 

1\. Maven: [https://lnkd.in/dfgBnrZj](https://lnkd.in/dfgBnrZj) 

\

🔍 Testing Tools:

1\. Selenium: [https://lnkd.in/dTnFN8bT](https://lnkd.in/dTnFN8bT) 

2\. Cucumber: [https://lnkd.in/dpmD4A9C](https://lnkd.in/dpmD4A9C) 

1\. Jenkins: [https://lnkd.in/dPmA6-ff](https://lnkd.in/dPmA6-ff) 

3\. Postman: [https://lnkd.in/d3xERi6c](https://lnkd.in/d3xERi6c) 

\

🔧 Build Tools:

1\. Maven: [https://lnkd.in/dfgBnrZj](https://lnkd.in/dfgBnrZj) 

2\. Gradle: [https://lnkd.in/dv6rQczZ](https://lnkd.in/dv6rQczZ) 

3\. Ant: [https://lnkd.in/dQgMsgef](https://lnkd.in/dQgMsgef) 

\

🔄 Pipeline Tools:

1\. Jenkins: [https://lnkd.in/dPmA6-ff](https://lnkd.in/dPmA6-ff) 

2\. TravisCI: [https://lnkd.in/dxxFaK_X](https://lnkd.in/dxxFaK_X) 

3\. Argo CD: [https://lnkd.in/dK5eXbYi](https://lnkd.in/dK5eXbYi) 

\

📊 Monitoring Tools:

1\. Grafana: [https://lnkd.in/dX5anVq9](https://lnkd.in/dX5anVq9) 

2\. Prometheus: [https://lnkd.in/ddxjc9bV](https://lnkd.in/ddxjc9bV) 

\

🔒 Security Tools :

1\. Sonar Qube: [https://lnkd.in/gCmTAarS](https://lnkd.in/gCmTAarS) 

\


---

# <mark style="background-color:#F8914D;">**250+ Interview questions -DevOps**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

[workbook/DevOps 250Q&A.pdf at main · chilops/workbook (github.com)](https://github.com/chilops/workbook/blob/main/DevOps%20250Q%26A.pdf) 

 

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

[^2]: [Kubernetes - Architecture - GeeksforGeeks](https://www.geeksforgeeks.org/kubernetes-architecture/)

    Kubernetes Architecture

[^3]: Control Plane Node
    Worker Node
    master
    node
    API Server
    techopsexamples . com
    ap
    c-m
    sched
    kubelet
    etcd
    k-proxy
    kubele
    kubeCTL
    Controller Scheduler Kubelet
    etcd
    Kube-proxy
    Kubelet
    Manager
    Pod
    ped
    E
    iptables
    Container
    Container
    Runtime
    Kubernetes Architecture Illustration

[^4]: 8
    Cloud
    kubectl
    Node 1
    Provider
    Network Edge
    Pods
    Ctrl Plane - 1,2...n
    Container Runtime
    etcd
    kubelet
    controller
    kube
    System Services
    Load
    manager
    apiserver
    Balancer
    End Users
    scheduler
    Node 1
    Pods
    Container Runtime
    kubelet
    System Services

[^5]: Monolithic
    N-Tier
    Microservices
    UI Codebase
    UI Codebase
    Ul team
    CO
    Recipe API
    Ul team
    Codebase
    Items API team
    top React
    Single
    Middleware
    Codebase
    Codebase
    Recipe API
    Recipe API team
    Recipe API Team
    Team
    Items API
    Codebase
    Items API Team
    - Ul team
    JSP,
    spring
    boot
    Items API Team
    Spring Boot
    . ..
    Users API Team
    Users API
    User API team
    DB Scripts
    Codebase
    DB team
    DB team
    Users API Team
    DDL, DML, Stored
    Procedures
    DB Scripts
    Migration Scripts
    DB team
    DDL, DML, Stored
    Procedures
    Migration Scripts

[^6]: apiVersion :
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

[^7]: H
    apiVersion: v1
    2
    kind: Pod
    3
    metadata:
    4
    name: hello-pod
    5
    namespace: roboshop
    6
    spec :
    # list of containers
    18
    containers :
    9
    name: hello-pod
    10
    image: nginx
    #here with this line port will not be opened, just for information
    ports :
    13
    - containerPort: 80

[^8]: B
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

[^9]: .
    Example Command:
    bash
    Copy code
    eksctl create cluster --name my-cluster --region us-west-2

[^10]: .
    Example Command:
    bash
    Copy code
    kubectl get pods

[^11]: EXPLORER
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

[^12]: POD
    IP address
    catalogue
    ELK
    CONT1
    CONT2
    sidecar
    proxy
    init containers
    N/W and storage

[^13]: labels vs annotaions
    - -------
    labels --> have some limitation on the length and charecters of key and values
    annotaions --> no limit on length and special charecters also can be used...
    labels are used to select other kubernetes resources.
    annotaions are used to select external resources to kubernetes.

[^14]: 18 . 234. 197.98 \| 172. 31. 41.186 \| t2.micro \| https: //github.com/chilops/k8-resources.git
    \[ centos@ip-172-31-41-186 \~/k8-resources/02-pods \]$ kubectl describe pod annotations
    Name :
    annotations
    Namespace :
    default
    Priority:
    0
    Service Account :
    default
    Node :
    ip-192-168-31-172. ec2. internal/192 . 168 . 31.172
    Start Time:
    Tue, 27 Aug 2024 10:24:25 +0000
    Labels :
    Trainer=SivakumarReddy
    course=Devops
    Annotations :
    com . roboshop . training . duration: 120 hours
    jenkins. url: https:/ /jenkins. com/roboshop/catalogue#45
    Status :
    Running
    IP:
    192 . 168 . 26.59

[^15]: Kubernetes Labels
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

[^16]: VM vs containerisation
    VM --> 2GB 2CPU --> resources are blocked irrespective of usage
    containerisation --> containers don't block resources, they are used dynamically
    1 VM --> roboshop containers/pods, amazon containers/pods
    traffic increased/code caused more resources to consume
    VM will be blocked by a single container
    we can restrict the resources consumed by containers...

[^17]: spec:
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

[^18]: Services
    if you want to expose pods to other applications or outside we must use services..
    1. expose to other apps or outside world
    2. load balancing
    3. service mesh
    1. Cluster IP --> purely internal to kubernets
    2. NodePort --> you can expose to outside world
    3. LoadBalancer --> you can expose to outside world

[^19]: Service
    Pod
    names as DNS

[^20]: 30133
    30133
    Cluster IP
    Pod
    to
    Actor
    30133
    NADES

[^21]: LoadBalancer
    NodePort
    Cluster IP

[^22]: 30133
    31197
    LB
    30133
    Cluster IP
    Pod
    31197
    Actor
    31197
    30133

[^23]: catalogue : 1. 0.0
    catalogue : 1 . 2. 0
    cluster-ip < node-port < load-balancer
    pod < replicaset < deployment

[^24]: DS
    RS
    pod
    pod
    osgood

[^25]: DS
    RS
    RS-2
    pod
    pod
    pod
    pod

[^26]: DS
    RS
    RS-2
    pod
    pod
    pod
    pod
    pod
    pod

[^27]: stateful vs stateless
    storage
    CRUD
    create data, read the data, update data, delete data. .
    file
    excel
    logs
    RDBMS
    NOSQL
    stateful applications --> doing operations on the data directly.

[^28]: catalogue cart user shipping payment web --> no own database, apps are not storing anything
    stateless Applications
    I
    we can immidiately restore, no business impact..

[^29]: K
    Amazon EKS

[^30]: Amazon EKS
    Storage
    EBS/EFS

[^31]: storage or k8 volumes
    stores data in worker nodes, internal volumes
    1. emptyDip
    2. hostPath
    external volumes
    - -
    1. static provisioning
    2. dynamic provisioning

[^32]: yaml
    Copy code
    apiVersion: v1
    kind: Pod
    metadata :
    name: example-pod
    spec :
    containers :
    - name: example-container
    image: busybox
    volumeMounts :
    - mountPath : /tmp
    name: temp- storage
    volumes :
    name: temp- storage
    emptyDir: {}

[^33]: yaml
    Copy code
    apiVersion: v1
    kind: ConfigMap
    metadata :
    name: filebeat-config
    namespace: kube-system
    data :
    filebeat . ym1 : \|
    filebeat . inputs :
    - type: container
    paths :
    - /var/lib/docker/containers/\*/\*.log
    processors :
    - add_kubernetes_metadata :
    in_cluster: true
    output . elasticsearch:
    hosts: \["http://elasticsearch: 9200"\]
    setup . kibana :
    host: "kibana : 5601"

[^34]: K
    Amazon EKS
    F--7
    PVC
    EBS

[^35]: Using Persistent Volumes:
    1. Create a PersistentVolume (PV):
    yaml
    Copy code
    apiVersion: v1
    kind: PersistentVolume
    metadata :
    name: my - pv
    spec :
    capacity :
    storage: 10Gi
    accessModes :
    - ReadWriteOnce
    persistentVolumeReclaimPolicy: Retain
    nfs :
    path: /path/on/nfs/server
    server: nfs-server-address

[^36]: 2. Create a PersistentVolumeClaim (PVC):
    yaml
    Copy code
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata :
    name: my - pvc
    spec :
    accessModes :
    -
    ReadWriteOnce
    resources :
    requests :
    storage: 10Gi

[^37]: Static Provisioning
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

[^38]: Dynamic Provisioning
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

[^39]: static
    1. first we need to create storage, either storage admin or k8 admin will create the storage
    2. we need to make this volume available to k8 cluster. we should install drivers.
    aws-ebs-csi drivers should be installed
    3. a proper role should be attached to ec2 instance to access EBS.

[^40]: 1. volume should be created automatically.
    2. there is another object called storageClass that can create storage dynamically based on
    the request.
    here external volume and pv would be created automatically by storageClass...

[^41]: 2. we need to make this volume available to k8 cluster. we should install drivers.
    aws-ebs-csi drivers should be installed
    3. a proper role should be attached to ec2 instance to access EBS.

[^42]: Helm Charts
    1. templatise the kubernetes manifests
    2. package manager for kubernetes

[^43]: bash
    Copy code
    helm install myapp ./myapp-chart
    This installs the entire application stack with one command!

[^44]: yaml
    Copy code
    apiVersion: apps/v1
    kind: StatefulSet
    metadata :
    name : web
    spec :
    serviceName: "nginx"
    replicas : 3
    selector :
    matchLabels :
    app : nginx
    template :
    metadata :
    labels :
    app: nginx
    spec :
    containers :
    name: nginx
    image: nginx
    ports :
    containerPort: 80
    volumeClaimTemplates :
    - metadata :
    name : www
    spec :
    accessModes: \[ "ReadWriteOnce" \]
    resources :
    requests :
    storage: 1Gi

[^45]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
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

[^46]: createUser
    user created
    NODE-1
    master
    NODE-2
    NODE-3
    My SQL

[^47]: yaml
    Copy code
    apiVersion: v1
    kind: Service
    metadata:
    name: my-headless-service
    spec :
    clusterIP: None # This makes the service headless
    selector :
    app : my- app
    ports:
    - port: 80

[^48]: 1. Role: Define what actions are allowed.
    yaml
    Copy code
    apiVersion: rbac . authorization . k8s . io/v1
    kind: Role
    metadata :
    namespace: dev # The role is limited to the 'dev' namespace
    name : pod-creator
    rules :
    - apiGroups: \[""\]
    resources: \["pods"\]
    verbs: \["create"\] # This role allows creating pods
    2. RoleBinding: Assign the role to a user.
    yaml
    Copy code
    apiVersion: rbac . authorization . k8s . io/v1
    kind: RoleBinding
    metadata :
    name: bind-pod-creator
    namespace: dev # Binding applies to 'dev' namespace
    subjects :
    kind: User
    name: dev-user # The user we are granting the role to
    apiGroup: rbac . authorization . k8s . io
    roleRef :
    kind: Role
    name: pod-creator # Refers to the 'pod-creator' role
    apiGroup: rbac . authorization . k8s . io

[^49]: namespace level
    - - -
    Role
    RoleBinding
    ClusterLevel
    ClusterRole
    ClusterRoleBinding

[^50]: 1. trainees --> read-only
    2. engineers --> limited write access
    3. team leader --> namespace admin

[^51]: Role example
    Here's an example Role in the "default" namespace that can be used to grant read access to pods:
    apiversion: rbac. authorization.k8s.io/v1
    kind: Role
    metadata:
    namespace: default
    name :
    pod -reader
    rules :
    - apiGroups: \[""\] # "" indicates the core API group
    resources: \["pods"\]
    verbs: \["get", "watch", "list"\]

[^52]: 1. authentication
    2. authorization

[^53]: EKS will use IAM for authentication. ..authorization should be from EKS

[^54]: HPA
    Autoscaling --> Avg CPU utilisation, if crosses 75% then VM are getting increased.

[^55]: How does a HorizontalPodAutoscaler work?
    Pod 1
    Pod 2
    Pod N
    BC / Deployment
    .....
    Scale
    Horizontal Pod Autoscaler

[^56]: yaml
    Copy code
    apiVersion: apps/v1
    kind: Deployment
    metadata:
    name : my- app
    spec :
    replicas: 2
    selector :
    matchLabels :
    app : my - app
    template :
    metadata :
    labels :
    app: my-app
    spec :
    containers :
    - name : app-container
    image : my-app-image
    resources :
    requests :
    cpu: 200m
    limits :
    cpu: 500m

[^57]: yaml
    Copy code
    apiVersion: autoscaling/v2
    kind: HorizontalPodAutoscaler
    metadata :
    name : my - app-hpa
    spec :
    scaleTargetRef :
    apiVersion: apps/v1
    kind: Deployment
    name : my- app
    minReplicas: 2
    maxReplicas: 10
    metrics :
    - type: Resource
    resource :
    name : cpu
    target:
    type: Utilization
    averageUtilization: 50 # Scale if CPU usage exceeds 50%

[^58]: Cluster
    Nodes
    Container
    runtime
    HPA
    1
    5
    4
    cAdvisor
    API
    metrics
    Metrics-
    Summary
    kubelet
    2
    Container
    server
    API
    Server
    API 3
    runtime
    pod data
    kubectl
    top

[^59]: VERTICAL SCALING
    HORIZONTAL SCALING
    Increase size of instance
    ( Add more instances )
    ( RAM, CPU etc. )
    OC
    Wikitechy

[^60]: Incoming request
    {+ Ingress
    Cluster
    Service
    Service
    Pod
    Pod
    Pod

[^61]: Yaml
    O Copy
    apiVersion: networking . k8s . io/v1
    kind: Ingress
    metadata :
    name: example-ingress
    spec :
    rules :
    host: yourdomain . com
    http:
    paths :
    - path: /app
    pathType: Prefix
    backend :
    service :
    name : web-app-service
    port :
    number : 80
    path: /api
    pathType: Prefix
    backend :
    service :
    name: api-service
    port:
    number : 80

[^62]: ingress
    appl . daws76s . online --> Ingress Controller --> ingress --> appl service --> appl pod

[^63]: 3 nodes --> 1.27
    upgrade master node --> you can't deploy new applications. but existing applications will
    run. we will announce downtime.
    we will create another node group --> 1.29 --> green
    we will slowly drain the nodes. for example old-node-1 is drained and other old nodes are
    tainted. then pods will automatically come up into new nodes.. .
    we will old node group. ..

[^64]: yaml
    Copy code
    apiVersion: v1
    kind: Pod
    metadata :
    name : my- pod
    spec :
    tolerations :
    - key: "key"
    operator: "Equal"
    value: "value"
    effect: "NoSchedule"

[^65]: yaml
    Copy code
    tolerations :
    - key: "gpu"
    operator: "Equal"
    value: "true"
    effect: "NoSchedule"

[^66]: yaml
    Copy code
    apiVersion: v1
    kind: Pod
    metadata:
    name: pod-with-node-affinity
    spec :
    affinity :
    nodeAffinity :
    requiredDuringSchedulingIgnoredDuringExecution :
    nodeSelectorTerms :
    - matchExpressions :
    - key: disktype
    operator: In
    values :
    - ssd
    containers :
    - name : my-container
    image: nginx

[^67]: yaml
    Copy code
    apiVersion: v1
    kind: Pod
    metadata :
    name: pod-with-pod-affinity
    spec :
    affinity :
    podAffinity:
    requiredDuringSchedulingIgnoredDuringExecution :
    labelSelector :
    matchExpressions :
    - key: app
    operator : In
    values :
    - my - app
    topologyKey: "kubernetes . io/hostname"
    containers :
    - name: my-container
    image: nginx

[^68]: yami
    Copy code
    apiVersion: v1
    kind: Pod
    metadata :
    name: pod-with-pod-anti-affinity
    spec :
    affinity :
    podAntiAffinity :
    requiredDuringSchedulingIgnoredDuringExecution :
    labelSelector :
    matchExpressions :
    - key : app
    operator: In
    values :
    - my - app
    topologyKey: "kubernetes . io/hostname"
    containers :
    - name : my-container
    image : nginx
    This ensures that no two pods with the label app=my-app will be scheduled on the same node. You
    can also use zone or region for spreading across larger topological areas.

[^69]: NAME
    READY
    STATUS
    RESTARTS
    AGE
    techops-examples
    0/1
    CreateContainerError
    5m

[^70]: Kubernetes Container Creation Error
    Client
    Kubernetes
    Container
    API
    Runtime
    Request container creation
    Initialize container
    failure
    < Fail to create container
    error
    CreateContainerError
    Client
    Kubernetes
    Container
    API
    Runtime

[^71]: Cause
    Description
    Incorrect Image
    The image specified in the Pod manifest
    doesn't exist, is unavailable, or lacks a
    command..
    Resource Constraints
    If the requested resources (CPU or
    memory) exceed the available capacity
    on the node.
    Volume Mount Issues
    The Pod is trying to mount a volume
    that doesn't exist or is misconfigured.
    Container Runtime Error
    An issue with the container runtime
    (e.g., Docker, containerd) on the node.

[^72]: Containers :
    techops -examples :
    Container ID:
    Image :
    ubuntu : latest
    Image ID:
    State:
    Waiting
    Reason:
    CreateContainerError
    Ready :
    False
    Restart Count: 0
    Resources :
    limits :
    memory : "4Gi"
    cpu: "2000m"
    Volumes :
    data-volume :
    Type :
    PersistentVolumeClaim (created from a PVC)
    Name :
    data-pvc
    Optional: false

[^73]: LAST SEEN
    TYPE
    REASON
    OBJECT
    MESSAGE
    30s
    Warning
    FailedCreate
    pod/techops -examples
    Failed to create container: CreateContainerError

[^74]: containers :
    - name: techops-examples
    image: nginx : 1. 21.3
    command: \["/bin/bash", "-c"
    "echo Application is up" \]

[^75]: resources :
    requests :
    memory : "2Gi"
    cpu: "1000m"

[^76]: volumes :
    - name: data-volume
    persistentVolumeClaim :
    claimName: data-pvc

[^77]: $ kubectl get pods
    NAME READY STATUS RESTARTS AGE
    techops-app 0/1 RunContainerError 0 6m 12s

[^78]: 
    - Missing or incorrect volume mounts (e.g., ConfigMap or Secret).

    - Attempting to write to a read-only volume.

    - Invalid commands or missing executables.

    - Permissions or security context issues.

[^79]: $ kubectl describe pod techops-app
    Events:
    Type Reason Age From Message
    Normal Scheduled 6m default-scheduler Successfully assigned default/techops-app to node-1
    Normal Pulling 6m kubelet Pulling image "techops-image:latest"
    Normal Pulled 6m kubelet Successfully pulled image "techops-image:latest"
    Warning Failed 6m kubelet Error: failed to start container "techops-container": Error
    response from daemon: oci runtime error: container_linux.go:345: starting container process
    caused "exec: \\"/app/start.sh\\": permission denied"
    Warning BackOff 5m (x3 over 6m) kubelet Back-off restarting failed container

[^80]: $ kubectl logs techops-app -c techops-container
    /bin/sh: 1: /app/start.sh: Permission denied

[^81]: $ kubectl get configmap techops-config
    Error from server (NotFound): configmaps "techops-config" not found
    $ kubectl get secret techops-secret
    Error from server (NotFound): secrets "techops-secret" not found

[^82]: containers:
    - name: techops-container
    image: techops-image:v1.2.3
    command: \["/app/start.sh"\]
    args: \["--env", "production", "--debug", "false"\]

[^83]: securityContext:
    runAsUser: 1000
    runAsGroup: 3000

[^84]: kubectl exec -it techops-app -- Is -\| /app/start.sh
    -rwxr-xr-- 1 appuser appgroup 4096 Nov 5 07:00 /app/start.sh
    In crux, proper file permissions, valid volume mounts, accurate command paths,
    and appropriate user contexts help to prevent RunContainerError.

[^85]: Pod level
    Container level
    Pod + Container
    pod.yaml
    pod.yaml
    pod.yaml
    apiVersion: v1
    apiVersion: v1
    apiVersion: v1
    kind: Pod
    kind: Pod
    kind: Pod
    metadata:
    metadata:
    metadata:
    name: techops-examples-pod
    name: techops-examples-pod
    name: techops-examples-pod
    spec:
    spec:
    spec:
    securityContext:
    containers:
    securityContext:
    runAsUser: 3000
    - name: app-container
    runAsUser: 3000
    fsGroup: 4000
    image: redis:6.2
    containers:
    containers:
    securityContext:
    - name: app-container
    - name: app-container
    runAsUser: 3000
    image: redis:6.2
    image: redis:6.2
    - name: log-container
    securityContext:
    - name: log-container
    image: fluentd:latest
    runAsUser: 5000
    image: fluentd:latest
    securityContext:
    runAsUser: 5000
    techopsexamples.com
    inherited by all containers
    applied individual containers container level overrides pod

[^86]: 
    - **runAsNonRoot & runAsUser:** Ensure containers don't run as root, enforcing a non-privileged user setup.

    - **allowPrivilegeEscalation:** Prevent containers from gaining additional privileges.

    - **readOnlyRootFilesystem:** Locks down the root filesystem to prevent tampering.

    - **seccomp:** Limits system calls, offering another layer of security by using profiles like `RuntimeDefault` or custom ones.

[^87]: apiVersion: v1
    kind: Pod
    metadata:
    name: techops-examples-pod
    spec:
    securityContext:
    runAsUser: 3000
    fsGroup: 4000
    runAsNonRoot: true
    allowPrivilegeEscalation: false
    readOnlyRootFilesystem: true
    seccompProfile:
    type: RuntimeDefault
    containers:
    - name: app-container
    image: redis:6.2
    - name: log-container
    image: fluentd:latest

[^88]: apiVersion: v1
    kind: Pod
    metadata:
    name: techops-examples-pod
    spec:
    containers:
    - name: app-container
    image: redis:6.2
    securityContext:
    runAsUser: 3000
    runAsNonRoot: true
    allowPrivilegeEscalation: false
    readOnlyRootFilesystem: true
    seccompProfile:
    type: RuntimeDefault
    - name: log-container
    image: fluentd: latest
    securityContext:
    runAsUser: 5000
    runAsNonRoot: true
    allowPrivilegeEscalation: false
    readOnlyRootFilesystem: true
    seccompProfile:
    type: Localhost
    localhostProfile: "custom-seccomp-profile.json"

[^89]: apiVersion: v1
    kind: Pod
    metadata:
    name: techops-examples-pod
    spec:
    securityContext:
    runAsUser: 3000
    runAsNonRoot: true
    allowPrivilegeEscalation: false
    readOnlyRootFilesystem: true
    seccompProfile:
    type: RuntimeDefault
    containers:
    - name: app-container
    image: redis:6.2
    securityContext:
    runAsUser: 5000
    runAsNonRoot: true
    allowPrivilegeEscalation: false
    readOnlyRootFilesystem: true

[^90]: Setting
    Defaults to
    Security best practice
    runAsNonRoot
    FALSE
    TRUE
    allowPrivilegeEscalation
    TRUE
    FALSE
    readOnlyRootFilesystem
    FALSE
    TRUE
    seccomp
    undefined
    RuntimeDefault or
    Localhost

[^91]: Star History
    aquasecurity/kube-bench
    stern/stern
    6.OK
    .ze gl/kube-score
    Cyberark/KubiScan
    E corneliusweig/rakkess
    5.0k
    4.0k
    GitHub Stars
    3.0k
    2.OK
    1,OK
    2018
    2020
    2022
    2024
    Date
    star-history.com

[^92]: 
    - YAML-based test configuration allows easy updates as specs evolve.

    - kube-bench auto-selects tests for the node's Kubernetes version.

[^93]: 
    - Filters pods with regex or <resource>/<name>, no exact pod IDs needed.

    - Tails all pod containers by default, but you can limit with the container flag.

    - Auto-removes deleted pods, adds new ones as created.

[^94]: 
    - Evaluates resource definitions like Deployments, Services, and Ingresses for misconfigs.

    - Supports CRD validation, checks labels, resource limits, and other key configs.

    - Provides a score based on best practices and highlights issues.

[^95]: 
    - Identify risky Pods\\Containers

    - Identify risky Roles\\ClusterRoles

    - Identify risky RoleBindings\\ClusterRoleBindings

    - Identify risky Subjects (Users, Groups and ServiceAccounts)

    - Dump tokens from pods (all or by namespace)

    - CVE scan

[^96]: 
    - Shows who can access Kubernetes resources and their actions.

    - Audits RBAC permissions for users, groups, and service accounts in a clear matrix view.

    - Supports CI/CD integration for continuous RBAC audits.

[^97]: 
    - Old clusters, users, and contexts staying in the config even after cluster deletion.

    - Manual cleanups becoming tedious and error-prone.

    - Slow and confusing environment switching due to too much clutter.

[^98]: clusters:
    - name: techopsexamples-cluster
    cluster:
    server: https://k8s.techopsexamples.com
    certificate-authority-data: Cluster CA

[^99]: users:
    - name: techopsexamples-user
    user:
    token: abc123tokenxyz

[^100]: contexts:
    - name: techopsexamples-context
    context:
    cluster: techopsexamples-cluster
    user: techopsexamples-user

[^101]: current-context: techopsexamples-context

[^102]: 
    ```
    kubectl config set-cluster techopsexamples-cluster --server=https://techopsexamples.cluster.com 
    ```

[^103]: 
    ```
    kubectl config set-credentials techopsexamples-user --token=abc123tokenxyz
    ```

[^104]: Sample cleanup summary:
    UBETIO
    Starting KubeTidy cleanup. ..
    Backup created at C: \\Users\\rhooper\\. kube\\config. bak_20240925_165258
    Removed clusters, users, and contexts related to unreachable clusters.
    Kubeconfig cleaned and saved.
    KubeTidy Summary
    Clusters Checked:
    35
    Clusters Removed:
    7
    Clusters Kept:
    28

[^105]: apiVersion: networking.k8s.io/v1
    kind: NetworkPolicy
    metadata:
    name: access-control-database
    spec:
    podSelector:
    matchLabels:
    app: techops-examples-db
    policy Types:
    - Ingress
    ingress:
    - from:
    - podSelector:
    matchLabels:
    role: admin

[^106]: 
    - **Labels Could Be Modified**: Developers could label any pod as  `role: admin` at runtime, granting it database access.

    - **Namespace Confusion**: Policies often overlooked namespaces, allowing a `role: admin` pod in the dev environment to mistakenly access production services.

[^107]: apiVersion: security.istio.io/v1
    kind: AuthorizationPolicy
    metadata:
    name: access-control-istio
    spec:
    rules:
    - from:
    - source:
    principals: \["cluster.local/ns/techops/saladmin-service-account"\]

[^108]: $ kubectl delete pod techops-pod
    pod "techops-pod" deleted

[^109]: Kube-Proxy
    Iptables
    Endpoint
    Controller
    API Server - Service
    Endpoint
    Endpoints
    Ingress
    Notified
    Core DNS
    kubectl delete pod
    API Server - ETCD
    SIGTERM
    SIGKILL
    POD DELETED
    deletion Timestamp
    deletionGracePeriodSeconds
    Terminating
    Notified
    API Server - kubelet
    Prestop Hook
    Graceful
    Shutdown
    API Server
    techopsexamples.com
    timeout 10s
    10s
    POD UP
    POD DOWN

[^110]: 1. kubectl delete pod: Triggers the API Server to update ETCD with
    deletionTimestamp and deletionGracePeriodSeconds, marking the pod
    as Terminating.
    2. API Server - Kubelet: Notifies the Kubelet of the pod's termination.
    3. Endpoint Controller: Removes the pod from active service endpoints,
    stopping any traffic from reaching the pod.
    4. PreStop Hook (if configured): Before sending SIGTERM, the Kubelet runs
    the PreStop Hook. This allows the pod to perform custom tasks (e.g., closing
    connections) during shutdown.
    5. SIGTERM: Kubelet sends SIGTERM, initiating a graceful shutdown. The pod
    is given the deletionGracePeriodSeconds (default 30s) to cleanly exit.
    6. Graceful Shutdown: During the grace period, the pod handles any ongoing
    tasks, such as completing requests or saving data, before it fully stops.
    7. SIGKILL: If the pod doesn't terminate within the grace period, SIGKILL is
    sent, forcing immediate shutdown.
    8. Pod Deleted: The API Server updates ETCD, marking the pod as deleted.
    Components like Kube-Proxy, Ingress, and others remove all references to
    the pod.
    Here are some common signals for your knowledge (though out of context):
    . SIGHUP: Hangup signal
    . SIGINT: Interrupt signal (triggered by Ctri+C)
    . SIGQUIT: Quit signal
    . SIGSTOP: Stop the process (cannot be caught or ignored)

[^111]: Warning NodePressure \[timestamp\] kubelet Node \[node-name \]
    status is now: NodeHasDiskPressure

[^112]: Implement Resource Quotas and Limits:
    apiVersion: v1
    kind: ResourceQuota
    metadata :
    name: storage-quota
    namespace: \[namespace\]
    spec :
    hard :
    requests . storage: 10Gi

[^113]: 
    - Provisions compute based on real-time pod needs

    - Launches only necessary instance types, consolidates workloads

    - Removes underutilized nodes, swaps expensive instances

[^114]: Pending pods
    Existing capacity
    Optimized capacity
    LLLLL
    sched
    88 8:
    LLLLL
    K
    TTTTT
    Unschedulable pods
    Just-in-time capacity
    TTTTT
    K
    Ref: Karpenter Architecture

[^115]: 
    - Enforces policies via validating and mutating requests

    - Targets resources by type, name, labels

    - Provides Policy Reports for compliance insights

[^116]: API
    HTTP
    Authn /
    Mutating
    Schema
    Validating
    etcd
    Request
    Handler
    Authz
    admission
    Validation
    admission
    Admission Review
    Admission
    Reports
    Admission Controller
    Background
    Scan Reports
    Webhook
    Webhook
    Report
    Configuration
    Controller
    Controllers
    Policy
    Engine
    Reports
    Cert
    Background
    Secrets
    Update
    Renewer
    Controller
    Requests
    -Kyverno Controllers
    Policies
    PolicyExceptions
    Ref: Kyverno architecture

[^117]: annotations :
    downscaler/downtime-replicas: "1"
    downscaler/uptime: Mon-Fri 08:00-19:00 Europe/Berlin

[^118]: 
    - `minAvailable` is below 100%.

    - `maxUnavailable` is above 0%.

    - Apps have more than one replica.

    - HPAs have `minReplicas` above 1.

[^119]: . Controller: A controller continuously monitors the state of resources and
    ensures the actual state matches the desired configuration. When something
    changes or fails, the controller works to bring things back into alignment.
    Control Loop
    Desired State
    Observe
    Act
    Analyze
    Actual State
    . Custom Resources (CRs): These are user-defined extensions to the
    Kubernetes API, allowing new functionality not provided by default. Custom
    Resource Definitions (CRDs) let you define new resources to represent your
    app's needs.
    Together, operators use CRDs and controllers to deploy and manage apps in
    Kubernetes clusters.
    Watch
    ooo
    Modifies
    Adjust State
    Change events
    User
    Custom Resource
    Operator
    Kubernetes
    API

[^120]: apiVersion: postgresql.dev/v1
    kind: PostgresCluster
    metadata:
    name: techops-database
    spec:
    instances: 3
    backups:
    enable: true
    schedule: "0 3 \* \* \*" # Daily backups at 3 am
    storage:
    size: 100Gi

[^121]: Downloads
    Creates
    Uploads
    Chart
    Deploys
    HELM
    Helm
    Helm user
    Developer
    Helm Charts
    Helm Repo
    Kubernetes
    cluster
    It provides all necessary configurations, dependencies, and templates for setting up
    applications in a Kubernetes cluster, acting as a blueprint for reusable, customizable
    deployments.
    Helm Chart Structure:
    techopsexampleschart/
    Helm chart root directory
    chart . yaml
    chart metadata ( name , version,
    description)
    LICENSE
    License information for the chart
    README . md
    Documentation and usage instructions
    values . yaml
    Default config values for customizing
    templates
    values . schema . json
    JSON schema for validating values. yaml
    input
    charts/-
    Holds chart dependencies
    templates/
    Kubernetes resource templates using Go
    deployment . yaml
    Deployment resource template
    service . yaml
    Service resource template
    _helpers . tpl
    Helper template for reusable content
    NOTES . txt
    Instructions displayed after chart
    installation

[^122]: dependencies:
    - name: redis
    version: "14.8.12"
    repository: "https://charts.bitnami.com/bitnami"

[^123]: Feature
    Kubernetes Operator
    Helm Chart
    Purpose
    Automates complex app
    Packages apps for
    lifecycles, especially for
    deployment on Kubernetes
    stateful apps
    Complexity
    Higher; requires CRDs
    Lower; uses templated
    and custom controllers
    YAML files
    Customization
    Highly customizable with
    Limited to values.yaml
    custom code
    parameters
    Lifecycle Management
    Full lifecycle (install,
    Basic lifecycle (install,
    update, scaling, failover)
    upgrade, remove)
    Learning Curve
    Steeper; requires
    Easier to learn; similar to
    understanding controllers package managers
    and CRDs
    GitOps
    Supports detailed, custom Basic GitOps for versioned
    GitOps workflows
    configurations
    Best For
    Apps needing complex
    Simple, deploy-only
    management
    applications

[^124]: /var/log/
    containers/
    Logs directory for each container in pods
    <pod-name>_<namespace>_<container-name><container-id> . log
    pods/
    <namespace>_<pod-name>_<uid>/
    <container-name>stdout . log
    Standard output log for the container
    <container-name>stderr . log -
    Standard error log for the container
    kubelet/
    kubelet . log
    Main log for kubelet service
    audit . log
    Audit logs for kubelet actions
    error. log
    Error logs for kubelet
    kube-apiserver/
    apiserver . log
    Main log for API server events
    audit . log
    API request audit logs
    error . log
    Error logs for the API server
    kube-scheduler/
    scheduler . log
    Scheduler logs for pod placements
    error . log
    Error logs for the scheduler
    kube-controller-manager/
    controller-manager . log
    Controller manager logs
    error . log
    Error logs for the controller manager

[^125]: etcd/
    etcd . log
    Main etcd log
    snapshot . log
    Logs for etcd snapshots
    error . log
    Error logs for eted
    containerd/
    containerd. log
    Logs from containerd runtime
    error . log
    Error logs for containerd
    network/
    techopsexamples. com
    cni . log
    Container Network Interface logs
    flannel . log
    Specific CNI provider logs
    calico. log
    Specific CNI provider logs
    error . log
    Network-related error logs
    node/
    syslog
    System level logs (Ubuntu/Debian)
    messages
    System level logs (RHEL/Centos)
    dmesg . log
    Hardware and boot information logs
    auth . log
    SSH and sudo actions authentication logs
    error . log
    Node-level error logs, if separated

[^126]: 1. Node logging Agent
    app-pod
    Logging
    app-container
    Backend
    stdout
    stderr
    log-file.log
    Pod
    logging-agent-pod
    logging-agent
    logrotate
    Ref: Kubernetes Documentation
    To implement cluster-level logging, deploy a node-level logging agent on each node,
    typically as a DaemonSet, to collect and forward logs to a backend.
    This agent, running as a container, accesses log directories from all application
    containers on the node.
    Node-level logging creates one agent per node without needing changes to
    applications.
    Containers log to stout and stderr in varied formats, which the node-level agent
    gathers for aggregation.

[^127]: 2. Streaming Sidecar Container
    app-pod
    app-container
    Logging
    streaming
    Backend
    container
    stdout
    stderr
    log-file.log
    Pad
    logging-agent-pod
    logging-agent
    logrotate
    Ref: Kubernetes Documentation
    By configuring sidecar containers to write to their own stout and stderr streams,
    you can leverage the kubelet and node-level logging agent already running on each
    node.
    Sidecars read logs from sources like files, sockets, or journald and output to
    separate streams, enabling multiple log streams for different application parts.
    This setup supports components that don't natively log to stdout or stderr, with
    minimal redirection overhead.
    Since kubelet manages stdout and stderr, you can easily access logs using tools
    like kubectl logs.

[^128]: 3. Sidecar Container With a Logging Agent
    app-pod
    Pod
    app-container
    Logging
    Backend
    logging-agent
    Ref: Kubernetes Documentation
    If the node-level logging agent doesn't meet your needs, you can add a sidecar
    container with a logging agent set up specifically for your application.
    4. Pushing Logs Directly From The Application
    app-pod
    Logging
    app-container
    Backend
    Ref: Kubernetes Documentation
    Logging that involves directly exposing or pushing logs from each application is
    outside the scope of Kubernetes, though it can be an option for specific cases, like
    when an application requires direct integration with an external logging service.

[^129]: Conventional Pipeline
    Kubernetes Pipeline
    code Commit
    Code Commit
    Developers
    Developers
    Build &
    Build &
    Test
    Test
    Store Builds in
    Push Image
    an artifactory
    to Registry
    Frog
    ARTIFACTORY
    techopsexamples .,co
    k8s Config
    Pull New
    Pull New
    Binary
    Docker Image
    Deploy
    Deploy
    Staging
    Staging
    Environment
    Cluster
    Sty Testing
    Sty Testing
    Deploy
    Deploy
    QA
    cluster
    QA
    QA Testing
    Rollout Strategy
    Environment
    QA Testing
    Deploy
    Blue-Green
    Canary
    Prod
    Deploy
    Environment
    Prod
    Monitor & Maintain
    Cluster
    Monitor & Maintain

[^130]: 100%
    V1
    LB
    V2

[^131]: 25%
    V1
    75%
    LB

[^132]: V1
    LB
    V2

[^133]: 
    - Organize your Kubernetes namespaces based on team functions or project requirements.

    - Implement [container scanning](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C6CV7bIeUUDlZGwHPz2MV4dJIEMmgeVe3vbXPtxx-2FYk0J0S1REDlPTu4hNtWn42SC4aOFP22k8uP-2B0nBYJ0z988-2BfyHIDuDHkmULVceV9XAcQypTRk-2FXhlt4UVruRyPWoxmQmkavBv90RsQ4jAEjUTSXDxeDSfnpkn2LTrjdJXmvBboKAZ0-2BHqZRZVwWRHFeNP-2F3IJoDVpJTHC-2FADyzRcuFTKDeMTZ1CJRE7FsXxxaRYFCTcmrt5JUD-2BAN8zFlgB6q2aXtLXEUS7IivjncEwkc504Bi-2FrzEfCo7LgcV2iRp8rXxr_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxMmx0IR1IqE0VVMXFJ5VGz2nI460971NCUB0Sy-2Fu7sOTOni6SH1ptUFdZ7KwTiaJMvPAat7FomGajpm8x8MHYwh2hWIRd9zDIovutwAzjSZWow-2FZJObhZCxNv3l5qlF2WnlrhFfX6IMpt3x1WuK8uub), secure your container registry, and regularly review access controls for Kubernetes resources.

    - Integrate [caching mechanisms](https://link.mail.beehiiv.com/ls/click?upn=u001.I5dhDmlt7nI3cxy6sds7C2dJ19d5fuEZK-2FSWdOqhfpCvMCq1ougs9pd7yOXstT7DoTJX5lHtkQlvLtUVujp9sOCyk8-2FZ8e-2B54tkHxNkfimBBis98PxD4MG7Bvlt-2BKzXgaSRIeig1olmc-2BgJQjXkBn7Us6HYTAQEAtckwotqbc2Jtv2WJU2ShOGGX16woKh2J3-2FbB5IpudhvIT12vUAaEoFYqYliNyCNp2A0qZ3oAzxQ3ML1LUFjUvauTEOiYt9yB8T3gvpB7HWWfF1HZXUsBeA-3D-3D3dzi_uS-2B26HIC5mmoe0MDqj4KlfrFog-2BNlFrKN68fhMFAYxMr4nPJinUD-2Bn8evikohMn-2BOsujFk-2F3l1aD8jNLLIMDu-2BinvkKr6G74EftfVwENY-2F0fJ2lk9gUnsHIJbwS-2Fy8AMrm9qvSDj8pYwInufpdckvli9XbdO6Z4dM1LwtWJGVerhBlf6JCFOFBhJnp15E6co87Ykd6n4G1TpmpnH8k3q61MpJYWx81HRiNLnQEheQL2aoOFKqzzOm8dxGrHdIT48FQkIgci3-2FQTuoE4mQ8Syzo4VmYIh6-2BBOh8GAG1o9rxNamBpnaoq6Nw8Kq9QC30namaywBr0IRYuJ-2FVHudXEI4LdTHVKLKHR8-2BeZ4vCgcZlunzeipU3kI4ryfhxo-2BDgn2HTtvpAPX-2FOi7nQYevr3mbJs-2FPPLno9KSMOICWcvVLD4-2F2Tu4EPeYsbBKemDi-2FC-2Bq) to avoid redundant builds, optimize image layers, and use lightweight base images to speed up deployments.

[^134]: apiVersion: v1
    kind: Pod
    Resource type (Pod in this case)
    metadata:
    name: techops-pod
    Unique name for the Pod
    labels:
    To organize and select Pods
    app: techops
    App label, useful for selectors
    tier: backend
    To identify the application layer
    spec :
    containers :
    Container (s ) running in this Pod
    name: techops-container
    Name of the container
    image: nginx : 1.23
    Docker image for the container
    ports :
    - containerPort: 80
    Port the container exposes internally
    env :
    Environment variables for configuration
    name : ENV
    value: production
    volumeMounts :
    > Volumes mounted inside the container
    name: config-volume
    > Volume defined in the "volumes" section
    mountPath: /usr/share/nginx/html
    Mount point inside the container
    volumes :
    name: config-volume
    Name of the volume
    configMap :
    > Use ConfigMap as the source
    name: techops-config.
    Reference the ConfigMap named
    "techops-config"
    restartPolicy: Always
    echopsexamples . com
    Pod restart policy ( Always, OnFailure,
    or Never)
    nodeSelector:
    Schedule pod on specific nodes
    disktype: ssd
    Schedule only on nodes labeled with
    ' disktype = ssd "
    tolerations :
    Allows scheduling on tainted nodes
    - key: "special-taint"
    Taint key to tolerate
    operator: "Equal"
    > (exact match) or Exists
    value: "true"
    Value to match
    effect: "NoExecute"
    Effect: NoSchedule (can't schedule),
    NoExecute (evict)
    securityContext:
    Pod-level security settings
    runAsUser: 1000
    Run containers as this user ID
    runAsGroup : 3000
    > Run containers with this group ID
    fsGroup: 2000
    Group ownership for mounted volumes
    initContainers :
    Runs before the main containers
    name: init-techops
    Init container name
    image: busybox
    -> Image for the init container
    command: \["sh", "-c", "echo Init; sleep 5"\]
    > Setup commands

[^135]: livenessProbe :
    Checks if the container is still running
    httpGet:
    path: /healthz
    HTTP endpoint to check health
    port : 80
    Port to send the HTTP request to
    initialDelaySeconds : 3.
    > Wait time before starting health checks
    periodSeconds : 5-
    > Interval between checks
    readinessProbe :
    > Checks if the container is ready to
    httpGet :
    techopsexamples com
    serve traffic
    path: /ready
    HTTP endpoint to check readiness
    port: 80
    Port to send the HTTP request to
    initialDelaySeconds : 3-
    > Wait time before starting readiness checks
    periodSeconds : 5
    > Interval between checks
    pod. yaml probes section sample

[^136]: spec :
    affinity :
    nodeAffinity :
    Rules to control node selection
    requiredDuringSchedulingIgnoredDuringExecution :
    nodeSelectorTerms :
    - matchExpressions :
    - key: zone
    Node must have the "zone" label
    operator: In
    .com
    > Operator: matches any of the specified
    values :
    - us-west-la
    sechopsexamples
    values
    Allowed zone: us-west-1a
    - us-west-1b
    > Allowed zone: us-west-16
    podAffinity :
    > Prefer Pods to be scheduled together
    preferredDuringSchedulingIgnoredDuringExecution :
    - weight : 100
    Priority of this preference
    podAffinityTerm:
    (higher = stronger)
    labelSelector:
    matchLabels :
    app: techops
    Prefer Pods with the "app=techops" label
    topologyKey: kubernetes . io/hostname
    Same node
    pod. yaml affinity section sample

[^137]: 
    - Monolithic vs Microservices

    - Serverless vs Self-Managed Virtual Instances

    - Kubernetes vs Do we really need Kubernetes?

[^138]: 
    - **Monolithic architecture** is a single, tightly integrated application where all components function as one unit.

    - **Microservices architecture** is a design where the application is split into independent services communicating via APIs.

[^139]: Monolith
    Micro Services
    Front End
    - - - ---
    Back End
    API Gateway / BFF
    O
    O
    Storage ----.

[^140]: Misaligned complexity can create a real problem, not the architecture itself.
    Imagine a spectrum.
    On the far left, your system has a manageable number of services:
    On the far right, the system has fragmented into too many services:
    The red square on the left is where microservices worked well initially:
    The green square is where the system ended up, due to uncontrolled growth:
    The gap between
    and is the misaligned complexity.
    You can call it "the microservices sprawl"
    Red Flags to Identify When Your Microservices Architecture is Becoming a
    Bad Idea:
    Duplicate functionalities across multiple services.
    Wasted resources on scaling less critical services.
    Poor visibility into service health and dependencies.
    Frequent cascading failures due to interdependencies.
    Overlapping responsibilities with unclear service ownership.
    Complex inter-service communication slows down troubleshooting.
    In short,
    It's the result of too many services, fragmented ownership, and poor boundaries.
    Unless you bring this under control, microservices will become a liability.

[^141]: 
    ### **1. Streamline and consolidate services**

[^142]: 
    - Merge services with overlapping functionalities

    - Reduce the granularity of services where it’s unnecessary

    - Centralize non-critical shared services

[^143]: 
    ### **2. Improve operational management**

[^144]: 
    - Introduce robust service discovery and dependency mapping tools

    - Enforce architectural boundaries and team ownership

    - Use automation for scaling, monitoring, and troubleshooting

[^145]: 1.31.x
    1.31.
    1.30 x
    1.30.x
    1.29.x
    1.29.x
    1.28 x
    1.28.
    1.27.x
    1.27.x
    1.26.X
    1.26.x
    1.25 x
    1.25.x
    1.24x
    1.24.X
    1.23 x
    1.23.x
    1.22 x
    1.22.x
    121.X
    1.21.x
    1.20 x
    1.20.x
    1.19.x
    1.19.x
    1.18 x
    1.18.x
    1.17.x
    1.17 x
    1.16.x
    1,16x
    1.15.X
    1.15.x
    1.14x
    1.14.x
    1.13x
    1,13.X
    2019
    2020
    2021
    2022
    2023
    2024
    202
    Kubernetes Versions Support Timeline

[^146]: Kubernetes Cluster Upgrade
    Cheat Sheet
    www.techopsexamples.com
    SCOPE THE UPGRADE
    UPGRADE ORDER
    COMPONENTS
    PREPARATION
    K Control Plane Node
    \*\* Kubeadm
    >\* Check Current Cluster Version
    \* Worker Nodes
    \* Kubelet
    kubectl version
    \* Kubectl
    K Backup Your Cluster
    \* Plan for Downtime
    Start Here !
    Control Plane
    DO's
    (Master Node )
    V
    Follow
    VERIFY KUBEADM VERSION
    Upgrade
    Documentation
    Worker Nodes
    kubeadm version -o json
    V
    Monitor Progress
    CHOOSE UPGRADE VERSION
    kubeadm upgrade plan
    Post-Upgrade
    Testing
    UNHOLD KUBEADM & INSTALL REQUIRED VERSION
    apt-mark unhold kubeadm & & apt-get update & & apt-get
    install -y kubeadm =x.yy.2-00 && apt-mark hold kubeadm
    DONT's
    APPLY KUBEADM UPGRADE
    X
    kubeadm upgrade node
    Rush
    VALIDATE UPGRADED VERSION
    Skip Rollback
    kubeadm version -o json
    Planning
    DRAIN THE NODE
    X
    Assume a Smooth
    kubectl drain <node> --ignore-daemonsets
    Upgrade
    UPGRADE KUBELET & KUBECTL
    apt-mark unhold kubelet kubectl && apt-get update && apt-get install -y
    kubelet=x.yy.2-00 kubectl=x.yy.2-00 && apt-mark hold kubelet kubectl
    RESTART SERVICES
    systemctl daemon-reload & systemctl restart kubelet
    UNCORDON THE NODE
    am/
    kubectl uncordon <node>
    Great job !"
    VERIFY UPGRADED VERSION C Pick up next
    kubectl get nodes

[^147]: Cost Distribution Over Black Friday (Using Karpenter)
    Instance Types
    1400
    Savings Plans
    Spot Instances
    On-Demand Instances
    1200
    1000
    800
    Cost ($)
    600
    400
    200
    Hour 1
    Hour 2
    Hour 3
    Hour 4
    Hour 5
    Hour 6
    Hour 7
    Hour 8
    Hour 9
    Hour 10
    Hour 11
    Hour 12
    Time Intervals

[^148]: 1. Enable Feature Gates
    Helm Chart Configuration to update and deploy:
    settings:
    featureGates:
    SpotToSpotConsolidation: true
    Drift: true
    NodeRepair: true

[^149]: 2. Configure Provisioner
    apiVersion: karpenter.sh/v1alpha5
    kind: Provisioner
    metadata:
    name: techops-provisioner
    spec:
    requirements:
    - key: "karpenter.sh/capacity-type"
    operator: In
    values: \["spot"\]
    provider:
    instance Types: \["m5.large", "m5.xlarge"\]
    ttiSecondsAfterEmpty: 30
    consolidation:
    enabled: true

[^150]: 3. Monitoring and Observability
    SpotToSpotConsolidation Logs:
    {"level": "info", "msg": "Migrating workload from spot node
    techops1 to more stable node techops2"}
    Drift Detection Logs:
    {"level": "info", "msg": "Drift detected on node techops1. Marking
    for termination and replacement."}
    NodeRepair Logs:
    {"level": "info", "msg": "Node repair initiated for unhealthy node
    techops1"}
    {"level": "info", "msg" : "Node replaced successfully"}
    Final Results:
    . 30% cost savings
    . Lean, healthy infrastructure
    . Zero downtime throughout the event

[^151]: Before
    After
    (Higher Latency)
    (Lower Latency)
    apiVersion: v1
    apiVersion: v1
    kind: Service
    kind: Service
    metadata:
    metadata:
    name: frontend-service
    name: frontend-service
    spec:
    spec:
    selector:
    selector:
    app: app-1
    app: app-1
    ports:
    ports:
    - protocol: TCP
    - protocol: TCP
    port: 80
    port: 80
    targetPort: 9376
    targetPort: 9376
    external TrafficPolicy: Local
    techopsexamples.com
    sessionAffinity: ClientIP

[^152]: 
    ### **externalTrafficPolicy: Local**

[^153]: 
    ### **sessionAffinity: ClientIP**

[^154]: affinity:
    podAntiAffinity:
    requiredDuring SchedulingIgnoredDuring Execution:
    - labelSelector:
    matchLabels:
    app: frontend
    topologyKey: kubernetes.io/hostname

[^155]: resources:
    requests:
    cpu: "500m"
    memory: "256Mi"
    limits:
    cpu: "1 "
    memory: "512Mi"

[^156]: Sample Network Policy to Allow Traffic from Specific IPs:
    ingress:
    - from:
    - ipBlock:
    cidr: 192.168.1.0/24
    ports:
    - protocol: TCP
    port: 80

[^157]: What do you want the attacker to see?
    echo $TECHOPS_API KEY
    \* \* \* \* \* \* \*\*
    OR
    echo $TECHOPS_API KEY
    lousy_apikey_get_in

[^158]: Top 10
    CICD-SEC-1 Insufficient Flow Control Mechanisms
    CI/CD
    CICD-SEC-2 Inadequate Identity and Access Management
    CICD-SEC-3 Dependency Chain Abuse
    Security
    CICD-SEC-4 Poisoned Pipeline Execution (PPE)
    Risks
    CICD-SEC-5 Insufficient PBAC (Pipeline-Based Access Controls)
    CICD-SEC-6 Insufficient Credential Hygiene
    CICD-SEC-7 Insecure System Configuration
    . . . . .
    CICD-SEC-8 Ungoverned Usage of 3rd Party Services
    CICD-SEC-9 Improper Artifact Integrity Validation
    OWASP
    CICD-SEC-10 Insufficient Logging and Visibility
    A point worth noting here, Secrets/Credentials handling cuts through other major
    risks.

[^159]: Why the
    PRINCIPLE of
    POLP
    LEAST PRIVILEGE
    Matters
    SHRINK
    ATTACK
    IMPROVE
    SURFACE
    opeRational
    PERFORMANCE
    \*
    STOP MALWARE in its tracks
    O
    20s
    Prepare
    for
    AUDITS
    guard
    against HUMAN ERROR

[^160]: 
    1. AWS Secrets Manager

    1. HashiCorp Vault

    1. Azure KeyVault

    1. Google Cloud Secret Manager

    1. Docker Secrets

[^161]: CI/CD
    Transit
    Azure
    Microsoft
    PKI Certificates
    Aare
    AWS
    aws
    Key /Value
    Consul
    Google
    Databases
    OIDC
    Nomad
    Kubernetes
    6 Token
    GitHub
    GitHub
    8
    SSH
    KMIP
    Nomad
    aws
    AWS
    Token
    Vault
    Google
    LDAP, Okta, RADIUS
    okta
    Azure
    Custom
    Transform
    PKI Certificates
    System
    Custom
    Kerberos
    8
    Authentication

[^162]: k8s-project/
    base/
    Common / shared Kubernetes manifests
    deployment . yaml
    Deployment manifest
    service . yaml
    Service definition to expose the app
    configmap . yaml
    ConfigMap for non sensitive configs
    ingress . yaml
    Ingress for routing traffic to the app
    kustomization . yaml
    Kustomize config to bundle resources
    overlays/
    Environment specific configs
    dev/
    Dev environment overrides
    kustomization . yaml
    Dev environment specific patches
    namespace . yaml
    To isolate resources in Dev
    configmap . yaml
    To override Dev specific configs
    ingress . yaml
    Dev Custom domain and SSL configs
    Outputs for bucket name and ARN
    techopsexamples. com
    staging/
    Staging environment overrides
    Same structure as 'Dev'
    prod/
    Production environment overrides
    Same structure as "Dev' and 'Staging'
    helm/
    For templating Kubernetes manifests
    Chart . yaml
    Helm chart metadata
    values . yaml
    Shared default values for Helm chart
    values/
    Environment-specific Helm values
    dev-values . yaml
    Dev specific configurations
    staging-values . yaml
    Staging specific configurations
    prod-values . yaml
    Production specific configurations

[^163]: Kubernetes POD Lifecycle - Behind the Scenes
    Pod accepted by the
    Pod is scheduled to a
    All Containers
    API server, staying
    node, with at least
    in the pod
    Pending
    one container defined
    terminated
    until containers
    in the pod
    Running
    Successfully
    are started
    Pending
    Running
    Succeeded
    Unknown
    Failed
    techopsexamples. com
    Kubelet stops
    One or more
    reporting to the
    containers excited
    API Server, the POD
    with non-zero
    is shown as
    status / terminated
    Unknown
    Unsuccessfully

[^164]: Top 10 Must-Know Design Patterns for Kubernetes Beginners
    Foundational
    Structural
    Behavioural
    Higher-level
    Health Probe
    1 1
    Batch Job
    Init Container
    Controller
    Predictable Demands
    Sidecar
    Stateful Service
    Operator
    M
    M
    Automated Placement
    Service Discovery
    Credit: Redhat

[^165]: Normal Containers
    Ephemeral Containers
    Start Agent
    Start Agent
    Agent queries kubelet for ContainerID
    techopsexamples. com
    Agent fetches Pod PID or Namespace from
    Agent launches an ephemeral container with
    runtime API
    preloaded utilities
    Agent mounts required utilities or scripts
    manually
    Agent executes tasks inside the production
    Tasks are executed in the ephemeral container
    container (risk of side effects)
    (isolated from app container)

[^166]: Launch an Ephemeral Container
    kubectl debug <pod-name> -c debug-container --image=busybox --
    target=<main-container>
    # Inspect Logs in the Ephemeral Container:
    kubectl logs <pod-name> -c debug-container
    # Run Commands in the Ephemeral Container:
    kubectl exec -it <pod-name> -c debug-container - - sh

[^167]: Kubernetes HPA vs VPA vs KEDA
    techopsexamples . com
    VPA
    Event Sources
    2. Calculate
    HPA
    replicas
    go kafka laRabbitMQ
    1. Read
    3. Provide pod
    1. Emit Events
    Configs
    resource
    from VP A
    recommendations
    KEDA Operator
    1. Query for
    3. Update the
    metrics
    Replica Count
    VPA
    Metrics
    7.
    Adapter
    Controller
    Scaler
    Recommender
    Apply
    pod
    4. Pod
    Spec
    3. Send
    2. Provides Metrics
    resource
    2. Reads pod
    Scaling
    Metrics Server
    recommendation
    resource
    instructions
    utilization metrics
    Kubernetes API Sever
    VPA
    HPA
    Metrics Server
    4. Scales
    Updater
    VPA
    up / down
    5 . Terminate
    Admission
    Deployment
    the pod
    Controller
    Deployment
    Replica Set
    Deployment
    8. Monitor
    Replica Set
    utilization
    4. Desired
    metrics
    5 . Desired
    6. Recreates
    replicas
    replicas
    pod
    Pod
    Pod 1
    Pod 2
    Pod N
    Pod 1
    Pod 2
    Pod N
    cpu: "500m"

[^168]: 
    1. **HPA + VPA**: Use HPA to scale pods based on CPU/memory usage while VPA adjusts pod resource requests for efficient utilization.

    1. **HPA + KEDA**: Use HPA for resource-based scaling and KEDA for event-driven scaling.

    1. **HPA + VPA + KEDA**: Combine all three for workloads that are both resource-intensive and event-driven, ensuring cost efficiency and performance.

[^169]: What You Assume
    Where you
    End up
    Right
    Size
    techopsexamples . com
    . . .... .. . .

[^170]: KUBERNETES DEPLOYMENT STRATEGIES
    Recreate
    Rolling Update
    Discard
    V1
    V1
    K
    LB
    Downtime: Yes
    V2
    Downtime: No
    V2
    Shadow
    Canary
    75%
    V1
    V1
    K
    LB
    LB
    25%
    Downtime: No
    V2
    Downtime: No
    V2
    Blue Green
    A/B Testing
    100%
    V1
    V1
    LB
    0%
    LB
    Downtime: No
    techopsexamples . com
    V2
    Downtime: Not Applicable
    V2

[^171]: KUBERNETES POD TROUBLESHOOTING TACTICS
    techopsexamples . com
    Verify Pod
    Check logs
    Configuration
    HOW
    Validate
    O
    Analyze Pod
    EFFECTIVE
    Container Images
    Status
    IT IS
    O Restart Pod
    O Describe Pod
    Review Service
    O Check Events
    Dependencies
    Check Network
    Connectivity
    O
    Inspect
    Resource Usage
    HOW OFTEN I DO IT

[^172]: 
    ```
    kubectl exec -it <pod_name> -- sh
    ```

[^173]: 
    ```
    ping <target_host>
    ```

[^174]: 
    ```
    curl <target_url>
    ```

[^175]: KUBERNETES pod.yaml STRUCTURE BREAKDOWN
    TECHOPSEXAMPLES.COM
    apiVersion: v1
    kind: Pod
    Resource type (Pod in this case)
    metadata:
    name: techops-pod
    Unique name for the Pod
    labels :
    To organize and select Pods
    app: techops
    App label, useful for selectors
    tier: backend
    To identify the application layer
    spec :
    containers :
    Container (s) running in this Pod
    name: techops-container
    Name of the container
    image: nginx : 1.23
    > Docker image for the container
    ports :
    - containerPort: 80
    Port the container exposes internally
    env :
    Environment variables for configuration
    name : ENV
    value: production
    volumeMounts :
    Volumes mounted inside the container
    name: config-volume
    > Volume defined in the "volumes" section
    mountPath: /usr/share/nginx/html
    > Mount point inside the container
    volumes :
    - name: config-volume
    Name of the volume
    configMap :
    Use ConfigMap as the source
    name: techops-config
    Reference the ConfigMap named
    "techops-config"
    restartPolicy: Always
    Pod restart policy ( Always, On Failure ,
    or Never)
    nodeSelector:
    Schedule pod on specific nodes
    disktype: ssd
    Schedule only on nodes labeled with
    " disktype = ssd "
    tolerations :
    Allows scheduling on tainted nodes
    - key: "special-taint"-
    Taint key to tolerate
    operator: "Equal"
    > (exact match) or Exists
    value: "true"
    Value to match
    effect: "NoExecute"
    Effect: NoSchedule (can't schedule),
    NoExecute (evict)
    securityContext :
    Pod-level security settings
    runAsUser: 1000
    Run containers as this user ID
    runAsGroup : 3000
    >Run containers with this group ID
    fsGroup : 2000
    > Group ownership for mounted volumes
    initContainers :
    Runs before the main containers
    name: init-techops
    > Init container name
    image: busybox
    > Image for the init container
    command: \["sh", "-c", "echo Init; sleep 5"\]
    -> Setup commands

[^176]: KUBERNETES COMMON ERRORS
    SIMPLIFIED EXPLANATION
    techopsexamples.com
    1. CRASHLOOPBACKOFF
    Pod restarts repeatedly because the
    container keeps failing.
    2. IMAGEPULLBACKOFF
    Pod cannot start because Kubernetes
    cannot pull the container image.
    X X
    3. OOMKILLED
    Container is killed because it used
    more memory than allowed.
    4. NODENOTREADY
    Pods cannot run because the node is
    unhealthy or disconnected.
    5. CONTAINERCREATING
    Pod is stuck because storage or
    network dependencies are not ready.
    6. EVICTEDPODS
    Pods are terminated to free resources
    when the node runs out of memory.

[^177]: Docker Images and Layers
    How the "IMAGE"
    Image
    -- appears.. when viewing
    acantril/somegame
    all layers
    4-
    Layer "573b4329b3b1"
    contains application
    Each layer
    contains only
    the differences
    -- layer "812de68fe4d8"
    from the layer
    contains env/libs
    below
    +-- layer "ab5ef0e58194"
    contains base linux
    Layers can be reused
    When running docker pull
    and they help avoid
    each layer is independent,
    unnecessary uploads
    A docker image is a collection of
    pulled only if it doesn't
    and downloads
    the file system layers
    already exist locally.
    Creating Docker Images & Dockerfile
    Registry (HUB)
    Docker Host
    Local Docker Image
    Local Docker Container
    E
    pull
    run
    Remote
    Docker Image
    build
    FROM alpine:latest
    So far you've
    LABEL
    maintainer="adrian@cantrill.io"
    used docker pull
    RUN apk --update add nginx
    to download a
    COPY 2048
    /usr/share/nginx/html
    remote image
    EXPOSE 80
    We're
    CMD \["nginx, "-9", "daemon
    off:"\]
    learning
    Dockerfile
    this

[^178]: docker architecture
    docker run nginx
    1. docker shell/ docker command send a request to docker deamon
    2. docker engine receives the request
    3. it will check whether image is available in local or not
    4. if available it will create container and show the response in client
    5. if not available, it will pul from docker central hub, keep it in local.
    6. create container and response to client

[^179]: Example of a Simple Dockerfile:
    dockerfile
    Copy code
    # Use an official Node.js runtime as a parent image
    FROM node : 14
    # Set the working directory inside the container
    WORKDIR /usr/src/app
    # Copy the local files to the working directory in the container
    COPY .
    # Install dependencies
    RUN npm install
    # Make port 3000 available to the

[^180]: dockerfiles > CMD >
    Dockerfile
    1
    FROM almalinux : 8
    2
    RUN yum install nginx -y
    3
    CMD
    \["nginx", "-g", "daemon off;"\]

[^181]: Example
    Dockerfile
    Copy code
    FROM ubuntu : 20 . 04
    ENTRYPOINT \["echo" \]
    CMD \["Hello, World!"\]
    .
    Running this image without arguments will execute \* echo Hello, World!".
    You can override the \* CMD part by passing arguments to \* docker run, like docker run my-
    image Goodbye!' , which will execute \* echo Goodbye!" .

[^182]: Example
    Dockerfile
    Copy code
    FROM ubuntu : 20. 04
    ENV APP_HOME=/usr/src/app
    ENV DEBUG=true
    WORKDIR $APP_HOME
    COPY . $APP_HOME
    CMD \["python", "app.py" \]
    In this example:
    \`APP_HOME=/usr/src/app" sets an environment variable \* APP_HOME" to \* /usr/src/app .
    \`DEBUG=true" sets the \*DEBUG" environment variable to \*true".
    .
    The \*WORKDIR command uses the \* APP_HOME variable to set the working directory to
    /usr/src/app .

[^183]: FROM almalinux : 8
    2
    ARG username
    3
    RUN adduser $username
    4
    USER $username
    5
    CMD \["sleep", "100"\]

[^184]: docker build -t arg: v1 --build-arg username=satya
    34 . 229. 144.33 \| 172. 31.22.2 \| t2.micro \| https: / /github. com/daws-76s/dockerfiles . git
    \[ centos@ip-172-31-22-2 \~/dockerfiles/ARG \]$ docker build -t arg:v1 --build-arg username=sivakumar
    \[+\] Building 0.1s (5/5) FINISHED
    docker : default
    EX
    \[internal\] load build definition from Dockerfile
    0 .03
    =>
    => transferring dockerfile: 1098
    0 . 0s
    =>
    \[internal\] load metadata for docker . io/library/almalinux: 8
    0. 1=
    =>
    \[internal\] load . dockerignore
    0 . 0s
    =>
    => transferring context: 2B
    0 .0=
    =>
    CACHED \[1/1) FROM docker . io/library/almalinux: 80sha256: 286bebaacc46c498394238b7a276991921829f
    0. 0s
    => exporting to image
    0. 03
    0.
    Os

[^185]: Syntax
    Dockerfile
    Copy code
    WORKDIR /path/to/directory
    Example
    Here's an example Dockerfile using \* WORKDIR" :
    Dockerfile
    Copy code
    FROM ubuntu : 20. 04
    WORKDIR /usr/src/app
    COPY
    RUN make /usr/src/app
    CMD \[" . /app"\]

[^186]: Dockerfile
    Copy code
    WORKDIR /usr/src/app
    COPY
    WORKDIR /usr/src/app/config
    COPY config/ .
    RUN . /setup . sh
    In this case, the first \* WORKDIR" sets the context for the \* copy . .' instruction, and the second
    "WORKDIR" changes the context to \* /usr/src/app/config" for the subsequent \* copy and RUN
    commands.

[^187]: V
    REPOS
    dockerfiles > onbulid > <dockerfile > ..
    > Ansible
    1
    FROM almalinux : 8
    > Concepts
    12
    RUN yum install nginx -y
    3
    dockerfiles
    RUN rm -rf /usr/share/nginx/html/index. html
    4
    ONBUILD ADD index. html /usr/share/nginx/html/
    > add
    15
    CMD \["nginx", "-g", "daemon off; " \]
    v arg
    dockerfile
    > CMD
    > copy
    > entrypoint
    > env
    > expose
    > from
    > label
    onbulid \~
    > test
    dockerfile

[^188]: REPOS
    dockerfiles > onbulid > test > < dockerfile > ...
    > Ansible
    - 1
    FROM on : v1
    > Concepts
    dockerfiles
    > add
    v arg
    dockerfile
    > CMD
    > copy
    > entrypoint
    > env
    > expose
    > from
    > label
    onbulid
    test -
    dockerfile
    <> index.html

[^189]: 3. 90. 236.230 \| 172. 31 . 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/onbulid \]$ docker build -t on:v1 .
    \[+\] Building 0.2s (8/8) FINISHED

[^190]: 3. 90. 236.230 \| 172. 31. 44.186 \| t2.micro \| https: //github.com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/onbulid/test \]$ docker build -t on-test:v1
    \[+\] Building 0.2s (7/7) FINISHED

[^191]: 3. 90. 236.230 \| 172. 31 . 44. 186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    centosdip-172-31-44-186 \~/dockerfiles/onbulid/test_\]$ docker run -d -p 8083:80 on-test:v1
    13232fb1 7da02cae8e6cdb27ccba2e276d1462bc140275ae3af448f7ff641943
    3. 90. 236.230 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/onbulid/test \]$ docker images
    REPOSITORY
    TAG
    IMAGE ID
    CREATED
    SIZE
    on-test
    v1
    788bccc637a0
    21 seconds ago
    305MB
    on
    v1
    56784a86130c
    2 hours ago
    305MB
    3. 90. 236.230 \| 172. 31. 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    centos@ip-172-31-44-186 \~/dockerfiles/onbulid/test \]$ docker ps
    CONTAINER ID
    IMAGE
    COMMAND
    CREATED
    STATUS
    PORTS
    NAMES
    13232fb17da0
    on-test : v1
    "nginx -g 'daemon of..."
    13 seconds ago
    Up 13 seconds
    0. 0. 0. 0:8083->80/tcp, : : :8083->80/tcp
    adoring_noether

[^192]: . Dockerfile: Used to create and build Docker images.
    . Docker Compose: Used to run Docker containers as part of a multi-
    container setup or with specific runtime configs.
    Dockerfile
    techopsexamples . com
    Build
    -Run-
    DockerFile
    Docker Image
    Docker Container
    S
    Docker Compose
    Docker Image
    Docker Container
    docker
    TITIT
    Compose
    Docker Image
    Docker Container
    compose.yml
    DockerFile
    Docker Image
    Docker Container

[^193]: 
    - **Orchestration:** Manages container communication, data sharing, and networking.

    - **Multi-Container Support:** Simplifies managing multiple services.

    - **Declarative Configuration:** Uses YAML for easy service setup.

    - **Resource Limiting:** Sets memory and CPU limits for services.

    - **Network Management:** Handles service networking automatically.

    - **Volume Management:** Manages shared or persistent data.

[^194]: Source code --> compile --> byte code (jar) --> run byte code
    JDK --> Java development kit
    JRE --> Java runtime environment
    JDK > JRE and JRE is subset of JDK
    JDK memory > JRE memory
    I

[^195]: REPOS
    roboshop-docker > shipping > Dockerfile > FROM
    #
    > learn-jenkins
    2
    # Build
    > notes
    13
    #
    > roboshop-ansible
    4
    FROM maven AS build
    > roboshop-ansible-roles
    5
    > roboshop-ansible-roles-tf
    16
    WORKDIR /opt/shipping
    roboshop-docker
    7
    8
    COPY pom. xml /opt/shipping/
    > cart
    19
    RUN mvn dependency : resolve
    > catalogue
    10
    COPY sec /opt/shipping/src/
    > mongodb
    11
    RUN mvn package
    > mysql
    12
    > payment
    13
    #
    shipping
    14
    # Run
    15
    #
    >
    src
    16
    FROM openjak:8-jdk
    Dockerfile
    17
    pom.xml
    18
    EXPOSE 8080
    > user
    19
    > web
    20
    WORKDIR /opt/shipping
    docker-compose.yaml
    21
    > roboshop-documentation
    22
    ENV CART_ENDPOINT=cart : 8080
    23
    ENV DB_HOST=mysql
    rohnchon-infra-dow
    24

[^196]: For example:
    Dockerfile
    Copy code
    FROM ubuntu : 20.04
    # Base layer
    RUN apt-get update
    # New layer
    RUN apt-get install -y python3 # Another new layer
    COPY . /app
    # Another new layer

[^197]: 1. base image
    creates container out of first instruction, intermediate container
    2. runs second instruction in the container, creates image out of this
    3. creates container out of 2 instructions.
    4. runs the command in the intermediate container. creates image out of these 3
    FROM node : 18. 19. 1-alpine3.19 --> creates container-1 here
    runs EXPOSE 8080 in container-1 --> creates image-1 out of this container-1
    create container-2 out of image-1
    runs this command addgroup -S roboshop & & adduser -S roboshop -G roboshop in container-2 -->
    creates image-2 out of this conatiner-2
    creates container-3 out of this image-2
    RUNS

[^198]: 1. we have a docker host where all containers are running
    what if docker host crash? we lose all containers
    even we use docker volumes, data is still in the host, so we lost data as well
    2. what if traffic increases/decreases? are our containers scalable
    3. even we have multiple containers to balance the load? who is the LB here?
    4. what if some container crashes? can docker make it available again?
    5. what about configurations and secrets? where to store them?
    6. what if we have multiple hosts running with containers
    I

[^199]: Git Workflow
    DEEP
    LEARNING
    NERDS
    LOCAL
    REMOTE
    WORKING
    STAGING
    LOCAL
    REMOTE
    DIRECTORY
    AREA
    REPO
    REPO
    git add
    git commit
    git push
    git fetch
    git checkout
    git pull

[^200]: Typical Merge
    Before Merge
    After Merge

[^201]: Git Merge & Rebase
    @logicmojo
    GIT
    main
    Original
    branch
    C
    D
    feature
    branch
    E
    G
    After "git merge"
    main
    branch
    B
    D
    G'
    git merge
    feature
    G
    branch
    main
    After "git rebase"
    branch
    B
    D
    E'
    G'
    git rebase
    G

[^202]: Fast Forward Merge
    Before Merge
    After Merge

[^203]: 243
    CO
    change
    Code Base
    Rebase
    A
    Code Base
    Rebase
    Code Base
    Merge Merge Conflict
    Branch
    Merge
    m
    Code Base
    Branch-
    -Merge

[^204]: hcl
    Copy code
    variable "instance_type" {
    default = "t2.micro"

[^205]: groovy
    Copy code
    pipeline {
    agent any
    stages {
    stage( ' Build' ) {
    steps {
    echo 'Building...'
    stage( ' Test' ) {
    when {
    branch 'master'
    steps {
    echo 'Running tests on master branch...'
    LP

