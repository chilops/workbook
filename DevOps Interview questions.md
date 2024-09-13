---
title: DevOps Interview questions
uuid: 534d208e-09f7-11ef-b967-5658f55e0c13
version: 104
created: '2024-05-04T14:48:53+05:30'
tags:
  - devops
  - devops-interview-questions
---

1. \

1. **Forward proxy vs Reverse proxy ?**


  ```
  VPN --> virtual private network
   
  Servers are not aware of clients are behind VPN
  anonymous access --> hiding our identity
   
  forward proxies can't understand real clients
   
  security --> companies can impose restrictions not to use particular sites, file upload and to monitor use 
  internet behaviour
   
  clients are aware of proxy, servers are not aware
  ```

 

**Reverse proxy**

\-------------------------------

```
clients are not aware of server side
apps use reverse proxy to secure their code
load balancing
```

 

 

**Forward proxy**

![056b653f-8702-45ee-bf3f-1f40c4f225b3.png|781](https://images.amplenote.com/534d208e-09f7-11ef-b967-5658f55e0c13/056b653f-8702-45ee-bf3f-1f40c4f225b3.png)

 

 

![4ea038c1-ba50-4738-b62b-be14f1f2b38f.png|797](https://images.amplenote.com/534d208e-09f7-11ef-b967-5658f55e0c13/4ea038c1-ba50-4738-b62b-be14f1f2b38f.png)

 

**Reverse proxy**

![70eb5ddf-a4e2-4e2e-b803-6b57bd06788d.png|781.3333740234375](https://images.amplenote.com/534d208e-09f7-11ef-b967-5658f55e0c13/70eb5ddf-a4e2-4e2e-b803-6b57bd06788d.png)

 

 

 

 

 

**Ansible Command module vs shell module?**

```
command -- > won't respect target machine shell variables and environment, it is running the command from outside
shell -- > It is like you logged in inside target machine directly and running command & shell module is little slower
```

 

 

 **Idempotence**

```
Ansible ***Idempotence - even you run your program infinite times, it should not create any damage.
For ex. If you trying to create user, if it already exist it wont create & it will go for next step. 
Its not same in shell scripting.
```

 

**What modules you used in Ansible?**

```
File module, get url module, user module, dnf module etc
```

 

 **What is handlers in Ansible?**

```
Handlers: running operations on change
Sometimes you want a task to run only when a change is made on a machine. 
For example, you may want to restart a service if a task updates the configuration of that service, 
but not if the configuration is unchanged Ansible uses handlers to address this use case. 
Handlers are tasks that only run when notified.
```

\

**What is terraform output?**

```
Terraform output is used to get the information from the created resources. 
EX. When we created an instance if we need instance ID, AMI ID or any other details from created instance 
we can get from it in output.

  
Also terraform output is used to get the information of one resource and provide as input to other resources.
```

\

**Terraform functions?**

```
Functions : Terraform has its own function, those we can use it. But we can't create own functions in terraform.
```

\

**what is local in terraform?**

![1388ebed-4e96-4c0b-96a5-d6ae8a17c597.png|588](https://images.amplenote.com/534d208e-09f7-11ef-b967-5658f55e0c13/1388ebed-4e96-4c0b-96a5-d6ae8a17c597.png) [^1]

\

\

<mark style="background-color:#f8d616;">**What is Terraform state & remote state**<!-- {"backgroundCycleColor":"25"} --></mark>**- <mark style="background-color:#f8914d;">? An IMP concept<!-- {"backgroundCycleColor":"24"} --></mark>** 

[^1]: Local Values
    v1.6.x (latest) V
    Hands-on: Try the Simplify Terraform Configuration with Locals tutorial.
    A local value assigns a name to an expression, so you can use the name multiple times within a
    module instead of repeating the expression.
    If you're familiar with traditional programming languages, it can be useful to compare Terraform
    modules to function definitions:
    . Input variables are like function arguments.
    . Output values are like function return values.
    . Local values are like a function's temporary local variables.

