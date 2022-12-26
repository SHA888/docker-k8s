# Docker and Kubernetes

## Docker CLI Cheat Sheet - Management

|       |     |
| ----- |-----|
| `docker info` | Display system information |
| `docker version` | Display the system's information |
| `docker login` | Log in to a Docker registry |

## Docker CLI Cheat Sheet - Running and Stopping
|       |     |
| ----- |-----|
| `docker pull [imageName]` | Pull an image from a registry |
| `docker run [imageName]` | Run containers |
| `docker run -d [imageName]` | Detached mode |
| `docker start [containerName]` | Start stopped containers |
| `docker ps` | List running containers | 
| `docker ps -a` | List running and stopped containers | 
| `docker stop [containerName]` | Stop containers | 
| `docker kill [containerName]` | Kill containers |
| `docker image inspect [imageName]` | Get image info |

## Docker CLI Cheat Sheet - Limits
|       |     |
| ----- |-----|
| `docker run --memory="256m" nginx` | Max memory |
| `docker run --cpus=".5" nginx` | Max CPU |

## Running a container
```bash
# pull and run an nginx server
docker run --publish 80:80 --name webserver nginx

# list the running containers
docker ps

# stop the container
docker stop webserver

# remove the container
docker rm webserver
```

## Docker CLI Cheat Sheet - Attach Shell
|       |     |
| ----- |-----|
| `docker run -it nginx -- /bin/bash` | Attach shell |
| `docker run -it -- microsoft/powershell:nanoserver pwsh.exe` | Attach Powershell |
| `docker container exec -it [containerName] --bash` | Attach to a running container |

## Let's run an Nginx container

Type the following Docker commands:

### Pull and run an Ngix server
```bash
docker run -d -p 8080:80 --name webserver nginx
```
### List the running containers
```bash
docker ps
```
### List the images