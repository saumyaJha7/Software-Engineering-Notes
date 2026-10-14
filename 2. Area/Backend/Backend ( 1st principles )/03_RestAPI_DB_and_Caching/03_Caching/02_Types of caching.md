---
tags:
  - BFFP
  - caching
---


### Caching is about avoiding slow work by remembering recent results —  at the network, machine, or application level.



## Q. Types of caching ( roughly )?

### Ans. Three types of caching :-


#### 1. Network based caching  : client-server ke bich ka physical distance kam kro .... uss client ka data usske pass wale server mai cache kro 

- CDN based ( edge servers ) : nearest server -> cache hit -> instant response 
![CDN or edge server caching](../../../../../excalidraw/CDN%20or%20edge%20server%20caching.png)
	
- DNS based : local DNS cache maintained by OS for IP resolution ( coz IP resolution is long process )  ... (==recursive resolver== )
	- firstly check in local , if cache hit -> instant return the ip
	- else , DNS -> Root server  -> TLD server -> ANS ->  get the IP


#### 2. Hardware based caching : CPU ke pass store krlo 

- l1 , l2 cache
- l3 cache



#### 3. Software based caching : use redis / Memcached 

- in memory   (  RAM mai store hota hai )
- key-value pairs 
- no sql type 




## ==Study more about each of them==

