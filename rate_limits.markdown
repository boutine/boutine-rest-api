# Rate limits

The default rate limit for calls to the REST API varies depending on the authorization method being used and whether the endpoint being called return public data or not.

1. Public data calls are permitted 100 requests per hour.

2. Non public data calls are permitted 200 requests per hour.

These are measured against the consumer key (client application identifier) being used for the call.
