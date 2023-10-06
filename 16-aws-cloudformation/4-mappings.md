# What are mappings 

Mappings are fixed variables within your CloudFormation Template
They're very handy to differentiate between different environments (dev vs prod), regions (AWS regions), AMI types, etc.
All the values are hardcoded within the template

## When would you use mappings vs parameters?

Mappings are great when you know in advance all the values that can be taken and that they can be deduced from variables such as:
- Region
- Availability Zone
- AWS account
- Environment (dev vs prod)
They allow safer control over the template
Use parameters when the values are really user specific

## Fn::FindInMap Accessing Mapping Values
We use Fn::FindInMap to return a named value from a specific key
!FindInMap[MapName,TopLevelKey,SecondLevelKey]