### Introduction

In the last six months I have been:
- Leading the Data Migration Project.
- A large contributor to the release of the new More Trees platform.
	- One of the main contributors of the initial data migration in preparation of the release of the new platform.
- Familiarising and contributing to the handover of More Trees from HarveyNash.
- Contributing to the Feature Development of the new More Trees platform.

Over the last six months, I have become the lead engineer on the data migration project, seeing major milestones through to completion, and delivering key pieces of work which many customer's have repeatedly been asking for, therefore easing up the workload for CS as they no longer have to handle these queries.

*Note: callout figures here*
Fixed the data integrity issues over 5,000,000 entries and identified and analysed data integrity issues.

I have now been a Graduate Software Engineer for 9.5 months, and over the last six months my responsibilities have increased drastically. I am now consistently and reliably delivering core milestones for data migration, and have been seeing it through to completion despite constantly changing requirements. I am now responsible for providing insight into and solving any data integrity issues that arise due to platform issues. I am now responsible for, and competent at debugging platform issues.

I believe I am performing well above a Graduate Software Engineer, and I am excited and looking forward to my responsibilities being realised through my promotion to Software Engineer in December.

### Achievements / Deliverables

Please refer to [[2024 H1 SMART Goals]] for details on how I have exceeded expectations on my Personal Goals (SMART) and seen them through to completion despite the priorities surrounding the data migration project.
#### Data Migration

The data migration project involves moving data from a legacy MySQL database to a completely new schema in CockroachDB. In detail, it involves:
- Defining data migration requirements with upper management to determine the scope of data needing to be migrated, and dealing with constantly changing requirements.
- Consistent investigation into and solving existing data integrity issues in the legacy MySQL database.
- Investigating and solving data integrity issues existing in the new More Trees platform which allows for the subsequent migration of legacy DB whilst maintaining data integrity.
- Creating ETL (Extract, Transform, Load) pipelines in various technologies (PHP Laravel, Java Spring Boot) which extract core user data from the legacy DB, transform it into a vastly different schema representation, and insert it into the new More Trees CockroachDB.
- Mentoring a new hire (Engineering Manager) on the More Trees data schema and data migration requirements.
- The monitoring of performance metrics (CockroachDB, GCP) during test migrations and live migrations, to ensure no degradation of platform functionality, and to optimise ETL parameters to improve performance of the data migration.
- Validating the data during test migrations, and post live migration to ensure the set of migrated data has improved the integrity of the legacy DB data.

##### Sanitising and Cleaning the Legacy DB Data

The data migration project involved the sanitisation and cleaning of the legacy DB data so that it is in an initial format which can be used to migrate user data into the new platform CockroachDB. The core tasks were:
- Identifying and resolving users with duplicate MTCodes in the legacy DB and generating MTCodes for users missing them. See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-fix-duplicate-mt-codes).
	- Business requirements required linking legacy user profiles with migrated user profile data. This involved identifying a method of uniquely linking a migrated user account with their legacy user profile. A one-to-one mapping of MTCode to Account Code was developed. After investigating the viability of this method, I found that all non-logged in users had no MTCode, and some users had the same MTCode. I developed an app to resolve these integrity issues.
- Identifying and flagging users with malicious intent, former users, already migrated users, users to anonymise, and teqmaven users. See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-flag-users-to-anonymise).
	- This simplified the user migration process as it identified a lot of edge case users, and met business requirements (For example, anonymising TeqMaven users), prior to running the main user migration script.
- Inserting missing users who have had plantations gifted to them.
	- Needed to resolve the plantation gifter-receiver dependency
- Identifying data integrity issues which need to be handled during the migration. For example,
	- Hostile/suspicious accounts (hostile user data).
	- Invalid timestamps.
	- Invalid addresses.
	- Invalid emails.
	- Payment history which does not line up with plantations made and credits received.
	- Incorrect project and tree types.
	- Missing data - payment transaction IDs, payments with no link to a user, incorrect payment types.
-  Identifying and resolving users with duplicate account codes.

**Outcome**
The sanitisation and cleaning of the legacy DB Data was very successful and well handled despite a large part of it being undertook by myself as an early graduate at the time. These tasks being performed at a much higher level than a graduate. 

The migrated user data which now exists in CockroachDB maintains the accuracy of the original user data whilst improving on the integrity by removing and sanitising the initial data. This removes future tech debt and ensures a good base to work upon going forward with MoreTrees. No complaints of missing or incorrect user data has been received by CS which is a testament to the success of this part of the project.
##### Sanitising and Cleaning the Production DB Data

Due to only a portion of the users being migrated pre-launch (1/6th), the subsequent migration of users required lots of additional built in functionality to handle users being active on the new platform. This involved:
- Handling cross-platform duplicate emails.
- Handling cross-platform duplicate account codes.
- Investigating and resolving incorrectly inserted account credit values. See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-fix-credits).

**Outcome**
The handling of data integrity issues arising post launch were handled successfully and resolved swiftly, with no complaints received by CS. Data integrity was maintained during the subsequent migration of the remaining 5/6ths of users (500,000).

#### User Migration App

One of the main deliverables of the data migration app was migrating 600,000 users from the legacy MySQL DB to the production CockroachDB. This involved creating an ETL pipeline in PHP Laravel, which involved:
- Extracting the required source data from MySQL.
- Transforming the source data by sanitising the data and converting it into the required schema structure.
- Inserting the source data into CockroachDB such that the app is performant and maintains integrity throughout.
- Building in redundancy so that if an unexpected fail occurs, the app can reliably pick up where it left off without any data integrity issues being introduced.
- Monitoring of performance metrics (CockroachDB, GCP) during test migrations and live migrations, to ensure no degradation of platform functionality, and to optimise ETL parameters to improve performance of the data migration.

See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-user-migration-script) for the user migration app.
See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-stripe-and-api-key-generator) for the stripe customer ID and API key generation app.

**Outcome**
All users have been migrated successfully, having their data sanitised and integrity improved from the source data. The deliverable was met before the deadline, despite constant battles with additional issues arising and requiring time from Jack King to run the app (The app was prepared months before being able to be run as Jack King was unavailable).
#### Plantation Migration App

One of the main deliverables of the data migration app was migrating all plantation data, 700000+ plantation records, for 600,000 users. This was a large task as a single record needed to be transformed across 3 different data tables in the new schema in a completely new format. I developed a new ETL pipeline, separate of the user migration app, to utilise CockroachDB best practices and improve performance.

See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-plantation-payment-history-migration-script) for the plantation migration app.
[Data Migration Tickets for the Post Launch Epic](https://thehut.atlassian.net/browse/IPMORE-521).

**Outcome**
I had autonomy over the plantation migration app as I was the sole leader of the data migration project when this part of data migration was undertook. I developed the app using CockroachDB best practices for data insertions, which improved upon the performance of the user migration app.
- 1000 user inserts for the user migration took 70 seconds, whilst 1000 inserts for the plantation migration 3.2 seconds. This was a performance increase of 22 times faster (2200%).

The plantation data migration was delivered within the deadline despite several unexpected data integrity issues arising. The delivery of the project was greatly appreciated by the stakeholders, Molly, as it had a positive impact on her job as a lot of the CS complaints she was receiving were about plantation data not being viewable. This deliverable was a very valuable piece of work for More Trees, and was appreciated by each member of SLT. This is evidence for myself having achieved objectives ahead of time and forging good relationships with key stakeholders.

![[THANK YOU.pdf]]
#### Payment History Migration App

One of the main deliverables of the data migration app was migrating all payment history data. This was a large task a the legacy DB payment history data was riddled with data integrity issues, and required the handling of a significant number of edge cases. Additionally, there were added requirements directly prior to migration, after development, which required building in functionality so that stripe subscription data can be linked retroactively post migration.

See [here](https://github.com/THG-More-Trees/mt-data-migration/tree/main/mt-plantation-payment-history-migration-script) for the payment history migration app.
[Data Migration Tickets for the Post Launch Epic](https://thehut.atlassian.net/browse/IPMORE-521).

**Outcome**
This project deliverable was delivered 2 days earlier than the deadline, despite increased requirements, and the deliverable was verbally appreciated by the product owners and SLT.

#### Platform Features Delivered & Harvey Nash Handover

Data migration was the primary objective for this half, however, as I had completed the creation of the data migration apps early, I was able to deliver additional work whilst waiting for availability from Jack King to run the apps. I delivered:

- The account limit feature - A user can only be associated with a maximum of 50 accounts. Ticket on HN Board.
- Investigation and Improvement of the external API error handling. See [here](https://thehut.atlassian.net/jira/software/c/projects/IPMORE/issues/IPMORE-601?jql=project%20%3D%20%22IPMORE%22%20AND%20assignee%20%3D%20712020%3A0ea7e0cc-075a-47d3-88c9-bf6d071dc379%20ORDER%20BY%20created%20DESC).
- Replacing the HarveyNash stripe account integration with the THG owned stripe account in DEV and UAT environments. See [here](https://thehut.atlassian.net/jira/software/c/projects/IPMORE/issues/IPMORE-588?jql=project%20%3D%20%22IPMORE%22%20AND%20assignee%20%3D%20712020%3A0ea7e0cc-075a-47d3-88c9-bf6d071dc379%20ORDER%20BY%20created%20DESC).
- Creating seed data for a local CockroachDB database, to be used for service development.
- Creating documentation for detailing the setup for Backend Development, and providing a tutorial session to teach other members of the More Trees team.
- Several bug fixes and git workflow updates.

#### Deliverables Rating

##### 4.0

***Make deliverables more concise***


For a graduate software engineer ....

1. I have a good understanding of both my personal ambitions and business needs and I have aligned my SMART goals such that both needs are met.
	- The main project I had the opportunity to work on outside of work, focused on technologies which are used by the More Trees team. Therefore, this goal directly correlate with delivering value for the business
	- My other SMART goals relate to writing documentation, performing tutorial sessions, and learning kubernetes. All of these relate directly to both personal ambitions and business needs, and they will correlate with delivering value for the business.
2. I have achieved all my objectives ahead of schedule, whilst developing good relationships with key stakeholders due to having a positive impact on their job and reducing complaints received from customer service. SLT have been vocal about my ability to deliver on time, despite constantly changing requirements and unexpected issues, which require rewrites to the data migration apps.
3. I regularly take on work beyond what is expected. I regularly finished writing data migration apps early and was able to take on additional pieces of work outside my main objective, and deliver these pieces of work successfully. Also, I took on additional pieces of work investing in my personal development outside of work, which increase my capacity deliver value for the business.
	- For example, there was a period of time where I finished the user migration app modifications before Jack King was able to get time to run them on production. During this period, I picked up More Trees feature development and delivered value - I delivered a feature which limits a user to being associated with a maximum of 50 accounts.
4. I support the delivery of others' ambitious goals were possible, despite being a graduate software engineer.
	- I supported and mentored an Engineering Manager early in the year on the data schema and data migration requirements, to help achieve the ambitious goal set for them to deliver the initial user migration pre-launch. Despite, difficulties in understanding and lacking experience in coding, I was able to support their delivery such that the pre-launch user migration was successful.
		- Provide more detail...
1. By definition of what I have achieved, I set a good example for what is achievable for other members of the team and provide a positive impact on their work day.
2. Leadership (Expand):
	1. Optimising for efficient use of Jacks time
	2. Pioneering ideas to improve the the efficiency of data migration
	3. Fought for deliverables
		1. preprocessing, caching, multirow inserts

##### Improvements

I believe to increase my ability to perform at a good mid-level software engineer level:
- The More Trees team and myself would benefit from me improving my ability to support the delivery of others' ambitious goals, mentor other team members, and knowledge share.
	- I will actively pursue this improvement by aligning my SMART goals such that there is quantifiable metrics to measure my improvement in this area. For example, having a SMART goal align with mentoring other team members in areas they wish to improve in. Additionally, I will push SLT for opportunities to demonstrate my ability to mentor and collaborate with other team members.
- Harbour a closer relationship with stakeholders by participating in the technical discussions defining functional requirements on larger pieces of work, and increasing my participation in providing updates on project progress.

### Behavioural Assessment

#### Ambition - 4.0

Stayed up til 5am during launch and up at 8am.

I am exceeding expectations for a Graduate Software Engineer in Ambition:
- I adapt to changing environments, have a positive attitude towards work, and perform well under pressure, reflecting on failures to improve.
	- During legacy DB payment history migration, there were changing requirements provided by the stakeholders close to the deadline, which called for swift changes to the migration app. I discussed and defined the functional requirements of this change, and implemented the changes. Despite the pressure of a looming deadline, and changing requirements I was able to deliver the legacy DB payment history milestone 2 days early.
- I seek developmental opportunities to push my performance.
	- I am constantly pushing SLT for work in other areas of the More Trees team which will up-skill in areas other than data migration. I am always excited when given opportunities to further develop as a software engineer, and it is known by Jack King that I repetitively ask for these opportunities. For example, I am constantly asking to be given work developing features on the More Trees platform despite my main responsibilities on data migration.
- I have enthusiasm and expertise about my work and hold myself accountable for my results.
	- I am always excited to deliver another milestone for the data migration project. I push for collaboration with Jack King to get an early head-start with key data migrations after an app is complete, and come prepared to those meeting to optimise our time spent together. I take responsibility for any data integrity issues that arise post migration, and I have shown the ability to quickly and reliably solve these issues. For example, when duplicate payment transactions were migrated during the legacy DB payment history, I was able to identify the issue source, identify the exact payments which should not have been migrated, and provided the update queries to remove the bad payments.
- I provide some support of others' goals whilst often exceeding expectations on personal goals.
	- I supported and mentored an Engineering Manager early in the year on the data schema and data migration requirements, to help achieve the ambitious goal set for them to deliver the initial user migration pre-launch. Despite, difficulties in understanding and lacking experience in coding, I was able to support their delivery such that the pre-launch user migration was successful.

**Improvements**

I will improve upon my Ambition by consistently dedicating more time to external projects which will up-skill myself in skills required as a software engineer on the More Trees platform. This involves:
- Learning and applying System Design principles that are beneficial for DevSecOps.
- Learning core Spring Boot principles and applying them in my day job.

Up-skilling in areas that are no data migration.

I will improve my Ambition by pushing SLT for opportunities to motivate others, delegate work, and monitor performance. I will do this by taking the lead of a feature development project, such as Buy Now Pay Later, or Guest Checkout, and delegating work on user stories.
#### Innovation - 4.0

I am exceeding expectations for a Graduate Software Engineer in Innovation:
- During the data migration project, there have been many data integrity issues which require in-depth discussions about the best way to approach a solution.
	- For example, during the development of the plantation migration app, I wanted to improve upon the speed of the user migration script as this was a large bottle neck to the ability to deliver the milestone faster. I investigated into ETL and CockroachDB best practices and developed the app such that CockroachDB inserts were pre-processed and pre-calculated and stored in a cache, which were then selected and inserted into CockroachDB as multi-row inserts. The pre-processing step reduces the time spent on processing the data during the CockroachDB insertion, and the cache provides an intermediate representation to validate the data effectively prior to inserting into the production DB. Additionally, the cache is used to keep track of the progress of the inserts into CockroachDB for large data sets, so that if the program failed (due to the connection dropping, for example), there is no loss of progress and the program can continue where it left off.
	- I monitored the improvement of this innovation to measure its success:
		- 1000 user inserts for the user migration took 70 seconds, whilst 1000 inserts for the plantation migration 3.2 seconds. This was a performance increase of 22 times faster (2200%).
	- I propose and discuss these ideas with other team members, such as Jack King, to explore the viability and effectiveness of different approaches, and to promote approaching solutions to problems creatively.

**Improvements**

I will improve upon my innovation identifying potential problems in the More Trees platform and communicating and exploring opportunities of improvement with the other team members. For example, there is a need for an improvement of service logging so that errors are more descriptive and can be used to better pinpoint the cause of the error. Part of this innovation was started in the `External API Error Handling Investigation` project, but a much larger piece of work is required across all services.
#### Decisiveness - 3.5

I occasionally exceed expectations for a Graduate Software Engineer in Decisiveness:
- I have made definite decisions whilst giving full consideration to the positive and negative impact, and have been held accountable for the outcome.
	- The solutions to data integrity issues often require solutions which have a positive and negative impact. For example, many legacy DB users were either TeqMaven, BugCrowd, and Malicious, and many solutions to handle these edge cases were considered. 
		1. They could be left out from user migration:
			- Positive: No suspicious/bad user actors will be present in the production More Trees DB. Negative: If the user had made plantations, they couldn't be linked to valid users who received the plantations.
		2. They could be migrated as they appear:
			- Positive: The user can be migrated without any loss of user data, and their user account can be linked to plantations made. Negative: The production DB will be populated with bad data such as SQL injections.
		3. They could be anonymised and migrated:
			- Positive: The user can be migrated, and their user account can be linked to plantations made. Negative: There is a loss of user data.
	- Full consideration was given to each proposed solution and the decision with SLT and the stakeholders was bullet point 3.

**Improvements**

I have not given myself 4.0 despite having shown the points:
- Consults others in decision making when appropriate.
- Remains firm in decision making processes when under pressure.
This is because I have not encouraged and supported others to apply their initiative proactively. 

I will improve upon my decisiveness by being more involved in the discussion of other team members work and working with them to refine and improve their ideas.

Ask more questions in peer reviews like Jack asked to me.

#### Leadership - 4.0

Rewrite leadership from the perspective of a project leadership.
- Generation confluence docs
- creating and developed a runbook
- coming prepared to meetings

I am meeting expectations for a Graduate Software Engineer in Leadership:
- As a Graduate Software Engineer, I have taken leadership over the data migration project, solved data integrity issues in both the legacy DB and production DB, and effectively delivered value for the stake holders..
- I have made an active effort to show leadership throughout the data migration project:
	- I lead the identification of data integrity problems, propose solutions, and delegate work to Jack King for required decisions on the proposed solutions.
		- For example, I identified payment history edge cases (such as payment transactions missing user IDs) proposed the various solutions (Insert an anonymous user, or exclude the payment). And delegated work required by Jack King to drive progression in the project.
	- I lead the development of data migration apps and challenge thinking in order to drive progression.
		- Refer to innovation example.

**Improvements**

I will improve upon my leadership in the next half by taking the lead of a feature development project, such as Buy Now Pay Later, or Guest Checkout. Further, I wish to collaborate with stakeholders to better understand the business needs around leadership.

#### Collaboration - 3.0

I am meeting expectations for a Graduate Software Engineer in Collaboration:
- I collaborate with More Trees team members during incidents, investigating bugs, and completing milestones.
	- For example, myself, Jack Owen, and Jonny King joined a group call to discuss the bugs surrounding the Invoice Price calculation. We discussed the current behaviour, expected behaviour, and potential fixes. We finalised a decision and confirmed the correct behaviour with Jack King. This collaborative effort produced a greater outcome by combining all members expertise. Additionally, it improved the positive relationships within the team.
- I collaborate with members of the business to broaden my understanding.
	- For example, I had several mentoring sessions with Joost (A Technical Solutions Architect outside of the direct More Trees team), to broaden my understanding of the More Trees data schema and how the More Trees platform is intended to work and develop in the future.

**Improvements**

I will improve upon my collaboration by seeking opportunities to collaborate with others outside my direct team.
- Utilising the THG Teams channels to collaborate with other members of the organisation. For example, using the CockroachDB champions channel to keep track of common issues and ask any questions relevant to the More Trees teams.
- Any advice?













- **Projects and Contributions**: List the key projects you worked on, detailing your specific contributions and their impact on the team or organisation.
	- Go through Jira Tickets and Notes - Include all work from January.
- **Achievements**: Highlight any significant achievements, such as completing a challenging project, meeting deadlines, or exceeding performance metrics.
	- Percentage increase in speed of data migration programs.
	- Approval email from Molly.
	- No complaints about plantations any more.
	- Excitement from Jack King over the speed of my data migration programs.
	- How resilient I was in encountering persistent data migration and integrity problems which require rewrites due to constantly changing requirements.
	- Meeting deadlines despite constantly changing requirements.
	- Positive impact on Molly's Job as she no longer has to deal with complaining customers.
	- Spent lots of time outside working hours to complete the project on time.
	- Always prepared for meetings
	- *Mention how you improved efficiency by a certain percentage, contributed to a project's success by delivering it ahead of schedule, or increased user engagement on a feature you worked on.* 
- **Innovations and Improvements**: Note any process improvements, automation, or innovations you introduced.
	- Used CockroachDB documentation and knowledge to implement optimisations to the data migration apps to increase the performance, better utilising data base resources.

Example - Support others' goals - Providing learning sessions on Backend development to aid others in achieving their goals of improving the Spring Boot Backend Development.

All jira tickets - https://thehut.atlassian.net/jira/software/c/projects/IPMORE/issues/IPMORE-779?jql=project%20%3D%20%22IPMORE%22%20AND%20assignee%20%3D%20712020%3A0ea7e0cc-075a-47d3-88c9-bf6d071dc379%20ORDER%20BY%20created%20DESC
