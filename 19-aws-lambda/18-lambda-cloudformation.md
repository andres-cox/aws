# Lambda and CloudFormation - inline

Inline functions are very simple 
Use the Code.zipFile property
You cannot include function dependencies with inline functions

# Lambda and CloudFormation - through S3

You must store the Lambda zip in S3
You must refer the S3 zip location in the CloudFormation code
- S3Bucket 
- S3Key: full path to zip
- S3ObjectVersion: of versioned bucket
If you update the code in S3, but don't update S3Bucket, S3Key or S3ObjectVersion, CLoudFormation won't update your function (versioning is important)

# Lambda and CloudFormation - through S3 Multiple accounts

It requires a Bucket policy, and execution role from other accounts, review documentation for more info.

