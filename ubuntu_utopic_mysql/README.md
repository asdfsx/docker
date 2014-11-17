##Build image  
>cd ubuntu\_utopic\_mysql  
>docker build -t ubuntu\_utopic\_mysql .    
>docker images  
>docker run -d --name mysql -p 22 -p 3306:3306 ubuntu\_utopic\_mysql  

##Test image:     
>docker run -it --rm --link mysql:mysql ubuntu\_utopic\_mysql bash -c 'mysql -h $MYSQL\_PORT\_3306\_TCP\_ADDR'
