---
tags:
  - theory
---


## Q. What is UDP ?
### Ans : Like TCP, it’s a protocol for sending data over the Internet. **Key difference** is that UDP is **faster but less reliable** than TCP.


## Concept of UDP ?
###  In short: UDP = “send and forget” method, while TCP = “send carefully and check.”


### **How UDP works**

- Data is split into packets (like TCP), but:
    1. **Packets are not numbered** → receiver may get them out of order.
    2. **No error checking or retransmission** → lost packets are not resent.
    3. **No guarantee all packets arrive** → but it’s faster because there’s less overhead.


## Where it is used : "Where speed matters than perfection" like 

- **Live video/audio streaming** (YouTube live, Zoom) → speed matters more than perfect delivery
- **Online gaming** → small packet losses are acceptable
- **DNS queries** → quick requests to servers


```
- TCP → reliable, slower, for important data
- UDP → fast, less reliable, for real-time or streaming data
```


