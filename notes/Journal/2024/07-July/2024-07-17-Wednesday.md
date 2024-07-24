---
created: 2024-07-17 09:27
tags:
  - DailyNotes
  - MoreTrees
  - Sprint2
---



#  Wednesday, July 17, 2024

<< [[Timestamps/2024/07-July/2024-07-16-Tuesday|Yesterday]] | [[Timestamps/2024/07-July/2024-07-18-Thursday|Tomorrow]] >>

---
---
### 📅 Wake Up
##### 🙌 One thing I'm excited about right now is...
- Beginning the implementation of the stripe subscription migration app.

##### 🚀 One thing I plan to accomplish today is...
-  Finish UAT testing of the cross charge plantation migration app.

---
---
# 📝 General Notes
---

## Block One
#### What I plan to do
- Implement the stripe subscription app functionality for reading in the stripe data.
- Create UAT MoreTrees accounts for the THG brands with cross charge payments.
#### What I accomplished
- Implemented the stripe subscription app functionality for:
	- Reading in the stripe payment intent data for linking them to stripe invoice data.
	- Reading in the stripe invoice data for linking them to stripe subscription data.
	- Reading in the stripe subscription data.
- Created UAT MoreTrees accounts for all team+{brand}@moretrees.eco accounts.
	- Personal brand accounts were not created in UAT as they would receive sign-up emails.
#### Notes
- N/A
---
## Block Two
#### What I plan to do
- Implement the functionality to link transaction IDs to Subscription Ids for the stripe subscription migration app.
#### What I accomplished
- Whilst developing the stripe subscription migration app I found an issue where migrated payments had the same stripe transaction ID. This requires investigation and resolution.
- Investigated and identified the payments with duplicate transaction IDs.
- Resolved the payments with duplicate transaction IDs by:
	- Identifying the payments with duplicate transaction ID.
	- Ensuring that they only exist once in stripe.
	- Removing the duplicates from the production CockroachDB.
	- Setting the legacy DB payments to migrated = 0.
#### Notes
- N/A
---
## Block Three
#### What I plan to do
- Investigate the payment and plantation discrepancies in the production DB
#### What I accomplished
- Jack and I investigated the payment and plantation discrepancies for accounts in the production DB. This query for finding these was produced:
	- ```
	SELECT COUNT(*) 
	FROM (
		SELECT a.id as account_id, SUM(al.credits) AS credits_bought, ac.credits_loaded,SUM(al.credits) - ac.credits_loaded as difference, credits_loaded - ac.credits_used as balance  
		FROM mt_user.accounts a  
		JOIN mt_transaction.account_credits ac ON ac.account_id = a.id  
		JOIN mt_transaction.account_ledgers al ON al.account_id = a.id  
		WHERE al.transaction_type_code IN ('TRA_BTC', 'TRA_FTC', 'TRA_PLTC', 'TRA_CCTC', 'TRA_BATA'
		)  
	GROUP BY a.id, ac.credits_loaded, ac.credits_used);``` ``
#### Notes
- These findings will be produced to Molly (the product owner) who will decide on what actions need to be taken to reconcile these differences.
---
## Block Four
#### What I plan to do
- Implement the stripe subscription app functionality for calculating the cache inserts for the subscription data and transaction ID to subscription ID map.
#### What I accomplished
- I have implemented the stripe subscription app functionality for calculating the cache inserts for the subscription data and transaction ID to subscription ID map.
- I have implemented the caching functionality so that these inserts are stored in the cache.
#### Notes
- The stripe subscription migration app functionality still needs unit tests written and some refactoring 

---
---
### 📅 Wind Down
##### 🙌 What did I achieve today
- Fixed an issue with duplicate payments stored in the legacy DB being brought forward to the production DB.
- I have implemented the stripe subscription app functionality for calculating the cache inserts for the subscription data and transaction ID to subscription ID map.

##### 🚀 How did I struggle today
* There was an unexpected issue with duplicate payments stored in the legacy DB being brought forward to the production DB. This took my priority so less time was spent on migrating the cross charge payment history data.

---
---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("2024-07-17") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("2024-07-17") SORT file.mtime asc
```