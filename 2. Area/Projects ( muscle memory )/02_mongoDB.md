

# Made a simple html page to get the email and name of users and performed insert and get operations .




# Things i learned :- 



### 1. cors error is real thing ... 

- frontend (html) : localhost:5500
- backend ( port = 3000) : localhost : 3000

- so faced the cors error ... therefore to solve it 
- install cors package , use as middleware in app.js ( with origin of ur frontend in this case 5500)

- ==One more point , localhost != 127.0.0.1 ... kahi kahi prblm aa skti hai to use ip everywhere==




### 2. Frontend se simple fetch ya axios req krni hoti hai .. with full url and boom frontend & backend is connected !!




### 3. **ODM is not the best in all condition .. everything is a trade off , ==understand this==**

- ODM : faster dev speed + easy schema + etc etc 
- Native drivers : more control + low latency ( not visible in small apps but very large apps mai )

- one more thing like , ODM use krne se thoda sa overhead aata hai coz ek aur layer is there ( latency in very high big apps like 100k req/sec)

- ODM : client -> ODM -> native driver -> MongoDB
- W/o ODM : client -> native driver -> MongoDB


