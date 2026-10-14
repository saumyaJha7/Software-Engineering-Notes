---
tags:
  - theory
  - BFFP
  - backend
  - server
---

![Serialisation_DeSer](../../../../excalidraw/Serialisation_DeSer.md)



## 1. Now Js objects / koi bhi aur data type can't be sent via network .

## 2. Network se sirf byte tfr hote hai .

## 3. So we transform the ==JSON STRING to Bytes== in order to send that bytes over the network 

- this is serialisation : converting data into common format so that both can make sense of it , i.e. language agnostic ( js ka data kiye to rust mai jaake same rhe and vice )

## 4. At Backend , it again is converted from ==Bytes to Rust Struct ( in this case )== 

- this is de-serialisation 

	


# For detail convo : https://chatgpt.com/g/g-p-6965c66158d88191bf53156a1fd46088-full-stack-overview/c/6965c6b8-28a8-8320-acb6-eb26e9de1136


