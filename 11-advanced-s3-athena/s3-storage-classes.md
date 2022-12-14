# S3 Storage Classes

- Amazon S3 Standard - General Purpose
- Amazon S3 Standard - Infrequent Access (IA)
- Amazon S3 One Zone - Infrecuent Access
- Amazon S3 Intelligent Tiering
- Amazon Glacier
- Amazon Glacier Deep Archive
- Amazon S3 Reduced Redundancy Storage (deprecated-omitted)

# S3 Standard - General Purpose

- High durability (99.99999%) of objects across multiple AZ
- If you store 10,000,000 objects with Amazon S3, you can on average expect to incur a loss of a single object once every 10,000 years
- 99,99% Availability over a given year
- Sustain 2 concurrent facility failures

Uses cases: Big Data analitics, mobile & gaming applications, content distribution..

# S3 Standard - Infrequent Access (IA)

- Suitable for data that is less frequently, but requires rapid access when needed
- High durability (99.99999999%) of objects across multiple AZs
- 99.9% Availability
- Low cost compared to Amazon S3 Standard
- Sustain 2 concurrent faciliry failures

Use cases: As a data store for disaster recovery, backups..

# S3 One Zone - Infrecuent Access

- Same as IA but data is stored in a single AZ
- High durability (99.9999999%) of objects in a single AZ; data lost when AZ is destroyed
- 99.5%
- Low latency and high throughput performance
- Supports SSL for data at transit and encryption at rest
- Low cost compared to IA (by 20%)

Use Cases: Storing secondary backup copies of on-premise data, or storing data you can recreate (like thumbnails)

# S3 Intelligent Tiering 

- Same low latency and high throughput performance of S3 Standard
- Small monthly monitoring and auto-tiering fee
- Automatically moves objects between two access tiers based on changing access patterns
- Designed for durability og 99.9999999% of objects across multiple Availability Zones
- Resilient against events that impact an entire Availability Zone
- Designed for 99.9% availability over a given year

# Amazon Glacier 

- Low cost object storage meant for archiving / backup
- Data is retained for the longer term (10s of years)
- Alternative to on-premise magnetic taoe storage
- Average annual durability is 99,999999999%
- Cost per storage per month (%0.004 / GB) + retrieval cost
- Each item in Glacier is called "Archive" (up to 40TB)
- Archives are stored in "Vaults"
 
# Amazon Glacier & Glacier Deep Archive

Amazon Glacier - 3 retrieval options:
- Expedited (1 to 5 minutes)
- Standard (3 to 5 hours)
- Bulk (5 to 12 hours)
- Minimum storage duration of 90 days

Amazon Glacier Deep Archive - for long term storage - cheaper:
- Standard (12 hours)
- Bulk (48 hours)
- Minimum storage duration of 180 days
