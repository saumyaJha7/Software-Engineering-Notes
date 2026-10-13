---
tags:
  - theory
  - CN
  - http
---



## Q. What is HTTP ?
### Ans : It is a protocol that defines **how messages are formatted and transmitted** between a **web browser (client)** and a **web server**.


## Q. How it works ?
### Ans : How it works (Step by Step):

1. You type `https://www.example.com` in your browser.
2. Browser (client) sends an **HTTP request** → “Please give me the homepage.”
3. Web server receives the request and sends back an **HTTP response** → “Here’s the homepage HTML, CSS, JS, images, etc.”
4. Browser displays the page for you.


### By default , HTTP is stateless protocol : Each request is independent. Server doesn’t remember previous requests (unless [[cookies]], sessions, or tokens are used).