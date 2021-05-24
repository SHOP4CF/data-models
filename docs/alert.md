## Alert

_(in progress)_

This model is based on [FIWARE Alert](https://github.com/smart-data-models/dataModel.Alert/blob/master/Alert/doc/spec.md).

Example for maintenance alert for skid (car-body platform) no. 12345:

```
{
    "id": "urn:ngsi-ld:Alert:company-xyz:pred-maint-3x29md89",
    "type": "Alert",
    "category": {
        "value": "predictiveMaintenance"
    },
    "subCategory": {
        "value": "skid"
    },
    "validTo": {
        "value": "2017-01-02T10:25:55.00Z"
    },
    "description": {
        "value": "Skid no. 12345 needs maintenance"
    },
    "location": {
        "type": "geo:json",
        "value": {
            "type": "Point",
            "coordinates": [-3.712247222222222, 40.423852777777775]
        }
    },
    "dateIssued": {
        "type": "DateTime",
        "value": "2017-01-02T09:25:55.00Z"
    },
    "alertSource": {
        "value": "urn:ngsi-ld:Asset:skid-12345"
    },
    "validFrom": {
        "type": "DateTime",
        "value": "2017-01-02T09:25:55.00Z"
    },
    "severity": {
        "value": "high"
    }
}
```
