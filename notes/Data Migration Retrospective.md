Plan:
- Go through the timeline of data migration
- What Went Well
	- Improved data quality
	- Migrated all user data and reduced CS complaints by 70%.
	- 
- What could have been better
	- Would have been better if I had the more full scope of tasks that needed to be done so that planning could be more accurate.
		- We had changes to requirements constantly which had delayed some of the completion dates, these were still completed on time / early, but with this knowledge the total time spent on data migration would have been reduced.
	- If I had full ownership of the data migration project from the very start, that way the time spent onboarding TT and then getting me up to scratch with his work when he left wouldn't have been needed.
	- 
- Improvements for the future

- What has been learnt
	- Optimising SQL queries
	- Optimising SQL inserts
	- Monitoring database performance and responding to load
	- Extensive More Trees data schema and data quality knowledge
	- Existing problems within the legacy More Trees platform which were unknown

Notes:
- Added requirements - transfer legacy bank transfers which weren't shown in finance transactions, but a customer has complained about not being present on in their history (so much be valid) - Lots of edge cases.
- Cross Charge Plantation and Payment History Reconciliation for brands went smoothly.
- Improvements of smoothly rolling out data migration objectives as the project progresses and we learned from past rollouts.
- Validation Process.
- Working on a solution to problems, not complaining about the problem itself.

### Introduction

The purpose of this retrospective is to analyse and reflect on the data migration project, identifying key successes, challenges, and areas for improvement. The scope of the project included migration all user, plantation, and payment history data from a legacy database schema to a new schema, with the main objective being to improve data quality.
### Project Overview

The project was initiated in January 2024 as a part of the launch of a new More Trees platform in February 2024. We needed to move data from an unstructured legacy DB schema with very poor data integrity to a very structured new DB schema where we wanted very good data quality.

**Key Milestones**
![[Timeline 2.pdf]]

### Migration Process
The typical migration milestone process follows these steps:
1. Initial assessment of the data and systems involved:
	- Identify data integrity issues that need solving.
2. Develop the migration app.
	- Extract required data from the legacy database.
	- Transform the data, improving the data quality and converting it into the data structure required.
	- Import the data into the required database.
3. Test the app (Local, Dev, UAT)
	- Run the application on real data and validate the output data.
4. Run the app in production
	- Creating run-books, monitoring performance, optimising performance.

### Successes and What Went Well
- Migrated (processed, sanitised, and inserted) a total of `~7,000,000` database records.
- Migrated all user data, plantation history, payment history, and subscription data, reducing CS complaints by ~70%.
- Significantly improved the data quality of the legacy platform data.
- Pioneered ideas to improve the efficiency of data migration, including pre-processing and caching source data and implementing multi-row inserts, resulting in a speed increase of 22x.
- Met deadlines despite frequent changing requirements.

### Challenges and Issues
- Identifying and fixing the integrity issues brought forward from the pre-launch user migration (duplicate emails, incorrect created_when date, incorrect account credits).
- Poor communication of proposed deadlines (improved as the project progressed).
- Handling the subsequent migration of users post launch on an active site.
	- Handover of a program in an unfamiliar language.
	- Handling cross-platform duplicate emails (requires consolidating user info).
	- Fixing issues with pre-launch migration app.
	- Monitoring performance metrics to ensure site functionality is not affected by the large migration.
- Slow run-time of the user migration app.
	- Monitored performance and resources to optimise DB queries and threads.
	- Managing the gradual migration of users over several days (implementing fault tolerance and persistence).
- Identifying and solving data integrity issues of payment data.
- Constantly changing requirements frequently caused an unexpected increase in work required close to deadlines (subscription migration, cross charge migration, bank transfer migration).
- Points where I got put on other work (feature development/ bug fixes) due to insufficient time from Jack King despite apps being completed. Pushed finish date back by 2 months.
### What would I do differently?

### Lessons Learned

### Area for Improvement