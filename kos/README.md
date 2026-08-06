# Implementación KOS (Vocabulario Controlado)

Esta carpeta contiene los **archivos de implementación de vocabulario controlado o KOS**, que representan la definición formal y legible por máquina de los vocabularios necesarios.

## Propósito

El objetivo de este directorio es almacenar los **archivos de vocabulario o KOS**, que describen los conceptos y las relaciones entre ellos.

## Contenido

Esta implementación incluye dos vocabularios SKOS para monitorización ambiental urbana:

- [`sensor-variables.ttl`](sensor-variables.ttl) - El tesauro de variables de sensor
- [`feature-of-interest.ttl`](feature-of-interest.ttl) - El vocabulario de características de interés

## Diseño de Vocabularios SKOS

Esta implementación KOS define dos esquemas de conceptos SKOS interconectados que trabajan juntos para describir observaciones de sensores en entornos urbanos.

### 1. SensorVariables (kos/sensor-variables.ttl)

Un esquema de conceptos que agrupa propiedades y magnitudes medidas por sensores en entornos urbanos. Sigue una estructura jerárquica con categorías de nivel superior y subcategorías anidadas.

**Categorías de nivel superior:**
- MeteorologicalVariables (Variables Meteorológicas)
- AirQualityVariables (Variables de Calidad del Aire)
- AcousticVariables (Variables Acústicas)
- WaterQualityVariables (Variables de Calidad del Agua)
- SoilVariables (Variables del Suelo)
- TrafficVariables (Variables de Tráfico)
- EnergyVariables (Variables Energéticas)
- WasteVariables (Variables de Residuos)
- SensorStatusVariables (Variables de Estado del Sensor)

**Estructura jerárquica:**
```
SensorVariables
├── MeteorologicalVariables
│   ├── TemperatureVariables
│   │   ├── AirTemperature
│   │   ├── RoadTemperature
│   │   ├── DewPointTemperature
│   │   ├── WetBulbTemperature
│   │   ├── HeatIndex
│   │   └── WindChill
│   ├── HumidityVariables
│   │   ├── RelativeHumidity
│   │   └── AbsoluteHumidity
│   ├── PressureVariables
│   │   ├── AtmosphericPressure
│   │   └── SeaLevelPressure
│   ├── WindVariables
│   │   ├── WindSpeed
│   │   ├── MaximumWindSpeed
│   │   ├── WindDirection
│   │   └── WindGustDirection
│   ├── PrecipitationVariables
│   │   ├── PrecipitationAmount
│   │   ├── PrecipitationIntensity
│   │   ├── SnowDepth
│   │   └── SnowWaterEquivalent
│   ├── RadiationVariables
│   │   ├── SolarIrradiance
│   │   ├── UVIndex
│   │   ├── PhotosyntheticallyActiveRadiation
│   │   └── NetRadiation
│   ├── LightVariables
│   │   ├── Illuminance
│   │   └── SunshineDuration
│   └── VisibilityVariables
│       ├── Visibility
│       └── CloudBaseHeight
├── AirQualityVariables
│   ├── GaseousPollutants
│   │   ├── NO2Concentration
│   │   ├── NOConcentration
│   │   ├── NOxConcentration
│   │   ├── O3Concentration
│   │   ├── SO2Concentration
│   │   ├── COConcentration
│   │   ├── NH3Concentration
│   │   └── H2SConcentration
│   ├── GreenhouseGases
│   │   ├── CO2Concentration
│   │   ├── CH4Concentration
│   │   └── N2OConcentration
│   ├── VolatileOrganicCompounds
│   │   ├── BenzeneConcentration
│   │   ├── TolueneConcentration
│   │   ├── XyleneConcentration
│   │   ├── FormaldehydeConcentration
│   │   └── TotalVOCConcentration
│   ├── ParticulateMatterVariables
│   │   ├── PM1Concentration
│   │   ├── PM25Concentration
│   │   ├── PM10Concentration
│   │   ├── TotalSuspendedParticles
│   │   └── ParticleNumberConcentration
│   ├── HeavyMetalVariables
│   │   ├── ArsenicConcentration
│   │   ├── NickelConcentration
│   │   ├── CadmiumConcentration
│   │   ├── LeadConcentration
│   │   ├── MercuryConcentration
│   │   └── BenzoAPyreneConcentration
│   ├── PollenVariables
│   │   ├── PollenConcentration
│   │   └── SporeConcentration
│   └── OdorVariables
│       ├── OdorIntensity
│       └── OdorConcentration
├── AcousticVariables
│   ├── EquivalentSoundPressureLevel
│   ├── StatisticalNoiseLevels
│   │   ├── L10
│   │   ├── L50
│   │   ├── L90
│   │   ├── Lmax
│   │   └── Lmin
│   └── TemporalNoiseLevels
│       ├── DayTimeNoiseLevel
│       ├── EveningNoiseLevel
│       ├── NightTimeNoiseLevel
│       └── DayEveningNightNoiseLevel
├── WaterQualityVariables
│   ├── WaterPhysicochemicalVariables
│   │   ├── WaterTemperature
│   │   ├── WaterPH
│   │   ├── WaterElectricalConductivity
│   │   ├── WaterTurbidity
│   │   ├── TotalDissolvedSolids
│   │   ├── ResidualFreeChlorine
│   │   ├── DissolvedOxygen
│   │   ├── OxygenSaturation
│   │   └── WaterRedoxPotential
│   ├── WaterHydraulicVariables
│   │   ├── WaterLevel
│   │   ├── WaterFlowRate
│   │   ├── WaterVelocity
│   │   └── WaterPressure
│   ├── WaterNutrientVariables
│   │   ├── NitrateConcentration
│   │   ├── NitriteConcentration
│   │   ├── PhosphateConcentration
│   │   └── AmmoniumConcentration
│   └── WaterBiologicalVariables
│       ├── ChlorophyllAConcentration
│       └── BlueGreenAlgaeConcentration
├── SoilVariables
│   ├── SoilTemperature
│   ├── SoilMoistureTension
│   ├── SoilMoistureContent
│   ├── SoilPH
│   ├── SoilElectricalConductivity
│   └── SoilSalinity
├── TrafficVariables
│   ├── TrafficFlowVariables
│   │   ├── VehicleCount
│   │   └── TrafficFlow
│   ├── TrafficSpeedVariables
│   │   ├── AverageTrafficSpeed
│   │   └── MaximumTrafficSpeed
│   └── TrafficOccupancyVariables
│       ├── LaneOccupancy
│       └── ParkingOccupancy
├── EnergyVariables
│   ├── ElectricityVariables
│   │   ├── ActivePower
│   │   ├── ReactivePower
│   │   ├── ActiveEnergy
│   │   ├── Voltage
│   │   ├── ElectricCurrent
│   │   └── PowerFactor
│   └── GasVariables
│       ├── GasFlowRate
│       ├── GasPressure
│       └── GasConsumption
├── WasteVariables
│   ├── ContainerFillLevel
│   ├── ContainerTemperature
│   └── ContainerWeight
└── SensorStatusVariables
    ├── BatteryLevel
    ├── BatteryVoltage
    ├── InternalSensorTemperature
    ├── SignalStrength
    └── SensorUptime
```

### 2. FeaturesOfInterest (kos/feature-of-interest.ttl)

Un esquema de conceptos que agrupa características de interés observables por sensores según la ontología SOSA. Cada característica tiene enlaces directos a propiedades observables a través de relaciones `sosa:hasProperty`.

**Estructura jerárquica con enlaces a propiedades:**
```
FeaturesOfInterest
├── Air
│   └── hasProperty → AirTemperature, RelativeHumidity, AtmosphericPressure,
│                     NO2Concentration, NOConcentration, NOxConcentration,
│                     O3Concentration, SO2Concentration, COConcentration,
│                     NH3Concentration, BenzeneConcentration, TolueneConcentration,
│                     XyleneConcentration
├── ParticulateMatter
│   └── hasProperty → PM1Concentration, PM25Concentration, PM10Concentration,
│                     ArsenicConcentration, NickelConcentration, CadmiumConcentration,
│                     LeadConcentration, BenzoAPyreneConcentration
├── Soil
│   └── hasProperty → SoilTemperature, SoilMoistureTension
├── RoadSurface
│   └── hasProperty → RoadTemperature
├── Wind
│   └── hasProperty → WindSpeed, MaximumWindSpeed, WindDirection
├── Precipitation
│   └── hasProperty → PrecipitationAmount
├── SolarRadiation
│   └── hasProperty → SolarIrradiance, UVIndex, PhotosyntheticallyActiveRadiation
├── AmbientLight
│   └── hasProperty → Illuminance
├── AirbornePollen
│   └── hasProperty → PollenConcentration
├── AcousticEnvironment
│   └── hasProperty → EquivalentSoundPressureLevel, DayTimeNoiseLevel,
│                     NightTimeNoiseLevel, DayEveningNightNoiseLevel
├── DrinkingWater
│   └── hasProperty → ResidualFreeChlorine, WaterTurbidity, WaterPH,
│                     WaterElectricalConductivity, DissolvedOxygen, WaterTemperature
└── IoTSensor
    └── hasProperty → BatteryLevel, BatteryVoltage, InternalSensorTemperature
```

## Principios de Diseño

### Integración con la ontología SOSA
- Los conceptos en **SensorVariables** están tipados como `sosa:ObservableProperty` y `qudt:QuantityKind`
- Los conceptos en **FeaturesOfInterest** están tipados como `sosa:FeatureOfInterest`
- Las características enlazan a propiedades usando relaciones `sosa:hasProperty`

### Integración con QUDT
- Unidades estandarizadas definidas vía `qudt:applicableUnit` para cada propiedad observable
- Utiliza vocabulario de unidades QUDT (por ejemplo, `unit:DEG_C`, `unit:PERCENT`, `unit:DeciB`)

### Etiquetas Bilingües
- Todos los conceptos incluyen etiquetas en inglés (`@en`) y español (`@es`)
- PrefLabels, AltLabels, Definitions y Comments se proporcionan en ambos idiomas

### Organización Jerárquica
- Utiliza `skos:narrower` y `skos:broader` para relaciones jerárquicas
- Conceptos top definidos vía `skos:hasTopConcept` en el esquema de conceptos

## Relación entre Vocabularios

Los dos vocabularios trabajan juntos para permitir el modelado completo de observaciones de sensores:

1. **FeaturesOfInterest** referencia **ObservableProperties** de SensorVariables a través de relaciones `sosa:hasProperty`
2. Esta separación permite:
   - Definiciones de propiedades reutilizables en SensorVariables
   - Agrupamiento contextual de propiedades por lo que se está observando (FeatureOfInterest)
   - Modelado flexible de observaciones siguiendo patrones SOSA

### Patrón de Observación de Ejemplo

```turtle
# Un sensor observa una propiedad de una característica
:observation1 a sosa:Observation ;
    sosa:observedBy :sensor1 ;
    sosa:observes edintkos-vars:AirTemperature ;
    sosa:featureOfInterest edintkos-foi:Air ;
    sosa:hasSimpleResult "22.5"^^xsd:decimal ;
    qudt:hasUnit unit:DEG_C .
```

En este patrón:
- `edintkos-foi:Air` (FeatureOfInterest) tiene `edintkos-vars:AirTemperature` como propiedad
- La observación enlaza tanto la característica como la propiedad siendo medida

## Estructura de Archivos

| Archivo | Descripción |
|------|-------------|
| [`kos/sensor-variables.ttl`](sensor-variables.ttl) | El tesauro de variables de sensor - define todas las propiedades observables con categorización jerárquica |
| [`kos/feature-of-interest.ttl`](feature-of-interest.ttl) | El vocabulario de características de interés - define características observables con enlaces a propiedades |

## Mejores Prácticas

- Mantén las versiones del vocabulario claramente etiquetadas y documentadas
- Valida la sintaxis y semántica antes de confirmar cambios
- Mantén la consistencia con los diagramas conceptuales y la documentación
- Utiliza un espacio de nombres estandarizado y una estrategia de prefijos

## Notas

- Esta carpeta contiene solo **archivos de implementación** — no diagramas, notas o documentación
- Considera agregar un registro de cambios o historial de versiones si se mantienen múltiples versiones del vocabulario
