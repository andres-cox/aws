# Lambda Function Dependencies

If your Lambda function depends on external libraries:
For example AWS X-Ray SDK, Database Clients, etc..

You need to install the packages alongside your code and zip it together
- For Node.js use npm & "node_modules" directory
- For Python use pip --target options
- For Java, include the relevant .jar files

Upload the zip straight to Lambda if less than 50MB, else to S3 first   
Native libraries work: they need to be compiled on Amazon Linux
AWS SDK comes by default with every Lambda function 