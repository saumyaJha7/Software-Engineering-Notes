---
tags:
  - sd
---
 
 we have 4 diffn lvls of isolation 

- **transaction isolation levels** define **how much one transaction is isolated from the changes made by other concurrent transactions**.

		a. READ UNCOMMITED : t2 can read uncommited changes of t1.  ("dirty read")
		b. READ COMMITED : t2 can only read commited changes of t1. 
		c. REPEATABLE READ : Once a transaction reads a row, subsequent reads of that row return the same value within that transaction. 
		d. SERIALIZABLE :  Transactions may execute concurrently, but the database prevents their operations from producing a result that could not happen if the transactions had run one after another.	
	- every read is a blocking read 
	- nd while one txn reads , others will have to wait.

```
A and B can execute concurrently
       ↓
If they don't conflict → both can proceed
       ↓
If they conflict → database coordinates them
       ↓
       ├── block one
       └── OR abort one
       ↓
Result is equivalent to serial execution
```




![[sd_isolation_levels|900]]



### So the fundamental trade off is ,

```
How much consistency do I want vs. how much concurrent work do I want?
```