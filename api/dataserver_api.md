# DataServer API

To use the DataServer API, the calling Client must [pass an access token](../getting_started/authorization.md) representing the user the Client is acting on behalf of.

To read data for users other than the caller, the Client must [act as an Agent](../getting_started/acting_as_agent.md).

## Write Data

```
POST /api/sample
```

The body of the request should contain a JSON encoded [`SampleDatas`](../core_resources.md#sampledatas) object.

## Perform a Query

```
POST /api/query
```

### Request Body JSON Object Attributes

| Name | Type | Description |
|-|-|-|
| Types | array | An array string, each the [`TypeIdentifier`](sample_type_scope.md#typeidentifier) of a Sample to query |
| RangeOfStartDate | [`DateRange`](core_resources.md#daterange-object) | A range of dates which matching Sample-start-dates must match |
| RangeOfEndDate | [`DateRange`](core_resources.md#daterange-object), optional| A range of dates which matching Sample-end-dates must match |
| OrderProperty | string, optional| The order of query results, either `StartDate` or `EndDate`. If omitted, defaults to `StartDate`. |
| OrderDirection | string, optional| The order direction of query results, either `Ascending` or `Descending`. If omitted, defaults to `Ascending`. |

### Response JSON Object Attributes

| Name | Type | Description |
|-|-|-|
| NumberOfResults | int | The number of results |
| ExpirationDate | string, ISO 8601 | The time at which query results expire |
| Key | string | A key to use to access query results |


## Access Query Results

```
GET /api/query
```

### Request Body JSON Object Attributes

| Name | Type | Description |
|-|-|-|
| Key | string | The key to use to access results, from [previous](#perform-a-query) |
| Skip | int, optional | The number of results to skip-over |
| Take | int, optional | The maximum number of results to return |

### Response JSON Object Attributes

| Name | Type | Description |
|-|-|-|
| Samples | array | Array of [`SampleData`](core_concepts#sampledata) |