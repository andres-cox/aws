# Elastic Beanstalk Docker

# Single Docker

Run your application as a single docker container

Either provide:
- Dockerfile: Elastic Beanstalk will build and run the docker container
- Dockerrun.aws.json(v1): Describe where *already build* docker image is: image, ports, volumes..

Beanstalk in Single Docker Container does not use ECS

# Multi Docker Container

Multi Docker helps run multiple containers per EC2 instance in EB

This will create for you:
- ECS cluster
- EC2 instances, configured to use the ECS CLuster
- Load Balancer (in high availability mode)
- Task definitions and execution

Requires a config Dockerrun.aws.json(v2) at the route of source code
Dockerrun.aws.json is used to generate the ECS task definition
You Docker images must be pre-built and stored in ECR other registry like Dockerhub 
