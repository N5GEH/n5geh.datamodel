## Building 
This entity contains a description of a Building. This entity is
associated with the vertical segments of smart homes

-   `id` : Unique identifier.
-   `type` : Entity type. It must be equal to `Building`.
-   `hasSensor`: See attribute `Relationship` , [Sensor](https://git.rwth-aachen.de/EBC/Team_BA/projects/n5geh/n5geh.datamodel/-/tree/master/DeviceModel/BuildingRelated###%20Sensor)
      -  Optional but recommended to optimize queries. 
-   `floorsAboveGround` : See attribute `Property` 
      -  Optional but recommended to optimize queries.
-   `floorsBelowGround` : See attribute `Property` 
      -  Optional but recommended to optimize queries.
-  `dataProvider` : The provider of the device.
     -   Attribute Type: `Property`. [Provider](http://schema.org/provider)
     -   Normative References:
        [https://schema.org/provider](https://schema.org/provider)
     -   Optional
-   `hasRoom` : See attribute `Relationship` 
      -  Optional but recommended to optimize queries.
-   `hasFloor` : See attribute `Relationship` 
      -  Optional but recommended to optimize queries.
-   `hasZone` : See attribute `Relationship` 
      -  Optional but recommended to optimize queries.
-   `category` : See attribute `Property` ,[Text](https://schema.org/Text)
      -  Optional but recommended to optimize queries.
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
-   `owner` : The owners of a Device.
     -   Attribute type: Property. List of references to [Person](http://schema.org/Person)
        or [Organization](https://schema.org/Organization) or List of URIs.
    -   Optional
-  `description` : Device's description.
     -   Attribute type: Property. [Text](https://schema.org/Text)
     -    [description](https://schema.org/description)
     -   Optional
## Examples

```json
{
  "id": "urn:ngsi-ld:Building:01",
    "type": "Building",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "hasRoom":{
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Room:01",
            "urn:ngsi-ld:Room:02"
        ]
    },
    "hasFloor":{
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Floor:01",
            "urn:ngsi-ld:Floor:02"
        ]
    },
    "hasZone":{
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Zone:01",
            "urn:ngsi-ld:Zone:02",
            "urn:ngsi-ld:Zone:03"
        ]
    },
    "category": {
        "type": "Property",
        "value": [
            "house"
        ]
    },
    "address": {
        "type": "Property",
        "value": {
            "@type": "https://schema.org/PostalAddress",
            "addressLocality": "London",
            "addressCountry": "UK",
            "postalCode": "EC4N 8AF",
            "streetAddress": "25 Walbrook"
        }
    },
    "owner": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Person:cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",
            "urn:ngsi-ld:Organization:1be9cd61-ef59-421f-a326-4b6c84411ad4"
        ]
    },
"decription": {
        "type": "Property",
        "value": "Multi-tenant office block"
    }
},
  "@context": [
    "https://raw.githubusercontent.com/mhg-local/N5GEH/master/Core-Context",
    "https://raw.githubusercontent.com/mhg-local/N5GEH/master/Building.jsonld"
  ]
}


```
