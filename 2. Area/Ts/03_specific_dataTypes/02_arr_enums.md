---
tags:
  - ts
---


## 1. readOnly arrays

```ts
// 1. readOnly arrays

let users: readonly string[] = ["u1", "u2"];

users.push("u3"); 

// this will give error 
```

## 2. tuples


```ts
let demoTuple: [string, number];

demoTuple = ["demo", 23];

// demoTuple = [23, "demo2"];   // error coz order
```

## 3. enums 

- to restrict the user choice 

```ts
enum CupSize {
  SMALL,
  MEDIUM,
  LARGE,
}
const size = CupSize.MEDIUM; 


enum orderStatus {
  PENDING = "pending",
  RECEIVED = "received",
}
  
const status = orderStatus.PENDING;
// status = "pending"
```