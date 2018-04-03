## Errors

> Errors with a message will return with the follow response body structure:

```
{ "error": <string>, "code": <integer> }
```

We use the standard HTTP response codes to indicate the status of the response. Codes in the 200s indicate success, 400s usually indicate a client configuration problem (that's you), while 500s indicate that something bad is happening on the server (that's us).

The codes are presented in the header of the response; some error responses will also contain a body with the message specified below:

Code | Meaning | Message
---- | ------- | -------
200 | Success
400 | Bad Request |
401 | Unauthorized | Bad credentials
404 | Not Found |
422 | Unprocessable Entity |
429 | Too Many Requests |
500 | Internal Server Error |
503 | Service Unavailable |
