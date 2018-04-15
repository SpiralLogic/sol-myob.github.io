---
layout: post
title:  "Kata Koda - Docker Notes"
date:   2018-03-26 09:00:01 +1100
tags: ["docker","katacoda.com"]
---

#Docker Notes.
Docker Notes and tips from the KataCoda.com docter interactive tutorials

## Notes
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
