# AWS CICD

# CICD Section Introduction

We know how to create resources in AWS manually (Fundamentals)
We know how to interact with AWS programmaticly (CLI)
We've seen how to deploy code to AWS using Elastic Beanstalk
All these manual steps make it very likelyfor us to do mistakes!

What we'd like is to push our code "in a repository" and have it deployed onto AWS
- Automatically
- The right way
- Making sure it's tested before deploying
- With possibility to go into different stages (dev,test,pre-prod,prod)
- With manual approval when needed

This section is all about automating the deployment we've done so far while adding increased safety
It correspond to a whole part of the AWS certification

We'll learn about:
- AWS CodeCommit: storing our code
- AWS CodePipeline: automating our pipeline from code to ElasticBeanstalk
- AWS CodeBuild: building and testing our code
- AWS CodeDeploy: deploying the code to EC2 fleets (not beanstalk)

# Continous Integration

Developers push the code to a code repository
A testing / build server checks the code as soon as it's pushed (Codebuild, Jenkins CI)
The developer gets feedback about the tests and checks that have passed / failed

The purpose:
- Find bugs
- Deliver code as the code is tested
- Deploy often
- Happier developers, as they're unblocked

# Continoues Delivery

Ensure that the software can be released reliably whenever needed
Ensure deployments happen often and are quick
Shift away from "one release every 3 months" to "5 releases a day"
That usually means autoamted deployment:
- CodeDeploy
- Jenkins CD
- Spinnaker

# Technology Stack for CICD

       CODE      -> BUILD   -> TEST  ->      DEPLOY          -> PROVISION

| AWS CodeCommit |   AWS CodeBuild    |              AWS Elastic Beanstalk                                        |
|    Github      |   Jenkins CI       | AWS CodeDeploy        | User Managed EC2 instances Fleet (Cloudformation) |
|                         Orchestrate: AWS CodePipeline                                                           |
