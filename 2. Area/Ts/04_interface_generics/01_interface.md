---
tags:
  - ts
---

## Interface : to give a shape to our data or objects




```ts
interface Phone {
  battery: number;
  name: string;
}
```



# but isme fn ka bhi structure store kr skte hai 


```ts
interface DiscountCalculator {
  (discountPercentage: number): number;
  // dP as input ( num ) and return bhi num krega
}
```


