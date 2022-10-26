# CNAME vs Alias

AWS Resources (Load Balancers, CloudFront..) expose an AWS hostname: lb1-1234.us-east-2.elb.amazonaws.com and you want myapp.mydomain.com

CNAME:
- Points a Hostname to any other hostname. (app.mydomain.com => blabla.anything.com)
- ONLY FOR NON ROOT DOMAIN (ex: something.mydomain.com)

Alias:
- Points a Hostname to an AWS resource (app.mydomain.com => blabla.anything.com)
- Works for ROOT DOMAIN and NON ROOT DOMAIN (ex: mydomain.com)
- Free of charge 
- Native Health Check