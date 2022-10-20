# Elastic Load Balancer - Cross Zone Load Balancing

With Cross Zone Load Balancing:
Each load balancer instance distributes evenly across all registered instances in all AZ
Example of 100 requests (50 requests for each ELB of AZ)
    AZ-1: 2 instances -> 10 requests each instance
    AZ-2: 8 instances -> 10 requests each instance

Without Cross Zone Load Balancing:
Requests are distributed in the instances of the node of the elastic load balncer
Example of 100 requests (50 requests for each ELB of AZ)
    AZ-1: 2 instances -> 25 requests each instance 
    AZ-2: 8 instances -> 6.25 requests each instance

Application Load Balancer (ALB)
- Always on (can't be disabled)
- No charges for inter AZ data

Network Load Balancer (NLB)
- Disabled by default
- You pay charges ($) for inter AZ data if enabled

Classic Load Balancer
- Through Console -> Enabled by default
- Through CLI / API -> Disabled by default
- No charges for inter AZ data if enabled 