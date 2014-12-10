
##Build image  
>cd ubuntu\_utopic\_redis  
>docker build -t ubuntu\_utopic\_redis .    
>docker images  
>docker run -d -p 6379:6379 -p 22 -v /data/redis:/data/redis ubuntu\_utopic\_redis

##Usage
>redis-cli -p6379

