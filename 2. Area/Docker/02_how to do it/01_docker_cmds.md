---
tags:
  - docker
---
	
## Docker engine ( daemon ) is the main brain which does all the things and we communicate with it using cli :- 


#### 1. docker : to get all the cmds 



#### 2. docker ps : list all running containers 
```js
docker ps --all // to get all the containers 
```


#### 3. docker images : 
```js
docker images --help  // --help kahi bhi lgane se other cmd visible
```




#### 4. docker run : it creates and runs the container with specified image 
```js
docker run -it <imageName>

// -it : "direct uss machine ka terminal open kro jo run ho rhi hai"
```



#### 5. Docker images cmds :- 


###### 1. pulling an image for future purpose ( not spinning any container or running it )
```js
docker pull <imageName>
```

- pulling from where ? hub.docker.com   ->  github for images 


###### 2. removing any image 
```js
docker image rm <imageName>
```





#### 6. Docker containers cmds :- 

```js
docker container --help
```

###### 1.  to give name to container  : --name my-container
```js
docker run -it --name my-container ubuntu
```

###### 2. to kill the container : 

-  stop the container but data is there 
- it is like shutdown your machine 
```js
docker kill <containerId>
```

###### 3. to remove the container :- 

- deleting the container 
- data ofc gone 
- it is like machine tod diya ya phek diya whatever ( destroying your machine )
```js
docker rm <containerId>
```


##### 4. to restart the container after killing it :- 

```js
docker restart <id>
```







