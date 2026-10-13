---
tags:
  - theory
  - vcs
  - git
---
![[vcs_101|700]]


## 1. system mai **git** to hai , and folder bhi hai but sbko thodi trek krega btana pdega ki kya track krna hai ... 

## 2. so inside that folder run this cmd so that git track krna start kre locally iss folder ko 

```js
git init
```

## 3. git track krta hai apne hidden folder mai ... ( .git ) : ye simple fs hai  jisme saare folder/files jo bhi add krenge ham uske changes track krta hai 

## 4. git by default track ni krta files .. usko btana pdta hai ye ye files track kro 

```js
git add <filename>
```

- git init : iss folder ko track krna chalu kro
- git add <> : git iss file ko vc kro 


## 5. Ab staging area se commit krenge to save the checkpoint or snapshot of that file at that moment . 

- har commit ki ek id hoti hai 
```js
git log  // to get the history 

git log --oneline  // to get in oneline
```


# ==ye sab local folder mai hi store ho rha hai ( .git ) ... not kahi aur cloud mai as of now !==

