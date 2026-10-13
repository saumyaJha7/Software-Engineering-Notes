---
tags:
  - code_notes
  - aggregate
  - backend
  - mongo
---


# Detailed theoritical convo : https://chatgpt.com/share/6937f689-bca0-800f-b6d1-ec99b51fdf5f



## Q. What is aggregation pipeline ?
### Ans. It’s a way to run data through a series of “steps” (stages) where each step transforms the documents, like a data-processing pipeline.


## Q. Why to use it ?
### Ans. Jab Complex / multiple things jab perform krne ho data p and , hamare server pe laake kr skte hai but better is ki mongoDB sb kre aur sidha resulted data bhje after series of operations.



## Practice of aggregation pipeline : https://chatgpt.com/share/693800ee-3f7c-800f-ba11-360149cc4255




# So how to get the subscribers and subscribed channels for a given user ( getProfile controller ) :- 



### 1. url mai jo username hai usko match kro user collections mai 
### 2. uss user ke subscribers ke docs join kro
### 3. uss user ne kitne subscribe kiye hai usko join kro 
### 4. add kro field ... subscribers and subscribedTo ka count and isSubscribed
### 5. subscribers and subcribedTo ka count = size of subscriber and subcribedTo array field jo lookup ki hamne 
### 6. isSubscribed : req.user._id hai kya subscribers mai 
### 7. jo jo jruri hai sirf wahi project krdo 



```
iss moment pe pura user ka collections hai jisme saare individual docs hai 
```
- **User ke pure collection se match krlo wo user doc jiska userName url mai ho ( req.params )**
```
iss step mai .. sirf ek doc hai user ka jo match krta hai 
```
- **join kro wo saare subscription model jisme channel match kre hamare doc ke userId se**
```
wo saare docs subs model ke jisme channel hamara hai .. 
```
- count the number of subs docs  using size of operator and add a field iske naam se.
```
hamara jo bhi user tha , uske subscribers ka count mil gya .. 
```


#### Now to get how many channels that user has subscribed :- 

- lookup aise subs doc jisme subscriber === _id  of the user !


## Also subscribe ho ya nai ye bhi check krna pdega .. 

- scenario ye hai ki ek user hai ( saumya ) wo yt chala rha hai and 
- wo endpoint hit krta hai yt/chaiaurcode ... to hamko kya kya dikhana hai 
- basic to mil jyga name , coverImage , avatar etc 
- subscribers kitne hai , kitno ko subcribe kiya AND maine subs kiya hai ya nai
- kiya hai to button mai subscribed likha hua dikha do 
- ni to , subscribe red collor mai dikha do 



#### So how to do it is :- 

- hamare pass docs joined hai pure .. 
- so ye check krlo ki chaiaurcode ke subscribers mai mera Id hai ki ni 
- mtlb jo subscribers ka array hai usme jo user log in hai uska id hai ki ni 