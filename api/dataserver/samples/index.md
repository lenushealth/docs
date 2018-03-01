# Samples

A _Sample_ is a represents a piece health data for a user for some time.

The time of a Sample is defined by a start and end date-time. If the start and end values are the same, the Sample represents an instant in time.

## Classifications of Sample

A Sample is classified as one of:

- [_QuantitySample_](quantity_samples.md) — data is a quantity, eg body-mass in kilograms
- [_CategorySample_](category_samples.md) – data is one of a fixed set of known values, eg `InBed` from a set `InBed`, `Asleep`, `Awake`
- [_CorrelationSample_](correlation_samples.md) – data is zero or more of a set of QuantitySamples or CorrelationSamples

## TypeIdentifier

Each Sample has a TypeIdentifier indicating to what classification (Quantity, Category, Correlation) the Sample belongs, and very specifically what the data represents.

For example the TypeIdentifier `StepCount` flags a Sample as being a Quantity that records a number of steps taken.

TypeIdentifers are used in within JSON request and response objects to say what a Sample represents.

## Scope

In order for a Client to read or write Samples on a user's behalf, the Client must have been granted appropriate scope.

There is a close coupling between a TypeIdentifier and scope, with each TypeIdentifier having two corresponding scopes (read and write variants).

For example, for a Client to read Samples of type `StepCount`, the Client must have been granted the `read_step_count` scope by the user.

