# ECR

ECR is a private Docker image repository

Access is control through IAM (permission errors => policy)

AWS CLI v1 login command -> $(aws ecr get-login --no-include-email --region us-west-1)
AWS CLI v2 login command -> aws ecr get-login-password --region us-west-2 | docker login --username AWS --password-stdin 123123.dsde.us-west-2.amazonaws.com

When logged you can do docker pull and docker push