---
concept: docker
entity_type: technique
aliases: []
sources: ["raw/devops_cloud.md"]
confidence: high
created_at: 2026-06-23T03:37:59Z
---

## Definition

Docker is a platform that uses OS-level virtualization to deliver software in packages called containers. These containers encapsulate an application and its dependencies, ensuring that the software runs reliably in different environments.

## How it Works

Docker operates based on the Linux kernel’s features: namespaces and control groups (cgroups). Namespaces provide isolation, while cgroups manage resources such as CPU and memory. Docker containers are isolated from each other and from the host, offering a lightweight, fast, and portable environment for deploying applications.

### Technical Components
- **Image**: A package that contains the application and its dependencies. Docker provides images through repositories, like the official Docker registry.
- **Container**: An instance of an image, running on the Docker engine and isolated from other environments.
- **Dockerfile**: A script that defines the steps for building a Docker image, typically including the base image, dependencies, and application source code.

## Variants

### Docker Desktop
A commercial version that simplifies the workflow for Windows and macOS users by providing an integrated environment for building and testing Docker applications.

### Docker Compose
A tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services, networks, and volumes, and use a single command to create and run all the services from your configuration.

### Docker Swarm
A native clustering solution that turns a group of Docker engines into a single, virtual Docker engine.

## Trade-offs

### Advantages
- **Portability**: Applications run consistently across different environments.
- **Isolation**: Containers are isolated from each other and the host, enhancing security.
- **Lightweight**: Containers use fewer resources than VMs, resulting in faster startup times.

### Limitations
- **Security Concerns**: Shared kernel means potential vulnerabilities can affect all containers.
- **Resource Management**: Ensuring that containers are efficiently allocated resources and do not consume excessive amounts.
- **Complexity in Large-Scale Deployments**: Managing numerous containers requires robust automation tools like Kubernetes for orchestration.

## See also
Containerization, [[kubernetes]], CI/CD, Infrastructure as Code, DevOps