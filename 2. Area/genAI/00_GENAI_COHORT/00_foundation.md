---
tags:
  - genAi
  - llm
  - ai
---
### 1. GPT : Engine 

### 2. Chatgpt , Claude , Gemini : Car ( built on top of that engine )


![llm_foundation](../../../excalidraw/llm_foundation.md)




## The engine works on a principle called transformers :- 


```
computers only understand maths , they can predict maths pattern therefore all this is done. 
```


### 1. Tokenisation
- brk text to small tokens 

### 2. Vector embeddings 
- tokens to vectors 

### 3. Positional Encoding 
- har token ka position info 
- Cat chase dog  && Dog chase cat : both same token nd vector embeddings but position alg 

### 4. Self attention 
- look for each tokens position nd form meaning 

### 5. Feed Forward ( Neural Networks )
- NN se pass kro 

### 6. Output Prediction 
- finally , model predicts the probab of next token


## 7. Next token ko input mai append krlo and then again Repeat this process continuously till end token  


