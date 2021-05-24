## Task

_(in progress)_

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

```
{
    "id": "urn:ngsi-ld:Task:company-xyz:im834wyoen78w37",
    "type": "Task",
    "isDefinedBy": {
        "type": "Relationship",
        "value": "urn:ngsi-ld:TaskDefinition:company-xyz:hybrid-transportation-x"
    },
    "involves": {
        "type": "Relationship",
        "value": [
            "urn:ngsi-ld:Device:company-xyz:agv-5",
            "urn:ngsi-ld:Person:company-xyz:person-x",
            "urn:ngsi-ld:Material:company-xyz:pallet"
        ]
    },
    "happensAt": {
        "type": "Relationship",
        "value": [
            "urn:ngsi-ld:Location:company-xyz:storage",
            "urn:ngsi-ld:Location:company-xyz:production-line-6"
        ],
        "metadata": {
            "locationFunction": {
                "value": [
                    "source",
                    "target"
                ]
            }
        }
    },
    "workParameters": {
        "type": "StructuredValue",
        "value": {
            "materialAmount": 8
        }
    },
    "status": {
        "value": "pending",
        "metadata": {
            "timestamp": {
                "value": "2020-12-01T11:23:19Z"
            }
        }
    },
    "outputParameters": {
        "type": "StructuredValue",
        "value": {},
        "metadata": {
            "timestamp": {
                "value": "2020-12-01T11:23:19Z"
            }
        }
    }
}
```
