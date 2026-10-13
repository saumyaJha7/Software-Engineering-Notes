---
tags:
  - redis
  - caching
  - DB
  - task_queue
  - backend
---

## Basic 3 files needed :- 



1. queue.js : queue and connection setup n export 
2. api.js ( producer ) : that adds job in the queue 
3. worker.js : that consumes the jobs 





### ofc api.js and worker dono ke liye server on rkhna pdega seperate .. 