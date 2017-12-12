# Health data types

There are three kinds of sample:

- A `Correlation`, representing a grouping of other samples.
- `Category` where the sample takes one of a set of well known values.
- `Quantity`, where the sample has a discrete value in a prescribed unit.

## Correlations
There are two types of correlation sample, `BloodPressure` and `Food`. Both group zero or more quantity samples.

### BloodPressure groups
- `BloodPressureSystolic`,
- `BloodPressureDiastolic`

### Food groups
- `DietaryFatTotal`,
- `DietaryFatPolyunsaturated`,
- `DietaryFatMonounsaturated`,
- `DietaryFatSaturated`,
- `DietaryCholesterol`,
- `DietarySodium`,
- `DietaryCarbohydrates`,
- `DietaryFiber`,
- `DietarySugar`,
- `DietaryEnergyConsumed`,
- `DietaryProtein`,
- `DietaryVitaminA`,
- `DietaryVitaminB6`,
- `DietaryVitaminB12`,
- `DietaryVitaminC`,
- `DietaryVitaminD`,
- `DietaryVitaminE`,
- `DietaryVitaminK`,
- `DietaryCalcium`,
- `DietaryIron`,
- `DietaryThiamin`,
- `DietaryRiboflavin`,
- `DietaryNiacin`,
- `DietaryFolate`,
- `DietaryBiotin`,
- `DietaryPantothenicAcid`,
- `DietaryPhosphorus`,
- `DietaryIodine`,
- `DietaryMagnesium`,
- `DietaryZinc`,
- `DietarySelenium`,
- `DietaryCopper`,
- `DietaryManganese`,
- `DietaryChromium`,
- `DietaryMolybdenum`,
- `DietaryChloride`,
- `DietaryPotassium`,
- `DietaryCaffeine`,
- `DietaryWater`

## Categories
There are eight types of category:
- `SleepAnalysis`,
- `AppleStandHour`,
- `CervicalMucusQuality`,
- `OvulationTestResult`,
- `MenstrualFlow`,
- `IntermenstrualBleeding`,
- `SexualActivity`,
- `MindfulSession`

A `SleepAnalysis` sample may take one of the following values:
- `InBed`,
- `Asleep`,
- `Awake`

A `AppleStandHour` sample may take one of the following values:
- `Stood`,
- `Idle`

A `CervicalMucusQuality` sample may take one of the following values:
- `Dry`,
- `Sticky`,
- `Creamy`,
- `Watery`,
- `EggWhite`

A `OvulationTestResult` sample may take one of the following values:
- `Negative`,
- `Positive`,
- `Indeterminate`

A `MenstrualFlow` sample may take one of the following values:
- `Unspecified`,
- `Light`,
- `Medium`,
- `Heavy`

A `IntermenstrualBleeding`, `SexualActivity`, or `MindfulSession` sample may only have the value `NotApplicable`.


## Quantities

Quantities can be of the following types and units:

### Body
- `BodyMassIndex` (KilogramPerSquareMeter)
- `BodyFatPercentage` (Percent between 0.0 and 1.0)
- `Height` (Meter)
- `BodyMass` (Kilogram)
- `LeanBodyMass` (Kilogram)
- `WaistCircumference` (Meter)

### Fitness
- `StepCount` (Count)
- `DistanceWalkingRunning` (Meter)
- `DistanceCycling` (Meter)
- `DistanceWheelchair` (Meter)
- `BasalEnergyBurned` (Joule)
- `ActiveEnergyBurned` (Joule)
- `FlightsClimbed` (Count)
- `NikeFuel` (Count)
- `AppleExerciseTime` (Second)
- `PushCount` (Count)
- `DistanceSwimming` (Meter)
- `SwimmingStrokeCount` (Count)
- `Vo2Max` (LiterPerKilogramSecond)

### Vitals
- `HeartRate` (CountPerSecond)
- `BodyTemperature` (Kelvin)
- `BasalBodyTemperature` (Kelvin)
- `BloodPressureSystolic` (Pascal)
- `BloodPressureDiastolic` (Pascal)
- `RespiratoryRate` (CountPerSecond)

## Beats per minute estimate of a user's lowest heart rate while at rest
- `RestingHeartRate` (CountPerSecond)

## Average heartbeats per minute captured by an Apple Watch while a user is walking
- `WalkingHeartRateAverage` (CountPerSecond)

## The standard deviation of heart beat-to-beat intevals (Standard Deviation of Normal to Normal)
- `HeartRateVariabilitySDNN` (Second)

## Results
- `OxygenSaturation` (Percent between 0.0 and 1.0)
- `PeripheralPerfusionIndex` (Percent between 0.0 and 1.0)
- `BloodGlucose` (KilogramPerLiter)
- `NumberOfTimesFallen` (Count)
- `ElectrodermalActivity` (Siemen)
- `InhalerUsage` (Count)
- `InsulinDelivery` (InternationalUnit)
- `BloodAlcoholContent` (Percent between 0.0 and 1.0)
- `ForcedVitalCapacity` (Liter)
- `ForcedExpiratoryVolume1` (Liter)
- `PeakExpiratoryFlowRate` (LiterPerSecond)

## Nutrition
- `DietaryFatTotal` (Kilogram)
- `DietaryFatPolyunsaturated` (Kilogram)
- `DietaryFatMonounsaturated` (Kilogram)
- `DietaryFatSaturated` (Kilogram)
- `DietaryCholesterol` (Kilogram)
- `DietarySodium` (Kilogram)
- `DietaryCarbohydrates` (Kilogram)
- `DietaryFiber` (Kilogram)
- `DietarySugar` (Kilogram)
- `DietaryEnergyConsumed` (Joule)
- `DietaryProtein` (Kilogram)
- `DietaryVitaminA` (Kilogram)
- `DietaryVitaminB6` (Kilogram)
- `DietaryVitaminB12` (Kilogram)
- `DietaryVitaminC` (Kilogram)
- `DietaryVitaminD` (Kilogram)
- `DietaryVitaminE` (Kilogram)
- `DietaryVitaminK` (Kilogram)
- `DietaryCalcium` (Kilogram)
- `DietaryIron` (Kilogram)
- `DietaryThiamin` (Kilogram)
- `DietaryRiboflavin` (Kilogram)
- `DietaryNiacin` (Kilogram)
- `DietaryFolate` (Kilogram)
- `DietaryBiotin` (Kilogram)
- `DietaryPantothenicAcid` (Kilogram)
- `DietaryPhosphorus` (Kilogram)
- `DietaryIodine` (Kilogram)
- `DietaryMagnesium` (Kilogram)
- `DietaryZinc` (Kilogram)
- `DietarySelenium` (Kilogram)
- `DietaryCopper` (Kilogram)
- `DietaryManganese` (Kilogram)
- `DietaryChromium` (Kilogram)
- `DietaryMolybdenum` (Kilogram)
- `DietaryChloride` (Kilogram)
- `DietaryPotassium` (Kilogram)
- `DietaryCaffeine` (Kilogram)
- `DietaryWater` (Liter)
- `UvExposure` (Count)

