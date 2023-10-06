# What are parameters

Parameters are a way to provide inputs to your AWS CloudFormation template
They are important to know about if:
- You want to reuse your templates across the company
- Some inputs can not be determined ahead of time
Parameters extremely powerful, controlled, and can prevent errors from happening in your templates thanks to types

Ask your self this:
- Is this CloudFormation resource configuration likely to change in the future
- If so, make it a parameter
You won't have to re-upload a template to change its content

## How to Reference a Parameter

The Fn::Ref function can be leveraged to reference parameters
Parameters can be used anywhere in a template
The shorthand for this in YAML is !Ref
The function can also reference other elements within the template

## Concept:Pseudo Parameters 

AWS offers us pseudo parameters in any CloudFormation template
These can be used at any time and are enabled by default 