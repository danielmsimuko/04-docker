## Running Containers 

`$ docker run hello-world` runs the hello world image 

### Swarm 

Swarm allows you to build a distributed cluster of docker machines to run containers. This is useful for orchestration, high availability, and scaling. 

`$ sudo docker swarm init` initialises a new docker swarm cluster 

`$ sudo docker node ls` prints out docker swarm info

`docker swarm init --advertise-addr <swarm manager private IP` initiates a docker swarm manager

Output to the command then allows for worker nodes to be made available using command: 

```
docker swarm join --token SWMTKN-1-2javq7ub3fhf1dtjz6piwg17rw8ffvkgz2h27e2zistnv628co-dr0ymhq1sj3ib5obztchntrkt 10.0.1.101:2377
```
You can confirm if the node has joined to: `docker node ls`

the output should be: 

```
cloud_user@ip-10-0-1-101:~$ sudo docker node ls
ID                            HOSTNAME        STATUS    AVAILABILITY   MANAGER STATUS   ENGINE VERSION
wl14y8fs9b7mp9hgvgqxc8el7 *   ip-10-0-1-101   Ready     Active         Leader           20.10.21
tq9fj6yhz44c7utddwgs775k1     ip-10-0-1-102   Ready     Active                          20.10.21

```
