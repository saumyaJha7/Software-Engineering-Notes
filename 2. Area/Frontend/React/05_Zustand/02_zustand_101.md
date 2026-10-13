---
tags:
  - react
  - zustand
  - state-management
---

## 1. Create a store 


```js
import { create } from "zustand";

export const useCounterStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
  decrement: () => set((state) => ({ count: state.count - 1 })),
}));
```





## 2. use the store 



```js
// this is un-optimised as we are subscribing to whole store .. if anything changes our component re-renders 

const { count, increment, decrement } = useCounterStore();
```


- so the better way is to selectively subscribe 

```js
const count = useCounterStore((state) => state.count);
const increment = useCounterStore((state) => state.increment);
const decrement = useCounterStore((state) => state.decrement);
```




