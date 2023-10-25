# Kinesis Data Streams

Billing is per shard provisioned, can have as many shards as you want 
Retention between 1 day (default) to 365 days
Ability to reprocess (replay) data
Once data is inserted in Kinesis, it can't be deleted (immutability)
Data that shares the same partition goes to the same shard (ordering)
Producers: AWS SDK, Kinesis Producer Library (KPL), Kinesis Agent
Consumers: 
- Write your own: Kinesis Client Library (KCL), AWS SDK
- Managed: AWS Lambda, Kinesis Data Firehose, Kinesis Data Analytics

# Kinesis Data Streams Security

Control access / authorization using IAM policies
Encryption in flight using HTTPS endpoints
Encryption at rest using KMS
You can implement encryption/decryption of data on client side (harder)
VPC Endpoints available for Kinesis to access within VPC
Monitor API calls using CloudTrail
 