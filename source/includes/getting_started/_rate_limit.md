## Rate Limit

We enforce the following rate limits to ensure decent response times for everyone using the API:

Throttle | Value
-------- | -----
Requests per minute | 60
Requests per second | 10

An HTTP status code of `429` (Forbidden) and a body with the message `Rate Limit Exceeded` is returned if the limits are exceeded (shocking, we know).
