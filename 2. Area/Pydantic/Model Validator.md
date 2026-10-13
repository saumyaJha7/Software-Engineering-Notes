

  

# Q. What is Model Validator ..
### `model_validator` is a **decorator function** (like `field_validator`) provided by **Pydantic v2**.
###  It is used when you want to **validate or modify the entire model at once**, not just a single field.
 .
  
  
  

# Q. Why to use Model Validator .. and not just Field Validator ?
## Ans . It is because .... 
###  `field_validator` = checks/cleans **one field**
### `model_validator` = checks/cleans **the whole model** (relationships between fields, global rules, etc.)

  
  
  

## Basic Examples :

```python
from pydantic import BaseModel, model_validator

class Employee(BaseModel):
    name: str
    start_date: str
    end_date: str

    @model_validator(mode="after")
    def check_dates(self):
        if self.end_date < self.start_date:
            raise ValueError("end_date cannot be before start_date")
        return self

```

### Here we need both `start_date` and `end_date` to compare.   
### `field_validator` can’t do this properly, because it only sees **one field at a time**.