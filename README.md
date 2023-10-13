# Secure DevOps Assignment 2

## Overview

This assignment demonstrates the implementation of a Secure DevOps pipeline using Docker, Docker Compose, and Jenkins pipelines. The objective was to establish a streamlined process for continuous integration and deployment of a basic Node.js web application.

## Completed Tasks

## Task 1: Repository Setup

Forked Repository:

Forked the provided repository aws-samples/aws-elastic-beanstalk-express-js-sample into personal GitHub.


Created New Repository:

Created a new repository named Project2-Compose in personal GitHub account.

## Task 2: Container and Jenkins Configuration

Docker Compose Setup:

Created a Docker Compose file (docker-compose.yml) in the Project2-Compose repository. This file orchestrates the execution of a Docker-In-Docker (DinD) container and a Jenkins container, utilizing the DinD container to execute a Jenkins pipeline.


Committed and Pushed Docker Compose File:

Used Git to add, commit, and push the docker-compose.yml file to the main branch of the Project2-Compose repository.

## Task 3: Jenkinsfile Creation

Created Jenkinsfile:

In the forked aws-elastic-beanstalk-express-js-sample repository, created a Jenkinsfile and stored it in the root directory. The Jenkinsfile is configured to use a Node 16 Docker image as the build agent and include a build step that runs the command npm install --save.


Committed and Pushed Jenkinsfile:

Used Git to add, commit, and push the Jenkinsfile to the main branch of the forked aws-elastic-beanstalk-express-js-sample repository.

## Task 4: Jenkinsfile Pipeline Setup

Set Up Jenkins Pipeline:

In the Jenkins setup, created a Pipeline project named 21543340_Project2_pipeline. This project was configured to utilize the previously created Jenkinsfile for its pipeline definition, employing the Pipeline script from SCM option.

## Next Steps

The established Secure DevOps pipeline is now ready for further development and deployment of applications.
