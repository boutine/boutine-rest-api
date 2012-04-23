# Authroization and Authentication


Request to Boutine API must be authorized using [OAuth](http://oauth.net/) (2.0 recommended). 

For non-public data, like a user's cart and user information required for checkout, 3-legged authentication is used.

The details of the authorization process, or flow, for OAuth 2.0 is the following for 3-legged authentication: 

1. When you create an application, you need to [register](http://www.boutine.com/oauth_clients/) it with Boutine. Boutine
   then provides you with a Consumer key and secret.
2. When your application needs to access Boutine API it asks for a token
   using any standard OAuth client library (depending on the technology/language of your application).

    The urls to be used are as follows:

    - Request token url: `http://www.boutine.com/oauth/request_token`
    - Authorize url: `http://www.boutine.com/oauth/authorize` or
      `http://www.boutine.com/oauth/authenticate`
    - Access token url: `http://www.boutine.com/oauth/access_token`

3. Boutine displays an OAuth page to the user asking them to authorize
   your application to request some of their data
4. If the user approves the Boutine gives your application a short-lived
   access token.
5. Your application requests user data, attaching the access token to
   the request.
6. If Boutine determines that your request and token are valid, it
   returns the requested data.

For public data [2-legged](http://oauth.googlecode.com/svn/spec/ext/consumer_request/1.0/drafts/2/spec.html) authentication is to be used, in which your application using Boutine API is given authorization on behalf of a user. Only cosumer key and secret are used in that case for identification of your application to Boutine and no user sign in is requested in the flow.
