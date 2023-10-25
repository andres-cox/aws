# AWS Integration & Messaging

When we start deploying multiple applications, they will inevitably need to communicate with one another
There are two patterns of application communication
- Synchronous communications (application to application)
- Asynchronous / Event based (application to queue to application)

Synchronous between applications can be problematic if there are sudden spikes of traffic
What if you need to suddenly encode 1000 videos but usually it's 10?

In that case, it's better to decouple your applications,
- Using SQS: queue model
- Using SNS: pub/sub model
- Using Kinesis: real-time streaming model

These services can scale independently from our application!