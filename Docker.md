🟡 Docker Installation on Amazon Linux / RHEL / CentOS

| Command                        | Single Line Explanation           |
| ------------------------------ | --------------------------------- |
| `sudo yum update -y`           | Updates all system packages.      |
| `sudo yum install docker -y`   | Installs Docker package.          |
| `sudo systemctl start docker`  | Starts Docker service.            |
| `sudo systemctl enable docker` | Enables Docker at system startup. |
| `docker --version`             | Checks installed Docker version.  |
| `docker run hello-world`       | Verifies Docker installation.     |

(For newer systems use sudo dnf install docker -y instead of yum.)


🟢 Docker Installation on Ubuntu

sudo apt update --------> Updates the system package index

sudo apt install ca-certificates curl gnupg -y -------> Installs required dependencies for Docker.

sudo apt update ---------> Refreshes package list including Docker repository.

sudo systemctl start docker   -------->  Starts the Docker service.

sudo systemctl enable docker      -------->  Enables Docker to start automatically on system boot.

docker --version     ------->  Verifies installed Docker version.

docker run hello-world      ------>  Tests Docker installation by running a sample container.

sudo usermod -aG docker $USER    ----->  	Adds current user to Docker group to avoid using sudo.

🟢 DOCKER BASIC COMMANDS

| Command            | Single Line Explanation                            |
| ------------------ | -------------------------------------------------- |
| `docker --version` | Shows the installed Docker version.                |
| `docker version`   | Displays Docker client and server version details. |
| `docker info`      | Shows system-wide Docker information.              |
| `docker help`      | Lists all Docker commands.                         |
| `docker login`     | Logs in to Docker Hub.                             |
| `docker logout`    | Logs out from Docker Hub.                          |


🟡 DOCKER IMAGE COMMANDS

| Command                         | Single Line Explanation                             |
| ------------------------------- | --------------------------------------------------- |
| `docker pull image`             | Downloads an image from Docker Hub.                 |
| `docker images`                 | Lists all locally available images.                 |
| `docker rmi image_id`           | Removes an image from local system.                 |
| `docker build -t name .`        | Builds an image from a Dockerfile.                  |
| `docker tag source target`      | Tags an image with a new name.                      |
| `docker push image`             | Pushes an image to Docker Hub.                      |
| `docker inspect image`          | Displays detailed image information in JSON format. |
| `docker history image`          | Shows image layer history.                          |
| `docker save -o file.tar image` | Saves an image as a tar archive.                    |
| `docker load -i file.tar`       | Loads an image from a tar archive.                  |


🔵 DOCKER CONTAINER COMMANDS

| Command                          | Single Line Explanation                       |
| -------------------------------- | --------------------------------------------- |
| `docker run image`               | Creates and starts a new container.           |
| `docker run -d image`            | Runs container in detached mode (background). |
| `docker run -it image bash`      | Runs container in interactive terminal mode.  |
| `docker ps`                      | Lists running containers.                     |
| `docker ps -a`                   | Lists all containers including stopped ones.  |
| `docker stop container`          | Stops a running container.                    |
| `docker start container`         | Starts a stopped container.                   |
| `docker restart container`       | Restarts a container.                         |
| `docker rm container`            | Removes a container.                          |
| `docker exec -it container bash` | Accesses a running container interactively.   |
| `docker logs container`          | Displays container logs.                      |
| `docker logs -f container`       | Shows live streaming logs of container.       |
| `docker top container`           | Displays running processes inside container.  |
| `docker stats`                   | Shows real-time container resource usage.     |
| `docker inspect container`       | Shows detailed container information.         |
| `docker rename old new`          | Renames a container.                          |
| `docker pause container`         | Pauses a running container.                   |
| `docker unpause container`       | Resumes a paused container.                   |
| `docker attach container`        | Attaches terminal to running container.       |

🟣 PORT MAPPING & VOLUMES

| Command                              | Single Line Explanation                   |
| ------------------------------------ | ----------------------------------------- |
| `docker run -p 8080:80 image`        | Maps host port 8080 to container port 80. |
| `docker run -P image`                | Maps all exposed ports automatically.     |
| `docker run -v host:container image` | Mounts a host directory inside container. |
| `docker volume create name`          | Creates a Docker volume.                  |
| `docker volume ls`                   | Lists all Docker volumes.                 |
| `docker volume inspect name`         | Shows detailed volume information.        |
| `docker volume rm name`              | Removes a Docker volume.                  |
| `docker volume prune`                | Removes unused volumes.                   |


🔴 DOCKER NETWORK COMMANDS

| Command                           | Single Line Explanation               |
| --------------------------------- | ------------------------------------- |
| `docker network ls`               | Lists Docker networks.                |
| `docker network create name`      | Creates a new network.                |
| `docker network inspect name`     | Shows detailed network information.   |
| `docker network rm name`          | Removes a Docker network.             |
| `docker run --network=name image` | Runs container in a specific network. |

🟠 DOCKER COMPOSE COMMANDS (New Syntax)

| Command                  | Single Line Explanation                        |
| ------------------------ | ---------------------------------------------- |
| `docker compose up`      | Starts services defined in docker-compose.yml. |
| `docker compose up -d`   | Starts services in background mode.            |
| `docker compose down`    | Stops and removes services.                    |
| `docker compose ps`      | Lists running compose services.                |
| `docker compose logs`    | Shows logs of compose services.                |
| `docker compose build`   | Builds services defined in compose file.       |
| `docker compose restart` | Restarts compose services.                     |


🟤 DOCKER SYSTEM CLEANUP

| Command                  | Single Line Explanation                             |
| ------------------------ | --------------------------------------------------- |
| `docker system df`       | Shows Docker disk usage.                            |
| `docker system prune`    | Removes unused data (containers, images, networks). |
| `docker container prune` | Removes all stopped containers.                     |
| `docker image prune`     | Removes unused images.                              |
| `docker network prune`   | Removes unused networks.                            |

🟢 ADVANCED DOCKER COMMANDS

| Command                                 | Single Line Explanation                         |
| --------------------------------------- | ----------------------------------------------- |
| `docker run --name name image`          | Assigns a custom name to container.             |
| `docker run --restart=always image`     | Automatically restarts container on failure.    |
| `docker update --memory 500m container` | Updates container resource limits.              |
| `docker cp file container:/path`        | Copies file into container.                     |
| `docker commit container image`         | Creates new image from container.               |
| `docker events`                         | Shows real-time Docker events.                  |
| `docker diff container`                 | Shows changes made inside container filesystem. |
| `docker export container > file.tar`    | Exports container filesystem as tar.            |
| `docker import file.tar image`          | Imports tar file as Docker image.               |


🔥 MOST IMPORTANT FOR DEVOPS INTERVIEW

docker build

docker run

docker exec

docker logs

docker compose up

docker push

docker system prune

docker inspect
