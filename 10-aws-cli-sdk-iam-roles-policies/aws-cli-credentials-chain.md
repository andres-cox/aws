# AWS CLI Credentials Provider Chain

The CLI will look for credential in this order
1. Command line options - --region, --output, and profile
2. Environment Variables - AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY
3. CLI credentials file - aws configure at ~/.aws/credentials
4. CLI configuration file - aws configure at ~/.aws/config
5. Container credentials - for ECS tasks
6. Instance profile credentials - for EC2 Instance Profiles

# AWS SDK Default Credentials Provider Chain

The Java SDK (example) will look fro credentials in this order
1. Java system properties - aws.accessKeyId and aws.secretKey
2. Environment Variables - AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY
3. The default credential profiles file - at ~/.aws/credentials shared by many SDk
4. Amazon ECS Container credentials - for ECS containers
6. Instance profile credentials - used on EC2 Instances

# AWS Credentials Scenario

An application deployed on an EC2 instance is using environment variables with credentials from an IAM user to call the Amazon S3 API

The IAM user has S3FullAccess permissions

The application only uses one S3 bucket, so according to best practices:
- An IAM Role & EC2 Instance profile was created for the EC2 instance
- The role was assigned the minimum permissions to access that one S3 bucket

*The IAM Instance profile was assigned to the EC2 instance, but it still has access to all S3 buckets, Why?*
the credentials chain is still giving priorities to the environment variables

# AWS Credentials Best Practices

Overall, NEVER EVER STORE AWS CREDENTIALS IN YOUR CODE

Best practice is for credentials to be inherited from the credentials chain

If using/working within AWS, use IAM roles
- EC2 instances roles for EC2 instances
- Lambda Roles for Lambda functions

If working outside of AWS, use environment variables / named profiles