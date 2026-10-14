---
tags:
  - caching
  - sd
---
### 2 types of populations :- 


- lazy population : user req kre , cache hit to bdhiya cache miss ho to db se data le aao + cache m rkh do.
- eager population : is further has two ways  

	1. whenever server writes , it writes on both , db as well as cache 
	2. when there is some need , like celebrity post , cache it right away or yt trending vids 

( lazy means , khud se kch nai krenge miss hoga to hi  krenge )


### Scaling : it's a db at the end so similar as db scaling 



![Pasted image 20261001092447.png](../../../../excalidraw/Pasted%20image%2020261001092447.png)
![Pasted image 20261001092511.png](../../../../excalidraw/Pasted%20image%2020261001092511.png)
![Pasted image 20261001092524.png](../../../../excalidraw/Pasted%20image%2020261001092524.png)