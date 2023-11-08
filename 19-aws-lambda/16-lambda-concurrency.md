# Lambda Concurrency and Throttling

Concurrency limit: up to 1000 concurrent executions

Can set a "reserved concurrency" at the function level (=limit) 
Each invocation over the concurrency limit will trigger a "Throttle"
Throttle behavior:
- If synchronous invocation => return ThrottleError - 429
- If asynchronous invocation => retry automatically and then go to DLQ
If you need a higher limit, open a support ticket

# Lambda Concurrency Issue

If you don't reserve (=limit) concurrency, the following can happen:
Let's say you have 3 applications working with Lambda, and one of the suddenly got many users up to 1000 concurrent executions. This behavior then makes the other 2 applications Throttle!
The concurrency limit affects to all your lambda applications

# Concurrency and Asynchronous Invocations

If the function doesn't have enough concurrency available to process all events, additional requests are throttled.
For throttling errors (429) and system errors (500-series), Lambda returns the event to the queue and attempts to run the function again for up to 6 hours
The retry interval increases exponentially from 1 second after the first attempt to a maximum of 5 minutes

# Cold Starts & Provisioned Concurrency

Cold Start:
- New instance => code is loaded and code outside the handler run (init)
- If the init is large (code, dependencies, SDK...) this process can take some time
- First request served by new instances has higher latency than the rest

Provisioned Concurrency:
- Concurrency is allocated before the function is invoked (in advance)
- So the cold start never happens and all invocations have low latency
- Application Auto Scaling can manage concurrency (schedule or target utilization)
Note: Cold Starts in VPC have been dramatically reduced in Oct & Nov 2019 


