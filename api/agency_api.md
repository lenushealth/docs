# Agency API

To use the Agency API, the calling Client must [pass an access token](../getting_started/authorization.md) representing a user with the role "Agent".

## Resolve Claims

Definition

```
GET /api/agency/claims
```

This endpoint takes no arguments.

Returns a [`AgencyClaimsResolution`](core_resources.md#agency-claims-resolution) object of the claims of the users overwhich the calling Agent has Agency.