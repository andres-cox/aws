# Amazon SNS

What if you want to send one message to many receivers?
You can have direct integration, in which in all services that needs the message you would need to implement a logic for each one.
Instead you can have an SNS topic which follows the Publish/Subscribe pattern, in which all the services subscribed to the SNS topic will be notified.

The "event producer" only sends message to one SNS topic
As many "event receivers" (subscriptions) as we want to listen to the SNS topic notifications 
Each subscriber to the topic will get the messages (note: new feature to filter messages)
Up to 10000000 subscriptions per topic
100000 topic limits
Subscribers can be:
- SQS
- HTTP / HTTPS (with delivery retries - how many times)
- Lambda
- Emails
- SMS messages
- Mobile Notifications

# SNS integrates with a lot of AWS services

Many AWS services can send data directly to SNS for notifications
CloudWatch (for alarms)
Auto Scaling Groups notifications
Amazon S3 (on bucket events)
CloudFormation (upon state changes => failed to build, etc)
etc..

# AWS SNS - How to publish

Topic Publish (using the SDK)
- Create a topic
- Create a subscription
- Publish to the topic

Direct Publish (for mobile apps SDK)
- Create platform application
- Create platform endpoint
- Publish to the platform endpoint
- Works with Google GCM, Apple APNS, Amazon ADM...

# AWS SNS - Security

Encryption:
- In-flight encryption using HTTPS API
- At-rest encryption using KMS keys
- Client-side encryption if the client wants to perform encryption/decryption itself

Access Controls: IAM policies to regulate access to the SNS API

SNS Access Policies (similar to S3 bucket policies)
- Useful for cross-account access to SNS topics
- Useful for allowing other services (S3..) to write to an SNS topic
