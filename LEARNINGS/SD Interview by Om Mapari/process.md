


## R-E-A-D-D  principle 





1. Requirements : 
		- understand this first ( ask or tell )
		- Functional Requirements ( what system should consist )
		- Non Functional Requirements ( how should system behave )



2. core Entities : 
		- analyse FR
		- based on that , design 3-4 tables initially
		- keep it simple , core features 



3. API's : 
		- analyse FR nd Entities 
		- design core intutive API's that are must 




4. high level Design : 
		- not too complex initially 
		- start with basics 
		- client , server , db 
		- build bottom up 
		- MOST IMP POINT here is to **tell the limitation of your current system**



5. Deep Dive : 
		- solve the NFRs here like scalibility , low latency etc 
		- scale db
		- read replicas
		- sharding 
		- message queues
		- api gateway
		- ALB
		- cache 
		- s3
		- other optimisation techniques , eg : precompute feed whenever user's friend post gets created so that when user open's insta , no need to calculate at that moment 
		- CDNs for celebrity problem
	