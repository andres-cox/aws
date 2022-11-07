# S3 Security

User Based
- IAM Policies - which API calls should be allowed for a specific user from IAM console

Resource Based
- Bucket Policies -bucket wide rules from S3 console - allow cross account
- Object Access Control List (ACL) - finer grain
- Bucket Access Contorl List (ACL) - less common

Note: an IAM principal can access as S3 object if
- The user IAM permissions allow it OR the resource policy ALLOWS it
- AND there's no explicit DENY

# S3 Bucket Policies

JSON based policies 
- Resources: buckets and objects
- Actions: Set of API to Allow or Deny
- Effect: Allow / Deny
- Principal: The account or user to apply the policy to

# Use S3 bucket for policy to
- Grant access to the bucket
- Force objects to be encrypted at upload 
- Grant access to another account (Cross Account)

# Bucket settigns for Block Public Access

Block public access to buckets and objects granted through
- new access control lists (ACLs)
- ane access control lists (ACLs)
- new public bucket or access point policies

Block public and cross-account access to buckets and objects through any public bucket or access point policies

These settings were created to prevent company data leaks

If you know your bucket should never be public, leave this on

Can be set at the account level

# S3 Security - Other

Networking
- Supports VPC Endpoints (for instances in VPC without www internet)

Logging and Audit
- S3 access logs can be stored in other S3 bucket 
- API calls can be logged in AWS CloudTrail

User Security
- MFA Delete: MFA (multi factor authentication) can be required in versioned buckets to delete objects
- Pre-Signed URLs: URLs that are valid only for a limited time (ex: premium video service for logged in users)
