# Core Resorces

## SampleData Object

The _SampleData_ object represents a single Sample in the DataServer. SampleDatas are the units that a Client uses to create Samples, and are the unit that are returned from querying the DataServer.


### Attributes

|Name|Type|Description|
|-|-|-|
|Device|string|A [string identifying the type of Device](#Device) used to measure the Sample|
|ClientAssignedId|string|A per-Sample unique-identifier assigned by the Client|
|Subject|string|The subject identifying the creator of the Sample. Only populated on query (not creation)|
|Type|string|The TypeIdentifier* of the Sample|
|DateRange|object|A [DateRange](#DateRange-object) indicating the time a Sample took place|
|QuantityValue|number|The value of the Sample when the Type indicates a QunatityValue, missing otherwise|
|CategoryValue|string|The value of the Sample when the Type indicates a CategorySample, missing otherwise|
|CorrelationObjects|array|An array of child SampleData objects. Only populated when the Type indicates a CorreleationSample|

#### Device Attribute

TODO



## DateRange Object

The _DateRange_ object represents a period or instant in time. If the upper and lower bounds are the same, the time represented is considered instant.

### Attributes

| Name       | Type   | Description |
|------------|--------|-------------|
| LowerBound | string | A date and time in ISO 8601 format indicating the start of the range |
| UpperBound | string | A date and time in ISO 8601 format indicating the end of the range   |
