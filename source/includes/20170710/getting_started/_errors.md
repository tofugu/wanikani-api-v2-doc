## Errors

> Errors with a message will return with the follow response body structure:

```
{ "error": <string>, "code": <integer> }
```

We use standard HTTP response codes to indicate the status of the response. Codes in the 200s indicate success, 400s usually indicate a client configuration problem (that's you), while 500s indicate that something bad is happening on the server (that's us).

The codes are presented in the header of the response; some error responses will also contain a body with the message specified below:

Code | Meaning | Message
---- | ------- | -------
200 | Success | n/a
401 | Unauthorized | “Unauthorized. Nice try.”
404 | Not Found |
422 | Unprocessable Entity | Description of how the request was malformed.
429 | Too Many Requests |
500 | Internal Server Error | n/a
503 | Service Unavailable | n/a
