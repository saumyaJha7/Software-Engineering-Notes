---
tags:
  - redis
  - caching
  - backend
  - DB
---

## There is an important concept in redis called TTL , time to live... it is used for building otp verification api's



![[Pasted image 20260901213228.png]]



## Some imp things about ttl :-


- set krte time ek params pass krna hota hai 
- also prod systems mai we can also store .. attemps , maxAttemps etc 

eg :- 

```
otp
attempts
maxAttempts
createdAt (sometimes useful)
lastAttemptedAt
```




