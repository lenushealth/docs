# Become an Agent for a user

Agency is requested by one user, to another, via a Client.

This is done via an API call, or older clients may still use a legacy in-browser UI.

## Via API

Definition

```
POST IDENTITYSERVER/api/agency/createagencyinvite
```

* `IDENTITYSERVER` is the base URL for the [IdentityServer](../../../environment.md)

## Request

A specification of the Agency requested, and how acceptance should be signaled back to the client.

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Email | string | The email-address of the user that is being invited to grant Agency |
| RequestedScopes | array of string | The names of scopes included in the invite |
| OrganizationId | string, optional | The id of an Organization, if the requesting user is acting as a memeber of an Organization |
| ClientNotifyPath | string, optional  | A path of an API endpoint on the client, called when a user accepts the invite. Query string parameters included are `subject` (the subject of the accepting user) and `state` (the value ClientNotifyState) |
| ClientNotifyState | string, optional  | Passed to the API endpoint defined by ClientNotifyPath |
| BrowserRedirectPath | string, optional  | A path on the client. A user who accepts an invite is redirected here. Included in the query string is `state` (the value BrowserRedirectState)  |
| BrowserRedirectState | string, optional  | Passed to the URL defined by BrowserRedirectPath |

## Response

Status code OK, or otherwise.

## Example

Request

```json
{
    "Email":"alice@example.com",
    "RequestedScopes":
    [
        "read.sleep_analysis",
        "read.blood_pressure.blood_pressure_systolic",
        "read.blood_pressure.blood_pressure_diastolic"
    ],
    "ClientNotifyPath":"/InviteResolution",
    "ClientNotifyState":"iuhve89srgh97wery89hcw978e4g3",
    "BrowserRedirectPath":"/Public",
    "BrowserRedirectState":"cb788woiqef93qr8cqh983"
}
```

## Legacy In-Browser Method

The requesting user should direct their browser to

```
IDENTITYSERVER/agency/invite?clientid=CLIENTID
```

* `IDENTITYSERVER` is the base URL for the [IdentityServer](../../../environment.md)
* `CLIENTID` is the [Client's Id](../../../register_client.md#client-id)

This facility is web UI, it is not an API call, so no embedding of access token is required.

Typically this would be a call to action within the client (application).

Typically facility is triggered via a call-to-action (button or link) on the Client.

The requesting user will be presented with a UI that allows them to specify the email-address of the target user, and scopes required.

The target user will then receive an email inviting them to share data with the requesting user. Accepting this invite creates the Agency relationship.