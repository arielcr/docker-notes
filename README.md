# Docker Notes

## Build an image
```
$ docker image build . -t myimage:1.0.0
```

## Run a container
```
$ docker container run -d -p 8080:80 --name=myWebServer myimage:1.0.0
```

## Pass parameters to docker run
```
$ docker container run myweb:3 4.4.4.4
```

## Run docker container on random port (uses port on EXPOSE)
*- d -> runs in background*
```
$ docker container run -d -P myweb:4
```

## List running containers
```
$ docker container ls
```

## Stop a container
```
$ docker container stop 0e1b4831cf32
```

## Specify Dockerfile name
```
$ docker image build -f Dockerfile.prod . -t custom:1
```

## Build image from remote location
```
$ docker image build https://github.com/madflojo/automatron.git -t automatron:1
```

## Docker image commands

### List images
```
$ docker image ls
```

### Delete images
```
docker image rm 65d55d448349
```

### Delete all images
```
docker image rm $(docker image ls -aq)
```

## Docker container commands

### List containers
```
$ docker container ls
```

### List running containers
```
$ docker container ps
```

### Stop containers
```
$ docker container stop 65d55d448349
```

### Stop all containers
```
$ docker container stop $(docker container ls -aq)
```

## If you want to remove all dangling images, run:
```
$ docker system prune 
```

## To remove all unused images, not just dangling ones, run:
```
$ docker system prune -a
```

## To remove all unused images not just dangling ones and volumes, run:
```
$ docker system prune -a --volumes
```

## To mount a valume
```
$ docker container run -p 8080:80 -v /Users/ariel/Code/docker/website:/usr/local/apache2/htdocs httpd:2.4
```

## Rename a tag
```
$ docker tag port:1 ariel85/mywebserver:latest 
```

## Go inside container
```
$ docker container exec -it e7ac5d7668e9 /bin/bash
```

## To push an image to the repository
```
$ docker image push ariel85/mywebserver:latest
```

## To pull an image to the repository
```
$ docker image pull ariel85/mywebserver:latest
```

## View image history (layers)
```
$ docker image history port:1
```

## View image info
```
$ docker image inspect port:1
```

