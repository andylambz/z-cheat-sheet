# Docker cheat sheet

#### Example
```sh
// Centos
$ docker pull centos
$ docker run centos
$ docker run -i -t centos
[root@4f0b435cdbd7 /]# exit
```
#### Show
```sh
// Show both running and stopped containers
docker ps -a
```

#### Build
```sh
// Build an image from the Dockerfile in the current directory and tag the image
docker build -t myimage:1.0 .

// List all images that are locally stored with the Docker Engine
docker image ls

// Delete an image from the local image store
docker image rm alpine:3.4
```

#### Run
```sh
// Run a container from the Alpine version 3.9 image, name the running container “web”
// and expose port 5000 externally, mapped to port 80 inside the container.
docker container run --name web -p 5000:80 alpine:3.9

// Stop a running container through SIGTERM
docker container stop web

// Stop a running container through SIGKILL
docker container kill web

// List the networks
docker network ls

// List the running containers (add --all to include stopped containers)
docker container ls

// Delete all running and stopped containers
docker container rm -f $(docker ps -aq)

// Print the last 100 lines of a container’s logs
docker container logs --tail 100 web
```

#### Share
```sh
// Pull an image from a registry
docker pull myimage:1.0

// Retag a local image with a new image name and tag
docker tag myimage:1.0 myrepo/myimage:2.0

// Push an image to a registry
docker push myrepo/myimage:2.0
```

#### Clean up
```sh
// Clean all
docker system prune
docker system prune -a

// Stop all running containers
docker stop $(docker ps -a -q)

// Delete stopped containers
docker container prune

// Images
docker image prune [-a]

// Volumes
docker volume prune
```
