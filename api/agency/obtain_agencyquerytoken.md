# Obtain AgencyQueryToken

Definition

```
POST /api/agency/querytoken
```

## Request

A specification of subjects to be included in a query by a Client acting on behalf of an Agent.

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| IncludeAll | bool | A flag indicating whether all subjects over which the caller has Agency are included |
| SpecificallyIncludedPseudoSubs | array | An array of string, each one a subject to be included |
| SpecificallyExcludedPseudoSubs | array | An array of string, each one a subject to be excluded |

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