# AWS CodeBuild in VPC

By default, your CodeBuild containers are launched outside your VPC
Therefore, by default it cannot access resources in a VPC
You can specify a VPC configurtation:
- VPC ID
- Subnets IDs
- Security Groups IDs
Then your build can access resources in your VPC (RDS, ElastiCache, EC2, ALB,..)
Use cases:
- Integration Tests,
- Data query
- Interaction with internal Load balancers