# X-Ray Write APIs (used by the X-Ray daemon)

PutTraceSegments: Uploads segment documents to AWS X-Ray
PutTelemetryRecords: Used by the AWS X-Ray daemon to upload telemetry
- SegmentReceivedCount, SegmentRejectedCounts, BackendConnectionErrors
GetSamplingRules: Retrieve all sampling rules (to know what/when to send)
GetSamplingTargets & GetSamplingStaticsSummaries: advanced
The X-Ray daemon needs to have an IAM policy authorizing the correct API calls to function correctly 
GetServiceGraph: main graph
BatchGetTraces: Retrieves a list of traces specified by ID. Each trace is a collection of segment documents that originates from a single request
GetTraceSummaries: Retrieves IDs and annotations for traces available for a specific time frame using and optional filter. To get the full traces, pass the trace IDs to BatchGetTraces
GetTraceGraph: Retrieves a service graph for one or more specific trace IDs
