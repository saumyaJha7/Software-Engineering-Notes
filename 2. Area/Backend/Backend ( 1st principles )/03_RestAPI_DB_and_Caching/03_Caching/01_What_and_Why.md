---
tags:
  - theory
  - BFFP
  - caching
---


## Q. Problem ?
### Ans. network calls mai lgta hai time isliye ux acha nai hota 



## Q. Solution -> Caching ?
### Ans. Caching is the mechanism of storing the frequently fetched data or subset of primary data  ( temporarily ) in fast access location . ==very imp==

### "jaha bhut jyada computation lg rhi hai ya heavy data send ho rha hai baar baar .. we try to cache it!"




## Example :- 

### 1. you search something in google 
### 2. if cache hit , shows the result turant
### 3. else go to server , ab cache krlo  for next query


## There are also something called :- 

1. Cache invalidation : removing outdated data 
2. TTL : how long data stays cached.


## Another example :- 

### Netflix itna saara data kaise w/o latency dikhata hai 

- it caches famous shows , your preferences etc in cdn 
- bhut saare algo lgake predicts what you will watch and caches it aggressively 
- also main server ki bjaye pass ke server p cache krta hai 

#### So , Netflix bypasses latency by moving content as close as possible to users using its own CDN, predictive caching, and adaptive streaming.



# Q. Jab sb itna sahi hai to saara data cache krlo n ?
### Ans. It is costlier than disk storage hence nai kr skte 


==why  it is more costly ? hardware difference ? what is actaully difn between memory and disk storage ? ==
##### ==study about db/network storage and in-memory storage==


