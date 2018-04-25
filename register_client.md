# Registering a Client

Client registration and management is done through the [DeveloperPortal](environment.md).

To register a Client you will provide:

* A [Client Id](#clientid) – characters used to uniquely identify your Client
* A [Redirect URI](#redirecturi) – a URL that the IdentityServer can call when completing authorization 
* A [Grant type](#granttypes-openidconnectflow) – the type of OpenId Connect flow used
* [Scopes](#scopes) – The permissions your Client can ask a user for
* A [Secret](#secret) – A "password" for your Client

You will use this information when authorizing your Client via OpenID Connect.

You set this information via the Client details page, and the Client secret page.

## Client Id

Your Client Id is a string of characters that uniquely identifies the Client within Lenus. Example:

```
a3c10260b6abf49c60bee6967b9bc076e9386237e6207a757cfe826f4e2015c8.superpedometer

|<---------------------------fixed prefix--------------------->| |<--customizable suffix-->|
```


A Client Id is made of a fixed prefix, a '.' character, and a suffix you supply. 

The fixed prefix is unique to you and cannot be customized.

The suffix must be unique within your set of clients, and can only contain characters from `0987654321abcdefghijklmnopqrstuvwxyz`



## Redirect URI

The IdentityServer will call this URI with authentication responses during the OpenID Connect flow. It is up to the Client what form this URI takes. 

## Grant Types - OpenID Connect Flow

Lenus uses OpenID Connect for authentication and authorization. You must decide what authentication flow is appropriate for your client.

| Flow Name            | Typical Use Case |
|----------------------|-------------|
| `authorization_code` | A server based application that can maintain a secret |
| `implicit`           | A client side application that cannot be trusted with a secret, and does not need refresh tokens |
| `hybrid`             | As `authorization_code` |


Refer to the [OpenID Connect documentation](https://openid.net/connect/) for full details.


## Scopes

Scopes control a Client's ability to:

* Access user information stored on the IdentityServer
* Use the [Agency API](api/agency/index.md)
* Read and write [Samples](api/dataserver/index.md) on the DataServer
* Read and write [Resources](api/fhir/index.md) through the FHIR API


## Secret

The secret is a string of characters that is used by the OpenID Connect process to authenticate a Client. It can be thought of as a password for the Client. It should be stored securely.






