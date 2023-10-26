# Why AWS Lambda

Amazon EC2:
- Virtual Servers in the Cloud
- Limited by RAM and CPU
- Continuously Running
- Scaling means intervention to add / remove servers

AWS Lambda:
- Virtual Functions - no servers to manage!
- Limited by time - short executions
- Run on-demand
- Scaling is automated!

# Benefits of AWS Lambda

Easy Pricing
- Pay per request and compute time
- Free tier of 1 million AWS Lambda requests and 400000GBs of compute time
Integrated with the whole AWS suite of services
Integrated with many programming languages
Easy monitoring through AWS CloudWatch
Easy to get more resources per functions (up to 3GB of RAM!)
Increasing RAM will also improve CPU and network!

# AWS Lambda language support

Node.js(javascript), Python, Java, C#(.NET), Golang, C#/Powershell, Ruby, Custom runtime API (commonly supported, ex: Rust)
Lambda Container Image
- The container image must implement the Lambda Runtime API
- ECS / Fargate is preferred for running arbitrary Docker images

# AWS Lambda Integrations - Main ones

- API Gateway
- Kinesis
- DynamoDB
- S3
- CloudFront
- CloudWatch Events EventBridge
- CloudWatch Logs
- SNS
- SQS
- Cognito

# AWS Lambda Pricing: Example

Pay per calls:
- First 1,000,000 requests are free
- $0.20 per 1 million requests thereafter

Pay per duration: (in increment of 100ms)
- 400,000 GB-seconds of compute time per month if FREE
- == 400,000 seconds if function is 1GB RAM
- == 3,200,000 seconds if function is 128MB RAM
- After that $1 for 600,000 GB-seconds

It is usually very cheap to run AWS Lambda so it's very popular
