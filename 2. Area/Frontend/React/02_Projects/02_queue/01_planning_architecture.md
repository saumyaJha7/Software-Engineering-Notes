---
tags:
  - react
  - planning
---

# "Get the data from form and show in display card"


## We have two components here :- 

- form 
- display card



### 1. Form problems 

#### - to keep one state "formData" or two diffn one , "name" and "service"
#### - how to share data ... ( state management problem )

- app mai hi state bna ke form and queue component mai pass kr skte hai ( one way )



## Problem with my logic :- 

- mai state declare to  kr rha tha app mai ... then wo saare states as props pass kr rha tha Form and Queue component mai and methods that changes them wo  uss file mai kr rha tha 

#### - Solution is to write the functions in app itself .. 


![[QMS_plan | 900]]




### - AddToQueue :

-  receives new customer's data and pushes into the queue 
- id yaha generate krenge 
- status bhi 

### - removeFromQueue : 

- gets the id and removes the customer 
### - updateStatus : 

- gets the id and newStatus
- loop through the arr 
- updates the specific customer's status 





## What is this id ?
- we will generate this for every customer on the time of adding them to queue 



