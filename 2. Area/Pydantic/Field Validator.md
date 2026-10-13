

  

# Q. What is Field Validator ..
### It is a decorator function used for **custom validation logic** when `Field`’s constraints are not enough

 ### You write **Python code** to enforce rules. 
 Runs automatically when model is created.
  
# Q. Why to Field Validator  .. and not Field ?
### Field is for **simple, built-in validation rules**.
### field validator is for **complex, custom validation logic** that `Field` cannot express.


  
  
  

## Basic Example  :

```python
from pydantic import BaseModel, field_validator

class User(BaseModel):
    name: str

    @field_validator("name")
    def must_start_with_capital(cls, v):
        if not v[0].isupper():
            raise ValueError("Name must start with a capital letter")
        return v

```

### Here, `Field` **cannot** enforce "must start with capital letter", so we need a custom `field_validator`