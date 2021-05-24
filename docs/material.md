## Material

_(in progress)_

Example of a [PCB](https://en.wikipedia.org/wiki/Printed_circuit_board)
under manufacturing with the outcome of quality control 
is given below.

The concrete structure of the `status` attribute depends on 
a specific use case.  

```
{
    "id": "urn:ngsi-ld:Material:company-xyz:pcb-ncw498w",
    "type": "Material",
    "status": {
        "type": "StructuredValue",
        "value": {
            "qualityControlOutcome": "defective"
        },
        "metadata": {
            "timestamp": {
                "value": "2020-12-01T11:23:19Z"
            }
        }
    }
}
```
