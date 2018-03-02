# Obtain AgencyQueryToken

An `AgencyQueryToken` is used when reading `Samples` from the DataServer to:

1. Identify the users the Agent is acting on behalf of.
1. Prove consent exists.

Definition

```
POST IDENTITYSERVER/api/agency/querytoken
```

* `IDENTITYSERVER` is the base URL for the [IdentityServer](../../../environment.md)

## Request

A specification of subjects to be included in a query by a Client acting on behalf of an Agent.

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| IncludeAll | bool, optional | A flag indicating whether all subjects over which the caller has Agency are included, defaults to `false` |
| SpecificallyIncludedPseudoSubs | array, optional | An array of string, each one a subject to be included, defaults to empty |
| SpecificallyExcludedPseudoSubs | array, optional | An array of string, each one a subject to be excluded, defaults to empty |

 The set of subjects is resolved by 

 - starting with all subjects, or an empty set, depending on the value of `IncludeAll`, then
 - adding any subjects from the `SpecificallyIncludedPseudoSubs` set, then
 - subtracting any subjects from the `SpecificallyExcludedPseudoSubs` set

## Response

A token that can be used by a Client acting on behalf of an Agent querying the DataServer.

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Value | string | The value of the token |

## Example

Request

```json
{
	"SpecificallyIncludedPseudoSubs": [
		"303a88f1-5999-41d7-949b-56130202b034",
		"c3a1c8b3-7fde-43c9-8c2c-df7122cebb99"
	]
}
```

Response

```json
{
	"Value": "gbhu93q4h9oq3ufhowpejf9qpoirhfiqwlekn"
}
```