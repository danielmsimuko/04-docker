## Running Containers 

`$ docker run hello-world` runs the hello world image 

### Swarm 

Swarm allows you to build a distributed cluster of docker machines to run containers. This is useful for orchestration, high availability, and scaling. 

`$ sudo docker swarm init` initialises a new docker swarm cluster 

`$ sudo docker node ls` prints out docker swarm info
