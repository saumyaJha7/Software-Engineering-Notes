---
tags:
  - next
---

https://chatgpt.com/share/69b562b7-bb4c-800f-9b78-523474765291


## 1. Simple fetch : request db each time 

```js
const response = await fetch("http://localhost:3000/api");
```


## 2. Next js fetch :- 

- can cache ( store the response )
- can re-validate 



```js
const response = await fetch("http://localhost:3000/api", {
    cache: "force-cache",
    next: { revalidate: 60 },
});
```



### Cache it for next requests ... and after every 60  seconds fetch automatically and cache it again for further next req


#### read about cache-tag for revalidation in between that time 





## Not found : https://nextjs.org/docs/app/api-reference/functions/not-found



