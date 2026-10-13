---
tags:
  - redis
  - task_queue
  - bg_job
  - backend
  - caching
  - DB
---

## Q1. Why queue exists?
#### Ans : Some work does not need to be completed before responding to the user. We put that work into a queue, and workers process it asynchronously.



## Q2. How to implement queue in redis ?
#### Ans : Redis provides a DS called list .

- LPUSH / RPUSH for pushing job into queue
- RPOP / LPOP for removing job from queue 


###### FIFO : we push from one side and remove from other ofc 




## Q3. Some terms ? 

- Producer : any piece of code that puts the job into queue 
- Consumer : any piece of code that consumes the job from queue 


## Q4. How to implement consumer/worker ?
#### Ans: we can't use a while loop and worker checking in each ms ki "koi job aaya kya?" , "koi job aaya kya?"

##### Rather a better way is when worker says :- 

```
"Redis, wake me up when a job becomes available."
```


- therefore we use function BLPOP / BRPOP  rather than simple LPOP or RPOP .

```
LPOP:
"Give me a job now."
       ↓
No job? → return null immediately
```

```
BLPOP: ( b means Blocking )
"Give me a job. If there isn't one,
wait until one arrives."
```




## Q5. What is the problem with basic redis queue made by us ?
#### Ans:- 

- job loss ( removed from queue but while executing some error occurred )
- Retry failed jobs
- Track whether a job is waiting/active/completed/failed
- Multiple workers
- Concurrency ( parallel workers )



## Q6. BullMQ ?
#### Ans: For happy case , basic queue is fine but when real issues are considered , we need robust software that handles all the things listed above .


- either re-invent the wheel and make custom software 
- use the existing std ones 





##### Note : BullMQ & RabbitMQ are different tech, not the exact alternate to each other 

