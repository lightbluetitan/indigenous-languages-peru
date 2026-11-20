# Data Sources

This document outlines the official sources used to compile, validate, and curate the **Indigenous Languages of Peru: A Curated Dataset of Language Types, Families, ISO Codes, and Speaking Peoples** (`indigenous_languages_peru.csv` and `indigenous_languages_peru.xlsx`).

## 1. Primary Sources

The 48 indigenous or native languages of Peru (`PE_01` to `PE_48`), along with their language types, linguistic families, speaking peoples, and ISO codes, were compiled and cross-checked across official Peruvian institutional records and normative instruments (reviewing individual language entries across the BDPI catalog rather than a single entry):

* **BDPI – Base de Datos de Pueblos Indígenas u Originarios (Lenguas)**
  * **Description:** Official database of the Ministry of Culture of Peru documenting indigenous or native languages and associated peoples across individual language entries.
  * **URL:** [https://bdpi.cultura.gob.pe/lenguas](https://bdpi.cultura.gob.pe/lenguas)

* **Ministerio de Cultura – Resolución Ministerial N.° 000122-2025-MC (Anexo)**
  * **Description:** Ministerial resolution annex from the Ministry of Culture of Peru (May 2025) supporting official reference and verification of indigenous or native languages.
  * **URL:** [https://transparencia.cultura.gob.pe/sites/default/files/transparencia/2025/05/resoluciones-ministeriales/rm000122-2025-mc-anexo.pdf](https://transparencia.cultura.gob.pe/sites/default/files/transparencia/2025/05/resoluciones-ministeriales/rm000122-2025-mc-anexo.pdf)

* **UNTRM – Anexo 2: Lista de lenguas indígenas u originarias**
  * **Description:** Institutional reference annex listing indigenous or native languages of Peru.
  * **URL:** [https://untrm.edu.pe/paginas/docs/6882481-anexo-2.pdf](https://untrm.edu.pe/paginas/docs/6882481-anexo-2.pdf)

* **Ministerio de Cultura – Marco Normativo de Lenguas Indígenas u Originarias del Perú (2020)**
  * **Description:** Normative and reference publication from the Ministry of Culture of Peru on indigenous or native languages.
  * **URL:** [https://www.culturacusco.gob.pe/wp-content/uploads/2017/07/MARCO-NORMATIVO-LENGUAS-INDIGENAS-U-ORIGINARIAS-DEL-PER%C3%9A_2020_publicaci%C3%B3n.pdf](https://www.culturacusco.gob.pe/wp-content/uploads/2017/07/MARCO-NORMATIVO-LENGUAS-INDIGENAS-U-ORIGINARIAS-DEL-PER%C3%9A_2020_publicaci%C3%B3n.pdf)

### Specific Source Notes on Edge Cases

* **Repeated ISO codes (`inp` and `jqr`):** Source records include `inp` across `PE_13` (*Ikitu*, family *Záparo*, speaking people *Ikitu*) and `PE_14` (*Iñapari*, family *Arawak*, speaking people *Iñapari*), and `jqr` across `PE_16` (*Jaqaru*, type *Andina*, family *Aru*, speaking people *Jaqaru*) and `PE_21` (*Kawki*, type *Andina*, family *Aru*, speaking people *Kawki*). These values are preserved as reported in the source materials.
* **Taushiro (`PE_41`, ISO `trr`):** Recorded with `peoples_speaking_language` as `NA` and `language_family` as `Záparo` in the structured dataset. According to the [BDPI Taushiro language record](https://bdpi.cultura.gob.pe/index.php/lenguas/taushiro), Taushiro (`trr`) has only one fluent speaker today—Amadeo García García, living in the Tigre River basin in the Loreto department—and is an Amazonian language whose linguistic affiliation has not been determined with certainty: some include it in the *Záparo* family (Beuchat and Rivet 1908), whereas Kaufman (1994) proposes a relationship with *Kandozi-Chapra* and the extinct *Omurano* (cited by Campbell 1997).

## 2. Access Date

All sources were consulted and validated during **November 2026** (release `1.0.0` dated **2026-11-19**).

## 3. Citation of Sources

When using this dataset, users are encouraged to acknowledge both this curated version and the official institutional sources:

> *Data compiled and cross-checked against official Peruvian sources (Ministry of Culture of Peru / BDPI, RM N.° 000122-2025-MC, UNTRM, and Marco Normativo de Lenguas Indígenas u Originarias del Perú), curated and standardized by Renzo Caceres Rossi.*

For academic purposes, please cite this curated version using the DOI and metadata provided in the `CITATION.cff` file included in this repository.