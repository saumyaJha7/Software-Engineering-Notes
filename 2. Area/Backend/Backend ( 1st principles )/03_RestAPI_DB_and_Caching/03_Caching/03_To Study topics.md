---
tags:
  - theory
  - BFFP
  - caching
---


## 1. two caching strategies 
-  Lazy caching ( cache aside )
- Write through

### 2. Eviction policies 
- LRU 
- LFU
- TTL based policy ( lowest TTL , remove it )


### 3. Use case of in-memory db's ( read more , case studies )

#### a. caching db query 
		- query with lots of joins for eg
		- let say there is amazon sale on m1 , if we don't cache the price,image etc  of m1 .. bhut jyada overhead aa jyga server pe coz millions are trying 
		- in short , cache the static data 
		- read heavy op and write is less frequent 

#### b. Session storage ( tokens etc ) 
	- har baar db lookup se acha cache krlo token for some time

#### c. 3rd party API caching 

- let say in any of your api , you are also hitting api of weather app 
- ab harr baar user uspe click krega to hamare api ke pass req aaygi then 
- waha se weather api ko jygi .... latency 
- and general data about weather of the day don't change every sec generally ..
- so it's better to cache it 
- also 3rd party api calls ka paisa lgta hai .. to jab pta hai weather 5 min phle ye tha and change hone ke aasaar nai dikh rhe hai to paisa bacha n .. 

















