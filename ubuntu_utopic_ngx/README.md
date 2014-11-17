##Build image  
>cd ubuntu\_utopic\_ngx  
>docker build -t ubuntu\_utopic\_ngx .    
>docker images  
>docker run -i -t -p 80:80 -v /home/core/logs:/var/log/nginx -v /home/core/www:/var/www ubuntu\_utopic\_ngx:latest  
>or  
>docker run -d --name ngx -p 80:80 -v /home/core/logs:/var/log/nginx -v /home/core/www:/var/www ubuntu\_utopic\_ngx:latest

##Test:     
>curl localhost:49154

##Restart:
>docker kill -s SIGHUP ngx