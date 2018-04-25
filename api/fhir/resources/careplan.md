# Care Plan Resource

## Supported Operations

The CarePlan resource supports the following:

```
POST /CarePlan
GET /CarePlan?searchparameter=value
GET /CarePlan/{id}
PUT /CarePlan/{id}
DELETE /CarePlan/
POST /CarePlan/_search
```


## Supported Search Parameters

|parameter|type|notes|
|---------|----|-----|
|patient|[reference](../searchparameters.md#reference)|This will search the _subject_ field of the CarePlan.  The reference can be relative (/Patient/123) or absolute (http://fhir.api/Patient/123)|
