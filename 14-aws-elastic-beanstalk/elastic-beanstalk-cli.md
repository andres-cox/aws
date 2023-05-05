# Elastic Beanstalk CLI

We can install an additional CLI called the "EB cli" which makes working with Beanstalk from the cli easier

Basic commands are: eb create, eb status, eb health,...

It's helpful for your automated deployment pipelines

# Elastic Beanstalk Deployment Process

- Describe dependencies (requirements.txt for python, package.json for node.js)
- Package code as zip, and decribe dependencies 
- Console: upload zip file (creates new app version), and then deploy
- CLI: create new app version using CLI (uploads zip), and then deploy
- Elastic Beanstalk will deploy the zip on each EC2 instance, resolve dependencies and start the application
