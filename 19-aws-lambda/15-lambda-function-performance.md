# Lambda Function Configuration

RAM:
- From 128MB to 3008MB in 64MB increments
- The more RAM you add, the more vCPU credits you get
- At 1792MB, a function has the equivalent of one full vCPU
- After 1792MB, you get more than one CPU, and need to use multi-threading in your code to benefit from it
If your application ic CPU-bound (computation heavy), increase RAM
Timeout: default 3 seconds, maximum is 900 seconds (15 minutes) (So for efforts that take more that 15 minutes you better use a different technology like EC2, ECS or Fargate)

# Lambda Execution Context

The execution context is a temporary runtime environment that initializes any external dependencies of your lambda code
Great for database connections, HTTP clients, SDK clients..
The execution context is maintained for some time in anticipation of another Lambda function invocation
The next function invocation can "re-use" the context to execution time and save time in initializing connections objects
The execution context includes the /tmp directory

# Lambda Functions /tmp space

If your Lambda function needs to download a big file to work
If your Lambda function needs disk space to perform operations
You can use the /tmp directory
Max size is 512MB
The directory content remains when the execution context is frozen, providing transient cache that can be used for multiple invocations (helpful to checkpoint your work)
For permanent persistence of an object (non temporary), use S3