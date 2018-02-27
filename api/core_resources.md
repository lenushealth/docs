# Core Resorces

## SampleData Object

The _SampleData_ object represents a single Sample in the DataServer. SampleDatas are the units that a Client uses to create Samples, and are the unit that are returned from querying the DataServer.

### Examples

#### SampleData for Creating a Height Sample

```
{
    "Device": "man=\"Apple\";mod=\"iPhone\";hwv=\"iPhone9,4\";swv=\"10.3.3\"",
    "ClientAssignedId": "57128634578",
    "Type": "Height",
    "DateRange": {
        "LowerBound": "2018-01-22T10:55:21+00:00",
        "UpperBound": "2018-01-22T10:55:21+00:00",
    },
    "QuantityValue": 1.74
}
```

#### SampleData for Creating a BloodPressure Sample

```
{
    "Device": "btn=\"A&A7236476\";swv=\"1.2\"",
    "ClientAssignedId": "8273647384",
    "Type": "BloodPressure",
    "DateRange": {
        "LowerBound": "2018-01-22T10:55:21+00:000",
        "UpperBound": "2018-01-22T10:55:21+00:000"
    },
    "CorrelationObjects": [
        {
            "Device": "btn=\"A&A7236476\";swv=\"1.2\"",
            "ClientAssignedId": "8273647385",
            "Type": "BloodPressureSystolic",
            "DateRange": {
                "LowerBound": "2018-01-22T10:55:21+00:000",
                "UpperBound": "2018-01-22T10:55:21+00:000"
            },
            "QuantityValue": 15998.7
        },
        {
            "Device": "btn=\"A&A7236476\";swv=\"1.2\"",
            "ClientAssignedId": "8273647386",
            "Type": "BloodPressureDiastolic",
            "DateRange": {
                "LowerBound": "2018-01-22T10:55:21+00:000",
                "UpperBound": "2018-01-22T10:55:21+00:000"
            },
            "QuantityValue": 12000
        }
    ]
}
```

Note the QuantityValues [in Pascals, not Millimeters of Mercury](../Samples.md#non-intuitive-units).

### Attributes

|Name|Type|Description|
|-|-|-|
|Device|string|A [string identifying the type of Device](#device) used to measure the Sample|
|ClientAssignedId|string|A per-Sample unique-identifier assigned by the Client|
|Subject|string|The [subject](#subject) identifying the creator of the Sample. Only populated on query (not creation)|
|Type|string|The [TypeIdentifier](../samples.md#typeidentifier) of the Sample|
|DateRange|object|A [DateRange](#daterange-object) indicating the time a Sample took place|
|QuantityValue|number|The value of the Sample when the Type indicates a QunatityValue, missing otherwise|
|CategoryValue|string|The value of the Sample when the Type indicates a CategorySample, missing otherwise|
|CorrelationObjects|array|An array of child SampleData objects. Only populated when the Type indicates a CorreleationSample|

#### Device

The device string should capture details about the type of device used to measure the Sample. It should not include particular device or user identifiers.

The Lenus convention used is to concatenate name value pairs of device information like so:

```
man="Apple";mod="iPhone";hwv="iPhone9,4";swv="10.3.3"
```

By convention, each name is three characters long, each value is double-quoted. Double-quotes within a value should be escaped thus `\"`.

| Conventional Name | Description |
|-------------------|-------------|
| man               | Manufacturer |
| mod               | Model |
| hwv               | Hardware Version |
| fwv               | Firmware Version |
| swv               | Software Version |
| udi               | UDI device identifier |
| btn               | Bluetooth name |

#### Subject

The Subject of a Sample is the creator and owner, i.e. the person the Sample is about.

When creating a Sample, the SampleData's Subject attribute is ignored – the identity of the owner is determined by authorization associated with the API call.

When a Client queries the DataServer on behalf of an Agent, the Subject value represents the unique reationship between the Agent and owner – the actual user identifer is hidden.



## DateRange Object

The _DateRange_ object represents a period or instant in time. If the upper and lower bounds are the same, the time represented is considered instant.

### Attributes

| Name       | Type   | Description |
|------------|--------|-------------|
| LowerBound | string | A date and time in ISO 8601 format indicating the start of the range |
| UpperBound | string | A date and time in ISO 8601 format indicating the end of the range   |




## AgencyClaimsResolution

The claims of users over which an Agent has Agency.

### Attributes

| Name | Type | Description |
|-|-|-|
| Claims | array | An array of [`AgencyClaims`](#agency-claims) objects |

### Example

```json
{
    "Claims": [
        {
            "Claims": [
                {
                    "Type": "scope",
                    "Value": "read_body_mass_index"
                },
                {
                    "Type": "name",
                    "Value": "Finlay Mackay"
                },
                {
                    "Type": "given_name",
                    "Value": "Finlay"
                },
                {
                    "Type": "family_name",
                    "Value": "Mackay"
                },
                {
                    "Type": "birthdate",
                    "Value": "2012-02-07"
                },
                {
                    "Type": "email",
                    "Value": "Finlay.Mackay@example.com"
                },
                {
                    "Type": "pseudo_sub",
                    "Value": "303a88f1-5999-41d7-949b-56130202b034"
                }
            ]
        },
        {
            "Claims": [
                {
                    "Type": "scope",
                    "Value": "email"
                },
                ...
            ]
        },
        ...
    ]
}

```



## AgencyClaims

A selection of claims of a single user visible by a specific Agent.

### Attributes

| Name | Type | Description |
|-|-|-|
| Claims | array | An array of [`Claim`](#claim) objects |


## Claim

A user claim.

| Name | Type | Description |
|-|-|-|
| Type | string | The type of the claim, e.g. `name` |
| Value | string | The value of the claim, e.g. `Joe Smith` |

