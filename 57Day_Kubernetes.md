---
title: 57Day_Kubernetes
uuid: 5e6efaaa-4219-11ef-8407-26e37c279344
version: 390
created: '2024-07-15T01:13:39+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#f8914d;">**What is stateless & what is stateful?**<!-- {"backgroundCycleColor":"24"} --></mark>

![352acef9-ebe1-4283-8947-fbc5fc41d444.png|1025](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/352acef9-ebe1-4283-8947-fbc5fc41d444.png) [^1]

<mark>**mysql, redis, mongodb & RabbitMQ are stateful applications**</mark>

\

![2186b359-ba99-4e05-b8d4-f107e780930f.png|1081.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/2186b359-ba99-4e05-b8d4-f107e780930f.png) [^2]

\

# <mark style="background-color:#f8914d;">**Storage - k8 Volumes**<!-- {"backgroundCycleColor":"24"} --></mark>

![0bc6b573-e304-4511-95c7-d19a09fb6c05.png|381](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/0bc6b573-e304-4511-95c7-d19a09fb6c05.png) [^3]

![84a13b3c-7e9c-4f32-9188-52169b51c164.png|797](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/84a13b3c-7e9c-4f32-9188-52169b51c164.png) [^4]

\

![edcb2482-d1d8-403f-a01c-e43cf54c20ac.png|434](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/edcb2482-d1d8-403f-a01c-e43cf54c20ac.png) [^5]

\

<mark style="background-color:#f8914d;">**k8 Volumes**<!-- {"backgroundCycleColor":"24"} --></mark>

![9a1b0a0b-6209-4f87-9fac-8b10f347d28a.png|604](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/9a1b0a0b-6209-4f87-9fac-8b10f347d28a.png) [^6]

\

\

# <mark style="background-color:#f8914d;">**emptyDir  - on worker nodes**<!-- {"backgroundCycleColor":"24"} --></mark>

![982498e2-58be-41e8-906f-509014318493.png|545](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/982498e2-58be-41e8-906f-509014318493.png) [^7]

\

![3172d473-40ab-43a4-b485-95c3d6c34c15.png|994.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/3172d473-40ab-43a4-b485-95c3d6c34c15.png) [^8]

\

![a1ca812b-51c2-40a4-b507-adc062fcf5e0.png|643](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/a1ca812b-51c2-40a4-b507-adc062fcf5e0.png) [^9]  

violet image(Elasticsearch in AWS)

\

\

\

# <mark style="background-color:#f8914d;">**Filebeat**<!-- {"backgroundCycleColor":"24"} --></mark>

![be50095c-45d7-4267-b8b6-75cb85d072fc.png|829.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/be50095c-45d7-4267-b8b6-75cb85d072fc.png) [^10]

![a1ca812b-51c2-40a4-b507-adc062fcf5e0.png|432](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/a1ca812b-51c2-40a4-b507-adc062fcf5e0.png) [^11]

\

Filebeat configuration for nginx

![](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/8391e10b-f2f8-4728-85c7-a9edf6e372ef.png) [^12]

\

git push & pull

![dbf73271-90d0-4f07-a5b0-7feb6e861943.png|772](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/dbf73271-90d0-4f07-a5b0-7feb6e861943.png) [^13]

![](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/2fcd56ff-41a6-438e-a4a7-9091d4ce1969.png) [^14]

\

creating POD

```
kubectl apply -f 01-emptyDir.yaml
```

![1c9907a1-4982-4d01-9156-815fda0c5b8c.png|1005.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/1c9907a1-4982-4d01-9156-815fda0c5b8c.png) [^15]

\

```
kubectl get pods
```

![cf315dbf-c883-438c-b50f-8fa02627dd10.png|1041.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/cf315dbf-c883-438c-b50f-8fa02627dd10.png) [^16]

\

logged in to sidecar

```
kubectl exec -it nginx-deployment -c filebeat-sidecar -- bash
cd /var/log/nginx
ls -l
```

![5dfcd527-12ae-47ac-af03-16e3f73bfd29.png|1093.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/5dfcd527-12ae-47ac-af03-16e3f73bfd29.png) [^17]

\

To check Filebeat started & collecting logs

```
kubectl logs nginx-deployment-343ererer -c filebeat-sidecar
```

![1554929e-bfcd-4be8-ac9e-51a8fbaccc90.png|1163.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/1554929e-bfcd-4be8-ac9e-51a8fbaccc90.png) [^18]

![a2682f14-68dc-4850-93fb-93f0bff71c62.png|1167.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/a2682f14-68dc-4850-93fb-93f0bff71c62.png) [^19]

\

# <mark style="background-color:#f8914d;">**HostPath (DeamonSet - Fluentd)**<!-- {"backgroundCycleColor":"24"} --></mark>

Logs on worker nodes are important, like weather worker nodes are connected to Kubernetes master or not, anyone hacking nodes?, monitoring nodes -CPU resources etc... 

The above logs also we need to ship.

\

We need to ship all the worker node logs to external system.

\

<mark style="background-color:#f8914d;">**DeamonSet**<!-- {"backgroundCycleColor":"24"} --></mark> <mark>**- It will make sure a pod runs in each and every node.**</mark> <mark style="background-color:#f8914d;">**Fluentd**<!-- {"backgroundCycleColor":"24"} --></mark> <mark>**will be deployed as DeamonSet that can access the underlying host logs and send them to ELK.**</mark>

![4f191171-54d1-4748-9931-075d4bc5ca80.png|462](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/4f191171-54d1-4748-9931-075d4bc5ca80.png) [^20]

\

<mark style="background-color:#f8914d;">what is DeamonSet ?<!-- {"backgroundCycleColor":"24"} --></mark> Interview question

DeamonSet will make sure a POD runs in each and every worker node. If you delete one worker node a POD in it will delete and if we add new worker node to a cluster then DeamonSet will automatically creates POD. (when you create POD it will create 3 pods in 3 cluster nodes)

\

![6766ea40-b516-4050-a5c7-f97ecad934f3.png|301](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/6766ea40-b516-4050-a5c7-f97ecad934f3.png) [^21] 

\

![2e73d4f4-81e1-4f50-94d8-9f25fb2ea6ed.png|597](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/2e73d4f4-81e1-4f50-94d8-9f25fb2ea6ed.png) [^22]

\

![e7d69cf9-c981-4e9b-bc24-4d694d06da33.png|1097](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/e7d69cf9-c981-4e9b-bc24-4d694d06da33.png) [^23]

\

git push & pull

![](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/cc9bf6e7-6525-48b1-b70a-e7356788d14e.png) [^24]

\

```
kubectl apply -f 02-hostpath.yaml
```

![9d14a1c4-1c00-45f0-8fe3-208d88610445.png|1102.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/9d14a1c4-1c00-45f0-8fe3-208d88610445.png) [^25]

\

To come to default namespace

```
kubens default
kubens kube-system
```

![6a069083-249b-4dc8-abdb-de9b398880d4.png|980](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/6a069083-249b-4dc8-abdb-de9b398880d4.png) [^26]

\

3 PODS create in cluster node(each NODE one POD)

```
kubectl get pods -n kube-system
```

![e488f09f-d2fc-496b-8721-f914f83984b1.png|1024.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/e488f09f-d2fc-496b-8721-f914f83984b1.png) [^27]

\

Now i can see entire logs of the HOST from a POD

```
kubectl exec -it fluentd-h5cxt -n kube-system -- bash
cd /var/log/
ls -l
```

![1f27ce09-8245-45ea-bfa5-0d9bdc9b1f5b.png|1077.3333740234375](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/1f27ce09-8245-45ea-bfa5-0d9bdc9b1f5b.png) [^28]

\

# <mark style="background-color:#f8914d;">**Deleting K8 cluster**<!-- {"backgroundCycleColor":"24"} --></mark>

```
eksctl delete cluster --config-file=eks.yaml
```

![](https://images.amplenote.com/5e6efaaa-4219-11ef-8407-26e37c279344/ca5f0b97-f638-4eab-aee3-69a3d93c8ecf.png) [^29]

[^1]: stateful vs stateless
    storage
    CRUD
    create data, read the data, update data, delete data. .
    file
    excel
    logs
    RDBMS
    NOSQL
    stateful applications --> doing operations on the data directly.

[^2]: catalogue cart user shipping payment web --> no own database, apps are not storing anything
    stateless Applications
    I
    we can immidiately restore, no business impact..

[^3]: K
    Amazon EKS

[^4]: data is getting stored in EC2 worker nodes. .
    pods are ephemeral, nodes are also ephemeral.

[^5]: Amazon EKS
    Storage
    EBS/EFS

[^6]: storage or k8 volumes
    stores data in worker nodes, internal volumes
    1. emptyDip
    2. hostPath
    external volumes
    - -
    1. static provisioning
    2. dynamic provisioning

[^7]: emptyDir
    For a Pod that defines an emptyDir volume, the volume is created when the Pod is assigned to a
    node. As the name says, the emptyDir volume is initially empty. All containers in the Pod can read
    and write the same files in the PemptyDin
    volume, though that volume can be mounted at the same
    or different paths in each container. When a Pod is removed from a node for any reason, the data in
    the emptyDir is deleted permanently.
    Note: A container crashing does not remove a Pod from a node. The data in an emptyDir volume
    is safe across container crashes.

[^8]: 1. emptyDir
    used for sidecar patterns, we mount the volume to sidecar and main container using
    emptyDir. then sidecar get access to storage
    filebeat --> public image from elasticsearch
    I

[^9]: 2
    storage

[^10]: filebeat --> public image from elasticsearch
    I
    there is some configuration for filebeat
    1. i/p and o/p --> i/p is what logs to access, o/p is where to ship the logs

[^11]: 2
    storage

[^12]: EXPLORER
    Dockerfile roboshop-docker\\web
    roboshop.conf
    ! manifest.yaml ..\\web
    REPOS
    k8-resources > storage > ! 01-emptyDir.yaml > {} spec > {} template > \[ \] volumes
    32
    spec :
    > catalogue-deploy
    34
    selector :
    > dockerfiles
    35
    matchLabels:
    > k8-eksctl
    38
    template:
    k8-resources
    39
    metadata:
    > 01-namespace
    40
    labels :
    > 02-pods
    41
    app: nginx
    > service
    42
    demo: deployment
    > sets
    43
    spec :
    44
    storage
    containers :
    45
    ! 01-emptyDir.yaml - U
    - name: nginx
    46
    image: nginx
    k8-roboshop
    47
    ports :
    > cart
    48
    - containerPort: 80
    > catalogue
    49
    volumeMounts :
    > debug
    50
    - name: nginx-logs
    > mongodb
    51
    mountPath: /var/log/nginx
    52
    > mysql
    53
    name: filebeat-sidecar
    > payment
    54
    image: docker . elastic. co/beats/filebeat: 7.17.3
    > rabbitmq
    55
    volumeMounts :
    > redis
    56
    - name: nginx-logs
    ) chinnina
    57
    mountPath: /var/log/nginx
    > OUTLINE
    58
    name: filebeat-config

[^13]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-roboshop (main)
    $ git add . ; git commit -m "jenkins"; git push origin main
    On branch main
    nothing to commit, working tree clean

[^14]: 44 . 211 . 248. 243 \| 172 . 31. 94.116 \| t2. micro \| null
    \[ centos@ip-172-31-94-116 \~ \]$ git clone https: //github. com/daws-76s/k8-resources . git
    Cloning into 'k8-resources' .
    remote: Enumeratiog objects: 99, done.
    remote: Counting objects: 100% (99/99) , done.
    remote: Compressing objects: 100% (67/67) , done.
    remote: Total 99 (delta 37) , reused 86 (delta 24) , pack-reused 0
    Receiving objects: 100% (99/99) , 9.46 KiB \| 3.15 MiB/s, done.
    Resolving deltas: 100% (37/37) , done.

[^15]: 44 . 211 . 248. 243 \| 172 . 31 .94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl apply -f 01-emptyDir . yaml
    configmap/filebeat-config unchanged
    deployment . apps/nginx-deployment created

[^16]: 44 . 211 . 248. 243 \| 172. 31 . 94.116 \| t2.micro \| https : / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl get pods
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    cart-5fcibccbf5-jp4nl
    1/1
    Running
    66m
    OO
    catalogue-79dd48d65f-h747p
    1/1
    Running
    67m
    mongodb-778f7b57d5-pw87m
    1/1
    Running
    68m
    mysql-7f4b445856-wg15v
    1/1
    Running
    53m
    nginx-deployment-5c74df 6cbd-2jcd4
    2/2
    Running
    10s
    nginx-deployment-5c74df6cbd-5z5p1
    2/2
    Running
    10s
    nginx-deployment-5c74df6cbd-qxq2q
    2/2
    Running
    10s
    payment-d947f8795-kt4vj
    1/1
    Running
    38m
    rabbitmq-697fb559c7-vinbh
    1/1
    Running
    4 4m
    redis-86d966bb7-kmxzw
    1/1
    Running
    67m
    shipping-8ffd9bc47-ddscv
    1/1
    Running
    51m
    user-796496c69f-ztp7s
    1/1
    Running
    67m
    web-688fccdc4c-r9swd
    1/1
    Running
    36m

[^17]: 44 . 211 . 248 . 243 \| 172. 31. 94. 116 \| t2.micro \| https: //github. com/daws-76s/k8-resources. git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl exec -it nginx-deployment-5c74df6cbd-2jcd4 -c filebeat-sidecar -- bash
    filebeat@nginx-deployment-5c74df6cbd-2jcd4: \~$ cd /var/log/nginx/
    filebeat@nginx-deployment-5c74df6cbd-2jcd4: /var/log/nginx$ 1s -1
    total 4
    -rw-r
    1 root root 0 Feb 27 02:59 access . log
    -rw-r-
    1 root root 509 Feb 27 02:59 error. log
    filebeat@nginx-deployment-5c74df6cbd-2jcd4 : /var/log/nginx$ cd

[^18]: . 248 .243
    172 .
    . 94 . 116
    t2 . micro
    centos@ip-
    k8-
    I https://github. com/daws-76s/k8-resources . git
    -resources/storage
    kubectl
    logs inginx-deployment-5c74df6cbd-

[^19]: 2024-02-27T02 : 59: 14 .219Z
    WARN
    beater/filebeat . go:136 Fileset ingress_controller for module nginx is loaded but was not e
    xplicitly defined in the config. Starting from v8.0 this fileset won't be loaded unless explicitly defined.
    2024-02-27T02 : 59:14.219Z
    INFO
    \[monitoring\]
    log/log. go : 142 Starting metrics logging every 30s
    2024-02-27T02 :59:14.220Z
    INFO
    instance/beat . go : 492
    filebeat start running.
    2024-02-27T02 : 59:14. 221Z
    INFO
    memlog/store . go : 119
    Loading data file of ' /usr/share/filebeat/data/registry/filebeat' succe
    eded. Active transaction id=0
    2024-02-27T02 : 59:14. 221Z
    INFO
    memlog/store . go : 124
    Finished loading transaction log file for ' /usr/share/filebeat/data/reg
    istry/filebeat' . Active transaction id=0
    2024-02-27T02 : 59:14 .222Z
    INFO
    \[registrar\]
    registrar/registrar . go : 109
    States Loaded from registrar: 0
    2024-02-27T02 : 59:14 .222Z
    INFO
    \[crawler\]
    beater/crawler . go:71 Loading Inputs : 3
    2024-02-27T02 : 59:14 . 222Z
    INFO
    \[crawler\]
    beater/crawler . go:117 starting input, keys present on the config: \[ fileset n
    ame module name exclude_files . 0 path. config path. data path . home path. logs paths . 0 pipeline processors. 1. add_fields . fields . ecs . version
    processors . 1.add fields . target type\]
    2024-02-27T02 : 59:14 . 222Z
    WARN
    \[cfgwarn\]
    log/input . go: 89 DEPRECATED: Log input. Use Filestream input instead.
    2024-02-27T02 : 59:14 . 222Z
    INFO
    \[input\] log/input . go: 171
    Configured paths: \[/var/log/nginx/access . log\*\] {"input_id": "6
    244dcb6-510c-45a3-a3ce-f70bd4cfb185")
    2024-02-27T02 : 59:14 .222Z
    INFO
    \[crawler\]
    beater/crawler . go : 148
    Starting input (ID: 15034772947704077448)
    2024-02-2702 : 59:14 . 222Z
    INFO
    \[crawler\]
    beater/crawler . go:117 starting input, keys present on the config: \[_fileset n
    ame module name exclude_files.0 multiline. match multiline. negate multiline. pattern path. config path . data path . home path . logs paths . 0 p
    ipeline processors. 1. add fields. fields. ecs. version processors . 1. add_fields . target type\]
    2024-02-27T02 : 59: 14. 223Z
    INFO
    \[input\] log/input . go: 171
    Configured paths: \[/var/log/nginx/error . log\*\] {"input id": "5
    1fe71a0-6d74-4061-83cd-825957d4dd2c"}
    2024-02-27T02 : 59:14 .223Z
    INFO
    \[crawler\]
    beater/crawler . go : 148
    Starting input (ID: 4126982979276092710)
    2024-02-27T02 : 59:14.223Z
    INFO
    \[crawler\]
    beater/crawler . go : 117
    starting input, keys present on the config: \[ fileset n

[^20]: DaemonSet
    A DaemonSet ensures that all (or some) Nodes run a copy of a Pod. As nodes are added to the
    cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage
    collected. Deleting a DaemonSet will clean up the Pods it created.
    Some typical uses of a DaemonSet are:
    . running a cluster storage daemon on every node
    . running a logs collection daemon on every node
    . running a node monitoring daemon on every node
    In a simple case, one DaemonSet, covering all nodes, would be used for each type of daemon. A
    more complex setup might use multiple DaemonSets for a single type of daemon, but with different
    flags and/or different memory and cpu requests for different hardware types.

[^21]: -
    Ivar/log

[^22]: hostPath
    A hostPath volume mounts a file or directory from the host node's filesystem into your Pod. This is
    not something that most Pods will need, but it offers a powerful escape hatch for some applications.
    Warning:
    Using the hostPath volume type presents many security risks. If you can avoid using a hostpath
    volume, you should. For example, define a local PersistentVolume, and use that instead.
    If you are restricting access to specific directories on the node using admission-time validation,
    that restriction is only effective when you additionally require that any mounts of that hostPath
    volume are read only. If you allow a read-write mount of any host path by an untrusted Pod,
    the containers in that Pod may be able to subvert the read-write host mount.
    Take care when using hostPath volumes, whether these are mounted as read-only or as read-
    write, because:
    . Access to the host filesystem can expose privileged system credentials (such as for the
    kubelet) or privileged APIs (such as the container runtime socket), that can be used for
    container escape or to attack other parts of the cluster.
    . Pods with identical configuration (such as created from a PodTemplate) may behave
    differently on different nodes due to different files on the nodes.
    Some uses for a hostPath are:
    . running a container that needs access to node-level system components (such as a container
    that transfers system logs to a central location, accessing those logs using a read-only mount
    of /var/log )
    . making a configuration file stored on the host system available read-only to a static pod; unlike
    normal Pods, static Pods cannot access ConfigMaps

[^23]: EXPLORER
    . . .
    op-docker\\web
    roboshop.conf
    ! manifest.yaml ..\\web
    ! 01-emptyDir.yaml
    ! 02-hos
    REPOS
    k8-resources > storage > ! 02-hostpath.yaml > {} spec > {} template > {} spec > \[ \] containers > { } 0 > \[ \]
    arcnieve
    19
    spec :
    > catalogue
    14
    template :
    > catalogue-deploy
    19
    spec :
    > dockerfiles
    20
    containers:
    > k8-eksctl
    21
    - name: fluentd
    AUVEHICLES
    k8-resources
    54
    resources :
    > 01-namespace
    55
    limits :
    > 02-pods
    56
    memory : 200Mi
    > service
    57
    requests :
    58
    cpu: 100m
    > sets
    59
    memory : 200Mi
    storage
    60
    volumeMounts :
    ! 01-emptyDir.yaml
    61
    name: varlog
    ! 02-hostpath.yaml \~ U
    62
    mountPath: /var/log
    k8-roboshop
    63
    terminationGracePeriodSeconds : 30 I
    > cart
    64
    volumes :
    > catalogue
    65
    - name: varlog
    66
    hostPath:
    > debug
    67
    path: /var/log
    > mongodb
    > mysql
    > payment

[^24]: user@AshDexter-T480 MINGW64 /c/devops/daws-76s/repos/k8-resources (main)
    $ git add
    . ; git commit -m "jenkins"; git push origin main
    \[main 44770e4\] jenkins
    1 file changed, 66 insertions (+)
    create mode 100644 storage/02-hostpath . yam1

[^25]: 44 . 211 . 248.243 \| 172 . 31.94.116 \| t2.micro \| https: //github. com/daws-76s/k8-resources .git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl apply -f 02-hostpath . yaml
    daemonset . apps/fluentd created

[^26]: 44 . 211 . 248. 243 \| 172 . 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubens default
    Context "terraform@roboshop . us-east-1. eksctl.io" modified.
    Active namespace is "default".

[^27]: 44 . 211 . 248. 243 \| 172. 31 . 94.116 \| t2.micro \| https: //github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl get pods -n kube-system
    NAME
    READY
    STATUS
    RESTARTS
    AGE
    aws-node-44cjv
    2/2
    Running
    104m
    aws-node-7p2g6
    2/2
    Running
    0
    104m
    aws-node-xmagm
    2/2
    Running
    0
    104m
    coredns-d9b6d6c7d-15sow
    1/1
    Running
    O
    116m
    coredns-d9b6d6c7d-17r6q
    1/1
    Running
    109m
    fluentd-h5ext
    1/1
    Running
    8s
    fluentd-nv2vb
    1/1
    Running
    8s
    fluentd-v7pgm
    1/1
    Running
    8s
    kube-proxy-9zsnj
    1/1
    Running
    104m
    kube-proxy-bang5
    1/1
    Running
    104m
    kube-proxy-1fs4b
    1/1
    Running
    104m

[^28]: 44 . 211 . 248.243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-resources . git
    \[ centos@ip-172-31-94-116 \~/k8-resources/storage \]$ kubectl exec -it fluentd-h5cxt -n kube-system -- bash
    root@fluentd-h5cxt: /# cd /var/log/
    root@fluentd-h5ext: /var/log# ls -1
    total 684
    drwxr-xr-x
    3 root root
    17 Feb 27 01:33 amazon
    drwx--
    2 root root
    23 Feb 13 04:49 audit
    drwxr-xr-x
    2 root root
    121 Feb 27 01:50 aws-routed-eni
    -rw
    1 root root
    1001 Feb 27 02:56 boot. log
    -rw
    1
    root voice
    0 Jan 26 17:53 btmp
    drwxr-x-
    2
    999
    997
    72 Feb 13 04:49 chrony
    -rw-r-
    1 root root
    11078 Feb 27 01:34 cloud-init-output. log
    -rw-r--r--
    root root
    102349 Feb 27 01:34 cloud-init. log
    drwxr-xr-x
    2 root root
    4096 Feb 27 03:19 containers
    -rw-
    root root
    2773 Feb 27 03:17 cron
    -rw-r--
    1 root root
    31572 Feb 27 01:33 dmesg
    -rw-r--r-
    1 root root
    30873 Feb 13 04:50 dmesg. old
    -rw-
    root root
    2375 Feb 13 04:49 grubby
    -rw-r--r--
    1 root root
    193 Jan 26 17:53 grubby_prune_debug
    drwxr-sr-x+
    4 root
    190
    86 Feb 27 01:33 journal
    -rw-r--r--
    1 root root 292292 Feb 13 04:53 lastlog
    -rw
    1 root root
    813 Feb 27 01:33 maillog
    -rw
    1 root root
    442088 Feb 27 03:19 messages
    drwxr-xr-x
    10 root root
    4096 Feb 27 03:19 pods
    -rw-
    1 root root
    7765 Feb 27 01:34 secure
    -rW
    1 root root
    0 Jan 26 17:53 spooler
    -rW
    1 root root
    0 Jan 26 17:53 tallylog
    -rw-rw-r-
    1 root voice
    2304 Feb 27 01:34 wtmp
    -rw
    1 root root
    7073 Feb 13 04:53 yum . log
    r /1

[^29]: 44 . 211 . 248.243 \| 172. 31. 94.116 \| t2.micro \| https: / /github. com/daws-76s/k8-eksctl . git
    \[ centos@ip-172-31-94-116 \~/k8-eksctl \]$ eksctl delete cluster --config-file=eks. yaml
    2024-02-27 03:30:19 \[\[\]
    deleting EKS cluster "roboshop"
    2024-02-27 03:30:19 \[\[\]
    will drain 0 unmanaged nodegroup (s) in cluster "roboshop"
    2024-02-27 03:30:19 \[\[\]
    starting parallel draining, max in-flight of 1
    2024-02-27 03:30:20 \[\[\]
    deleted 0 Fargate profile (s)
    2024-02-27 03:30:20 \[ \~\]
    kubeconfig has been updated

