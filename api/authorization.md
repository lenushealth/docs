# Authorization

## Access Token

An access token represents a Client's permission to act on behalf of a user. To aquire an access token, a Client must use the standard OpenID Connect mechanism built into IdentityServer to authenticate the user.

A Client will need:

* Functionality to complete the OpenID Connect flow - likely this is provided by a third-party library appropriate for the platform that the Client runs on.
* Client details: Client Id, Grant Type, Scopes, any Secret set

The IdentityServer supports endpoint discovery via a discovery document at 

```
/.well-known/openid-configuration
```

The grant types supported by Lenus (`authentication_code`, `implicit`, `hybrid`) mean that user authentication always takes place in a web browser. The user will be presented with an opertunity to provide credentials, then accept scopes requested by the Client. If the user completes this, an access token will be vended to the Client.

See the official [OpenID Connect documentation](http://openid.net/connect/).

### Using an Access Token

With appropriate scope, an access token can be used to:

* Read and write Samples with the [DataServer API](dataserver/index.md)
* Get user identity information from the IdentityServer's OpenID Connect `userinfo` endpoint
* Perform Agent tasks with the IdentityServer's [Agency API](agency/index.md)

In all three cases, the access token should be embedded into the HTTP request headers of a call to the DataServer using _Bearer Authorization_:

```
Authorization: Bearer ACCESSTOKEN
```

Where `ACCESSTOKEN` is the access token.

## Scope

TODO - where does this go?

Authorzation is based on OpenID scopes.

Each type of Sample has two corresponding scopes – one representing read-access, the other write-access.

A complete [set of scopes supported by the platform](TODO).

A Client may read or write a particular type of Sample on behalf of a user, when that user has granted the Client the corresponding scope. For example, a weight management smartphone app may have been granted the scopes [`read_body_mass`](TODO) and [`write_body_mass`](TODO).

## Using Scope

A Client may act with scope for a User in calls to the DataServer by either:

- using scopes represented in the access token, or
- acting as an Agent, using scopes granted by the user to the Agent

### Acting as an Agent



#### AgencyQueryToken


