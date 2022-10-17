# EFS - Elastic File System

Managed NFS (network file system) that can be mounted on many EC2

EFS works with EC2 instances in multi-AZ

High available, scalable, expensive (x3 gp2), pay per use (so in some scenarios might be cheaper if't not use contantly)

Use Cases: content management, web serving, data sharing, Wordpress
Uses NFSv4.1 protocol
Uses security group to control access to EFS
Compatible with Linux based AMI (not windows)
Encryption at rest using KMS

POSIX file system (~Linux) that has a standard file API
File system scales automatically, pay-per-use, no capacity planning.

# Performance & Storage Classes

EFS Scale
- 1000s of concurrnet NFS clients, 10GB+/s throughput
- Grow to petabyte-scale netfowk file system - automatically
Performance Mode
- General purpose (default): latency sensitive use cases(web server, CMS, etc)
- Max I/O higher latency, throughput, highly parallel (big data, media processing)
Throughput Mode
- Bursting (1TB = 50MiB/s + busrt of up to 100MiB/s)
- Provisioned: set your throughput regardless of storage size, ex: 1GiB/s for 1 TB storage
Storage Tiers (lifecycle management feature - move file after N days)
- Standard: for frequently accessed files
- Infrequent access (EFS-IA): cost to retrieve files, lower price to store

** EFS is a share file system network across multiple instances, requires to customize security groups between then to make it work. 