---
tags:
  - theory
  - models
  - data_modelling
  - backend
  - DB
  - thinking
---

![eCommerce_models_01](../../../../excalidraw/eCommerce_models_01.md)

## This is what I thought but :-

## User : 
1. User jab phli baar ayga to address thodi na dalega 
2. User ka email and pass to lena hi hai , bhale otp login ho

## Product :
1. Stock kitna hai can be added 
2. description about it.
3. Image kaise bhul gaya

#### For image : - 
1. Not the best practice to store the image directly to db as it overheads the db.
2. we store in aws bucket or cloudinary etc 


## Cart : ( Sir ne nahi liya tha but le skte hai can be used when user added to the cart and right now not ordering and wants to order after 1 day)
1. coupons abhi hata de wo order krne ke time dekhte hai 
2. user kon hai 
3. totalPrice kitna hai 



## And also order ka bhi rkhna pdega na , ki kya order diya hai usme address wagerah aayga .



![eCommerce_models_02](../../../../excalidraw/eCommerce_models_02.md)



## I had two questions at this time :- 

1. Do we need category model ?
2. Doesn't we need cart model ?


## Got the answer :- 

1. yes 100 percent because linking is required .
2. you can , but not best approach because for this only temporary db's exists like redis .


# For detailed convo : [[Why questions on models|gemini convo]]


## So the final model list is :- 

1. User 
2. Category
3. Product
4. Order

# And orderSchema mai bhut kch hai jo mai soch nai paya tha like :- paymentStatus , orderStatus etc etc + ek aur model banana pdega orderItems because [[why orderItems model]]

### Because yeh kahi aur use nai hoga ek hi file bana skte hai coz order schema mai hi use hoga.


## Read this for understanding orderSchema : [[orderSchema]]




 
