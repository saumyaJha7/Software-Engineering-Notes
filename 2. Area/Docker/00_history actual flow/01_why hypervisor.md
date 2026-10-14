---
tags:
  - containarisation
  - docker
  - VM
---


## "There was a time when on one server only one OS used to run and often the RAM nd CPU were idle ."


![need of containarisation](../../../excalidraw/need of containarisation.md)

## Now we install OS on top of it , and run any node app for example .

- here the point is that node app might not be using full ram , cpu or disk 
- so our resources are not getting used 
- coz ek server pe ek hi OS etc 


![need of containarisation 2](../../../excalidraw/need of containarisation 2.md)


## then came the hypervisor software , which was the resource management software which made it possible to use only ==certain part of ram , cpu and disk== for our app and also run it is isolated env 




# Hypervisor is great and used in aws , gcp etc etc ... this is similar to what they do 

- divide the actual hardware into segments 
- give you the isolated env in a big hardware 

### bas problem was that it is very heavy software ,


# so there was a need for something fast and light weight so that we dont have to fully install any OS , there comes docker  



