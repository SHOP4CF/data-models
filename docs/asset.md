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
    "state": {
        "type": "Property",
        "value": "available",
        "observedAt": "2020-12-01T11:23:19Z"
    },
    "@context": [
        "https://smartdatamodels.org/context.jsonld",
        "https://raw.githubusercontent.com/shop4cf/data-models/master/docs/shop4cfcontext.jsonld"
    ]
}
```

Attribute `state` is the state of the asset from an operational point of view.
Its concrete structure/value depends on a specific use case.
