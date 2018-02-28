# DataServer API

The DataServer API allows authorized Clients to read and write Sample data to the DataServer.

To use the DataServer API, the calling Client must [pass an access token](../getting_started/authorization.md) representing the user the Client is acting on behalf of.  To read data for users other than the caller, the Client must also [act as an Agent](../getting_started/acting_as_agent.md).

## Write Data

```
POST /api/sample
```

### Request 

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Samples | array | Array of [`SampleData`](core_resources.md#sampledata) |

Writing data cannot be done by an Agent, it must be done by the owner of the Samples.

## Perform a Query

```
POST /api/query
```

### Request 

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Types | array | An array string, each the [`TypeIdentifier`](sample_type_scope.md#typeidentifier) of a Sample to query |
| RangeOfStartDate | [`DateRange`](core_resources.md#daterange-object) | A range of dates which matching Sample-start-dates must match |
| RangeOfEndDate | [`DateRange`](core_resources.md#daterange-object), optional| A range of dates which matching Sample-end-dates must match |
| OrderProperty | string, optional| The order of query results, either `StartDate` or `EndDate`. If omitted, defaults to `StartDate`. |
| OrderDirection | string, optional| The order direction of query results, either `Ascending` or `Descending`. If omitted, defaults to `Ascending`. |

### Response

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| NumberOfResults | int | The number of results |
| ExpirationDate | string, ISO 8601 | The time at which query results expire |
| Key | string | A key to use to access query results |


## Access Query Results

```
GET /api/query
```

### Request

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Key | string | The key to use to access results, from [previous](#perform-a-query) |
| Skip | int, optional | The number of results to skip-over |
| Take | int, optional | The maximum number of results to return |

### Response

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Samples | array | Array of [`SampleData`](core_resources.md#sampledata) |