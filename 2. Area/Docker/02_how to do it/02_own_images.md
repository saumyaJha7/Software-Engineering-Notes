---
tags:
  - docker
---

# Creating own images to solve the actual problem of difn dev env's



- so the case is , I have a project in my machine which has ( node v22.14.0 , npm 11.1.0)
- plan is to make docker image of it and publish it
- and then we can give docker image to all the contributors 
- in that way the problem is solved 




### Step 1 : create a docker file 

- it is a config file 
- it's name should be "Dockerfile"
- what should be there in the file is listed below :- 
```js
1. base image 
2. install node ( run certain cmds )
3. copy the src code ( yaha ka code waha )
```



### Step 2 : built the image 
```js
docker build -t <name> <where is the docker file ( like . means isi folder mai)> 
```

- this cmd reads the docker file 
- and build the image based on that 


#### Now spin a container and boom .... our src code is their as well as all the dev env is also there ... now we can just run the project there 





## Now teen hi file + node install kiya hai uske baad bhi size of image is 500+ mb ... How to optimise it ?


- base image  ( ubuntu ) uska size
- and wo bloated hai ( usme bhut kch hai jo ni chahiye )


### So what is the good practice is :- 

- node js ka hi official image use kro 
- specific version and desired os
- like in our case we've used alpine ( which is very lightweight coz usme faltu ka kch ni hai bas node is running .. like ls etc cmds bhi nai )
- also we can give cmd that will automatically gets executed when container is spun

### Now the size is 200 MB ( less then half )


#### Always use as light base image as possible ( not depended or unused ones )





## one more opt techniques :-

- cache krta hai docker jo bhi change nai hue hai wo 
- to kya kro src code nice rkho and bacha hua upar 
- so that dubara run kre to cache ho max chize




