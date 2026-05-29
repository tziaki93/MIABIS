The **Ontology for BIoBanking (OBIB)** supports the annotation and modeling of biobank activities, specimen contents, and administration. It is aligned with [MIABIS (Minimum Information About BIobank data Sharing)](https://github.com/MIABIS/miabis) and built on [Basic Formal Ontology (BFO)](http://basic-formal-ontology.org/).

**IRI:** `http://purl.obolibrary.org/obo/obib.owl`

---

## Version History

### v2.1 — Current Release

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

#### Removed Classes

| ID | Label | Replaced by |
|---|---|---|
| OBIB_0000482 | specimen donor's date of birth | OBIB_0002034 `specimen donor date of birth` |
| OBIB_0000483 | donor's biological sex | OBIB_0002020 `donor biological sex` |

#### Minor Fixes
Encoding corrections in definitions of `OBIB_0000168`, `OBIB_0000244`, `OBIB_0000245`, `OBIB_0000269`, `OBIB_0000356` (special characters for °C).
