# ELB - Connection Draining

Feature Naming:
- CLB: Connection Draining 
- Target Group: Deregistration Delay (for ALB & NLB)

Time to complete "in-flight requests" while the instance is de-registering or unhealthy

Stop sending new requests to the instance which is de-registering

Between 1 to 3600 seconds, default is 300 seconds

Can be disabled (set value to 0)

Set to allow value if requests are short
