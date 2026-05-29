# Ontology for Biobanking (OBIB)

> **Version:** 2.1  

## Overview

The **Ontology for Biobanking (OBIB)** is an OWL ontology for the semantic annotation and formal modeling of the activities, contents, and administration of biobanks. Biobanks are facilities that collect and store biological specimens (e.g., blood, tissues, bodily fluids) along with associated annotation and clinical data.

OBIB is built on the **Basic Formal Ontology (BFO)** as its upper ontology and is derived from a curated subset of the **Ontology for Biomedical Investigation (OBI)**. It is developed in compliance with [OBO Foundry](http://obofoundry.org/) principles. The first version of OBIB was produced by merging two earlier biobank-related ontologies: **OMIABIS** and the **UPenn Biobank Ontology**.

In this version, the ontology was further extended to support the MIABIS v3 implementation requirements. The following core classes were added along with the supporting classes and object properties, revised, or ontologized as part of the new implementation work:

* **Sample Donor**
* **Event**
* **Sample**

---

## Conceptual Model

The ontology was designed using **OntoUML**, a conceptual modeling language based on the Unified Foundational Ontology (UFO), in order to support semantically precise domain analysis and conceptual modeling. The implemented ontology itself remains aligned with the Basic Formal Ontology (BFO) and follows OBO Foundry principles for interoperability and OWL-based biomedical ontology development.
The diagram below illustrates the core structure of OBIB.

#### Added Classes

**Biobank**
| ID | Label |
|---|---|
| OBIB_0002015 | infrastructural capabilities |
| OBIB_0002016 | organisation capabilities |
| OBIB_0002017 | bioprocessing and analytical capabilities |
| OBIB_0002018 | quality management standard |
| NCIT_C60776 | contact information |

**Sample (Work in Progress-Sample Type Values)**
| ID | Label |
|---|---|
| OBIB_0002015 | anatomical site ontology |
| OBIB_0002016 | sample creation date and time |
| OBIB_0002017 | anatomical site |
| OBIB_0002018 | anatomical site ontology version |
| OBIB_0002019 | anatomical site ontology code |
| OBIB_0002020 | anatomical site ontology description |
| OBIB_0002021 | Ascites fluid |
| OBIB_0002022 | sample content diagnosis |
| OBIB_0002023 | use and access conditions |
| OBIB_0002024 | sample source |
| OBIB_0002028 | bone |
| OBIB_0002029 | bone marrow aspirate |
| OBIB_0002030 | bone marrow plasma |
| OBIB_0002031 | bone tissue |
| OBIB_0002032 | bronchoalveolar lavage |
| OBIB_0002033 | cancer cell lines |
| OBIB_0002034 | dental pulp |
| OBIB_0002035 | digital sample |
| OBIB_0002036 | embryo |
| OBIB_0002037 | entire body organ |

**Sample Donor**
| ID | Label |
|---|---|
| OBIB_0002020 | donor biological sex |
| OBIB_0002034 | specimen donor date of birth |
| OBIB_0002045 | specimen donor ID |

**Dataset Types**
| ID | Label |
|---|---|
| OBIB_0002039 | lifestyle dataset |
| OBIB_0002040 | environmental dataset |
| OBIB_0002041 | physiological dataset |
| OBIB_0002042 | biochemical dataset |
| OBIB_0002043 | genomic dataset |
| OBIB_0002044 | clinical dataset |
| OBIB_0002046 | psychological dataset |
| OBIB_0002052 | proteomic dataset |
| OBIB_0002053 | metabolomic dataset |
| OBIB_0002054 | body (radiological) image |
| OBIB_0002055 | whole slide image |
| OBIB_0002056 | photo image |
| OBIB_0002057 | genealogical records |

**Event** *(new module)*
| ID | Label |
|---|---|
| OBIB_0002047 | event |
| OBIB_0002048 | event ID |
| OBIB_0002049 | event date and time |
| OBIB_0002050 | age at event |
| OBIB_0002051 | age at event unit |

#### Added Object Properties

| ID | Label |
|---|---|
| OBIB_0002019 | has identifier |
| OBIB_0002021 | occured at |
| OBIB_0002022 | has unit of measurement |
| OBIB_0002023 | has condition |
| OBIB_0002024 | created on |
| OBIB_0002025 | collected at |
| OBIB_0002025 | has biological sex |
| OBIB_0002026 | has storage temperature |
| OBIB_0002027 | donates |
| OBIB_0002028 | has creation time |
| OBIB_0002030 | has birth date |
| OBIB_0002032 | has anatomical origin |
| OBIB_0002033 | has diagnosis |
| OBIB_0002038 | dataset type |


---

## Loading the Ontology

The ontology is serialized in **OWL** format. It can be loaded using any OWL-compatible tool:

- **Protégé** (recommended): Open `obib.owl` via *File → Open*

---

## Contributors

|FORTH|
