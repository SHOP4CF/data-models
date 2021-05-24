_This is work in progress!_

The data models in [the SHOP4CF project](https://shop4cf.eu/) focus on information exchanged among SHOP4CF components.

## Concept data models

The concept data models 
(i.e. the definitions of data entities, relationships, and attributes)
as well as further explanations of the data architecture
are described in Section 8 of the [SHOP4CF architecture](https://opencalls.shop4cf.eu/call/filePreview/50). 

Reviewing the data architecture may be necessary 
to understand this technical representation better.

## FIWARE representation

The common technical representation of most of the data models is 
[FIWARE NGSI](https://fiware-datamodels.readthedocs.io/en/latest/howto/index.html).  

### Conventions

Beyond the [FIWARE Smart Data Models guidelines](https://github.com/smart-data-models/data-models/blob/master/guidelines.md), 
SHOP4CF defines the following convention.

An entity identifier should be a [URN](https://en.wikipedia.org/wiki/Uniform_Resource_Name), 
built as `urn:ngsi-ld:<entity-type>:<factory-id>:<entity-id>`, 
for instance: `urn:ngsi-ld:Device:company-xyz:sensor-abc-12345`.

### Examples

The examples given below provide an overview 
of the FIWARE representation for the SHOP4CF concept data models.

**Warning! These examples are in the NGSI v2 normalised format. 
Please note the SHOP4CF project chose to adopt the NGSI-LD format, so the examples need to be adjusted.**

Examples of the data models:

- Resources:
    - [Device](device.md)
    - [Material](material.md)
- [Task](task.md)
- [Alert](alert.md)