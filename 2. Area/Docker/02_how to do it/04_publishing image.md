---
tags:
  - docker
---


hub.docker.com   == github for docker images 

( we can publish our images and also pull others as well )



## 1. create a repo 


## 2. build an image with same name as repo ( like username/reponame)

```js
jhasaumya/node-app
```

- or another way is tag kro my-app ko with repo name and then push :- 
			- docker tag my-app jhasaumya/node-app
			- docker push jhasaumya/node-app


## 3. login docker by running 

```js
docker login
```


## 4. push that image to repo 

```js
docker push <imageName>
```



