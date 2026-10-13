---
tags:
  - DB
  - mongo
  - backend
  - code_notes
---


## We have to connect the db instantly our code loads  , so  to connect db we have two ways :- 

1. Write the db connection ka code in index.js file ( coz wahi entry point hai )
2. Write the code elsewhere and import it in the index file -> **more better approach**



## Approach 1 :- 

1.  index.js mai hi fn likho ( directly/IIFE dono ok , but IIFE makes more sense )
#### For revision : [[IIFE]]

2. async await + try-catch ke sath likho 
3. app bhi initialise krke , listen krwalo 

# Take :- 
- Good approach , sb IIFE ke andar hai to pollute nai hoga global env etc , but main point is ==index file mai bhut kch likh diya== , code is not modular .






## Approach 2 :- 

1. db folder mai function likho and sirf index file mai execute kra do!

## Take :-
	- code modular ho gya 
	- index file clean ho gyi 





# Some points I noticed to be followed for good practices :- 

1. always write clean and modular code .
2. extra checkings at each variables with ==precise error message== helps debugging very faster.
3. whenever there is an error in connecting to DB , exit the process ( read more abt this method in node).




