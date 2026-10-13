
```
static files like images / logos / user files etc ke liye use hota hai
```
## 1. Ham images wagerah  store krenge user ka into third party services like AWS ya Cloudinary , now there are two approaches to do that :- 


## 2.1 : user se photo lo and temporarily usko apne server pe rkho , in case koi connection lost ya kch hai to bhi hamare pass photos/videos hai and then baad mai usko third party services mai daalo .

## 2.2 : ya phir directly user ke upload krte hi , cloudinary mai daal do . 



# To bas wahi temp rkhne ke liye we create a public folder and usme temp folder ... and jab bhi kch rkhna hoga temporarily wahi rkh denge . 

### Now the problem is khali folder git track nai krta and track hi nai krega to agar kch change hota hai iss folder mai to prod mai wo reflect kaise hoga ..... so iske liye we create a temp file called .gitkeep in temp folder ..( waise to kch bhi naam de do but ye std hai )

