
## IIFE -> Immediately Invoked Function Expression

```js
function connectDB(){
	// do something
}
connectDB()
```

```js
(function () {
	// do something
})() 

// (function)(execute turant)
```


### Both snippets _run the code inside_:

```js
function connectDB() {
  // do something
}
connectDB();
```
…and…
```js
(function () {
  // do something
})();
```

👉 In both cases, the code inside the function body executes.

---

# ❌ **But they are NOT doing the same thing**

## **1. The named function creates a global function**

`function connectDB() { ... }`

- This **adds `connectDB` to the global scope** (or current scope)
- The function stays available after being called
- Anyone can call it again later

`connectDB();
connectDB(); 
// can call multiple times`

---

## **2. The IIFE does _not_ create a global function**

`(function () { ... })();`

- The function exists **only for that moment**
- It is **not named** (anonymous)
- You **cannot call it again**
- It does **not pollute the global scope**

	someName(); // ❌ Not possible`

This makes an IIFE good for **initialization code** that should run once and stay private.




#### In some codeBases you will find that IIFE is started with a semi-colon : the reason is agar phle kahi semiColon nahi hoga to error aata hai bas isliye ..

```js
;()()
```


