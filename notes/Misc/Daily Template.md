---
created: <% tp.file.creation_date() %>
tags:
  - DailyNotes
  - MoreTrees
  - Sprint2
---



#  <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

<< [[Timestamps/<% tp.date.now("YYYY", -1) %>/<% tp.date.now("MM-MMMM", -1) %>/<% tp.date.now("YYYY-MM-DD-dddd", -1) %>|Yesterday]] | [[Timestamps/<% tp.date.now("YYYY", 1) %>/<% tp.date.now("MM-MMMM", 1) %>/<% tp.date.now("YYYY-MM-DD-dddd", 1) %>|Tomorrow]] >>

---
---
### 📅 Wake Up
##### 🙌 One thing I'm excited about right now is...
- 

##### 🚀 One thing I plan to accomplish today is...
-  

---
---
# 📝 General Notes
---

## Block One
#### What I plan to do
- ...
#### What I accomplished
- ...
#### Notes
- ...
---
## Block Two
#### What I plan to do
- ...
#### What I accomplished
- ...
#### Notes
- ...
---
## Block Three
#### What I plan to do
- ...
#### What I accomplished
- ...
#### Notes
- ...
---
## Block Four
#### What I plan to do
- ...
#### What I accomplished
- ...
#### Notes
- ...

---
---
### 📅 Wind Down
##### 🙌 What did I achieve today
- 

##### 🚀 How did I struggle today
* 

---
---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc
```