---
tags:
  - thinking
  - backend
  - actualLearning
  - assignment
---
# Chatgpt convo ( paginate ) : https://chatgpt.com/share/6944c995-74d0-800f-beea-df5c9e0bffc7



# Task 1 :- get video Comments 

```
1. part by part mai dikhana hai 
2. video hai .. usme comments dikhane hai so each object is a comment and lookup mai owner ke details chahiye .. 
```

### 1. get the videoId and validate
### 2. Pipeline 

- get only comments jaha videoId match ho
- lookup kro users ko to get info 
- jo chahiye wahi rkh baaki hata and unwind owner field 

### 3. aggregatePaginate - pipeline and options 
### 4. return the res 


# Task 2 :- add Comment

### 1. get the content from body and videoId from params 
### 2. check for empty and validity of Id
### 3. check video DB mai hai ya nai
### 4. create a new entry and handle null
### 5. return res




# Task 3  : delete comment

### 1. get the comment ID
### 2. check valid hai ya nai 
### 3. check DB mai comment hai ya nai
### 4. findOneAndDelete ( id and owner) 
### 5. return res



# Task 4 : update comment

### 1. get the commentId and newComment
### 2. check for validity and null
### 3. check DB mai ye comment hai bhi ya ni
### 3. findOneAndUpdate and handle null
### 5. return res

