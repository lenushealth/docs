# Agency API

Agency is a relationship that describes scope granted by one user to another for use within the context of a specific Client.

e.g. One Agency relationship might describe the fact that a doctor has been granted access to a patient's blood pressure readings via a website Client.

In order for one user (A) to act as an Agent for another (B):

1. (A) must have the role `Agent` TODO - undecided how htis happens
1. (A) must have requested Agency over (B)
1. (B) must have accepted (A)'s request



## Tasks

* [Become an Agent](become_an_agent.md) of a user
* [Resolve Claims](resolve_claims.md) of the users over which the calling Agent has Agency. Useful for:
    * Determining user identity info, e.g. name, email-address
    * Determining which scopes are granted
* [Obtain AgencyQueryToken](obtain_agencyquerytoken.md) to use with a query to the DataServer API

To use the Agency API, the calling Client must [pass an access token](../getting_started/authorization.md) representing a user with the role "Agent".
