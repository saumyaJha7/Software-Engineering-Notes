---
tags:
  - ts
---

## 1. We can make custom types 

```ts
type MasalaChai = { type: "MasalaChai"; sugar: number };
type GingerChai = { type: "GingerChai"; ginger: number };

type Chai = MasalaChai | GingerChai;  

// now we know chai is of Type of Chai ( consistency )
function serveChai(chai: Chai) {
  if (chai.type === "MasalaChai") {
    console.log("Masala chai with " + chai.sugar + " sugar");
  } else if (chai.type === "GingerChai") {
    console.log("Ginger chai with " + chai.ginger + " ginger");
  }
}
```



## 2. Forceful Type  assertions 

 - sometimes we have to forcefully tell tsc that type is string or whatever

```ts
let order: any = "1234";

// this will work but suggestion nai aa rhe coz tsc don't know it's type
// let orderLength : number = order.length;

let orderLength: number = (order as string).length;
// here we are forcefully telling tsc that it's a string
```


- one more example ki let say data localstorage mai stored hai .. 

```ts
type book = {
  name: string;
};

let bookStringFromLocalStorage = '{"name": "Sophie's World"}';
let bookObject = JSON.parse(bookStringFromLocalStorage) as book;

// .name suggestion tbhi milega jab tsc ko data type pta hoga
console.log(bookObject.name);
```





## 3. Interface 

- [[interface vs type | read this for understanding the difference between types and interface]]




## 4. Intersection 

```ts
type Wheel = { wheelCount: number };
type Engine = { engineCount: number };
  
type Car = Wheel & Engine;
  
// error coz dono chahiye
// const myCar : Car = {
//     wheelCount : 4,
// }

const myCar: Car = {
  wheelCount: 4,
  engineCount: 2,
};
```



## 5. ReadOnly

- ek baar jo assign ho gya bas uske baad no change

```ts
type Product = {
  name: string;
  readonly price: number;
};

const p1 : Product = {
    name : "laptop",
    price : 10000
}
  
p1.name = "mobile"
// p1.price = 22   // this will give error coz price is readonly
```





