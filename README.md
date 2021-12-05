Part 1 - Dockerize it
---

Overview: Running a website continuously using a docker container.

Source for index.html: Project 5's index.srv1.html.

Source for Dockerfile: https://hub.docker.com/_/httpd
1. How you installed docker + dependencies: Used the following commands: "sudo apt update", "sudo apt install apt-transport-https ca-certificates curl software-properties-common", "curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -", "sudo add-apt-repository "deb [arch-apt-repository] https://download.docker.com/linux/ubuntu bionic stable"". Source: https://geekflare.com/docker-installation-guide/
2. How to build the container: Use the command "sudo docker build -t my-apache2" Source: https://hub.docker.com/_/httpd
3. How to run the container: Use the command "sudo docker run -dit --name test myapache2" Source: https://hub.docker.com/_/httpd
4. How to view the project: Type "52.3.67.147" into your search bar.

Part 2 - GitHub Actions and DockerHub
---

1. Process to create DockerHub public repo: I created a free account, clicked "Create Repository", named my repository "project-6-repo", and then created my repository.
2. Allow DockerHub authentication via CLI using Dockhub credentials:
3. Configure GitHub Secrets
 - What credentials are needed: Username and password for Docker.
 - How to set secrets and secret names: Create a "secrets" environment by going to "Settings", "Environments", then "Create Environment" with the name "secrets" (or any preferred name). Then click "Add Secret" and add your docker username / password under secret labels.
4. Configure GitHub Workflow
 - Variables to change: I created the .yml file in .github/workflows using a default .yml docker file offered by GitHub under the "Actions" tab. I then created an environment that holds the values of the correct username / password from my evironment named secrets that I made before using these lines (separated by /'s): "env: / SECRET_DOCKER_USER: ${{secrets.SECRET_DOCKER_USER}} / SECRET_DOCKER_PASSWORD: ${{secrets.SECRET_DOCKER_PASSWORD}}". I also gave it a place to build in using the line: "run: sudo docker build . --file Dockerfile --tag cicd-elizabethrw/project-6-repo" (the base of this was given by the default .yml docker file). I also added a command to push to DockerHub after building using "run: sudo docker push ${{secrets.SECRET_DOCKER_USER}}/project-6-repo". The .yml file itselfcan be viewed in .github/workflows, and it is titled "docker-image.yml" (name that was given by the default .yml docker file).

Part 3 - Deployment
---

1. How to pull the image: 
2. How to run the container:
