---
tags:
  - js
  - async
  - promises
  - interview
---


## By default js executes the code line by line , i.e. synchronously . ( Single Threaded JS )


```js
console.log("1st log");
console.log("2nd log");
console.log("3rd log");
console.log("4th log");
```



![sync js thread](../../../excalidraw/sync%20js%20thread.png)


## Main thread kya krega ek ek krke task uthayga and execute krega ...  jab tk ek execute ho rha hai tb tk kch aur kaam ni ho skta ...  ==**Blocking Nature**==





![sync js thread flow](../../../excalidraw/sync%20js%20thread%20flow.png)


# Q. What is the problem ?
## Ans : Consider a real world case , we are making an e-comm app and as soon as customer orders any item we have to do these things :- 

- checking the inventory
- creating an order in db
- charging the payment
- send the invoice 


### isme time lgta hai ye sb krne mai to main thread block ho jyga sync mai krenge toh ..

## So always our aim is to free up the main thread taaki apni app block na ho , there comes the concept of async js .

