---
tags:
  - next
  - email
  - backend
---


### We write this in helper function :- 



https://chatgpt.com/g/g-p-6965c66158d88191bf53156a1fd46088-full-stack-overview/c/69bffa70-0aec-8321-a4aa-3e638a76b06a



## We have two cases where mail is getting used :- 


- verify user ( while signup )
- reset password 



### So  instead of making two different functions we have made only one function and have made it parameterised .


#### We will accept :- 

- emailTo : jisko bhjna hai email 
- emailType : verify hai ya reset uske acc subject rkh skte hai 
- userId 



## Now sendMail function mai .. 

- type check krenge ki verify hai ya reset-pass
- verify hai to verifyToken gen krke db mai store krlo + expiry bhi 
- send the token to user in mail via query params 
- if it's reset pass , do this with resetToken



### And we are using mailtrap for testing mails :- 

- read more about it in gpt link or theiry official docs


