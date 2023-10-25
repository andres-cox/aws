# Amazon SQS - FIFO Queue

FIFO = First In First Out (ordering of messages in the queue)
Limited throughput: 300 msg/s without batching, 3000 msg/s with
Exactly-once send capability (by removing duplicates)
Messages are processed in order by the consumer

# SQS FIFO - Deduplication

De-duplication interval is 5 minutes
Two de-duplication methods:
- Content-based deduplication: will do a SHA-256 hash of the message body
- Explicitly provide a Message Deduplication ID

# SQS FIFO - Message Grouping

If you specify the same value of MessageGroupID in an SQS FIFO queue, you can only have one consumer, and all the messages are in order
To get ordering at the level of a subset of messages, specify different values for MessageGroupID
- Messages that share a common  Message Group ID will  be in order within the group
- Each Group ID can have a different consumer (parallel processing!)
- Ordering across groups is not guaranteed 