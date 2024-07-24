
## Introduction

[Smart Goal Document](https://hutgroupnorthwich-my.sharepoint.com/:x:/r/personal/thomas_gill20_thehutgroup_com/_layouts/15/Doc.aspx?sourcedoc=%7B4F3FD1AE-46B7-4BF6-8C64-B691B6EAC973%7D&file=SMART%20Objectives%202024.xlsx&action=default&mobileredirect=true&DefaultItemOpen=1&login_hint=Thomas.Gill20%40thehutgroup.com&ct=1720948093303&wdOrigin=OFFICECOM-WEB.START.EDGEWORTH&cid=d52ac523-e9fc-4feb-9f11-8cc881632dd8&wdPreviousSessionSrc=HarmonyWeb&wdPreviousSession=d1c7396c-a0c2-4ba3-8e38-a3ea1da03368)
#### Purpose

The purpose of this document is to provide a detailed account of the SMART goal achievements, including accomplishments, lessons learnt, and the applicability of the skills within the More Trees Team.

The evidence for these SMART goals has either been documented within the `SMART Objectives 2024` document or show cased to my manager Jack Owen.
#### Scope

The document covers the goals set, the progress made towards achieving them, and how the outcomes benefit both my professional growth and the More Trees Team.

#### Note

- These SMART goals were created halfway through the first half of 2024. I had several managerial changes throughout which these SMART goals were not properly defined until March. Despite these setbacks, I am very happy with the outcome of these SMART goals and the skills I have learned.
- These SMART goals were impeded by data migration taking a much higher priority and requiring lots of my time. I spent significant hours outside of working hours, to aid in the successful completion of the user and plantation migration so that the project can be met on schedule. I believe these extenuating circumstances should be taken into account during my performance review.
## Springboot Application - Lift
#### Introduction

**Specific** - Create a mobile application for tracking weight training performance metrics and measuring progression of workouts. Backend written in Spring Boot and frontend written in React Native (typescript). Implement integrations with stripe, auth0 (all security concerns along with this), openAPI, CockroachDB. Create and implement the database schema for the app.
**Measured** - There is a viewable schema of the data model implemented in cockroach DB. Users are able to register through auth0, with their jwt tokens being handled through OAUTH2 principles, and pages are access controlled. Users are able to create workouts and add their performance metrics for a given workout session. Stripe integration allows users to upgrade to a premium account. 
**Achievable** - Not achievable but this is a stretch goal (Kierons suggestion). 
**Relevant** - The backend architecture is similar to the new MoreTrees platform, and the general web programming principles will improve my capabilities as an engineer.
**Time-based** - 30th June 2024:
- NOTE: Due to HN Handover of MoreTrees, I had less time available for personal projects after work hours.
#### Technology Stack

**Database: CockroachDB**
- CockroachDB was initially chosen as the More Trees platform uses CockroachDB as its database management system.

**Authentication and Authorisation: Auth0**
- Auth0 was chosen as I have made a previous application where I implemented the OAUTH2 authorization protocol, with self-management of JWT tokens. I wanted to explore different methods of authorization, additionally, the More Trees platform uses Auth0 so the skills I learn are directly applicable.

**Backend Framework: Spring Boot**
- Spring Boot (Java) was chosen as it is the language I'll primarily be using during work at THG, so any knowledge gained is beneficial for the company.

**API Specification and Documentation: OpenAPI**
- I chose to use a package for the generation of API documentation as I haven't had much experience using this directly other than on MoreTrees. Additionally, the OpenAPI specification is used by the MoreTrees backend services.

**Frontend Framework: React Native**
- I wanted to develop a mobile application and I wanted to use React as it is used on MoreTrees, so I chose to use React Native. 

#### Open API Specification

##### What has been Achieved?

1. I have learnt how to integrate OpenAPI API generation within a springboot application.
2. Gain knowledge in designing and documenting RESTful APIs.

##### Lessons Learnt

1. I have learnt that integrating documentation from the beginning of the development process is crucial.
	- This is even more important when the development team is large and consistency of the API usage is critical. It ensures the documentation grows with the project and remains accurate.
2. Comprehensive API documentation improves and speeds up the onboarding process for new developers.
	- This is because new developers can become productive quicker when they have access to clear documentation.
3. When there is standardised API documentation, it improves communication across the team as there is a single source of truth API functionalities. 
	- For example, which parameters certain API endpoints accept.
4. API First approach is beneficial as we have to consciously think about API specification prior to development.

##### Benefit / Applicability to MoreTrees

1. All the lessons learnt are directly applicable to software engineering within a development team. Therefore, these are directly beneficial for the More Trees team.
2. My knowledge gained for using the best practices for writing OpenAPI documentation is carried across to the More Trees platform development as we use OpenAPI for API specification.

#### CockroachDB

##### What has been Achieved?

1. I have learnt how to implement a database solution within a Spring Boot application.
2. I have developed and designed an effective data model for the Lift application which effectively stores the required data with minimal redundancy
	- I have applied the lessons taught by Joost Doevelaar, during his mentoring, for his design decisions for the More Trees database schema.
- I have created and managed a CockroachDB Cloud database cluster, uploading my database schema and connecting it to my java application.

##### Lessons Learnt

1. I learnt about troubleshooting common issues with integrating a cockroach DB cluster in a spring boot java application.
2. I learnt the important of trouble shooting practices and robust monitoring.
	- This is additionally applicable to the More Trees data migration project as robust monitoring is very important when migrating large data sets.
3. I applied knowledge my knowledge of database normal form to design and develop an effective data base model for storing the data required for the Lift application with minimal redundancy.

##### Benefit / Applicability to MoreTrees

1. All the lessons learnt are directly applicable to software engineering within a development team. Therefore, these are directly beneficial for the More Trees team.
2. The development and design of a database model with no redundancy requires lots of forward thinking and considerations for built-in flexibility for future features. The skills developed carrying out this activity is directly applicable to More Trees for when we need to extend the database model for future features required by the product owner. For example, the introduction of Carbon Credit purchase functionality.
4. Being able to give insight into monitoring metrics is directly applicable to the More Trees team because it can help to quickly diagnose issues with slow end points due to inefficient queries. Additionally, it can help optimise resource usage to minimise costs.

#### Authentication and Authorisation: Auth0

##### What has been Achieved?

1. I have integrated an Auth0 API and Application within the Lift technology stack. This enables secure authentication and authorisation across both the backend and frontend application.
2. I have successfully set up JWT token management within the Spring Boot application so that users can be correctly authenticated and access control can be applied across the Lift API end points.
3. Integrated granular access control using Auth0's roles and permissions features to allow precise control over which resources and functionalities a user has access to, enhancing the security of the Lift application.
4. Leveraged Auth0’s SDKs and documentation to simplify the implementation of authentication and authorization.

##### Lessons Learnt

1. Understanding and implementing security best practices which is crucial for protecting user data.
	-  Auth0 provides a strong foundation, but it is still essential to follow best practices such as regularly updating dependencies, using strong passwords, and rotating secrets.
2. I have learnt how to handle permissions and roles within an Auth0 API and Application.
3. I have learnt how to troubleshoot and debug common issues with Auth0 during the process of retrieving JWT access tokens, retrieving management tokens, sending password reset emails, signing up a new user, and giving roles to users.
4. I have learnt how to monitor authentication and authorisation activities within Auth0 which is crucial for maintaining security, and is helpful in troubleshooting and debugging issues.
	- Using Auth0’s monitoring and analytics tools can be used to help track login attempts, identify suspicious activities, and ensure the overall health of the authentication system.
- Follow the [OWASP Top 10](https://owasp.org/www-project-top-ten/).

##### Benefit / Applicability to MoreTrees

1. All the lessons learnt are directly applicable to software engineering within a development team. Therefore, these are directly beneficial for the More Trees team.
2. The More Trees application uses Auth0 for authentication and authorisation. Therefore:
	- Learning the usage of the Auth0 API is directly applicable to More Trees as I will be more equipped for developing features revolving around changing or using the authentication and authorisation processes.
	- Learning how to handle permissions and roles is directly applicable to MoreTrees as there is frequently changes to roles and permissions when there are new features added. For example, implementation of admin assign credit and cross charge functionality required changes to Auth0 roles and permissions.
	- Learning how to monitor authentication and authorisation activities in Auth0 is directly applicable to More Trees as I will be more equipped to troubleshoot and firefight security incidents or authentication issues.

#### Backend Framework: Spring Boot

##### What has been Achieved?

1. I have written the BE framework in Spring Boot java integrating with other essential tools such as Spring Security, Spring Data, MapStruct, and HttpClient.

##### Lessons Learnt

1. I have learnt how to develop and use a Web Client Config for performing web requests and handling the responses returned (such as to Auth0).
2. I have improved my ability to implement security best practices, within the Security Configuration, Cors Configuration, and Jwt Auth Filter.

##### Benefit / Applicability to MoreTrees

1. All the lessons learnt are directly applicable to software engineering within a development team. Therefore, these are directly beneficial for the More Trees team.
2. The knowledge gained from setting up security and web client configurations is directly beneficial to the development on the More Trees Team as we have our own configurations setup using the same Spring Boot packages.

***As these lessons were learnt and skills were developed on an external project outside of More Trees, it shows my dedication to providing value to the team and THG as a whole.***
## Kubernetes Deployment

See the [powerpoint](https://hutgroupnorthwich-my.sharepoint.com/:p:/r/personal/thomas_gill20_thehutgroup_com/_layouts/15/Doc.aspx?sourcedoc=%7B4BBCD684-5318-4B09-999E-0775D11D0BDE%7D&file=Personal%20Kubernetes%20Deployment%20Evidence.pptx&action=edit&mobileredirect=true&DefaultItemOpen=1&login_hint=Thomas.Gill20%40thehutgroup.com&ct=1720946673994&wdOrigin=OFFICECOM-WEB.START.REC&cid=dae4abc5-8f3b-4971-b961-7e9ade8df6d7&wdPreviousSessionSrc=HarmonyWeb&wdPreviousSession=d1c7396c-a0c2-4ba3-8e38-a3ea1da03368) I created.
#### What has been Achieved?

1. Creating a Kubernetes Cluster using MiniKube.
2. Build the lift Docker image:
	- Package the Spring Boot Lift Application.
	- Write a Dockerfile to create the Docker image.
	- Containerise the Application.
	- Push the image to the container registry.
- Deploy the application to the Kubernetes Cluster.
	- Create a Kubernetes Deployment file.
	- Create a Kubernetes Service file.
	- Deploy the container image to the cluster.
	- Access the application and debug any container deployment issues. Issues encountered:
		- Pulling the Lift Application image from the docker hub registry​
			- Solution 1: Download the Cloudflare CA Cert and add it to ~/.docker/certs.d​
			- Solution 2: Pull the image from the local registry of images​
		- Running the application failed due to missing secrets​
			- Solution 1: Upload the secrets to the Kubernetes Cluster
- Upload the secrets required for the application to the cluster.
	- Create the Kubernetes Secret configuration file which define the secrets required by the application.
	- Deploy the secrets to the cluster.
	- Update the Kubernetes Deployment file to use the secrets.

Even though I have just outlined the steps I took throughout this SMART goal to achieve the original goal, this in itself is what has been achieved. And, each step has provided value and lessons which can be applied to the More Trees team.
#### Lessons Learnt

1. Improved my ability writing Kubernetes deployment, service, and secret files.
2. Improved my ability debugging container deployment issues.
3. Improved my understanding of Kubernetes.

#### Benefit / Applicability to MoreTrees

1. All the lessons learnt are directly applicable to software engineering within a development team. Therefore, these are directly beneficial for the More Trees team.
2. On the More Trees team it is frequently required to debug container deployment issues on a Kubernetes Cluster, therefore the skills improved through this SMART goal is directly beneficial for the More Trees team.
3. On the More Trees team it is likely we may need to alter the Kubernetes deployment files for the BE services or UI.
## More Trees Documentation

#### What has been Achieved?

1. I have written comprehensive documentation covering the data migration project, the More Trees data model, and the backend services. 
	- Each of the data migration documentation pages are directly relevant to current/past work and is essential for understanding what has been done throughout core parts of data migration.
	- Each of the backend service documentation and Data Model pages is essential for onboarding new More Trees developers.
2. The pages are:
	- A detailed document on the purpose, setup, functionalities, usage, and troubleshooting of the user migration app. See [here](https://github.com/THG-More-Trees/mt-data-migration/blob/main/mt-user-migration-script/README.md).
	- A detailed document on the purpose of the  `mt-flyway` repository and how database migration changes are applied across different environments. See [here](https://github.com/THG-More-Trees/mt-flyway/blob/develop_mt_user/README.md).
	- A detailed document on the purpose, setup, functionalities, and execution of the `mt-anonymise-user` repository. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/4913201222/How+to+Anonymise+user+data).
	- A development guide on setting up, interacting with the backend services. It includes guides on testing changes locally using postman and testing development features by deploying a feature branch to the develop environment. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/4932338342/Backend+Development).
	- A document detailing common issues encountered during development, so that onboarded developers can quickly resolve common issues. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/4933189707/Common+Issues)
	- A development guide on how to migrate stripe accounts. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/4936794119/How+to+Migrate+stripe+account).
	- A document detailing the Error Handling Investigation project. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/4949213268/Error+Handling+Investigation).
	- I have additionally started creating developer documentation which details the entirety of the Data Model. It will detail: the reasoning behind design decisions, areas of in-built flexibility for future feature, relationships between data schema entities (such as account and user), and how the schema is utilised by the backend services. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/5012684910/Tables).
	- Several other pages documenting data migration. See [here](https://thehut.atlassian.net/wiki/spaces/MOR/pages/4881449044/Data+Migration).

#### Lessons Learnt

1. Improved my ability to write comprehensive, concise, and accessible documentation for the team's projects and processes to improve knowledge sharing and onboarding.
2. I have learned the importance of collaborative input and that gathering input from various team members enriches documentation (For example, gaining insight in improvement to the `mt-flyway` documentation during my knowledge sharing session for setting up Backend Services).
3. I have reinforced my knowledge of the importance of structured and well organised documentation for clarity and ease of use by other team members.

#### Benefit / Applicability to MoreTrees

1. All of these pages are directly applicable to the More Trees team:
	- The developer documentation improves knowledge sharing which can be used by other members of the team to increase productivity as it minimises the need to re-investigate issues and ask other team members for help.
	- Enhances onboarding process as the developer setup time is reduced and common issues can be resolved quickly.
	- Improves collaboration between team members.
	- Increases auditing of projects so that past design decisions are recorded and can be reflected on in the future.
	- Captures lessons learned and best practices from previous projects, promoting continuous improvement.
