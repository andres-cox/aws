# Fargate

When launching an ECS Cluster, we have to create our EC2 instances
If we need to scale, we need to add EC2 instances
So we manage infrastructure...

With Fargate, it's all Serverless!
We don't provision EC2 instances
We just create task definitions, and AWS will run our containers for us
To scale, just increase the task number. Simple! no more EC2