---
tags:
  - thinking
  - backend
  - assignment
  - actualLearning
---


```
Saare routes mai verifyJWT lgaye coz .. login user hi chahaiye 
```


## ==jab bhi id se match krana ho .... tab direct userId bhjne se nai hoga i.e.==
```js
{
      $match: {
        _id: userId,
      },
},
```

## **We have to pass the actual pura mongoDB ka ID .. and ye mongoose kr dega**
```js
{
      $match: {
        _id: new mongoose.Types.ObjectId(userId),
      },
},
```




# Task1 :-  Create a tweet 

### 1. get the content and check it 
### 2. get the userId from req
### 3. create a tweet 
### 4. check for errors 
### 5. return the res 


# Task 2 :- Delete a tweet

### 1. get the tweetId from params 
### 2. handle for null and validID hai ya nai check 
### 3. delete the tweet 
### 4. handle for error
### 5. return res


```
delete and update mai ek point aur hai ki ... koi aur user jo login ho and usko tweetId pata ho dusre ki to update kr skta hai , so to stop this .. we will use findOneAndUpdate method jisme owner bhi pass krenge to verify owner hi update krega !
```


# Task 3 :- Update Tweet

### 1. get the new content  from body and tweetId from params
### 2. check for null and valid ID
### 3. findByIdAndUpdate .. 
### 4. handle errors for wrond userId or any db failure
### 5. return res 


# Task4 :- Get user tweets 

###  1. get the the userid 
### 2. check for valid ID 
### 3. aggregate pipeline 

- get the user doc from "users"  
- lookup tweets ka jisme owner == userId
- jo details chahiye wahi rkho baaki saari hata do 

### 4. Check for null 
### 5. return the whole thing jo pipeline se aayi







