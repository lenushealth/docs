# Read Samples

Samples may be read by a Client acting on behalf of:

1. the owner of Samples, or
1. an Agent of the owners of Samples.

The procedure for reading Samples the owner or an Agent differs only by the inclusion of an AgencyQueryToken.

## Perform a Query

```
GET DATASERVER/api/sample
```

* `DATASERVER` is the base URL for the [DataServer](../../../environment.md)

### Request 

Query string parameters:

| Name | Type | Description |
|-|-|-|
| Types | array | An array string, each the [`TypeIdentifier`](../sample_type_scope.md#typeidentifier) of a Sample to query |
| StartDate.LowerBound | ISO 8601 date-time | Match Sample-start-dates after this date-time |
| StartDate.UpperBound | ISO 8601 date-time | Match Sample-start-dates before, or on, this date-time |
| EndDate.LowerBound | ISO 8601 date-time, optional | Match Sample-end-dates after this date-time |
| EndDate.UpperBound | ISO 8601 date-time, optional | Match Sample-end-dates before, or on, this date-time |
| CreationDate.LowerBound | ISO 8601 date-time, optional | Match Sample-creation-dates after this date-time |
| CreationDate.UpperBound | ISO 8601 date-time, optional | Match Sample-creation-dates before, or on, this date-time |
| OrderProperty | string, optional| The order of query results, either `StartDate` or `EndDate`. Defaults to `StartDate`. |
| OrderDirection | string, optional| The order direction of query results, either `Ascending` or `Descending`. Defaults to `Ascending`. |
| Skip | int, optional | The number of results to skip-over. Defaults to 0. |
| Take | int, optional | The maximum number of results to return. Defaults to 100, clipped to 1000.  |

#### As an Agent

The query may be performed as an Agent by including an [AgencyQueryToken](../../agency/tasks/obtain_agencyquerytoken.md) in the request header.

```
agency-query-token: <token-value>
```


An AgencyQueryToken can only be used once.

An AgencyQueryToken must be used within 30 seconds of issue.

### Response

JSON: An object containg an array of [`SampleData`](../core_resources.md#sampledata) and counts.

#### Attributes

| Name       | Type   | Description |
|------------|--------|-------------|
| Datas | Array of [`SampleData`](../core_resources.md#sampledata) | The sample data |
| Count | int | The number of samples in this result  |
| TotalAvailable | int | The total unpaged number of samples available |
