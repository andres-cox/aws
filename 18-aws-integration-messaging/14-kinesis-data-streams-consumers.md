# Kinesis Data Streams Consumers

Get data records from data streams and process them
- AWS Lambda
- Kinesis Data Analytics
- Kinesis Data Firehose
- Custom Consumer (AWS SDK) - Classic or Enhanced Fan-Out
- Kinesis Client Library (KCL): library to simplify reading from data stream

# Kinesis Consumers - Custom Consumer

Shared (Classic) Fan-out Consumer -> 2 MB/sec per shard across all consumers
Enhanced Fan-out Consumer -> 2 MB/sec per consumer per shard

# Kinesis Consumers Types

Shared (Classic) Fan-out Consumer - pull
- Low number of consuming applications
- Read throughput: 2 MB/sec per shard across all consumers
- Max. 5 GetRecords API calls/sec
- Latency ~200ms 
- Minimize cost ($)
- Consumers poll data from Kinesis using GetRecords API call
- Returns up to 10 MB (then throttle for 5 seconds) or up to 10000 records

Enhanced Fan-out Consumer - push
- Multiple consuming applications for the same stream
- 2 MB/sec per consumer per shard
- Latency ~70ms
- Higher costs ($$$)
- Kinesis pushes data to consumers over HTTP/2 (SubscribeToShard API)
- Soft limit of 5 consumer applications (KCL) per data stream (default)

# Kinesis Consumers - AWS Lambda

- Supports Classic & Enhanced fan-out consumers
- Read records in batches
- Can configure batch size and batch window
- If error occurs, Lambda retries until succeed or data expired
- Can process up to 10 batches per shard simultaneously


