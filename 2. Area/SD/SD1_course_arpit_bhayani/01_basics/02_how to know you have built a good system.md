---
tags:
  - sd
---
```
Every system is "infinitely" buildable nd hence knowing when to stop the evolution is important.
```


### Some tangible parameters :- 

1. you've broken ur system into componets 


2. every component has a clear set of responsibility ( in most cases it must be exclusive as well )
		- server : serves user's req for feed over http 
		- generator : generate feed for the user based on follows , recommendation engine nd posts



3. for each component , you've slight technical details figured out :
		- db n cache
		- scaling n fault tolerance 
		- async processing 
		- communication

		- for eg , server ... yes db n cache figured out , made scalable , but nothing for async processing but atleast you've clarity .. nd thought on this paramenter ki iss sub-component ko ye chahiye ye nai 



4. each component ( in isolation ) is :-

	- scalable :
			 - horizontally scalable
			-  like what if users grew to 100k then how we would scale db 
			- how paralley we can compute feed of many users etc
			
	- fault tolerant : 
			- plan for recovery ( of mostly data ) in case of failure 
			- how should our system behave when generator is down ?
			- what happens if db down , data ??

	- Availability :
			- one component failure should not affect other components 
			- component functions even when some component "fails".
			- what if my one server goes down , system still available ?
			- no single point of failure 