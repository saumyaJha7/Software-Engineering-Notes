---
tags:
  - react-native
  - blog
---



When you start learning React, one term shows up everywhere:

> **Virtual DOM**

	But what actually is it?  
	And more importantly — **why does it exist?**
	
	Let’s break it down step by step in the simplest way possible.

---

# The Problem: Direct DOM Updates are Expensive

As we know , Browsers use  **Real DOM** to display UI.

Yes , we know that but what is the issue?
👉 Issue is that updating the Real DOM is **slow and costly**.

#### *Why so* ?

Because every change ( no matter how big or small ) can trigger:
- Layout recalculation (**reflow**)
- Repainting full UI 

Even a small update can affect the whole page.

---

## Example

Let say you have this in your page :-  

```html
 <h1>Aircraft Models</h1>
 
<ul>
	<li>Boeing 747</li>
	<li>Airbus A380</li>
</ul>
```

---

Now if the 3rd "li" needs to be added  , browser recalculates layout and repaints affected parts of UI, despite  a small change. 
 
 #### That is the issue : Expensive DOM updates 


# So react comes with the idea that : Don’t Touch the DOM Directly

Instead of updating the Real DOM every time…

React does something smarter:

> It first works in memory (Virtual DOM), then updates only what’s needed.

---
### Let me explain what I mean :- 


#  Real DOM vs Virtual DOM

## Real DOM
- Actual DOM created by browser
- Responsible for rendering UI
- Slow to update frequently

---

## Virtual DOM
- Lightweight **JavaScript representation** of UI 
- Stored in memory
- Fast to create and compare

---

### Yes that is it . 
## Virtual DOM = lightweight JavaScript object representation of actual DOM made in order to help react compare the updates in memory via virtual DOM and then update only what is required in the actual DOM .


## Simple Analogy for you to make mental model :- 

- Real DOM = Actual building  
- Virtual DOM = Blueprint of that building  

React uses the blueprint to decide what to change before touching the real structure.
And by doing that it saves a lot of expensive updates .

---

# Initial Render (First Time)

When your component loads for the first time:

- . React runs your component
-  Creates a **Virtual DOM tree**
-  Converts it into **Real DOM**
-  UI appears on screen

So first time → obviously everything is created from scratch

---

## Virtual DOM tree created by React :- 
![[blog-01 react virtual dom tree|900]]




## Initial Render Flow

![[blog-01 react intial render flow|900]]

---

# What Happens When State or Props Change?

Whenever:
- State changes (`useState`, `setState`)
- Props change
- or any change for that matter 

👉 React **re-runs the component function**

---

##  Important Thing to notice :- 

> React does NOT re-render the entire page  
> It only re-renders the affected component and its subtree.

---

## Let's understand this with an example :- 

- let say we added the 3rd li inside the ul

```html
 <h1>Aircraft Models</h1>
 
<ul>
	<li>Boeing 747</li>
	<li>Airbus A380</li>
	<li>Gulfstream G650</li>
</ul>
```

# 🌲 Step 1: New Virtual DOM Tree

After re-render:

- React creates a **new Virtual DOM tree**
- The old Virtual DOM is still stored


![[blog-01 old vs new virtual dom tree|900]]


👉 Think of it as taking a new snapshot of UI

---

# 🔍 Step 2: Diffing (Reconciliation)

Now React compares:

![[blog-01 diffing algo|900]]


This process is called:

> **Diffing** (or **Reconciliation**)

---

## Goal

Find:
- What changed?
- What stayed the same?

---

# ⚡ How React Finds Minimal Required Changes

React uses a few simple rules while comparing trees.

---

## 1. Same element type

If element type is same:

```jsx
<div className="old" />
		-> 
<div className="new" />
```

React updates only changed attributes instead of replacing whole node.

---

## 2. Different element type

If type changes:

```jsx
<div />
→
<span />
```

React replaces the old node completely.

---

## 3. Lists and keys

For lists, React uses `key` prop to track elements.

```jsx
<li key="1">A</li>
<li key="2">B</li>
```

Keys help React identify:
- added items
- removed items
- moved items

efficiently.

---

👉 Using these rules, React calculates the minimal updates needed for the Real DOM.

---

# Step 4: Update Real DOM

After diffing:

- React knows exactly what changed
- It updates **only those parts**


![[blog-01 minimal DOM update|900]]


---


>So Without Virtual DOM -> Rebuild entire DOM
>With Virtual DOM -> Update only changed nodes


---

## Now why React  is Fast is obvious to us , it is because :- 

- Real DOM operations = expensive
- Virtual DOM operations = cheap (in memory)

---

## So the core Idea is :- 

> React minimizes expensive ) DOM updates — and that’s what makes it fast.

---

## The full react flow :- 

![[blog-01 react full flow|900]]

---
# Final Summary :

- Virtual DOM = lightweight copy of Real DOM
- React creates a new Virtual DOM on every update
- It compares old vs new (diffing)
- Updates only required parts in Real DOM
- This makes React efficient and performant

