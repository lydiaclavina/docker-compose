# docker-compose
* vagrant ssh docker
* cd /vagrant
* docker-compose up -d
* docker ps
* Check if port forwarding works
  1. curl localhost:8080 : displays
 => </h1>Welcome to tomcat from centos in docker</h1>
    </p>Hello</p>
  ii. browse localhost:8080 in browser: displays
  => Welcome to tomcat from centos in docker 
  Hello
* docker container exec -it lyd-mysql /bin/bash
  1. mysql -u root -p
   => enter root password specified in .env file
  2. logged in to mysql
  => mysql> show databases;
  => tododb should be present
