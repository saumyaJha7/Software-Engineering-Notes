---
tags:
  - react
---


```js
// title hai to render ... nai to nai + 0 pe 0 render krega
title && (
  <h3 className="text-xl font-bold mb-3 text-gray-800">
    {title}
  </h3>
)

// else is there + 0 pe nai chalega 
title
  ? <h3 className="text-xl font-bold mb-3 text-gray-800">{title}</h3>
  : null
```




## Q. What is children prop ?
### Ans. Any jsx that is passed inside the component ... 


### For eg. let's say <Container/> function accepts children as prop ..

```js
function Container({children , text}){
	return (
		<>
			<h1> {text} </h1>
			<p> {children} </p>
		</>
	)
}
```

## So here "Container" component/function accepts two props .. one is title and one is children 



```html
<Container title="Demo"> 
	<h1> Hi this is h1 </h1>
</Container>
```

## In this case children prop mai pura h1 jyga 

```html
{children} = <h1> Hi this is h1 </h1>
```




# Why we use it ?
## - For arranging components
## - By breaking them into subParts





### In case of the example taken in class :- 


#### 1. Container component :

	- iska role hai arrange krna bas layout mai 
	- layout change krenge to alignment change hota rhega 
	- iss case mai , iske children mai saare cards component aynge
	- line 50-95 is = {children}


#### 2. Card component :-

	- this is for root level implementation 
	- ( isme css add kr skte hai for common or may be based on props )
	- iske liye children hai jo bhi ham bhj rhe hai like 3 p tags ya buttons 



### 3. ChildrenProps (  main ) component :- 

	 - iska role hai to again apply css at top level ( iss file mai )
	 - and arrange the components as per need 



![childrenProps](../../../../excalidraw/childrenProps.md)




# how it can be used is ... ==we may have an array and we can show the details in different cards .. like arr.map inside the container and each ele = each card==


