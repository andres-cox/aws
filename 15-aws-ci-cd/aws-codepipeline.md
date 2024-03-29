# AWS CodePipeline

Continuous delivery
Visual Workflow
Source: Github / CodeCommit / Amazon S3
Build: CodeBuild / Jenkins / etc..
Load Testing: 3rd party tools
Deploy: AWS CodeDeploy / Beanstalk / CloudFormation / ECS
Made of stages:
- Each Stage can have sequential actions and / or parallel actions
- Stages examples: Build / Test / Deploy / Load Test / etc..
- Manual approval can be defined at any stage

# AWS CodePipeline Artifacts

Each pipeline stage can create "artifacts"
Artifacts are passed stored in Amazon S3 and passed on to the next stage 

# AWS CodePipeline Troubleshooting

CodePipeline state changes happen in AWS CloudWatch Events, which can in return create SNS notifications.
- You can create events for failed / cancelled stages

If codepipeline fails a stage, your pipeline stops and you can get information in the console

AWS CloudTrail can be used to audit AWS API calls.

If Pipeline can't perform an action, make sure the "IAM Service Role" attached does have enough permissions (IAM Policy)