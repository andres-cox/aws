# CloudFront Caching 

Cache based on
- Headers 
- Session Cookies
- Query String Parameters

The cache lives at each CloudFront Edge Location

You want to maximize the cache hit rate to minimize requests to the origin

Control the TTL (0 seconds to 1 year), can be set by the origin using the Cache-Control header, Expires header..

You can invalidate part of the cache using the CredentialInvalidation API

# CloudFront Maximize Cache hits by separating static and dynamic distributions

Static requests -> CloudFront (cached) -> s3 (static content)
Dynamic requests -> CloudFront -> ALB+EC2 (cached based on correct headers and cookies)

(See image)

# Caching Invalidations

You can invalidate cache through AWS console in CloudFront -> Invalidations -> Create Invalidation Object