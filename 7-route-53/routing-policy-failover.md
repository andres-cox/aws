# Failover Routing Policy

For this policy Health Checks are mandatory

Let's say we have two instances for one domain:
- First one is the primary (health check has to be enabled)
- And the second is the secondary for disaster recovery

So if there is a request to Route53 and we have good health in primary it'll send it to it but if it's unhealthy Route53 is smart enough to failover to the secondary with this policy.