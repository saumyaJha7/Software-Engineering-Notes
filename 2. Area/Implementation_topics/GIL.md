---
tags:
  - theory
  - gil
---



##  problem : Python uses CPython (the default implementation).
### CPython manages memory internally.
### If multiple threads changed the same memory at the same time ([[race condition]])→ chaos (corruption, crashes).


## Solution: Python uses a Global Interpreter Lock (GIL).
### GIL = a lock that allows only one thread to execute Python bytecode at a time.
### Even if you have 10 threads, only one runs Python code at a time, then GIL switches to another thread.



👉 So in Python: Threads don’t give true parallelism for CPU-heavy work (because of GIL).
But threads are still great for I/O-bound tasks (networking, file reading), since waiting doesn’t need the CPU.

```
🔑 Example analogy:- 

Imagine a kitchen (CPU).
You have 5 cooks (threads).
But there’s only one knife (GIL).
So even though you have 5 cooks, only 1 can chop at a time.
But while one is chopping, others can still boil water (I/O tasks).
```