---
tags:
  - theory
  - node
  - code_notes
  - events
---


## Q. What is events in node js ?
### Ans : A signal about whether certain task is done ya consider it like moment of change of state of any task like timer expire ho gya , user ne order kr diya .
```
moment when payment is done , that is an event , now grant the user access of the course that is done by eventHandler listening to the payments event .
```



## Q. Advantages of  events ?
### Ans : Event hone ke baad jo function chlna tha wo apne aap chal jyga **jab wo event trigger hoga tb**.

- **Enable non-blocking I/O** — Node.js can handle many tasks at once efficiently.
- **Simplify asynchronous programming** — You can just listen for when something happens.




## Consider the following scenario :-

### 🎯 Scenario: "When payment is made, give the user access to the course"

You can think of it like this:

- **Event name:** `"paymentSuccess"`
- **Listener:** A function that gives access to the course
- **Emitter:** The part of your app that handles payments (e.g., Stripe webhook or checkout process)
    

---

### 🧠 Conceptually

> **When the “paymentSuccess” event happens → run the code that grants course access.**

That way, you don’t have to tightly couple the payment logic and access logic together — they communicate through **events**.

---

### 🧩 Example Code

```js
const EventEmitter = require('events');
const paymentSystem = new EventEmitter();

// 1. Listen for the event
paymentSystem.on('paymentSuccess', (userId, courseId) => {
  console.log(`✅ Payment received from user ${userId}`);
  console.log(`🎓 Granting access to course ${courseId}`);
  // Code here to give access (e.g., update database)
});

// 2. Simulate payment completion
function processPayment(userId, courseId) {
  console.log('💳 Processing payment...');
  
  // After successful payment
  setTimeout(() => {
    console.log('💰 Payment successful!');
    paymentSystem.emit('paymentSuccess', userId, courseId);
  }, 2000);
}

// Run it
processPayment('user123', 'course456');

```


**Output:**

```css
💳 Processing payment...
💰 Payment successful!
✅ Payment received from user user123
🎓 Granting access to course course456
```

---

### 🧩 Why this is useful

- **Loose coupling:** Payment logic doesn’t need to know _how_ access is granted — just that it should happen after payment.
    
- **Scalability:** Later, you could also listen for `paymentSuccess` to:
    - Send a confirmation email
    - Log analytics
    - Notify an admin

All without touching the payment code!

