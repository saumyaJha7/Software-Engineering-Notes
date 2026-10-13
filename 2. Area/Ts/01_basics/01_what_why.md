---
tags:
  - ts
---

## Q1. Why we need TS ?
### Ans : Js mai types nai hai 




## Q2. What is TS ?
### Ans : Js with additional powers such as types 



![[why_ts|900]]




```js
function greet(name){
	return "Hello " + name;
}

greet("saumya");
greet(23);

// Consistency issue!
```



```ts
function greet(name: string):string{
	return "Hello "+name;
}

greet("saumya");

// this will give error khud se 
// greet(23);
```