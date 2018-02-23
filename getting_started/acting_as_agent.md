# Acting as an Agent

An Agent may read users' data, where a user has explicitly granted Agency.

For users over which they have Agency, an Agent can:

1. Read claims from the IdentityServer
1. Read health data from the DataServer

## Becoming an Agent

## Reading Claims

Claims may be retrieved by performing a `GET` request to the IdentityServer's `/api/agency/claims` endpoint, returning a collection of collections of claims.

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

## Reading Health Data

To read health data from the DataServer as an Agent, a Client must first obtain an _AgencyQueryToken_.

To obtain an AgencyQueryToken, a Client makes an `POST` call to the IdentityServer's endpoint `/api/agency/querytoken` with a request:

```json
{
	"SpecificallyIncludedPseudoSubs": [
		"303a88f1-5999-41d7-949b-56130202b034",
		"c3a1c8b3-7fde-43c9-8c2c-df7122cebb99"
	]
}
```

returning:

```json
{
	"Value": "gbhu93q4h9oq3ufhowpejf9qpoirhfiqwlekn"
}
```


Reading Samples from the Data Server as an Agent is [done in the same way]("reading_samples") as a sample owner, with the exception that the AgencyQueryToken value is present in the request header.

```
agency-query-token: <token-value>
```

Once used, an AgencyQueryToken cannot be reused.

AgencyQueryTokens expire after 30 seconds.