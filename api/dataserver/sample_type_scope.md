# TODO

Preamble and explanation here

## TypeIdentifier

Each Sample has a TypeIdentifier indicating what the Sample data represents, and what type (Quantity, Category, Correlation) the Sample is. For example a Sample recording the number of steps has takem has the TypeIdentifier `StepCount`.

## Scope

In order for a Client to read or write Samples on a user's behalf, the Client must have been granted appropriate scope.

For example, for a Client to read Samples of type `StepCount`, the Client must have been granted the `read_step_count` scope by the user.

### TODO

* [QuantitySamples](quantity_samples.md)
* [CategorySamples](category_samples.md)
* [CorrelationSamples](correlation_samples.md)
