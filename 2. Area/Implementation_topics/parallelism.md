---
tags:
  - Parallalism
  - gil
---
## What is parallelism ?
### Ans : Diffn people (in our case **multiple cores**) , doing difn things at exact same time !

## Q. Example of  parallelism ?
### Ans : Now imagine you have two cooks in the kitchen:

   -  One person cooks rice.
   - Another person chops vegetables.
   - Both are happening truly at the same time.


```python
from multiprocessing import Process
import time

def brew_chai(name):
    print(f"Start of {name} chai brewing")
    time.sleep(3)
    print(f"End of {name} chai brewing")

if __name__ == "__main__":
    # Simple list comprehension
    chai_makers = [ Process(target=brew_chai, args=(f"#{chai}", )) for chai in ["Ginger" , "Lemon" , "Peach"]  ]
    # chai_makers = [
    #               Process(target=brew_chai, args=(f"#{chai}", ))
    #               for chai in ["Ginger" , "Lemon" , "Peach"]  
    # ]
    
    # Start all process
    for p in chai_makers:
        p.start()
    # 3 processes are running the same time using difn cores

    # wait for all to complete
    for p in chai_makers:
        p.join() # this tells the main program to wait here until this process finishes.

    print("All chai served")

# Without multiprocessing:
#   Ginger chai: 3s
#   Lemon chai: 3s
#   Peach chai: 3s
#   Total = 9s (one after another).

# With multiprocessing:
#   All three start together.
#   Each takes 3s.
#   Total = ~3s 🎉
```


## Note : Always use **dunder_main_** while using multiprocessing because there is generally an error of not knowing where to start in the case of parallalism !