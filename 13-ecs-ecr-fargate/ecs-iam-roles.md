# ECS IAM Roles Deep Dive

EC2 Instance Profile:
- Used by the ECS agent
- Makes API calls to ECS service
- Send container logs to CLoudWatch Logs
- Pull Docker image from ECR

ECS Task Role:
- Allow each task to have a specific role
- Use different roles for the different ECS Services you run (S3,RDS)
- Task role is defined in the task definition 