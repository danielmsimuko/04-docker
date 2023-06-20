## Creating a simple html webpage using httpd and nginx via docker containers 

log into vm via: `ssh cloud_user@3.83.64.78`

run `$ docker version` and make sure to get output looking like: 
```
Client: Docker Engine - Community
 Version:           24.0.2
 API version:       1.02
```
pull latest docker image via: `$ docker pull httpd:latest`. output should look like: 

```
latest: Pulling from library/httpd
5b5fe70539cd: Pull complete
```
run a test docker image using httpd via: `$ docker run --name httpd -p 8080:80 -d httpd:latest`
51d9e1e2874b072aabefbbe8528feddeda8567f9d0346374d83473c314a5b190

[cloud_user@ip-10-0-1-224 ~]$ docker ps
CONTAINER ID   IMAGE          COMMAND              CREATED         STATUS         PORTS                                   NAMES
51d9e1e2874b   httpd:latest   "httpd-foreground"   6 seconds ago   Up 5 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   httpd

[cloud_user@ip-10-0-1-224 ~]$ git clone https://github.com/linuxacademy/content-widget-factory-inc
Cloning into 'content-widget-factory-inc'...

[cloud_user@ip-10-0-1-224 ~]$ cd content-widget-factory-inc/

[cloud_user@ip-10-0-1-224 content-widget-factory-inc]$ cd web/

[cloud_user@ip-10-0-1-224 web]$ ll
total 16
drwxrwxr-x. 2 cloud_user cloud_user   76 Jun 20 18:07 img
-rw-rw-r--. 1 cloud_user cloud_user 3059 Jun 20 18:07 index.html
-rw-rw-r--. 1 cloud_user cloud_user 2910 Jun 20 18:07 quote.html
-rw-rw-r--. 1 cloud_user cloud_user 2611 Jun 20 18:07 support.html
-rw-rw-r--. 1 cloud_user cloud_user 2645 Jun 20 18:07 widgets.html

[cloud_user@ip-10-0-1-224 web]$ docker stop httpd
httpd

[cloud_user@ip-10-0-1-224 web]$ docker rm httpd
httpd

[cloud_user@ip-10-0-1-224 web]$
[cloud_user@ip-10-0-1-224 web]$ docker run --name httpd -p 8080:80 -v $(pwd):/usr/local/apache2/htdocs:ro -d httpd:latest
2178165dc2c9b00e6c738c735a00e199e1300b918abc95e09a3270755ca617b7

[cloud_user@ip-10-0-1-224 web]$ docker ps
CONTAINER ID   IMAGE          COMMAND              CREATED          STATUS          PORTS                                   NAMES
2178165dc2c9   httpd:latest   "httpd-foreground"   11 seconds ago   Up 10 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   httpd

