# Search Parameter Types

## String

String searches take the format

```
/{resourceType}?parameter=[value]
```
The search will match to the field with a case- and accent-insensitive search.

Note that the FHIR modifiers are **not** currently supported:

```
/{resourceType}?parameter:contains=value
/{resourceType}?parameter:exact=value
```

## Reference

Reference searches take the format

```
/{resourceType}?parameter=[id]
/{resourceType}?parameter=[resourceType]/[id]
/{resourceType}?parameter=[uri]
```

For a [id] search, the api will only search the current resource type using a local reference.

For a [type]/[id] search, the api will search for a local reference to any resource type.

For a [uri] search, the api will search for any match for the uri in the parameter field.

Note that local references can be used interchangeably with full uri for the FHIR api.  For example, for the FHIR api base url of https://fhir.api/ then the following patient searches are considered to be equivalent:

```
/{resourceType}?patient=Patient/123
/{resourceType}?patient=https://fhir.api/Patient/123
```
