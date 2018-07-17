# FHIR API

The FHIR API allows authorized Clients to read and write Resources based on the [HL7 FHIR 3 (STU) Standard](https://www.hl7.org/fhir/)

Resources that are currently supported are:

* [Patient](./resources/patient.md)
* [Care Plan](./resources/careplan.md)
* [Observation](./resources/observation.md)
* [Media](./resources/media.md)
* [RiskAssessment](./resources/riskassessment.md)

The calling Client must [pass an access token](../authorization.md#access-token) representing the user that the Client is acting on behalf of.  

To read resources for a user other than the caller, the Client must [act as an agent](../agency/index.md).

## Scopes

To read or write resources the appropriate scopes must be authorized for the client.  Scopes follow the format:

```
operation.resourceType
```

For example

```
read.patient
write.careplan
```

## Resource Operations

Each resource supports a number of operations, such as create, read, update.  The individual resource pages give more detail, but in general, the capabilities are the same for each one.

Full details of supported operations are available from the metadata endpoint

```
GET /metadata
```
The server will accept and return JSON or XML, depending on the Accepts and Content-Type headers sent with the request.  This should be one of:

```
application/fhir+json
application/fhir+xml
```

### Supported Operations
```
POST /{resourceType}
```
The server will create a new resource from the body of the request, and assign a new id.  If you send a resource id it will be overwritten.  The server will return an OperationOutcome resource with the new id.  The full resource uri will be returned in the ETag header.

```
GET /{resourceType}/{id}
```
The server will return the resource with the corresponding id.  It will always return the latest version of the resource.  If a resource existed, but has been deleted, this will return a 410 Gone Http status code.

```
PUT /{resourceType}/{id}
```
The server will create a new version of the existing resource based on the body of the request.

```
DELETE /{resourceType}/{id}
```
The server will delete the latest version of the resource.  The version history still remains.

## Search

Search is available through two endpoints

```
GET /{resourceType}?searchParameter=value
```
```
POST /{resourceType}/_search
```
For the POST method, the search parameters are encoded in the request body.

Each resource has different supported search parameters.  See individual resource documentation for more detail on which parameters are supported.

Supported search parameter types are:

* [String](searchparameters.md#search)
* [Reference](searchparameters.md#reference)

Searches return a resource type of [Bundle](https://www.hl7.org/fhir/bundle.html)
