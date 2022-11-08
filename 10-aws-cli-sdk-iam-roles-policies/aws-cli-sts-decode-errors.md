# AWS CLI STS Decode Errors

When you run API calls and they fail, you can get a long error message 

This error message can be decoded using STS command line:
*sts decode-authorization-message*

```
aws sts decode-authorization-message --encoded-message <value-encoded>
```


