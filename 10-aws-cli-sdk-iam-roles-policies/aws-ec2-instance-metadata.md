# AWS EC2 Instance Metadata

AWS EC2 Instance Metadata is powerful but one of the least known features to developers

It allows AWS EC2 instances to "learn about themselves" withput using an IAM Role for that purpose

The URL is http://169.254.169.254/latest/meta-data (only can be access from EC2 instance, can use curl)

You can retrieve the IAM Role name from the metadata, but you CANNOT retrieve the IAM Policy

Metadata = Info about the EC2 instance
Userdata = launch script of the EC2 instance

