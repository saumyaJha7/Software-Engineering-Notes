---
tags:
  - DB
  - backend
  - pg
  - drizzle
---


## Q. Three ways to setup db ?

#### 1. Download db 
#### 2. Use cloud based pg 
- latency
- cost ( in future )

#### 3. Docker  ( we are using this )

- check docker --version 
- make docker-compose.yml 
- write whatever in the doc or check khud ka file( search postgres docker )
- after that , run docker compose up -d
- docker compose down for stopping it




## Q. Drizzle setup ? ( checkout docs as well side by side )

- go to their web and follow the project structure 
- drizzle folder : all the structure / schema 
- drizzle.config.js ( on root ) : drizzle ka config 
- npm init -y :
- npm i drizzle-orm pg dotenv
- npm i -D drizzle-kit
- .env 


### then make src/db/index.js  -> import dotenv and db instance 

```pgsql
url =  postgres://<username>:<password>@<host>:<port>/<db_name>
```



### then define schema in drizzle folder 


### then we have to define drizzle config (  modify acc to file structure )



### now schema bna to diya wo pg ko batana bhi pdega so run

```js
npx drizzle-kit push
```

#### Read the schema and create a table in pg 

## to view that , dizzle provides a ui ... run npx drizzle-kit studio ( open in chrome )




#### - if any user is created , it will reflect in the ui as well 








