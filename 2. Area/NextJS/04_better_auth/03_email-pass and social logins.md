---
tags:
  - next
  - better-auth
  - auth
---

## In the auth.js file write whatever methods you want for singup and login like email ,pass or github etc etc 


### For email and pass , the syntax is :- 

```js
import { betterAuth } from "better-auth";

export const auth = betterAuth({
  //...other options
  emailAndPassword: { 
    enabled: true, 
  },  
});
```

### Read for other socialProviders like google , github or any other also 