---
tags:
  - theory
  - ReST-API
  - BFFP
  - backend
  - api
---

## Some stds :- 


#### 1. versioning :  /v1 ,  /v2
#### 2. resources in plural  :  /v1/books
- even though one book is req  :  /v1/books/:bookId

#### 3. space =>  -      and   capital => small 
- Carl Sagan  =>  /books/carl-sagan

#### 4. Whenever there is other then basic CRUD work ( custom actions ) , we should use ==POST== method 
- eg : POST /send-email 


	


## Q. What is idempotency ?  
### Ans. Same output / state in db despite the number of time any API is called . 

- Idempotent : get , put , delete 
- Non-Id : post  

##### Resources : https://restfulapi.net/idempotent-rest-apis/





