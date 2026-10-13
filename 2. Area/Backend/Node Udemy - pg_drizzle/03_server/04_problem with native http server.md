---
tags:
  - server
  - node
  - problem
---

## consider the following code :-

```js
const http = require('http')

const server = http.createServer((req,res) => {

    switch(req.url){
        case '/':
            if(req.method === 'GET') res.end("HomePage")

        case '/signUp':
            if(req.method === 'GET') res.end("SignUp form dikha do")
            else if(req.method === 'POST') res.end("Signup krdo")
            else if(req.method === 'DELETE') res.end("Do the desired work")    
            else if(req.method === 'PATCH') res.end("Do the work")
            else res.end("Put ka kaam krdo")
            
        case '/about' :

            // ifelse 5

    }  

})

server.listen(8000)
  
```


## Even this small code is not easy to read and write , therefore to solve this express js came into the picture . 

## Express uses this http module only , but does a lot of behind task to make it easy for us to write code  + built-in bhut saari functionnality deta hai jo native http module ke pass nai hai





