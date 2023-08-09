# Docker Notes

Docker community edition is free OS Docker Engine 

## Installation + Config

Installing on a CentOS 7 Server: 

First remove any already existing docker images via: 

```
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```
To then install the latest version of docker: 

```
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Confirm that docker is running: 

```
sudo systemctl start docker
```
To runa a test hello world container

```
sudo docker run hello-world
```
this will produce an output that looks like: 

``` 
daniel@NT2201LB:~$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
719385e32342: Pull complete
Digest: sha256:c2e20
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
```
## Other Common commands 

to check the status of docker: 

```
daniel@NT2201LB:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Mon 2023-06-19 10:51:03 BST; 3min 21s ago
```
