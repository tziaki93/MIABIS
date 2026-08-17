# Ontology for Biobanking (OBIB)

> **Version:** 2.3

## Overview

The **Ontology for Biobanking (OBIB)** is an OWL ontology for the semantic annotation and formal modeling of the activities, contents, and administration of biobanks. Biobanks are facilities that collect and store biological specimens (e.g., blood, tissues, bodily fluids) along with associated annotation and clinical data.

OBIB is built on the **Basic Formal Ontology (BFO)** as its upper ontology and is derived from a curated subset of the **Ontology for Biomedical Investigation (OBI)**. It is developed in compliance with [OBO Foundry](http://obofoundry.org/) principles. The first version of OBIB was produced by merging two earlier biobank-related ontologies: **OMIABIS** and the **UPenn Biobank Ontology**.

In this version, the ontology was further extended to support the MIABIS v3 implementation requirements. Building on the Biobank, Collection, Network, and Research Resource work of v2.2, this version completes the **Sample Type** coverage required by MIABIS Core v3.0 — non-human, non-blood, and digital/processed sample types, alongside the underlying bodily-fluid, tissue, and cell-line hierarchies needed to classify them:

* **Sample Type** *(bodily fluid, blood, tissue, bone, cell, processed/digital, and environmental specimens)*

| Ontology    | MIABIS Version | Classes | Properties | Individuals | Axioms |
|--------------|----------------|----------|-------------|--------------|---------|
| OMIABIS (2013) | MIABIS v1   | 249      | 64          | 34           | —       |
| OBIB (2016)    | MIABIS v2   | 516      | 83          | —            | 1172    |
| OBIB (2023)    | MIABIS v2   | 1804     | 93          | 226          | 17807   |
| OBIB (2026)    | MIABIS v2.1 | 1844     | 108         | 226          | 18117   |
| OBIB (2026)    | MIABIS v2.2 | 1868     | 206         | 226          | 18346   |
| OBIB (2026)    | MIABIS v2.3 | 1926     | 203         | 267          | 18893   |

---

#### Added Classes

**Bodily Fluid & Blood Specimens**
| ID | Label |
|---|---|
| OBIB_0002057 | ascites fluid |
| OBIB_0002060 | body cavity fluid |
| OBIB_0002160 | Menstrual blood |
| OBIB_0002163 | nasal washing |
| OBIB_0002169 | tears specimen |
| obib.owl/OBIB_0002034 | dental pulp |
| OBIB_0002155 | serum |
| OBIB_0002159 | Liquid Biopsy |
| OBIB_0002175 | Whole blood |
| OBIB_0002176 | Whole blood, dried (e.g. Guthrie cards) |

**Tissue & Bone Specimens**
| ID | Label |
|---|---|
| OBIB_0002150 | Tissue (fresh frozen or fixed) |
| OBIB_0002151 | Tissue (frozen or FFPE) |
| OBIB_0002171 | Tissue (fixed) |
| OBIB_0002172 | Tissue (FFPE) |
| OBIB_0002173 | Tissue (fresh frozen) |
| OBIB_0002152 | Embryo or fetal tissue |
| obib.owl/OBIB_0002036 | embryo |
| OBIB_0002154 | Post-mortem tissue |
| obib.owl/OBIB_0002028 | bone |
| obib.owl/OBIB_0002029 | bone marrow aspirate |
| obib.owl/OBIB_0002030 | bone marrow plasma |
| obib.owl/OBIB_0002037 | entire body organ |
| OBIB_0002170 | tooth specimen |

**Cell-Based Specimens**
| ID | Label |
|---|---|
| OBIB_0002140 | Fibroblasts |
| OBIB_0002149 | Primary cell |
| OBIB_0002158 | Isolated Tumor Cell (neoplastic cell) |
| OBIB_0002165 | Peripheral blood mononuclear cells (PBMC) |
| obib.owl/OBIB_0002033 | cancer cell lines |
| OBIB_0002167 | Immortalised cell line specimen |
| OBIB_0002168 | Stem cell (and iPS cell) |

**Processed & Other Specimens**
| ID | Label |
|---|---|
| OBIB_0002166 | protein extract |
| OBIB_0002164 | organoid specimen |
| OBIB_0002157 | Isolated or enriched exosomes |
| obib.owl/OBIB_0002035 | digital sample |
| OBIB_0002174 | Urine Sediment specimen |
| OBIB_0002156 | Gas exhaled |
| OBIB_0002153 | Isolated microbes |

**Environmental / Food Specimens**
| ID | Label |
|---|---|
| OBIB_0002147 | Specimen from environment or food |
| OBIB_0002148 | Food specimen |

#### Obsolete Classes

None in this version.

#### Added Object Properties

| ID | Label |
|---|---|
| OBIB_0002040 | sample type |
| OBIB_0002058 | dataset type |

---

## Conceptual Model

The ontology was designed using **OntoUML**, a conceptual modeling language based on the Unified Foundational Ontology (UFO), in order to support semantically precise domain analysis and conceptual modeling. The implemented ontology itself remains aligned with the Basic Formal Ontology (BFO) and follows OBO Foundry principles for interoperability and OWL-based biomedical ontology development.
The diagram below illustrates the core structure of OBIB.

<img width="4017" height="1238" alt="OntoUMLv2 2" src="https://github.com/user-attachments/assets/bb5d7d3e-d7c2-4174-acea-a4847263ce83" />


## Loading the Ontology

The ontology is serialized in **OWL** format. It can be loaded using any OWL-compatible tool:

- **Protégé** (recommended): Open `obib.owl` via *File → Open*

---

## Contributors

|FORTH|
