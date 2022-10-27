# Weighted Routing Policy

Control the % of the requests that go to specific endpoint
Ex:
instance a weight: 70% 
instance b weight: 20% 
instance c weight: 10%
All a,b,c instances are targeted for a specific domain, so route53 will route requests based on weight 

Helpful to test 1% of traffic on new app version for example

Helpful to split traffic between two regions

Can be associated with Health Checks