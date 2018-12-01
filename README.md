# DockerManual

## docker install in Ubuntu 18.04
 - $ sudo apt-get update
 - $ sudo apt install docker-ce

### install a specific version of docker-ce
 - $ sudo apt-get install docker-ce=\<VERSION\>

## Add Docker's official GPG key:
 $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

### verify fingerprint
 $ sudo apt-key fingerprint 0EBFCD88


## docker daemon이 자동 실행될 수 있도록 설정 
 - $ sudo systemctl enable docker

## check it running 
 - $ sudo systemctl status docker

## Executing the Docker Command without sudo
 - $ sudo usermod -aG docker ${USER}

## To apply the new group membership, log out of the server and back in, or type the following:
 - $ su - ${USER}

## Confirm user id is now added to the docker group by typing: 
 - $ id -nG

## Docker daemon start
 - $ sudo service docker start

## docker daemon start
 - $ sudo /etc/init.d/docker start

## docker daemon restart
 - $ sudo service docker restart

## Add the docker group
 - $ sudo groupadd docker 

## Add self to the docker group
 - $ sudo gpasswd -a myusername docker

## update docker client to know docker host
 - $ docker -H localhost:2375 images

## persistent env update
 - echo "export DOCKER_HOST=localhost:2375" >> ~/.bash_profile

## Delete all stopped containers
 - $ docker rm $(docker ps -a -q)
