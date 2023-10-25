# Amazon SQS - What's a queue?

# Standard Queue

Oldest offering (over 10 years old)
Fully managed service, used to decouple applications
Attributes
- Unlimited throughput, unlimited number of messages in queue
- Default retention of messages: 4 days, maximum of 14 days
- Low latency (<10 ms on publish and receive)
- Limitation of 256KB per message sent
Can have duplicate messages (at least once delivery, occasionally)
Can have out of order messages (best effort ordering)

# SQS - Producing Messages

Produced to SQS using the SDK (SendMessage API)
The message is persisted in SQS until a customer deletes it
Message retention: default 4 days, up to 14 days

Example: send an order to be processed
- Order id
- Customer id
- Any attributes you want
SQS standard: unlimited throughput

# SQS - Consuming Messages

Consumers (running on EC2 instances, servers, or AWS Lambda)
Poll SQS for messages (receive up to 10 messages at a time)
Process the messages (example: insert the message into an RDS database)
Delete the messages using the DetectMessage API

# SQS - Multiple EC2 Instances Consumers

Consumers receive and process messages in parallel
At least once delivery
Best-effort message ordering
Consumers delete messages after processing them
We can scale consumers horizontally to improve throughput of processing

# SQS with AutoScalingGroup (ASG)

This is a common scenario in which there are many messages in queue, so we can use a CloudWatch Metric with Queue Length for SQS that triggers a CloudWatch Alarm which communicates to the ASG with EC2 instances, so finally we can scale instances accordingly of the load. 

# SQS to decouple between application tiers

Main purpose of this feature is to manage accordingly different applications (see image). If we have a frontend app with video processing and we send requests to a backend processor through SQS. We can handle the load easily each app with ASGs and SQS. So we get the best performance based in load separately 

# Amazon SQS - Security

Encryption:
- In-flight encryption using HTTPS API
- At-rest encryption using KMS keys
- Client-side encryption if the client wants to perform encryption/decryption itself

Access Controls: IAM policies to regulate access to the SQS API

SQS Access Policies (similar to S3 bucket policies)
- Useful for cross-account access to SQS queues
- Useful for allowing other services (SNS, S3..) wo write to an SQS queue
