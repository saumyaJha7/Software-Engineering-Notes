---
tags:
  - theory
  - backend
---


## 1. server bhi chahiye .. and as soon as app load ho chahiye .. just like db connection ( ==koi bhi async await fn promise return krta hai to , server start kr skte hai connect db success hua to==)

```
also extra event listeners bhi add kr skte hai ... like for errors etc app.on() krke .
```



## 2. kch middleWares are surely needed for config and accepting the data in different ways ( json , file ya url etc) such as :- 

- cors : sirf frontend ka specific dena hota hai .. jab hosted ho toh , but abhi bas all kr rha . ==cors error are resolved in backend by allowing specific frontend routes only==
- express.json() : for accepting json data 
- express.urlencoded() : for accepting query params 
- express.static() : for accepting temp photos , favicons etc .
- cookieParser() : for setting up and reading cookie in the client's server .




## 3. To Standardise the api response ( ==whether it is success or failure==) , in order to provide structure and reliability to the devs ... we create a class and use that to return the response .



## 4. AsyncHandler : [[why asyncHandler fn]]


```
ye wrapper fn can be used for middleWares as well ... isliye params mai err,req,res,next charon le skte ho .
```







