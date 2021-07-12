## Asset

Asset is a tangible item that is needed for a manufacturing process
but is neither a material nor a device.
It may be a tool or an element of a device.

For instance, a gripper for a robot (i.e. for a device) or a hammer for a person are assets.

Example of a hammer is given below.

```json
{
    "id": "urn:ngsi-ld:Asset:company-xyz:hammer-xqi7wnx",
    "type": "Asset",
    "description": {
        "type": "Property",
        "value": "Red hammer no. 58"
    },
    "status": {
        "type": "Property",
        "value": "available",
        "observedAt": "2020-12-01T11:23:19Z"
    },
    "@context": [
        "https://smartdatamodels.org/context.jsonld"
    ]
}
```

The concrete structure of the `status` attribute depends on 
a specific use case.  
