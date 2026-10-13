---
tags:
  - code_notes
  - backend
---


# Password hashing :- 

1. we write it generally in the models files only.
2. we want to hash the pass just before saving the user ( ==when first time login or updating the user's password ONLY ==)
3. So .. pre **middleWare** is used of express .. which runs just before an event ( ==like save , delete==)
4. One main thing , don't use arrow function here as it doesn't have the context ( no this ) .. 
5. Also time lgta hai to use async await .


```
1. bcrypt.hash(what to hash , how many rounds of algo run) .. 
2. password must be encrypted only and only if .. there is a change in the passsword or new user , not when someone changes there avatar name or something ..
   
3. To check change hua hai ya ni ... use this.isModified() method and iske andarr yaad rkhna ki string mai dena hai field ka naaam like ("password") 

4. Also jab check krna hoga ki password sahi hai ya ni tb bhi to decrypt krna pdega and check krna pdega .. so we can add it userSchema only by using .methods prop .
```




# JWT :- 

```
ham sirf refresh token rkhte hai .. coz access (jwt) token to server create krega and client's browser ko dega & expire ho jyga 1hr mai phir generate krega .. so on 
```

1. dono tokens ka secret and expiry .env mai store kro.
2. userSchema mai do method add kro .. generate accessToken and refreshToken 
3. accessToken generate method mai thoda payload bhjte hai generally 
4. refreshToken generate method mai payload ke naam p sirf id bhte hai 


```
Q. How to generate these jwt tokens ?
Ans. jwt.sign() method does that .. it takes generally three parameter payload , secret and expiry .

Note : payload mai data db se aa rha hai  . ( this keyword ki wajah se , that's why we used normal fn not arrow )
```




