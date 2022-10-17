# EBS Volume Types

EBS Volumes come in 6 types
- gp2/gp3 (SSD): General purpose SSD volume that balances price and performance for a wide variety of workloads
- io1/io2 (SSD): Higlyhest-performance SSD volume for mission-critical low-latency or high-throughput workloads
- st1(HDD): Low Cost HDD volume designed for frequently accessed, throughput-intensive workloads
- sc1(HDD): Lowest Cost HDD volume designed for less frecuency accessed workloads

EBS Volumes are characterized in Size | Throughput | IOPS (I/O Ops Per Sec)
When in doubt always consult aws documentation - it's good
Only gp2/gp3 and io1/io2 can be used as boot volumes

# EBS Volume Types Use Cases

## General Purpose SSD
Cost effective storage, low-latency
System boot volumes, Virtual Desktops, development and test environments
1 GiB - 16TiB 
gp3:
    Baseline of 3000 IOPS and throughput of 125MiB/s
    Can increase IOPS up to 16000 and throughput to 100MiB/s independently
gp2:
    Small gp2 volumes can burst IOPS to 3000
    Size of the volume and IOPS are linked, max IOPS is 16000
    3 IOPS per GB, means at 5334GB we are at the mas IOPS

## Provisioned IOPS (PIOPS) SSD
Critical business applications with sustained IOPS performance
Or applications that need more than 1600 IOPS
Great for Database workloads (sensitive to storage perf and consistency)
io1/io2 (4GiB - 16GiB)
    Max PIOPS: 64000 for Nitro EC2 instances & 32000 for other
    Can increase PIOPS independently from storage size
    io2 have more durability and more IOPS per GiB (at the same price as io1)
io2 Block Express (4GiB - 64TiB)
    Sub-millisecond latency
    Max PIOPS: 256000 with an IOPS:GiB ratio of 1000:1
Supports EBS Multi-attach

## Hard Disk Drives (HDD)
Cannot be a boot volume
125MiB to 16TiB
Throughput Optimized HDD (st1)
    Big Data, Data Warehouses, Log Processing
    Max Throughput 500 MiB/s - max IOPS 500
Cold HDD (sc1)
    For data that is infrequently accessed
    Scenarios were lower cost is important
    Max througput 250MiB/s - max IOPS 250


