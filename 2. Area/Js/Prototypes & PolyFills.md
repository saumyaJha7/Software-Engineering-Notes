---
tags:
  - theory
  - thinking
  - js
  - interview
  - job
---

#### **Try all this in browser** 

```js
const arr = [1,2,3];

arr.length;
```

## Length method kaha se aaya , we haven't defined ... 


- Array ki saari functionality Array.prototype mai rhta hai 
- arr object mai add krte hai .__proto_  and similarly baaki data types mai bhi parent se inherit.
- jab bhi koi naya method access krne jaate hai 
- sbse phle wo check krta hai hamne declare kiya kya 
- if not , arr.__proto_.length mai check krta hai 


## So ham uss prototype mai apne methods/fields  bhi add kr skte hai 


```js
Object.prototype.greet = function(){
	console.log("hello");
}

let obj = { name : "Saumya" };

obj.greet(); // it will run coz obj.__proto__ mai wo add ho gaya hoga 
```



# Q. What is pollyfills ?

## Consider the case ki koi js update aaya and kisi browser mai ni chal rha hai i.e.  koi method add kiya js ne like .map and hamne wo use kiya hai but wo kisi browser p ni chal rha hai ... ==tab to hamari website crash ho jygi , to usse bachne ke liye we use our own custom methods==


```js
if(!Array.prototype.greet) {

    // fallback/backup function : POLYFIll
    Array.prototype.greet = function(){
        console.log("hi!");
    }
}
```



## So , there might be question in interview that 

- directly :  " Make a pollyfill function of for-each "
- story form :  " client ke browser mai error aa rha ( .forEach fucntion does not exist on arr variable ) .. so how will you debug it ? "


```js
// check cohort folder in js section
```




#### "Everything in js is object" : coz har chiz ke prototype mai last object kya hai object ...  ( test krle khud se for array , string etc ... Array._proto_ , String._proto__.__proto__)



### Q. Also extend krna class ko means what ? 

- child class ke proto mai parent class dedo 
- bts yahi ho rha hai , so ab koi bole ki inheritance achieve kro without extends keyword so ans is this !