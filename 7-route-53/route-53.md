# AWS Route 53 Overview

Route53 is a managed DNS (Domain Name System)

DNS is a collection of rules and records which helps clients understand how to reach a server throughits domain name

In AWS, the most common records are:
- A: hostname to IPv4
- AAAA: hostname to IPv6
- CNAME: hostname to hostname
- Alias: hostname to AWS resource

Route53 can use:
- public domain names you own (or buy) -> application1.mypublicdomain.com
- private domain names that can be resolved by your instances in your VPCs -> application1.company.internal

Route53 has advanced features such as:
- Load Balancing (thorugh DNS - also called client load balancing)
- Health Checks (although limited..)
- Routing Policy: simple, failover, geolocalization, latency, weighted, multi value

You pay $0.50 per month per hosted zone

