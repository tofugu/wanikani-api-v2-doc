## Rate Limit

WaniKani API has the following rate limits active:

Throttle | Value
-------- | -----
Requests per minute | 45
Requests per second | 10

HTTP status code `429` (Forbidden) and body with the message `Rate Limit Exceeded` is returned if the limits are exceeded.
