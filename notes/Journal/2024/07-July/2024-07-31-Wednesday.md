---
created: 2024-07-31 11:39
tags:
  - DailyNotes
  - MoreTrees
  - Sprint2
---



#  Wednesday, July 31, 2024

<< [[Timestamps/2024/07-July/2024-07-30-Tuesday|Yesterday]] | [[Timestamps/2024/08-August/2024-08-01-Thursday|Tomorrow]] >>

---
---
### 📅 Wake Up
##### 🙌 One thing I'm excited about right now is...
- Completing the brand cross charge payment history migration.

##### 🚀 One thing I plan to accomplish today is...
-  Find the cause of the stripe 3DS issue in app runtime.

---
---
# 📝 General Notes
---

## Block One
#### What I plan to do
- Investigate the Stripe 3DS issue
#### What I accomplished
- I found that the stripe 3DS issue is caused by a [TLS error](https://support.stripe.com/questions/webhooks-how-to-investigate-and-fix-tls-error).
- Updating the ip Allow List for the dev app runtime environments to the possible [web hook IP CIDRs](https://docs.stripe.com/ips?locale=en-GB) did not fix the issue.
#### Notes
- N/A
---
## Block Two
#### What I plan to do
- Continued testing the dev app runtime environment
	- Created tickets on the outcome of the dev app runtime test.
- Updated the test plan
#### What I accomplished
- Finished testing on the dev app runtime environment:
	- Created tickets for fixing the stripe TLS error and fixing the external endpoint requiring access token authentication bug.
- Updated the test plan:
	- Added admin assign credits section.
	- Added external endpoint section.
#### Notes
- N/A
---
## Block Three
#### What I plan to do
- Pair program with Jack Owen on dev app runtime TLS issue.
#### What I accomplished
- Pair programmed with Jack Owen on dev app runtime TLS issue.
	- We found that the environment is missing the R11 Lets Encrypt certificate which is causing a break in the certificate chain.
	- We have posed a question in the app runtime chat and waiting on a response.
- PR review with Jack and Jonny on the data migration in user management service.
- Pair programmed on resolving the issue with the config.yaml not being updated in the project management service UAT workflow.
#### Notes
- N/A
---
## Block Four
#### What I plan to do
- Add unit tests to the stripe subscription migration app.
#### What I accomplished
- I have added tests to the stripe subscription migration app for classes:
	- `GeneralUtilityTest`
- I have spent a lot of time trying to work around mocking static methods and static member variables which I needed to learn power Mockito.
#### Notes
- N/A

---
---
### 📅 Wind Down
##### 🙌 What did I achieve today
- Identified the stripe 3DS issue in app runtime, and escalated the issue with the app runtime team so that we can get the R11 certificate added to the certificate chain.

##### 🚀 How did I struggle today
* N/A

---
---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("2024-07-31") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("2024-07-31") SORT file.mtime asc
```