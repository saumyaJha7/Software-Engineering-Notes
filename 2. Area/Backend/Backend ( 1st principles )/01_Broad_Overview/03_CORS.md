---
tags:
  - CORS
  - BFFP
  - thinking
---
## https://chatgpt.com/g/g-p-6965c66158d88191bf53156a1fd46088-full-stack-overview/c/69dcdfbf-a134-8322-9795-bcc978cf2140


## CORS mai do type ke req hai :- 

### 1. Simple req 

![[https_cors_flow_simple_req| 900]]
- Browser is the enforcer ... backend just res ki allowed hai ya nai 



### 2. Preflighted req ( 3 mai se koi ek condition )

- methods : PUT , PATCH , DELETE 
- Header : Auth / custom headers 
- Content-Type : app/json

![[http_cors_flow_preflight_req | 900]]




# ==Directly test the things practically , make a server and test it in network tab!==


https://aws.amazon.com/what-is/cross-origin-resource-sharing/

https://www.geeksforgeeks.org/websites-apps/cross-origin-resource-sharing-cors/



### " Most of the req we make is preflight req as content-type : json is considered a pre-flight req"

