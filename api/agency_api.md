# Agency API

To use the Agency API, the calling Client must [pass an access token](../getting_started/authorization.md) representing a user with the role "Agent".

## Resolve Claims

Definition

```
GET /api/agency/claims
```

This endpoint takes no arguments.

Returns a [`AgencyClaimsResolution`](core_resources.md#agencyclaimsresolution) object representing the claims of the users over which the calling Agent has Agency.


## Obtain AgencyQueryToken

Definition

```
POST /api/agency/querytoken
```

The body of the request should contain a JSON encoded [`AgencyQueryTokenRequest`](core_resources.md#agencyquerytokenrequest).

Returns an [`AgencyQueryToken`](core_resources.md#agencyquerytoken).