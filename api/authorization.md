# Authorization

## Access Token

An access token represents a Client's permission to act on behalf of a user. To acquire an access token, a Client must use an OpenID Connect flow with information provided at [Client Registration](../register_client.md)

A Client will need:

* Functionality to complete the OpenID Connect flow - likely this is provided by a third-party library appropriate for the platform that the Client runs on.
* Client details: Client Id, Grant Type, Scopes, any Secret set

The IdentityServer supports endpoint discovery via a discovery document at 

```
GET IDENTITYSERVER/.well-known/openid-configuration
```

* `IDENTITYSERVER` is the base URL for the [IdentityServer](../../../environment.md)

The grant types supported by Lenus (`authentication_code`, `implicit`, `hybrid`) mean that user authentication always takes place in a web browser. The user will be presented with an opportunity to provide credentials, then accept scopes requested by the Client. If the user completes this, an access token will be vended to the Client.

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

## DataServer Scope

Each type of data has corresponding scopes. The access token passed to a DataServer API call must include appropriate scope for the data requested.

See the [documentation on Samples](dataserver/samples/index.md) for full details.

A Client may act with scope for a User in calls to the DataServer by either:

- using scopes represented in the access token, or
- [acting as an Agent](../acting_as_agent.md), using scopes granted by the user to the Agent

## DataServer API Version Request Header

As well as an access token, each request to the DataServer must have an HTTP request header indicating the version of API used. Only version 2.0 is currently supported, so you must supply the exact header:

```
api-version: 2.0
```

