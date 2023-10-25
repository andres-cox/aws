# Kinesis Firehose

Fully managed service, no administration, automatic scaling, serverless
- AWS Redshift / Amazon S3 / ElasticSearch
- 3rd party partner: Splunk / MongoDB / DataDog / NewRelic / ..
- Custom: send to any HTTP endpoint
Pay for data going through Firehose
Near Real Time
- 60 seconds latency minimum for non full batches
- Or minimum 32MB of data at a time
Supports many data formats, conversions, transformations, compression
Supports custom data transformations using AWS Lambda
Can send failed or all data to a backup S3 bucket

# Kinesis Data Streams vs Firehose

Kinesis Data Streams
- Streaming service for ingest at scale
- Write custom code (producer/consumer)
- Real-time (~200ms)
- Manage scaling (shard splitting / merging)
- Data storage for 1 to 365 days
- Supports replay capability

Kinesis Data Firehose
- Load streaming data into S3 / Redshift / ES / 3rd party / custom HTTP
- Fully managed
- Near real-time (buffer time min. 60sec)
- Automatic scaling
- No data storage
- Doesn't support replay capability


