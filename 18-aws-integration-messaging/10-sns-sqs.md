# SNS + SQS: Fan Out

Push once in SNS, receive in all SQS queues that are subscribers
Fully decoupled, no data loss
SQS allows for: data persistance, delayed processing and retries of work
Ability to add more SQS subscribers over time
Make sure SQS queue access policy allows for SNS to write

# Application: S3 Events to multiple queues

For the same combination of: event type (e.g. object create) and prefix (e.g. images/) you can only have one S3 Event rule
If you want to send the same S3 event to many SQS queues, use fan out

# Amazon SNS - FIFO Topic

FIFO = First In First Out (ordering messages in the topic)
Similar features as SQS FIFO
- Ordering by Message Group ID (all messages in the same group are ordered)
- Deduplication using a Deduplication ID or Content Based Deduplication
Can only have SQS FIFO queues as Subscribers
Limited throughput (same throughput as SQS FIFO)

# SNS FIFO + SQS FIFO: Fan Out

In case you need fan out + ordering + deduplication
Buying service -> SNS FIFO topic -> SQS FIFO Queue -> Shipping Service

# SNS - Message Filtering

JSON policy used to filter messages sent to SNS topic's subscriptions
If a subscription doesn't have a filter policy, it receives every message
You can have an SQS Queue for each filter. So you have different actions for each scenario based in filter criteria.