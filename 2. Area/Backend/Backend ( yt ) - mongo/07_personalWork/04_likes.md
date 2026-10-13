---
tags:
  - thinking
  - backend
  - actualLearning
  - assignment
---

# task 1 : get all the liked videos by the user !

```
1. I am assuming ki jab bhi like krega user video mai to wo field add hogi .. 
2. and baaki field null rhegi .. 
```
- match jisme likedBy == userid and video == objectId
- lookup kro and video field mai hi change krdo 
- ==yaha aur sub-pipelines likh ke user ke bhi details show krenge==
- now after pipeline , handle empty array case
- return res with formatted data



# Task 2 : toggle Video Like 

- get the id from params
- check valid hai ya nai mongoose id
- match the doc where video == id from params and user also match
- agar hai ( liked ) , to doc uda do 
-  agar koi doc nai hai ( not liked ) toh doc bna do 


## Same for toggle Tweet and Comment !