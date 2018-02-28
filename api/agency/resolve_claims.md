# Resolve Claims

Definition

```
GET /api/agency/claims
```

This endpoint takes no arguments.

## Response

An object representing the claims of the users over which the calling Agent has Agency.

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Claims | array | An array of `AgencyClaims` objects (see below) |

### AgencyClaims

A selection of claims of a single user visible by a specific Agent. Attributes:

| Name | Type | Description |
|-|-|-|
| Claims | array | An array of `Claim` objects (see below) |


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

