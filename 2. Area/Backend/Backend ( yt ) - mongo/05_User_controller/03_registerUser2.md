---
tags:
  - backend
  - thinking
---


## 1. How to get the data from frontend :- 

- there are many ways such as form  , raw json , url etc
- form and raw json -> direclty req.body se mil jata hai 
- url se ayga toh -> req.params


## 2. How to upload the files/images into local server :- 

- routes file mai inject kro middleware just before registerUser method.
- how to use is multer middleware file se upload instance le aao
- upload.fields mai array ke form mai jitne files chahiye likh lo


## 3. Validation :- 

- there are many ways to do it 
- function bna lo .. wahi p koi method se krlo etc 


## 4. User exists :- 

- User model ka ref lo and mongodb mai check krlo user hai kya .
- userName and email dono se dekhenge , isliye mongoose ka $or operator use hoga 

```js
$or : [{ userName } , { email }]
```


## 5. How to check if files are there or not locally :- 

- multer kya krta hai req mai ek field add krta hai .. files naam se jiske andar path hota hai .
- hamesha rhe guarantee nai hai isliye ternary op ke sath rkho

```
for clear understanding , log krlo req.files ko and dekh lo kya kya hai .. usme saare details hote hai about size , type etc etc etc .
```


## 6. Upload the file to cloudinary :- 

- use the cloudinary util method and just provide the localPath there
- time lgega hi , isliye async await 
- check specially for avatar ki url aaya ya nai.


## 7. Insert to db :-

- user.create method se insert to db
- coverImage hai ya nai kya pata isliye extra checking imp hai.



## 8. Check for user creation :-

- directly check kr skte hai ... empty ya null hai kya
- ya phir ek aur db call kre but confirm way ki pata chalega + remove bhi kr payenge 
- so .. User.findById()


## 9. Remove password and token :- 

- .select() method hai jisme "-" lga ke string mai field ka naam likho toh hatt jata hai 
- eg :   User.select("-email -name") 


## 10. Return the response :- 

- use apiResponse format to standardize the response .





# Some errors and debugging :- 

- Db dusre continent mai hai ... so await chahiye hi .
- coverImage nai bheje to error aa rha hai , so handle it and set "" in db.
- Environment variables load krna sahi se .. wrna issue hi ni smjh ayga kya hai but issue env ka hoga 

 ==what i did was .. index.js run krne wali script mai hi env variables load krlo .==

```js
dev : nodemon -r dotenv/config src/index.js
```


