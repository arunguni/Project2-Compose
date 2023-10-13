#Secure DevOps Project
##Overview
This project focuses on the implementation of a Secure DevOps pipeline using Docker, Docker Compose, and Jenkins pipelines. The objective is to establish a streamlined process for continuous integration and deployment of a basic Node.js web application.

##Prerequisites
Linux server running Ubuntu 20.04 with Docker and Docker Compose installed.
Personal GitHub account.
##Tasks
###Task 1: Repository Setup
Fork the repository aws-samples/aws-elastic-beanstalk-express-js-sample into your personal GitHub.
Create a new repository in your personal GitHub called Project2-Compose.
###Task 2: Container and Jenkins Configuration
In the newly created Project2-Compose repository, create a Docker Compose file/stack to run:
A Docker-In-Docker (DinD) container.
A Jenkins container that uses the DinD container to run a Jenkins pipeline.
Commit and push the Docker Compose file to the main branch of the Project2-Compose repository.
###Task 3: Jenkinsfile Creation
In your forked aws-elastic-beanstalk-express-js-sample repository, create a Jenkinsfile in the root of the repo. The Jenkinsfile should:
Use a Node 16 Docker image as the build agent.
Include a build step that runs the command npm install --save.
Commit and push the Jenkinsfile to the main branch of your forked aws-elastic-beanstalk-express-js-sample repo.
###Task 4: Jenkinsfile Pipeline Setup
In your Jenkins setup, follow the provided guide to create a Pipeline project named StudentID_Project2_pipeline (e.g., 123456_Project2_pipeline, where 123456 is your StudentID) which uses the newly created Jenkinsfile for its pipeline definition (make sure you select Pipeline script from SCM option).
Make sure that your pipeline runs successfully (check the pipeline logs).
###Notes
Create Docker network:
Sudo docker network create jenkins
Start Docker-In-Docker container:
sudo docker run --name dind -d \
--network jenkins --network-alias docker \
--privileged \
-u root \
-e DOCKER_TLS_CERTDIR=/certs \
-v docker-certs-ca:/certs/ca \
-v docker-certs-client:/certs/client \
-v jenkins-data:/var/jenkins_home \
docker:dind
Start Jenkins container:
docker container run --name jenkins \
--detach --restart unless-stopped \
--network jenkins \
-u root \
--env DOCKER_HOST="tcp://docker:2376" \
--env DOCKER_CERT_PATH=/certs/client \
--env DOCKER_TLS_VERIFY=1 \
--volume docker-certs-client:/certs/client:ro \
--volume jenkins-data:/var/jenkins_home \
--publish 8080:8080 --publish 50000:50000 \
-v /usr/bin/docker:/usr/bin/docker \
jenkins/jenkins:lts-jdk11
