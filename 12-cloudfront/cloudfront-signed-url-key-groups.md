# CloudFront Signed URL Process

Two types of Signers:
Either a trusted key group (recommended)
- Can leverage APIs to create and rotate keys (and IAM for API security)
An AWS account that contains a CloudFront Key Pair
- Need to manage keys using the root account and the AWS console
- Not recommended because you shouldn't use the root account for this

If your CloudFront distribution, create one or more trusted key groups

You generate your own public / private key
- The private key is used by your applicatons (e.g EC2) to sign URLs
- The public key (uploaded) is used by CloudFront to verify URLs


