# Reading Samples

Samples may be read by a Client acting on behalf of:

1. the owner of Samples, or
1. an Agent of the owners of Samples.

The procedure for reading Samples the owner or an Agent differs only by the inclusion of an AgencyQueryToken.

Reading Samples is a two-staged process:

1. Perform a query, receiving metadata regarding the query results.
1. Read query results.

## Performing a Query

Make a POST request to the DataServer on `/api/query` with a JSON Query object in the body, e.g.:

```json
{
	"Types": [
		"StepCount"
	],
	"RangeOfStartDate": {
		"LowerBound": "2018-01-22T00:00:00+00:00",
		"UpperBound": "2018-01-23T00:00:00+00:00"
	}
}
```


Receive back a metadata object, e.g.:

```
{
	"NumberOfResults": 2,
	"ExpirationDate": "2018-02-22T11:39:31+00:00",
	"Key": "hqf9ipruwhgqf98ewy9qw8e9t78yfrtd54"
}
```


## Reading Query Results

Using the metadata from the previous step, make a GET request to the DataServer on `/api/query` with query string parameters:

* `key`, the key from metadata
* `skip` (optional), the number of results to skip over
* `take` (optional), the maximum number of results to return

e.g.: `/api/query?key=hqf9ipruwhgqf98ewy9qw8e9t78yfrtd54`

Receive back an object with an array of Samples, e.g.:

```
{
	"Samples": [
		{
			"Subject": "cf085994-5f73-4adc-8b51-2e92bb76e4ce",
			"Type": "StepCount",
			"QuantityValue": 212,
			"DateRange": {
				"LowerBound": "2018-01-22T07:31:00+00:00",
				"UpperBound": "2018-01-22T09:53:00+00:00"
			}
		},
		{
			"Subject": "cf085994-5f73-4adc-8b51-2e92bb76e4ce",
			"Type": "StepCount",
			"QuantityValue": 7820,
			"DateRange": {
				"LowerBound": "2018-01-22T10:05:00+00:00",
				"UpperBound": "2018-01-22T22:05:00+00:00"
			}
		}
	]
}
```

