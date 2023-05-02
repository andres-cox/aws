# ECS Data Volumes - EC2 Task Strategies

The EBS volume is already mounted onto the EC2 instances

This allows your Docker containers to mount the EBS volume and extend the storage capacity of your task

Problem: if your task moves from one EC2 instance to another one, it won't be the same EBS volume and data

Use cases: 
- Mount a data volume between different containers on the same instance
- Extend the temporary storage of a task.

# EFS File Systems

Works for both EC2 tasks and fargate tasks

Ability to mount EFS volumes onto tasks

Tasks launched in any AZ will be able to share the same data in the EFS volume

Fargate + EFS = serverless + data storage without managing servers

Use Case: persisten multu AZ shared storage for your containers

# Bind Mounts Sharing data between containers

Works for both EC2 Tasks (using local EC2 instance storage) and Fargate tasks (get 4GB for volume mounts)

Useful to share between multiple containers part of the same ECS task

Great for "sidecar" container pattern where the sidecar can be used to send metrics/logs to other destinations (separation of concerns)
