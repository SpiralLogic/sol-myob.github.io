Docker Notes:


Download and run a docker image as a container, the -d flag will demonize it:
`docker run -d [image-name]`

List running docker containers:
`docker ps`

Expose a port from the container to the host (by default the ip address is the local host):
`docker run -p 127.0.0.1:6379:6379 [image-name]`

Exposing a folder to the docker image using a volume:
`docker run -v /opt/docker/data/redis:/data redis`

Run docker container interactively
`docker run -it ubuntu bash`
