---
concept: kubernetes
entity_type: concept
aliases: ["k8s"]
sources: ["raw\\devops_cloud.md"]
confidence: high
created_at: 2026-06-23T04:15:03Z
---

## Definition
Kubernetes, often abbreviated as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications. It is designed to provide a consistent and portable environment for deploying containerized applications across different computing environments. wikilinks Kubernetes extends and builds on the containerization technology pioneered by Docker, enabling the management of complex application architectures through a powerful and flexible cluster management system.

## How it works
Kubernetes works by abstracting the underlying infrastructure, allowing applications to run consistently across different environments, from local systems to public and private clouds. At its core, it manages a cluster of nodes, which are physical or virtual machines, and assigns roles to these nodes within the cluster. The primary roles include **master nodes** and **worker nodes** ([wikilinks master-node]), where master nodes manage the cluster and worker nodes run the actual workloads.

### Pods
The smallest deployable unit in Kubernetes is a pod, which can consist of a single container or multiple containers that are tightly coupled and share resources. Each pod is assigned a unique IP address within the cluster, which remains stable even as containers within the pod are replaced or restarted.

### Services
To ensure that workloads are accessible within and outside the cluster, Kubernetes provides the concept of **Services** ([wikilinks service]). Services enable communication by defining a logical set of pods and a policy for accessing them, which can include load balancing across multiple pods.

### Deployments
For managing the lifecycle of pods in a cluster, Kubernetes introduces the concept of **Deployments**. A Deployment allows users to describe the desired state of a collection of pods (their number, configuration, and update strategy) and automatically enforces that state in the cluster ([wikilinks deployment]).

### Scheduling
The Kubernetes **Scheduler** decides how to run pods on nodes, taking into account node resources, pod attributes, and the user’s scheduling requests. Once a decision is made, the Scheduler interacts with the **kubelet** agent on the node to start the containers specified by the pod configuration.

### Automation and Scaling
Kubernetes supports automatic scaling to handle changes in demand. Users can specify scaling rules based on application load or resource usage levels, and the Kubernetes cluster will automatically increase or decrease the number of pods running to maintain desired performance.

## Variants
There are several variants and implementations of Kubernetes, such as:
- **Red Hat OpenShift**, which is a container application platform that builds on Kubernetes by adding features like integrated development environments, tooling, and enterprise-grade security.
- **AWS EKS (Elastic Kubernetes Service)**, which optimizes Kubernetes for the AWS environment, enabling users to run Kubernetes on AWS cloud infrastructure without managing the underlying infrastructure.

## Trade-offs
While Kubernetes offers numerous benefits in terms of automating and scaling containerized applications, it also comes with some trade-offs:
- **Complexity**: Kubernetes introduces a new layer of abstraction that can be complex to understand and may require significant initial setup and configuration effort.
- **Learning Curve**: There is a substantial learning curve for Kubernetes, particularly for developers and operations teams. This can be mitigated by following best practices and using existing patterns for deploying applications.
- **Resource Overhead**: Kubernetes can sometimes add a layer of overhead to large systems, which might not be necessary or beneficial for smaller or less complex environments.