# EC2 Instance storage

EBS volumes are network drives with but "limited" performance

If you need a high-performance hardware disk, use EC2 Instance Store

Better I/O performance 
EC2 Instance store lose their storage if they are stopped (ephemeral)
Good for buffer / cache / scratch data / temporary content 
Risk of data loss if hardware fails
Backups and Replication are your responsability

* Very High IOPS (2 times faster than EBS)