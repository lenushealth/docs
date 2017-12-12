# Request Agency Claims (API)

In order for a health professional to interact with the health data for patients they have agency over they need to make requests to the Lenus Identity service to retrieve a set of claims for those patients.  This endpoint will return a JSON body:

```json
{
    "claims" : [
        {
            "claims" : [
                { "type" : "email", "value" : "user@example.com" },
                { "type" : "sub", "value" : "user@example.com" },
                { "type" : "email", "value" : "user@example.com" }
            ]
        }
    ]
}
```

![](img/request-agency-claims--overview.png)