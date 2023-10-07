# Why Monitoring is important

We know how to deploy applications
- Safely
- Automatically
- Using Infrastructure as Code
- Leveraging the best AWS components
Our applications are deployed, and users don't care how we did it

Our applications only care that the application is working!
- Application latency: Will it increase over time?
- Application outages: customer experience should not be degraded
- Users contacting the IT department or complaining is not a good outcome
- Troubleshooting and remediation

Internal Monitoring
- Can we prevent issues before they happen?
- Performance and Cost
- Trends (scaling patterns)
- Learning and Improvement

# Monitoring in AWS 

AWS CloudWatch:
- Metrics: Collect and track key metrics
- Logs: Collect, monitor analyze and store log files
- Events: Send notifications when certain events happen in your AWS
- Alarms: React in real-time to metrics / events

AWS X-Ray:
- Troubleshooting application performance and errors
- Distributed tracing of microservices

AWS CloudTrail:
- Internal Monitoring of API calls being made
- Audit changes to AWS resources by your users
