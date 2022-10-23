# Caching Implementation Considerations

- Is it safe to cache data? Data may be out of date, eventually consistent
- Is caching effective for that data?
    - Pattern: data changing slowly, few keys are frequent needed 
    - Anti patterns: data changing rapidly, all large key space frequently needed
- Is data structured well for caching?
    - example: key value caching or caching of aggregations results

Which Caching Dessign is the most appropriate?

# Lazy Loading / Cache-Aside / Lazy Population

See image

Pros:
- Only requested data is cached (the cache isn't filled up with unused data)
- Node failures are not fatal

Cons:
- Cache miss penalty that results in 3 round trips, noticeable delay of that request (impact user experience)
- State data: data can be updated in the database and outdated in the cache

# Write Through - Add or update cache when database is updated

See image

Pros:
- Data in cache is never stale, reads are quick 
- Write penalty vs Read penalty (each write require 2 calls)

Cons: 
- Missing data until is added / updated in the DB. Mitigation is to implement Lazy Laoding strategy as well
- Cache churn - a lot of the data will never read

# Cache Evictions and Time To Live (TTL)

Cache eviction can occur in three ways:
- You delete the item explicity in the cache
- Item is evicted and the memory is full and it's not recently used (LRU)
- You set an item time-to-live (TTL)

TTL are helpful for any kind of data:
- Leaderboards
- Comments
- Activity Streams

TTL can range from few seconds to hours or days

If too many evictions happen due to memory, you should scale up or out

# Final words of wisdom

- Lazy Loading / Cache aside is easy to implement and works for many situtations as a foundation, especially on the read side
- Write-through is usually combined with Lazy Loading as targeted for the queries or workloads that benefit from this optimization
- Setting a TTL is usually not a bad idea, except when you are using Write-Through. Set it to a sensible value for your application
- Only cache the data that makes sense (user profiles, blogs, etc)

Quote: There are only two hard things in Computer Science: cache invalidation and naming things 
