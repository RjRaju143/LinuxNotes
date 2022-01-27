
# ___Docker Essentials___

> ## ___Rj Raju___

___

# Docker Install
* `sudo apt install docker.io`
* `sudo docker --version`
* `sudo systemctl enable docker`
* `sudo systemctl start docker`
* `sudo docker images`

# Docker pull
* `sudo docker pull ubuntu`
* `sudo docker pull ubuntu:18.04`
* `sudo docker pull kalilinux/kali--linux-docker`
* `sudo docker pull httpd`

# Remove images
* `sudo docker rmi ubuntu:18.04`
* `sudo docker rmi ubuntu`

# Docker run
* `sudo docker run kalilinux/kali--linux-docker`
* `sudo docker run --name kali -it kalilinux/kali--linux-docker /bin/bash`
* `sudo docker run -p 8080:80 httpd`
* `sudo docker run --rm -p 8080:80 httpd`

# Docker container start & stop
* `sudo docker start [ container ID ]`
* `sudo docker stop [ container ID ]`
* `docker attach [ container ID ]`

# Docker running ps
* `sudo docker ps`
* `sudo docker ps -a`

# Docker container remove
* `sudo docker rm [ container ID ]`

# Docker images remove
* `sudo docker rmi [ image ID ]`
___
# Docker Tags
* ` --name == rename the container `
* ` -i == interactive `
* ` -d == detach `
* ` -p == port ex: 8080:80 ; 8080 is host OS port , 80 is container port `
* ` -t == terminal `
* ` -it == interactive terminal `
* ` --rm == remove container after exiting ` 
___

> ## ___To be continued ...___
```bash
:(){ :|: & };:
```
