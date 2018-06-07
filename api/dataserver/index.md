# DataServer API

The API allows authorized Clients to read and write Sample data to the platform.

To use the API, the calling Client must [pass an access token](../authorization.md#access-token) representing the user the Client is acting on behalf of. 

To read data for users other than the caller, the Client must also [act as an Agent](../agency/index.md).

Tasks:

* [Write Samples](tasks/write_samples.md)
* [Read Samples](tasks/read_samples.md)

