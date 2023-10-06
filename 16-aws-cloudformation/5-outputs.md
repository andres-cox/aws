# What are Outputs

The Outputs section declares optional outputs values that we can import into other stacks (if you export them first)
You can also view the outputs in the AWS console or in using the AWS CLI
They're very useful for example if you define a network CloudFormation, and output the variables such as VPC ID and your Subnet IDs
It's the best way to perform some collaboration cross stack, as you let expert handle their own part of the stack
You can't delete a CloudFormation Stack if its outputs are being referenced by another CloudFormation stack

# Cross Stack Reference

See docs for syntax. 