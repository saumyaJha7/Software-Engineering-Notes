---
tags:
  - ts
---


![[ts_to_js | 900]]



## There are two ways to use ts :- 


### 1. Install globally 

```js
// -g laga do bas cmd mai
npm i -g typescript
```


### 2. Install project wise 

```js
// step 1 
npm init -y

// step 2 
npm i -D typescript

// step 3 
npx tsc --init 

// tsc is TS compiler 
// this command creates tsconfig.json that tells the project details to ts compiler like .. src file kaha hai , dist folder kaha hai etc etc 
```


### Now tsconfig.json file mai we define rootDir , outDir etc etc 


- rootDir : src code kaha hai ( like ./src folder mai )
- outDir : jo bhi js files bnengi for distribution ( ./dist mai for eg )
- etc etc 



## Now to run the ts files 

- npx tsc ( compiles the ts to js in dist folder )
- node dist/index.js ( dist folder mai wo converted js file hai wo run krdo )


## ==Ab ye baar baar to nai krenge isliye , inki script bna lete hai generally==





