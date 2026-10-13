---
tags:
  - theory
  - Concurrency
  - Parallalism
  - Threading
  - async
  - gil
---
## Q. What is Concurrency ?
### Ans : Concurrency = one person (only **one core** is involved)doing multiple tasks but exaclty not at same time , **SWITCHING BETWEEN TASKS EFFICIENTLY**

## Q. Example of  Concurrency ?
### Ans : Think of a single person cooking food:

-  You put rice on the stove.
-  While it’s cooking, instead of just standing there, you start chopping vegetables.

    Then you check the rice again, then stir the curry, then wash some dishes.
- You’re switching tasks quickly, not actually doing them at the same exact time, but it feels like multiple things are happening together.

```python
import threading
import time

def take_orders():
    for i in range(1, 4):
        print(f"Taking order for #{i}")
        time.sleep(2) # maan lo yaha koi db call hai
        
def brew_chai():
    for i in range(1, 4):
        print(f"Brewing chai for #{i}")
        time.sleep(3) # koi process ho rha hai

# create threads
# Threads = lightweight workers that can do tasks concurrently.
order_thread = threading.Thread(target=take_orders)
brew_thread = threading.Thread(target=brew_chai)

# starting the threads
order_thread.start() # order_thread will execute the take_order fn in backGround
brew_thread.start() # ye brew_chai execute krega BACKGROUND m , SIMULTANEOUSLY
#  Now both functions are running at the same time (concurrently).

# wait for BOTH to finish
order_thread.join()
brew_thread.join()
# Without join(), the program could exit before threads finish their work.

# What this code does is : dono fn ek sath chalata hai jb jis fn ka kaam ho jata hai to thread uspe dhyan deta hai while the other process is running in the background
print(f"All orders taken and chai brewed")
```