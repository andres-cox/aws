# AWS RDS Overview

RDS Stands for Relational Database Service
It's a managed DB Service for DB use SQL as a query language
It allows you to create databases in the cloud that are managed by AWS
- Postgress
- MySQL
- Oracle
- Microsoft SQL Server
- Aurora (AWS Proprietary database)

# Advanatage over using RDS versus deploying DB on EC2

RDS is a managed service:
- Automated procisioning, OS patching
- Continous backups and restore to specific timestamp (Point in Time Restore)
- Monitoring Dashboards
- Read replicas for improved read performance
- Multi AZ setup for DR (Disaster Recovery)
- Maintenance windows for upgrades
- Scaling capability (vertical and horizontal)
- Storage backend by EBS (gp2 or io1)

BUT you can't SSH into your instances

# RDS Backups

Backups are automatically enabled in RDS
Automated backups:
- Daily full backup of the database (during the maintenance window)
- Transaction logs are backed-up by RDS every 5 minutes
- => ability to restore to any point in time (from oldest backup to 5 minutes ago)
- 7 days retention (can be increased to 35 days)

# DB Snapshots

Manually triggered by the user
Retention of backup for as long as you want

# RDS - Storage Auto Scaling

- Helps you increase storage on your RDS DB instance dynamically
- When RDS detects you are running out of free database storage, it scales automatically
- Avoid manually scaling your database storage
- You have to set Maximum Storage Threshold (maximum limit for DB storage)
- Automatically modify storage if:
    - Free storage is less than 10% of allocated storage
    - Low-storage lasts at least 5 minutes
    - 6 hours passed since last modification
- Useful for applications with unpredictable workloads
- Supports all RDS database engines (MariaDB,MySQL,PostgreSQL,SQL Server,Oracle)


