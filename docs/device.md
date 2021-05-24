## Device

_(in progress)_

This model is based on [FIWARE Device](https://github.com/smart-data-models/dataModel.Device/blob/master/Device/doc/spec.md).

> An apparatus (hardware + software + firmware) intended to accomplish a particular task (sensing the environment, actuating, etc.). A Device is a tangible object which contains some logic and is producer and/or consumer of data. A Device is always assumed to be capable of communicating electronically via a network.

The required attributes are: `id`, `type`, `controlledProperty`.

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

An example entity reporting the position of AGV `agv-713` within the shop floor:

```
{
    "id": "urn:ngsi-ld:Device:company-xyz:agv-713",
    "type": "Device",
    "category": {
        "value": ["sensor"]
    },
    "controlledProperty": {
        "value": ["location"]
    },
    "relativePosition": {
        "value": [5.5, 21],
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
- `relativePosition` is "location of this device in a coordinate system according to its local emplacement".
We use it for coordinates within a shop floor.
