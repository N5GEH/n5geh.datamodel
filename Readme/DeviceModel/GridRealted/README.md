# GridRelated: 
It is composed of the following categories of Device Model in related to Building and inheritating properties belong to [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device)
-   Convertor
    - [AC-DC](https://github.com/N5GEH/SARGON/blob/master/Readme/DeviceModel/GridRealted/README.md#ac-dc)
-   [Meter](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel/GridRealted#meter)
    - [EnergyMeter](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel/GridRealted#energy-meter)
    - [PMU](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel/GridRealted#pmu)
    - [PowerMeter](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel/GridRealted#power-meter)
-   Storage
    - [Batery](###Batery)
### AC-DC
Convertor in AC-DC network, according to IEC 61850 standard. It can inherit properties of [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device)
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `ACDC`.
-   `logicalNode'`: 
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     - Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `loN`
- `primaryCurrent`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)
     -   Mandatory
     -   Abbriviation: `prC`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
- `primaryVoltage` :
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     - Value : [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `prV`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
- `secondaryCurrent`:
     -  Attribute type: `Property`. 
     - Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `seC`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional  
 - `secondaryVoltage`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)  
     -   Optional
     -   Abbriviation: `secV`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`. 
     -  Value: object of [SubCategory]https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModelx)
     -   Optional
- `address` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
        -   `Type`: [Text](https://schema.org/PostalAddress)
        -   `addressLocality`: locality [Text](https://schema.org/Text)
        -   `addressCountry`: Country [Text](https://schema.org/Text)
        -   `postalCode` :  Post code [Text](https://schema.org/Text)
        -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional


### Example
```json
{
  give is soon!
 
}

```
### Meter
A metering device, inherit [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device) properties
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `Meter`.
-   `name`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `prV`
-  `listening`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)    
     -   Optional
     -   Abbriviation: `lis`    
-  `sampleRate`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `sam`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `writable`: 
     -  Attribute type: `Property`. 
     -   Value: [Boolean](https://schema.org/Boolean)
     -   Optional
-  `sampleInterval`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `saI`  
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `loggingInterval`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `loI`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`. 
     -  Value: object of [SubCategory](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel)
     -   Optional
- `hasChannel`: 
     -  Attribute type: `Property`.  [Channel](https://sargon-n5geh.netlify.app)
     -  Value: [Text](https://schema.org/Text)
     -  Optional
     - ( Angle, Frequency, Maqnititute, Rocf, TimeStamp)
- `isMeasuredIn`: 
     -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     
- `address` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
        -   `Type`: [Text](https://schema.org/PostalAddress)
        -   `addressLocality`: locality [Text](https://schema.org/Text)
        -   `addressCountry`: Country [Text](https://schema.org/Text)
        -   `postalCode` :  Post code [Text](https://schema.org/Text)
        -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional


### Example
```json
{
  give is soon!
 
}

```

### Energy Meter
A metering device for energy, inherit [Metering]() and [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device) properties
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `EnergyMeter`.
-  `accomplishes`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   (eneryEfficiency)
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `address` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
        -   `Type`: [Text](https://schema.org/PostalAddress)
        -   `addressLocality`: locality [Text](https://schema.org/Text)
        -   `addressCountry`: Country [Text](https://schema.org/Text)
        -   `postalCode` :  Post code [Text](https://schema.org/Text)
        -   `streetAddress`: Street address [Text](https://schema.org/Text)
- `isMeasuredIn`: 
     -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     

### Example
```json
{
  give is soon!
 
}

```
### PMU
A metering device, inherit [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device) and [Meter](### Meter)properties
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `PMU`.
-  `readableName`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `nam`
-  `sampleRate`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `sam`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `activePower`: 
     -  Attribute type: `Property`. 
     -   Value: [String](https://schema.org/String)
     -   Optional
     -   Abbriviation: `acP`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `reactivePower`: 
     -  Attribute type: `Property`. 
     -   Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `reP`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `sampleInterval`: 
     -  Attribute type: `Property`. 
     -   Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `saI`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `loggingInterval`: 
     -  Attribute type: `Property`. 
     -   Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `loI`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel)
     -   Optional
- `hasChannel`: 
     -  Attribute type: `Property`.  [Channel]
     -  Value: [Text](https://schema.org/Text)
     -  Optional
     - ( Angle, Frequency, Maqnititute, Rocf, TimeStamp)
- `isMeasuredIn`: 	A relationship identifying the unit of measure used for a certain entity.
     -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     
- `address` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
        -   `Type`: [Text](https://schema.org/PostalAddress)
        -   `addressLocality`: locality [Text](https://schema.org/Text)
        -   `addressCountry`: Country [Text](https://schema.org/Text)
        -   `postalCode` :  Post code [Text](https://schema.org/Text)
        -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional


### Example
```json
{
  give is soon!
 
}

```
### Power Meter
A metering device for power, inherit [Metering]() and [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device) properties
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `PowerMeter`.
-  `accomplishes`: 
     -  Attribute type: `Property`. 
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     -   (eneryEfficiency)
-  `accuracy`: 
     -  Attribute type: `Property`.
     -  Value: [Text](https://schema.org/Text)
     -   Optional
-  `activePower`: 
     -  Attribute type: `Property`. 
     -   Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `acP`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `reactivePower`: 
     -  Attribute type: `Property`. 
     -   Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `reP`
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-  `hasFunction`: 
     -  Attribute type: `Relationships`.
     -  Value:  object of  [Function](https://w3id.org/saref#Function)
     -   Optional
-  `hasState`: 
     -  Attribute type: `Relationships` 
     -  Value:  object of  [State](https://w3id.org/saref#State)
     -   Optional
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel)
     -   Optional
- `address` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
        -   `Type`: [Text](https://schema.org/PostalAddress)
        -   `addressLocality`: locality [Text](https://schema.org/Text)
        -   `addressCountry`: Country [Text](https://schema.org/Text)
        -   `postalCode` :  Post code [Text](https://schema.org/Text)
        -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional


### Example
```json
{
  give is soon!
 
}
