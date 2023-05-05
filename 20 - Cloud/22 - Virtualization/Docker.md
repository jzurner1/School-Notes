### Architecture
Docker uses a client/server architecture, where the client component talks to the server component using a REST API. The server, also known as the Docker engine, sits in the background and takes care of building and running Docker containers.

# Concepts
A **docker image** is a read-only immutable template that defines how a container will be realized. A **docker container** is a runtime instance of a docker image that gets created when the `docker run` command is implemented.

# Installation
### Ubuntu
First, install the necessary docker files using the `apt` command:
`apt install docker.io`

Next, check if the installation worked by checking the version and running the hello-world image:
`docker --version`
`docker run hello-world`

Before running any docker commands, you may have to start docker if it has not been previously started since the last startup.

# Commands
Run an installed image: `docker run <image name>`
List installed images: `docker images`
Delete an installed image: `docker image rm <image name>`
Delete all installed images: `docker image rm $(docker ps -a -q)`

List running containers: `docker ps`
List all containers: `docker ps -a`
Stop a container: `docker stop <container name>`
Stop all containers: `docker stop $(docker ps -a -q)`
See the logs of a container: `docker logs <container name>`