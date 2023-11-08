# AWS Lambda Limits to Know - per region

Execution:
- Memory allocation: 128MB - 10GB (64MB Increments)
- Maximum execution time: 900 seconds (15 minutes)
- Environment variables (4KB)
- Disk capacity in the function container (in/tmp): 512MB
- Concurrency Executions: 1000 (can be increased)

Deployment:
- Lambda function deployment size (compressed .zip): 50MB
- Size of uncompressed deployment (code + dependencies): 250MB
- Can use the /tmp directory to load other files at startup
- Size of environment variables (4KB)
