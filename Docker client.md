# Docker client

Pull an image or a repository from a registry
-
```
doker pull [image name]
```
The docker images can be found in https://hub.docker.com/

Run a command in a new container
-
```
docker run [image name]
```
To set the port for the container to run
```
docker run -p [host port]:[container port] [image name]
```
Stop a container
-
```
docker stop [container id]
```

List images
-
```
docker images
```
#### Output
REPOSITORY|TAG|IMAGE ID|CREATED|SIZE
|:--|--|--|--|--|
|hello-world|latest|4ab4c602aa5e|2 months ago|1.84kB

List containers
---
```
docker ps
```
#### Output
CONTAINER ID|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAMES
|--|--|--|--|--|--|--|
To show all the containers add -a
```
docker ps -a
```
#### Output
CONTAINER ID|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAMES
|--|--|--|--|--|--|--|
494ed773b1e8|hello-world|"/hello"|3 minutes ago|Exited (0) 3 minutes ago| |zealous_yonath

Delete a container
---
```
docker rm [container id]
```
Delete an image
---
```
docker rmi [image id]
```