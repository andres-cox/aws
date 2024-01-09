# DynamoDB = Provisioned Throughput

Table must have provisioned read and write capacity units
Read Capacity Units (RCU): Throughput for reads
Write Capacity Units (WCU): Throughput for writes
Option to setup auto-scaling of throughput to meet demands
Throughput can be exceeded temporary using "burst credit"
If burst credit are empty, you'll get a "ProvisionedThroughputException"
It's then advised to do an exponential back-off retry

# DynamoDB - Write Capacity Units

One write capacity unit represents one write per second for an item up to 1KB in size
If the items are larger than 1KB, more WCU are consumed

Example 1: We write 10 objects per seconds of 2KB each.
- We need 2*10 = 20WCU
Example 2: We write 6 objects per second of 4.5KB each
- We need 6*5 = 30WCU (4.5 gets rounded to the upper KB)
Example 3: We write 120 objects per minute of 2KB each
- We need 120/60 * 2 = 4WCU

# Strongly Consistent Read vs Eventually Consistent Read

Eventually Consistent Read: If we read just after a write, it's possible we'll get unexpected response because of replication
Strongly Consistent Read: If we read just after a write, we will get the correct data
By Default: DynamoDB uses Eventually Consistent Read, but GetItem, Query & Scan provide a "ConsistentRead" parameter you can set to True

# DynamoDB - Read Capacity Units

One read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4KB in size.
If the items are larger than 4KB, more RCU are consumed

Example 1: 10 strongly consistent reads per seconds of 4KB each
- We need 10*4KB/4KB = 10RCU
Example 2: 16 eventually consistent reads per seconds of 12KB each 
- We need (16/2)*(12/4) = 24RCU
Example 3: 10 strongly consistent reads per seconds of 6 KB each
- We need 10*8KB/4KB = 20RCU (we have to round up 6KB to 8KB)

# DynamoDB - Partitions Internal

Data is divided in partitions
Partition keys go through a hashing algorithm to know to which partition they go to
To compute the number of partitions:
- By capacity: (TOTAL RCU / 3000) + (TOTAL WCU / 1000)
- By size: Total Size / 10GB
- Total partitions = CEILING(MAX(Capacity,Size))

WCU and RCU are spread evenly between partitions

# DynamoDB - Throttling

If we exceed our RCU or WCU, we get ProvisionedThroughputExceededExceptions
Reasons:
- Hot keys: one partition key is being read too many times (popular item for ex)
- Hot partitions:
- Very large items: remember RCU and WCU depends on size of items
Solutions:
- Exponential back-off when exception is encountered (already in SDK)
- Distribute partition key as much as possible
- If RCU issue, we can use DynamoDB Accelerator (DAX)
