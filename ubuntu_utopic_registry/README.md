##Build image  
>cd ubuntu\_utopic\_registry  
>docker build -t ubuntu\_utopic\_registry .    
>docker images  
>docker run -d --name registry -p 22 -p 5000:5000 -e STORAGE\_PATH=/registry -e    SQLALCHEMY\_INDEX\_DATABASE=sqlite:////registry/docker-registry.db -v /home/core/registry:/registry ubuntu\_utopic\_registry

##Test image:     
>ssh root@localhost -p49153  
>docker tag ubuntu\_utopic\_ssh localhost:5000/ubuntu\_utopic\_ssh  
>docker push localhost:5000/ubuntu\_utopic\_ssh  
>docker tag ubuntu:utopic localhost:5000/ubuntu:utopic  
>docker push localhost:5000/ubuntu:utopic
