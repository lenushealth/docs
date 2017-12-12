# Lenus Health API

The Lenus Health API allows an application to interface with a "health data store" in a secure manner, supporting the ability to interact with the health data store on behalf of a user, submitting and querying health related data.

This documentation is not designed to be a comprehensive introduction to the Lenus health platform and instead will focus on providing technical documentation to other developers wishing to interface with the platform.

The documentation will provide:

- Details of the authentication and authorisation model used by the platform
- Technical documentation on the available endpoints with sample usage scenarios
- A list of health data types supported by the platform with samples of their usage

## API Authentication and Authorisation
To use the Lenus Health APIs you must have 2 things:

- A valid bearer access token retrieved via the Lenus Identity OpenIdConnect authorisation server
- A valid subscription key, this is created when signing up to the service

### How to retrieve a bearer access token
An access token is retrieved by communicating with the Lenus authorisation server using standard OpenIdConnect (oidc) protocols, ideally you would use an authentication library to do it.  For this authentication you will need:

- A `client_id` configured with the required scopes to access (read/write) specific health data (such as blood pressure or heartrate)
- A `client_secret`
- Details of the Lenus authorisation server endpoint

When configured your web application or mobile application will redirect to the Lenus Identity service and request that the user logs in with their account, from here you will be able to access the Lenus platform on their behalf to submit and/or query data.
