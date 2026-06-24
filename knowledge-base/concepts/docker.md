---
concept: docker
entity_type: concept
aliases: []
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T09:43:54Z
---

## Definition
Docker is a software platform that enables developers to build, ship, and run applications inside lightweight, portable containers, which can be executed almost anywhere, from a local desktop to a large-scale cluster. It builds on the concept of a container, which encapsulates an application and its dependencies into a single package, ensuring the same behavior in any environment.

## How it works
Docker leverages **linux-namespaces** and **linux-control-groups** to create isolated environments for running processes—containers—that have their own filesystem, network stack, and user space. Docker images contain a read-only layer of the application and its dependencies, and containers are created from these images, running the contained processes with read-write capabilities on top of the image.

The *Dockerfile* is a text file that Docker uses to自动化构建应用程序的镜像。它包含构建镜像的指令和环境变量等配置参数，文档化了构建步骤，并且可以通过版本控制系统管理。镜像可以存储在注册表中（如Docker Hub），并通过Docker Daemon调用。

一个Docker容器是通过运行一个或多个应用数据卷容器进行文件管理的。容器之间可以通过Docker Bridge或者直接通过物理网络相互通信。Docker还支持跨机器的容器，比如使用Swarm进行容器管理，允许容器分布在网络中的多个节点上，提高了资源利用效率。

## Variants
Docker支持多种容器化解决方案，包括但不限于用于构建微服务架构的特定数据管理策略。此外，针对特定场景的容器化方案不断涌现，例如使用Docker Compose进行多个容器的本地开发环境配置，或使用Kubernetes这样的[[kubernetes]]来编排大规模的容器集群。

##

## Trade-offs
Docker的优势在于提高了环境一致性，并允许应用程序在不同的环境中以相同的方式运行，从而提升了开发和生产的效率。然而，容器化依赖于操作系统上的内核功能，这意味着每台运行容器的应用机器都必须具备兼容的操作系统版本。此外，容器化需要容器运行时工具，例如Docker Daemon来执行容器镜像。虽然Docker能够提供高效的资源利用率和快速启动时间，但它也引入了新的运维和复杂性问题，这可能是Docker相对于传统虚拟机方案的**virtual-machines**的一个性能优化**speed-improvement**。

## See also
linux-namespaces
linux-control-groups
[[kubernetes]]
virtual-machines
speed-improvement