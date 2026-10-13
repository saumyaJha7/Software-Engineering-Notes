---
tags:
  - ts
---
# ==read more about it and use-cases==

## Ye code ko re-usable bnane ke kaam aate hai .. 



```ts
function wrapInArray<T>(item: T): T[] {
  return [item];
}
console.log(wrapInArray("masala"));
```



```ts
function pair<A, B>(a: A, b: B): [A, B] {
  return [a, b];
}
```


## Generic interfaces 

```ts
interface Box<T> {
  size: T;
}
const myBox: Box<string> = { size: "small" };
```