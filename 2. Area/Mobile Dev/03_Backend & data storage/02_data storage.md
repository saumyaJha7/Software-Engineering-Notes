---
tags:
  - react-native
  - backend
---
https://gregarious-gray-075.notion.site/Data-Storage-Offline-Support-369c3158e38d80528978f188265c9ff2


## 1. AsyncStorage 

- it is local storage system for rn & expo apps
- key value store 
- persistent ( data remains even after app close , reload or device restart )


##### Features :- 

- local 
- persistent 
- unEncrypted ( therefore no sesitive data simple things here )
- string hi store krta hai ( so obj store krne ke liye json.stringify() )



##### UseCase :- 

- darkMode 
- user's some preference 
- loginState




## 2. SecureStorage 


- similar to asyncStorage bas secure 


##### UseCase :- 

- senstive data 
- tokens 
- passwords etc 



### Use async as a general choice ... ( read when to use sync )





## 3. SQLite 


- light weight local db 
- stores in actual rows and cols 


#### UseCase :- 

- good for large data
- offline first apps 



#### use async 






## 4. expo-file-system 


- module to interact with device ka local fs


- read more about in the notion notes 