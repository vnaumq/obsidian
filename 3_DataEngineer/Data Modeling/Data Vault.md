[[Data Modeling]]

## What is a data vault?

A **data vault** is a data modeling design pattern used to build a data warehouse for enterprise-scale analytics. The data vault has three types of entities: **hubs,** **links,** and **satellites.**

**Hubs** represent core business concepts, **links** represent relationships between hubs, and **satellites** store information about hubs and relationships between them.

The data vault is a data model that is well-suited to organizations that are adopting the lakehouse paradigm
![[data-vault-modeling-image.png]]

## Data vault modeling: Hubs, links, and satellites

- **Hubs** - Each hub represents a core business concept, such as they represent Customer Id/Product Number/Vehicle identification number (VIN). Users will use a business key to get information about a Hub. The business key may have a combination of business concept ID and sequence ID, load date, and other metadata information.
- **Links** - Links represent the relationship between Hub entities.
- **Satellites** - Satellites fill the gap in answering the missing descriptive information on core business concepts. Satellites store information that belongs to Hub and relationships between them.

A few additional things to keep in mind:

- A satellite cannot have a direct connection to another satellite.
- A hub or link may have one or more satellites.

## Data vault benefits

- Agile
- Structured, with flexibility for refactoring
- Extremely scalable, up to PBs volumes
- Uses patterns that support ETL code generation
- Familiar architecture: data layers, ETL, star schemas