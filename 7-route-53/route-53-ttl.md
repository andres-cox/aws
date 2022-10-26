# DNS Records TTL (Time to live)

There is a DNS cache for TTL duration in user web browser

So if the user request a DNS (example.com) Route 53 will response with IP of DNS and it'll be cached in Web Browser for 300s (TTL: 300s)

So this way we help Route53 browser to not be overloaded by many requests.

High TTL (e.g 24 hr):
- Less traffic on DNS
- Possibly outdated records

Low TTL (e.g 60s):
- More traffic on DNS
- Records are outdated for less time
- Easy to change records

TTL is mandatory for each DNS record
