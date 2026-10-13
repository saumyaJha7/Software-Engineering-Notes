

  

# Q. What is Computed field ?
### A **computed field** is a property of your model that is **not stored directly in the input**, but is **calculated from other fields**.
### It behaves like a **read-only field**
  
  
  
	
# Q. Why to use Computed field ?

###  When you need a field that depends on other fields (e.g., `full_name`, `age_from_dob`). 
 

  
  
  

## Basic Code Example :

```python
from pydantic import BaseModel, computed_field

class User(BaseModel):
    first_name: str
    last_name: str

    @computed_field  
    @property # it gives access as a prop
    def full_name(self) -> str:
        return f"{self.first_name} {self.last_name}"

u = User(first_name="Saumya", last_name="Jha")
print(u.full_name) 
```
