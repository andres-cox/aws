# X-Ray with Elastic Beanstalk

AWS Elastic Beanstalk platform includes the X-Ray daemon
You can run the daemon by setting an option in the Elastic Beanstalk console or with a configuration file (in .ebsextensions/xray-daemon.config)
Make sure to give your instance profile the correct IAM permissions so that the X-Ray daemon can function correctly
Then make sure your application code is instrumented with the X-Ray SDK
Note: The X-Ray daemon is not provided for Multicontainer Docker