# Docker-Tutorial

This Readme file contains necessary commands used in Docker.

### Managing Docker Service:
- To start the Docker engine: 
  ```bash
  sudo systemctl start docker
  ```
- To stop the Docker engine:
  ```bash
  sudo systemctl stop docker.service docker.socket
  ```
- To enable Docker to start at boot:
  ```bash
  sudo systemctl enable docker 
  ```
- To disable Docker from starting at boot:
  ```bash
  sudo systemctl disable docker
  ```

### Working with Images:
- To build an image from a Dockerfile:
  ```bash
  docker build -t image_name:tag .
  ```
  - Use `.` if Dockerfile is in the current directory else specify the path of the Dockerfile.
- To view all Docker images installed locally: 
  ```bash
  docker images
  ```
- To pull an image from Docker Hub:
  ```bash
  docker pull image_name
  ```
- To remove an image: 
  ```bash
  docker rmi image_id
  ```
- To remove unused images: 
  ```bash
  docker image prune # -a to remove all images
  ```

### Working with Containers:
- To run a container from an image (creating and starting):
  ```bash
  docker run image-repo:tag # tag for any version (optional)
  ```
- To run a container in detached mode (background):
  ```bash
  docker run -d image-repo:tag
  ```
- To run a container and enter into it (interactive mode):
  ```bash
  docker run -it name/image_id /bin/bash
  ```
  - Use `-itd` to run in interactive and detached mode.
- To run a container with a specific name:
  ```bash
  docker run --name container_name -d image-repo:tag
  ```
- To run a container with a specific port:
  ```bash 
  docker run -d -p host_port:container_port image-repo:tag
  ```
- To enter a running container: 
  ```bash
  docker exec -it container_id /bin/bash
  ```
  - Use `-itd` to run in interactive and detached mode (container will not stop when you exit).
  
- To exit a container and stop it:
  - Type `exit` or press `Ctrl+D`.
  
- To exit a container without stopping it: 
  - Press `Ctrl+P` then `Ctrl+Q`.
  
- To stop a running container: 
  ```bash
  docker stop container_id
  ```
  
- To start a stopped container:
  ```bash
  docker start container_id
  ```

- To view all running containers: 
  ```bash
  docker ps
  ```
- To view all containers (including stopped ones):
  ```bash
  docker ps -a
  ```
- To view the logs of a container:
  ```bash
  docker logs container_id
  ```

### Removing Containers:
- To remove a container:
  ```bash
  docker rm container_id
  ```
- To remove all stopped containers:
  ```bash
  docker container prune
  ```

### Other Commands:
- To remove all unused data (containers, images, volumes):
  ```bash
  docker system prune
  ```
- To remove **all** containers, images, networks, and volumes:
  ```bash
  docker system prune -a
  ```
