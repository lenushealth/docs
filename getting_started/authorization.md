# Authorization

## Access Token

An access token represents a Client's permission to act on behalf of a user. To aquire an access token, a Client must use the standard OpenID Connect mechanism built into IdentityServer to authenticate the user.

A Client will need:

* Functionality to complete the OpenID Connect flow - likely this is provided by a third-party library appropriate for the platform that the Client runs on.
* Client details: Client Id, Grant Type, Scopes, any Secret set

The IdentityServer supports endpoint discovery via a discovery document at `https://ENVIRONMENT/.well-known/openid-configuration`, where `ENVIRONMENT` is the appropriate [environment](TODO) for your subscription.

The grant types supported by Lenus (`authentication_code`, `implicit`, `hybrid`) mean that user authentication always takes place in a web browser. The user will be presented with an opertunity to provide credentials, then accept scopes requested by the Client. If the user completes this, an access token will be vended to the Client.

### Using an Access Token

With appropriate scope, an access token can be used to:

* Read and write Samples with the [DataServer API](TODO)
* Get user identity information from the IdentityServer's `userinfo` endpoint
* Perform [Agent](TODO) tasks with the IdentityServer's [Agency API](TODO)

In all three cases, the access token should be embedded into the HTTP request headers of a call to the DataServer using _Bearer Authorization_:

```
Authorization: Bearer <access_token>
```

## Scope

TODO - where does this go

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
