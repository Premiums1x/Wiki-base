---
concept: iaac-infrastructure-as-code
entity_type: technique
aliases: []
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T09:43:59Z
---

## Definition
Infrastructure as Code (IaC) is a practice in which infrastructure is provisioned and managed using code rather than physical hardware, which extends infrastructure-as-a-service. IaC is a foundational component within the broader DevOps paradigm, enhancing automation, consistency, and repeatability in infrastructure management. This approach allows infrastructure to be defined and implemented using configuration files, which can be stored in version control systems, enabling a consistent and auditable lifecycle for infrastructure management.

## How it works
In IaC, the usual manual tasks of setting up and configuring servers and applications are automated through code, typically written in a high-level language or a domain-specific language. Developers utilize tools like Terraform to declare infrastructure configurations and apply these configurations to large-scale cloud environments efficiently. Infrastructure is described in plain text files, which are often written in JavaScript Object Notation (JSON) or YAML formats. These files contain metadata about networking, storage, compute resources, and other infrastructure components.

This method not only reduces the risk of human errors associated with manual configuration but also facilitates the creation of a version-controlled record of the infrastructure changes. Every aspect of the servers, including network settings and security configurations, is specified in code, allowing for rapid deployment in multitenant cloud environments. This is particularly advantageous in DevOps, where changes can be deployed quickly and repeatedly without manual intervention.

For instance, in a typical scenario involving a multipurpose web application, IaC might be used to automate the creation of VPCs (Virtual Private Clouds), storage volumes, firewalls, subnet configurations, database instances, load balancers, and application server nodes. Once the infrastructure is defined as code, it can be applied across environments, including development, testing, and production, ensuring parity and reducing the chances of misconfiguration.

Terraform, a popular IaC tool, builds on the concept of IaC by allowing users to manage multiple cloud providers and on-premises infrastructure resources through a single configuration. This tool supports a wide array of cloud providers such as Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP), and Alibaba Cloud, alongside traditional physical infrastructure and emerging cloud services.

## Variants
Several variants and implementations of IaC have emerged, including:
- **Terraform**: Implements IaC by providing a declarative language to describe cloud resources and infrastructure, including AWS EC2 instances, VPCs, and OpenStack resources. It enables the creation, modification, and deletion of infrastructure resources through configuration files.
- **CloudFormation**: A service provided by AWS that helps users model and set up their AWS resources so that those resources are provisioned in a safe, efficient way and so that infrastructure is defined in code.
- **Pulumi**: An open-source infrastructure as code project that allows developers to write infrastructure-as-code in TypeScript, Python, or Go. Pulumi builds on IaC by providing a developer-friendly interface and leveraging an ecosystem of familiar languages and libraries.

## Trade-offs
The adoption of IaC involves several trade-offs, limitations, and considerations:
- **Complexity**: Managing infrastructure as code can be complex, especially for large, dynamic environments where nuanced configurations and dependencies exist. Additionally, learning the syntax and tooling of specific IaC solutions is non-trivial.
- **Cost**: Depending on the size and complexity of infrastructure, IaC can lead to increased costs due to the need for professional software tools and expertise. Some tools are only available under enterprise licenses or require significant recurring costs for ongoing use.
- **Security**: While IaC can aid in securing infrastructure (e.g., by reducing human error), it introduces new threats and vulnerabilities. For instance, if a configuration file is accidentally committed with sensitive information, it can compromise security across the environment.
- **Integration**: For organizations that have historically relied on manual configuration management, the transition to IaC requires integration of new processes, toolsets, and skill sets. Overcoming resistance to change and retraining personnel can be a significant hurdle.

## See also
- infrastructure-as-a-service
- devops