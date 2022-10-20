# SSL / TLS Basics

An SSL Certificate allows traffic between your clients and your load balancer to be encrypted in transit. (in-flight encryption)

SSL refers to Secure Sockets Layer, used to encrypt connections 
TLS refers to Transport Layer Security, which is a newer version
Nowadays, TLS certificates are mainly used, but people still refer as SSL

Public SSL certificates are issued by Certificate Authorities (CA)
Comodo, Symantic, GoDaddy, GlobalSign, DigiCert, Letsencrypt...

SSL certificates have an expiration date (you set) and must be renewed

# Load Balancer - SSL Certificates

Users -> HTTPS(encrypted)-> LB -> HTTP (Private VPC) -> EC2 instance

The load balancer uses an x.509 certificate (SSL/TLS server certificate)
You can manage certificates using ACM (Amazon Certificate Manager)
You can create upload your own certificates alternatively
HTTPS Listener:
- You must specify a default certificate
- You can add an optional list of certs to support multiple domains
- Clients can us SNI (Server Name Indication) to specify the hostname they reach
- Ability to specify a security policy to support older versions of SSL/TLS (legacy clients)

# SNI - Server Name Indication

- SNI solves the problem of loading multiple SSL certificates onto one web server (to serve multiple websites)
- It's a newer protocol, and requires the client to indicate the hostname of the target server in the initial SSL handshake.
- The server will then find the correct certificate, or return the default one

Note:
Only works for ALB and NLB (newer generation), Cloudfront
Does not work for CLB (older generation)

# Elastic Load Balancers - SSL certificates

Classic Load Balancer
- Supports only one SSL certificate
- Must use multiple CLB for multiple hostname with multiple SSL certificates

Application Load Balancer
- Supports multiple listeners with multiple SSL certificates
- Uses Server Name Indication (SNI) to make it work

Network Load Balancer
- Supports multiple listeners with multiple SSL certificates
- Users Server Name Indication (SNI) to make it work

