---
tags:
  - py
  - lib
---
 
  

# Q. What is pydantic ?

###  Pydantic is a **Python library for data validation and settings management** using **Python type hints**.   It ensures that the data you’re working with is the type and shape you expect—converting and validating it automatically.


# Q. Why to use pydantic ?
### Ans . Because it provides type safety  .
###  Also , it tries best to convert the data into desired type , but if it couldn't do that , then only error is raised +  error message is very clear so that devs can find the error directly 


# Q. Basic code of  pydantic ?

```python
from pydantic import BaseModel

class User(BaseModel):
	id : int
    name : str
    is_active : bool

input_data = {
    "id" : 1 ,
    "name" : "Saumya" ,
    "is_active" : True
} 

user1 = User(**input_data)  # it needs to be unpacked coz pydantic teen chiz expect kr rha hai and input_data is as a whole treated as one
print(user1)

input_data = {
    "id" : 2 ,
    "name" : "Ankit" ,
    "is_active" : "No"  # error 
}

user2 = User(**input_data)
print(user2)
```

  
  
  

## The power of pydantic is greatly enhanced by using [[Field]] , [[Field Validator]] , [[Model Validator]] , [[Computed field]]

### There are different  models for real world use case like [[nested model]]  , [[self-referencing model]]



## Some of the good practices are [[102_good_practices]]