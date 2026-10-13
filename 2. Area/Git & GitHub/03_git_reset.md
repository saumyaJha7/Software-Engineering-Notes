---
tags:
  - theory
  - git
---


#### Now let say we have 3 commits and ab head 3rd commit ko point kr rha hai and next commit krenge to uske aage bdh jyga head & so on ... 

#### So if we want to revert to the 1st commit wala state ( may be waha tk sb sahi chal rha tha ) ... so use :- 

```js
git reset <abc>  // commit ID
```

![[git_reset]]



## Iske kya hoga 1st commit wale state mai aa jayngi saari files and jo add kiya  hai code  2nd and 3rd commit mai wo ... as changes show honge mtlb not commited ( Modified )




# Also there is way to delete all the codes added in 2nd and 3rd commit , but usse phir wo permanently loss hoga ..i.e. not recoverable so be aware 

```js
git reset --hard <abc> ;

// generally it is avoided
```
