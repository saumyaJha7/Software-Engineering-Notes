---
tags:
  - theory
  - backend
  - fullStack
---


### A **proxy** in Express.js is a setup that allows your server to **relay HTTP requests** to another target server. It’s commonly used to:
- Avoid **CORS (Cross-Origin Resource Sharing)** issues
- Hide or simplify API endpoints
- Add custom headers, authentication, or caching logic
- Combine multiple backend services behind one unified API
    

---

## **How to use proxy**

## Jo bhi tool use krke bnaye ho frontend uspe depend krta hai , for example abhi vite se bnayi hai to just google it vite proxy. 

FOR vite :- 
```
vite.config.js file mai add krna hota hai 
```

---
## How it solves CORS problem ?
### req kisi bhi url se ho rhi ho , agar usme "/api" hai to :-
1. usme prePend ho jyga "http://localhost:4000" and the url becomes -> "http://localhost:4000/api/data"
2. req ka origin same ho jyga hence ye valid url maana jyga 

---

### 🏁 **Summary**

| Concept     | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| **What**    | A way to forward requests from your Express app to another server |
| **Why**     | To avoid CORS, combine APIs, or customize request flow            |
| **How**     | depends                                                           |
| **Example** | `/api → https://api.example.com`                                  |

