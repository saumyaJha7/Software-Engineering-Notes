---
tags:
  - theory
  - node
  - architecture
  - backend
  - job
---

## Node's official doc : https://nodejs.org/en/learn/asynchronous-work/event-loop-timers-and-nexttick



![[nodejs_architecture|800]]



## Event queue : events/req ka queue i.e. jo bhi req aati jayngi users se wo queue mai line se lgti jayengi

## Event loop : aisa loop jo queue ko continously watch krta rehta hai koi req to nai aayi AND jab req aati hai to FIFO principle se wo req ko pick krta hai and queue se remove krde hai ..


# Now here is what the event loop does :- 

- Event loop ek watchman hai jo queue ko dekhta rehta hai.
- Jab koi request/event ready hota hai, wo usse uthata hai aur execute karta hai.
- Agar async kaam hai → background me bhej deta hai (OS ya thread pool ke paas).
- Agar sync kaam hai → khud hi karta hai, aur tab tak kisi aur ko process nahi kar sakta.


## What is a thread pool : It is a pool of workers , i.e. different threads that executes the task so that main thread is not blocked . By default , 4 thread hote hai but depends on machine etc etc.


# The flow is something like this for async operation :-

### 1. client made the req
### 2. event queue mai gaya 
### 3. loop ne uthaya and delegate kr diya
### 4. ek thread assign hua and BACKGROUND mai execution start hua ( **main thread abhi next queue ka task process kr skta hai**)
### 5. Thread ke execute krne ke baad wapas se event queue mai lined up ho gaya
### 6. baaki kaam krne ke baad loop dubara usko uthayga , then will just execute .

![[nodejs_architecture_flow|900]]




```
problem with sync code : Hamare pass limited thread hi hote hai , so consider a case where 10k users are trying to register at the same time , then kch few initial users ke liye to wo kaam krega but uske baad bhut slow ho jyga website , coz event loop ek user ki query execute jb tk krega tb tk dusre user ko wait krna hi pdega , therefore it is must to write the code in async manner , FOR THIS CASE.
```
