---
tags:
  - backend
  - expo
  - react-native
---

## Expo = UI + routing 


#### But also it provides backend routes to be written directly inside the same folder 


- similar to next js routes
- deployed on cloudflare edges ( so same prblm ki db connected hai guarantee nai hai .. so have to check each time )
- less control than actual backend 








- can read about it more :- 
  
https://gregarious-gray-075.notion.site/Networking-Backend-Integration-369c3158e38d808bbfcaef22bbca8bc0

https://chatgpt.com/g/g-p-69fd72aa379c8191afa95830f8ca4383-mobile-dev/c/6a606157-93dc-83e8-bc6e-a4b32480d4f2




# My opinion + it is suggested also that backend should be seperate .


### Now we have two options :-



1. normal express backend 
2. BaaS ( to know more read gpt convo )



### BaaS : pre-built services to make our life easy 

- so that same code repeat na krna pde har project mai 
- and also , no need to offload everything 
- agar lge apna db , to don't use supabase db 
- agar lge s3 storage nai , then use supabase ka storage 

#### It is all about use case ( read more about it in gpt )



### Simple thumb rule :- 

- simple CRUD things , directly call supbase from the app itself ( RLS hai so no worry )
- kch business logic hai ya sensitive secrets hai etc to backend ko call kro app se and backend will internally do all the math ( be it custom logic , calling supabase or stripe whatever )


When starting a project, I ask:
### Does this feature make my product unique?

If **No**
Delegate it.

Examples
- Login
- Storage
- Email verification

---

If **Yes**
Own it.

Examples
- Recommendation algorithm
- Workout scoring
- Expense categorization



Don't become attached to either approach.

Instead, think like an architect.

When someone says:
> "We're using Supabase."

Your first thought should be:
> **Which parts of Supabase?**



