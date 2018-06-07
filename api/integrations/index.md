# Integrations API

Integrations can be established between a Health platform account and any configured 3rd party service.  This connection can be established and revoked by an individual and allows the Health platform to conenct into the 3rd party service using an account specified my an individual.  Integrations utilise OAuth2 protocols to securely allow connectivity and allows the Health platform to interactive with specific scopes and data as consented by the owner of the 3rd party service account.

## Using Integrations as an application developer

As an application developer you can utilise these connections to perform specific integration actions on behalf of a logged in Health platform user and a 3rd party service within your client application, however the Health platform will acts as a gatekepper between your application and the 3rd party to protect the flow and quality of information passing between you, the health platform and a 3rd party.

In order to make use of any integrations provided by the health platform your client application _must_ be verified and trusted by the health platform.  This is currently a manual step and will require you to contact our team for further details on the verification process.

Once a trust is established between your client application and the specific integration you are able to access a set of common integration APIs that allow you to interogate the status of an integration for a specific user.

## Integrations API

### Return all integration statuses for a user

This endpoint will return an array of objects containing the state of each integration your application is trusted to use, with a property indicating whether the user has `connected` the integration and a `connectUri` that can be used to request the user establish the connection.

```
GET API/integrations/v1/
```

* `API` is the base URL for the [API](../../../environment.md)

## Response

An array of json objects representing each integration your client is trusted to use, along with some status information

```json
[
    {
        "name": "Integration #1",
        "connected": true,
        "connectUri": "https://identity.dhi-dse.scot/integrations/oauth2/integration-1/connect"
    },
    {
        "name": "Integration #2",
        "connected": false,
        "connectUri": "https://identity.dhi-dse.scot/integrations/oauth2/integration-2/connect"
    }
]
```

### Return a specific integration status for a user

This endpoint will return a single object containing the state of the integration, with a property indicating whether the user has `connected` the integration and a `connectUri` that can be used to request the user establish the connection.

```
GET API/integrations/v1/<integration-id>
```

* `API` is the base URL for the [API](../../../environment.md)

## Response

An array of json objects representing each integration your client is trusted to use, along with some status information

```json
{
    "name": "Integration #1",
    "connected": true,
    "connectUri": "https://identity.dhi-dse.scot/integrations/oauth2/integration-1/connect"
}
```

## Using the `connectUri` to initiate a request to establish an integration connection

The `connectUri` is returned from a call to the integrations status api endpoint and returning a uri that can be used by the client application should the integration not be established, redirecting will begin the connection process, forwarding the user to the login/consent pages for the 3rd party service.  Once the connection is establioshed the user will be returned to the health platform integrations summary page by default.  The `connectUri` supports additional query parameters that can be used to redirect back into your application when the integration connection is completed (whether successful or not):

`client_id` - your client_id value to the `connectUri` and on completion we will redirect the browser back to the configured _Uri_ field within your client application setup within the [Developer Portal](../../../environment.md).
`ReturnPath` - a path string (beginning with /), this will be appended onto the _Uri_ found within your client application configuration, i.e. `myapplication://goto_page`

i.e. `https://identity.dhi-dse.scot/integrations/oauth2/integration-1/connect?client_id=kjhsdf9876sdfkjhsdlkjhsdf9807sdf.myapplication&returnPath=/goto_page`

If the integration connection is not successfully established then an `error` query parameter will be appended to the redirected uri, i.e. `myapplication://goto_page?error=access_denied`.  This can be parsed to determine your next move.