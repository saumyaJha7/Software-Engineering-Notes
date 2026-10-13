---
tags:
  - thinking
  - backend
  - actualLearning
  - assignment
---

# Task 1 : update video 

- basic checks for Id and data

```
- now jab bhi ye url hit hua hai tb hamne routes mai hi file ko local Serve p store kra liya hai
- and multer by default localPath provide krta hai in req.files or file
- hamko sidha wo localPath cloudinary pe dalna hai and url string field set krna hai
```

- get the old thumbnail path of cloudinary
- get the localPath from multer's req.file 
- upload on cloudinary and handle the error 
- update the doc with cloudinary url as thumbnail
- delete oldCloudinary photo and return res


# Task 2 : Toggle Publish status

- get the video id and check 
- findOneAndUpdate  .... **Id as well as owner bhi match krna hai isliye**
- ==use not operator and set the value==
- handle empty and return res


# Task 3 : Publish a video 

- get title , desc and validate 
- get both the files and validate 
- duration from cloudinary 
- 