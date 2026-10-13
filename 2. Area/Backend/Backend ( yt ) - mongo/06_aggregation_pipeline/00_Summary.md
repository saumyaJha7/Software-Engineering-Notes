---
tags:
  - backend
  - mongo
  - aggregate
---

# Aggregation pipelines are what makes mongo powerful ... use it wisely and you can do wonders with the data , get the data acc to you with any condition 


# ==Study each topic ache se .. mongo's docs with playground and gpt thorough prompt ... kya kya kr skte sb with ex==




##  1. Group : groups based on certain condition 

```js
[
	{
		$group : {
			_id: "$city",  
			totalCount : { $sum : 1 }  // 1 here is accumulator mtlb ek doc mile to previous value mai 1 add kr dena and hence total count 
		}
	}
]
```


- this groups based on city mtlb ... groups bn jaynge of docs with count 
- ek group hoga "mumbai" , "delhi" etc 
- can calculate avg of certain grp ya max , min etc kch bhi ... sort , limit 


##### Also you can give _id as null  , usse saare docs group ho jynge ( if needed whole doc )






## 2. Unwind : Dealing with arrays 

- rip aparts the array and make it single obj 




## 3. Accumulators like ... sum and push 




## 4. Match with all operator 