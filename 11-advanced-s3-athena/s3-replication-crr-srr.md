# S3 Replication (Cross Region and Same Region) CRR & SRR

Must enable versioning in source and destination
Cross Region Replication (CRR)
Same Region Replication (SRR)
Buckets can be in different accounts 
Copying is asynchronous 
Must give proper IAM permissions to S3

CRR - Use Cases: compliance, lower latency access, replication across accounts
SRR - Use Cases: log aggregation, live replication between production and test accounts

# S3 Replication - Notes

After activating, only new objects are replicated (not retroactive)

For DELETE Operations:
- If you delete without a version ID, it adds a delete marker, not replicated
- If you delete with a version ID, it deletes in the source, not replicated

There is no "chaining" of replication
- If bucket 1 has replication into bucket 2, which has replication into bucket 3
- Then objects created in bucket 1 are not replicated in bucket 3
