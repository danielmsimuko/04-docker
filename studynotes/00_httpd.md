PS C:\Users\daniel.msimuko> ssh cloud_user@3.83.64.78

[cloud_user@ip-10-0-1-224 ~]$ docker version
Client: Docker Engine - Community
 Version:           24.0.2
 API version:       1.43

[cloud_user@ip-10-0-1-224 ~]$ docker pull httpd:latest
latest: Pulling from library/httpd
5b5fe70539cd: Pull complete

[cloud_user@ip-10-0-1-224 ~]$ docker run --name httpd -p 8080:80 -d httpd:latest
51d9e1e2874b072aabefbbe8528feddeda8567f9d0346374d83473c314a5b190

[cloud_user@ip-10-0-1-224 ~]$ docker ps
CONTAINER ID   IMAGE          COMMAND              CREATED         STATUS         PORTS                                   NAMES
51d9e1e2874b   httpd:latest   "httpd-foreground"   6 seconds ago   Up 5 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   httpd

[cloud_user@ip-10-0-1-224 ~]$
