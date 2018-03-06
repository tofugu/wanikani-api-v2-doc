## Errors

> Errors with a message will return with the follow response body structure:

```
{ "error": <string> }
```

The WaniKani API uses the following error codes:

Error Code | Meaning | Message
---------- | ------- | -------
400 | Bad Request |
401 | Unauthorized | Bad credentials
403 | Forbidden | Rate Limit Exceeded
404 | Not Found |
500 | Internal Server Error |
503 | Service Unavailable |
