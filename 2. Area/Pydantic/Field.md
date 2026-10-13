


  

# Q. What is Field
## `Field` is used inside a **Pydantic model** to give **extra metadata, validation rules, or defaults** for a field.
## Think of it like a "customization layer" on top of your type hints.

  
  
  

# Q. Why to use Field  .. and not just default pydantic ?


### It is because without `Field`, you’d just have simple type validation (like `str`, `int`).  
## But with `Field`, you can:

### - Add **extra validation rules** (`min_length`, `ge`, `le`, regex).
### - Control whether the field is **required** or optional.
### - Provide **metadata** (description, title, examples) → useful for API docs in FastAPI.

### - Define **default values** in a cleaner way.

  


## Example :

```python 
from typing import Optional
from pydantic import BaseModel, Field

class Employee(BaseModel):
    id: int
    name: str = Field(
        ...,  # now it is mandatory field
        min_length=3,
        max_length=20,
        description="Employee name"
    )

```



### Different types of validation props in `Field`:

- **Strings** → `min_length`, `max_length`
    
- **Numbers** → `gt`, `ge`, `lt`, `le`, `multiple_of`
    
- **Docs/Meta** → `title`, `description`, `example`, `alias`, `deprecated`, `const`