---
concept: iac
entity_type: concept
aliases: ["Infrastructure-as-Code"]
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T07:54:44Z
---

## Definition
Infrastructure as Code (IaC) is a DevOps practice that enables the definition and management of infrastructure configurations through code rather than via manual procedures. This approach often extends to the abstract layer where definitions are written using specific tools and interpreted to create, change, modify, or optimize the infrastructures. IaC builds on the broader DevOps principles of automation, consistency, and repeatability, ensuring that infrastructure can be treated as a version-controlled software project.

## How it works
IaC operates by defining the desired state of the infrastructure in configuration files, often using a specific, domain-specific language (DSL) designed for infrastructure configuration. These files can be checked into a source control repository to maintain a versioned and auditable history of changes. Tools like Terraform, cloudformation, and Ansible are common choices for expressing this infrastructure in code. Once the configuration files are written, these tools can be invoked to either create the necessary infrastructure or modify it to align with the described state. 

Each configuration file specifies the resources—such as servers, network interfaces, load balancers, security groups—that make up the desired environment. The tools then read these files and interact with target cloud providers, such as AWS or Azure, to either provision, reconfigure, or terminate the required resources based on the file definitions.

- **Toolchain**: Many tools offer plugins or integrations with CI/CD pipelines. For example, Terraform can be integrated with GitHub Actions to automatically apply infrastructure changes whenever code is pushed to a repository, closely tying IaC with DevOps practices.
- **Version Control**: Infrastructure definitions are checked into version control systems like Git, allowing for collaboration and rollback in case of errors, microservices.

## Variants
While Terraform is often cited as a leading tool for IaC, several other tools implement this approach, each with nuanced differences tailored to specific environments or architectures:
- **CloudFormation (AWS)**: Primarily for Amazon Web Services, this tool provides an infrastructure-as-code (IaC) service that allows users to programatically create and manage AWS resources.
- **Azure Resource Manager (ARM) templates** (AZURE): Used for Microsoft Azure resources to define and provision infrastructure.
- **Pulumi**: Offers a multi-cloud approach, supporting various cloud providers and leveraging familiar languages like Python, JavaScript, and C# to describe infrastructure.
- **Kubernetes Helm**: For complex Kubernetes deployments, Helm uses charts to encapsulate packages of related resources.

## Trade-offs
While IaC provides significant benefits, such as consistent infrastructure, faster deployments, and easier rollbacks, it also has some trade-offs and considerations:
- **Skillset Diversity**: Teams adopting IaC may need developers with infrastructure knowledge due to the nature of writing code to define infrastructure.
- **Learning Curve**: The initial setup and ramp-up phase can be steep as learning new configuration languages and tools is required.
- **Operational Costs**: While changes can be automated, the underlying operational costs of running multiple environments (dev, test, prod) or regions can be high, [[devops]].
- **Error Risk**: Incorrectly written configuration files can lead to operational disruptions or security vulnerabilities.
- **Cloud Dependency**: While IaC offers flexibility across cloud providers, deep integration with a specific cloud's APIs and tools might introduce dependency.

IaC trades off ease of manual provisioning with the consistency and automation benefits (RelTradesOff). It benefits from strong typing and rich language features for defining infrastructure configurations, which improves the reliability and response time in deploying IaC-based environments (RelOptimizes).

## See also
[[devops]], [[terraform]], cloudformation, microservices, containers-and-orchestration