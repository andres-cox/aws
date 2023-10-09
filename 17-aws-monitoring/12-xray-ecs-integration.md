# ECS + X-Ray integration options

ECS runs containers configured in EC2 instances

X-Ray Container as a Daemon -> There will be a daemon container in each EC2 instance (communication is configured by UDP)
X-Ray Container as a Side Car -> There will be an X-Ray Side Car for each container (Same behavior for Fargate clusters)

These are configured with Task Definitions
