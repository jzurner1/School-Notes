
### Architecture
Docker uses a client/server architecture, where the client component talks to the server component using a REST API. The server, also known as the Docker engine, sits in the background and takes care of building and running Docker containers.

# Installation
### Ubuntu
First, install the necessary docker files using the `apt` command:
`apt install docker.io`

Next, check if the installation worked by checking the version and running the hello-world image:
`docker --version`
`docker run hello-world`

You can list the images that are currently installed on your device. This should include the hello-world image from the last step:
`docker images`

You can also list the current docker processes that are running. To show all of them, even the ones not running, use the `-a` option:
`docker ps`
`docker ps -a`