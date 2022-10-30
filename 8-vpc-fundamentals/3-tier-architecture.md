# Typical 3 tier solution architecture

User --> Route 53 --> ELB (Multi AZ) <--> 3 instances in its AZs (With ASG) <--> ElastiCache / Amazon RDS
                      Public Subnet                Private Subnet                      Data Subnet