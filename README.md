docker
======

Dockerfile's

#Example
##Build image  
>cd ubuntu\_utopic\_ssh  
>docker build -t ubuntu\_utopic\_ssh .    
>docker images  
>docker run -d --name ssh -p 22 ubuntu\_utopic\_ssh  

##Test image:     
>ssh root@localhost -p49153  
