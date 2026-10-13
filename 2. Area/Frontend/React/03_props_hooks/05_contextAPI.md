---
tags:
  - react
---


## Q. Problem ?
### Ans : Props drilling 

- grandchild ko prop ki need hai .. faltu mai parent and grandparent ko bhi pass krna pdega 



## Solution ?
### Ans : 

![[contextAPI|900]]



## Actually context is not outside , rather it is inside in the react dom tree..


![[contextAPI_02|900]]




## Now there are three components in contextAPI :- 



#### 1. creating a context 
#### 2. providing the access to the context 
#### 3. using that context to get the data





## There are two ways to do that :- 

### 1. Do them in one file 

### 2. Or in difn ones ( Usually the folder structure looks like ) :-

##### -  creating a context : in a separate context file
##### - providing the access in App file ( or any main file )
		- we make a Provider function that uses the children prop 
##### - using the context in any file 




# Ab isme techniques ya good practices aati hai jo sochne se ya dekhne se hi aygi ..  like iss code mai kiya hai sir ne 


- themeProvider component 
- value jo pass ki hai wo perfect hai 
- harr part ko alg-alg component mai break kiya hai
- use of children prop bhut ache se ..
- Custom Hook to use the context .. ( khud se bhi kr skte hai har jagah but it is clean )




### Q. How to read values from context ?
### Ans : by useContext hook ( or custom hook that under the hood does this for us )



### Q. How to write or update the values ?
### Ans : What we pass in value is state .... so change the state and you just updated the context value

