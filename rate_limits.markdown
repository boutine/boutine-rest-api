# Rate limits

The default rate limit for calls to the REST API are measured against the consumer key (client application identifier).

One client application can make 200 requests to the REST APIs of Boutine in 1 hour.

Whenever an API is accessed the response header contains X-RateLimit-Limit and X-RateLimit-Remaining information:

HTTP/1.1 200 OK
X-RateLimit-Limit: 200
X-RateLimit-Remaining: 199


If you exceed the 200 API calls in 1 hour then you get the following response:

HTTP/1.1 403 Forbidden
X-RateLimit-Limit: 200
X-RateLimit-Remaining: 0

