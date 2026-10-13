---
tags:
  - react
---

## useRef = useState without re-renders 



- like it stores the state 
- but when it changes , no re-rendering happens 
- it is used to refn dom ele directly



```js
import { useRef } from "react";


export default function demo() {
  const myRef = useRef(null);  // refn declaration


  function focusInput() {
    myRef.current.focus();   // to focus on the refn
  }


  function getInputValue() {
    console.log(myRef.current.value);
  }


  return (
    <>
      <input ref={myRef} onChange={getInputValue} /> // now it's refn to this input
      <button onClick={focusInput}>Focus on input </button>
    </>
  );
}
```



# Why we need forwardRef ?

## By default , useRef works only on dom components only.. not on custom ones ..


#### therefore to solve this issue forwardRef is used ..

```js
function MyInput() {
  return <input />;
}

const ref = useRef(null);
<MyInput ref={ref} />   // ❌ ref won't reach the input
```


### Example using forwardRef :-

```js
import {useRef, forwardRef } from "react";

const CustomInput = forwardRef((props, ref) => {
  return <input ref={ref} {...props} />;
});

function App() {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <>
      <CustomInput ref={inputRef} />
      <button onClick={focusInput}>Focus</button>
    </>
  );
}
```



## CustomInput mai ref use kr paa rhe hai coz usme forwardRef use kiya hai 


