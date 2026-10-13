---
tags:
  - theory
  - dev
  - server
  - backend
---

#  There are different types of middle-wares :-

| Type                        | Where it runs                                                                      | Example meaning                                                             |
| --------------------------- | ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Global Middleware**       | Runs on **every route** and **every method**                                       | `app.use()` → chalega **sab routes** pe                                     |
| **Router-Level Middleware** | Runs on **all routes inside a router** (like `/books/...`) and for **all methods** | `router.use()` → chalega **/books** ke sab subroutes pe                     |
| **Route-Level Middleware**  | Runs on **a specific route + method**                                              | `app.get('/books', middleware)` → chalega **sirf /books pe GET request** pe |


#### 🥇 Global Middleware
```js
app.use((req, res, next) => {
  console.log('Global middleware -> sab route pe chalega');
  next();
});
```

#### 🥈 Router-Level Middleware
```js
bookRouter.use((req, res, next) => {
  console.log('Router middleware -> /books ke sab routes pe chalega');
  next();
});
```

#### 🥉 Route-Level Middleware
```js
function onlyForGET(req, res, next) {
  console.log('Route middleware -> sirf GET /books pe chalega');
  next();
}

bookRouter.get('/', onlyForGET, (req, res) => {
  res.send('All books');
});
```


### 🔍 Output flow example:

If someone sends:

- `GET /books` → all 3 run ✅  
    (Global → Router → Route-level)
    
- `POST /books` → only Global + Router ✅  
    (no route-level for POST)
    
- `GET /users` → only Global ✅  
    (no router or route-level)