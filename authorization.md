# Authorization

## Access Token

A user's identity is authenticated using the standard OpenID Connect mechanism built into IdentityServer. Authenticating produces an access token for the Client.

The access token represents the Client's permission to act on behalf of the user. The access token must be sent with any call to the DataServer to prove authorization.

An access token should be embedded into the HTTP request headers of a call to the DataServer as _Bearer Authorization_

```
Authorization: Bearer <access_token>
```

## Scope

Authorzation is based on OpenID scopes.

Each type of Sample has two corresponding scopes – one representing read-access, the other write-access.

A complete [set of scopes supported by the platform](TODO).

A Client may read or write a particular type of Sample on behalf of a user, when that user has granted the Client the corresponding scope. For example, a weight management smartphone app may have been granted the scopes [`read_body_mass`](TODO) and [`write_body_mass`](TODO).

## Using Scope

A Client may act with scope for a User in calls to the DataServer by either:

- using scopes represented in the access token, or
- acting as an Agent, using scopes granted by the user to the Agent

### Acting as an Agent

If a user has granted another [permission to act as an Agent](TODO) within the context of a Client, then that Client may make calls to the DataServer with authentication for the Agent, but accessing the user's data.

A normal call to the DataServer is distinguished from a call where an Agent is acting on another user's behalf by the incusion of an _AgencyQueryToken_ in the request header.

Example:

- Alice has granted Bob [permission to act as an Agent](TODO), with scope `read_heart_rate` within a website that is a Client of the Lenus platform
- Bob uses the website
- The website needs to display Alice's heart rate, so it makes a call to the DataServer, including an appropriate AgencyQueryToken.
- The DataServer resolves the scopes represented in the AgencyQueryToken, and performs the query

#### AgencyQueryToken

When acting as an Agent, each call to the DataServer must be accompanied by an AgencyQueryToken as the value of the `agency-query-token` header.

```
agency-query-token: <token-value>
```

Once used, an AgencyQueryToken cannot be reused.

AgencyQueryTokens expire after 30 seconds.

To obtain an AgencyQueryToken, a Client makes an API call to the IdentityServer.

```
TODO technical description of call in standard format
```
