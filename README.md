Part 1 - Dockerize it
---
Overview: Running a website continuously using a docker container
1. How you installed docker + dependencies: Used the following commands: "sudo apt update", "sudo apt install apt-transport-https ca-certificates curl software-properties-common", "curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -", "sudo add-apt-repository "deb [arch-apt-repository] https://download.docker.com/linux/ubuntu bionic stable"". Source: geekflare.com/docker-installation-guide/
2. How to build the container: Use the command "sudo docker build -t my-apache2" Source: hub.docker.com/_/httpd
3. How to run the container: Use the command "sudo docker run -dit --name test myapache2" Source: hub.docker.com/_/httpd
4. How to view the project: Type "52.3.67.147" into your search bar.
