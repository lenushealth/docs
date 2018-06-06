# Media Resource

## Supported Operations

The Media resource supports the following:

```
POST /Media
GET /Media?searchparameter=value
GET /Media/{id}
PUT /Media/{id}
DELETE /Media/
POST /Media/_search
```


## Supported Search Parameters

|parameter|type|notes|
|---------|----|-----|
|patient|[reference](../searchparameters.md#reference)|This will search the _subject_ field of the Media.  The reference can be relative (/Patient/123) or absolute (http://fhir.api/Patient/123)|
