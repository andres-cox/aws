# Kinesis Producers

Puts data records into data streams
Data record consists of:
- Sequence number (unique per partition-key within shard)
- Partition key (must specify while put records into stream)
- Data blob (up to 1 MB)
Producers:
- AWS SDK: simple producer
- Kinesis Producer Library (KPL): C++, Java, batch, comprehension, retries
- Kinesis Agent: monitor log files
Write throughput: 1 MB/sec or 1000 records/sec per shard
PutRecord API
Use batching with PutRecords API to reduce costs & increase throughput

# Kinesis - ProvisionedThroughputExceeded

If at some point you are overproducing to one shard from 1MB/sec to 2MB/sec for some reason, you will get  ProvisionedThroughputExceeded exception  
Solution:
- Use highly distributed partition key
- Retries with exponential backoff
- Increase shards (scaling)