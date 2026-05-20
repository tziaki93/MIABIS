# Ontology for Biobanking (OBIB)

> **Version:** 2023-04-05  
> **IRI:** `http://purl.obolibrary.org/obo/obib.owl`  
> **License:** [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

---

## Overview

The **Ontology for Biobanking (OBIB)** is an OWL ontology for the semantic annotation and formal modeling of the activities, contents, and administration of biobanks. Biobanks are facilities that collect and store biological specimens (e.g., blood, tissues, bodily fluids) along with associated annotation and clinical data.

OBIB is built on the **Basic Formal Ontology (BFO)** as its upper ontology and is derived from a curated subset of the **Ontology for Biomedical Investigation (OBI)**. It is developed in compliance with [OBO Foundry](http://obofoundry.org/) principles. The first version of OBIB was produced by merging two earlier biobank-related ontologies: **OMIABIS** and the **UPenn Biobank Ontology**.

---

## Conceptual Model

The ontology was designed using **OntoUML**, a conceptual modeling language based on the Unified Foundational Ontology (UFO). The diagram below illustrates the core structure of OBIB.

![OBIB OntoUML Diagram](ontouml_diagram.png)

### OntoUML Stereotypes Used

| Stereotype | Meaning |
|---|---|
| `<<kind>>` | A rigid, fundamental type of entity (e.g., Specimen) |
| `<<role>>` | An anti-rigid type defined by a relational context (e.g., Specimen Donor playing a role) |
| `<<relator>>` | A mediating entity that grounds a relation between two or more entities (e.g., Event) |
| `<<category>>` | An abstract, rigid type that applies across multiple kinds (e.g., anatomical site) |
| `<<datatype>>` | A structured data value |
| `<<nominalquality>>` | An identifier or code |
| `<<enumeration>>` | A fixed set of allowed values |
| `<<quantity>>` | A measurable quantity |
| `<<mediation>>` | A relation through which a relator mediates between entities |

---

## Core Classes

### Specimen Donor (`OBIB_0000728`) — `<<role>>`

> *A Homo sapiens who contributes a specimen.*

A person bearing the role of donor in the context of specimen collection. The Specimen Donor **participates in** one or more Events and **donates** one or more Specimens.

| Attribute | ID | Type | Definition |
|---|---|---|---|
| specimen donor ID | OBIB_0002045 | `<<nominalquality>>` | Unique ID code of the sample donor within the sample collection |
| donor's biological sex | OBIB_0000483 | `<<enumeration>>` | Biological sex of the person who bears the role of donor |
| donor's date of birth | OBIB_0000482 | `<<datatype>>` | Calendar date on which a particular donor of a specimen was born |
| dataset type | OBIB_0002046 | `<<enumeration>>` | Data categories available or linkable to the donor (e.g., Clinical, Genomic, Proteomic, Metabolomic, Radiological image, etc.) |

---

### Event (`OBIB_0002047`) — `<<relator>>`

> *Something that happens in a given place and time that is related to the sample and/or sample donor.*

An Event mediates between a Specimen Donor and a Specimen. It captures contextual information about the circumstances of specimen collection or related occurrences.

| Attribute | ID | Type | Definition |
|---|---|---|---|
| event ID | OBIB_0002048 | `<<nominalquality>>` | Random ID for each event, created by the database implementation |
| event date and time | OBIB_0002049 | `<<datatype>>` | Expression of both date and time that an event has happened or will happen |
| age at event | OBIB_0002050 | `<<quantity>>` | The age of an individual at the time of an event |
| age at event unit | OBIB_0002051 | `<<enumeration>>` | Unit defining age at event (years, months, weeks, days, gestational weeks) |

---

### Specimen (`OBI_0100051`) — `<<kind>>`

> A biological specimen collected from a donor.

The central entity of the biobank. A Specimen is **collected at** an Event, is **donated** by a Specimen Donor, and is associated with an **anatomical site** via a mediation relation.

| Attribute | ID | Type | Definition |
|---|---|---|---|
| specimen ID | OBIB_0000721 | `<<nominalquality>>` | A proper name that identifies a specimen, usually as a label on the specimen cassette |
| sample type | OBIB_0002014 | `<<datatype>>` | Type of biological specimen (e.g., Plasma, Serum, Whole blood, Tissue (fixed), RNA, DNA, etc.) |
| storage temperature setting | OBIB_0000689 | `<<datatype>>` | Temperature setting inside a container participating in a storage process (e.g., −80 °C, liquid nitrogen, room temperature) |
| sample creation date and time | OBIB_0002016 | `<<datatype>>` | Date and time the sample was created (ISO 8601 format; partial values allowed) |
| sample content diagnosis | OBIB_0002022 | `<<datatype>>` | ICD-10 or ORPHA code describing the diagnosis of the sample content (e.g., presence of carcinogenic material) |
| use and access conditions | OBIB_0002023 | `<<datatype>>` | Conditions that may change the availability of the donated samples (e.g., Commercial use, Collaboration, Specific research use, Genetic data use) |
| sample source | OBIB_0002024 | `<<datatype>>` | The source from which the samples were collected or isolated (Human, Animal, Environment) |

---

### Anatomical Site (`OBIB_0002017`) — `<<category>>`

> *Name of the body site where the specimen was obtained from, such as a specific organ or tissue.*

The anatomical site is linked to a Specimen through a **mediation** relation. It is described either via a controlled ontology (coded) or as free text when precise coding is not available. It may consist of one or more component descriptions.

| Attribute | ID | Type | Definition |
|---|---|---|---|
| anatomical site ontology | OBIB_0002015 | `<<datatype>>` | Name of the ontology used for describing the anatomical source (e.g., ICD-O-3 topography) |
| anatomical site ontology version | OBIB_0002018 | `<<datatype>>` | Version of the selected ontology for anatomical site |
| anatomical site ontology code | OBIB_0002019 | `<<nominalquality>>` | Anatomical site code from the selected ontology version |
| anatomical site ontology description | OBIB_0002020 | `<<datatype>>` | Description corresponding to the selected ontology code |
| anatomical site free text | OBIB_0002021 | `<<datatype>>` | Free-text explanation of the anatomical site when unknown or insufficiently described (ICD-10 or ORPHA classification codes recommended) |

---

## Relations

| Relation | Domain | Range | Cardinality | Description |
|---|---|---|---|---|
| `participates in` | Specimen Donor | Event | 1..* → 1..* | A donor participates in one or more events |
| `donates` | Specimen Donor | Specimen | 1..* → 1..* | A donor donates one or more specimens |
| `collected at` | Specimen | Event | 1..* → 1 | A specimen is collected at exactly one event |
| `has` | Specimen / Event / Donor | Attributes | 1..* → 1 | Each entity has its associated attributes |
| `<<mediation>>` | Specimen | Anatomical Site | 1..* → 1 | Mediates the association between a specimen and its anatomical origin |
| `has component` | Anatomical Site | Anatomical Site subtypes | 1..* → 1..* | An anatomical site may have component sub-descriptions |

---

## Namespace Prefixes

| Prefix | URI |
|---|---|
| `obib:` | `http://purl.obolibrary.org/obo/obib.owl/` |
| `obo:` | `http://purl.obolibrary.org/obo/` |
| `BFO:` | `http://purl.obolibrary.org/obo/BFO_` |
| `OBI:` | `http://purl.obolibrary.org/obo/OBI_` |
| `IAO:` | `http://purl.obolibrary.org/obo/IAO_` |
| `RO:` | `http://purl.obolibrary.org/obo/RO_` |
| `PATO:` | `http://purl.obolibrary.org/obo/PATO_` |
| `UO:` | `http://purl.obolibrary.org/obo/UO_` |

---

## Loading the Ontology

The ontology is serialized in **OWL/XML** format. It can be loaded using any OWL-compatible tool:

- **Protégé** (recommended): Open `obib.owl` via *File → Open*
- **Python (owlready2)**:
  ```python
  from owlready2 import get_ontology
  onto = get_ontology("obib.owl").load()
  ```
- **Apache Jena / SPARQL**: Load as an RDF graph and query with SPARQL

---

## Dependencies and Imports

OBIB reuses terms from the following ontologies:

| Ontology | Role |
|---|---|
| BFO (Basic Formal Ontology) | Upper ontology |
| OBI (Ontology for Biomedical Investigation) | Domain ontology base |
| IAO (Information Artifact Ontology) | Information entities |
| RO (Relation Ontology) | Object properties |
| PATO (Phenotype and Trait Ontology) | Quality terms |
| UO (Units Ontology) | Measurement units |
| EFO (Experimental Factor Ontology) | Date of birth class |
| OGMS (Ontology for General Medical Science) | Diagnosis terms |

---

## Contributors

| Name |
|---|
| Alice Nzinga |
| Chris Stoeckert |
| Jan-Eric Litton |
| Jie Zheng |
| Loreana Norlin |
| Maria Anderberg |
| Martin N. Fransson |
| Mathias Brochhausen |
| Mikael Eriksson |
| Roxana Merino-Martinez |
| Sanela Kjellqvist |
| William R. Hogan |

---

## License

This ontology is released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/) license.
