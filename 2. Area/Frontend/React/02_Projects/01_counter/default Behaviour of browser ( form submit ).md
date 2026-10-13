---
tags:
  - theory
  - browser
---
## Also read about event bubbling 



## ✅ What `e.preventDefault()` Does

`preventDefault()` tells the browser:

👉 **“Do NOT run the element’s default behavior.”**

Every HTML element has built-in behaviors. When an event happens (click, submit, etc.), the browser automatically performs its default action unless you stop it.

---

## 🌐 Browser’s Default Behavior for Forms

When you submit a form like this:

`<form>   <input name="email" />   <button type="submit">Submit</button> </form>`

The browser will:

1. Package all form fields
    
2. Send them to the URL in the `action` attribute
    
3. **Reload the page**
    

If there is no `action` attribute, it reloads the same page.

---

## 🔁 What Happens Without `e.preventDefault()`

React example:

`function handleSubmit(e) {   console.log("Form submitted"); }`

Result:

- Console logs `"Form submitted"`
    
- Browser reloads the page
    
- React state is wiped
    
- UI resets
    

This feels like your app is "refreshing" or "breaking"

---

## 🛑 What Happens With `e.preventDefault()`

`function handleSubmit(e) {   e.preventDefault();   console.log("Form submitted"); }`

Result:

- Page does NOT reload
    
- React keeps control
    
- You can send data using `fetch` / `axios`
    
- State remains intact
    

This allows React to behave like a **single-page application (SPA)** instead of a traditional website.

---

## 🧠 Mental Model

Think of it like:

> “Browser, don’t take over. I’ll handle this with JavaScript.”

---

## ⚡ Real-World Analogy

Imagine clicking an elevator button:

- Default behavior → elevator goes up
    
- `preventDefault()` → you intercept the button and choose where to go manually
    

---

## 🧩 Why SPAs Need It

Traditional HTML:

`Submit → Reload → New Page`

React:

`Submit → JavaScript handles data → No reload`

React apps rely on JavaScript routing and state — page reloads destroy both.

---

## ✅ Other Places You’ll See `preventDefault()`

- Clicking links
    
- Drag & drop
    
- Right-click menus
    
- Keyboard shortcuts
    

Example:

`document.addEventListener("contextmenu", e => {   e.preventDefault(); // disables right-click menu });`

---

## 🏁 Short Answer

Without `e.preventDefault()`:  
➡️ Form submission reloads the page

With `e.preventDefault()`:  
➡️ You control what happens using JavaScript