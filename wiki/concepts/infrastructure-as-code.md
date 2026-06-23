---
concept: infrastructure-as-code
entity_type: technique
aliases: ["iac"]
sources: ["raw/devops_cloud.md"]
confidence: high
created_at: 2026-06-23T03:38:40Z
---

## Definition

Infrastructure as Code (IaC) is the management and provisioning of infrastructure through machine-readable definition files, as opposed to physical hardware configuration or the use of interactive configuration tools. It offers a way to automate the creation and management of infrastructure resources through code, thereby improving scalability, reliability, and consistency.

## How it works

In IaC, developers write code or scripts to describe the desired state of the infrastructure components, such as virtual machines, storage, networks, and security policies. The code can be versioned, reviewed, and tested like other pieces of code, which ensures the infrastructure aligns with the development practices used in a DevOps environment. This code is then used by automation tools to build, update, or destroy the infrastructure according to the defined specifications.

A typical workflow involves the following steps:
1. Developers write IaC scripts using a supported language or template.
2. The scripts are committed to version control systems like Git.
3. Automation tools, such as Terraform, Ansible, or AWS CloudFormation, interpret the scripts to build or modify the infrastructure.
4. Any updates or changes to the infrastructure can be managed through merging changes to the IaC files, which are then applied through the automation tool.

## Variants

There are several tools and methods to implement Infrastructure as Code which include:

- **Terraform**: A tool for building, changing, and versioning infrastructure safely and efficiently. It can manage multiple cloud providers and code is written in HCL (HashiCorp Configuration Language).
  
- **AWS CloudFormation**: An Infrastructure as Code service used to model and provision, in an Amazon Web Services (AWS) environment, all the necessary resources such as computing instances, storage devices, databases, security parameters, etc.

- **Ansible**: An open-source software provisioning, configuration management, and application deployment tool that can also be used for orchestration. It uses a simple language written in YAML.

- **Chef**: An IT automation platform that enables Infrastructure as Code to simplify the work of system administrators in controlling and managing IT infrastructure.

- **Puppet**: An open-source configuration management tool focusing on reducing the complexity and repetition of systems management tasks. Puppet uses a declarative language to define the system configuration.

## Trade-offs

While IaC offers numerous benefits, such as improving reproducibility, enabling consistent infrastructure state across multiple environments, and reducing manual errors, there are also several trade-offs and limitations to consider:

- **Learning Curve**: Developers or system administrators may face a steeper learning curve as they need to understand the new configuration language and tools associated with IaC.
  
- **Complexity**: Although IaC simplifies infrastructure management, it can become complex to debug and maintain, especially in large-scale systems where the infrastructure can rapidly evolve.
  
- **Vendor Lock-In**: Some tools or platforms may limit users to specific cloud providers or services, which can lead to vendor lock-in.
  
- **Testing**: Ensuring the quality and reliability of infrastructure managed through IaC can be challenging, as real-world infrastructure changes often have a broad impact which is hard to test comprehensively.

## See also
DevOps, [[cloud-computing]], Terraform, Ansible, AWS CloudFormation, Continuous Integration and Continuous Delivery