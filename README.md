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
```bash
docker images
```

### Attach to the container
```bash
docker container exec -it webserver bash
```

### Exit from the container
```bash
exit
```

### Stop the container
```bash
docker stop webserver
```

### Remove the container from memory
```bash
docker rm webserver
```

### Remove the image
```bash
docker rmi nginx
```

## Docker CLI Cheat Sheet - Building

|       |     |
| ----- |-----|
| `docker build -t [name:tag] .` | Build an image using a Dockerfile located in the same folder |
| `docker build -t [name:tag] -f [fileName]` | Build an image using a Docker file located in a different folder |
| `docker tag [imageName] [name:tag]` | Tag an existing image |

### Dockerfile - static HTML site
```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

### Build the image
```bash
docker build -t webserver-image:v1 .
```

### Run the container
```bash
docker run -d -p 8080:80 --name webserver-container webserver-image:v1
```

### Display the running containers
```bash
curl localhost:8080
```

### Dockerfile - Node site
```dockerfile
FROM alpine
RUN apk add --update nodejs nodejs-npm
COPY . /src
WORKDIR /src
RUN npm install
EXPOSE 8080
ENTRYPOINT ["node", "./app.js"]
```

## Docker CLI - Tagging
```dockerfile
- docker tag => Create a target image
  - name:gat
    - myimage:v1
  - repository/name:tag
    - myacr.azureerc.io/myimage:v1
```