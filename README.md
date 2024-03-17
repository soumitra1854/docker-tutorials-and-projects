# Docker-Tutorial
This Readme file contains the necessary commands used in docker.
- sudo systemctl start docker -> to start docker engine
- sudo systemctl stop docker -> to stop docker
- docker images -> to see all docker images installed in our local machine
- docker run image -> to start a new image as a container
- docker run -it name/image_id /bin/bash -> to run a container a enter in it
- systemctl disable/enable docker -> to allow to run at boot-up
- exit -> in a conatiner to stop running the conatiner and exit if started with run command
- docker stop container_id -> to stop a running container 
- docker start container_id -> to start a stopped container
- docker exec -it/itd container_id /bin/bash -> to enter into a running container, itd for detach mode so when press exit not stop container
- ctrl+p then ctrl+q -> to exit a container without stopping from running
- docker container prune -> to remove all stopped containers

