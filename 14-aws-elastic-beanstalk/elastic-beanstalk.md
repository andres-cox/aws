# AWS Elastick Beanstalk Overview

# Developer Problems in AWS
- Managing Infrastructure
- Deploying Code
- Configuring all the databases, load balancers, etc.
- Scaling concerns

Most web apps have the same architecture (ALB+ASG)
All the developers want is their code to run!
Possibly, consistently across different applications and environments

# AWS Elastick Beanstalk Overview

Elastic Beanstalk is a developer centric view of deploying and application in AWS

It uses all the components we have use before: EC2,ASG,ELB,RDS,etc..
But it's all in one view that's easy to make sense of!
We still have control for the full configuration

Beanstalk is free but you pay for the underlying instances

# Elastic Beanstalk

Managed service
- Instance configuration / OS is handled by beanstalk
- Deployment strategy is configurable but performed by Elastic Beanstalk

Just the application code is the responsability for the developer

Three architecture models
- Single instance deployment: good for dev
- LB + ASG: great for production or pre-production web applications
- ASG only: great for non-web apps in production (workers,etc)

# Elastic Beanstalk

Elastic Beanstalk has three components 
- Applicaction
- Application version: each deployment gets assigned a version
- Environment name (dev,test,prod): free naming

You deploy application versions to environments and can promote application versions to the next environment

Rollback feature to previous application version

Full control over lifecycle of environments

Support for many platforms: Go, Java, PHP, Python, ....

