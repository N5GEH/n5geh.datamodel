# BuildingRelated: 
It is composed of the following categories of Device Model in related to Building and inheritating properties belong to [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device)
- [Sensor](###Sensor)
- [Actuator](###Actuator)
- [Controller](###Controller)
- [PID](###PID)
- [RVK](###RVK)
### Sensor
A device that detects and responds to events or changes in the physical environment such as light, motion, or temperature changes. [SAREF](https://w3id.org/saref#Sensor)
-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `Sensor`.
-  `loggingInterval`: 
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `loI`
- `locatedIn`: Place of Sensor
     -  Attribute type: `Relationship`. object of [Building](x), [Room](x), and [Zone](x)
     -   Mandatory
- `readableName` : Human readable name of Device if it has
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `nam`
- `writable`: if sensor is able to be written
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: wri
 - `sampleRate`: Rate of sample values
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `sam`
- `sampleInterval`:Interval to send sample values
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: saI
- `listening`: if sensor is able to listen to the commands
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `lis`
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `hasChannel`: to define channel of sensors
     -  Attribute type: `Relationships`.  object of [Channel](x)
     -  (Angle, Frequency, Maqnititute, Rocf, TimeStamp)
     -   Optional
- `isMeasuredIn`: to track device model categories
     -  Attribute type: `Relationships`.  object of [Measurment](x)
     -  (Currency, Energy, Pressure, Power, Template, ..)
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
  "id": "urn:ngsi-ld:Sensor:01",
  "type": "Sensor",
  "readableName": {
    "type": "Property",
    "value": "KNX Gateway knxip://137.226.249.67:3671"
  },
  "controlProperty": {
    "type": "Relationship",
    "object": "urn:ngsi-ld:Property:Tempreture"
  },
  "soppurtedNetwork":{
    "type": "Property",
     "value": "KNX"
  },
  "loggingInterval":{
    "type": "Property",
    "value": "2s"
  },
   "locatedIn":{
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Building:01",
            "urn:ngsi-ld:Zone:02",
            "urn:ngsi-ld:Room:01"
        ]
    },
  "address": {
    "type": "Property",
    "value": {
      "type": "https://schema.org/PostalAddress",
      "addressLocality": "London",
      "addressCountry": "UK",
      "postalCode": "EC4N 8AF",
      "streetAddress": "25 Walbrook"
    }
  },
 "@context": [
        "https://raw.githubusercontent.com/Maliheh-Haghgoo/N5GEH/master/Core-Context.NGSILd.jsonld",  
        "https://raw.githubusercontent.com/Maliheh-Haghgoo/N5GEH/master/Device.jsonld" ]
 
}

```
### Actuator
 A device responsible for moving or controlling a mechanism or system. [Actuator](https://w3id.org/saref#Actuator).
-   `id` : Unique identifier.
-  `type` : Entity type. It must be equal to `Sensor`.
-  `hasSensor`: refer to connected Sensor
     -  Attribute type: `Relationship`. object of [Sensor](https://w3id.org/saref#Sensor)
     -   Optional
- `locatedIn`: Place of Actuator
     -  Attribute type: `Relationship`. object of [Building](x), [Room](x), and [Zone](x)
     -   Mandatory
- `readableName` : Human readable name of Device if it has
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `nam`
- `writable`: if sensor is able to be written
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: wri
 - `sampleRate`: Rate of sample values
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `sam`
- `sampleInterval`:Interval to send sample values
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: saI
- `listening`: if sensor is able to listen to the commands
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `lis`
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `hasChannel`: to define channel of sensors
     -  Attribute type: `Relationships`.  object of [Channel](x)
     -  (Angle, Frequency, Maqnititute, Rocf, TimeStamp)
     -   Optional
- `isMeasuredIn`: to track device model categories
     -  Attribute type: `Relationships`.  object of [Measurment](x)
     -  (Currency, Energy, Pressure, Power, Template, ..)
     -   Optional
-  `address` : Location of this device represented by a GeoJSON geometry of  type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
          -   `Type`: [Text](https://schema.org/PostalAddress)
          -   `addressLocality`: locality [Text](https://schema.org/Text)
         -   `addressCountry`: Country [Text](https://schema.org/Text)
         -  `postalCode` :  Post code [Text](https://schema.org/Text)
         -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional

### Example
```json
{
"id": "urn:ngsi-ld:Actuator:valve1",
"type": "Actuator",
"locatedIn":{
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Building:01",
            "urn:ngsi-ld:Zone:02"
        ]
    },
 "hasSensor": {
        "type": "Relationship",
        "object":"urn:ngsi-ld:Sensor:01"
    }
},
 "@context": [
        "https://raw.githubusercontent.com/Maliheh-Haghgoo/N5GEH/master/Core-Context.NGSILd.jsonld",  
        "https://raw.githubusercontent.com/Maliheh-Haghgoo/N5GEH/master/Device.jsonld" ]
 
}

```
### Controller
 A device responsible for controlling actuators and sensors 
-   `id` : Unique identifier.
-  `type` : Entity type. It must be equal to `Controller`.
-  `connectedSensor`: refer to te connected sensor
     -  Attribute type: `Relationship`. object of [Sensor](https://w3id.org/saref#Sensor)
     -   Mandatory
- `connectedActuator`: refer to te connected sensor
     -  Attribute type: `Relationship`. object of [Actuator](https://w3id.org/saref#Actuator)
     -   Mandatory
- `locatedIn`: Place of Controller
     -  Attribute type: `Relationship`. object of [Building](x), [Room](x), and [Zone](x)
     -   Mandatory
- `setValue` : set value to controller sensor 
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `seV`
- `ipAddress` : IP Address of controller 
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `ipA`
- `controllAsset` : IP Address of controller 
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `coA`
- `supplierName` : Name of supplier
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbrivia`tion: `suN
- `source` : source of data
     - Attribute type: `Property`. [Text](https://schema.org/Text)
     -   Optional
     -   Abbriviation: `sou`
- `writable`: if sensor is able to be written
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: wri
 - `sampleRate`: Rate of sample values
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `sam`
- `sampleInterval`:Interval to send sample values
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: saI
- `listening`: if sensor is able to listen to the commands
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `lis`
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `hasChannel`: to define channel of sensors
     -  Attribute type: `Relationships`.  object of [Channel](x)
     -  (Angle, Frequency, Maqnititute, Rocf, TimeStamp)
     -   Optional
- `isMeasuredIn`: to track device model categories
     -  Attribute type: `Relationships`.  object of [Measurment](x)
     -  (Currency, Energy, Pressure, Power, Template, ..)
     -   Optional
-  `address` : Location of this device represented by a GeoJSON geometry of  type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
          -   `Type`: [Text](https://schema.org/PostalAddress)
          -   `addressLocality`: locality [Text](https://schema.org/Text)
         -   `addressCountry`: Country [Text](https://schema.org/Text)
         -  `postalCode` :  Post code [Text](https://schema.org/Text)
         -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional

### Example
```json
{
 give it soon
}


```
### PID
 A controller device for buildiing related area. It uses properties of [Controller](### Controller) and [Device](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/Device)
-   `id` : Unique identifier.
-  `type` : Entity type. It must be equal to `PID`.
-  `kp`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `kp`
-  `ti`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `ti`
-  `td`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `td`
-  `higherLimit`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `hl`
 -  `lowerimit`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `ll`
 -  `reverseAction`: 
     -  Attribute type: `Property`. 
     -   Optional
     -   Abbriviation: `reA`
- `subCategory`: to track device model categories
     -  Attribute type: `Relationships`.  object of [SubCategory](x)
     -   Optional
- `isMeasuredIn`: to track device model categories
     -  Attribute type: `Relationships`.  object of [Measurment](x)
     -  (Currency, Energy, Pressure, Power, Template, ..)
     -   Optional
-  `address` : Location of this device represented by a GeoJSON geometry of  type point.
     -   Attribute type: `GeoProperty`. `geo:json`.
    -   Attribute metadata:
          -   `Type`: [Text](https://schema.org/PostalAddress)
          -   `addressLocality`: locality [Text](https://schema.org/Text)
         -   `addressCountry`: Country [Text](https://schema.org/Text)
         -  `postalCode` :  Post code [Text](https://schema.org/Text)
         -   `streetAddress`: Street address [Text](https://schema.org/Text)
    -   Optional

### Example
```json
{
 give it soon
}

```
### RVK

