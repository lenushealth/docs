# Become an Agent for a user

Agency is requested by one user, to another, via a Client.

The requesting user should visit

```
https://<IdentityServer>/agency/invite?clientid=<ClientId>
```

Typically this is done via a call-to-action (button or link) on the Client.

The requesting user will be presented with a UI that allows them to specify the email-address of the target user, and scopes required.

The target user will then receive an email inviting them to share data with the requesting user. Accepting this invite creates the Agency relationship.