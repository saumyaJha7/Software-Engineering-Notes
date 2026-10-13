---
tags:
  - sd
---
```
Databases are most critical component of any system.
They make or break a system.

// if you solve the db prblm , more than half of ur problem is solved.
```


## The main two reason relational db's are used is :- 

#### a.  relational db's provides us "transactions" ( it is atomic unit of work )

#### b. they provide ACID properties .

- nd ofc relations + joins 





### 1. Atomicity 
		- all statements within the transaction takes effect or none.
		- "sb hoga ya to kch nai hoga"


## 2. Consistency 
		- After a database operation, the database remains in a valid state according to all the rules/constraints defined for it.

- eg let say a bank has total money : 1000rs ( A has 200 nd B has 800 )
- now after a db operation there are different possibilities , like A may got 200 rs so system becomes A-400 nd B-600 
- whatever PnC , but total amount will be 1000 only.
- also rule ye bhi hoga hi ki negative nai ho skta so it can't be 
- that is consistency ( check constraints , fk constraints , cascades )
- ==After any successfully committed transaction, the database must be in a valid state.==



## 3. Isolation
		- concurrent transactions should behave correctly without improperly interfering with each other.



## 4. Durability
			- Durability means that once a transaction is successfully committed, its changes are permanently preserved, even if the database crashes afterward.


```
Transaction
    ↓
   COMMIT
    ↓
💥 Database crashes
    ↓
Database comes back
    ↓
Changes are still there ✅
```


# So in short , ACID is :- 

```
A → All or nothing
C → Valid state
I → Transactions don't improperly interfere
D → Committed changes survive
```






