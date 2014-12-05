Copy from [https://github.com/jcsaaddupuy/docker-pypiserver](https://github.com/jcsaaddupuy/docker-pypiserver "jcsaaddupuy/docker-pypiserver")

##Build image  
>cd ubuntu\_utopic\_pypiserver  
>docker build -t ubuntu\_utopic\_pypiserver .    
>docker images  
>docker run -d -v /data/pypiserver/packages:/data/pypiserver/packages -p 8080:8080 -p 22 ubuntu\_utopic\_pypiserver

##Usage
first, you should modify the pip config file
>vi ~/.pypirc  
[distutils]  
index-servers =  
  coreos    
[coreos]  
repository: http://192.168.131.133:8080  
username: admin  
password: password

then you can upload your own packages to this pypiserver  
>python setup.py sdist upload -r coreos

and download packages  
>pip install plumber -i http://192.168.131.133:8080/simple

