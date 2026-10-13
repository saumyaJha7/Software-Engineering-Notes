


## What is TCP handshake (Also known as 3 way handshake)? 
## The **3-way handshake** makes TCP reliable by ensuring both devices are ready, synchronized, and can communicate before data transmission begins.

 
## Q. Why do we need it ?
## Ans. Because TCP is **connection-oriented**.

- It ensures both sender and receiver are **ready**,
- They **agree on sequence numbers** (so data can be tracked in order),
- And the channel is reliable before data starts flowing.


## 3 steps of TCP handhshake are  :-  


### 1. Synchronize  : client -> server 
- Client wants to set a connection so It sends a TCP packet with the **SYN flag = 1** and a **random initial sequence number (ISN)**.

### 2. Synchronize-Acknowledge : server -> client 
- The server receives the SYN.
- It replies with a packet where:
    - **SYN = 1** (to sync its own sequence number),
    - **ACK = 1** (to acknowledge the client’s sequence number).

### 3. Acknowledge : client -> server
- The client acknowledges the server’s sequence number with an **ACK = 1**.


```
✅ At this point, connection is established.
Both sides now know:

- They can reach each other.
- They have agreed on starting sequence numbers.
- The channel is reliable → ready to send data.
```

##  **Analogy (Phone Call 📞)**

1. **You (client):** “Hello, can you hear me?” (SYN)
2. **Friend (server):** “Yes, I can hear you. Can you hear me?” (SYN-ACK)
3. **You (client):** “Yes, I hear you.” (ACK)  
    👉 Now the conversation can start.

