# Amazon S3 Overview - Buckets

Amazon S3 allows people to store objects (files) in "buckets" (directories)
Buckets must have a globally unique name
Buckets are defined at the region level
Naming Convention
- No uppercase
- No underscore
- 3-63 characters long
- Not an IP
- Must start with lowercase letter or number

# Amazon S3 Overview - Objects

Objects (files) have a key
The key is the FULL path (after my-bucket)
- s3://my-bucket/my_file.txt
- s3://my-bucket/my_folder1/another_folder/my_file.txt

The key is composed of prefix + object name
- s3://my-bucket/my_folder1/another_folder/my_file.txt
                |          prefix         |  objectname |

There is no concept of directories within buckets (although the UI will trick you to think otherwise)
Just keys with very long names that containe slashes ("/")

Object values are the content of the body
- Max object size is 5TB (5000GB)
- If uploading more than 5GB, must use "multi-part upload"

Metadata (list of text key / value pairs - system or user metadata)
Tags (Unicode key / value pair - up to 10) - useful for security / lifecycle
Version ID (if versioning is enabled)
