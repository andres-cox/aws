# Lambda - Asynchronous Invocations

S3, SNS, Cloudwatch events
The events are placed in an Event Queue
Lambda attempts to retry on errors
- 3 retries total
- 1 minute wait after 1st, then 2 minutes wait
Make sure the processing is idempotent (in case of retries)
If the function is retried, you will see duplicate logs entries in CloudWatch Logs
Can define a DLQ (dead-letter queue) - SNS or SQS - for failed processing (need correct IAM permissions)
Asynchronous invocations allow you to speed up the processing if you don't need to wait for the result (ex: you need 1000 files processed) 

# Lambda - Asynchronous Invocations - Services

- Amazon Simple Storage Service (S3)
- Amazon Simple Notification Service (SNS)
- Amazon CloudWatch events / EventBridge
- AWS CodeCommit (CodeCommit Trigger: new branch, new tag, new push)
- AWS CodePipeline (invoke a Lambda function during the pipeline, Lambda must callback)
--other--
- Amazon CloudWatch Logs (logs processing)
- Amazon Simple Email Service
- AWS CloudFormation
- AWS Config
- AWS IoT
- AWS IoT Events