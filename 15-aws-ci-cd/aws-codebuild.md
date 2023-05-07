# AWS CodeBuild

Fully managed build server
Alternative to other build tools such as Jenkins
Continous Scaling (no servers to manage or provision - no build queue)
Pay for usage: the time it takes to complete the builds
Leverages Docker under the hood for reproducible builds
Possibly to extend capabilities leveraging our own base Docker images
Secure: Integration with KMS for ecryption of build artifacts, IAM for build permissions, and VPC for network security, Cloudtrail for API calls logging
Source Code from Github / CodeCommit / CodePipeline / S3
Build instructions can be defined in code (buildspec.yml file)
Output logs to Amazon S3 & AWS CloudWatch logs
Metrics to monitor CodeBuild statistics
Use CloudWatch alarms to detect failed builds and trigger notifications
CloudWatch Events / AWS Lambda as a Glue
SNS notifications
Ability to reproduce CodeBuild locally to troubleshoot in case of errors
Builds can be defined within CodePipeline or CodeBuild itself   

See image for CodeBuild workflow

# CodeBuild BuildSpec

buildspec.yml file must be at the root of your code
Define environment variables:
- Plaintext variables
- Secure secrets: use SSM Parameter store
Phases (specifies commands to run)
- Install: install dependencies you may need for your build
- Prebuild: final commands to execute before build
- Build: actual build commands
- Post build: finishing touches (zip output for example)
Artifacts: What to upload to S3 (encrypted with KMS)
Cache: Files to cache (usually dependencies) to S3 for future build speepup

# CodeBuild Local Build

In case of need of deep troubleshooting beyond logs
You can run CodeBuild locally on your desktop (after installing docker)
For this, leverage the CodeBuild agent

