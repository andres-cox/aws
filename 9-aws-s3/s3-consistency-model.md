# Amazon S3 - Consistency Model 

Strong consistency as of December 2020

After a:
- Successful write of a new object (new PUT)
- or an overwrite or delete of an existing object (overwrite PUT or Delete)

..any:
- Subsequent read request immediatly receives the latest version of the object (read after write consistency)
- Subsequent list request immediatly reflects changes (list consistency)

Available at no additional cost, without any performance impact