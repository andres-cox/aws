# Elastic Beanstalsk Migration

## Load Balancer

After creating an Elastic Beanstalk environment, you cannot change the Elastic Load Balancer type (only the configuration)

To migrate:
- create a new environment with the same configuration except LB (can't clone)
- deploy your application onto the new environment
- perform a CNAME swap or route53 dns update

## RDS with Elastic Beanstalk

RDS can ve provisioned with Beanstalk, which is great for dev / test
This is not great for prod as the database lifecycle is tied to the Beanstalk environment lifecycle
The best for prod is to separatly create an RDS database and provide our EB applicaction with the connection string

Decouple RDS
- Create a snapshot of RDS DB (as a safeguard)
- Go to the RDS console and protect the RDS database from deletion
- Create a new Elastic Beanstalk environment, withoit RDS, point your application to existing RDS
- Perform a CNAME swap (blue/green) or Route53 update, confirm working
- Terminate the old environment (RDS won't be deleted)
- Delete CloudFormation stack (in DELETE_FAILED state)