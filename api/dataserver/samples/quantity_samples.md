
# QuantitySamples

A QuantitySample represents data that is expressed by a number and unit. For example:

- body-mass in kilograms
- height in meters
- heart-rate in beats-per-second

## Non-intuitive Units

The units of a QuantitySample is implied by its type. SI units are used throughout, meaning that some QuantitySamples have quantities in non-intuitive units, eg blood-pressure Samples are stored in Pascals, rather than the more commonly used millimeters of mercury.



## Body Quantities

| TypeIdentifier              | Unit                        | Scope Suffix, prefixed with `read_` or `write_` |
| -|-|- |
| BodyMassIndex               | Kilogram Per Square Meter   | body_mass_index |
| BodyFatPercentage           | Percent (0.0 to 1.0)        | body_fat_percentage |
| Height                      | Meter                       | height |
| BodyMass                    | Kilogram                    | body_mass |
| LeanBodyMass                | Kilogram                    | lean_body_mass |
| WaistCircumference          | Meter                       | waist_circumference |


## Fitness Quantities
| TypeIdentifier              | Unit                        | Scope Suffix, prefixed with `read_` or `write_` |
| -|-|- |
| StepCount                   | Count                       | step_count |
| DistanceWalkingRunning      | Meter                       | distance_walking_running |
| DistanceCycling             | Meter                       | distance_cycling |
| DistanceWheelchair          | Meter                       | distance_wheelchair |
| BasalEnergyBurned           | Joule                       | basal_energy_burned |
| ActiveEnergyBurned          | Joule                       | active_energy_burned |
| FlightsClimbed              | Count                       | flights_climbed |
| NikeFuel                    | Count                       | nike_fuel |
| AppleExerciseTime           | Second                      | apple_exercise_time |
| PushCount                   | Count                       | push_count |
| DistanceSwimming            | Meter                       | distance_swimming |
| SwimmingStrokeCount         | Count                       | swimming_stroke_count |
| Vo2Max                      | Liter Per Kilogram Second   | vo2_max |


## Vitals Quantities

| TypeIdentifier              | Unit                        | Scope Suffix, prefixed with `read_` or `write_` |
|-|-|-|
| HeartRate                   | Count Per Second            | heart_rate |
| BodyTemperature             | Kelvin                      | body_temperature |
| BasalBodyTemperature        | Kelvin                      | basal_body_temperature |
| BloodPressureSystolic       | Pascal                      | blood_pressure_systolic |
| BloodPressureDiastolic      | Pascal                      | blood_pressure_diastolic |
| RespiratoryRate             | Count Per Second            | respiratory_rate |
| RestingHeartRate            | Count Per Second            | resting_heart_rate |
| WalkingHeartRateAverage     | Count Per Second            | walking_heart_rate_average |
| HeartRateVariabilitySDNN    | Second                      | heart_rate_variability_sdnn |


## Results Quantities

| TypeIdentifier              | Unit                        | Scope Suffix, prefixed with `read_` or `write_` |
|-|-|-|
| OxygenSaturation            | Percent (0.0 to 1.0)        | oxygen_saturation |
| PeripheralPerfusionIndex    | Percent (0.0 to 1.0)        | peripheral_perfusion_index |
| BloodGlucose                | Kilogram Per Liter          | blood_glucose |
| NumberOfTimesFallen         | Count                       | number_of_times_fallen |
| ElectrodermalActivity       | Siemen                      | electrodermal_activity |
| InhalerUsage                | Count                       | inhaler_usage |
| InsulinDelivery             | International Unit          | insulin_delivery |
| BloodAlcoholContent         | Percent (0.0 to 1.0)        | blood_alcohol_content |
| ForcedVitalCapacity         | Liter                       | forced_vital_capacity |
| ForcedExpiratoryVolume1     | Liter                       | forced_expiratory_volume1 |
| PeakExpiratoryFlowRate      | Liter Per Second            | peak_expiratory_flow_rate |


## Nutrition Quantities

| TypeIdentifier              | Unit                        | Scope Suffix, prefixed with `read_` or `write_` |
|-|-|-|
| DietaryFatTotal             | Kilogram                    | dietary_fat_total |
| DietaryFatPolyunsaturated   | Kilogram                    | dietary_fat_polyunsaturated |
| DietaryFatMonounsaturated   | Kilogram                    | dietary_fat_monounsaturated |
| DietaryFatSaturated         | Kilogram                    | dietary_fat_saturated |
| DietaryCholesterol          | Kilogram                    | dietary_cholesterol |
| DietarySodium               | Kilogram                    | dietary_sodium |
| DietaryCarbohydrates        | Kilogram                    | dietary_carbohydrates |
| DietaryFiber                | Kilogram                    | dietary_fiber |
| DietarySugar                | Kilogram                    | dietary_sugar |
| DietaryEnergyConsumed       | Joule                       | dietary_energy_consumed |
| DietaryProtein              | Kilogram                    | dietary_protein |
| DietaryVitaminA             | Kilogram                    | dietary_vitamin_a |
| DietaryVitaminB6            | Kilogram                    | dietary_vitamin_b6 |
| DietaryVitaminB12           | Kilogram                    | dietary_vitamin_b12 |
| DietaryVitaminC             | Kilogram                    | dietary_vitamin_c |
| DietaryVitaminD             | Kilogram                    | dietary_vitamin_d |
| DietaryVitaminE             | Kilogram                    | dietary_vitamin_e |
| DietaryVitaminK             | Kilogram                    | dietary_vitamin_k |
| DietaryCalcium              | Kilogram                    | dietary_calcium |
| DietaryIron                 | Kilogram                    | dietary_iron |
| DietaryThiamin              | Kilogram                    | dietary_thiamin |
| DietaryRiboflavin           | Kilogram                    | dietary_riboflavin |
| DietaryNiacin               | Kilogram                    | dietary_niacin |
| DietaryFolate               | Kilogram                    | dietary_folate |
| DietaryBiotin               | Kilogram                    | dietary_biotin |
| DietaryPantothenicAcid      | Kilogram                    | dietary_pantothenic_acid |
| DietaryPhosphorus           | Kilogram                    | dietary_phosphorus |
| DietaryIodine               | Kilogram                    | dietary_iodine |
| DietaryMagnesium            | Kilogram                    | dietary_magnesium |
| DietaryZinc                 | Kilogram                    | dietary_zinc |
| DietarySelenium             | Kilogram                    | dietary_selenium |
| DietaryCopper               | Kilogram                    | dietary_copper |
| DietaryManganese            | Kilogram                    | dietary_manganese |
| DietaryChromium             | Kilogram                    | dietary_chromium |
| DietaryMolybdenum           | Kilogram                    | dietary_molybdenum |
| DietaryChloride             | Kilogram                    | dietary_chloride |
| DietaryPotassium            | Kilogram                    | dietary_potassium |
| DietaryCaffeine             | Kilogram                    | dietary_caffeine |
| DietaryWater                | Liter                       | dietary_water |
| UvExposure                  | Count                       | uv_exposure |
