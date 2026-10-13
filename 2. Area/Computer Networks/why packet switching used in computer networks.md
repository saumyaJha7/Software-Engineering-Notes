---
tags:
  - CN
  - theory
---
## 🚫 Problems with Circuit Switching for ARPANET

1. **Inefficient use of bandwidth**  
   - In circuit switching, once a circuit is established, the bandwidth is reserved whether or not data is being transmitted.  
   - Computers communicate in **bursts** (short messages with idle time in between), so most of the reserved circuit would sit unused.

2. **Poor scalability for many-to-many communication**  
   - ARPANET needed to connect many computers across universities and research labs.  
   - Setting up a separate circuit for each connection would have required massive infrastructure and been very costly.

3. **Lack of robustness**  
   - If a circuit (path) broke (e.g., due to equipment failure), the whole connection would be lost.  
   - The military wanted a system that could **survive outages** and still deliver data (important for Cold War resilience).

4. **Slow setup time**  
   - Establishing a circuit takes time before communication can start.  
   - Packet switching allows immediate transmission — just break data into packets and send them.

5. **Not suited for data traffic**  
   - Circuit switching was designed for **voice calls** (continuous, real-time, constant data rate).  
   - Computer communication is **bursty, irregular, and needs reliability** (error correction, retransmission). Packet switching handles this much better.

---

## ✅ Why Packet Switching Was Better for ARPANET

- **Efficient bandwidth sharing**: Multiple users share the same network paths dynamically.  
- **Resilience**: Packets can be rerouted if part of the network goes down.  
- **Scalability**: Easy to add more computers without redesigning the whole network.  
- **Optimized for data**: Handles bursts, retransmissions, and error correction naturally.  

---

👉 In short: **Circuit switching wasted resources, lacked flexibility, and was fragile. Packet switching offered efficiency, robustness, and scalability — exactly what ARPANET needed.**
