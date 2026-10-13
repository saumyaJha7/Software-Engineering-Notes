---
tags:
  - theory
  - dev
  - server
  - backend
  - http
  - DB
---



## Q. What is API ?
### Ans : An common interface for two softwares to talk to each other ( req the data , get the data etc)



## Q. What is ReST API ?  
### Ans : It is a type of API jo kch architectural principles ko follow krti hai  , such as :-


1. **Client–Server Architecture**
    - The client (like a web app or mobile app) and server (which hosts the API) are separate.
    - The client only handles the user interface and sends requests; the server manages data and business logic.
    - This ==separation== improves scalability and flexibility.
        
2. **Statelessness**
    - Each API request must contain all the information needed to process it.
    - The ==server doesn’t store any session== data about the client between requests , data store krne ke liye db hai .
    - Example: If you log in, your app must send your token on _every_ request — the server doesn’t “remember” you automatically.
        
3. **Cacheability**
    - Responses from the server should define whether they can be cached (to improve performance).
    - Example: Responses can include HTTP headers like `Cache-Control`.
        
4. **Uniform Interface**
    - All interactions between client and server follow a consistent structure.
    - This usually includes:
        - Using ==standard HTTP metho==ds (`GET`, `POST`, `PUT`, `DELETE`)
        - Using resource URIs (like `/users/1`)
        - Returning data in standard formats (often JSON)
        - Using standard response codes (`200`, `404`, `500`, etc.)


