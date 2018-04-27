# Patient Resource

## Supported Operations

The patient resource supports the following:

```
GET /Patient?searchparameter=value
GET /Patient/{id}
PUT /Patient/{id}
DELETE /Patient/
POST /Patient/_search
```

It does **not** support creation of new patient resources through POST.  A patient must already be registered on Lenus, in which case they will have an empty Patient resource.  To update this resource, use the PUT operation.

## Supported Search Parameters

|parameter|type|notes|
|---------|----|-----|
|identifier|[string](../searchparameters.md#string)|This is different to the id, and is an identifier on another system that could be used to link the FHIR resource to the external system|
