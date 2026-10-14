---
tags:
  - redis
  - sd
  - msg_broker
  - kafka
---
### okay so what was happening in kafka 
```
consumer pull data at their own pace , so kafka may get 10k events per second , but consumer can consume 2k per sec only , so they do 2k only nd rest is stored there
```


### but in case of realtime pubsub ( eg. redis pubsub )
```
as soon as redis gets the message , it broadcasts the message to whoever has subscribed to the channel , if any subscriber is down , the message gets lost for that subs 
```




![Pasted image 20261007195146.png](../../../../excalidraw/Pasted%20image%2020261007195146.png)

### A very useful mental model :- 

**Kafka:**
> **"Here is a queue of work. Process it at your own pace."**

**Redis Pub/Sub:**
> **"Something just happened. Whoever is listening, hear this."**




![Pasted image 20261007195306.png](../../../../excalidraw/Pasted%20image%2020261007195306.png)
![Pasted image 20261007195328.png](../../../../excalidraw/Pasted%20image%2020261007195328.png)