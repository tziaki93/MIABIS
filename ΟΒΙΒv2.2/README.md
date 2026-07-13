# Ontology for Biobanking (OBIB)

> **Version:** 2.2  

## Overview

The **Ontology for Biobanking (OBIB)** is an OWL ontology for the semantic annotation and formal modeling of the activities, contents, and administration of biobanks. Biobanks are facilities that collect and store biological specimens (e.g., blood, tissues, bodily fluids) along with associated annotation and clinical data.

OBIB is built on the **Basic Formal Ontology (BFO)** as its upper ontology and is derived from a curated subset of the **Ontology for Biomedical Investigation (OBI)**. It is developed in compliance with [OBO Foundry](http://obofoundry.org/) principles. The first version of OBIB was produced by merging two earlier biobank-related ontologies: **OMIABIS** and the **UPenn Biobank Ontology**.

In this version, the ontology was further extended to support the MIABIS v3 implementation requirements. The following core classes were added along with the supporting classes and object properties, revised, or ontologized as part of the new implementation work:

* **Biobank**
* **Collection**
* **Network** *(new module)*
* **Research Resource**

---

#### Added Classes

**Biobank**
| ID | Label |
|---|---|
| OBIB_0002015 | infrastructural capabilities |
| OBIB_0002016 | organisation capabilities |
| OBIB_0002017 | bioprocessing and analytical capabilities |
| OBIB_0002018 | quality management standard |

**Collection**
| ID | Label |
|---|---|
| OBIB_0002027 | collection unique resource locator |
| OBIB_0002035 | age low |
| OBIB_0002031 | age high |
| OBIB_0002037 | age low unit |
| OBIB_0002038 | age high unit |
| OBIB_0002058 | dataset type |
| OBIB_0002042 | sample collection setting |
| OBIB_0002044 | collection design |
| OBIB_0002023 | access and use condition |
| OBIB_0002045 | collection or research resource status |
| OBIB_0002046 | publications |

**Network** *(new module)*
| ID | Label |
|---|---|
| OBIB_0002047 | network |
| OBIB_0002048 | network ID |
| OBIB_0002049 | network name |
| OBIB_0002050 | network unique resource locator |
| OBIB_0002051 | juristic person |
| OBIB_0002052 | country |
| OBIB_0002053 | network description |
| OBIB_0002054 | network status |
| OBIB_0002055 | common collaboration topics |
| OBIB_0002056 | network type |

**Research Resource**
| ID | Label |
|---|---|
| OBIB_0002041 | research resource identifier |
| OBIB_0002043 | research resource unique resource locator |
| OBIB_0002059 | research resource design |

#### Obsolete Classes

| ID | Label | Reason |
|---|---|---|
| OBIB_0000650 | name of sample collection responsible or principal investigator | Removed in v3.0; PI contact information merged into general Contact Information |
| OBIB_0000686 | count of current sampled human study participant | Replaced by unified "Total number of subjects" (OBIB_0000687) |

#### Added Object Properties

| ID | Label |
|---|---|
| RO_0002351 | has_member *(used for Network members)* |

---

## Loading the Ontology

The ontology is serialized in **OWL** format. It can be loaded using any OWL-compatible tool:

- **Protégé** (recommended): Open `obib.owl` via *File → Open*

---

## Contributors

|FORTH|
