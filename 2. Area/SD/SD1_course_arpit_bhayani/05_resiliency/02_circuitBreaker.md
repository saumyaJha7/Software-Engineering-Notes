---
tags:
  - sd
---

### There are other ways in which circuit breaker can be implemented , but the idea is similar ( prevent cascading failure )

- coz db approach is basic implementation of it , isme one prblm is that kya pta common db khud bottleNeck bn jaaye 
- this is for naive implementation , to undestand the circuit breaker concept , we can make things more complicated / sophisticated in real world 
- one way is harr service ke pass apna config ho , nd jab bhi kch change ho service health m we update the respective services 
- so read more abt it 




![[Pasted image 20261008121126.png]]
![[Pasted image 20261008121145.png]]
![[Pasted image 20261008121158.png]]
![[Pasted image 20261008121209.png]]

- so it is like if service is healthy , then only req
- else , handle that case 
- may be servce general feed in case of social networks app 
- or whatever acc to useCase , but this way can prevent complete outage 

![[Pasted image 20261008121224.png]]