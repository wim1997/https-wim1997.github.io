## Installation docker
history

first with this command can understand do u have docker in ur system or don;t exist :

      docker status

tell the ur service state:

     systemctl status docker

set shekan :
    
    vim /etc/resolv.conf

if u want set shekan go in this website : set : nameserver 178.22.122.100

was wrong but u know was experience for this task:

    docker pull mysql:latest
    
show the images and versions of docker:

    docker images
    
show image of container mysql  docker :  

    docker images mysql
    
show proccess of docker :
    
   
    docker ps

**connect to mysql docker :

  sudo docker run --name=[container_name] -d mysql/mysql-server:latest

  sudo docker run --name=mysql -d mysql/mysql-server:latest

**run bash mysql_docker:
 
   sudo docker -it mysql_docker bash
   
   sudo docker -it mysql bash
   
   sudo docker exec -it mysql bash
   
   docker run --name=mysql mysql/mysql-server:latest
   
**then restart docker:

   docker restart 
   
** restart container mysql in docker:
   
   docker restart mysql
   
**again run :

  docker run --name=mysql mysql/mysql-server:latest
   
  sudo docker run --name=mysql -d mysql/mysql-server:latest
   
  sudo docker exec -it mysql bash
   
  docker exec -it mysql mysql -uroot -p
   
  docker logs mysql 2>&1 | grep GENERATED
   
   ls

**copy csv file to txt file :

   cp avr.csv avr.txt
   
   cat avr.txt
   
   docker exec -it mysql bash

   cp avr.csv mysql.txt

   docker exec -it mysql mysql -uroot -p

   cp /Documents/ /tmp avr.csv mysql.txt
  
   pwd

   cp  avr.csv mysql.txt /home/wim/Documents /tmp
   
   ls

   cp -r  avr.csv mysql.txt /home/wim/Documents /tmp

   vim test.sh.

   ./test.sh.

   sudo curl -L "https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose.

   docker-compose --version.


   docker run -it --network some-network --rm mysql mysql -hsome-mysql -uexample-user -p

   docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag


   docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag


   docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag

 
   docker run --namemysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag

   docker run --name mysql -e MYSQL_ROOT_PASSWORD=zadi1997 -d mysql:tag

   docker run --name mysql -e MYSQL_ROOT_PASSWORD=zadi1997 -d mysql:latest

   docker ps -a

##my installing mysql in docker was wrong now in this command fix it :

   docker rm --force mysql

   docker rm --force redis

   docker ps -a

   docker create -v awesome:/foo -v /bar --name hello redis

   docker run --name mysql -e MYSQL_ROOT_PASSWORD=zadi1997 -d mysql:latest

   vim stack.yml
    
   docker stack deploy -c stack.yml mysql
  
   apt install wget.
  
   wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb.
  
   sudo apt install ./google-chrome-stable_current_amd64.deb.
  
   vim test.sh
  
   ./test.sh
  
   chmod 777 test.sh 

   apt install docker
  
   apt update
  
   docker cp
  
   systemctl
  
   sudo apt install apt-transport-https ca-certificates curl software-properties-common
  
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  
   sudo systemctl status docker
  
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -.
  
   sudo apt update.

   apt-cache policy docker-ce.

   sudo apt-get install ca-certificates.

  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg.

   sudo apt-get update.

   sudo apt install apt-transport-https ca-certificates curl software-properties-common.

   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -.

  curl -fsSL https://download.docker.com/linux/ubuntu/gpg. 
  
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg.
  
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -.
 
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable".
 
   sudo apt-get update.
 
  apt-cache policy docker-ce.
 
   sudo apt install docker-ce.
 
   docker --version.
 
   docker-compose --version.
 
   docker pull mysql:latest.
 
   docker exec -it mysql.
 
   docker ps.
 
   docker run --name mysql -p 3306:3306 -v mysql_volume:/var/lib/mysql/ -d -e "" mysql.
 
   vim /etc/apt/sources.list.
 
   docker exec -it mysql.
 
   docker images mysql.
 
  vim /etc/resolv.conf. 
 
  docker ps.
 
  docker images mysql.
 
  docker exec -it mysql.
 
  docker exec -it mysql bash.
 
  systemctl status mysql.
 
  sudo docker run mysql -d.
 
  sudo docker run --name=[container_name] -d mysql/mysql-server:latest.
 
  sudo docker run --name=mysql -d mysql/mysql-server:latest.
 
  sudo docker run --name=mysql -d mysql/mysql:latest.
 
  sudo docker run --name=mysql -d mysql/mysql-server:latest.
 
  docker ps.
 
  sudo docker -it mysql_docker bash.
 
  sudo docker -it mysql bash.
 
  sudo docker -it mysql-server bash.
 
  docker ps -a.
 
  docker restart mysql.
 
  sudo docker -it mysql-server bash.
 
  sudo docker -it mysql bash.
 
  sudo docker -it mysql bash -d.
 
  sudo docker exec -it mysql bash. 
 
  docker run --name=mysql mysql/mysql-server:latest.
 
  docker run --name=mysql mysql/mysql:latest.
 
  docker run --name=mysql-server mysql/mysql-server:latest.
 
  docker start es01 es02 es03 kib01. 
  
  docker logs -f kib01.
  
  docker logs -f es01. 
  
  sysctl -w vm.max_map_count=262144.
  
  docker start es01 es02 es03 kib01.
  
  docker logs -f es01.
  
  docker exec -it es01 bash. 
  
  curl -IkXGET http://localhost:9200/_cluster/health.
  
  curl -X PUT "localhost:9200/my-index-000001?pretty".
  
  clear | grep -n 10
  
  clear | tail -10
  
**What is tmux? # Tmux is a terminal multiplexer an alternative to GNU Screen . In other words, it means that you can start a Tmux session and then open multiple windows inside that session. Each window occupies the entire screen and can be split into rectangular panes.
  
  apt install tmux

  tmux