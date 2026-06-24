---
concept: continuous-delivery
entity_type: concept
aliases: ["CD"]
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T07:54:39Z
---

## Definition
Continuous Delivery (CD) is a software development practice that ensures that code changes can be released to production at any time. It extends [[continuous-integration]] (CI) by automating the deployment phase, delivering and maintaining an executable application in a release-ready state.

## How it works
Continuous Delivery builds on continuous integration (CI), where automated systems check in the code changes at each step, from initial code commit through to the final stages of deployment. The process involves several key steps:

1. **Coding** - Developers write code and push it to a version control system.
2. **Building** - Automated processes assemble the code and other artifacts.
3. **Testing** - Automated tests are run to ensure the code functions as expected.
4. **Integration** - The code is merged into the mainline branch.
5. **Deployment** - The code is automatically deployed to staging environments, and possibly to production, depending on the maturity of the process and the business context.

During testing, various methodologies such as unit-testing, acceptance-test, and performance testing are used to ensure the integrity and quality of the released software. This approach not only speeds up the release process but also reduces the risk of introducing bugs at late stages.

### Environments and Automation
Each environment from development to production requires the exact same conditions, ensuring that the software behaves consistently across all stages. Automation is crucial in Continuous Delivery, as it ensures that humans are not involved in the release process, reducing the likelihood of human error. Common tools used for automation include Jenkins, GitLab CI, and GitHub Actions, which implement CI by automatically running tests every time code changes are integrated into the main branch.

## Variants
Continuous Delivery has a few related practices and implementations, including:

- **Continuous Deployment**: An extreme form of CD where code changes are automatically deployed to production without human intervention after passing all automated checks. This practice builds on Continuous Delivery by eliminating the need for manual approval gates.
- **Blue-Green Deployments**: A technique that optimizes the deployment process by running two identical production environments (Blue and Green). When a new version of the software is ready for release, it is deployed to the Green environment, which is then swapped with the Blue environment without interruption.

## Trade-offs
While Continuous Delivery enhances speed and reduces the risk of human error, it introduces its own set of challenges:

1. **Initial Overhead**: Implementing a Continuous Delivery pipeline can be complex and time-consuming, as it requires setting up CI/CD tools, defining workflows, and automating tests, which are prerequisites for a smooth deployment process.
2. **Complexity Management**: Maintaining a robust Continuous Delivery pipeline requires a significant amount of effort and can become overly complex if not managed well.
3. **Dependency on Automated Tools**: Continuous Delivery relies heavily on automated tools and processes, which can become a single point of failure if not properly maintained.

These trade-offs highlight the need for careful planning and ongoing maintenance to optimize the use of Continuous Delivery.

## See also
[[continuous-integration]], unit-test, acceptance-test