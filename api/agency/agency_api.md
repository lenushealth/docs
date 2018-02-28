# Agency API

Tasks:

* [Become an Agent](become_an_agent.md) of a user
* [Resolve Claims](resolve_claims.md) of the users over which the calling Agent has Agency. Useful for:
    * Determining user identity info, e.g. name, email-address
    * Determining which scopes are granted
* [Obtain AgencyQueryToken](obtain_agencyquerytoken.md) to use with a query to the DataServer API

To use the Agency API, the calling Client must [pass an access token](../getting_started/authorization.md) representing a user with the role "Agent".
