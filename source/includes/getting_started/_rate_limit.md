## Rate Limit

The WaniKani API has the following rate limits active:

Throttle | Value
-------- | -----
Requests per minute | 45
Requests per second | 10

An HTTP status code of `429` (Forbidden) and a body with the message `Rate Limit Exceeded` is returned if the limits are exceeded (shocking, we know).
