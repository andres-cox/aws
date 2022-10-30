# Network ACL & Security Groups

NACL (Network ACL)
- A firewall which controls traffic from and to subnet
- Can have ALLOW and DENY rules
- Are attached at the Subnet level
- Rules only include IP addresses

Security Groupds
- A firewall that controls traffic to and from and ENI (elastic network interface) / an EC2 instance
- Can have only ALLOW rules
- Rules include IP addresses and other security groups

# VPC Flow Logs

Capture information about IP traffic going into your interfaces:
- VPC Flow logs
- Subnet Flow logs
- Elastic Network Interface Flow logs

Helps to monitor & troubleshoot connectivity issues. Example:
- Subnets to internet
- Subnets to subnets
- Internet to subnets

Captures network information from AWS managed interfaces too: Elastic Load Balancers, ElastiCache, RDS, Aurora, etc..

VPC Flow Logs data can go to S3 / CloudWatch logs