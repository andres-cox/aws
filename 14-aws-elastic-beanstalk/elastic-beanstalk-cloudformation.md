# Elastic Beanstalk Under the Hood

Under the hood, Elastic Beanstalk relies on CloudFormation

CloudFormation is used to provision other AWS services

Use Case: you can define CloudFormation resources in your .ebextensions to provision ElastiCache, an S3 bucket, anything you want!

