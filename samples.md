# Samples

A _Sample_ is a represents a piece health data for a user for some time.


The time of a Sample is defined by a start and end date-time. If the start and end values are the same, the Sample represents an instant in time.


A Sample is classified by the type of data it represents:

- _QuantitySample_ — data is a quantity, eg mass in kg
- _CategorySample_ – data is one of a fixed set of known values, eg `InBed` from a set `InBed`, `Asleep`, `Awake`
- _CorrelationSample_ – data is zero or more of a set of QuantitySamples or CorrelationSamples






