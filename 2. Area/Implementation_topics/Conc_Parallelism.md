---
tags:
  - async
  - Threading
  - Concurrency
  - theory
aliases:
  - Read more about them
---
```
Concurrency == Threading
Parallalism == Multi-Proccessing
```

## -  What is [[Concurrency]] and [[parallelism]]?


# Quick Difference

## Concurrency = "I can handle multiple tasks, but one at a time, switching quickly."

## Parallelism = "I have multiple workers, so tasks actually run simultaneously."



![[threads_process| 600]]
1. ek hi process mai multiple threads hote hai 
2. process hi multiple hote hai isliye ... 
								a) data sharing ni hota , process 1 apna change krta hai and so no .... ( soln : use queue,pipes etc)
								b) main method mai btana pdta hai kaha se execution start kre

```
Concurrency: asyncio, threading → Good for waiting tasks (like network requests).
Parallelism: multiprocessing → Good for CPU-heavy tasks (like crunching numbers).
```


