---
tags:
  - ts
---


## Q1. What is union ?

### Ans : Mulitple options for data types ( also khud ke bhi data types de skte hai )


```ts
let orders: string | number = "1234";
orders = 1234;

let userStatus: "active" | "inactive" = "active";
userStatus = "inactive";
// userStatus = "pending" // error
```



### Q2. What is any ?

### Ans : Kabhi kabhi ho skta hai ki we don't know kya data type ayga in api call ya whatever to we use any ( explicilty bhi bta skte hai ya by default bhi wahi rhta hai if variable not initialised )

```ts
// this will give error 

let users = ["10", "12"];
let isUserPresent: boolean;
for (let user of users) {
  if (user === "10") {
    isUserPresent = true;
    break;
  }
}
console.log(isUserPresent);


// this will work 
let users = ["10", "12"];
let isUserPresent: any;   // or just let isUser;
for (let user of users) {
  if (user === "10") {
    isUserPresent = true;
    break;
  }
}
console.log(isUserPresent);
```