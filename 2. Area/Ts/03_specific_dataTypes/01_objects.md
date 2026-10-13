---
tags:
  - ts
---

## 1. generally whenever we give more values it doesn't have any issue !!


```ts
type Cup = {
  size: string;
};

const myChai = {
  size: "small",
  name: "Masala chai",
};

const myChai2: Cup = myChai;
console.log(myChai2);
```




## 2. custom types ka array

```ts
type Item = { name: string; quantity: number };
type Address = { street: string };
  
type Order = {
  id: string;
  items: Item[];
  address: Address;
};
```


# 3. optional updates ( imp )

- baaki props same rkhni ho bs ek do hi change krna ho tb

```ts
const updateUser = (changes : Partial<User>) => {
	// logic
}
```



# 4. required 

```ts
type User = {
	name? : string
}

const getUser = ( user : Required<User>) => {
	// ab jab bhi ye fn call kroge name dena hi pdega
}
```


