# Lambda@Edge

You have deployed a CDN using CloudFront
What if you wanted to run a global AWS Lambda alongside?
Or how to implement request filtering before reaching your application?

For this you can use Lambda@Edge: deploy Lambda functions alongside your CloudFront CDN
- Build more responsive applications
- You don't manage servers, Lambda is deployed globally  
- Customize the CDN content
- Pay only for what you use

You can use Lambada to change CloudFront requests and responses:
- After CloudFront receives a request from a viewer (viewer request)
- Before CloudFront forwards the request to the origin (origin request)
- After CloudFront receives the response from the origin (origin response)
- Before CloudFront forwards the response to the viewer (viewer response)

You can also generate responses to viewers without ever sending the request to the origin

# Lambda@Edge: Use Cases

- Website Security and Privacy
- Dynamic Web Application at the Edge
- Search Engine Optimization (SEO)
- Intelligently Route Across Origins and Data Centers
- Bot Mitigation at the Edge
- Real-time Image Transformation
- A/B Testing
- User Authentication and Authorization
- User Prioritization
- User Tracking and Analytics
