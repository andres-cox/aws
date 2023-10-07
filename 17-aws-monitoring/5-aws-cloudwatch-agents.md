# CloudWatch Logs Agent & Unified Agent

For virtual servers (EC2 instances, on-premises servers)

CloudWatch Logs Agent
- Old version of the agent
- Can only send to CloudWatch Logs

CloudWatch Unified Agent
- Collect additional system-level metrics such as RAM, processes, etc.. 
- Collect logs to send to CloudWatch Logs
- Centralized configuration using SSM Parameter Store
Metrics collected directly on your Linux Server / EC2 instance
- CPU (active, guest, idle, system, user, steal)
- Disk metrics (free, used, total), Disk IO (writes, reads, bytes, iops)
- RAM (free, inactive, used, total, cached)
- Netstat (number of TCP and UDP connections, net packets, bytes)
- Processes (total, dead, blocked, idle, running, sleep)
- Swap Space (free, used, used %)
Reminder: out-of-the-box metrics for EC2 - disk, CPU, network (High Level) 