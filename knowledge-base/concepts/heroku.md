---
concept: heroku
entity_type: concept
aliases: []
sources: ["raw\\08-devops-and-cloud\\devops_cloud.md"]
confidence: high
created_at: 2026-06-24T07:54:55Z
---

## Definition
Heroku is a cloud platform that simplifies building, deploying, and managing web applications. It is a Platform as a Service (PaaS) and extends [[cloud-computing]]. Heroku implements the idea of treating infrastructure and runtime as a service, thus requiring developers to focus only on their application code and business logic.

## How it works
### Platform as a Service (PaaS)
Heroku functions as a PaaS by abstracting away the underlying infrastructure from developers. This abstracting infrastructure-as-code allows developers to focus on higher-level tasks such as developing and deploying applications rather than managing servers or operating systems.

### Deployment
A developer can deploy an application to Heroku by committing code to a supported version control repository, such as Git. Heroku, leveraging its ci-cd, automatically builds, tests, and deploys the application. Developers can push their code changes to a specific "slug" (a versioned code snapshot) and Heroku seamlessly handles the deployment process.

### Dynos and Services
#### Dynos
A dyno is Heroku's unit of runtime execution. It provides a sandboxed environment for application processes and can be scaled up and down to match the application’s usage level. The application’s process can run as web or worker dynos, serving web requests and background tasks respectively.

#### Services
Heroku supports various services, which integrate directly with applications, extending the applications with additional capabilities like databases, Redis for caching, or managed Kafka for event streams. These services are accessible to the application code through environment variables and Heroku’s runtime support.

### Buildpacks
A buildpack is a collection of scripts and configurations that inform Heroku how to build and run specific types of applications. Heroku recommends a handful of official buildpacks that work with many popular languages and frameworks, such as Ruby, Python, Node.js, and Go. Developers can also create custom buildpacks if their application needs are not covered by the official ones.

### Environment Variables and Config Files
Heroku manages configurable application settings with environment variables. These variables are used to configure application behavior for different environments (development, staging, production) without changing the application’s code. This setup is critical for holding sensitive information like API keys and database access credentials securely.

## Variants
Heroku offers multiple plans and add-ons for different needs and budgets, ranging from a free tier to premium options with advanced features. These variations aim to cater to a wide spectrum of user requirements, from hobbyist projects to large-scale enterprise applications.

## Trade-offs
While Heroku simplifies the developers’ life by abstracting away infrastructure management, it also [depends on] the constraints of the Heroku architecture. This can lead to a trade-off where customization is limited compared to IaaS, which grants more freedom and flexibility over the underlying system. Additionally, as an all-inclusive platform, the cost can escalate as the complexity and scale of the application increase due to the dynamic pricing model based on Dyno hours and addons used.