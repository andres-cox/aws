# Amazon ElastiCache Overview

The same way RDS is to get managed Relational Databases..
EslastiCache is to get managed Redis or Memcached
Caches are in-memory databases with really high permformance, low latency
Helps reduce load off of databases for read intensive workloads
Helps make your application Stateless
AWS takes care of OS maintainance / patching, optimizations, setup, configuration, monitoring, failure recovery and backups
"Using ElastiCache involves heavy application code changes

# ElastiCache Solution Architecture - DB Cache

Application Queries ElastiCache, if not available, get from RDS and store in ElastiCache
Helps Relieve load in RDS
Cache must have an invalidation strategy to make sure only the most current data is used there. (This is challenging)

# ElastiCache Solution Architecture - User Session Store

User logs into any of the application 
The application writes the session data into ElastiCache
The user hits another instance of our application
The instance retrieves the data and the user is already logged in

# ElastiCache - Redis vs Memcached 

Redis:
- Multi AZ with Auto-Failover
- Read Replicas to scale reads and have high availability
- Data Durability using AOF persistance
- Backup and restore features

Memcached:
- Multinode for partitioning of data (sharding)
- No high availability
- Non persistent
- No backup and restore
- Multi-threaded architecture
