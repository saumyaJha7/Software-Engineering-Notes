---
tags:
  - auth
  - BFFP
  - backend
  - thinking
---
# ==Generally the industry suggestion is to go with auth provider like better-auth ==

-  khud ke liye project bna rhe to implement khud ka may be but in big apps provider works 


## Q. What is Authentication ?
### Ans. Who are you wrt to our system. ( ==Identity==)



## Q. What is Authorisation ?
### Ans. What can you do. ( ==Access==) 
- you cant reset anyone else's password ( not authoried to do )




## Q. Problem ?
#### Ans. HTTP is stateless therefore harr barr login krna pdega with details . 



# Q. Solution ?
## Now there are different types of authentication :- 

### 1. Statefull Auth 
- Server stores the sessions 
- session tokens based auth 
- good thing : high security + full control ( revoking any user )
- bad thing : scalability issues coz db m kitne logo ka store kroge  + latency + multiple servers then how to maintain session
- use case : banks ( places where security matters a lottt )


### 2. Stateless Auth 

#### 2.1 Token based auth ( JWT )
- server does not neccesarily store ( or lookup in db after each req )
- JWT token based auth
- good thing : scalability + instant 
- bad thing : security lapse  ( to overcome it we use hybrid approach ) 


#### "neither is good in all case , depends on situation .. but one way would be to use both depending on the some factor ( read more about it ... case studies may be)"

#### Read here : [[Sessions vs JWT]]


#### 2.2 . API key based 

- easy to use ( just get the apikey and call )
- machine to machine OR backend to backend 
- stateless ( everytime apikey bhji pdegi )
- eg : gpt4.1 ke uske API key ke through apne backend mai uska response lena ( this is api key bases auth i.e. OpenAI ko btana ki konsi machine hai .. ) 



### Delegation based auth :- 

#### What was the problem with stateless : 
- one app wanting resources of other apps like ( Ig wants contact list )
- 100 apps -> 100 passwords  ( alg rkhenge to user ke liye prblm , same rkhega user to security problem )


#### Solution :- 
- central hub and just delegate the headache to them ... wo hamko user kon hai btade 
- trusting third party for auth
- password ki jagah token milega google se chatgpt ko .. and usse wo limited chiz hi kr skta hai hamare data ke sath .. 
- like google password pta hai to sb kr skte hai acc ka , but tokens pta hai to may be sirf contact read kr skte ho ya calender mai kch add kr skte ho BAS 
- eg : google login

##### OIDC : it tells about user kon hai  ( authentication )
##### OAuth ( 2.0 ) : it tells what user can do ( authorization )



##### Gpt convo ( apikey and delegation based auth ) : https://chatgpt.com/g/g-p-6965c66158d88191bf53156a1fd46088-full-stack-overview/c/696a2649-076c-8320-9037-36f7ff6d26b2


### yt video : https://youtu.be/A95rliroC8Q?si=BIKXVP1MPC3oJAYs












