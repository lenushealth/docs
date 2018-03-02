# Write Samples

n.b. Writing data cannot be done by an Agent, it must be done by the owner of the Samples.

```
POST DATASERVER/api/sample
```

* `DATASERVER` is the base URL for the [DataServer](../../../environment.md)

## Request 

JSON object attributes:

| Name | Type | Description |
|-|-|-|
| Samples | array | Array of [`SampleData`](../core_resources.md#sampledata) |

