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
- acting as an Agent

