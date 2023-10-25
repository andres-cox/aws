# SQS vs SNS vs Kinesis

SQS:
- Consumer "pull data"
- Data is deleted after being consumed
- Can have as many workers (consumers as we want)
- No need to provision throughput
- No ordering guaranteed (except FIFO queues)
- Individual message delay capability

SNS:
- Push data to many subscribers
- Up to 10 million subscribers
- Data is not persisted (lost if not delivered)
- Pub/Sub (Publish subscribe pattern)
- Up to 100000 topics
- No need to provision throughput
- Integrates with SQS for fan out architecture pattern 

Kinesis:
- Consumers "pull data"
- As many consumers as we want
- Possibility to replay data
- Meant for real-time big data, analytics and ETL
- Ordering at the shard level
- Data expires after X days
- Must provision throughput   
