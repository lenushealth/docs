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
	* a Correlation SampleData of TypeIdentifier "BloodPressure"
	* two child Quantity SampleData of TypeIdentifiers "BloodPressureSystolic" and "BloodPressureDiastolic"

### Example

A Client that reads iron ingestion from the DataServer should:

1. Be configured to request the scopes
	* read.food
	* read.food.dietary_iron
1. When reading data, deconstruct:
	* a Correlation SampleData of TypeIdentifier "Food"
	* a child Quantity SampleData of TypeIdentifiers "DietaryIron" 



## TypeIdentifier and Scope

| TypeIdentifier  | Related QuantitySample TypeIdentifier   | Scope Suffix, prefixed with `read.` or `write.` |
| -|-|- |
| BloodPressure   | BloodPressureSystolic                   | blood_pressure |
|                 | BloodPressureDiastolic |
| Food groups     | DietaryFatTotal                         | food |
|                 | DietaryFatPolyunsaturated |
|                 | DietaryFatMonounsaturated |
|                 | DietaryFatSaturated |
|                 | DietaryCholesterol |
|                 | DietarySodium |
|                 | DietaryCarbohydrates |
|                 | DietaryFiber |
|                 | DietarySugar |
|                 | DietaryEnergyConsumed |
|                 | DietaryProtein |
|                 | DietaryVitaminA |
|                 | DietaryVitaminB6 |
|                 | DietaryVitaminB12 |
|                 | DietaryVitaminC |
|                 | DietaryVitaminD |
|                 | DietaryVitaminE |
|                 | DietaryVitaminK |
|                 | DietaryCalcium |
|                 | DietaryIron |
|                 | DietaryThiamin |
|                 | DietaryRiboflavin |
|                 | DietaryNiacin |
|                 | DietaryFolate |
|                 | DietaryBiotin |
|                 | DietaryPantothenicAcid |
|                 | DietaryPhosphorus |
|                 | DietaryIodine |
|                 | DietaryMagnesium |
|                 | DietaryZinc |
|                 | DietarySelenium |
|                 | DietaryCopper |
|                 | DietaryManganese |
|                 | DietaryChromium |
|                 | DietaryMolybdenum |
|                 | DietaryChloride |
|                 | DietaryPotassium |
|                 | DietaryCaffeine |
|                 | DietaryWater |
