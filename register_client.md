# Registering a Client

Client registration and management is done through the [DeveloperPortal](TODO). Navigate to the Client registration screen, and fill in the form.

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
* Use the [Agency API](TODO)
* Read and write [Samples](TODO) on the DataServer






