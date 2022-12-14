# Aurora Overview

Aurora is a proprietary technology from AWS (not open sourced)

Postgress and MySQL are both supported as Aurora DB (that means your drivers will work as if Aurora was a Postgres or MySQL database)

Aurora is AWS cloud optimized and claims 5x performance improvment over MySQL on RDS, over 3x the performance of Postgres on RDS

Aurora storage automatically grows in increments of 10Gb up to 64TB.

Aurora can have 15 replicas while MySQL has 5, and the replication process is faster (sub 10ms replica lag)

Failover in Aurora is instantaneous. It's HA native.

Aurora costs more than RDS (20% more) - but is more efficient

## Aurora High Availability and Read Scaling

6 copies of your data across 3 AZ:
- 4 copies out of 6 needed for writes
- 3 copies out of 6 need for reads
- Self healing with peer-to-peer replication 
- Storage is striped across 100s volumes

One aurora instance takes writes (master)

Automated failover for master in less than 30 seconds

Master + up to 15 Aurora Read Replicas serve reads

Support for Cross Region Replication

## Aurora DB cluster

See image

## Features of Aurora

- Automatic fail-over
- Backup and recovery
- Isolation and security
- Industry compliance
- Push-button scaling 
- Automated patching with zero downtime
- Advanced monitoring
- Routine Maitainance 
- Backtrack: restore data at any point of time without using backups

# Aurora Security

- Similar to RDS because uses the same engines
- Encryption at rest using KMS
- Automated backups, snapshots and replicas are also encrypted
- Encryption in flight using SSL (same process as MySQL or Postgres)
- Possibility to authenticate using IAM token (same method as RDS)
- You are responsable for protecting the instance with security groups
- You can't ssh

