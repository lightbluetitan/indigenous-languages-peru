# Limitations

This document outlines the known limitations of the **Indigenous Languages of Peru: A Curated Dataset of Language Types, Families, ISO Codes, and Speaking Peoples** (`indigenous_languages_peru.csv` and `indigenous_languages_peru.xlsx`) to ensure its proper use in research and development.

## 1. Scope of Coverage

This dataset is strictly limited to a **curated reference table of the 48 indigenous or native languages of Peru** (`PE_01` to `PE_48`, comprising 44 Amazonian and 4 Andean languages across 18 linguistic families) and the six variables defined in its schema (`language_id`, `language_name`, `language_type`, `language_family`, `peoples_speaking_language`, and `iso`).
* It does NOT include speaker counts or demographic census figures, geographic coordinates or polygon boundaries, dialectal inventories, or lexicographic/grammatical data.
* Users requiring detailed ethnolinguistic profiles, speaker statistics, or spatial mapping should consult official Peruvian institutional records and specialized linguistic or anthropological resources.

## 2. Multi-Value Fields and Source Edge Cases

Multi-value entries in `peoples_speaking_language` and `iso` (three-letter ISO codes) are stored as semicolon-delimited strings (`;`) within single cells rather than normalized into separate relational tables.
* Users performing relational queries or per-code/per-people aggregations in R, Python, or SQL will need to split semicolon-delimited strings first.
* **Repeated ISO codes:** Source records include `inp` across `PE_13` (*Ikitu*, family *Záparo*, speaking people *Ikitu*) and `PE_14` (*Iñapari*, family *Arawak*, speaking people *Iñapari*), and `jqr` across `PE_16` (*Jaqaru*, type *Andina*, family *Aru*, speaking people *Jaqaru*) and `PE_21` (*Kawki*, type *Andina*, family *Aru*, speaking people *Kawki*). These overlaps are preserved as reported in the source materials rather than deduplicated or altered.
* **Taushiro (`PE_41`, ISO `trr`):** `peoples_speaking_language` is recorded as `NA` and `language_family` as `Záparo` following the structured source fields. According to the [BDPI Taushiro language record](https://bdpi.cultura.gob.pe/index.php/lenguas/taushiro), Taushiro (`trr`) has only one fluent speaker today—Amadeo García García, living in the Tigre River basin in the Loreto department—and is an Amazonian language whose linguistic affiliation has not been determined with certainty: some include it in the *Záparo* family (Beuchat and Rivet 1908), whereas Kaufman (1994) proposes a relationship with *Kandozi-Chapra* and the extinct *Omurano* (cited by Campbell 1997).

## 3. Temporal Snapshot

The dataset reflects a curated snapshot compiled and validated for release `1.0.0` (**2026-11-19**) based on official Peruvian sources and normative instruments.
* Any subsequent updates, official reclassifications, or newly recognized entries will be addressed in future versioned releases following Semantic Versioning conventions.

## 4. Language and Orthographic Conventions

Variable names (column headers) are written in English using `snake_case`, while data values are preserved in Spanish following official terminology and orthography (such as *Chamikuro* vs. *Chamicuro*, *Maijɨki*, *Murui-Muinanɨ*, and *Ese eja*).
* This design maintains fidelity to official Peruvian records and source terminology.
* Users requiring English translations of language names, family labels, or speaking peoples will need to apply their own translation or mapping layer.

## 5. Non-Official Status

Although this dataset was compiled and cross-checked against official Peruvian sources (Ministry of Culture of Peru / BDPI, RM N.° 000122-2025-MC, UNTRM, and Marco Normativo de Lenguas Indígenas u Originarias del Perú), this specific curated version is maintained by an **independent researcher**.
* It should be treated as a curated technical standardization for research and educational purposes, and not as an official publication of the Ministry of Culture of Peru or any other state institution.