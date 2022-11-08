# AWS CLI multiple accounts

When first installing AWS CLI you set up default creds at ~/.aws/configure

You can add another profile with `aws configure --profile <new-profile>`

And run `--profile <profile>` for other commands to use those creds

# MFA with CLI

To use MFA with the CLI, you must create a temporary session

To do so, you must run the *STS GetSessionToken* API call

`aws sts get-session-token --serial-number <arn-of-the-mfa-device> --token-code <code-from-token> --duration-seconds 3600`

Once having temporary creds can add it with `aws configure --profile mfa` and also need to add `aws_session-token` in ~/.aws/configure
