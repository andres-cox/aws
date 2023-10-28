# S3 Event Notifications

S3:ObjectCreated, S3:ObjectRemoved,...
Object name filtering possible (*.jpg)
Use case: generate thumbnails of images uploaded to S3 (you can trigger SNS, SQS or async lambda for this event)

S3 event notifications typically deliver events in seconds but can sometimes take a minute or longer
If two writes are made to a single non-versioned object at the same time, it is possible that only a single event notification will be sent

If you want to ensure that an event notification is sent for every successful write, you can enable versioning on your bucket
