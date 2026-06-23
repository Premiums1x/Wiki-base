---
concept: cloud-computing
entity_type: concept
aliases: []
sources: ["raw/devops_cloud.md"]
confidence: high
created_at: 2026-06-23T03:38:02Z
---

## Cloud Computing

### Definition
Cloud computing is a model for on-demand availability of computer system resources, especially data storage and computing power, without direct active management by the user. The term is generally used to describe data centers available to many users over the Internet.

### How it Works

#### Infrastructure
Cloud computing relies on sharing of resources to achieve coherence and economies of scale similar to a utility (like the electricity grid) often with functions coated into web service (such as Amazon Web Services). At the foundation of cloud computing is the broader concept of converged infrastructure and shared services.

#### Key Components
1. **On-demand self-service**: Users can access computing resources as needed without requiring human interaction.
2. **Broad network access**: Access is available over the network and through standard mechanisms or proprietary tools.
3. **Resource pooling**: Resources are pooled to serve multiple consumers while still preserving identity and state.
4. **Rapid elasticity**: Resources can be rapidly and elastically provisioned, often in a near-instant manner.
5. **Measured service**: The resource usage can be monitored, controlled, and reported, providing transparency for both the provider and consumer of the utilized service.

### Variants
#### Types of Cloud Services
1. **IaaS (Infrastructure as a Service)**:
   - **Description**: Provides virtualized computing resources over the internet. Users have control over the OS, storage, and deployed applications. Examples include AWS EC2, Azure Virtual Machines.
2. **PaaS (Platform as a Service)**:
   - **Description**: Offers a platform allowing customers to develop, run, and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app. Includes services like Heroku, AWS Elastic Beanstalk.
3. **SaaS (Software as a Service)**:
   - **Description**: Software applications delivered on-demand over the internet, eliminating the need for organizations to install and run applications on their computers. Examples include Office 365 and Google Workspace.

### Trade-offs
#### Advantages
1. **Cost Efficiency**: Reduces the need for a huge upfront investment in hardware and software.
2. **Scalability**: Easily scale resources up or down to match demand.
3. **Accessibility**: Access resources from anywhere with an internet connection.
4. **Collaboration**: Facilitates teamwork across different geographical locations.

#### Limitations
1. **Data Security**: Risks associated with data breaches and unauthorized access.
2. **Downtime**: Dependence on the internet, which can lead to service interruptions.
3. **Vendor Lock-in**: Difficulty in switching providers due to data and service dependencies.

### See also
- Continuous Integration and Continuous Delivery (CI/CD)
- Containers and Orchestration
- Infrastructure as Code (IaC)
- DevOps