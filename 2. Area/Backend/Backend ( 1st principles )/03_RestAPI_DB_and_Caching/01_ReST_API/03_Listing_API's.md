---
tags:
  - ReST-API
  - BFFP
  - backend
  - api
---


## Some things to keep in mind while building listing api's like list all books etc 

```js
// simple get all orgs 
localhost:3000/oraganisations

// with pagination
localhost:3000/oraganisations?limit=5&page=2

// sorting
localhost:3000/organisation?sortBy=name
localhost:3000/organisation?sortOrder=asc

// filtering
localhost:3000/organisation?status=active
```

#### 1. Pagination :- ( so that ek sath 1000 data na bhjna pde ,api slow hoga )
- accept "limit" and "page" as query params 
- limit : by default any number like 10
- page : 1 by default ofc


#### 2. Sorting  :- 
- accept "sortBy" : by default "createdAt" rkh skte 
- "sortOrder" : asc/desc ( by default , "desc" )


#### 3. Filter :- 
- filter param : by default show all 
- like status = "active" wahi orgs



# One imp tip : "use default values on every not so imp fields so that client se aaye ya naa aaye , we have defaults , ofc name , email nai rkhenge default but you get it"



## Also one more good practice in list ==all== api calls :- 

- suppose we dont have any books to list 
- instead of sending 404 , we ==generally== prefer to send 200 
- and the response looks something like this 
- send 404 when getting one particular or some particular books but not there

```js
{
	"data" : [],  
	"total" : 0,  // eg : total number of orgs 
	"page" : 1 ,
	"totalPages" : 0
}
```

