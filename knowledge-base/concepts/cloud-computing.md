---
concept: cloud-computing
entity_type: concept
aliases: []
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T07:54:14Z
---

## Definition
Cloud Computing refers to the delivery of computing services—servers, storage, databases, networking, software, analytics, and intelligence—over the internet (the cloud), enabling organizations to scale resources based on demand and pay only for what they use. It extends software-as-a-service (SaaS), infrastructure-as-a-service (IaaS), and platform-as-a-service (PaaS), providing businesses with a more flexible and cost-effective computing model. As a fundamental concept, cloud computing builds on [[devops]], the combination of software development (Dev) and information technology operations (Ops) that seeks to shorten the systems development life cycle and provide continuous delivery with high software quality.

## How it works
Cloud computing works through virtualization, a process that simulates hardware functionality to abstract the underlying physical hardware from the software, allowing multiple virtual machines (VMs) to run on a single physical server. This abstraction enables significant scalability because additional virtual machines can be deployed or decommissioned as needed, without the need to physically provision or reconfigure hardware. Users can access cloud services over the internet, providing flexible and location-independent access to compute resources.

The cloud model typically involves a deployment that can be either public, private, or hybrid. Public clouds are owned and operated by third-party cloud service providers and are accessible to the public over the internet. Examples include Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform. Private clouds, on the other hand, are owned and operated exclusively by a single organization and can be managed internally or by a third party, providing more control over the environment and data. Hybrid clouds integrate private and public clouds to achieve the best of both environments, providing flexibility and control over sensitive or critical data.

### Infrastructure as a Service (IaaS)
IaaS delivers virtualized computing resources over the internet, providing users with virtual machines and other resources that typically need to be mapped onto physical hardware. This includes infrastructure components such as physical or virtual servers, networking gear (routers/switches), and storage devices. Users can provision virtual servers and other resources from a web portal or API, and they are responsible for installing and managing operating systems, middleware, runtime, and applications on the infrastructure.

### Platform as a Service (PaaS)
PaaS is a service model of cloud computing where a cloud provider hosts the hardware and software tools needed for application development. This includes the operating system, programming language execution environment, database management, web server, and other tools for app developers. Users are only responsible for writing the code and configuring the applications, while the cloud provider manages the underlying environment.

### Software as a Service (SaaS)
SaaS offers software applications over the Internet, on a subscription basis, allowing users to access software applications on an as-needed, on-demand basis. Users can access SaaS applications using any web browser at any time, eliminating the need for local installations and configurations.

Cloud computing is integral to the implementation of DevOps, a set of practices that emphasizes the collaboration and communication of both software developers and other information-technology (IT) professionals while automating the software delivery and infrastructure changes. By leveraging cloud services, DevOps teams can deploy applications more quickly and efficiently, improving the quality and performance of software as well as business operations.

DevOps benefits from cloud computing in providing scalable resources for development and testing environments, allowing teams to perform operations with a high degree of speed and efficiency. Containers and container orchestration, commonly used in DevOps practices, are more efficiently integrated with cloud computing. Kubernetes, [[kubernetes]], a platform for managing containerized applications, can be seamlessly utilized alongside cloud infrastructure to automate deployment, scaling, and operation of application containers across clusters of hosts.

## Variants
The primary variants of cloud computing are:

1. **Public Clouds**: Offer services to a wide range of organizations via the Internet, making the most cost-efficient option for users.
2. **Private Clouds**: Set up for exclusive use by a single organization and operated within a firewall or on a private network.
3. **Hybrid Clouds**: Comprise a combination of public and private clouds, allowing data to be shared between them as needed.
4. **Multi-Cloud Architectures**: Involve using multiple cloud computing services from different providers to add flexibility to an organization's existing infrastructure.

These variants optimize cloud usage based on cost, security, and scalability requirements. However, the choice between public, private, and hybrid clouds depends on the specific needs of an organization. For instance, companies with strict regulatory requirements might prefer private clouds due to enhanced security and control, whereas those needing scalability and cost-effectiveness might opt for public clouds.

## Trade-offs
Cloud computing has several trade-offs, many of which depend on the business model and specific needs of the user.

### Security
One of the primary trade-offs is security. In the realm of IaC (Infrastructure as Code), even though it allows for consistent and version-controlled infrastructure configurations, security can be compromised through misconfiguration and the compromise of the IaC templates themselves or the secrets typically stored within them. Additionally, accessing data in a shared environment raises concerns about data confidentiality and integrity.

### Costs
Flexibility has a trade-off in terms of predictability and cost. While public clouds can offer variable pricing that scales with resource usage, making it cost-effective for unpredictable workloads, it can lead to unexpected expenses if usage peaks. Conversely, private clouds require upfront investment in infrastructure that may not be fully utilized during off-peak times, leading to underutilized resources unless designed for scalability.

### Automation
While cloud computing allows for quicker deployment and scaling of resources, which can depend on [[devops]] for quicker and more efficient development cycles, over-reliance on automation can lead to a lack of understanding of underlying processes and troubleshooting skills among teams. This can hinder problem resolution when automation scripts fail.

## See also
[[devops]]
[[kubernetes]]
infrastructure-as-code