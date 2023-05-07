# AWS CodeDeploy for EC2 and ASG

Define how to deploy the application using appspec.yml + deployment strategy
Will do in-place update to your fleet of EC2 instances
Can us hooks to verify the deployment after each deployment phase

# CodeDeploy to ASG

In place updates:
- Updates current existing EC2 instances
- Intances newly created by an ASG will also get automated deployments

Blue / Green deployment
- A new autoscaling group is created (settings are copied)
- Choose how long to keep old instances
- Must be using an ELB

# CodeDeploy Roll backs 

You can specify automated rollback options
- Roll back when a deployment fails
- Roll back when alarm thresholds are met
- Disable rollbacks - Do not perform rollbacks for this deployment

If a rollback happens, CodeDeploy redeploys the last known good revision as a new deployment.