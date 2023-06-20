## Creating a container image file

login to virtual machine: `$ ssh cloud_user@18.234.118.74`

pull latest httpd image: `$ docker pull httpd`

run a demo webtemplate to ensure smooth ops `$ docker run --name webtemplate -d httpd`

now we enter container: `$ docker exec -it webtemplate bash`

update and install git `$ apt update && apt install git -y`

clone website and send it to desired repo 

root@65d87d720862:/usr/local/apache2# git clone  https://github.com/linuxacademy/content-widget-factory-inc.git /tmp/widget-factory-inc

List the files in the htdocs/ directory:
ls -l htdocs/
Remove the index.html file:
rm htdocs/index.html
Copy the webcode from /tmp/ to the htdocs/ folder:
cp -r /tmp/widget-factory-inc/web/* htdocs/
