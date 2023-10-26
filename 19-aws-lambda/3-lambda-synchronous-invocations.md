# Lambda - Synchronous Invocations

Synchronous: CLI, SDK, API Gateway, Application Load Balancer
- Results is returned right away
- Error handling must happen client side (retries, exponential backoff, etc..)

# Lambda - Synchronous Invocations - Services

User Invoked:
- Elastic Load Balancing (Application Load Balancer)
- Amazon API Gateway
- Amazon CloudFront (Lambda@Edge)
- Amazon S3 Batch

Service Invoked:
- Amazon Cognito
- AWS Step Functions

Other Services:
- Amazon Lex
- Amazon Alexa
- Amazon Kinesis Data Firehose