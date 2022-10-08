# AMI Overview

AMI = Amazon Machine Image

AMI are a customization of an EC2 instance 
    You add your own software, configuration, operating system, monitoring
    Faster boot / configuration time because all your software is pre-packaged

AMI are built for a specific region (and can be copied accross regions)

You can launch EC2 instances from
    A public AMI: AWS provided
    Your own AMI: you make an maintain them yourself
    An AWS Marketplace AMI: an AMI someone else made (and potentially sells)

# AMI Process (from an EC2 instance)

Start an EC2 instance and customize it

Stop the instance (for data integrity)

Build an AMI - this will also create EBS Snapshots

Launch instances from new AMI

Note: using custom AMI make the boot proccess much faster with your configuration
