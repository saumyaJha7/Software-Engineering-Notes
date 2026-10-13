---
tags:
  - react
---


## Suppose we have a message app and msg counts inc :- 


#### how it will be done in js :- 

![[js_state_manage|900]]




- manually grab the ele 1 refn
- update it 
- same for jitne bhi ele hai 
- suppose 10 ele hai , dusre dusre page mai to complicated ho jyga 




## Now how reacts solves this is :- 


![[React_state|900]]




#### In react , one main point is there :- 

- UI = fn(state)
- just update the state , react khud se manages the UI 



### And wahi react ka spcl variable is declared and set with the help of a hook called useState 


- the spcl variable are always declared inside the fn 
- but outside of the return statement 





# One imp question :- 



#### setCount bhi ek callBack leta hai in real use , ham bas uska short hand notation likhte hai 


```js
// actual syntax
setCount( (prevValue) => prevValue + 1 );

// shortHand notation
setCount(count + 1);
```



### Both works the same usually but difference comes in some case like :- 



- let say count = 10 

```js
setCount(count+1);
setCount(count+1);
setCount(count+1);
```

- this will give output as ... count = 11


```js
setCount((prev) => prev + 1);
setCount((prev) => prev + 1);
setCount((prev) => prev + 1);
```


- this will output , count = 13