---
tags:
  - redis
  - DB
  - caching
---

So to make live leaderboard . 

We need 4 things mainly 

1. Incrby : to increase single numerical value by any number 

2. Zincby : same as incrby just that is works on sorted sets . 

3. Zrevrank : gives rank of user from high test to lowest marks ( 0 based index ) 

4. Zrevrange : gives list of users im a certain range ( descemdigg , 0 based ) 



## Read more abt them , read code .