---
tags:
  - msg_broker
  - bg_job
  - sd
---

![[Pasted image 20261007115249.png]]
![[Pasted image 20261007115307.png]]

![[Pasted image 20261007115322.png]]
![[Pasted image 20261007115331.png]]
![[Pasted image 20261007115505.png]]
![[Pasted image 20261007115520.png]]

- generally there is ttl to a msg / job let say 14 days 
- job one came to broker 
- worker picks the task ( email worker )
- but before sending the email it crashed ( retry mechanisms )
- ( so job is read by worker but email is not set , how to handle it )

```
One way of doing it is listed below , different services may have diffn exact ways but the idea is similar to get the retry mechanism 
```

- we do one thing , delete the task from broker only after successfull email send 
- so worker picks the job ( atp do not delete the job from queue )
- worker does the job 
- then it deletes from queue 
- ( nd at the end after some fix days , khud se to job delete hi honi if not explicitly deleted by any worker )


![[Pasted image 20261007115538.png]]
![[Pasted image 20261007115545.png]]
