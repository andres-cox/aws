# AWS CodeCommit

Version control is the ability to understand the various changes that happened to the code over time (and possibly roll back)

All these are enabled by using a version control system such as Git

A Git repository can live on one's machine, but it usually lives on a central online repository

Benefits are:
- Collaborate with other developers
- Make sure the code is backed-up somewhere
- Make sure it's fully viewable and auditable

Git repositories can be expensive

The industry includes:
- Github: free public repositories, paid private ones
- Bitbucket

And AWS CodeCommit
- Private Git repositories
- No size limit on repositories (scale seamlessly)
- Fully managed, high available
- Code only in AWS Cloud account => increased security and compliance
- Secure (encrypted, access control, etc..)
- Integrated with Jenkins / CodeBuild / other CI tools

# CodeCommit Security

Interactions are done using Git (standard)

Authentication in Git:
- SSH Keys: AWS Users can configure SSH keys in their IAM console
- HTTPS: Done through the AWS CLI Authentication helper or Generating HTTPS credentials
- MFA (multifactor authentication) can be enabled for extra safety

Authoritation in Git:
- IAM Policies manage user / roles rights to repositories

Encryption
- Repositories are automatically encrypted at rest using KMS
- Encrypted in transit (can only use HTTPS or SSH - both secure)

Cross Account access:
- Do not share your SSH keys
- Do not share your AWS credntials
- Use IAM role in your AWS account and use AWS STS (with AssumeRole API)

# CodeCommit vs Github

Similarities:
- Both are git repositories
- Both support code review (pull requests)
- Both can be integrated with AWS CodeBuild
- Both support HTTPS and SSH method of authentication

Differences:
Security:
- Github: Github Users
- CodeCommit: AWS IAM Users & Roles
Hosted:
- Github: hosted by Github
- Github Enterprise: self hosted on your servers
- CodeCommit: managed & hosted by AWS
UI:
- Github UI is fully featured 
- CodeCommit UI is minimal

# CodeCommit Notifications

You can trigger notifications in CodeCommit using AWS SNS (Simple Notification Service) or AWS Lambda or AWS CloudWatch Event Rules

Use cases for notifications AWS SNS / AWS Lambda:
- Deletion of branches
- Trigger for pushes that happens in master branch
- Notify external build system
- Trigger AWS Lambda function to perform codebase analysis (maybe credentials got commited in the code?)

Use cases for CloudWatch Event Rules:
- Trigger for pull requests updates (created / updated / deleted / commented)
- Commit comment events
- CloudWatch event rules goes into an SNS topic 
