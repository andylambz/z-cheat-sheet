# Docker cheat sheet

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
```
