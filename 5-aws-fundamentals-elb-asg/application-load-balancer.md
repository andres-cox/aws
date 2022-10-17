# Application Load Balancer (v2) ALB

Application load balancers is Layer 7 (HTTP)

Load Balancing to multiple HTTP applications acrross machines (Target Groups)
Load Balancing to multiple applications on the same machine (ex: containers)
Support for HTTP/2 and WebSocket
Support redirects (from HTTP to HTTPS for example)

Routing Tables to different target groups:
- Routing based on path in URL (example.com/users & examples.com/posts)
- Routing based on hostname in URL (one.example.com & other.example.com)
- Routing based on Query String, Headers (example.com/users?id=123&order=false)

ALB are a great fit for micro services & container-based application (example: Docker & Amazon ECS)
Has a port mapping feature to redirect to a dynamic port in ECS
In comparison, we'd need multiple Classic Load Balancer per application

** So lets say you have 2 EC2 instances for users request and another 2 EC2 instances for search requests. Each pair of ec2 instances are in a target group. So when there is a request /users or /search the ALB will connect to the corresponing instances based in the target group. 

# Target group (Group of instace services)

Can be groups of:
- EC2 instances (can be managed by an auto scaling group) - HTTP
- ECS tasks (managed by ECS itself) - HTTP
- Lambda functions - HTTP request is translated into a JSON event
- IP Addresses - must be private IPs (on-premises servers)

ALB can route to multiple target groups
Health checks are the target groups level 

# Query Strings/Parameters Routing 

ALB can select different target groups based in requests like ?Platform=Mobile or ?Platform=Desktop.

# ALB Good to know

Fixed hostname (xxx.region.elb.amazonaws.com)
The application servers don't see the IP of the client directly 
- The true IP of the client is inserted in the header X-Forwarded-For
- We can also get Port (X-Forwarded-Port) and proto (X-Forwarded-Proto)
