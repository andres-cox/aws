# S3 Websites

S3 can host static websites and have them accessible on the www

The website URL will be:
- <bucket-name>.s3-website-<AWS-region>.amazonaws.com OR
- <bucket-name>.s3-website.<AWS-region>.amazonaws.com

If you get a 403 (Forbidden) error, make sure the bucket policy allows public access reads.