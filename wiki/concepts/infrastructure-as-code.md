---
concept: infrastructure-as-code
entity_type: concept
aliases: ["iac"]
sources: ["raw\\devops_cloud.md"]
confidence: high
created_at: 2026-06-23T04:15:21Z
---

## Definition
Infrastructure as Code (IaC) refers to the process of managing and provisioning computer data centers through machine-readable definition files, eliminating the need for manual processes. These files act as source of truth for infrastructure management, enabling version control and collaboration. wikilink-devops builds on this concept by emphasizing automation and integration between development and operations teams, with IaC being an essential part of automated infrastructure setups. The ultimate goal of IaC is to produce scalable, configurable, repeatable, and version-controlled operating environments and server setups.

## How it works
IaC operates by translating the desired state of the infrastructure into configuration files written in a programming language or markup language. These configuration files are stored in a repository such as Git and can be version-controlled, allowing teams to track changes, establish a baseline, and apply code reviews in the infrastructure. Tools like wikilink-terraform enable this practice by reading these files and provisioning the described infrastructure using APIs.

### Core Components
The core components of IaC involve three main processes:
1. **Provisioning** automatically creates and configures virtual machine images, databases, and other cloud services using scripts or APIs. This involves specifying the desired properties of resources, such as size, operating system, and network configuration, in a machine-readable format.
2. **Configuration Management** manages the deployment and configuration of applications and infrastructure, ensuring consistency across environments. Tools like Ansible and Chef are commonly used to manage software installations, configuration files, and system initialization settings.
3. **Orchestration** manages the interaction between different services and components, often within a complex environment. Tools like Kubernetes take this a step further by orchestrating container deployments, scaling, and management.

IaC practices typically leverage Infrastructure-as-a-Service (IaaS) providers to dynamically allocate computing resources on-demand. This enables teams to quickly adapt to changing workloads and scale resources up or down as required.

## Variants
There are several approaches and tools that implement IaC, each with its own characteristics. Some popular tools include:
- **Terraform** by HashiCorp, which is language agnostic, supports multiple cloud providers, and boasts a declarative syntax that makes it easy to describe desired infrastructure. Terraform is widely recognized for its robust community and extensive library of resources.
- **AWS CloudFormation** is a service offered by Amazon Web Services that uses templates to create sets of related resources and supports SAM (Serverless Application Model) for serverless applications.
- **Microsoft Azure Resource Manager (ARM)** templates used in the Azure cloud environment provide detailed infrastructure specifications.
- **Puppet and Chef** focus more on configuration management, detailing how systems should be configured, rather than the initial creation of infrastructure components.

These tools or frameworks differ in terms of complexity, target audiences, and specific features like support for different cloud providers, ease of use, or ability to automate complex scenarios.

## Trade-offs
IaC offers significant benefits but also has notable trade-offs. Writing and maintaining code for infrastructure necessitates higher skills and training for operations personnel, as traditional scripting and configuration management practices are replaced by programming. This shift can be costly and time-consuming. Additionally, while IaC promotes better security by providing a template that all environments follow, misconfigurations in these templates can create vulnerabilities that affect large portions of infrastructure simultaneously.

IaC setups require careful planning and continuous updates to adapt to changes in infrastructure needs, thereby demanding robust testing and validation procedures to ensure safety and conformity with desired states. Also, as tools and languages evolve, keeping pace with latest version requirements can be challenging.