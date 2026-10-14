---
tags:
  - models
---



  

# Q. What is nested model ?
## - A **nested model** is when a field in one `BaseModel` is itself another `BaseModel`.
## - It lets you build **hierarchical, structured data models** (like JSON inside JSON).

## **Nested model** = `BaseModel` inside another `BaseModel`.

![nested model](../../excalidraw/nested model.md)
  
  

# Q. Why to use nested model ?
## 1. **Structured data** → mirrors how real-world data (JSON, API responses, configs) are usually nested.
## 2. **Automatic validation** → Pydantic validates nested models recursively.
### - Wrong types inside `address` will raise validation errors.

### 3. **Reusability** → You can reuse small models (`Address`, `User`) in multiple larger models.

### 4. **Clarity** → Keeps your code organized and mirrors real-world objects.





  
  

## Basic Code Example :


```python
from pydantic import BaseModel

class Address(BaseModel):
    city: str
    zipcode: str

class User(BaseModel):
    id: int
    name: str
    address: Address   # 👈 Nested model

user = User(
    id=1,
    name="Saumya",
    address={"city": "Delhi", "zipcode": "110001"}  # dict auto-converted
)

print(user)
# id=1 name='Saumya' address=Address(city='Delhi', zipcode='110001')

print(user.address.city)  
# Delhi
```
