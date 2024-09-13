---
title: Interview & Concepts
uuid: 0729dc16-5479-11ef-a2e2-0663d8339c46
version: 3608
created: '2024-08-07T10:23:45+05:30'
tags:
  - interview
---

\

# <mark style="background-color:#F8914D;">**Kubernetes**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![88d372c0-b6a9-4552-b6c6-3fb5bb051292.png|667](https://images.amplenote.com/602cceb4-48a2-11ef-bf57-26e37c279344/88d372c0-b6a9-4552-b6c6-3fb5bb051292.png) [^1]

### **1Q. What is Kubernetes and Architecture?**<!-- {"collapsed":true} -->

**Good site for Kubernetes architecture** --> [Kubernetes - Architecture - GeeksforGeeks][^2] 

\

Kubernetes is popular container orchestration tool.  It is responsible to run and manage the containers.

Kubernetes helps to manage & automate the deployment, scaling and management of containerized applications.

It consists of several components that work together to provide a robust and scalable solution for running and managing containerized workloads.

![853f71a6-9f7f-4d98-aed0-bac93b5cd734.png|797](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/853f71a6-9f7f-4d98-aed0-bac93b5cd734.png) [^3]

\

**Control plane components (master Node):**

1. **kube-apiserver:** This is the primary component and frontend for the Kubernetes API, which is used by other components and external tools to interact with cluster.

1. **etcd:** etcd is a distributed, consistent key-value store used by Kubernetes to storage all cluster data, including configuration, state and metadata.

1. **kube-scheduler:** The scheduler is responsible for scheduling and assigning pods (a group of one or more containers) to specific nodes in the cluster based on resource requirements and constraints.

1. **kube-controller-manager:** This component runs various controllers that regulate the state of the cluster and perform tasks such as replicating PODS, managing node lifecycle and managing endpoint objects.

1. **Cloud-controller-manager:** It is responsible for interacting with underlying cloud provider and managing resources specific to that cloud platform.

**Node Components:**

1. **kubelet:** This is primary node agent that runs on each node in the cluster. It is responsible for managing pods, monitoring their health, and reporting back to control plane.

1. **kube-proxy:** This component acts as a network proxy and load balancer, facilitating communication between pods and forwarding traffic to the appropriate services.

1. **Container Runtime:** Kubernetes supports various container runtimes, such as Docker, Containerd, or CRI-O. These runtimes are responsible for pulling and running container images.

![c5aff5bd-4310-4b18-90a6-ab651d685467.jpg|819.9884643554688](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/c5aff5bd-4310-4b18-90a6-ab651d685467.jpg) [^4]

![1811efad-61af-4c34-b290-c7ec0a8e32c4.jpg|939.9884643554688](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/1811efad-61af-4c34-b290-c7ec0a8e32c4.jpg) [^5]

![1811efad-61af-4c34-b290-c7ec0a8e32c4.jpg|939.9884643554688](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/1811efad-61af-4c34-b290-c7ec0a8e32c4.jpg) [^6]

\

**Cluster:** collection of machines

**Master Node:** Manages and coordinates the cluster.

**Worker Nodes:** Run the application.

**PODS:** Groups of containers.

**Services:** Network access for pods.

**Volumes:** Persistent data storage.

**ConfigMaps/Secrets:** Manage configuration and sensitive data.

\

- Kubernetes run across a cluster node.

- Using Kubernetes different nodes can communicate with each other.

- Kubernetes is an open-source platform also, this is widely used in industries.

- Kubernetes takes care of scaling and failover for your application running on the container.

\

![8aa8d1a2-d1f6-4a69-a069-c92f08d2e213.jpg|871.9791870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/8aa8d1a2-d1f6-4a69-a069-c92f08d2e213.jpg) [^7]

![3dfbf686-ae5b-43f2-ac8a-a906f7073d9a.png|336](https://images.amplenote.com/11aa18c0-400d-11ef-b01a-26e37c279344/3dfbf686-ae5b-43f2-ac8a-a906f7073d9a.png) [^8]

\

### **2Q. What are Kubernetes Pods?**<!-- {"collapsed":true} -->

- It a smallest deployable unit in Kubernetes (POD same as container). It wraps one or more applications in a container. 

- PODS are temporary - If one fails, Kubernetes auto-creates a new one to keep things running smoothly.

- PODS are the workers in your kubernetes cluster.

    - Have a unique IP address for easy communication.

    - Use storage volumes as needed.

    - Carry configuration info for container operations.

    - Most pods have one container, but some team up a few to get the jobs done.

    - ![11eae365-e37e-4a4d-b439-599e393dc26b.png|665.0000610351562](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/11eae365-e37e-4a4d-b439-599e393dc26b.png) [^9]

**Benefits:**

- Multiple containers in a pod communicate easily via localhost.

- Simplify data sharing.

- Start containers for tasks before the main application runs.

- Scale automatically based on demand.

- Pods make scaling and communication a breeze.

![00d911e8-1633-4dbd-a782-8f4e643a7982.png|373](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/00d911e8-1633-4dbd-a782-8f4e643a7982.png) [^10]

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

![af91c856-7e69-461e-bf61-bb5884e2c088.png|797.9977416992188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/af91c856-7e69-461e-bf61-bb5884e2c088.png) [^11]

\

2\. **kubectl**

- **Purpose**: `kubectl` is the standard command-line tool used to interact with Kubernetes clusters, regardless of where they are hosted (AWS, Google Cloud, on-premises, etc.). It allows you to control and manage Kubernetes resources.

- **Usage**:

    - **Resource Management**: `kubectl` is used to manage Kubernetes resources like pods, deployments, services, and more. It operates at the level of Kubernetes objects and configurations.

    - **Cluster Interaction**: Once your Kubernetes cluster is up and running (regardless of how it was created), `kubectl` is used to interact with it by applying configurations, inspecting resources, and troubleshooting.

![7ea83e25-a5de-443d-a6b4-d5a9d2a19390.png|803.9931030273438](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/7ea83e25-a5de-443d-a6b4-d5a9d2a19390.png) [^12]

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

Every resource is YAML... a basic syntax is

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

![8f19e3a9-1d8c-49f8-8501-51ae36bfbe37.png|864](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8f19e3a9-1d8c-49f8-8501-51ae36bfbe37.png) [^13]

### **5Q. Can multiple containers run in a POD?**<!-- {"collapsed":true} -->

![8db0ae92-3b52-4882-bdd6-7fa16398847c.png|554](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8db0ae92-3b52-4882-bdd6-7fa16398847c.png) [^14]

Multiple containers in a Pod are used when there's a need for close coordination, shared resources, or sidecar functionalities that complement the main application running in the Pod.

\

In Kubernetes, a **Pod** is the smallest deployable unit and can contain one or more containers. There are several reasons why you might have multiple containers in a single Pod:

1. **Tight Coupling**: When containers need to work closely together, they are often placed in the same Pod. For example, you might have one container serving an application and another container logging data for that application. They share the same network namespace and can easily communicate via `localhost`.

1. **Shared Resources**: Containers within the same Pod share the same storage volumes and can access the same files. This is useful if you have multiple containers that need to access the same data, such as a web server and a file processing service.

1. **Sidecar Pattern**: A common use case for multiple containers in a Pod is the sidecar pattern, where one container adds functionality to the main container. For example, you might have a sidecar container handling log collection, monitoring, or injecting security configurations.

1. **Ambassador Pattern**: This pattern involves one container acting as a proxy or ambassador to the outside world for another container. This can be useful for services that need to interact with legacy systems or external APIs.

1. **Adapter Pattern**: Sometimes, a container is used to modify or adapt the output of another container before it is consumed by the main application. For instance, a container could transform data from one format to another, making it easier for the main application to consume.

1. **Shared Namespace**: Containers in the same Pod share the same network namespace, meaning they can communicate with each other using `localhost`. This is useful for closely related processes that need to be aware of each other's presence without exposing services to the external network.

6Q. <mark>**Annotations in Kubernetes?**</mark>

![8197b075-444c-4d0c-a358-29b7cb86f750.png|856](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/8197b075-444c-4d0c-a358-29b7cb86f750.png) [^15]

\

```
kubectl describe pod <POD Name>
```

![0f4aef69-4086-41be-87ee-0f413469a86e.png|1156.2037353515625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/0f4aef69-4086-41be-87ee-0f413469a86e.png) [^16]

\

![ad124751-b492-450e-a05f-080c98c18d69.png|550.9838256835938](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/ad124751-b492-450e-a05f-080c98c18d69.png) [^17]

### **6Q. How resources used in Kubernetes?**<!-- {"collapsed":true} -->

![a05fdef4-be06-486f-8b4f-2afe0a0b6062.png|1034](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/a05fdef4-be06-486f-8b4f-2afe0a0b6062.png) [^18]

\

Restrict POD resources:

![0d3593ab-d9a4-46f7-b0ad-e0a1dc0c1843.png|483](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/0d3593ab-d9a4-46f7-b0ad-e0a1dc0c1843.png) [^19]

\

### **7Q. What are ConfigMap in Kubernetes?** Its nothing but a key value pair(to store environment parameters)<!-- {"collapsed":true} -->

A **ConfigMap** in Kubernetes is an API object used to store non-confidential data in key-value pairs. It allows you to decouple configuration artifacts from image content to keep containerized applications portable. You can use a ConfigMap to store configuration files, command-line arguments, environment variables, or any other configuration data your application needs.

\

Here’s a brief overview:

- **Storage**: Holds non-sensitive configuration data as key-value pairs.

- **Usage**: Can be used in Pods as environment variables, command-line arguments, or mounted as files in a volume.

- **Purpose**: Decouples configuration from application code, making it easier to manage and update without changing the container images.

ConfigMaps are especially useful when you need to configure applications in different environments (e.g., development, staging, production) without altering the application itself.

\

### **8Q. What are Secrets in Kubernetes?**<!-- {"collapsed":true} -->

A **Secret** in Kubernetes is an API object that stores sensitive data, such as passwords, OAuth tokens, SSH keys, and other credentials. Unlike ConfigMaps, Secrets are specifically designed to handle sensitive information and provide a secure way to manage such data in your cluster.

\

Here’s a brief overview:

- **Storage**: Stores sensitive information in base64-encoded format (though not encrypted by default).

- **Usage**: Can be used in Pods as environment variables, mounted as files in volumes, or accessed directly by the application.

- **Purpose**: Provides a secure method to manage and distribute sensitive information to applications without embedding it directly in the application code or container images.

Secrets help keep your application’s sensitive data secure, reducing the risk of exposing confidential information.

\

### **9Q. Kubernetes services?**<!-- {"collapsed":true} -->

![6655c8a3-7cbb-433e-95f8-0d4609aaed34.png|1028.9814453125](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/6655c8a3-7cbb-433e-95f8-0d4609aaed34.png) [^20]

\

Every POD should attach to services

![993ac4ce-c57c-4695-9aaf-786009b2e960.png|446](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/993ac4ce-c57c-4695-9aaf-786009b2e960.png) [^21]

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

### **10Q. What is ClusterIP service in Kubernetes?**<!-- {"collapsed":true} -->

A **ClusterIP** service in Kubernetes is the default type of service that provides internal access to your application within the Kubernetes cluster. It exposes the service on a stable internal IP address, which can only be accessed from within the cluster.

Here’s a brief overview:

- **Internal Access**: Only accessible within the Kubernetes cluster; not exposed to the external network.

- **Use Case**: Ideal for internal communication between microservices within the cluster, like databases or backend services that don’t need to be accessed directly by users.

- **IP Address**: Automatically assigned an IP address by Kubernetes that is used by other services or Pods within the cluster to reach the service.

ClusterIP services are essential for managing internal traffic within your Kubernetes environment, ensuring that services can communicate with each other securely and efficiently.

\

### **11Q. What is NodePort service in Kubernetes?**<!-- {"collapsed":true} -->

A **NodePort** service in Kubernetes exposes your service on each Node's IP address at a static port. This allows external access to your service from outside the Kubernetes cluster, making it possible to communicate with the service directly through the node's IP and the specified port.

Here’s a brief overview:

- **External Access**: Exposes the service on a specific port on each Node in the cluster, allowing external traffic to reach the service.

- **Port Range**: The port number is typically chosen from a range of 30000-32767, though you can specify a custom port within this range.

- **Access Method**: You can access the service using `<NodeIP>:<NodePort>`, where `NodeIP` is the IP address of any Node in the cluster, and `NodePort` is the port number allocated by Kubernetes.

NodePort services are useful when you need to expose a service to external users or applications without using a cloud provider’s load balancer. However, it’s more rudimentary compared to the `LoadBalancer` service, as it relies on the node’s IP and port for access.

\

<mark>**If we create NodePort then ClusterIP also by default it creates**</mark>

![c9ec92e8-247a-421c-af5f-4f884a0eb338.png|683](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c9ec92e8-247a-421c-af5f-4f884a0eb338.png) [^22]

\

### **12Q. What is Load Balancer service in Kubernetes?**<!-- {"collapsed":true} -->

A **LoadBalancer** service in Kubernetes automatically provisions an external load balancer to expose your service to the internet or an external network. This service type is primarily used in cloud environments where the cloud provider can allocate a load balancer to route traffic to the Kubernetes service.

Here’s a brief overview:

- **External Access**: Exposes the service to external clients, making it accessible from outside the Kubernetes cluster.

- **Automatic Provisioning**: When you create a LoadBalancer service, Kubernetes interacts with the cloud provider (e.g., AWS, GCP, Azure) to automatically create a load balancer and configure it to forward traffic to the Kubernetes service.

- **Load Distribution**: Distributes incoming traffic across the Pods associated with the service, ensuring even load distribution and improving fault tolerance.

- **Public IP**: The service is assigned a public IP address by the cloud provider, which external clients can use to access the service.

LoadBalancer services are ideal for applications that need to be exposed to the internet or external users, as they provide a managed and scalable way to handle incoming traffic.

\

![b8d067b3-7816-4c43-b83e-61a451529a80.png|378.9930419921875](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/b8d067b3-7816-4c43-b83e-61a451529a80.png) [^23]

![72b70446-4bb9-42af-a007-857cd40d670a.png|852](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/72b70446-4bb9-42af-a007-857cd40d670a.png) [^24]

\

\

### **13Q. Explain ReplicaSet in Kubernetes?**<!-- {"collapsed":true} -->

**ReplicaSet** in Kubernetes is a controller that ensures a specified number of identical Pods are running at any given time. It’s responsible for maintaining the desired number of replicas (copies) of a Pod, automatically scaling up or down to match the defined state.

Here’s a brief overview:

- **Purpose**: Ensures that a specified number of Pods are running, creating or deleting Pods as necessary to maintain the desired state.

- **Scaling**: Automatically adjusts the number of Pods if one or more Pods fail or are deleted, ensuring high availability.

- **Selector**: Uses a label selector to identify which Pods are part of the ReplicaSet, ensuring that only Pods with matching labels are managed.

- **Use Case**: Commonly used to maintain stateless applications, ensuring they have the necessary number of instances running.

While ReplicaSets can be used directly, they are most commonly managed by Deployments, which offer additional features like rolling updates and rollback capabilities.

\

<mark>ReplicaSet is not useful in changing the version of application. ReplicaSet is only used to maintain the replicas.</mark>

\

we can't control random ID

![e57ac976-0970-4ac0-ae8c-f5d22d5fce2a.png|412](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/e57ac976-0970-4ac0-ae8c-f5d22d5fce2a.png) [^25]

\

### **14Q. Explain Deployment in Kubernetes?**<!-- {"collapsed":true} -->

A **Deployment** in Kubernetes is a higher-level abstraction that manages a group of Pods and their ReplicaSets. It provides a declarative way to manage application updates, scaling, and rollbacks, making it easier to maintain the desired state of an application.

Here’s a brief overview:

- **Manages ReplicaSets**: A Deployment manages ReplicaSets, which in turn manage the Pods. When you create or update a Deployment, Kubernetes ensures the appropriate ReplicaSet is created or updated accordingly.

- **Rolling Updates**: Deployments support rolling updates, meaning they can gradually replace old Pods with new ones without downtime. This allows for seamless updates to your application.

- **Rollback**: If something goes wrong during an update, you can roll back to a previous version. Kubernetes keeps track of the history of Deployments, making it easy to revert to a stable state.

- **Scaling**: You can scale the number of Pods in a Deployment up or down with a simple command. This can be done manually or automatically using Horizontal Pod Autoscaling.

- **Self-Healing**: Deployments ensure that the specified number of Pods are always running. If a Pod fails, Kubernetes automatically creates a new one to replace it.

Deployments are essential for managing the lifecycle of applications in Kubernetes, providing robust features for deployment strategies, scaling, and maintaining high availability.

\

![c45efcdd-98a5-4307-8b6b-ab226a4c27c6.png|708](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/c45efcdd-98a5-4307-8b6b-ab226a4c27c6.png) [^26]

![5104dabe-68e5-47d2-bbc4-e927102cdb4b.png|510](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/5104dabe-68e5-47d2-bbc4-e927102cdb4b.png) [^27]

\

At any point of time 3 pods will run

![9a49d034-a26d-4bb3-9038-c58dd442b647.png|780](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/9a49d034-a26d-4bb3-9038-c58dd442b647.png) [^28]

\

DeploymentSet deletes old ReplicaSet & pods once new ReplicaSet & pods created <mark>**( This is also called ROLLING Update)**</mark>

![bfcca94f-4339-4c9b-9979-dfcf5686ac5b.png|899](https://images.amplenote.com/ab83b9de-3f3f-11ef-b6cc-26e37c279344/bfcca94f-4339-4c9b-9979-dfcf5686ac5b.png) [^29]

### **15Q. What is stateless & what is stateful in k8?**<!-- {"collapsed":true} -->

In Kubernetes (K8s), the terms **stateless** and **stateful** refer to how applications or services manage their data and how they handle scaling, failure recovery, and deployment.

\

![352acef9-ebe1-4283-8947-fbc5fc41d444.png|1025](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/352acef9-ebe1-4283-8947-fbc5fc41d444.png) [^30]

\

<mark>**mysql, redis, mongodb & RabbitMQ are stateful applications**</mark>

![2186b359-ba99-4e05-b8d4-f107e780930f.png|1081](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/2186b359-ba99-4e05-b8d4-f107e780930f.png) [^31]

\

**Stateless in Kubernetes**

- **Definition:** In Kubernetes, a stateless application does not retain any data or state between different requests or sessions. Each pod (a pod is the smallest deployable unit in Kubernetes) can be replaced, scaled up, or down without any concern for data persistence.

- **Usage:** Stateless applications are often used for web servers, API servers, or microservices that don't need to keep any session or state information.

- **Examples:**

    - **Deployment:** In K8s, you usually deploy stateless applications using a `Deployment`. This controller ensures that the specified number of pod replicas are running and can handle scaling and updates without data loss concerns.

- **Advantages:**

    - Easy to scale horizontally by adding more pods.

    - Simplified deployment and management.

    - High availability, as new pods can easily replace failed ones.

**Stateful in Kubernetes**

- **Definition:** Stateful applications, on the other hand, retain data or state between different requests or sessions. Each pod in a stateful application may have a unique identity, persistent storage, and possibly a specific order of deployment.

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

### <mark style="background-color:#FFFFFF;">**16Q. Storage - k8 Volumes?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

![0bc6b573-e304-4511-95c7-d19a09fb6c05.png|381](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/0bc6b573-e304-4511-95c7-d19a09fb6c05.png) [^32]

\

Data is getting stored in EC2 worker nodes...

**pods are ephemeral (temporary), nodes are also ephemeral.**

![edcb2482-d1d8-403f-a01c-e43cf54c20ac.png|319.9884033203125](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/edcb2482-d1d8-403f-a01c-e43cf54c20ac.png) [^33]

![9a1b0a0b-6209-4f87-9fac-8b10f347d28a.png|604](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/9a1b0a0b-6209-4f87-9fac-8b10f347d28a.png) [^34]

\

\

\

### **17Q. What is `emptyDir` in K8?**<!-- {"collapsed":true} -->

In Kubernetes, `emptyDir` is a type of volume that is created when a pod is assigned to a node and exists as long as that pod is running. It’s often used for temporary storage needs, where data doesn't need to persist after the pod is terminated.

**How `emptyDir` Works:**

- **Creation:** An `emptyDir` volume is created when a pod is scheduled onto a node. The directory inside the pod starts out empty.

- **Storage Location:** The data in an `emptyDir` volume is stored on the worker node's filesystem where the pod is running. The specific location of the data on the node depends on the container runtime being used (e.g., Docker, containerd).

- **Lifecycle:** The `emptyDir` volume is deleted when the pod is removed from the node, whether it's due to completion, failure, or manual termination.

**Use Cases:**

- **Scratch Space:** For temporary files generated during the execution of a pod, such as intermediate processing data.

- **Caching:** To store temporary cache data that doesn't need to persist beyond the pod's lifecycle.

- **Inter-process Communication:** If you have multiple containers in a pod that need to share data, an `emptyDir` volume can be mounted into each container for this purpose.

**Key Characteristics:**

- **Ephemeral:** The data in an `emptyDir` volume is lost if the pod is terminated or rescheduled to another node.

- **Performance:** Since `emptyDir` is stored on the node’s local storage, it can provide high-speed access to data, making it suitable for performance-sensitive temporary storage needs.

**Types of `emptyDir`:**

- **Memory-backed:** You can specify that the `emptyDir` should be stored in RAM by setting the `medium: "Memory"` field. This creates a `tmpfs` (in-memory filesystem) on the node, which can be faster but is limited by the available RAM.

![5ebaf4a8-0679-4ec9-9c17-8516a56bcc3a.png|731.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5ebaf4a8-0679-4ec9-9c17-8516a56bcc3a.png) [^35]

\

**Considerations:**

- **Non-Persistence:** If your application needs to retain data even if the pod is rescheduled, `emptyDir` is not the right choice. For persistent data, you would use persistent volumes (PVs).

- **Node Affinity:** Since the data is tied to the specific node where the pod is running, if the pod is moved to another node, the data in `emptyDir` is lost.

In summary, `emptyDir` is a useful volume type in Kubernetes for scenarios requiring temporary, non-persistent storage that is local to the node.

\

\

### **18Q. What is filebeat in K8?**<!-- {"collapsed":true} -->

**Filebeat** is a lightweight log shipper from the Elastic Stack (ELK Stack), used for forwarding and centralizing log data. When deployed in a Kubernetes (K8s) environment, Filebeat is commonly used to collect and ship logs from the various containers and pods running in the cluster to a central logging system, such as Elasticsearch or Logstash.

\

**How Filebeat Works in Kubernetes:**

In a Kubernetes environment, Filebeat is typically deployed as a **DaemonSet** to ensure that there is one instance of Filebeat running on each worker node in the cluster. This allows Filebeat to collect logs from all pods running on that node.

**Deployment Steps:**

1. **Deploy Filebeat as a DaemonSet:**

    1. Filebeat is deployed using a DaemonSet to ensure that it runs on every node in the Kubernetes cluster. This enables log collection from all pods across the cluster.

1. **Configuration:**<!-- {"offset":1} -->

- Filebeat can be configured using a ConfigMap in Kubernetes. The configuration specifies which log files to monitor and where to ship the logs (e.g., Elasticsearch, Logstash).

![24771776-6b11-4c59-805e-ee98edda90f3.png|770.9837646484375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/24771776-6b11-4c59-805e-ee98edda90f3.png) [^36]

**Inputs:** Defines the log paths to monitor, often targeting the Docker container logs stored on the host system.

**Processors:** Enhances the logs with metadata, such as pod names, namespaces, and node details, using the `add_kubernetes_metadata` processor.

**Output:** Specifies where to send the logs, such as an Elasticsearch cluster.

\

1. **Log Collection:**

    1. Filebeat reads log files from the mounted host paths (e.g., `/var/lib/docker/containers/\*/\*.log`) and forwards them to the configured output.

    1. The `add_kubernetes_metadata` processor enriches the logs with Kubernetes-specific metadata, making it easier to filter and search logs based on Kubernetes objects like pods, namespaces, and nodes.

1. **Monitoring and Scaling:**

    1. Because Filebeat is deployed as a DaemonSet, it automatically scales with your cluster. As new nodes are added, a new Filebeat instance is deployed to collect logs from that node.

    1. Logs can be monitored and visualized in tools like Kibana, which can be set up to work with Elasticsearch.

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

### **19Q. <mark style="background-color:#FFFFFF;">What is DeamonSet & Fluentd in k8?<!-- {"backgroundCycleColor":"11"} --></mark>**<!-- {"collapsed":true} -->

DeamonSet will make sure a POD runs in each and every worker node. If you delete one worker node a POD in it will delete and if we add new worker node to a cluster then DeamonSet will automatically creates POD. (when you create POD it will create 3 pods in 3 cluster nodes).

<mark style="background-color:#F8914D;">**DeamonSet**<!-- {"backgroundCycleColor":"24"} --></mark> <mark>**- It will make sure a pod runs in each and every node.**</mark> <mark style="background-color:#F8914D;">**Fluentd**<!-- {"backgroundCycleColor":"24"} --></mark> <mark>**will be deployed as DeamonSet that can access the underlying host logs and send them to ELK.**</mark>

\

### **20Q. External volumes in K8?**<!-- {"collapsed":true} -->

In Kubernetes, external volumes are used to persist data for applications running in Pods beyond the lifecycle of the Pod itself. This is crucial because Pods are ephemeral, meaning that when a Pod is terminated, any data stored inside it is lost. External volumes help ensure that important data is preserved and accessible across Pod restarts, rescheduling, or even across different nodes in the cluster.

\

<mark>**Persistent volume - It represents the external storage**</mark>

<mark>**Persistent volume claim - pods should request volumes through PVC**</mark>

\

pod - pvc - pv - ebs

![b9bda56c-f4ec-4ce1-a7d6-8ceefd61c43e.png|448.9930419921875](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b9bda56c-f4ec-4ce1-a7d6-8ceefd61c43e.png) [^37]

**Types of External Volumes in Kubernetes:**

1. **PersistentVolume (PV) and PersistentVolumeClaim (PVC)**:

    1. **PersistentVolume (PV)**: This is a storage resource in the cluster that has been provisioned by an administrator or dynamically provisioned using a StorageClass. PVs are a cluster-level resource.

    1. **PersistentVolumeClaim (PVC)**: This is a request for storage by a user. It is a claim to a PV. Pods can use PVCs as a volume source to store data externally.

1. **NFS (Network File System)**:

    1. NFS can be used as a Kubernetes volume to provide shared storage across multiple Pods. It is an external storage that is mounted into the Pod.

1. **Cloud Provider Volumes**:

    1. Cloud providers like AWS, Google Cloud, and Azure offer storage services that can be integrated with Kubernetes. Examples include:

        1. **AWS EBS (Elastic Block Store)**

        1. **Google Persistent Disk (GPD)**

        1. **Azure Disk**

1. **CSI (Container Storage Interface)**:

    1. CSI is an interface that allows Kubernetes to access storage systems from different vendors. It standardizes how storage providers expose their storage systems to Kubernetes.

1. **ConfigMap and Secret**:

    1. These are special types of volumes used to inject configuration data and sensitive information (like passwords, keys) into Pods.

![cb75eced-2676-47c5-84fc-b0fc10a2a006.png|780.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/cb75eced-2676-47c5-84fc-b0fc10a2a006.png) [^38]

![29084767-fe1a-4941-9f39-45bda4602f70.png|779.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/29084767-fe1a-4941-9f39-45bda4602f70.png) [^39]

![29084767-fe1a-4941-9f39-45bda4602f70.png|779.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/29084767-fe1a-4941-9f39-45bda4602f70.png) [^40]

\

**Key Points:**

- **Retention Policies**: PVs have a `persistentVolumeReclaimPolicy` which determines what happens to the PV after its PVC is deleted (e.g., Retain, Delete, or Recycle).

- **Access Modes**: These define how the volume can be mounted (e.g., ReadWriteOnce, ReadOnlyMany, ReadWriteMany).

- **Dynamic Provisioning**: You can configure dynamic provisioning using StorageClass, where PVCs automatically trigger the creation of a new PV.

External volumes in Kubernetes are critical for stateful applications that require data persistence, and they integrate well with various storage systems, both on-premises and in the cloud.

\

\

### **21Q. Static provisioning vs dynamic provisioning in k8?**<!-- {"collapsed":true} -->

In Kubernetes, **static provisioning** and **dynamic provisioning** are two approaches to managing Persistent Volumes (PVs) for persistent storage in a cluster. They differ primarily in how the storage resources are allocated and bound to Persistent Volume Claims (PVCs).

\

<mark style="background-color:#F3DE6C;">**Static Provisioning:**<!-- {"backgroundCycleColor":"14"} --></mark>

**Static provisioning** is a manual process where an administrator creates Persistent Volumes (PVs) ahead of time. These PVs are available for users to claim through Persistent Volume Claims (PVCs).

![c5694c35-f557-46a8-b8a6-9dcbe71558b0.png|405](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/c5694c35-f557-46a8-b8a6-9dcbe71558b0.png) [^41]

**How It Works:**

1. **Administrator creates PVs**: The cluster administrator manually defines and creates PVs, specifying the storage details such as capacity, access modes, and storage backend (e.g., NFS, AWS EBS, etc.).

1. **User creates PVC**: A user creates a PVC, specifying the required storage size and access mode. The Kubernetes control plane matches this PVC with a pre-existing PV that meets the requirements.

1. **Binding**: Kubernetes binds the PVC to the appropriate PV based on the request. If no matching PV is available, the PVC remains unbound until a suitable PV is created.

**Pros:**

- **Control**: Administrators have full control over the exact specifications of the storage being provided.

- **Predictability**: Since PVs are pre-provisioned, there is a clear understanding of what storage resources are available.

**Cons:**

- **Manual management**: Requires manual intervention to create and manage PVs, which can be cumbersome in large or dynamic environments.

- **Inefficiency**: Potential for unused PVs if they are not claimed by any PVCs, leading to wasted resources.

\

<mark style="background-color:#F3DE6C;">**Dynamic Provisioning**<!-- {"backgroundCycleColor":"14"} --></mark>

**Dynamic provisioning** automates the creation of Persistent Volumes (PVs) when a Persistent Volume Claim (PVC) is made. This approach uses StorageClasses to define the parameters for provisioning storage dynamically.

![b57faf5c-78d2-4863-aa04-809723be00a2.png|453.9814758300781](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/b57faf5c-78d2-4863-aa04-809723be00a2.png) [^42]

**How It Works:**

1. **Administrator defines a StorageClass**: The cluster administrator defines StorageClasses that describe different types of storage with specific parameters (e.g., performance characteristics, storage backend).

1. **User creates PVC with StorageClass**: A user creates a PVC and specifies a StorageClass. Kubernetes uses the StorageClass to dynamically provision a PV that meets the claim's requirements.

1. **Dynamic Provisioning**: Kubernetes automatically provisions a new PV based on the StorageClass parameters and binds it to the PVC. The user does not need to worry about the details of the underlying storage.

**Pros:**

- **Automation**: Simplifies storage management by automating the provisioning of PVs.

- **Scalability**: Ideal for dynamic environments where the demand for storage can change rapidly.

- **Flexibility**: Users can easily request storage without needing to know the details of the storage infrastructure.

**Cons:**

- **Less control**: Administrators have less direct control over the specific details of each PV that is created.

- **Dependence on StorageClasses**: Requires properly defined StorageClasses for different storage needs, which may add complexity.

![542257d8-ea59-40bf-a065-02d8402ec911.png|1126](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/542257d8-ea59-40bf-a065-02d8402ec911.png) [^43]

\

Dynamic

![29bf1d20-8f28-484b-9dd4-8c1f632be0f2.png|1038](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/29bf1d20-8f28-484b-9dd4-8c1f632be0f2.png) [^44]

\

Below 2 steps are common for both static & dynamic provisioning

![5fe0548f-aec0-4623-92fb-b392ef1cab72.png|1029](https://images.amplenote.com/b2c8c290-432a-11ef-b895-26e37c279344/5fe0548f-aec0-4623-92fb-b392ef1cab72.png) [^45]

\

### **22Q. What is helm charts and how its useful in kubernetes?**<!-- {"collapsed":true} -->

What HELM do is keeping all the constant values separate and values which are going to change will maintain separately.

![ea2bb69a-0e63-4a35-a288-11d3873196e0.png|512.9976806640625](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/ea2bb69a-0e63-4a35-a288-11d3873196e0.png) [^46]

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

![01499fc4-e090-4f0a-9126-139825c15920.png|970.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/01499fc4-e090-4f0a-9126-139825c15920.png) [^47]

\

\

### **23Q. Explain StatefulSet in Kubernetes?**<!-- {"collapsed":true} -->

A **StatefulSet** in Kubernetes is used to manage stateful applications. Unlike Deployments (which are used for stateless apps), StatefulSets ensure that each pod has a unique, stable identity and persistent storage.

\

**Key Features:**

1. **Stable Network ID**: Each pod gets a stable DNS name (like `pod-0`, `pod-1`), which doesn’t change when the pod is restarted.

1. **Persistent Storage**: Each pod gets its own persistent volume, which stays the same even if the pod is deleted or recreated.

1. **Ordered Scaling**: Pods are created and terminated in an ordered, sequential manner.

**Example:**

Here’s a basic example of a StatefulSet managing a simple app:

![84a797e8-4eda-4a07-a32b-bea1579b13cb.png|834.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/84a797e8-4eda-4a07-a32b-bea1579b13cb.png) [^48]

**StatefulSet** creates 3 pods, each with a unique identity (like `web-0`, `web-1`, `web-2`).

Each pod gets its own persistent storage (`1Gi` each) using a `volumeClaimTemplate`.

\

**Now each POD will have each volume in  StatefulSet**

In StatefulSet PV & volumes wont delete( so that we can use the data present in the volumes for new pods)

### **24Q. Headless service in Kubernetes?**<!-- {"collapsed":true} -->

<mark>**Headless service is used for stateful applications,**</mark> **when you pick headless service instead of single IP address you will get all PODS IP address in same cluster. So that it is easy for replica to communicate with other replicas.**

\

<mark>For normal deployment we have ClusterIP but for StatefulSet we don't have ClusterIP(None)</mark>

![a4a6502e-153a-4325-b955-58a94c1bf793.png|1004.9884033203125](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/a4a6502e-153a-4325-b955-58a94c1bf793.png) [^49]

\

it can communicate with background DB's

![917fc8a8-cd91-43b4-a995-f03dbc3409af.png|550](https://images.amplenote.com/5d3dae66-43fd-11ef-8f52-6ef34fa959ce/917fc8a8-cd91-43b4-a995-f03dbc3409af.png) [^50]

\

A **Headless Service** in Kubernetes is a service without a cluster IP. Instead of load-balancing requests across a set of pods, it allows direct communication with individual pod IPs. This is useful for stateful applications where you need to communicate with specific pods (like in a **StatefulSet**).

\

**Key Features:**

1. **No Load Balancing**: It doesn't distribute traffic across pods but returns the IP addresses of all the matching pods.

1. **Direct Pod Access**: Clients can connect to specific pods by their DNS names (e.g., `pod-0.my-service.namespace.svc.cluster.local`).

1. **DNS Resolution**: Each pod gets its own DNS entry, which helps in identifying and connecting to a specific pod.

**Example:**

A headless service looks like this:

![b64407a0-7b31-4b3d-9a26-219438efbd68.png|800.995361328125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b64407a0-7b31-4b3d-9a26-219438efbd68.png) [^51]

In this example:

- The service doesn’t have a `clusterIP`.

- It’s used to route traffic directly to pods by their individual DNS names rather than through a single service IP.

This is particularly useful for stateful apps where each pod has its own identity, such as databases or replicated services.

\

<mark>**Keeping DB's in kubernetes is not recommended,  (DB teams upgrades is difficult for DB's , end customer data(DB)we should not keep in kubernetes)**</mark>

<mark>**In any interview if they ask if your MYSQL & other DB are running in Kubernetes? tell them NO**</mark>

\

### **25Q. RBAC in Kubernetes?**<!-- {"collapsed":true} -->

**RBAC (Role-Based Access Control)** in Kubernetes is used to control who can perform specific actions on resources (like pods, services, etc.) within a cluster. It allows you to define **roles** and **permissions** for different users or applications.

\

**Key Concepts:**

1. **Role**: Defines a set of permissions (e.g., can create pods, can delete services).

1. **RoleBinding**: Assigns a role to a user or group, granting them the permissions defined in the role.

1. **ClusterRole**: Similar to Role but applies cluster-wide (not just in a specific namespace).

1. **ClusterRoleBinding**: Binds a ClusterRole to a user or group cluster-wide.

**Simple Example:**

Let’s say we want to give a user named `dev-user` permission to create pods in the `dev` namespace.

1\. **Role**: Define what actions are allowed.

![94798b8e-e33d-4a38-ab53-89d7a648d7b2.png|694.9884033203125](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/94798b8e-e33d-4a38-ab53-89d7a648d7b2.png) [^52]

\

**Explanation:**

- The **Role** `pod-creator` allows creating pods in the `dev` namespace.

- The **RoleBinding** ties this role to `dev-user`, giving them the ability to create pods in that namespace.

This helps control access in a fine-grained, secure manner within Kubernetes clusters.

\

![1e850338-a0f3-4bec-80d4-774363ee0d43.png|399](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/1e850338-a0f3-4bec-80d4-774363ee0d43.png) [^53]

![cf6c20fa-fca5-482a-b7c3-e20974863024.png|506](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/cf6c20fa-fca5-482a-b7c3-e20974863024.png) [^54]

\

for trainees

![e0694915-9639-46fe-9446-baf5eab6f59d.png|765.995361328125](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/e0694915-9639-46fe-9446-baf5eab6f59d.png) [^55]

\

![ddbed138-cd4e-4b1d-bf9e-f5a94b1f9078.png|302](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/ddbed138-cd4e-4b1d-bf9e-f5a94b1f9078.png) [^56]

\

Authentication - For TCS gate entry we have entry access

Authorization - We have ODC access to particular project, not for all ODC's

\

![17d36f9c-f911-43aa-9523-e9a34a3d22e5.png|862](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/17d36f9c-f911-43aa-9523-e9a34a3d22e5.png) [^57]

If we are using on-premise then we use Microsoft AD

cyberark

\

\

\

### **26Q. Horizontal POD Autoscaling (HPA) in Kubernetes?**<!-- {"collapsed":true} -->

![5c519f72-3c1d-4e9d-b21b-577e20a06022.png|1200](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/5c519f72-3c1d-4e9d-b21b-577e20a06022.png) [^58]

![07363199-4af8-4fb5-b44e-2400528d949d.png|731](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/07363199-4af8-4fb5-b44e-2400528d949d.png) [^59]

\

**Horizontal Pod Autoscaling (HPA)** in Kubernetes automatically adjusts the number of pod replicas in a deployment, replica set, or stateful set based on observed resource usage (like CPU or memory) or custom metrics. It ensures that your application scales up when demand increases and scales down when the load decreases.

\

**How HPA Works:**

- **Monitors Resource Usage**: HPA checks metrics (like CPU utilization).

- **Adjusts Pod Count**: Based on predefined thresholds, it increases or decreases the number of running pods to maintain the desired performance.

**Example:**

Let's create an HPA for a deployment that scales based on CPU usage.

1\. **Deployment** (for the application):

![b05cf16d-00a4-444a-8146-cd580c28d25e.png|627.9976806640625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/b05cf16d-00a4-444a-8146-cd580c28d25e.png) [^60]

\

2\. **HPA** (to autoscale based on CPU):

![6422a658-b332-4283-ba49-7f06543ecebf.png|707.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/6422a658-b332-4283-ba49-7f06543ecebf.png) [^61]

\

**Explanation:**

- The **Deployment** starts with 2 replicas of `my-app`.

- The **HPA** monitors the CPU usage of the `my-app` pods. If CPU utilization exceeds 50%, more pods are created (up to 10). If the load drops, pods will be reduced (down to 2).

This ensures efficient resource usage, allowing the app to handle varying workloads without manual intervention.

![7ec1e1a8-af81-45af-a965-2fc120f694ea.png|896.99072265625](https://images.amplenote.com/e13d2f64-44b8-11ef-9566-26e37c279344/7ec1e1a8-af81-45af-a965-2fc120f694ea.png) [^62]

### <mark style="background-color:#FFFFFF;">**27Q.Horizontal scaling vs vertical scaling?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

**Vertical scaling** - We can increase CPU, RAM, HD

**Horizontal scaling** - Increases no of PODS based of traffic

![3a502df7-46e8-41ba-ac05-3516f74ad48c.png|631](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/3a502df7-46e8-41ba-ac05-3516f74ad48c.png) [^63]

### **28Q. Ingress controller in K8?**<!-- {"collapsed":true} -->

An **Ingress Controller** in Kubernetes is a special type of controller that manages access to services in a cluster, typically HTTP and HTTPS traffic. It listens for changes to **Ingress** resources and configures a load balancer (or reverse proxy) to route traffic based on the rules defined in those Ingress resources.

Here’s a breakdown:

- **Service**: In Kubernetes, a service exposes your app running inside pods.

- **Ingress**: This defines the routing rules to your services from the outside world (like how to reach your app via a specific URL).

- **Ingress Controller**: It’s a piece of software (usually a load balancer or reverse proxy) that actually implements those rules and makes them work. Without it, the Ingress rules have no effect.

**Example Setup (Step-by-Step)**

1. **Create a Kubernetes Service** Let's say you have a service running in your Kubernetes cluster that serves a simple web app.

![bb3810c8-1b1e-414d-a526-9855980f7ba9.png|767.0023193359375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/bb3810c8-1b1e-414d-a526-9855980f7ba9.png) [^64]

\

1. **Create an Ingress Resource** This defines how the traffic from outside the cluster should reach your service. For example, we want to route traffic from `my-app.example.com` to the `my-service` inside Kubernetes.<!-- {"offset":1} -->

![0daadd4d-f9b7-4293-bac5-419ea58b0b9e.png|776.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/0daadd4d-f9b7-4293-bac5-419ea58b0b9e.png) [^65]

\

3\.**Deploy an Ingress Controller (Nginx example)** You need an ingress controller like **NGINX Ingress Controller** or **Traefik** to manage the Ingress resource. If you're using NGINX, you would deploy it using:

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
```

1. **Access your app via Ingress** Now, once the ingress controller is running, and assuming DNS is set up for `my-app.example.com`, any HTTP request to `my-app.example.com` will be routed to the `my-service` in your Kubernetes cluster.<!-- {"offset":3} -->

**Key Points:**

- **Ingress** is like a map that tells the system where the traffic should go.

- **Ingress Controller** is the engine that makes the routing happen.

- Without an Ingress Controller, an Ingress resource alone won’t do anything.

![9ff19e7c-8373-49db-a890-c1cf4dba94b6.png|815](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/9ff19e7c-8373-49db-a890-c1cf4dba94b6.png) [^66]

\

![ffd1731d-4432-46c7-a3ea-aafe071363c0.png|1180](https://images.amplenote.com/e043608c-4586-11ef-a034-26e37c279344/ffd1731d-4432-46c7-a3ea-aafe071363c0.png) [^67]

\

### <mark style="background-color:#FFFFFF;">**29Q. Deployment strategies in K8?**<!-- {"backgroundCycleColor":"11"} --></mark><!-- {"collapsed":true} -->

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

### **30Q<mark style="background-color:#FFFFFF;">. EKS Upgrade using Blue/green?<!-- {"backgroundCycleColor":"11"} --></mark>**<!-- {"collapsed":true} -->

![b516011f-340f-45ee-a4b2-17d99ee76fb6.png|1090](https://images.amplenote.com/ddc6c490-47dc-11ef-8674-6ef34fa959ce/b516011f-340f-45ee-a4b2-17d99ee76fb6.png) [^68]

\

### **31Q. Taints & tolerations in k8?**<!-- {"collapsed":true} -->

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

![588b55ad-33d5-49bf-8097-1a8b408dd865.png|803.9930419921875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/588b55ad-33d5-49bf-8097-1a8b408dd865.png) [^69]

\

This allows the pod to tolerate the `key=value:NoSchedule` taint and be scheduled on nodes with that taint.

\

**Taints and Tolerations in Action:**

- **Scenario 1: Reserve Nodes for Specific Workloads** You can taint certain nodes to ensure only specific workloads (like GPU-intensive jobs) are scheduled there. Only pods with matching tolerations can run on those nodes.

    - **Taint** the node: `kubectl taint nodes gpu-node gpu=true:NoSchedule`

    - **Tolerate** it in the pod spec:

![92902108-ecfc-4949-a8c1-ae2be66625ad.png|747.986083984375](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/92902108-ecfc-4949-a8c1-ae2be66625ad.png) [^70]

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

### **32Q. affinity and anti-affinity in k8?**

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

![2f3d91be-d3be-4ff8-904d-98a32130fb73.png|801.99072265625](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/2f3d91be-d3be-4ff8-904d-98a32130fb73.png) [^71]

- **`requiredDuringSchedulingIgnoredDuringExecution`**: This means the scheduler must place the pod on a node that meets the affinity rules, but once the pod is running, any changes to the node (like removing the label) won’t affect the pod.

There is also **`preferredDuringSchedulingIgnoredDuringExecution`**, which gives preference to certain nodes but doesn’t strictly require it.

\

**Pod Affinity**

Pod affinity allows a pod to be scheduled on the same node or in the same zone as other pods that match specific labels. It’s useful when you want pods to be co-located to reduce network latency or improve communication between them.

\

Example: Pod Affinity

In this example, the pod will be scheduled near other pods with the label `app=my-app`.

![ef8f275b-4b45-4be9-9c87-f1d657209189.png|685](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ef8f275b-4b45-4be9-9c87-f1d657209189.png) [^72]

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

![02f0c7dc-c70b-44ce-b0bc-f86b915a6bec.png|720](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/02f0c7dc-c70b-44ce-b0bc-f86b915a6bec.png) [^73]

**Key Concepts**:

- **Node Affinity**: Controls pod placement based on node labels.

    - Example use: Schedule pods only on nodes with SSDs or GPU resources.

- **Pod Affinity**: Controls pod placement based on the presence of other pods.

    - Example use: Schedule pods that need to communicate closely on the same node (e.g., for performance).

- **Pod Anti-Affinity**: Ensures that certain pods are not scheduled together to increase reliability and availability.

    - Example use: Spread replicas of the same application across different nodes to avoid single points of failure.

These rules provide fine-grained control over pod scheduling, helping optimize performance, reliability, and resource utilization in Kubernetes clusters.

### **33Q. explain Prometheus monitoring tool for k8?**

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

![ebd1905b-1ed5-41df-8080-97dafa09b97d.jpg|649](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ebd1905b-1ed5-41df-8080-97dafa09b97d.jpg) [^74]

![f0df8362-a561-4f7f-b23a-1ef74337cb30.png|937](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/f0df8362-a561-4f7f-b23a-1ef74337cb30.png) [^75]

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

![c2450288-cd5c-4578-b50e-f88311cdc101.png|548](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/c2450288-cd5c-4578-b50e-f88311cdc101.png) [^76]

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

![55d24192-8c42-46ab-8482-7ef33191568d.png|459](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/55d24192-8c42-46ab-8482-7ef33191568d.png) [^77]

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

![9d618288-e8f1-4aea-966b-5b5ddd178b7f.png|817](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/9d618288-e8f1-4aea-966b-5b5ddd178b7f.png) [^78]

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

![ec0a5176-60e3-47e5-8268-e54e70a110bd.png|740](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/ec0a5176-60e3-47e5-8268-e54e70a110bd.png) [^79]

\

\

### **24Q. what is ARG instruction in docker?**<!-- {"collapsed":true} -->

The `ARG` instruction in a Dockerfile defines a build-time variable that users can pass to the Docker build process to customize the image creation. Unlike environment variables set with `ENV`, `ARG` variables are not persisted in the final image, meaning they are only available during the image build process.

![5785c489-6979-4915-aa3d-6f86755636df.png|501](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/5785c489-6979-4915-aa3d-6f86755636df.png) [^80]

\

![1e612a2c-e321-45bf-9e1b-9a3cdbb2232a.png|1058.666748046875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/1e612a2c-e321-45bf-9e1b-9a3cdbb2232a.png) [^81]

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

![e42233b1-5bf4-419b-b6bb-6c003346a390.png|867](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/e42233b1-5bf4-419b-b6bb-6c003346a390.png) [^82]

In this example:

- `WORKDIR /usr/src/app`: Sets `/usr/src/app` as the working directory.

- `COPY . .`: Copies the contents of the current directory on the host into `/usr/src/app` in the container because the working directory has been set to `/usr/src/app`.

- `RUN make /usr/src/app`: Executes the `make` command in the `/usr/src/app` directory.

- `CMD \["./app"\]`: Executes the `./app` executable in the `/usr/src/app` directory when the container starts.

\

**Multiple `WORKDIR` Instructions:**

You can use multiple `WORKDIR` instructions in a Dockerfile to change the working directory at different stages.

![e3fbe365-916f-434b-9716-aa02a444aab2.png|914](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/e3fbe365-916f-434b-9716-aa02a444aab2.png) [^83]

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

![4cf8595d-8026-460d-b31d-5a74ccd15dce.png|659](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/4cf8595d-8026-460d-b31d-5a74ccd15dce.png) [^84]

\

![148c59f4-b295-4462-8351-72a017d88e36.png|721](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/148c59f4-b295-4462-8351-72a017d88e36.png) [^85]

\

**Parent image creation**

![d8ff6b60-1a8a-4437-9a96-d9da70737a08.png|905.6666870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/d8ff6b60-1a8a-4437-9a96-d9da70737a08.png) [^86]

\

**Child image creation (uses parent image)**

![dc473c62-9c60-4b8d-a003-c7d1c0a381f6.png|924.6666870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/dc473c62-9c60-4b8d-a003-c7d1c0a381f6.png) [^87]

\

![89ce30a6-6752-423e-aa95-571c7953700e.png|1024.666748046875](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/89ce30a6-6752-423e-aa95-571c7953700e.png) [^88]

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

### **31Q. What is Docker compose?**<!-- {"collapsed":true} -->

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

\

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

![887e52ec-a93f-4954-9922-7166a678fc53.png|768](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/887e52ec-a93f-4954-9922-7166a678fc53.png) [^89]

![6d3c3f51-7c71-4e4d-b455-1cf214832864.png|740](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/6d3c3f51-7c71-4e4d-b455-1cf214832864.png) [^90]

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

    1. ![11370cc3-a33f-46d5-8d26-820bad5c5736.png|810.9954223632812](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/11370cc3-a33f-46d5-8d26-820bad5c5736.png) [^91]

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

![004e11a5-a365-4fae-aa33-5831c74207f4.png|891.9907836914062](https://images.amplenote.com/e8fba9fc-39b8-11ef-8998-6ef34fa959ce/004e11a5-a365-4fae-aa33-5831c74207f4.png) [^92]

\

### **36Q. Docker disadvantages?**<!-- {"collapsed":true} -->

![272239aa-6f8b-49d3-af12-5a28650234a8.png|995](https://images.amplenote.com/3bc33404-3aa7-11ef-8e08-6ef34fa959ce/272239aa-6f8b-49d3-af12-5a28650234a8.png) [^93]

---

# <mark style="background-color:#F8914D;">**GIT**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

### **1Q. Explain GIT in simple words?**

Git is like a diary for your code. Imagine you're writing a book, and every time you make changes, you save a copy. Git lets you track these changes, go back to any version you saved, and even work with others on the same book without messing up each other's work.

It helps you:

1. **Save Versions:** Every time you make changes, you can save a "snapshot" or version of your code.

1. **Go Back in Time:** If you make a mistake, you can go back to any previous version.

1. **Collaborate:** If you're working with others, Git helps merge everyone's changes smoothly.

It's a tool that keeps your code organized and helps you manage changes efficiently.

![003d69a0-f8c0-4480-aba5-a5b6249d0714.jpg|526.9791870117188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/003d69a0-f8c0-4480-aba5-a5b6249d0714.jpg) [^94]

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

![230c4b3b-730f-4e9c-8c80-b2fd7508322c.png|345.9953918457031](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/230c4b3b-730f-4e9c-8c80-b2fd7508322c.png) [^95]

\

### **12Q. What is the difference between `git merge` and `git rebase`?**

**Answer:**   Merge preservers history, rebase Restructure history.   when in doubt just merge, Never use rebase on public branches.

![7d1a98b2-c7f3-4d01-aed3-847eedf56113.jpg|483.9930725097656](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/7d1a98b2-c7f3-4d01-aed3-847eedf56113.jpg) [^96]

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

![18602b10-a3f0-4b23-8959-6fda153ed2fe.png|339.9884338378906](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/18602b10-a3f0-4b23-8959-6fda153ed2fe.png) [^97]

\

\

### **14Q. How do you resolve a merge conflict in Git?**

**Answer:** When a merge conflict occurs, Git will mark the conflict in the affected files. You need to open the files, manually resolve the conflicts, and then mark the conflicts as resolved using `git add`. Finally, you commit the resolution with `git commit`.

\

![3f6023a2-9f9e-4a40-81bf-64f4c060dc6d.jpg|752.9977416992188](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/3f6023a2-9f9e-4a40-81bf-64f4c060dc6d.jpg) [^98]

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

![dfd3192f-0960-4088-84d7-02b9f3cb9bd4.png|687](https://images.amplenote.com/0729dc16-5479-11ef-a2e2-0663d8339c46/dfd3192f-0960-4088-84d7-02b9f3cb9bd4.png) [^99]

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

[^5]: Kubernetes Architecture Diagram
    Master Node
    Worker Node
    Key Value Store (ETCD)
    POD
    8888
    Kubelet
    POD
    API
    Container
    Server
    Controller
    Runtime
    (Docker)
    Optional Add-ons
    (UI, DNS..)
    Scheduler
    Network Proxy
    (Kube-Proxy)
    Developer
    Worker Node
    POD
    Kubelet
    POD
    Container
    Runtime
    (Docker)
    Network Proxy
    Users
    (Kube-Proxy)
    Optional Add-ons
    (UI, DNS..)

[^6]: Kubernetes Architecture Diagram
    Master Node
    Worker Node
    Key Value Store (ETCD)
    POD
    8888
    Kubelet
    POD
    API
    Container
    Server
    Controller
    Runtime
    (Docker)
    Optional Add-ons
    (UI, DNS..)
    Scheduler
    Network Proxy
    (Kube-Proxy)
    Developer
    Worker Node
    POD
    Kubelet
    POD
    Container
    Runtime
    (Docker)
    Network Proxy
    Users
    (Kube-Proxy)
    Optional Add-ons
    (UI, DNS..)

[^7]: Monolithic
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

[^8]: apiVersion :
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

[^9]: H
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

[^10]: B
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

[^11]: .
    Example Command:
    bash
    Copy code
    eksctl create cluster --name my-cluster --region us-west-2

[^12]: .
    Example Command:
    bash
    Copy code
    kubectl get pods

[^13]: EXPLORER
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

[^14]: POD
    IP address
    catalogue
    ELK
    CONT1
    CONT2
    sidecar
    proxy
    init containers
    N/W and storage

[^15]: labels vs annotaions
    - -------
    labels --> have some limitation on the length and charecters of key and values
    annotaions --> no limit on length and special charecters also can be used...
    labels are used to select other kubernetes resources.
    annotaions are used to select external resources to kubernetes.

[^16]: 18 . 234. 197.98 \| 172. 31. 41.186 \| t2.micro \| https: //github.com/chilops/k8-resources.git
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

[^17]: Kubernetes Labels
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

[^18]: VM vs containerisation
    VM --> 2GB 2CPU --> resources are blocked irrespective of usage
    containerisation --> containers don't block resources, they are used dynamically
    1 VM --> roboshop containers/pods, amazon containers/pods
    traffic increased/code caused more resources to consume
    VM will be blocked by a single container
    we can restrict the resources consumed by containers...

[^19]: spec:
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

[^20]: Services
    if you want to expose pods to other applications or outside we must use services..
    1. expose to other apps or outside world
    2. load balancing
    3. service mesh
    1. Cluster IP --> purely internal to kubernets
    2. NodePort --> you can expose to outside world
    3. LoadBalancer --> you can expose to outside world

[^21]: Service
    Pod
    names as DNS

[^22]: 30133
    30133
    Cluster IP
    Pod
    to
    Actor
    30133
    NADES

[^23]: LoadBalancer
    NodePort
    Cluster IP

[^24]: 30133
    31197
    LB
    30133
    Cluster IP
    Pod
    31197
    Actor
    31197
    30133

[^25]: nginx-rs-<random-id>

[^26]: catalogue : 1. 0.0
    catalogue : 1 . 2. 0
    cluster-ip < node-port < load-balancer
    pod < replicaset < deployment

[^27]: DS
    RS
    pod
    pod
    osgood

[^28]: DS
    RS
    RS-2
    pod
    pod
    pod
    pod

[^29]: DS
    RS
    RS-2
    pod
    pod
    pod
    pod
    pod
    pod

[^30]: stateful vs stateless
    storage
    CRUD
    create data, read the data, update data, delete data. .
    file
    excel
    logs
    RDBMS
    NOSQL
    stateful applications --> doing operations on the data directly.

[^31]: catalogue cart user shipping payment web --> no own database, apps are not storing anything
    stateless Applications
    I
    we can immidiately restore, no business impact..

[^32]: K
    Amazon EKS

[^33]: Amazon EKS
    Storage
    EBS/EFS

[^34]: storage or k8 volumes
    stores data in worker nodes, internal volumes
    1. emptyDip
    2. hostPath
    external volumes
    - -
    1. static provisioning
    2. dynamic provisioning

[^35]: yaml
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

[^36]: yaml
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

[^37]: K
    Amazon EKS
    F--7
    PVC
    EBS

[^38]: Using Persistent Volumes:
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

[^39]: 2. Create a PersistentVolumeClaim (PVC):
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

[^40]: 2. Create a PersistentVolumeClaim (PVC):
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

[^41]: Static Provisioning
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

[^42]: Dynamic Provisioning
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

[^43]: static
    1. first we need to create storage, either storage admin or k8 admin will create the storage
    2. we need to make this volume available to k8 cluster. we should install drivers.
    aws-ebs-csi drivers should be installed
    3. a proper role should be attached to ec2 instance to access EBS.

[^44]: 1. volume should be created automatically.
    2. there is another object called storageClass that can create storage dynamically based on
    the request.
    here external volume and pv would be created automatically by storageClass...

[^45]: 2. we need to make this volume available to k8 cluster. we should install drivers.
    aws-ebs-csi drivers should be installed
    3. a proper role should be attached to ec2 instance to access EBS.

[^46]: Helm Charts
    1. templatise the kubernetes manifests
    2. package manager for kubernetes

[^47]: bash
    Copy code
    helm install myapp ./myapp-chart
    This installs the entire application stack with one command!

[^48]: yaml
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

[^49]: 54 . 234. 195. 42 \| 172. 31. 89.51 \| t2. micro \| https: / /github. com/daws-76s/k8-resources . git
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

[^50]: createUser
    user created
    NODE-1
    master
    NODE-2
    NODE-3
    My SQL

[^51]: yaml
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

[^52]: 1. Role: Define what actions are allowed.
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

[^53]: namespace level
    - - -
    Role
    RoleBinding
    ClusterLevel
    ClusterRole
    ClusterRoleBinding

[^54]: 1. trainees --> read-only
    2. engineers --> limited write access
    3. team leader --> namespace admin

[^55]: Role example
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

[^56]: 1. authentication
    2. authorization

[^57]: EKS will use IAM for authentication. ..authorization should be from EKS

[^58]: HPA
    Autoscaling --> Avg CPU utilisation, if crosses 75% then VM are getting increased.

[^59]: How does a HorizontalPodAutoscaler work?
    Pod 1
    Pod 2
    Pod N
    BC / Deployment
    .....
    Scale
    Horizontal Pod Autoscaler

[^60]: yaml
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

[^61]: yaml
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

[^62]: Cluster
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

[^63]: VERTICAL SCALING
    HORIZONTAL SCALING
    Increase size of instance
    ( Add more instances )
    ( RAM, CPU etc. )
    OC
    Wikitechy

[^64]: yaml
    Copy code
    apiVersion: v1
    kind: Service
    metadata :
    name: my-service
    spec :
    selector:
    app : my - app
    ports :
    - protocol: TCP
    port: 80
    targetPort : 8080

[^65]: yaml
    Copy code
    apiVersion: networking . k8s . io/v1
    kind: Ingress
    metadata :
    name: my- ingress
    annotations :
    nginx . ingress . kubernetes . io/rewrite-target: /
    spec :
    rules :
    - host: "my-app . example. com"
    http:
    paths :
    - path: /
    pathType: Prefix
    backend :
    service :
    name: my-service
    port :
    number : 80

[^66]: Ingress Controller
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

[^67]: ingress
    appl . daws76s . online --> Ingress Controller --> ingress --> appl service --> appl pod

[^68]: 3 nodes --> 1.27
    upgrade master node --> you can't deploy new applications. but existing applications will
    run. we will announce downtime.
    we will create another node group --> 1.29 --> green
    we will slowly drain the nodes. for example old-node-1 is drained and other old nodes are
    tainted. then pods will automatically come up into new nodes.. .
    we will old node group. ..

[^69]: yaml
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

[^70]: yaml
    Copy code
    tolerations :
    - key: "gpu"
    operator: "Equal"
    value: "true"
    effect: "NoSchedule"

[^71]: yaml
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

[^72]: yaml
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

[^73]: yami
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

[^74]: Docker Images and Layers
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

[^75]: docker architecture
    docker run nginx
    1. docker shell/ docker command send a request to docker deamon
    2. docker engine receives the request
    3. it will check whether image is available in local or not
    4. if available it will create container and show the response in client
    5. if not available, it will pul from docker central hub, keep it in local.
    6. create container and response to client

[^76]: Example of a Simple Dockerfile:
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

[^77]: dockerfiles > CMD >
    Dockerfile
    1
    FROM almalinux : 8
    2
    RUN yum install nginx -y
    3
    CMD
    \["nginx", "-g", "daemon off;"\]

[^78]: Example
    Dockerfile
    Copy code
    FROM ubuntu : 20 . 04
    ENTRYPOINT \["echo" \]
    CMD \["Hello, World!"\]
    .
    Running this image without arguments will execute \* echo Hello, World!".
    You can override the \* CMD part by passing arguments to \* docker run, like docker run my-
    image Goodbye!' , which will execute \* echo Goodbye!" .

[^79]: Example
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

[^80]: FROM almalinux : 8
    2
    ARG username
    3
    RUN adduser $username
    4
    USER $username
    5
    CMD \["sleep", "100"\]

[^81]: docker build -t arg: v1 --build-arg username=satya
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

[^82]: Syntax
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

[^83]: Dockerfile
    Copy code
    WORKDIR /usr/src/app
    COPY
    WORKDIR /usr/src/app/config
    COPY config/ .
    RUN . /setup . sh
    In this case, the first \* WORKDIR" sets the context for the \* copy . .' instruction, and the second
    "WORKDIR" changes the context to \* /usr/src/app/config" for the subsequent \* copy and RUN
    commands.

[^84]: V
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

[^85]: REPOS
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

[^86]: 3. 90. 236.230 \| 172. 31 . 44.186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/onbulid \]$ docker build -t on:v1 .
    \[+\] Building 0.2s (8/8) FINISHED

[^87]: 3. 90. 236.230 \| 172. 31. 44.186 \| t2.micro \| https: //github.com/chilops/dockerfiles.git
    \[ centosdip-172-31-44-186 \~/dockerfiles/onbulid/test \]$ docker build -t on-test:v1
    \[+\] Building 0.2s (7/7) FINISHED

[^88]: 3. 90. 236.230 \| 172. 31 . 44. 186 \| t2.micro \| https: //github. com/chilops/dockerfiles.git
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

[^89]: Source code --> compile --> byte code (jar) --> run byte code
    JDK --> Java development kit
    JRE --> Java runtime environment
    JDK > JRE and JRE is subset of JDK
    JDK memory > JRE memory
    I

[^90]: REPOS
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

[^91]: For example:
    Dockerfile
    Copy code
    FROM ubuntu : 20.04
    # Base layer
    RUN apt-get update
    # New layer
    RUN apt-get install -y python3 # Another new layer
    COPY . /app
    # Another new layer

[^92]: 1. base image
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

[^93]: 1. we have a docker host where all containers are running
    what if docker host crash? we lose all containers
    even we use docker volumes, data is still in the host, so we lost data as well
    2. what if traffic increases/decreases? are our containers scalable
    3. even we have multiple containers to balance the load? who is the LB here?
    4. what if some container crashes? can docker make it available again?
    5. what about configurations and secrets? where to store them?
    6. what if we have multiple hosts running with containers
    I

[^94]: Git Workflow
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

[^95]: Typical Merge
    Before Merge
    After Merge

[^96]: Git Merge & Rebase
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

[^97]: Fast Forward Merge
    Before Merge
    After Merge

[^98]: 243
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

[^99]: groovy
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

