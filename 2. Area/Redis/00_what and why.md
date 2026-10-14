---
tags:
  - redis
  - backend
  - caching
---

```
Note : DB's are evolving so much ... and line blur hote ja rhi hai .. like we can use pg as well for caching .. 
```


## Q. What is redis ? ( Remote dictionary server )
### Ans :- It is an in-memory db i.e. it stores the data in the RAM not in disk that's why it is super fast as RAM is directly accessible to CPU .

- also RAM ka naam hi random access memory hai means , koi bhi location p data read krne ke liye almost same time lgta hai 
- used where frequently asked record ( hot record )
- jaha data frequently change nai ho rha like profile details etc  


## Q. why is redis ?
### Ans :-  harr req p db call nai krna pdega so fast 

#### common use cases : 
- cache
- session management 
- OTP storage 
- rate limiting 
- queue and pub-sub

![why redis](../../excalidraw/why%20redis.png)




# Ultimate source of truth is always a db .. redis app ko fast krne ke liye jo record baar chahiye unko jldi serve krne ke liye hai .




## But also redis helpful hai ofc in many scenarios like 


1. bhut saare users aayege sale wale din to server toh horizontally scale kr diye par db to bottleneck bn gya n ( we can use db sharding ya replication but let's say ek hi db rkhna hai ) tb redis will fasten the process 
![case where redis shines](../../excalidraw/case%20where%20redis%20shines.png)


## IT IS NOT THE SOLUTION TO EVERY PROBLEM .. understand the problem .. 

		( always check these things ... MAY BE redis will help here  )
- read pressure reduce karna hai ( non volatile hot data )
- expirable temporary data store krna hai kya  ( like tokens , otp's etc )  
- any shared things betn difn servers ( like rate limiting counter , blackListing users , page views , likes  etc ) 
- bg jobs ( email queues etc )


( possibly ho skta hai redis use ho ... understand the pain point clearly )