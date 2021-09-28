## Rate Limit

We enforce the following rate limits to ensure decent response times for everyone using the API:

Throttle | Value
-------- | -----
Requests per minute | 60

An HTTP status code of `429` (Forbidden) and a body with the message `Rate Limit Exceeded` is returned if the limits are exceeded (shocking, we know).

In the response headers, the following rate limit information is provided:

Header | Description
------ | -----------
RateLimit-Limit | The rate limit for the current period.
RateLimit-Remaining | The remaining rate available for the current period.
RateLimit-Reset | The timestamp of when the rate limit will reset. The value is epoch time in seconds.

It is recommended to make use of the header rate limit details to programatically handle HTTP status code `429` responses in an optimal way.
