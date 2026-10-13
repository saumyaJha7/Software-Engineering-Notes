

---

# 🔹 What is an `interface` in TypeScript?

An **interface** defines the structure of an object or class.

👉 Think of it as a **contract** — “anything that follows this interface must have these fields.”

## ✅ Basic example

interface User {  
  name: string;  
  age: number;  
}

Now you can use it:

```typescript
const u: User = {  
  name: "Rahul",  
  age: 25  
};
```

If you forget a property or use the wrong type, TypeScript gives an error.

---

## ✅ Interface with functions

interface Login {  
  username: string;  
  login(): void;  
}

---

## ✅ Extending interfaces (inheritance)

interface Animal {  
  name: string;  
}  
  
interface Dog extends Animal {  
  breed: string;  
}

Interfaces are **great for OOP-style code** and classes.

---

# 🔹 What is a `type` in TypeScript?

A **type alias** lets you create a custom type name for _anything_, not just objects.

type User = {  
  name: string;  
  age: number;  
};

Looks similar to interface — but `type` is more flexible.

---

## ✅ Types can do more advanced stuff

### 1️⃣ Union types

type Status = "success" | "error" | "loading";

---

### 2️⃣ Combine multiple types

type A = { name: string };  
type B = { age: number };  
  
type Person = A & B;

---

### 3️⃣ Functions

type Add = (a: number, b: number) => number;

---

# 🔥 Interface vs Type — Key Differences

|Feature|interface|type|
|---|---|---|
|Object shapes|✅ Yes|✅ Yes|
|Union types (`|`)|❌ No|
|Intersections (`&`)|⚠️ Limited|✅ Yes|
|Extend / inheritance|✅ `extends`|✅ via `&`|
|Declaration merging|✅ Yes|❌ No|
|Best for classes/OOP|⭐ Excellent|Good|
|Best for complex types|Limited|⭐ Powerful|

---

# 🧠 Super Simple Rule (Most Devs Follow)

👉 Use **`interface`** when:

- Defining object shapes
    
- Working with classes
    
- Building APIs / models
    

👉 Use **`type`** when:

- You need unions (`A | B`)
    
- Advanced type logic
    
- Utility types or transformations
    

---

# 🪄 Real-World Example

interface ApiUser {  
  id: number;  
  name: string;  
}  
  
type ApiStatus = "loading" | "success" | "error";

Here:

- Interface = structure
    
- Type = flexible value definition
    

---

# ⚡ Quick Analogy

- **interface** = blueprint of a house 🏠
    
- **type** = math formula or definition 📐