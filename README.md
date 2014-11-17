docker
======

Dockerfiles

first pull ubuntu:utopic  
> docker pull ubuntu:utopic  

then build the ssh image
> cd ubuntu\_utopic\_ssh/  
> docker build -t ubuntu\_utopic\_ssh .

most of other images are based on ubuntu\_utopic\_ssh