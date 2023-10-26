# Lambda Integration with ALB

To expose a Lambda function as an HTTP(S) endpoint..
You can use the Application Load Balancer (or an API Gateway)
The Lambda function must be registered in a target group

# ALB to Lambda: HTTP to JSON

Request Payload for Lambda Function -> long json format see docs

# Lambda to ALB conversions: JSON to HTTP

Response from the lambda function -> Json with HTTP info

# ALB Multi-Header Values

ALB can support multi header values (ALB setting)
When you enable multi-value headers, HTTP headers and query string parameters that are sent with  multiple values are shown as arrays within the AWS Lambda event and response objects
