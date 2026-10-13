---
tags:
  - backend
  - pg
---

## Q. Problem ?
### Ans.  let say 10k entries hai student ki , and koi ek student chahiye to pura O(10k) search lgega .



## Q. Solution -> indexes ? How ?
### Ans. Ek ds mai index and uske corresponding row ka pointer rkhlo 


#### Benefits ?
- saari row ni search krni hai , sidha index se usi row mai phucho 
- Indexes make queries **much faster**, especially on large tables.
- Indexes works best when there are certain constraints such as :- 
		- where 
		- join 
		- group by 
		- unique 
		- etc


## Trade offs :- 

- Slower insert and update : index bhi to update krna hai 
- extra disk space



# **Rule**: Index read-heavy, filter-heavy columns — not everything.





