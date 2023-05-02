# ECS Service with Load Balancer

Let's say you have 2 EC2 instances that are running 2 containers each.
You'd better provide a random port for the host so containers don't have conflicts whr forwarding ports.
So an Application Load Balancer is needed with dynamic port forwarding to comunicate with all containers.