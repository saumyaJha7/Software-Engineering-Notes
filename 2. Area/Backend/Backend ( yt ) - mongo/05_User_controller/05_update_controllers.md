


# changeCurrentPassword ( verifyJWT run krenge coz login needed ):- 

### 1. get both the pass from req.body
### 2. validate both .
### 3. get the user from db ( userId from req.user  )
### 4. validate the password from db
### 5. change the user.password and save it ( save coz hash bhi to krna hai )

### 6. return ApiResponse 









```
similar for other basic functions
```

# UpdateUserAvatar / CoverImage :-

```
- multer middleWare use krenge to get the file from the user to our local server . 
- EK hi file hai isliye , upload.field ka use krenge and hence req.file ( not files )
  
- also , verifyJWT bhi use krenge to verify login hai ya nai
```

### 1. get the file to local server from the user via multer middleWare .
### 2. check for errors
### 3. upload it to cloudinay , handle for error
### 4. get the cloudinary url .. 
### 5. change the avatar field via req.user
### 6. handle the error and return the res .