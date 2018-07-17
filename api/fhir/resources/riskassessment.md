# Risk Assessment Resource

## Supported Operations

The RiskAssessment resource supports the following:

```
POST /RiskAssessment
GET /RiskAssessment?searchparameter=value
GET /RiskAssessment/{id}
PUT /RiskAssessment/{id}
DELETE /RiskAssessment/
POST /RiskAssessment/_search
```


## Supported Search Parameters

|parameter|type|notes|
|---------|----|-----|
|patient|[reference](../searchparameters.md#reference)|This will search the _subject_ field of the RiskAssessment.  The reference can be relative (/Patient/123) or absolute (http://fhir.api/Patient/123)|
|identifier|[string](../searchparameters.md#string)|This is different to the id, and is an identifier on another system that could be used to link the FHIR resource to the external system|
