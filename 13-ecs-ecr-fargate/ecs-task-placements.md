# ECS Tasks Placement

When a task of type EC2 is launched, ECS must determine where to place it, with the constraints of CPU, memory and available port.

Similarly, when a service scales in, ECS needs to determine which task to terminate

To assist with this, you can define a task placement strategy and task constraints

Note: this is only for ECS with EC2, not for Fargate.

# ECS Task Placement Process

Task placement strategies are a best effort

When Amazon ECS place tasks, it uses the following process to select container instances:
- Identify the instances that satisfy the CPU, memory and port requirements in the task definition.
- Identify the instances that satisfy the task placement constraints.
- Identify the instances that satisfy the task placement strategies.
- Select the instance for the task placement

# ECS Task Placement Strategies

Binpack:
- Place Task based in the least available amount of CPU or memory
- This minimizes the number of instances in use (cost savings)

Random:
- Place the task randomly

Spread:
- Place the task evenly based on the specific value
- Example: InstanceId, Attribute: ecs.availability-zone

You can mix them together

# ECS Task Contraints

distinctInstance: place each task in a different container instance

memberOf: places task on instances that satisfy an expression
- Uses the cluster query language (advanced) -> "attribute:ecs.instance-type =~ t2.*"