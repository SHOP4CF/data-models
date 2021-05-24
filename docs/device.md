## Device

_(in progress)_

This model is based on [FIWARE Device](https://github.com/smart-data-models/dataModel.Device/blob/master/Device/doc/spec.md).

Two examples are given below: a sensor and an AGV.

### Sensor

An example sensor with serial number "9845A", 
measuring electrical current on a busbar (kind of an electical conductor) no. 789, 
with the current value of 11.54 A:

```
{
    "id": "urn:ngsi-ld:Device:company-xyz:sensor-12345",
    "type": "Device",
    "source": {
        "value": "urn:ngsi-ld:Device:company-xyz:busbar-789"
    }
    "category": {
        "value": ["sensor"]
    },
    "serialNumber": {
        "value": "9845A"
    },
    "controlledProperty": {
        "value": ["electricCurrent"]
    },
    "value": {
        "value": 11.54,
        "metadata": {
            "timestamp": {
                "value": "2020-12-01T11:23:19Z"
            }
        }
    },
    "deviceState": {
        "value": "ok"
    }
}
```

Notes:
- `controlledProperty=electricCurrent` is our extensions of the origin data model.  
- Ampere is the unit for electric current in the metric system,
so this unit is not explicit in the JSON representation.

### AGV

...
