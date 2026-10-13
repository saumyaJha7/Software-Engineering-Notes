---
tags:
  - sd
  - kafka
  - async
  - bg_job
  - msg_broker
---


### Kafka :  msg streaming platform 

- high throughput ( real time event streaming ... very high number of events we can send to kafka )
- durable  ( keeps the log , not deleted after work done .... we can set some deletion policy but by default it stays )
- stateful  ( when one service has read till point a , it can commit nd later it can read from there only , so state is maintained )




![[kafka 101.png]]



![[Pasted image 20261007191431.png]]
![[Pasted image 20261007191740.png]]
![[Pasted image 20261007191805.png]]



And one **very important distinction** to retain:

> **Kafka doesn't decide what action to perform.**  
   Kafka stores and delivers the events. **The consumer/service contains the business logic that decides what to do with them.**






- Partitions :- 
		-  how partition works is 
		- each topic has n partitions 
		- msg arrives in topic 
		- based on same algo , it is placed in partition  
		- then consumer grp's instance execute from respective partition only
	

```
so the black box is not at the end when message is beign picked up by consumer grp.
Rather it is there at the initial phase when the event is going to be stored at any topic
```


![[kafka partitioning 101|900]]





![[Pasted image 20261007193332.png]]
![[Pasted image 20261007193344.png]]	