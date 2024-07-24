---
created: 2024-07-10 08:12
tags:
  - DailyNotes
  - MoreTrees
  - Sprint2
---



#  Wednesday, July 10, 2024

<< [[Timestamps/2024/07-July/2024-07-09-Tuesday|Yesterday]] | [[Timestamps/2024/07-July/2024-07-11-Thursday|Tomorrow]] >>

---
---
### 📅 Wake Up
##### 🙌 One thing I'm excited about right now is...
- Getting prepared to run the legacy DB payment history migration in production.

##### 🚀 One thing I plan to accomplish today is...
-  Successfully showcase my SMART goals to Jack Owen.

---
---
# 📝 General Notes
---

## Block One
#### What I plan to do
- Prepare for SMART goal showcase meeting with Jack Owen.
- Perform official UAT testing of the legacy DB payment history migration with Jack King.
#### What I accomplished
- Prepared for SMART goal showcase meeting with Jack Owen.
- Began UAT testing with Jack King. #JackKing He only spent minimal time UAT testing together (which required him) due to apartment issues.
#### Notes
- Frontend of the Lift app is not working correctly. The device won't reload when changes are made to the code.
- Issue Found with Payment History where converted amount doesn't line up with amount.
---
## Block Two
#### What I plan to do
- Investigate the suspicious payments made by legacy user ID 4636.
- Investigate and find any other suspicious payments that aren't already excluded by the known edge cases.
- 1-to-1 with Jack Owen
#### What I accomplished
- The legacy user ID 4636 has 3 suspicious payments which have a 99.9% discount, 99% discount, and 80% discount.
- No other payments are found to be suspicious, this has been confirmed by finding all payments where the price paid in stripe compared to the credits received is greater than a 50% discount (the platform only allowed 50% discounts).
- 1-to-1 with Jack Owen went badly, he wasn't impressed by my presentation.
	- He wants an extensive list of what was achieved throughout these SMART goals and what benefit they provided to the More Trees team.
#### Notes
- N/A
---
## Block Three
#### What I plan to do
- Perform UAT testing with Jack King.
- Confirm decision with Jack King on how the suspicious payments should be handled.
- Proceed with development on the cross charge payment history migration app functionality.
#### What I accomplished
- UAT testing was carried out successfully.
	- All users tested had their payment amount and credits received totals migrated correctly.
	- The users were able to view their payment history on the More Trees site successfully.
	- The users were able to view their payment history invoices the More Trees site successfully.
- The legacy user ID 4636 has payment IDs (88238, 88298, 88330) and credit balance corrected in the old DB.
	- When this user had their payment history migrated in UAT, all their payments are now migrated as they reflect stripe correctly.
- Updated the models required in the cross charge payment history migration app functionality to reflect the need for invoice numbers to be generated automatically. This allows invoices to be viewed as they will not be null.
#### Notes
- N/A

---
---
### 📅 Wind Down
##### 🙌 What did I achieve today
- Fully locally tested and UAT tested the legacy DB payment history migration app functionality ready for running in production tomorrow.

##### 🚀 How did I struggle today
* I felt inadequate in front of Jack Owen during my 1-to-1. I feel as if despite me putting in all my effort during the working day, my objectives that are done outside working hours are suffering. This is then used as evidence in my review which then works against me.

---
---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("2024-07-10") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("2024-07-10") SORT file.mtime asc
```