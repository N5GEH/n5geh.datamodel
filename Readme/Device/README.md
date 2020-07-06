# Device
This entity contains a harmonised description of a generic device model and is therefore applicable to all IoT segments and related IoT applications. The Device includes an optional hierarchical structure that allows device types to be grouped in a flexible way.

-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `Device`.
-   `source` : A sequence of characters giving the source of the entity data.
    -   Attribute type: Property. [Text](https://schema.org/Text) or [URL](https://schema.org/URL)
    -   Optional
 -   `controlledProperty` : See attribute `Relationship` from [SAREF](https://w3id.org/saref#Property). Optional but recommended to optimize queries.
     -   Attribute type :`Relationship`
     -   Optional    
     -   (temperature, humidity, light, motion, fillingLevel,  occupancy, power, pressure, smoke, energy, airPollution,  noiseLevel, weatherConditions, precipitation, windSpeed,  windDirection, atmosphericPressure, solarRadiation, depth, pH,  conductivity, conductance, tss, tds, turbidity, salinity,  orp, cdom, waterPollution, location, speed, heading,  weight, waterConsumption, gasComsumption,  electricityConsumption, soilMoisture, trafficFlow,  eatingActivity, milking, movementActivity). 
     -    Attribute metadata:
          -   `measurementValue`: For certain measurement types the measurement value.
               -    type: `Property`
               -    Value: `Number`
          -   `measurementUnit`: For certain measurement unit according to the selected control property.
               -    type: `Property`
               -    Value: `String`
-   `hasDeviceModel` :
    -  Attribute type : `Relationship` List of [DeviceModel](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/DeviceModel)
    -  Optional
-  `controlledAsset` : The asset(s) (building, object, etc.) controlled by the
    device.
     -   Attribute type: `Relationship` . List of [Text](https://schema.org) or Reference(s) to another entity.
    -   Optional
    -   Abbriviation : `coA`
-   `isUsedfor` : link to commodity objects

    -   Attribute type: `Relationship` . List of [Commodity](https://w3id.org/saref#Commodity) or Reference(s) to another entity.
    -   Optional
    -   Abbriviation : `isU`
-  `inRoom` : link to object of rooms in a building

    -   Attribute type: `Relationship` . List of [Room]() or Reference(s) to another entity.
    -   Optional
    -   Abbriviation : `inR`
-   `serialNumber` : 
     -   Attribute type:`Property`. List of [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `seN`
-   `supplierName` : 
     -   Attribute type:`Property`. List of [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `suN`
-   `dataProvider` :  The provider of the device.
     -   Attribute Type: `Property`. [Provider](http://schema.org/provider)
     -   Normative References:
        [https://schema.org/provider](https://schema.org/provider)
     -   Optional
     -   Abbriviation: `daP`
-   `ipAddress` : The IP address of the device. It can be a comma separated list
    of values if the device has more than one IP address.
     -   Attribute type: `Property`. List of [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `ipA`
-   `supportedProtocol` : 
-    `location` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
     -   Normative References:  [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    -   Optional.
-  `description` : Device's description.
     -   Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Normative References:
        `https://uri.etsi.org/ngsi-ld/description` equivalent to [description](https://schema.org/description)
     -   Optional
-  `dateInstalled` : A timestamp which denotes when the device was installed
    (if it requires installation).
     -   Attribute type: `Property`. [DateTime](https://schema.org/DateTime)
     -   Optional

-  `hasState` : State of this device from an operational point of view. Its value can be vendor dependent.See attribute from [SAREF](https://w3id.org/saref#State)
     -   Type: `Relationship` , [State](https://w3id.org/saref#State)
     -   Value : From SAREF (Close, MultiLevel, Off, On, Open, Start, Stop) 
     -   Optional
-  `isMeasuredIn` :.See attribute from [SAREF](https://w3id.org/saref#Measurment)
     -   Type: `Relationship` , [Measurment](https://w3id.org/saref#Measurment)
     -   Optional
     -   Attribute metadata:
         -   `measurementUnit`: For certain measurement unit acording to the selected the measurement domain.
              -    type: `Property`
              -    Value: `String`
-  `hasCommand` :.See attribute from [SAREF](https://w3id.org/saref#Command)
     -   Type: `Relationship` , [Command](https://w3id.org/saref#Command)
     -   Optional
     -   (Close, GetCurrentMeteringData, GetSensing, Notify, On, Off, Open, Close, Pause, SetAbsoluteLevel, SetRelativeLevel, Start, Stop,...)
-  `hasFunction` :.See attribute from [SAREF](https://w3id.org/saref#Function)
     -   Type: `Relationship` , [Function](https://w3id.org/saref#Function)
     -   Optional
     -   (sensing, actuating, Event, OnOff, OpenClose, SatrtStop, TopPosition, Metering)
-   `owner` : The owners of a Device.
     -   Attribute type: `Relationship`. List of references to [Person](http://schema.org/Person)
        or [Organization](https://schema.org/Organization) or List of URIs.
    -   Optional
-  `createdAt` : Entity's creation timestamp.
     -   Attribute type: `Property`. [DateTime](https://schema.org/DateTime)
     -   Read-Only. Automatically generated.
     -   abbriviation : `crA`
-  `modifiedAt` : Last update timestamp of this entity.
     -   Attribute type: `Property`. [DateTime](https://schema.org/DateTime)
     -   Read-Only. Automatically generated.
     -   Abbriviation : `moA`


**Note**: JSON Schemas are intended to capture the data type and associated
constraints of the different Attributes, regardless their final representation
format in NGSI-LD.

## Examples

### Normalized Example

```json
{
    "id": "urn:ngsi-ld:Device:device-9845A",
    "type": "Device",
 "controlledAsset": {
        "type": "Relationship",
        "object": ["urn:ngsi-ld::wastecontainer-Osuna-100"]
    },
    "serialNumber": {
        "type": "Property",
        "value": "9845A"
    },
    "controlledProperty": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:Property:Tempreture",
        "measurementUnit": {
            "type": "Property",
            "value": "celsius"
        },
        "measurementValue": {
            "type": "Property",
            "value": 1
        }
    },
    "owner": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:Person:XY"
    },
    "ipAddress": {
        "type": "Property",
        "value": ["192.14.56.78"]
    },
    "hasState": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:State:open"
    },
    "@context": [
        "https://schema.lab.fiware.org/ld/context",
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"
    ]
}
```



