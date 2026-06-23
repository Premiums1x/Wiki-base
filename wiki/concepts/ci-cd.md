---
concept: ci-cd
entity_type: technique
aliases: ["continuous-integration-and-delivery"]
sources: ["raw/devops_cloud.md"]
confidence: high
created_at: 2026-06-23T03:38:27Z
---

## Definition
Continuous Integration and Continuous Delivery (CI/CD) refer to a set of practices and tools that automate the steps in the software release process, from integration and testing to deployment. The primary goal is to increase team productivity and application reliability by making the software delivery process more efficient and error-free.

## How it works
In the CI/CD process, software is built, tested, and deployed in a consistent and automated manner. Automating these steps helps to detect and address issues early in the development cycle. The process is typically driven by version control systems, where every commit triggers an automated build, test, and potentially deployment (as in continuous deployment).

1. **Continuous Integration**: Developers commit their code to a shared repository. These commits are immediately compiled and tested against the existing codebase. The result is a single integrated product that can be built and tested on demand.

2. **Continuous Delivery**: If the code passes initial tests in continuous integration, it is packaged into a deployment-ready artifact and released to a testing/staging environment. In continuous delivery, developers aim for the capability to release anytime, without human intervention.

3. **Continuous Deployment**: In continuous deployment, the code that passes tests in the development environment is automatically deployed to the production environment, thereby releasing new features and fixes to users without explicit approval or action by developers or system administrators.

## Variants
**Continuous Integration (CI)**: Focuses on ensuring that code changes from different developers do not conflict with each other. Common tools include Jenkins, Travis CI, and GitHub Actions.

**Continuous Delivery (CD)**: Extends CI by automating the entire pipeline, ensuring that the product can be released reliably at any time. Tools like Spinnaker, GitLab CI, and CircleCI provide advanced deployment pipeline capabilities.

**Continuous Deployment**: A more automated version of continuous delivery where every code change that passes the tests is deployed to the production environment automatically without human interaction. Tools like Google Cloud Deployment Manager and AWS CodePipeline support this fully automated approach.

## Trade-offs
Key trade-offs and considerations include:
- **Complexity**: Implementing CI/CD can be complex and requires significant investment in tooling and culture shift.
- **Risk Management**: Automated deployment can introduce unexpected errors or failures that are not caught until they affect the production environment.
- **Infrastructure Costs**: Using cloud services for maintaining CI/CD pipelines can increase operational costs, particularly for organizations with high deployment frequency.
- **Maintenance Overhead**: CI/CD pipelines rely on continuous maintenance and updates to cope with new tools and technologies.

## See also
DevOps, Infrastructure as Code, Jenkins, [[docker]], [[kubernetes]], GitHub Actions, Terraform