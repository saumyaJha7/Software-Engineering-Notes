---
tags:
  - theory
  - DB
  - backend
  - mongo
---
# For doubt , visit : https://chatgpt.com/share/691b0294-3c70-800f-b6a8-63255f3ebe9b




```
Dependencies needed :- 

1. dotenv : for env variables
2. mongoose : for talking to mongoDB
3. express : for creating servers 
```


## 1. Project bnao naya and basic yes yes setup kro 

```
bg mai mongoDb aws ( ya jo bhi use kroge as service provider while setup ) pe hi db bnaya and jo bhi krna tha wo kar diya hamare liye , ab jo bhi mongoDB mai krenge , wo bg mai jyga aws mai hi ... kaise wo mongo dekh lega , hame bas mongo tk bhjna hai !
```

## 2. To connect with mongo db , it needs userName , pass + IP address allowed + url  

	1. How to get name,pass and IP is -> go to security quickStart page 
	2. get the userName and password !
	3. select local env
	4. add 0.0.0.0/0 IP i.e. sbko access de do ( read more about it)

# ==Production mai sirf wahi IP enable krte hai jaha backend ka code hota hai , like aws ya digitalOcean ki machine ka ... testing ke liye temporarily krna alg baat hai ==

	1. To get the url -> go to db -> clusters and connect 
	2. alag alag tools hai to connect , we're selecting compass abhi (read more)
	3. copy the uri and change the password 


## 3. Now place all three  details to .env file +  set the db name in constants file and export it  
```
1. MongoDB URI mai ending slash hata dena 
2. Password mai special char avoid krna 
```


# 4. Always remember two things while connecting the db :- 

1. error aa skta hai so ==try catch ya promises== mai wrap kro
2. db dusre continent mai hai .. time lagta  , isliye ==async await== use kro 


## 5. Where to write the function to connect DB  : [[connectDB function]]



## 6. Where to load env variables is : index.js file mai ( entry point ) , because what we want is jaldi se jldi accessible ho jaaye env variables harr jagah , haarrr file mai isliye sbse phli file jo load hoti hai usme hi load krlo.

```
Also one more thing , node phle sb kch import krta hai to db.js mai fn ke bahar env variables accessible nai hai ... there are many ways to solve it but  one way is to access the env variables inside function.
```



