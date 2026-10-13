---
tags:
  - theory
  - thinking
  - backend
---
```
standard practice hai ki agar api bana rhe hai to naam bhi vaisa hi de route ka with verioning so ... 

"/users"  ->  "/api/v1/users"
```


## 1. badi problem ko chote-chote step mai baatiye ... and solve individual sub problems ( that is why plan is imp )


## 2.  controllers mai logic likhna hai ... wo fn jisme saara kaam likha hai .  
```
yaha async handler ka use kr rhe hai .. kyuki wo ek higher order fn hai to usme core logic likha hua fn pass kr rhe hai .. async await .. try catch wo lga lega.
```

## 3. routes folder  mai define krna hai ki iss route pe , ye wala fn chala do.

```
routes are created with the help of express Router .. which is a fnality of express js whose job is to manage routes and controllers .
```


## 4. app.js / server.js mai sirf itna bta do ki "/users" pe req aayi to control .. userRouter ko pass krdo .. iske aage ke req usme hai .

```
sirf userRouter import kro and jo sub url hai "users" usme sidha userRouter ko control dedo bas.
```









