---
tags:
  - github
  - git
---



# Problem :- 

- main branch chal rhi hai 
- ek naayi branch hai feat/b .. usme aapne 20 commit kiye 
- main mai jab merge krne jaoge to saare 20 commits aa jayenge 
- ==un-necessary commits hai , we just need one commit that feat/b done==


## Solution :- 


 - use squash command while merging 
 - it only adds the code changes on the main branch 
 - ==now khud se main branch mai dubara commit kro==
 - sirf wo commit jyga history mai 


```js
git merge --squash demo
```




![github_squash](../../excalidraw/github_squash.md)


## Advantages :- 

- history clean 
- if bug can delete whole feature by removing just one commit 


## Disadvanatages :- 

- if bug , toh debug krna thoda problem hoga .. 
- history to clean ho gyi par detail chala gya uski wajah se 



# So it depends kya krna hai kya nai .. one workaround can be .. ==squash kro but wo branch delete mat kro so that uska history pura uss branch mai rhe and main wala bhi pollute na ho==




