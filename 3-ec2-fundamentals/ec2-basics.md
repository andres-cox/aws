# EC2 Basics

EC2 is one of the most popular OF AWS' offering

EC2 = Elastic Compute Cloud = Infrastructure as a Service 

It mainly consists  in the capacity of:
    Renting Virtual Machines (EC2)
    Storing data in virtual devices (EBS)
    Distributing Load across Machines (ELB)
    Scaling the services using an auto-scaling group (ASG)

Knowing  EC2 is fundamental to understand whow the cloud works

# EC2 sizing & configuration options

- Operating system (OS): Linux, Windows or Mac OS
- How much compute power & cores (CPU)
- How much random-access memory (RAM)
- How much storage space:
    Network-attached (EBS & EFS)
    Hardware (EC2 instance store)
- Network card: speed of the card, Public Ip address
- Firewall rules: security group
- Bootstrap script (configure at first lunch): EC2 user data

# EC2 User data 

It's possible to bootstrap our instances using EC2 User data script
Boostraping means launching commands when a machine starts
That script is only run once at the instance first start
EC2 user data is used to automate boot tasks such as:
    Installing updates
    Installing software
    Downloading common files from the internet
    Anything you can think of
The EC2 User Data Script runs with the root user
