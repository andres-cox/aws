# IAM: Users & Groups

IAM: Identity and Access Management (Global Service)

Root account created by default, shouldn't be used or shared

Users are people within your organiation and can be grouped

Groups only contain users not other groups

Users don't have to belong to a group and user can belong to multiple groups

# IAM: Permissions

Users and groups can be assigned JSON documents called policies

These policies define the permissions of the user

In AWS you apply the least privilege principle: Don't give more permissions than a user needs

# Notes

It's a best practice to create a custom IAM user instead of the root one
With a new IAM user you can login to aws using your alias or the new account id
 