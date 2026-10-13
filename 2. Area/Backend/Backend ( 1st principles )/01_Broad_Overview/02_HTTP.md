---
tags:
  - theory
  - http
  - backend
  - BFFP
  - server
---

## Q. What is http ?
## Ans. It is protocol used in sending or receiving hyper-texts.


## Two main points about it :- 

### 1. It is stateless 
- no data/memory of previous req
- therefore each http req carry all the neccessary info each time for server to process it .
- ( hence we need state to remember like cookie or tokens etc )

### 2. Client server Architecture 
- client sends the req and then only server sends the response .



## Now there is something called headers which is sent by both sides 


### Headers : It is meta data ... data about data 

- kaha bhjna hai 
- kab req aaya 
- kon req kiya 
- kaha se req kiya 
- http method 
- content type 
- etc etc


### - Headers are sent when client sends the req and also when server responds 
	- Req headers : user-agent , authorization , cookie ( hepls server understand about client's env , preferences etc )
	- Res headers : 

	- General Headers : Date , Connection , Cache-Control 
	- ( more type of headers like security headers etc )


#### Headers are like amazon parcel ke upar jo likha hota hai wo ( details about both parties ) in order to reach the destination correctly and meanwhile the actual payload is inside ( encrypted ).



## Q. Idempotent vs Non-Idempotemt ?

### Ans : What happens when you repeat the same request multiple times .


#### 1. Idempotent methods : baar baar req krne se bhi result same aaye 

- GET , PUT  , DELETE 
- result stays the same -> Idempotent 


##### 2. Non - Idempotent : ...... result varies 

- POST , PATCH ( usually )
- difference result each time -> Non Idempotent


## Q. Why it matters ? 
### Retry logic ( eg. network failure )
- Idempotent methods : Safe to retry 
- Non - Idempotent : might create duplicates 


