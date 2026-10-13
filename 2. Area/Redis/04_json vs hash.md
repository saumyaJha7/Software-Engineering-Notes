---
tags:
  - redis
  - backend
  - DB
  - caching
---



## There are mainly 2 ways to store value in redis :- 



- in string 
- in hash table 




### 1. String 

- this is done using simple set method
- we can't store json directly there so we have to stringify it while storing 
- and parse it while retrieving 
- now Main pain point is , we can't directly update the fields of json 



##### Let's take an example of user profile :- 

```js
{
	name : "Saumya",
	age : 20,
	city : "Pune"
}
```



##### Now if we stored the value in string , we won't be able to update it ofc 

```js
user:123
   ↓
"{\"name\":\"Saumya\",\"age\":20,\"city\":\"Pune\"}"
```



### 2. Hash table 

- this is done using hset method 
- ye use krne se value hash table mai store hoti hai
- we can update the individual fields as well 
- also kch parse nai krna pdega sidha json ayga 



```js
await redis.hSet("user:123", {
  name: "Saumya",
  age: "20",
  city: "Pune"
});
```


```js
Redis Hash

Key: user:123

Field       Value
-----------------
name        Saumya
age         20
city        Pune
```



#### now we can update the age individually 

```js
await redis.hSet("user:123", "age", "21");
```



### One last thing : the value here stored is also a string ( the value ) ... so when storing or retrieving age , we have to typecast to suitable format.






# Some methods :- 



- set : stores in string 
- hset : stores in hash table 
- hgetAll : returns whole json 
- hget : get one field



