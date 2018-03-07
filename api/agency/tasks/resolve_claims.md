# Resolve Claims

Use this endpoint to determine all claims for each Agency (the relationship of Agent-user/target-user/Client), including identifying claims (e.g. name), and DataServer scope (e.g. `read_step_count`).

Definition

```
GET IDENTITYSERVER/api/agency/claims
```

* `IDENTITYSERVER` is the base URL for the [IdentityServer](../../../environment.md)

This endpoint takes no arguments.

## Response

An array (one item per user) of array (one item per claim) of `Claim` objects (see below) representing the claims of the users over which the calling Agent has Agency.

#### Claim

A user claim. Attributes:

| Name | Type | Description |
|-|-|-|
| Type | string | The type of the claim, e.g. `name` |
| Value | string | The value of the claim, e.g. `Joe Smith` |

### Example Response

```json
{
    "Claims": [
        {
            "Claims": [
                {
                    "Type": "scope",
                    "Value": "read_body_mass_index"
                },
                {
                    "Type": "name",
                    "Value": "Finlay Mackay"
                },
                {
                    "Type": "given_name",
                    "Value": "Finlay"
                },
                {
                    "Type": "family_name",
                    "Value": "Mackay"
                },
                {
                    "Type": "birthdate",
                    "Value": "2012-02-07"
                },
                {
                    "Type": "email",
                    "Value": "Finlay.Mackay@example.com"
                },
                {
                    "Type": "pseudo_sub",
                    "Value": "303a88f1-5999-41d7-949b-56130202b034"
                }
            ]
        },
        {
            "Claims": [
                {
                    "Type": "scope",
                    "Value": "email"
                },
                ...
            ]
        },
        ...
    ]
}

```

