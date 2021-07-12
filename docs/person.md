## Person

Person is a human (human worker) who can perform a step in manufacturing.

```json
{
    "id": "urn:ngsi-ld:Person:company-xyz:worker-xqi7wnx",
    "type": "Person",
    "firstName": {
        "type": "Property",
        "value": "John"
    },
    "lastName": {
        "type": "Property",
        "value": "Smith"
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
