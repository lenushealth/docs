# Registering a Client

Client registration and management is done through the [DeveloperPortal](environment.md).

Two pages allow you to provide Lenus with information that you will use to authorize your Client connecting to Lenus.

1. The Client Details page, allowing you to set [Client Id](#clientid), callback URLs, [grant types](#granttypes-openidconnectflow), and [scopes](#scopes).
1. The Client Secret page, allowing you to set the [secret](#secret).

Once you have completed this process you will have a unique Client Id and client secret, which you will need when you work through the Authorization set-up of your Client.

## Client Id

Your Client Id is a string of characters that uniquely identifies the Client within Lenus.

A Client Id is made of a fixed prefix, a '.' character, and a suffix you supply. 

The fixed prefix is unique to you and cannot be customized.

The suffix must be unique within your set of clients, and can only contain characters from `0987654321abcdefghijklmnopqrstuvwxyz`

Example:

```
a3c10260b6abf49c60bee6967b9bc076e9386237e6207a757cfe826f4e2015c8.superpedometer

|<---------------------------fixed prefix--------------------->| |<--customizable suffix-->|
```


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


## Secret

The secret is a string of characters that is used by the OpenID Connect process to authenticate a Client. It can be thought of as a password for the Client. It should be stored securely.






