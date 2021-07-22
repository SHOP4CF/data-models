## Process

Process models a set of manufacturing operations to be executed
(i.e. [Tasks](task.md)).
Process references Process Definition that specifies how to perform the work in detail.

Process is not executed directly,
but its constituent Tasks are executed by concrete agents.

### Example #1 - Creating Process   

A party requesting unloading supplies creates Process
that specifies an existing Process Definition and some work parameters:

```json
{
    "id": "urn:ngsi-ld:Process:company-xyz:nc847rc8347nc3",
    "type": "Process",
    "isDefinedBy": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:ProcessDefinition:company-xyz:unloading-supplies"
    },
    "workParameters": {
        "type": "Property",
        "value": {
            "truckId": 838
        }
    },
    "status": {
        "type": "Property",
        "value": "pending",
        "observedAt": "2020-12-01T11:23:19Z"
    },
    "@context": [
        "https://smartdatamodels.org/context.jsonld",
        "https://raw.githubusercontent.com/shop4cf/data-models/master/docs/shop4cfcontext.jsonld"
    ]
}
```

Required attributes are: `id`, `type`, `isDefinedBy`, `status`.

Further notes on the attributes:
- `isDefinedBy` references a Process Definition (which does not rather live in Context Broker)
- `workParameters` are use-case specific, as in [Task](task.md)
- `status` represents the current execution status, as in [Task](task.md)

### Example #2 - Process starts

Another party responsible for ordering concrete Tasks (e.g. a scheduler)
creates relevant Tasks for that Process.
It also updates the Process by changing its `status`
and adding references to the Tasks:

```json
{
    "id": "urn:ngsi-ld:Process:company-xyz:nc847rc8347nc3",
    "type": "Process",
    "isDefinedBy": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:ProcessDefinition:company-xyz:unloading-supplies"
    },
    "workParameters": {
        "type": "Property",
        "value": {
            "truckId": 838
        }
    },
    "status": {
        "type": "Property",
        "value": "assigned",
        "observedAt": "2020-12-01T11:30:21Z"
    },
    "outputParameters": {
        "type": "Property",
        "value": {
            "riskApproved": true,
            "riskReport": "https://example.com/report-123"
        },
        "observedAt": "2020-12-01T11:23:19Z"
    },
    "isComposedOf": {
        "type": "Property",
        "value": [
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Task:company-xyz:unload-track-n283xy283"
            },
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Task:company-xyz:move-supplies-to-storage-xnw7x8n4"
            },
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Task:company-xyz:organise-supplies-on-shelves-ian73xwxn"
            }
        ],
        "observedAt": "2020-12-01T11:30:21Z"
    },
    "@context": [
        "https://smartdatamodels.org/context.jsonld",
        "https://raw.githubusercontent.com/shop4cf/data-models/master/docs/shop4cfcontext.jsonld"
    ]
}
```

Further notes:
- `outputParameters` are use-case specific, as in [Task](task.md)
- `isComposedOf` references a set of constituent Tasks
