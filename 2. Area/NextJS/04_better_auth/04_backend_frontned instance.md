---
tags:
  - next
  - better-auth
  - auth
---
# 1. ==All backend request comes here==

## Make a "catch all" API  route :- 


📁 `app/api/auth/[...all]/route.js`

```js
import { auth } from "@/lib/auth";  
import { toNextJsHandler } from "better-auth/next-js";  
  
export const { GET, POST } = toNextJsHandler(auth);
```


👉 Why:

- This is the **entry point**
- All auth requests go here:
    
```js
/api/auth/signin  
/api/auth/signup  
/api/auth/session
```



##  2. This is what frontend uses  :- 


📁 `lib/auth-client.js`

```js
import { createAuthClient } from "better-auth/react";  
  
export const authClient = createAuthClient({  
  baseURL: "http://localhost:3000",  
});
```
