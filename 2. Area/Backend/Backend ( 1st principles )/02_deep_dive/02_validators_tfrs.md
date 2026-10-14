---
tags:
  - BFFP
  - backend
  - server
  - security
---
![handler_service and repo flow](../../../../excalidraw/handler_service%20and%20repo%20flow.png)

## Example of tfrs are :- 

- like nickname optional hai so agar user ne nai diya to by default can send person's firstName as nichname.
- username all in lowercase db mai


### Validators :-    ==“Is the data valid?”==

- for checking the validity of data before proccessing it or storing it ( so that code phate n )
- it is done so that db mai sahi store ho , app crash na ho 
- eg : email format , age >= 18 , required fields must be there etc 


##### Three types of validations :- 
- Syntactic : email => --@---.--- ( yahi format ) ya phone => -- ----
- semantic : age ( < 0 ) , dob ( future mai ni)
- type : age = number 

### Transformations :-  ==_“Convert data into the right shape”_==

- to change the incoming data into format our app wants .
- eg : "42" -> 42 or trim krna etc
- another eg : by default query params are in string  , but we want to change it to number  


## example :- 

```js
router.put(
  "/users/:id",
  validateUserId,
  updateUser
)
```




