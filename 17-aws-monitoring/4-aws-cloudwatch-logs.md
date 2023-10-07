# AWS CloudWatch Logs

Applications can send logs to CloudWatch using th SDK
CloudWatch can collect log from:
- Elastic Beanstalk: collection of logs from application
- ECS: collection from containers
- AWS Lambda: collection from function logs
- VPC Flow Logs: VPC specific logs
- API Gateway
- CloudTrail based  on filter
- CloudWatch log agents: for example on EC2 machines
- Route53: Log DNS queries
CloudWatch Logs can go to:
- Batch exporter to S3 for archival
- Stream to ElasticSearch cluster for further analytics
CloudWatch Logs can use filter expressions
Logs storage architecture:
- Log groups: arbitrary name, usually representing an application
- Log stream: instances within application / log files / containers
Can define log expiration policies (never expire, 30 days, etc)
Using AWS CLI we can tail CloudWatch logs
To send logs to CloudWatch, make sure IAM permissions are correct
Security: encryption of logs using KMS at the Group Level

# CloudWatch Logs for EC2

By default, no logs from your EC2 machine will go to CloudWatch
You need to run a CloudWatch agent on EC2 to push the log files you want
Make sure IAM permissions are correct
The CloudWatch log agent can be setup on-premises too

# CloudWatch Logs metric Filter

CloudWatch Logs can use filter expressions
- For example, find a specific IP inside of a log
- Or count occurrences of "ERROR" in your logs
- Metric filters can be used to trigger alarms

Filters do not retroactively filter data. Filters only publish the metric data points for events that happen after the filter was created


