---
tags:
  - theory
  - async
  - Threading
---



## Q. What is async IO ?
### Ans : it is to wait for the task to complete while we do the other tasks in the event loop and when that task is done we will execute that as well ..... 


## Q. Advantages of  async IO ?
### 1.  **non-blocking code** = Instead of waiting for each HTTP request one by one, you can fire off 100 requests and let them finish as responses come in.

### 2. **great** for IO tasks . 

## So in short , it does efficient handling of many I/O-bound tasks with less overhead, cleaner code, and better scalability than threads or blocking code.


## Example code :- 

```python
import asyncio

# co-routine = special fn that can be paused (wo fn jisme async laga ho = co-routine )
async def task1():
    print("Task1 started")
    await asyncio.sleep(3)   # pretend waiting for DB
    print("Task1 finished")

async def task2():
    print("Task2 started")
    await asyncio.sleep(1)   # await keyword is for waiting (like time.sleep()) but non-blocking .. 
    print("Task2 finished")

async def main():
    # Run both tasks concurrently
    await asyncio.gather(task1(), task2())

asyncio.run(main())

```


```python
Task1 started
Task2 started
Task2 finished   # finishes first because it slept only 1 sec
Task1 finished   # finishes later

# ➡️ Here, instead of blocking 3+1 = 4 seconds, total time = ~3 seconds.  
# Because while Task1 is waiting for 3 seconds, Task2 executes.
```
