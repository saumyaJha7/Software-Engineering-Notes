---
tags:
  - DB
  - backend
---


## Hamesha data kya lene wale hai user se ispe charcha phle honi chahiye coz , agar ek bhi field baad mai add krna pda  to pura logic , save krne ka tarika etc change krna pdega.



### Note : "Hamesha data save krne ka phle socho rather than validation " - Register over Login
![[data_modelling_basics|600]]



## Phle khud ke dimag mai clear krna hai ki kaise store krna hai , broader idea ki kya kaise hoga  . ==Draw as much as you can==



## Consider an example ki todos , banana hai . 

- First point is not kaha aur kaise db mai store krunga
- Sbse phle kya kya store krunga 



### Note : It is good practice to store the fileName as user.models.js rather than user.js . (==js file hi hai bas file dekh ke pata chal rha hai ki kya hoga usme==)






### Note : Jo bhi aap naam doge model ka like "User" , "Todo" wo mongo db jab store krta hai to standardise krta hai usko to 

- lowerCase
- Plural
### For ex: "User" -> "users" or "Todo" -> "todos" or "categories" -> "categories"


## Created at and updated at itni common fields hai ki mongoose directly support krta hai bas {timestamps : true} krdo and dono field ban jayengi . ( link : https://mongoosejs.com/docs/timestamps.html)
