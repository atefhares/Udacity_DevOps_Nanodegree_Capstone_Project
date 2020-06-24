# Udacity DevOps Nanodegree Capsone Project - Atef Hares

The Goal of this project is to create a pipeline that automates the proccess of deploying the provided PythonApp to a kubernetes cluster on AWS

## What is built here:
- Using Jenkins to create and manage a pipeline through the provided JenkinsFile
- Using Docker to create an image of the app and push it to dockerhub
- Using AWS CloudFormation & Ansible to setup the production env.
- Deploying the app.

  The pipeline has these main stages:
  - **TESTING**: Running unit testing on the code
  - **DOCKERIZING**: Dockerizing the application into an image locally
  - **PUSHING**: Pushing the built image to DockerHub
  - **BUILDING_INFRASTURTURE**: Building the infrastructure and Kubernetes cluster using AWS cloudformation and ansbile
  - **DEPLOYING**: Deploying the dockrized app from dockerhub onto the cluster in AWS

## Getting starting:
- Install jenkins, git, python3 + pip3, docker, ansible
- Configure jenkins to create a pipeline using the provided `JenkinsFile` + configure needed credentials [DockerHub, AWS]
- Run the pipeline!

## Outputs
