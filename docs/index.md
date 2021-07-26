The data models in [the SHOP4CF project](https://shop4cf.eu/) aim at ensuring interoperability of the SHOP4CF software components,
thus they model pieces of information exchanged among the components.

## Concept data models

The concept data models 
(i.e. the definitions of data entities, relationships, and attributes)
as well as further explanations of the data architecture
are described in Section 8 of the [SHOP4CF architecture](https://opencalls.shop4cf.eu/call/filePreview/50). 

Reviewing the data architecture may be necessary 
to understand this technical representation better.

## FIWARE representation

The common technical representation of most of the data models is 
FIWARE NGSI-LD
[[1]](https://fiware-datamodels.readthedocs.io/en/latest/ngsi-ld_howto/index.html)
[[2]](https://github.com/FIWARE/tutorials.Linked-Data).

### Conventions

Beyond the [FIWARE Smart Data Models guidelines](https://github.com/smart-data-models/data-models/blob/master/guidelines.md), 
SHOP4CF defines the following convention.

An entity identifier should be a [URN](https://en.wikipedia.org/wiki/Uniform_Resource_Name), 
built as `urn:ngsi-ld:<entity-type>:<factory-id>:<entity-id>`, 
for instance: `urn:ngsi-ld:Device:company-xyz:sensor-abc-12345`.

### Examples

The examples given below provide an overview 
of the FIWARE representation for the SHOP4CF concept data models.

Examples of the data models:

- Resources:
    - [Device](device.md)
    - [Material](material.md)
    - [Asset](asset.md)
    - [Person](person.md)
- [Task](task.md)
- [Process](process.md)
- [Alert](alert.md)
