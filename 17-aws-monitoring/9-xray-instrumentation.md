# X-Ray Instrumentation in your code

Instrumentation means the measure of product's performance, diagnose errors, and to write trace information
To instrument your application code, you use the X-Ray SDK
Many SDK require only configuration changes
You can modify your application code to customize and annotation the data that the SDK sends to X-Ray, using interceptors, filters, handlers, middleware

# X-Ray Concepts

Segments: Each application / service will send them
Subsegments: if you need more details in your segment
Trace: segments collected together to form an end-to-end trace
Sampling: decrease the amount of requests send to X-Ray, reduce cost
Annotations: Key Value pairs used to index traces and use with filters
Metadata: Key Value pairs, not indexed, not used for searching

The X-Ray daemon / agent has a config to send traces cross account:
- make sure the IAM permissions are correct - the agent will assume the role
- This allows to have a central account for all your application tracing

# X-Ray Sampling Rules

With sampling rules, you control the amount of data that you record
You can modify sampling rules without changing your code

By default, the X-Ray SDK records the first request each second, and five percent of any additional requests
One request per second is the reservoir, which ensure that at least one trace is recorded each second as long the service is serving requests
Five percent is the rate at which additional requests beyond the reservoir size are sampled

# X-Ray Custom Sampling Rules

You can create your own rules with reservoir and rate
Minimum rate: Reservoir: 10, Rate: 0.10 (minimum rate 10%, just to keep track everything is looking good)
Debugging: Reservoir: 1, Rate: 1 (trace all requests, more expensive, useful for temporarily troubleshooting) 


