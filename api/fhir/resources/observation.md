# Observation Resource

## Supported Operations

The Observation resource supports the following:

```
POST /Observation
GET /Observation?searchparameter=value
GET /Observation/{id}
PUT /Observation/{id}
DELETE /Observation/
POST /Observation/_search
```


## Supported Search Parameters

|parameter|type|notes|
|---------|----|-----|
|patient|[reference](../searchparameters.md#reference)|This will search the _subject_ field of the Observation.  The reference can be relative (/Patient/123) or absolute (http://fhir.api/Patient/123)|
