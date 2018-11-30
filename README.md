# DockerManual

## docker daemon start
 - $ sudo /etc/init.d/docker start

## docker daemon restart
 - $ sudo service docker restart

## Add the docker group
 - $ sudo groupadd docker 

## Add self to the docker group
 - $ sudo gpasswd -a myusername docker

## Delete all stopped containers
 - $ docker rm $(docker ps -a -q)
