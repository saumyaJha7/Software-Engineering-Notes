---
tags:
  - thinking
  - backend
  - actualLearning
  - assignment
---




# Task 1 : get User ne kinko subscribe kiya hai 

- get subs Id and validate it
- match krlo model mai jaha subs  === subsId
- lookup krlo and get the channel ( user ) ki jo detail chahiye wahi le lo
- empty ke liye handle krlo
- return the channel list only . 



# Task 2 : get user ke subscribers 

- get the channel Id and validate 
- match the docs where channel === channel ID
- similar as above 
- ==bas facet ke andar wrap kiya and count field add ki==


# Task 3 : toggle subscription

- get channel Id and validate
- find kro doc jisme channelId and subcriber match kre
- mile to delete krdo ( unsubscribe )
- nai mile to create krdo ( subscribe )
- handle errors and return res
