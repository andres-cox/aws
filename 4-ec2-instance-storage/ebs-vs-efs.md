# EBS vs EFS 

## EBS - Elastic Block Storage

EBS Volumes
- EBS volumes can be attached to only one instance at a time
- Are locked at the Availability Zone (AZ) leve
- gp2: IO increases if the disk size increases
- io1: can increase IO independently

To migrate an EBS across AZ
- Take a snapshot
- Restore the snapshot to another AZ
- EBS backups use IO and you shouldn't run them while your application is handling a lot of traffic

Root EBS Volumes of instances get terminated by default if the EC2 instances get terminated (can be disabled)

## EFS - Elastic File System

Mounting 100s of instances across AZ
EFS share website files (Wordpress)
Only for Linux Instances (POSIX)

EFS has a higher price point than EBS
Can leverage EFS-IA for cost savings

