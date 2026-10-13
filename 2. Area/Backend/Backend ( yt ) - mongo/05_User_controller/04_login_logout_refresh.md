---
tags:
  - backend
  - thinking
---


# Steps for login :- 


### 1. get the user details . 
- validate for empty .
### 2. check the details in db .
- db mai hai ya nai email
- email hai to pass sahi hai n
- agar ni to return error
### 3. generate AT + RT . 
- use already declared method using "user"
### 4. store  RT in db . ( better to hash it , par yaha nai kiya hai )
- update the RT
- while saving the user , validateBeforeSave : false .. ( so that mongoose doesn't touch other fields )
### 5. set both in cookie .  ( cookie-parser middleWare on)
- httpOnly and secure true krna
- so that frontend se cookie modify na ho , sirf server se ho .
### 6. return success response 
- jo bhi user ki field nai bhjni hai .. wo select krlo 
- send with standardised ApiResponse 






# Steps for logout :- 

## - Better approach :

### First run the auth middleware , then the actual controller .( ==auth middleWare wala kaam directly kr skte the ... but harr baarr lgega hi aur aise hi routes pe isliye better approach== )

#### In auth middleWare  ( wrap in try-catch coz verify method error deta hai if not valid JWT  , ya expire ho gya toh ):- 
- get the token either from cookie or auth headers 
- check for empty token -> 401 
- else , use jwt.verify() to check for expiry + any changes in data + returns payload .
- get the user with the userId received in payload ( remove pass and RT field )
- attach the user object with req and call next() 

#### Actual controller :-
- get the userId and just remove  the RT field via $unset
- findByIdAndUpdate - read more about it .. 
- clear the AT + RT from cookie and send the success res



## - ==this is what I thought==
### 1. check if cookies are there or not ( req.cookie access kr skte hai coz cookie-parser use kiye hai)
### 2. If no cookies or RT , send 204 -> already loggedOut
### 3. find the user with this RT from db.
### 4. undefined krdo RT ko .
### 5. clear AT + RT from cookie .
- give same options jo set krne ke time diye the


```js
// step 1
  const cookies = req.cookies;
  console.log(cookies);
  if (!cookies)
    return res
      .status(204)
      .json(new ApiResponse(204, cookies, "User is already loggedOut !"));

  
  // step 2
  const refreshToken = cookies?.refreshToken;
  if (!refreshToken)
    return res
      .status(204)
      .json(new ApiResponse(204, cookies, "User is already loggedOut !"));

  // step 3
  const user = await User.findOne({ refreshToken });

  // step 4
  if (user) {
    user.refreshToken = undefined;
    await user.save({ validateBeforeSave: false });
  }

  // step 5

  const options = {
    httpOnly: true,
    secure: true,
  };

  return res
    .status(200)
    .clearCookie("accessToken", options)
    .clearCookie("refreshToken", options)
    .json(new ApiResponse(200, cookies, "User logout successfully !"));
```





# Steps for refreshAt :- 
### 1. get the RT from cookie 
### 2. check for empty -> 401 
### 3. verify RT valid , sahi hai ya nai with verify method 
### 4. check RT with DB wala RT
### 5. generate the AT ( RT as well for security )
### 6. set cookie and send res 
