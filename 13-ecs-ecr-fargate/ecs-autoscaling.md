# ECS - Service Auto Scaling

CPU and RAM are tracked in CloudWatch at the ECS service level
- Target Tracking: target a specific average CloudWatch alarms.
- Step Scaling: scaled based on CloudWatch alarms.
- Scheduled Scaling: based on predictable changes.

ECS Service Scaling (task level) is NOT equal to EC2 Auto Scaling (instance level)

Fargate Auto Scaling is much easier to setup (because serverless)

# ECS - Cluster Capacity Provider

A capacity provider is used in assosciation with a cluster to determine the infrastructure that a task runs on.
- For ECS and fargate users, the FARGATE and FARGATE_SPOT capacity providers are added automaticly
- For Amazon ECS on EC2, you need to associate the capacity provider with an auto-scaling group

When you run a task or a service, you define a capacity provider strategy, to prioritize in which provider to run.

This allows the capacity provider to automatically provision infrastruture for you.