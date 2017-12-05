## Rate Limiter

WaniKani API has the following rate limits active:

* 60 requests per minute
* 10 requests per second

HTTP status code `403` (Forbidden) and body with message "Rate Limit Exceeded" is returned if the limits are exceeded.
