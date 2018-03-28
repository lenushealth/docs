# Samples

A _Sample_ represents a piece health data for a user for some time.

The time of a Sample is defined by a start and end date-time. If the start and end values are the same, the Sample represents an instant in time.

A Sample belongs to one of three families:

- [_QuantitySample_](quantity_samples.md) — data is a quantity, eg body-mass in kilograms
- [_CategorySample_](category_samples.md) – data is one of a fixed set of known values, eg `InBed` from a set `InBed`, `Asleep`, `Awake`
- [_CorrelationSample_](correlation_samples.md) – data is zero or more of a set of QuantitySamples or CorrelationSamples

## TypeIdentifier

Each Sample has a TypeIdentifier indicating to what family (Quantity, Category, Correlation) the Sample belongs, and very specifically what the data represents.

For example, the TypeIdentifier `step_count` flags a Sample as being a Quantity that records a number of steps taken.

TypeIdentifers are used within JSON request and response objects to say what a Sample represents.

**TypeIdentifiers are case-sensitive**.

## Scope

In order for a Client to read or write Samples on a user's behalf, the Client must have been granted appropriate scope.


There is a close coupling between a TypeIdentifier and scope. The form of a scope is the TypeIdentifier prefixed with `read.` or `write.`, for read and write access respectively.

For example, for a Client to read Samples of type `step_count`, the Client must have been granted the `read.step_count` scope by the user.

**Scopes are case-sensitive**.
