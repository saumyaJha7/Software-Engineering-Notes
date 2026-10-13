---
tags:
  - models
---
  
# Q. What is self-referencing model ..
## A **self-referential model** is a model that **references itself** as a field.
### - Useful for **recursive or tree-like data structures** (e.g., comments, categories, org charts).
  
  

# Q. Why to use self-referencing model .. ?

## Ans .consider a real world scenario ... someone comments then someone replies to that comment and then again owner replies to the reply .. and so on ... i.e.

  ![[self-refn model | 600]]
  
  

## Basic Code Example :

```python

from pydantic import BaseModel
from typing import List, Optional

class Comment(BaseModel):
    id: int
    text: str
    author: str
    replies: Optional[List['Comment']] = []  # 👈 self-reference for nested replies

Comment.model_rebuild() # this is for performance upgradation .. agar ni use krenge to bhut drop hoga performance ( forwad refn)

# Example data
comment = Comment(
    id=1,
    text="This is the main comment",
    author="Alice",
    replies=[
        Comment(
            id=2,
            text="This is a reply",
            author="Bob",
            replies=[
                Comment(id=3, text="Nested reply here", author="Charlie")
            ]
        ),
        Comment(
            id=4,
            text="Another reply",
            author="Dave"
        )
    ]
)

print(comment.model_dump())

```