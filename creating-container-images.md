## Creating a container image file

login to virtual machine: `$ ssh cloud_user@18.234.118.74`

pull latest httpd image: `$ docker pull httpd`

run a demo webtemplate to ensure smooth ops `$ docker run --name webtemplate -d httpd`

now we enter container: `$ docker exec -it webtemplate bash`

update and install git `$ apt update && apt install git -y`

clone website and send it to desired repo 

`$ git clone  https://github.com/linuxacademy/content-widget-factory-inc.git /tmp/widget-factory-inc`

Remove the index.html file using : `$ rm htdocs/index.html`

Copy the webcode from /tmp/ to the htdocs/ folder: `cp -r /tmp/widget-factory-inc/web/* htdocs/`

To create an image from container. We need the container id: `$ docker ps`

```
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS         PORTS     NAMES
65d87d720862   httpd     "httpd-foreground"   6 minutes ago   Up 6 minutes   80/tcp    webtemplate
```

using container id, create docker image:`$ docker commit 65d87d720862 web1`

check docker image has been creaated: `$ docker images`

```
REPOSITORY                 TAG       IMAGE ID       CREATED         SIZE
web1                       latest    b579921b685b   3 seconds ago   189MB
example/widgetfactory.v1   latest    9db82f2f157f   2 minutes ago   278MB
httpd                      latest    ad303d7f80f9   6 days ago      168MB
```

run the image: ``$ docker run -d --name website -p 8081:80 web1``

```
$ docker ps
CONTAINER ID   IMAGE            COMMAND              CREATED          STATUS          PORTS                                   NAMES
45fc25b6fc74   web1             "httpd-foreground"   30 seconds ago   Up 29 seconds   0.0.0.0:8081->80/tcp, :::8081->80/tcp   website
65d87d720862   httpd            "httpd-foreground"   8 minutes ago    Up 8 minutes    80/tcp                                  webtemplate
```
