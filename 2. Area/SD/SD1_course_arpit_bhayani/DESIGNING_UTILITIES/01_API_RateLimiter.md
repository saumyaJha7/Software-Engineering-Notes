---
tags:
  - sd
  - hands-on
  - design
---
- RL : first line of defense for servers 
- counts , expiry etc store krna hai , check krna hai so : redis db will be better 
- koi alg se service ki need initially to nai hai 
- LB ya proxy mai hi ye logic likh skte 
- direct LB ya proxy ko redis se connect krdo 
- uss redis mai sirf RL ki chize hongi so nothing to worry 


![rate_limiter.png](../../../../excalidraw/rate_limiter.png)


- now one can also scale the redis db 
- ( depending on the load )




- also some RL algo's :- 

		- Fixed Window : "har 1 min mai 5 req" ( bounday prblm )
		- Sliding Window : "moving 1 min mai 5 req" ( solves boundary prblm )
		- Leaky Bucket 



![rate_limiter_1.png](../../../../excalidraw/rate_limiter_1.png)


![rate_limiter_2.png](../../../../excalidraw/rate_limiter_2.png)


![rate_limiter_3.png](../../../../excalidraw/rate_limiter_3.png)


![rate_limiter_4.png](../../../../excalidraw/rate_limiter_4.png)


![rate_limiter_5.png](../../../../excalidraw/rate_limiter_5.png)


![rate_limiter_6.png](../../../../excalidraw/rate_limiter_6.png)


![rate_limiter_7.png](../../../../excalidraw/rate_limiter_7.png)


![rate_limiter_8.png](../../../../excalidraw/rate_limiter_8.png)


![rate_limiter_9.png](../../../../excalidraw/rate_limiter_9.png)


![rate_limiter_10.png](../../../../excalidraw/rate_limiter_10.png)

