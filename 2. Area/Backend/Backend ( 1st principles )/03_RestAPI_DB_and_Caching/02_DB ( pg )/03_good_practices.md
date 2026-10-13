---
tags:
  - BFFP
  - good_practices
  - thinking
---


## 1. : we can make two tables  , users and users profile 

- users : imp chiz like id , password , createdat 
- user_profiles : one to one relation hoga users table se and isme jo bhi profile ki chize hoti hai wo rkh skte hai 


##### Benefit is : scalable as main users table change nai krna hai generally 



## 2. in pg db , use plural  + small letters + _  sign to name the tables 

- users 
- fullName   -> full_name




## 3. Imp of referential integretiy ..  ( cascade , restrict , null , default )

- users table
- projects table ( on delete restrict)

```
so whenever user is set to delete it will check if there are any projects with this user in it , if yes do not allow user to be deleted until there is entry in projcets table
```



## 4. Separate migration for seeding data ( test ke liye data )





### 5. General thumb rule for putting an index :-


- first check kitne baar query ho rha hai , performance hit aa rha hai kya etc etc

-  field is involved in :
		- join condition
		- where clause
		- sort clause