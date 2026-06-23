---
concept: kubernetes
entity_type: technique
aliases: ["k8s"]
sources: ["raw/devops_cloud.md"]
confidence: high
created_at: 2026-06-23T03:38:19Z
---

## Definition

Kubernetes (often abbreviated as K8s) is an open-source, industrial-grade container orchestration system designed for automating deployment, scaling, and operations of application containers across clusters of hosts. Kubernetes aims to make scaling containerized applications efficient and straightforward.

## How it works

Kubernetes operates on a master-worker architecture with multiple components:

### Core Components

- **Pod**: The smallest unit of deployment in Kubernetes, each Pod contains one or more containers. Pods facilitate inter-container communication and shared resources.
- **Service**: A Service exposes a set of Pods to provide a network identity (IP and port) for access from inside and outside the cluster. Services can be used to set up load balancers, manage DNS, and more.
- **Deployment**: A Deployment controller manages how Pods are created, updated, and scaled. Deployments ensure that a specified number of Pods are running at any given time and also handle rolling updates and roll-backs for applications without downtime.

### Key Features

- **Orchestration and Management**: Automatically schedules and runs application containers for scaling and maintaining resilience. It manages the entire lifecycle of applications from deployment to updates and scaling.
- **Self-healing**: Kubernetes ensures application availability and performance by restarting containers that fail, replaces and reschedules containers, and kills containers that don't respond to user-defined health checks.
- **Hybrid and Multi-Cloud**: Kubernetes is cloud-agnostic, allowing applications to be deployed and managed across multiple environments including on-premises, hybrid, and multi-cloud.
- **Scalability**: Kubernetes provides a simple and robust way to scale applications horizontally for handling varying user loads.

## Variants

- **OpenShift**: Developed by Red Hat, OpenShift is a Kubernetes-based platform that offers additional enterprise features such as integrated developer tools, security policies, and support for various deployment models.
- **Kubernetes Managed Services**: Many cloud providers, including AWS (Amazon EKS), Google (Google Kubernetes Engine, GKE), and Microsoft (Azure Kubernetes Service, AKS), offer managed Kubernetes services that simplify the deployment and management of Kubernetes clusters.

## Trade-offs

- **Complexity**: Kubernetes is a complex platform, demanding substantial technical expertise for setup and maintenance.
- **Resource Consumption**: Managing a Kubernetes cluster can consume significant system resources, which might not be ideal for small-scale applications.
- **Security Considerations**: Kubernetes has its own security vulnerabilities and requires careful configuration and monitoring to ensure security.

## See also

- DevOps
- Containerization
- Continuous Integration and Continuous Delivery (CI/CD)