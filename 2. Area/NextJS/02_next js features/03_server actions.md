---
tags:
  - next
---


## https://chatgpt.com/g/g-p-6965c66158d88191bf53156a1fd46088-full-stack-overview/c/69b57485-2bcc-8320-9ab9-8e6a0cd898c9


## https://nextjs.org/docs/app/getting-started/updating-data





## it's like tRPC ... directly call server fn from react components that eliminates api routes .

### best for form submissions , button mutation 


```js
"use server"
```



# ==Normal api banke bhi kr skte ho and ye bhi ek tarika hai==


### Normal flow :- 

- client  ->  fetch  ->  /api/route  -> database  -> json response to client


### With Server Actions :-

- client/component  ->  Server Actions ( fn )  -> database  -> response 

