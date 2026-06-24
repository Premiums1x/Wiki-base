---
concept: github-actions
entity_type: concept
aliases: []
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T07:55:02Z
---

## Definition
Github Actions is an automation platform provided by GitHub that allows for the execution of application workflows in a Continuous Integration/Continuous Deployment (CI/CD) continuous-integration-continuous-delivery pipeline. It extends the functionality of Git by enabling users to define and automate tasks triggered by common actions within their repositories.

## How it works
Github Actions operates by evaluating workflow files stored in `.github/workflows` directories of GitHub repositories. These files are written in YAML and specify the conditions under which actions are executed, such as pull requests, pushes, or issues. The workflow definition includes details on the sequence of jobs and steps required to perform a given automation task.

A job is a set of steps that run on the same runner and can include source and environment setup, tests, and containerization using Docker or other container technologies. Github Actions supports an extensive library of pre-built actions created by the GitHub community or distributed through third-party vendors. These actions can be called directly in workflow files, providing developers with a wide array of functionalities that can be easily incorporated into their automation pipelines.

Additionally, Github Actions can interact with other services and tools through API calls, extending the scope of automated tasks to include deployments on cloud platforms such as Kubernetes and other container orchestration frameworks [[kubernetes]], as well as the deployment of applications on various cloud infrastructure layers, including Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) infrastructure-as-code.

## Variants
Despite being a comprehensive automation solution, Github Actions offers the flexibility to implement customized workflows tailored to specific development processes or compliance requirements. Developers can modify existing actions or create their own using Docker containers or custom scripts. These custom actions can then be published to the GitHub Actions Marketplace for broader adoption, contributing to the growing community of available automated tasks.

## Trade-offs
While Github Actions provides a powerful solution for CI/CD automation, it does have certain limitations which developers should consider. Firstly, executing workflows on runners hosted by GitHub can incur costs depending on the usage and complexity of the actions used, especially for large-scale enterprises or frequent deployments. Organizations with strict data isolation requirements might prefer self-hosted runners to maintain control over the execution environment, though this approach adds complexity and management overhead. Furthermore, reliance on Github Actions could lock developers into the GitHub ecosystem, potentially limiting flexibility if transitioning to or supporting other version control systems becomes necessary.

## See also
Continuous Integration/Continuous Deployment (CI/CD)
Kubernetes
Infrastructure as Code