# Geoproximity Routing Policy

Route traffic to your resources based on the geographic location of users and resources

Ability to shift more traffic to resources based in the defined bias

To change the size of the geographic region, specify bias values:
- To expand (1 to 99) - more traffic to the resource
- To shrink (-1 to -99) - less traffic to the resource 

Resources can be:
- AWS resources (specify AWS region)
- Non-AWS resources (specify Latitude and Longitude)

You must use Route53 Traffic Flow (advanced) to use this feature

This is helpful when you want to shift more traffic to a specific region (so you increase bias)