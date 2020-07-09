# Device
This entity contains a harmonised description of a generic device model and is therefore applicable to all IoT segments and related IoT applications. The Device includes an optional hierarchical structure that allows device types to be grouped in a flexible way.

-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `Device`.
-   `source` : A sequence of characters giving the source of the entity data.
    -   Attribute type: Property. [Text](https://schema.org/Text) or [URL](https://schema.org/URL)
    -   Optional
 -   `controlledProperty` : See attribute from [SAREF](https://w3id.org/saref#Property). Optional but recommended to optimize queries.
     -   Attribute type :`Property`
     - Value: [Text](https://schema.org/Text)
     -   Optional    
     -   (temperature, humidity, light, motion, fillingLevel,  occupancy, power, pressure, smoke, energy, airPollution,  noiseLevel, weatherConditions, precipitation, windSpeed,  windDirection, atmosphericPressure, solarRadiation, depth, pH,  conductivity, conductance, tss, tds, turbidity, salinity,  orp, cdom, waterPollution, location, speed, heading,  weight, waterConsumption, gasComsumption,  electricityConsumption, soilMoisture, trafficFlow,  eatingActivity, milking, movementActivity). 
     -  Attribute metadata:
        - isMeasuredIn: 
            -  Attribute type: `Property`. [isMeasuredIn](https://w3id.org/saref#isMeasuredIn)
            -  Value: [Text](https://schema.org/Text)
            -   Optional
-   `hasDeviceModel` :
    -  Attribute type : `Relationship` List of [DeviceModel](https://github.com/N5GEH/SARGON/tree/master/Readme/DeviceModel)
    -  Optional
-  `controlledAsset` : The asset(s) (building, object, etc.) controlled by the
    device.
     -   Attribute type: `Property` . 
    -  Value: [Text](https://schema.org/Text) or Reference(s) to another entity.
    -   Optional
    -   Abbriviation : `coA`
-   `isUsedfor` : lList of [Commodity](https://w3id.org/saref#Commodity)
    -   Attribute type: `Property` .
     -  Value: [Text](https://schema.org/Text) or Reference(s) to another entity.
    -   Optional
    -   Abbriviation : `isU`
-  `inRoom` : link to object of rooms in a building

    -   Attribute type: `Relationship` .
    -  Value: object of  of [Room]() or Reference(s)
    -   Optional
    -   Abbriviation : `inR`
-   `serialNumber` : 
     -   Attribute type:`Property`.
     -  Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `seN`
-   `supplierName` : 
     -   Attribute type:`Property`.
     - Value: [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `suN`
-   `dataProvider` :  The provider of the device, [Provider](http://schema.org/provider)
     -   Attribute Type: `Property`. 
     - Value: [Text](https://schema.org/Text)
     -   Normative References:
        [https://schema.org/provider](https://schema.org/provider)
     -   Optional
     -   Abbriviation: `daP`
-   `ipAddress` : The IP address of the device. It can be a comma separated list
    of values if the device has more than one IP address.
     -   Attribute type: `Property`.
     -   VAlue : [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `ipA`
-   `supportedProtocol` : 
     -   Attribute type: `Property`.
     -   VAlue : [Text](https://schema.org/Text)
     -   Optional
     -  (ul20, mqtt, lwm2m, http, websocket, onem2m,  sigfox, lora, nb-iot, ec-gsm-iot, lte-m, cat-m, 3g,  grps
-    `location` : Location of this device represented by a GeoJSON geometry of
    type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
     -   Normative References:  [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    -   Optional.
-  `description` : Device's description.
     -   Attribute type: `Property`.
     - VAlue: [Text](https://schema.org/Text)
     -   Normative References:
        `https://uri.etsi.org/ngsi-ld/description` equivalent to [description](https://schema.org/description)
     -   Optional
-  `dateInstalled` : A timestamp which denotes when the device was installed
    (if it requires installation).
     -   Attribute type: `Property`.
     -  Value: [DateTime](https://schema.org/DateTime)
     -   Optional

-  `hasState` : State of this device from an operational point of view. Its value can be vendor dependent.See attribute from [SAREF](https://w3id.org/saref#State)
     -   Type: `Property`.
     -   Value : [Text](https://schema.org/Text)
     - (Close, MultiLevel, Off, On, Open, Start, Stop) 
     -   Optional
-  `isMeasuredIn` :A relationship identifying the unit of measure used for a certain entity. [SAREF](https://w3id.org/saref#isMeasuredIn)
     -   Type: `Property`.
     -  Value: [Text](https://schema.org/Text)
     -   Optional
-  `hasCommand` : directive that a device must support to perform a certain function. A command may act upon a state, but does not necessarily act upon a state. For example, the ON command acts upon the ON/OFF state, but the GET command does not act upon any state, it simply gives a directive to retrieve a certain value. We propose here a list of commands that are relevant for the purpose of SAREF, but this list can be extended.from [SAREF](https://w3id.org/saref#Command)
     -   Type: `Property` ,
     -  Value:  [Text](https://schema.org/Text)
     -   Optional
     - (Set level, Close, Notify, Off, Stop, Get,Toggle, Pause, Step down, Step up , Function, On , Open, Start, GetCurrentMeteringData, GetSensing, SetAbsoluteLevel, SetRelativeLevel, Start, Stop,...)
-  `hasFunction` :.See attribute from [SAREF](https://w3id.org/saref#Function)
     -   Type: `Property`.
     -   Value: [Text](https://schema.org/Text) 
     -   Optional
     -   (sensing, actuating, Event, OnOff, OpenClose, SatrtStop, TopPosition, Metering)
-   `owner` : The owners of a Device.
     -   Attribute type: `Relationship`.
     - Value: object of [Person](http://schema.org/Person) or [Organization](https://schema.org/Organization) or List of URIs.
    -   Optional
-  `createdAt` : Entity's creation timestamp.
     -   Attribute type: `Property`. 
     -  Value: [DateTime](https://schema.org/DateTime)
     -   Read-Only. Automatically generated.
     -   abbriviation : `crA`
-  `modifiedAt` : Last update timestamp of this entity.
     -   Attribute type: `Property`. 
     -  Value: [DateTime](https://schema.org/DateTime)
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
        "type": "Property",
        "Value": "Tempreture",
        "isMeasuredIn": {
            "type": "Property",
            "value": "celsius"
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
        "type": "Property",
        "object": "open"
    },
    "@context": [
        "https://schema.lab.fiware.org/ld/context",
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"
    ]
}
```



