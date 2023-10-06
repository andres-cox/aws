# Overview

# Infrastructure as Code

Currently we have been doing a lot of manual work
All this manual work will be very tough to reproduce
- In another region
- In another aws account 
- Within the same region if everything was deleted

Wouldn't it be great, if all our infrastructure was ..code?
That code would be deployed and create / update / delete our infrastructure

# What is Cloudformation

Cloudformation is a declarative way of outlining your AWS infrastructure, for any resources (most of them are supported)

For example, within a cloudformation template you say:
- I want a security group
- I want two EC2 machines using this security group
- I want two Elastic IPs for these EC2 machines 
- I want an S3 bucket
- I want a load balancer (ELB) in front of these machines

The CloudFormation creates those for you, in teh right order, with the exact configuration that you specify

# Benefits of AWS CloudFormation

Infrastructure as Code
- No resources are manually created, which is excellent for control
- The code can be version controlled for example using git
- Changes to the infrastructure are reviewed through code

Cost
- Each resources within the stack is stagged with an identifier so you can easily see how much a stack costs you
- You can estimate the costs of your resources using the CloudFormation template
- Savings strategy: In Dev, you could automation deletion of templates at 5PM and recreated at 8AM, safely

Productivity
- Ability to destroy and recreate an infrastructure on the cloud on the fly 
- Automated generation of Diagram for your templates
- Declarative programmings (no need to figure out ordering and orchestration)

Separation of concern: create many stacks for many apps, and many layers. Ex.
- VPC stacks
- Network stacks
- App stacks

Don't reinvent the wheel
- Leverage existing templates on the web
- Leverage the documentation

# How CloudFormation works 

Templates have to be uploaded in S3 and then referenced in CloudFormation
To update a template, we can't edit previous ones. We have to reupload a new version of the templates in AWS
Stacks are identified by name
Deleting a stack deletes every single artifact that was created by CloudFormation

# Deploying CloudFormation templates

Manual way:
- Editing templates in the CloudFormation designer
- Using the console to input parameters, etc

Automates way:
- Editing templates in a yaml file
- Using AWS CLI (command line interface) to deploy the templates
- Recommended way when you fully want to automate your flow 

# CloudFormation Building Blocks 

Templates components:
- Resources: your AWS resources declared in the template (MANDATORY)
- Parameters: the dynamic input for your template
- Mappings: the static variables for your template
- Outputs: References to what has been declared
- Conditionals: List of conditions to perform resource creation
- Metadata

Template helpers:
- References
- Functions




