


## We have some ways to apply async processing in our system :- 




#### 1. Redis :- 

	- it intrinsicaly not a queue system
	- but it provides basic primitives to use it as a queue 
	- LPOP , RPOP , etc etc 
	- but main question is jab kch khud se krna pdega 
	- job failure , retries , crash , message persistence , deletion etc etc 



### 2. RabbitMQ :- 

	- it is a msg broker 
	- isme producer , worker sbka logic , retries khud likna pdega 
	- RabbitMQ is particularly useful for service-to-service communication
	- ki video service ne job add kr diya , subtitle service apne logic se usko process kr legi 


![rabbitMQ use case](../../../../excalidraw/rabbitMQ use case.md)




### 3. BullMQ : 

	- it is a complete job queue / bg job processing framework built on Redis.
	- so it gives api's to do all things ( worker, retries , failure etc )
	- use it when u directly need : I have a job to execute





### 4. Kafka : 


	- it is conceptually quite different 
	- but is used for async processing 

( more abt it in next notes )




# So basically difference is :- 


Raw Redis
→ "Here are primitives. Build your queue."

BullMQ
→ "Here is a ready-made job queue built using Redis."

RabbitMQ
→ "Here is a dedicated message broker."

Kafka
→ "Here is a distributed event streaming system."