# DevOps with Docker: part 1 solutions  

Table of contents:
[1.1 Getting started](#11-getting-started)  
[1.2 Cleanup](#12-cleanup)  
[1.3 Secret message](#13-secret-message)
[1.4 Missing dependencies](#14-missing-dependencies)
[1.5 Sizes of images](#15-sizes-of-images)
[1.6 Hello Docker Hub](#16-hello-docker-hub)
[1.7 Two line Dockerfile](#17-two-line-dockerfile)

### 1.1 Getting started  
#### Output:  

```
CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS                          PORTS      NAMES
3d103ae39bff   memcached   "docker-entrypoint.s…"   2 minutes ago    Exited (0) About a minute ago              jolly_mcclintock
700e1db12c49   nginx       "/docker-entrypoint.…"   2 minutes ago    Exited (0) About a minute ago              romantic_germain
5eddc5cf7ca6   redis       "docker-entrypoint.s…"   2 minutes ago    Up 2 minutes                    6379/tcp   peaceful_euler
```

### 1.2 Cleanup:  
#### Outputs:
docker ps -a :`CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES`  
docker images: `REPOSITORY   TAG       IMAGE ID   CREATED   SIZE`

### 1.3 Secret message:
#### Solution:  
```
$ docker run -d -it --name secretmsg devopsdockeruh/simple-web-service:ubuntu
$ docker exec -it secretmsg bash
$ tail -f ./text.log
```
#### Message:  
`You can find the source code here: https://github.com/docker-hy`  

### 1.4 Missing dependencies:
#### Solution:  
Extend the given shell commands to install curl inside the container:  
`docker run -it ubuntu sh -c 'apt-get update; apt-get install curl; echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'`  

### 1.5 Sizes of images
#### Size comparison:  
Ubuntu: 83MB  
Alpine:15.7MB

#### Message: 
`You can find the source code here: https://github.com/docker-hy`

### 1.6 Hello Docker Hub
#### Solution:
```
$ docker run -it devopsdockeruh/pullexercise  
$ basics
```

#### Message:
`This is the secret message`

### 1.7 Two line Dockerfile
[Link to Dockerfile](./files/17_Dockerfile)

#### Solution:  
```
$ docker build -f ./files/17_Dockerfile ./files/ -t web-server
$ docker run web-server
```

### Image for script
[Link to Dockerfile](./files/18_Dockerfile)
