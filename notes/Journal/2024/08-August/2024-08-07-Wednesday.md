---
created: 2024-08-07 07:59
tags:
  - DailyNotes
  - MoreTrees
  - Sprint2
---



#  Wednesday, August 07, 2024

<< [[Timestamps/2024/08-August/2024-08-06-Tuesday|Yesterday]] | [[Timestamps/2024/08-August/2024-08-08-Thursday|Tomorrow]] >>

---
---
### 📅 Wake Up
##### 🙌 One thing I'm excited about right now is...
- Finishing running the app fixing the pre-launch migrated user created_when dates.

##### 🚀 One thing I plan to accomplish today is...
-  Developing the endpoint for hashing the API keys encrypted using the UAT AES.

---
---
# 📝 General Notes
---

## Block One
#### What I plan to do
- Work on the ticket for hashing the API keys encrypted using the UAT AES salt and password in production.
#### What I accomplished
- Worked on adding the endpoint for hashing the API keys encrypted using the UAT AES salt and password in production
	- Got the core changes done.
#### Notes
- N/A
---
## Block Two
#### What I plan to do
- Re-work the changes adding the endpoint for hashing the API keys encrypted using the UAT AES salt and password in production
#### What I accomplished
- Standup
- Re-worked hashing the encrypted API keys by re-using existing functionality so change is much smaller.
- Investigated why the number of API keys to encrypt has increased by 7 since the original hashing of API keys:
	- Reasoning: `The user we tested previously had a user status 0, but they also had no plantations in the account ledger - meaning they did not fit the criteria to have their API key hashed. However, they have now activated their account (user status 1), so they would now fit the criteria to get it hashed if we were to run it again`
	- Proposed solution: Ignore those newly identified users if they aren't encrypted using UAT AES salt and password as they were originally going to be left out and have no plantations anyway.
#### Notes
- ...
---
## Block Three
#### What I plan to do
- Prepare the changes adding the endpoint for hashing the API keys encrypted using the UAT AES for merge into develop
#### What I accomplished
- Prepared the changes adding the endpoint for hashing the API keys encrypted using the UAT AES for merge into develop
	- Updated helm secret chart 
	- Added UAT AES salt and password secrets into DEV vault and PROD vault.
	- Merged in the environment variables updates in `mt-deployment`.
	- Merged the changes adding the endpoint for hashing the API keys encrypted using the UAT into develop.
	- Tested the endpoint in the dev environment.
- Reviewed CAB for the hash api key release.
#### Notes
- N/A
- 
---
## Block Four
#### What I plan to do
- Work with Jack King on the app updating the created_when date of pre-launch migrated users.
#### What I accomplished
- Reviewed the PRs for [IPMORE-817](https://thehut.atlassian.net/browse/IPMORE-817).
- Started UAT testing of the app updating the created_when date of pre-launch migrated users.
	- Found an out of bounds issue when updating account_users (Fixed next day).
#### Notes
- N/A
---
---
### 📅 Wind Down
##### 🙌 What did I achieve today
- Prepared the changes adding the endpoint for hashing the API keys encrypted using the UAT AES for release (skipped UAT due to secrets being handled differently).

##### 🚀 How did I struggle today
* N/A

---
---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("2024-08-07") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("2024-08-07") SORT file.mtime asc
```