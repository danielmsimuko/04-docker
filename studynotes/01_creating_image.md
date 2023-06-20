## Creating a container image file

login to virtual machine: `$ ssh cloud_user@18.234.118.74`

pull latest httpd image: `$ docker pull httpd`

run a demo webtemplate to ensure smooth ops `$ docker run --name webtemplate -d httpd`

now we enter container: `$ docker exec -it webtemplate bash`

update and install git `$ apt update && apt install git -y`
