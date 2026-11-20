# Methodology

This document describes the systematic process used to create the **Indigenous Languages of Peru: A Curated Dataset of Language Types, Families, ISO Codes, and Speaking Peoples** (`indigenous_languages_peru.csv` and `indigenous_languages_peru.xlsx`).

## 1. Data Acquisition

The 48 indigenous or native languages of Peru (`PE_01` to `PE_48`)—comprising 44 Amazonian and 4 Andean languages across 18 linguistic families—were compiled and cross-checked across official Peruvian institutional records and normative instruments, reviewing individual language entries across the BDPI catalog rather than a single entry:

* [BDPI – Base de Datos de Pueblos Indígenas u Originarios (Lenguas)](https://bdpi.cultura.gob.pe/lenguas)
* [Ministerio de Cultura – Resolución Ministerial N.° 000122-2025-MC (Anexo)](https://transparencia.cultura.gob.pe/sites/default/files/transparencia/2025/05/resoluciones-ministeriales/rm000122-2025-mc-anexo.pdf)
* [UNTRM – Anexo 2: Lista de lenguas indígenas u originarias](https://untrm.edu.pe/paginas/docs/6882481-anexo-2.pdf)
* [Ministerio de Cultura – Marco Normativo de Lenguas Indígenas u Originarias del Perú (2020)](https://www.culturacusco.gob.pe/wp-content/uploads/2017/07/MARCO-NORMATIVO-LENGUAS-INDIGENAS-U-ORIGINARIAS-DEL-PER%C3%9A_2020_publicaci%C3%B3n.pdf)

## 2. Data Curation and Normalization

To ensure source fidelity and technical interoperability, the following criteria were applied:

* **Source Fidelity and Orthography:** Official terminology and spellings in Spanish (such as *Chamikuro* vs. *Chamicuro*, *Maijɨki*, *Murui-Muinanɨ*, and *Ese eja*) were preserved rather than silently altered, while variable names (column headers) were defined in English.
* **Header Standardization:** All variable names were defined using `snake_case` (`language_id`, `language_name`, `language_type`, `language_family`, `peoples_speaking_language`, `iso`) for consistent access in R, Python, and SQL.
* **ID and Multi-Value Formatting:** The `language_id` field follows the alphanumeric format `PE_01` to `PE_48`. Multi-value entries in `peoples_speaking_language` and `iso` (three-letter ISO codes) are separated by semicolons (`;`).
* **Preservation of Edge Cases:** Repeated ISO codes in source records (`inp` for *Ikitu* `PE_13` and *Iñapari* `PE_14`; `jqr` for *Jaqaru* `PE_16` and *Kawki* `PE_21`) are retained as reported. For *Taushiro* (`PE_41`, ISO `trr`), `peoples_speaking_language` is recorded as `NA` and `language_family` as `Záparo`, accompanied by documentation from the [BDPI Taushiro language record](https://bdpi.cultura.gob.pe/index.php/lenguas/taushiro) noting its single fluent speaker (Amadeo García García in the Tigre River basin, Loreto) and scholarly discussion on its linguistic classification (Beuchat and Rivet 1908; Kaufman 1994 via Campbell 1997).
* **Encoding:** Files were validated with **UTF-8 encoding (confidence = 1.0)** in R, supporting accented characters and official orthography across Windows, macOS, and Linux.

## 3. Quality Control (QA)

The final dataset underwent a multi-step validation process:

1. **Completeness Check:** Verified the presence of exactly 48 records (`PE_01` to `PE_48`), covering 44 Amazonian and 4 Andean languages across 18 linguistic families.
2. **Schema Validation:** Confirmed 6 character columns (`language_id`, `language_name`, `language_type`, `language_family`, `peoples_speaking_language`, `iso`) across both `.csv` and `.xlsx` formats.
3. **Missing Value Check:** Confirmed zero missing values across `language_id`, `language_name`, `language_type`, `language_family`, and `iso`, and 1 missing value (`NA`) in `peoples_speaking_language` corresponding to `PE_41` (*Taushiro*).
4. **Cross-Source Validation:** Cross-checked entries across the BDPI language catalog and official Peruvian normative documents.
5. **Encoding Verification:** Tested the CSV file using `readr::guess_encoding()` in R, confirming UTF-8 encoding with `confidence = 1.0` (above `ISO-8859-1` at `0.32` and `ISO-8859-9` at `0.21`).

## 4. Compatibility Testing

Both dataset formats (`indigenous_languages_peru.csv` and `indigenous_languages_peru.xlsx`) were imported and verified in R and Python without errors or warnings:

* **R:** `.xlsx` loaded via `readxl::read_excel()` and `.csv` via `readr::read_csv()`, parsing all 48 rows and 6 character columns.
* **Python:** Both files imported via `pandas.read_excel()` and `pandas.read_csv()`, returning `(48, 6)` DataFrames with 1 missing value in `peoples_speaking_language` (`PE_41` — *Taushiro*).

## 5. Software and Tools

* **Data Processing:** Spreadsheet / CSV
* **Validation:** R (`readr`, `readxl`) and Python (`pandas`)
* **Documentation:** Markdown and Citation File Format (`CITATION.cff`)
* **Version Control & Archiving:** Git / GitHub (`indigenous-languages-peru`) and Zenodo