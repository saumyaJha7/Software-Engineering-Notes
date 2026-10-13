---
tags:
  - backend
  - theory
---


```
"File upload ko ham generally util folder mai bnate hai coz ... ye harr route mai ni aane waal kaam .. jaha ayga waha sidha import kr lenge "
```


# Flow :- 
1. get the file from the user .
2. store it into local server ( disk )
3. upload it to cloud server .
   3.1 : If succeeded , delete the local file .
   3.2 : else , retry or error message .


## 1. generally it is a good practice ki 3rd party service use kre and files waha upload kre and get the link to work on , so we are using cloudinary for that ( behind the scene aws hi use ho rha hai )

## 2. Ham user se file lene ke liye and usko local mai store krne ke liye multer package ka use krenge . ( express-fileupload bhi kr skte hai ) .. 




# Now there are two ways to upload file to cloud server :- 

1. Take the file from the user using multer and directly upload it to cloudinary's server using their sdk .
2. Take the file from the user using multer ... temporary store it into our own server ( so that cloudinary mai upload krane mai problem aayi to retry kr skte hai ) .. and then upload to cloud 


## we are going with 2nd way , so :- 

1. we will make a file in utils folder ... jiska kaam kya hai ki ==localhost pe uploaded  file/asset ko cloudinary pe dalna hai==
2. agar file upload ho gyi successfully unke server mai to hamare se hata do 
3. else , dubara try kro unke server mai daalne ka .


## Q. How to delete a file from local server ?
## Ans. Using "fs" module in node js , we can unlink the file from fs ( read more about it ... but in short baat ye hai ki file ka refn/pointer chala jata hai .. ab file not accessible but original data / content rehta hai jab tk rewrite na kro uss jagah koi nayi chiz ) 





# Q. How to store the file in local server ?

## Ans. with the help of multer .... it is written as middleware on specific route jaha jaha need aygi file upload ka .

```
memory mai bhi store kr skte hai ... ya disk storage mai bhi , we will go with disk storage ( read about it )
```

1. create a storage instance which takes .. destination to store the file + fileName to store as ( fileName thoda unique har time to avoid overwriting agar ek naam ki 3 file aayi toh ).
2. create a multer instance using this storage . 
3. export it 


### To use it , just use it as a middleWare on whatever route you want like :- 

```js
app.post('/upload', upload.single('file'), (req, res) => {
  console.log(req.file);
  res.send('File uploaded!');
});
```




# Q. How to send the local file to cloudinary ?
## 1. config the cloudinary sdk  with name , key and secret .
## 2. time lgega sdk ko + fs se deal kr rhe hai .. try catch is needed

## 3. accept the localPath in the fn and upload the file to cloudinary using upload method ... it takes the filePath and additional params ( if you want )

## 4. time lgega is liye await .. and ye method pura detail return krta hai about the uploaded file , like naam , height , width , size , type , ==PUBLIC URL==  etc etc etc  .
## 5. delete krdo agar ho gaya to ... else return null




