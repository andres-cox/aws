# What's an EBS volume 

An EBS (Elastic Block Store) Volume is a network drive you can attach to your instances while they run 

It allow your instances to persist data, even after their termination

They can only be mounted to one instance at a time (at the CCP level)

They are bound to a specific availability zone

Analogy: Think of them as a "network USB stick"

# EBS Volume

It's a network drive
    It uses the network to communicate the instance, which means ther might be a bit of latency 
    It can be detached from an EC2 instance and attached to another one quickly

It's looked to an availability zone (AZ)
    An EBS Volume in us-east-1a cannot be attached to us-easst-1b
    To move a volume across, yuo first need to snapshot it

Have a provisioned capacity (Size in GBs, and IOPS)
    You get billed for all the provisioned capacity
    You can increase the capacity of the drive over time

# EBS - Delete on Termination attribute

Controls the EBS behaviour when an EC2 instance terminates 
    By default, the root EBS volume is deleted (attribute enabled)
    By default, any other attached EBS volume is not deleted (attribute disabled)

This can be controlled by AWS Console / AWS CLI

Use case: preserve root volume when instance is terminated



