
# QuantitySamples

[Please note the important relationship some QuantitySamples have with CorrelationSamples](correlation_samples.md#important-note).

A QuantitySample represents data that is expressed by a number and unit. For example:

- body-mass in kilograms
- height in meters
- heart-rate in beats-per-second

## Non-intuitive Units

The units of a QuantitySample is implied by its type. SI units are used throughout, meaning that some QuantitySamples have quantities in non-intuitive units, eg blood-pressure Samples are stored in Pascals, rather than the more commonly used millimeters of mercury.

## Body Quantities

Scope is TypeIdentifier prefixed with `read.` or `write.`. 

| TypeIdentifier | Unit                        |
|- |-|
| body_mass_index | Kilogram Per Square Meter   |
| body_fat_percentage | Percent (0.0 to 1.0)        |
| height | Meter                       |
| body_mass | Kilogram                    |
| lean_body_mass | Kilogram                    |
| waist_circumference | Meter                       |


## Fitness Quantities

Scope is TypeIdentifier prefixed with `read.` or `write.`. 

| TypeIdentifier | Unit                        |
|- |-|
| step_count | Count                       |
| distance_walking_running | Meter                       |
| distance_cycling | Meter                       |
| distance_wheelchair | Meter                       |
| basal_energy_burned | Joule                       |
| active_energy_burned | Joule                       |
| flights_climbed | Count                       |
| nike_fuel | Count                       |
| apple_exercise_time | Second                      |
| push_count | Count                       |
| distance_swimming | Meter                       |
| swimming_stroke_count | Count                       |
| vo2_max | Liter Per Kilogram Second   |


## Vitals Quantities

Scope is TypeIdentifier prefixed with `read.` or `write.`, except in the case of `blood_pressure_systolic` and `blood_pressure_diastolic`, where the prefixes are `read.blood_pressure.` and `write.blood_pressure.`. 

| TypeIdentifier | Unit                        |
|-|-|
| heart_rate | Count Per Second            |
| body_temperature | Kelvin                      |
| basal_body_temperature | Kelvin                      |
| blood_pressure_systolic | Pascal                      |
| blood_pressure_diastolic | Pascal                      |
| respiratory_rate | Count Per Second            |
| resting_heart_rate | Count Per Second            |
| walking_heart_rate_average | Count Per Second            |
| heart_rate_variability_sdnn | Second                      |


## Results Quantities

Scope is TypeIdentifier prefixed with `read.` or `write.`. 

| TypeIdentifier | Unit                        |
|-|-|
| oxygen_saturation | Percent (0.0 to 1.0)        |
| peripheral_perfusion_index | Percent (0.0 to 1.0)        |
| blood_glucose | Kilogram Per Liter          |
| number_of_times_fallen | Count                       |
| electrodermal_activity | Siemen                      |
| inhaler_usage | Count                       |
| insulin_delivery | International Unit          |
| blood_alcohol_content | Percent (0.0 to 1.0)        |
| forced_vital_capacity | Liter                       |
| forced_expiratory_volume1 | Liter                       |
| peak_expiratory_flow_rate | Liter Per Second            |


## Nutrition Quantities

Scope is TypeIdentifier prefixed with `read.food.` or `write.food.`. 

| TypeIdentifier | Unit                        |
|-|-|
| dietary_fat_total | Kilogram                    |
| dietary_fat_polyunsaturated | Kilogram                    |
| dietary_fat_monounsaturated | Kilogram                    |
| dietary_fat_saturated | Kilogram                    |
| dietary_cholesterol | Kilogram                    |
| dietary_sodium | Kilogram                    |
| dietary_carbohydrates | Kilogram                    |
| dietary_fiber | Kilogram                    |
| dietary_sugar | Kilogram                    |
| dietary_energy_consumed | Joule                       |
| dietary_protein | Kilogram                    |
| dietary_vitamin_a | Kilogram                    |
| dietary_vitamin_b6 | Kilogram                    |
| dietary_vitamin_b12 | Kilogram                    |
| dietary_vitamin_c | Kilogram                    |
| dietary_vitamin_d | Kilogram                    |
| dietary_vitamin_e | Kilogram                    |
| dietary_vitamin_k | Kilogram                    |
| dietary_calcium | Kilogram                    |
| dietary_iron | Kilogram                    |
| dietary_thiamin | Kilogram                    |
| dietary_riboflavin | Kilogram                    |
| dietary_niacin | Kilogram                    |
| dietary_folate | Kilogram                    |
| dietary_biotin | Kilogram                    |
| dietary_pantothenic_acid | Kilogram                    |
| dietary_phosphorus | Kilogram                    |
| dietary_iodine | Kilogram                    |
| dietary_magnesium | Kilogram                    |
| dietary_zinc | Kilogram                    |
| dietary_selenium | Kilogram                    |
| dietary_copper | Kilogram                    |
| dietary_manganese | Kilogram                    |
| dietary_chromium | Kilogram                    |
| dietary_molybdenum | Kilogram                    |
| dietary_chloride | Kilogram                    |
| dietary_potassium | Kilogram                    |
| dietary_caffeine | Kilogram                    |
| dietary_water | Liter                       |

## UV Exposure Quantities

Scope is TypeIdentifier prefixed with `read.` or `write.`. 

| TypeIdentifier | Unit                        |
|-|-|
| uv_exposure | Count                       |
