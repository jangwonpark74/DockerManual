# DockerManual

## docker install in Ubuntu 18.04
 - $ sudo apt install docker-ce

## check it running 
 - $ sudo systemctl status docker

## Executing the Docker Command without sudo
 - $ sudo usermod -aG docker ${USER}

## To apply the new group membership, log out of the server and back in, or type the following:
 - $ su - ${USER}

## Confirm user id is now added to the docker group by typing: 
 - $ id -nG

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
