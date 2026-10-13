---
tags:
  - theory
  - CN
  - OSI
---


## Q. What is OSI model ?
### Ans : It is a **conceptual framework** that explains **how data travels** from one computer to another across a network (like the Internet).


![[excalidraw/OSI Model|OSI Model | 900]]


## - The 7 Layers of OSI Model :- 

| **Layer (Top → Bottom)** | **What it does**                                                | **Example**                                   |
| ------------------------ | --------------------------------------------------------------- | --------------------------------------------- |
| **7. Application**       | Interfaces for the user → apps use this layer to access network | Web browser, email, WhatsApp                  |
| **6. Presentation**      | Formats, encrypts, compresses data                              | JPEG, MP3, SSL/TLS encryption                 |
| **5. Session**           | Manages communication sessions                                  | Logging into a website, keeping you connected |
| **4. Transport**         | Breaks data into segments, ensures reliable delivery (TCP/UDP)  | TCP (reliable), UDP (fast)                    |
| **3. Network**           | Decides the best path for data, handles addressing              | IP addresses, routers                         |
| **2. Data Link**         | Transfers data between two directly connected devices           | Ethernet, Wi-Fi (MAC addresses)               |
| **1. Physical**          | Actual transmission of bits (0s and 1s)                         | Cables, Wi-Fi signals, fiber optics           |

## **How Data is Sent via the Internet (Step by Step)**

### Example: You open a website (say _www.google.com_)

1. **Application Layer (7)**
    - Browser creates a request (HTTP/HTTPS).
        
2. **Presentation Layer (6)**
    - Data is formatted (text, images) and encrypted if HTTPS.
        
3. **Session Layer (5)**
    - Maintains your connection with Google’s server.
        
4. **Transport Layer (4)**
    - Data is broken into **segments**.
    - TCP ensures reliability (all packets delivered, in order).
        
5. **Network Layer (3)**
    - Each **packet** gets an **IP address** (your IP + Google’s IP).
    - Routers decide the best path across the Internet.
        
6. **Data Link Layer (2)**
    - Adds **MAC address** of your device and next router.
    - Works on local Wi-Fi or Ethernet.
    - Data in frames .
        
7. **Physical Layer (1)**
    - Data becomes **electrical signals, radio waves, or light pulses**.
    - Travels through cables, Wi-Fi, or fiber optics.
        
---
### **At Google’s Server (the receiver)**

- The process happens **in reverse** (Physical → Data Link → Network … → Application)
- Finally, the server understands the request and sends back the webpage.



### Difference between Transport and Network layer is : [[2. Area/Computer Networks/network_transport layer]]
