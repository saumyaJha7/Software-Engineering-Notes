---
tags:
  - BFFP
  - server
  - backend
---


![handler_services etc](../../../../excalidraw/handler_services%20etc.png)




# What a handler/controller does ?

- gets the data ( converts bytes to readable format .. js mai to middleware lgane se ho jaata hai , other languages mai khud krna pdta hai )
- run the validators and transform the data acc to your conveince 
- business logic in modular way ( 1 method 1 job )
- db calls efficienlty 
- return the response with proper msg and status codes 



### What is the job of middlewares ?

##### 1. to execute common functions wherever req.
##### 2. some of the common use cases are :- 

	- security checking : cors ( if same origin to set one header etc ) , auth 
	- logging and monitoring 
	- rate limiting ( very imp )
	- auth middlewares 




