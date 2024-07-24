---
created: 2024-07-24 08:02
tags:
  - DailyNotes
  - MoreTrees
  - Sprint2
---



#  Wednesday, July 24, 2024

<< [[Timestamps/2024/07-July/2024-07-23-Tuesday|Yesterday]] | [[Timestamps/2024/07-July/2024-07-25-Thursday|Tomorrow]] >>

---
---
### 📅 Wake Up
##### 🙌 One thing I'm excited about right now is...
- Progressing onto migrating the Brand Cross Charge plantation and payment history data.

##### 🚀 One thing I plan to accomplish today is...
- Getting the bug fix for correctly updating the `account_credits` table when planting by card in a production-ready state for Thursday 10AM.

---
---
# 📝 General Notes
---

## Block One
#### What I plan to do
- Review all outstanding PR review requests.
#### What I accomplished
- Reviewed the IPMORE-787: Add JMS SSL support PR for transaction management service, notification management service, and user management service.
	- Investigated the AMQ Connection factory, and asked questions surrounding optimal parameters.
- Reviewed the IPMORE-755: Hash users external API key PR.
	- Investigated how the new method of storing and validating API keys works.
	- Asked a question on proper function functionality and naming.
- Reviewed the IPMORE-755: Hash api key for external controller PR
	- Voiced my concern about putting hashed API keys in the URI of a get request and proposed an alternative solution.
#### Notes
- To improve my understanding of the code base I am spending a longer amount of time reviewing PRs and investigating the entire area of code surrounding the changes.
---
## Block Two
#### What I plan to do
- Work on stripe subscription migration app.
#### What I accomplished
- Worked on the stripe subscription migration app:
	- Validating the legacy DB subscription payment transactions that have no stripe invoice ID (they were auto-top-up payments)
	- Create the models for reading in the Account Subscription inserts from the cache
#### Notes
- N/A
---
## Block Three
#### What I plan to do
- Work on making the changes requested for the bug fix for correctly updating the `account_credits` table.
#### What I accomplished
- Worked on making the changes requested for the bug fix for correctly updating the `account_credits` table:
	- Refactoring the `account_credits` table update.
	- Refactoring failing tests (lots!).
	- Simplifying parameter passing.
#### Notes
- N/A
---
## Block Four
#### What I plan to do
- Test the changes made to the bug fix for correctly updating the `account_credits` table.
#### What I accomplished
- Test the changes made to the bug fix for correctly updating the `account_credits` table.
	- Tested locally.
	- Deployed to DEV environment and tested.
	- Deployed to UAT environment and tested.
#### Notes
- I worked extra late today (2 hours).

---
---
### 📅 Wind Down
##### 🙌 What did I achieve today
- Dev and UAT tested the bug fix for correctly updating the `account_credits` table in preparation for the release tomorrow.

##### 🚀 How did I struggle today
* I struggled updating and validating failing unit tests a little bit.

---
---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("2024-07-24") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("2024-07-24") SORT file.mtime asc
```