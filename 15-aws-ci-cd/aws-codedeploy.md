# AWS CodeDeploy

We want to deploy our application automatically to many EC2 instances
These instances are not managed by Elastic Beanstalk
There are several ways to handle deployments using open source tools (Ansible, Terraform, Chef, Puppet)
We can use the managed Service AWS CodeDeploy

# Steps to make it work

Each EC2 Machine (or On premise machine) must be running the CodeDeploy Agent
The agent is Continously polling AWS CodeDeploy for work to do
CodeDeploy sends appspec.yml file
Application is pulled from Github or S3
EC2 will run the deployment instructions
CodeDeploy Agent will report of success / failure of deployment on the instance

# Other

EC2 instances are grouped by deployment group (dev/test/prod)
Lots of flexibility to define any kind of deployments
CodeDeploy can be chained into CodePipeline and use artifacts from there
CodeDeploy can re-use existing setup tools, works with any application, auto scaling interaction
Note: Blue/Green only works with EC2 instances (not on premise)
Support for AWS Lambda deployments
CodeDeploy does not provision resources

# AWS CodeDeploy Primary Components 

Application: unique name
Compute platform: EC2 / On-premise or Lambda
Deployment Configuration: Deployment rules for success / failures 
- EC2 / On-premise: you can specify the minimun number of healthy instances for the deployment
- AWS Lambda: specify how traffic is routed to your updated Lambda function versions
Deployment Group: group of tagged instances (allow to deploy gradually)
Deployment Type: In-place deploymentor blue/green deployment
IAM instance profile: need to give EC2 the permissions to pull from S3 / Github
Application Revision: application code + appspec.yml file
Service Role: Role for CodeDeploy to perform what it needs
Target Revision: Target deployment application version

# AWS CodeDeploy AppSpec

File section: how to source and copy from S3 / Github to filesystem
Hooks: set of instructions to do to deploy the new version (hooks can have timeouts). The order is:
- Application stop
- DownloadBundle
- BeforeInstall
- AfterInstall
- ApplicationStart
- ValidateService: really important

# AWS CodeDeploy Deployment Config

Configs:
- One a time: one instance at a time, one instance fails => deployment stops
- Half at a time: 50%
- All at once: quick but no healthy host, downtime. Good for dev
- Custom: min healthy host = 75%

Failures: 
- Instances stay in "failed state"
- New Deployments will first be deployed to "failed state" instances
- To rollback: redeploy all deployment or enable automated rollback for failures

Deployment Targets:
- Set of EC2 instances with tags
- Directly to an ASG
- Mix of ASG / Tags so you can build deployment segments
- Customization in scripts with DEPLOYMENY_GROUP_NAME environment variables