# EBS Multi-Attach - io1/io2 family

Attach the same EBS voume to multiple EC2 instances in the same AZ

Each instance has full read & write permission to the volume

Use case: 
    Achieve higher application availability in clusterd Linux Applications (ex.Teradata)
    Applications must manage concurrent write operations

Must use a file system that's cluster-aware (not XFS,ex4,etc..)