---
tags:
  - code_notes
  - backend
  - thinking
---


# Break down the bigger problems into sub-parts , and solve step by step :- 


## Problem : Register user 


## Steps :- 

### 1. get the user details from frontend.
### 2. check for all the details correctness .
### 3. store the user into db .
### 4. return the user .


## ==Handle the errors in each step gracefully== 




# Some steps that I missed at first go :- 

- check if user already exists or not .
- images and avatar ko handle krna pdega ache se , checking ke sath
  



# So exact steps are :- 


 1. get the user details from frontend .
 2. upload the avatar and image  ( multer middleware )  .
 3. validate each detail .
 4. check if user already exists .
 5. check if files are there locally or not . ( avatar specially coz required hai )
 6. upload images/avatar on cloudinary and get the url . ( avatar specially )
 7. create a user object and add to db.
 8. check for user creation 
 9. remove password and refresh token from res .
 10. return res .





