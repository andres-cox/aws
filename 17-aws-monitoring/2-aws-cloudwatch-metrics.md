# AWS CloudWatch Metrics

CloudWatch provide metrics for every services in AWS
Metric is a variable to monitor (CPU Utilization, NetworkIn, NetworkOut..)
Metrics belong to namespaces
Dimension is an attribute of a metric (instance id, environment, etc..)
Up to 10 dimensions per metric
Metrics have timestamps
Can create CloudWatch dashboards of metrics

# AWS CloudWatch EC2 Detailed Monitoring
EC2 instance metrics have metrics "every 5 minutes"
With detailed monitoring (for a cost), you get data "every 1 minute"
Use detailed monitoring if you want to more prompt scale your ASG!
The AWS free tier allow us to have 10 detailed monitoring metrics
Note: EC2 memory usage is by default not pushed (must be pushed from inside the instance as a custom metric)

# AWS CloudWatch Custom Metrics

Possibility to define and send your own custom metrics to CloudWatch
Ability to use dimensions (attributes) to segment metrics
- Instance.id
- Environment.name
Metric Resolution
- Standard 1 minute
- High resolution up to 1 second (StorageResolution API parameter) - Higher cost
Use API call PutMetricData
Use exponential back off in case of throttle errors
