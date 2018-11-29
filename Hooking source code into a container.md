# Hooking source code into a container

What is a volume?
> Special type of directory in a container typically referred to as a "data volume"
> Can be shared and reused among container
> Updates to an image won't affect a data volume

Creating a data volume
-
The `-v` parameter creates a container volume that points to a path given by docker if the host location is not set
```
docker run -p [host port]:[container port] -v [container volume] [image name]
```
**Example**
```
docker run -p 80:3000 node -v /var/www
```
To find the default path of the volume of a container we run the next comand:
```
docker inspect [container name]
```
This command will output all the information of the container. The volume path can be found in the section of "Mounts".
The host location is indicated in the `Source` key
```json
"Mounts": [
            {
                "Type": "volume",
                "Name": "98358593a56a611c997b24c818e6afb5efe11d66e8298362c15bfe6b562aec5b",
                "Source": "/var/lib/docker/volumes/98358593a56a611c997b24c818e6afb5efe11d66e8298362c15bfe6b562aec5b/_data",
                "Destination": "/var/www",
                "Driver": "local",
                "Mode": "",
                "RW": true,
                "Propagation": ""
            }
        ]
```

The volume will persist even if the container is deleted because another container can be using that volume.
To delete the volume too is necesary run the comand `rm` with the parameter `-v`:
```
docker rm -v [container id]
```

Creating custom data volume
--
To set the location in the docker host, the locations must be provided in the `-v` parameter as can be seen on the next example:
```
docker run -v [location host]:[location container] [image name]
```

```
docker run -p 8080:3000 -v $(pwd):/var/www
```
To set the working directory of a container, it must be indicated with the `-w` and the wanted location
```
docker run -w "[working directory path]" 
```