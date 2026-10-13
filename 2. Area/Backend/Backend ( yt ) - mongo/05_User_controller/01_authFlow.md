---
tags:
  - theory
  - backend
  - thinking
  - auth
---


## Very detailed Convo , : https://chatgpt.com/share/69301310-9fd8-800f-ac99-106325e9c1de


![[auth flow|700]]



## Flow of auth 

### 1. First time registration
- `/auth/register`
    - Save user.
    - Either:
        - Just 200 → frontend goes to `/login`, or
        - Issue AT + RT + cookies (auto-login).
    
### 2. Login
- `/auth/login`
    - Email + password.
    - If ok → generate AT + RT.
    - Store hashed RT in DB.
    - Set cookies.
    - Frontend now considers user “logged in”.
    
### 3. Normal API calls
- Protected routes use `authMiddleware`.
- If AT valid → pass.
- If AT expired/missing → 401 → frontend calls `/auth/refresh`.

### 4. Refresh
- `/auth/refresh`
    - Check RT from cookie & DB.
    - If valid → new AT (+ RT), set cookies.
    - If invalid/expired → 401 → frontend redirects to `/login`.