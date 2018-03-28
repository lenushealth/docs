# CorrelationSamples

A CorrelationSample groups nutritional or blood pressure QuantitySamples.

## Important Note

TL;DR: You need to have scope, and request TypeIdentifiers for Correlation and Quantity.

The relationship between CorrelationSamples and QuantitySamples that is important to consider when:

* Requesting scope
* Using the [DataServer API](../index.md)

When reading or writing Quantity Samples that are correlated (are grouped by a parent Correlation Sample), a request must:

* contain appropriate scope for Quantities _and_ Correlations
* contain TypeIdentifiers for Quantities _and_ Correlations

### Example

A Client that writes systolic and diastolic blood pressure data to the DataServer should:

1. Be configured to request the scopes
	* write.blood_pressure
	* write.blood_pressure.blood_pressure_systolic
	* write.blood_pressure.blood_pressure_diastolic
1. When writing data, construct:
	* a Correlation SampleData of TypeIdentifier "blood_pressure"
	* two child Quantity SampleData of TypeIdentifiers "blood_pressure_systolic" and "blood_pressure_diastolic"

### Example

A Client that reads iron ingestion from the DataServer should:

1. Be configured to request the scopes
	* read.food
	* read.food.dietary_iron
1. When reading data, deconstruct:
	* a Correlation SampleData of TypeIdentifier "food"
	* a child Quantity SampleData of TypeIdentifiers "dietary_iron" 



## TypeIdentifier and Scope

Scope is TypeIdentifier prefixed with `read.` or `write.`. 

| TypeIdentifier  | Related QuantitySample TypeIdentifier   |
| -|-|-                                                     |
| blood_pressure  | blood_pressure_systolic                 |
|                 | blood_pressure_diastolic                |
| food            | dietary_fat_total                       |
|                 | dietary_fat_polyunsaturated             |
|                 | dietary_fat_monounsaturated             |
|                 | dietary_fat_saturated                   |
|                 | dietary_cholesterol                     |
|                 | dietary_sodium                          |
|                 | dietary_carbohydrates                   |
|                 | dietary_fiber                           |
|                 | dietary_sugar                           |
|                 | dietary_energy_consumed                 |
|                 | dietary_protein                         |
|                 | dietary_vitamin_a                       |
|                 | dietary_vitamin_b6                      |
|                 | dietary_vitamin_b12                     |
|                 | dietary_vitamin_c                       |
|                 | dietary_vitamin_d                       |
|                 | dietary_vitamin_e                       |
|                 | dietary_vitamin_k                       |
|                 | dietary_calcium                         |
|                 | dietary_iron                            |
|                 | dietary_thiamin                         |
|                 | dietary_riboflavin                      |
|                 | dietary_niacin                          |
|                 | dietary_folate                          |
|                 | dietary_biotin                          |
|                 | dietary_pantothenic_acid                |
|                 | dietary_phosphorus                      |
|                 | dietary_iodine                          |
|                 | dietary_magnesium                       |
|                 | dietary_zinc                            |
|                 | dietary_selenium                        |
|                 | dietary_copper                          |
|                 | dietary_manganese                       |
|                 | dietary_chromium                        |
|                 | dietary_molybdenum                      |
|                 | dietary_chloride                        |
|                 | dietary_potassium                       |
|                 | dietary_caffeine                        |
|                 | dietary_water                           |

