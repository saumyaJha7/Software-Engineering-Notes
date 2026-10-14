---
tags:
  - theory
  - backend
  - auth
---
# **Understand the trade-offs :- **
## ==JWT mai acha hai ye ki fast hai / scalable hai , but security breach ho skti hai ... like youtube etc==
## ==Sessions ka kya fyda hai ki security top notch hai bhale harr barr login krna pd rha hai .. like Banking apps==



# Consider a case :- 

1. First of all , http is stateless ... so it forgets after each req ( ==that means after each refresh also==)
2. So user logins any web at 8 am .
3. User refreshes -> it needs to login again .. 
4. Bad user exp 


# So to solve this ... 

1. Session Tokens : Server mai store krlo identity ... browser ko cookie ( **small data pieces**) mai id de do( for checking ) (==stateful==)

2. JWT : Client ko identity dedo in the form of token .. and server bass token valid hai ya nai check krke .. login krwa dega . ( ==stateless==)



![session tokens](../../../../excalidraw/session tokens.md)
![jwt](../../../../excalidraw/jwt.md)



# So jwt is industry standard  , now another problem is there with jwt :- 

#### Server just checks if the token is valid or not , phir chahe koi bhi bheje ... so jwt leak hua to bhi server nai pakad pyga , Therefore

- tokens must expire shortly .
- but also user must not be asked to login again and again .


### Hence to solve this issue ...  A hybrid approach i.e. two token model is there :- 

1. Access Token : Short span ( jwt ) token used to validate etc etc
2. Refresh Token : Long span token used to generate / refresh access token  



## For detailed convo : https://chatgpt.com/share/69268d95-1c04-800f-a989-4fbd3b59881e

## For very deep and system lvl understanding  : https://youtu.be/j1C8gZkIRKc?si=Qib-UFbrwcQLZTRv





