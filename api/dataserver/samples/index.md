# Samples

A _Sample_ is a represents a piece health data for a user for some time.

The time of a Sample is defined by a start and end date-time. If the start and end values are the same, the Sample represents an instant in time.

## TypeIdentifier

Each Sample has a TypeIdentifier indicating what the Sample data represents, and what type (Quantity, Category, Correlation) the Sample is. For example a Sample recording the number of steps has takem has the TypeIdentifier `StepCount`.

## Scope

In order for a Client to read or write Samples on a user's behalf, the Client must have been granted appropriate scope.

For example, for a Client to read Samples of type `StepCount`, the Client must have been granted the `read_step_count` scope by the user.

A Sample is classified by the type of data it represents:

- [_QuantitySample_](quantity_samples.md) — data is a quantity, eg body-mass in kilograms
- [_CategorySample_](category_samples.md) – data is one of a fixed set of known values, eg `InBed` from a set `InBed`, `Asleep`, `Awake`
- [_CorrelationSample_](correlation_samples.md) – data is zero or more of a set of QuantitySamples or CorrelationSamples
