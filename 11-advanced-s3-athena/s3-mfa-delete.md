# S3 MFA-Delete

MFA (multi factor authentication) forces user to generate a code on a device (useally a mobile phone or hardware) before doing important operations on S3

To use MFA-Delete, enable versioning on the S3 bucket

You will need MFA to:
- permanetly delete an object version
- suspend versioning on the bucket

You won't need MFA for
- enabling versioning
- listing deleted versions

Only the bucket owner (root account) can enable/disable MFA-delete
MFA-Delete can only be enable using the CLI

