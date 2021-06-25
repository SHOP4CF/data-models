## Task

Task is a manufacturing operation that is to be executed. 
This data model is considered indivisible, although in the real world, it may be a complex multi-step operation.
Task references Task Definition that specifies how to perform the work in detail.

Example for a task is given below. 
The task consists of the two steps:
- AGV #5 to move 8 pallets from the storage to production line #6,
- then person X to move the pallets onto the line.

It is assumed that there is a Task Definition already defined 
that describes such a hybrid transportation work, 
but yet without parameter values such as how, how many, what, where from, where to.

```json
{
    "id": "urn:ngsi-ld:Task:company-xyz:im834wyoen78w37",
    "type": "Task",
    "isDefinedBy": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:TaskDefinition:company-xyz:hybrid-transportation-x"
    },
    "involves": {
        "type": "Property",
        "value": [
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Device:company-xyz:agv-5"
            },
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Person:company-xyz:person-x"
            },
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Material:company-xyz:pallet"
            }
        ]
    },
    "happensAt": {
        "type": "Property",
        "value": [
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Location:company-xyz:storage",
                "locationFunction": {
                    "type": "Property",
                    "value": "source"
                }
            },
            {
                "type": "Relationship",
                "object": "urn:ngsi-ld:Location:company-xyz:production-line-6",
                "locationFunction": {
                    "type": "Property",
                    "value": "target"
                }
            }
        ]
    },
    "workParameters": {
        "type": "Property",
        "value": {
            "materialAmount": 8
        }
    },
    "status": {
        "type": "Property",
        "value": "pending",
        "observedAt": "2020-12-01T11:23:19Z"
    },
    "outputParameters": {
        "type": "Property",
        "value": {
            "materialsAlreadyTransported": 0,
            "percentageCompleted": 0
        },
        "observedAt": "2020-12-01T11:23:19Z"
    },
    "@context": [
        "https://smartdatamodels.org/context.jsonld"
    ]
}
```

Required attributes are: `id`, `type`, `isDefinedBy`, `status`.

Further notes on the attributes:
- `isDefinedBy` references a Task Definition (which does not rather live in Context Broker)
- `involves` references a set of involved resources
- `happensAt` references a set of involved locations (which do not rather live in Context Broker)
- `locationFunction` within `happensAt` is optional, an its values are use-case specific
- `workParameters` are use-case specific and are set by the party that orders the task
- `status` represents the current execution status with the following allowed values:
`pending`, `assigned`, `inProgress`, `completed`, `paused`, `suspended`, `failed`
- `outputParameters` are use-case specific and are usually set and updated by the party
that executes the task
