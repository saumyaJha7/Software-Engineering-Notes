---
tags:
  - next
  - better-auth
  - auth
---
# ==v7 mai changes hue hai , and this is v6 ka code so be aware==


## 1. npm i better-auth


## 2. set url & key in .env


## 3. inside lib folder , create auth.js 


(==for prisma setup ==) : (https://claude.ai/chat/d23a699b-3f1f-4da6-9cc3-236c4be3965c)
## 4. install prisma && prisma/client 


## 5. get the pg url from neon and store in .env

- https://chatgpt.com/g/g-p-6911d8d7e0f48191baee043e09b52030-backend/c/69c510ab-7124-8320-aa0e-431e9a391e41


## 6. npx prisma init

- update the schema.prisma  
- and run npx prisma generate
- this generates a folder called "generated" in src

### 6.1 : this is next js , so edge runtime therefore we have check phle se db connection hai kya so make one db.js inside lib folder 

```js
import { PrismaClient } from "@/generated/prisma/client";

const globalForPrisma = globalThis;

export const db = globalForPrisma.prisma ?? new PrismaClient();

if (process.env.NODE_ENV !== "production") globalForPrisma.prisma = db;
```

## 7. in auth.js , create the basic setup 

```js
import { betterAuth } from "better-auth";
import { prismaAdapter } from "better-auth/adapters/prisma";
import { db } from "@/lib/db.js";

export const auth = betterAuth({
  database: prismaAdapter(db, {
    provider: "postgresql",
  }),
});
```



## 8.  npx @better-auth/cli generate ( to create users , sessions etc tables )

- also migrate : npx prisma db push



## 9. provide google & github id + secret in .env 

- https://better-auth.com/docs/authentication/google
- https://better-auth.com/docs/authentication/github
- or search google better auth





