# AWS SDK Overview

What if you want to perform actions on AWS directly from your applications code? (without using the cli)

You can use an SDK (software development kit)

Official SDKs are..
- java
- .NET
- Node.js
- PHP
- Python (name boto3 / botocore)
- Go
- Ruby
- C++

We have to use the AWS SDK when coding against AWS Services such as DynamoDB

Fun fact.. the AWS CLI uses the Python SDK (boto3)

The exam expects you to know when you should use an SDK

Good to know: if you don't specify or configure a default region, then us-east-1 will be chosen by default