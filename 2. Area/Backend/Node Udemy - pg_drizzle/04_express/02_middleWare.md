---
tags:
  - theory
  - backend
  - server
---



## Q. What is middle-ware ?
### Ans : It is a piece of code that runs **everytime** req comes , before it gets to the specific routes . Ex : for auth , logging etc

- Can be used for logging req , auth , extra checking for bad requests etc 
- It has all the access in req - res cycle to end it , change it or to forward it to the next ones.

![[req_res_flow_express | 500]]
![[middleware|500]]

![[middleware_2|500]]


## Q. Why middle-ware ?
### 1. Cleaner / Modular Code
### 2. Pre-processing before actual route
### 3. Re-usability , baar baar auth ke badle ek baar .




