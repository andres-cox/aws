# Elastick Beanstalk Deployments Modes

- Single Instance -> Great for dev
- High Availability -> Great for prod

# Beanstalk Deployment Options for Updates

- All at once (deploy all in one go): fastest, but instances aren't available to serve traffic for a bit (downtime) 
- Rolling: Update a few instances at a time (bucket), and then move onto the next bucket once the first bucket is ready
- Rolling with additional batches: like rolling, but spins up new instances to move the batch (so that the all application is still available)
- Immutable: spins up new instances in a new ASG, deploys version to these instances, and then swaps all the instances when everything is healthy

# All at Once

app-V1 -> turn off -> deploys app-V2

- Fastest deployment
- Application has downtime
- Great for quick iterations in develpoment environment
- No Additional costs

# Rolling

app-V1 with 4 instances -> all at once process for 2 instances -> we get 2 intances with app-V1 and other 2 instances with app-V2 -> all at once process again for remaining 2 instances

- Application is running with below capacity
- Can set the bucket size
- Application is running both versions simultaneously
- No additional cost
- Long deployment with applications that covers many instances

# Rolling with additional batches

Same process as rolling but instead of upgrading 2 instances of the current service we add 2 new instances and after follow same process, so at some point we are at overcapacity. 

- Application is running at capacity
- Can set the bucket size
- Application is running both versions simultaneously
- Small additional cost
- Longer deployment
- Good for prod

# Immutable

So roll based in ASG, by creating a new one ASG with app-V2 and the merging it to the main ASG so at this point we are with double capacity, finally we terminate app-V1 instances

- Zero downtime
- New code is deployed to new instances in a temporary ASG
- High cost double capacity
- Longest deployment
- Quick rollback in case of failures (just terminate new ASG)
- Great for prod 

# Blue / Green

- Not a "direct feature" of beanstalk
- Zero downtime and release facility
- Create a new "stage" environment and deploy v2
- The new environment (green) can be validated independently and roll back if issues
- Route53 can be setup using weighted policies to redirect a little bit of traffic to the stage environment
- Using Beanstalk "swap URLs" when done with the environment test

# Traffic Splitting

- Canary testing
- New Application version is deployed to a temporary ASG with the same capacity
- A small % of traffic is sent to the temporary ASG for a configurable amount of time
- Deployment health is monitored
- If there's a deployment failure, this triggers an automated rollback (very quick)
- No application downtime
- New instances are mitigated from the temporary to the original ASG
- Old application version is then terminated

Difference with blue green is that this one is all automated


