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
    "isSpecifiedBy": {
        "type": "Property",
        "value": [
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:ResourceSpecification:company-xyz:any-operator"
            },
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:ResourceSpecification:company-xyz:operator-with-high-voltage-privileges"
            }
        ]
    },
    "@context": [
        "https://smartdatamodels.org/context.jsonld",
        "https://raw.githubusercontent.com/shop4cf/data-models/master/docs/shop4cfcontext.jsonld"
    ]
}
```
Further notes on the attributes:
- `state` is the state of the person from an operational point of view.
Its concrete structure/value depends on a specific use case.
- `isSpecifiedBy` references a set of Resource Specifications that the Person fulfills
(and that do not rather live in Context Broker)
