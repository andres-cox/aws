# AWS Lambda Best Practices

Perform heavy-duty work outside of your function handler
- Connect to databases outside of your function handler
- Initialize the AWS SDK outside of your function handler
- Pull in dependencies or datasets outside of your function handler

Use environment variables for:
- Database Connection Strings, S3 Bucket, etc.. don't put these values in your code
- Passwords, sensitive values.. they can be encrypted using KMS

Minimize your deployment package size to its runtime necessities
- Break down the function if need be
- Remember the AWS Lambda limits
- Use Layers where necessary

Avoid using recursive code, never call a function call itself
