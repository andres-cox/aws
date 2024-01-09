# DynamoDB

NoSQL Serverless Database

# Traditional Architecture

Traditional applications leverage RDBMS databases
These databases have the SQL query language
Strong requirements about the data how should be modeled
Ability to do join, aggregations, computations
Vertical scaling (means usually getting a more powerful CPU/RAM/IO)

# NoSQL Databases

NonSQL databases are non-relational databases and are distributed
NonSQL databases include MongoDB, DynamoDB, etc
NonSQL databases do not support join
All the data that is needed for a query is present in one row
NonSQL databases don't perform aggregations such as "SUM"
NonSQL databases scale horizontally

There is no "right or wrong" for NoSQL vs SQL, they just require to model the data differently and think about user queries differently

# DynamoDB

Fully managed, High available with replication across 3 AZ
NoSQL database - not a relational database
Scales to massive workloads, distributed database
Millions of requests per seconds, trillions of row, hundreds of TB of storage
Fast and consistent in performance (low latency on retrieval)
Integrated with IAM for security, authorization and administration
Enables event driven programming with DynamoDB Streams
Low cost and auto scaling capabilities 

# DynamoDB - Basics

DynamoDB is made of tables
Each table has a primary key (must be decided at creation time)
Each table can have an infinite number of items (=rows)
Each item has attributes (can be added over time - can be null)
Maximum size of a item is 400KB
Data types supported are:
- Scalar Types: String, Number, Binary, Boolean, Null
- Document Types: List, Map
- Set Types: String Set, Number Set, Binary Set

# DynamoDB - Primary Keys

Option 1: Partition key only (HASH)
Partition key must be unique for each item
Partition key must be "diverse" so that the data is distributed
Example: user_id for a users table

Option 2: Partition key + Sort key
The combination must be unique
Data is grouped by partition key
Sort key == range key
Example; user-games table
- user_id for the partition key
- game_id for the sort key

# DynamoDB - Partition Keys exercise

We're building a movie database
What is the best partition key to maximize data distribution?
- movie_id
- producer_name
- leader_actor_name
- movie_language
movie_id has the highest cardinality so it's a good candidate
movie_language doesn't take many values and may be skewed towards English so it's not a great partition key