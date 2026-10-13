---
tags:
  - github
---




## Ek hi branch hai "main" and do dev ek sath kaam kr rhe hai to conflict ho skta hai when they will push the code .. that is why branching is there in github!!




![[github_branching|800]]


## 1. To create a new branch 

```js
git branch <branchName>
```


## 2. To change current branch 

```js
git checkout <branchName>
```



# So here is the thing :- 

### 1. main branch mai saara main code rkho jo deployed hai 

### 2. naya branch bnao and work kro usme .. 

### 3. main branch mai abhi kch bhi changes nai dikega .. konsi file bnayi ya kya code update kiya ... kch nai 

### 4. jab kaam ho jaaye to ... ==main== branch se merge command chala do 




# For practically seeing all this concept .. do by yourself on pvt repo .. 


### What I've done here is :-  ( gitllens mai dekh le delete commit ke baad )

- main branch mai 2 commit kiye 
- then 2nd commit ke baad nayi branch bnayi 
- then demo mai jaake usme commit kiye 2 
- then again main mai aake commit kiya "logout code"
- then main se merge krdi demo branch toh ssaare changes demo ke main mai aagye .

##### ==demo branch delete nai hogi khud se ofc merge hone ke baad .. agar krna hai to explicitly krna pdega .. or else we can continue to work on that branch as well ==



![[github_branching_02|700]]
