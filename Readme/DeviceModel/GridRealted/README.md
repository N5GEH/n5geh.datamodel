# GridRelated: 
It is composed of the following categories of Device Model in related to Building and inheritating properties belong to [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device)
-   Convertor
    - [AC-DC](https://github.com/N5GEH/SARGON/blob/master/Readme/DeviceModel/GridRealted/README.md#ac-dc)
-   Meter
    - [EnergyMeter](###Energy)
    - [PMU](###PMU)
    - [PowerMeter](###Power)
-   Storage
    - [Batery](###Batery)
### AC-DC
Convertor in AC-DC network, according to IEC 61850 standard. It can inherit properties of [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device)
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `ACDC`.
-  `logicalNode'`: 
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `loN`
- `primaryCurrent`: 
     -  Attribute type: `Property`. 
     -   Mandatory
     -   Abbriviation: `prC`
- `primaryVoltage` :
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `prV`
- `secondaryCurrent`:
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `seC`
 - `secondaryVoltage`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `secV`
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
-  `name`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `prV`
-  `listening`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `lis`    
-  `sampleRate`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `sam`
-  `writable`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `wri`
-  `sampleInterval`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `saI`   
-  `loggingInterval`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `loI`
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `hasChannel`: 
     -  Attribute type: `Relationships`.  object of [Channel](x)
     -   Optional
- `isMeasuredIn`: Unit of measurment
     -  Attribute type: `Relationships`.  object of [Measurment](x)
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
-  `sampleInterval`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `saI`   
-  `loggingInterval`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `loI`
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `hasChannel`: 
     -  Attribute type: `Relationships`.  object of [Channel](x)
     -   Optional
- `isMeasuredIn`: Unit of measurment
     -  Attribute type: `Relationships`.  object of [Measurment](x)
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
     -   Optional
     -   (eneryEfficiency)
-  `accuracy`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   string
-  `activePower`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `acP`
-  `reactivePower`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `reP`
-  `controlledProperty`: 
     -  Attribute type: `Relationships` to the object of  [Property](https://w3id.org/saref#Property)
     -   Optional
-  `hasFunction`: 
     -  Attribute type: `Relationships` to the object of  [Function](https://w3id.org/saref#Function)
     -   Optional
-  `hasState`: 
     -  Attribute type: `Relationships` to the object of  [State](https://w3id.org/saref#State)
     -   Optional
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
    -   Optional


### Example
```json
{
  give is soon!
 
}
