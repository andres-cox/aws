# Elastic Load Balancing

## What is load balancing?

Load Balancers are servers that forward internet traffic to multiple servers (EC2 instances) downstream.
For example: you have 3 ec2 instances with your app, and 3 users are trying to connect to your app, with the load balancer each user will connect to each ec2 instance individually so the load is balanced

## Why use a load balancer?

- Spread load accross multiple downstream instances
- Expose a single point of access (DNS) to your application
- Seamlessly handle failures of downstream instances
- Do regular health checks to your instances
- Provide SSL termination (HTTPS) for your websites
- Enforces stickness with cookies 
- High Availiability accross zones
- Separate public traffic from private private traffic

## Why use an EC2 Load Balancer?

An ELB (EC2 Load Balancer) is a managed load balancer
- AWS guarantees that it will be working
- AWS takes care of upgrades, maintainance, high availability
- AWS provides only a few configuration knobs

It cost less to setup your own load balancer but it will be more effort on your end
It is integrated with many AWS offering / services

## Health Checks 

- Health Checks are crucial for Load Balancers
- They enable the load balancer to know if instances that forward traffic are available to reply requests
- The health check is done on a port and a route (/health is common)
- If the response  is not 200 (OK), then the instance is unhealthy

# Types of Load Balancer on AWS

AWS has 3 kinds of managed Load Balancers

- Classic Load Balancer (v1 - old generation) - 2009
    HTTP, HTTPS, TCP
- Application Load Balancer (v2 - new generation) - 2016
    HTTP, HTTPS, WebSocket
- Network Load Balancer (v2 - new generation) - 2017
    TCP, TLS,(secure TCP) & UDP

Overall, it's recommended to use the newer / v2 generation load balancers as they provide more features

You can setup internal (private) or external (public) ELBs

# Load Balancers Security Groups

Users -> HTTP/HTTPS from anywhere -> Load Balancer -> HTTP Restricted to Load Balancer -> EC2
         Load Balancer Security Group                 Applications Security Group

Load Balancer Security Group: Ports: 80/443, HTTP/HTTPS -> For user to have acces to load balancer
Applications Security Group: Port: 80, HTTP- -> Allow Traffic only from Load Balancer

# Load Balancer Good to Know

LBs can scale but not instantaneously - contact AWS for a "warm-up"

Troubleshooting
- 4xx errors are client induced errors
- 5xx are application induced errors
- Load Balancer Errors 503 means at capacity or no registered target (overloaded)
- If the load balancer can't connect to your application, check your security groups!

Monitoring
- ELB access logs will log all access requests (so you can debug per request)
- CloudWatch Metrics will give you aggregate statistics (ex: connections count)
