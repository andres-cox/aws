# ChangeSets

When you update a stack, you need to know what changes before it happens for greater confidence
ChangeSets won't say if the update will be successful

# Nested Stacks

Nested stacks are stacks as part of other stacks
They allow you to isolate repeated patterns / common components in separate stacks and call them from other stacks
Example:
- LoadBalancer configuration that is re-used
- Security Group that is re-used
Nested stacks are considered best practice
To update a nested stack, always update the parent (root stack)

# Cross vs Nested Stacks

Cross Stacks
- Helpful when stacks have different lifecycles
- Use Outputs Export and Fn::ImportValue
- When you need to pass export values to many stacks (VPC id,...)

Nested Stacks
- Helpful when components must be re-used
- Ex: re-use how to properly configure an Application Load Balancer
- The Nested stack only is important to the higher level stack (it's not shared)

# StackSets

Create, update, or delete stacks across multiple accounts and regions with a single operation
Administrator account to create StackSets
Trusted accounts to create, update, delete stack instances from StackSets
When you update a StackSet, all associated stack instances are updated throughout all accounts and regions
