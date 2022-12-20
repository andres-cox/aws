# EC2 instance types

AWS has the following Naming convetions

    m5.2xlarge

m: instance class
5: generation (AWS improve them over time)
2xlarge: size within the instance

# General Purpose
Balance Between: Compute, Memory and Networking (starts with 't','m') (t2.micro)

# Compute Optimized
Great for compute-intensive tasks that require high performance processors (starts with 'c')
    Batch processing workloads
    Media transcoding
    High performance web servers
    High performance computing (HPC)
    Scientific modeling & machine learning 
    Dedicated gaming servers

# Memory optimized 
Fast performance for workloads that process large data sets in memory (starts with 'R', 'X', 'z')
    High performance, relational/non-relational databases
    Distributed web scale cache stores
    In-memory databases optimized for BI (Business Logic)
    Applications processing real time processing of big unstructured data

# Storage Optimized
Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage (starts with 'I', 'D', 'H')
    High frequency inline transaction processing (OLTP) systems
    Relation & NoSQL databases
    Cache for in-memory databases (for example Redis)
    Data warehousing applications
    Distributed file systems

    



