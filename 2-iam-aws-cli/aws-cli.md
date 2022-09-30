# How can users acess AWS?

To access aws you have 3 options:

    - AWS Management Console (Protected by password + MFA)
    - AWS Command Line Interface (CLI): protected by access keys
    - AWS Software Developer Kit (SDK) - for code: protected by access keys

Access key are genereated through the AWS console

Users manage their own access keys (DON'T SHARE THEM) 

# Once installed

With access and secret keys (select your IAM user and go to security creadentials)

aws configure

aws iam list-users

# AWS Cloud Shell

You can use aws cli in the cloud with AWS cloud shell, it'll be already  installed 