# Become an Agent for a user

Agency is requested by one user, to another, via a Client.

The requesting user should direct thier browser to

```
IDENTITYSERVER/agency/invite?clientid=CLIENTID
```

* `IDENTITYSERVER` is the base URL for the [IdentityServer](../../../environment.md)
* `CLIENTID` is the [Client's Id](../../../register_client.md#client-id)

This facility is web UI, it is not an API call, so no embedding of access token is required.

Typically facility is triggered via a call-to-action (button or link) on the Client.

The requesting user will be presented with a UI that allows them to specify the email-address of the target user, and scopes required.

The target user will then receive an email inviting them to share data with the requesting user. Accepting this invite creates the Agency relationship.