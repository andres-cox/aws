# EC2 instance role

Never ever set 'aws configure' access and secret key inside ec2 instance

It's a security issues, if a person has acces to your ec2 instance will have access to those keys as well

For this pupose we can create an IAM role for the instance and that will automaticly give permissions to AWS CLI in the instance.

You can customize yout IAM role to least privilage principle for this instance