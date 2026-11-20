# Indigenous Languages of Peru: A Curated Dataset of Language Types, Families, ISO Codes, and Speaking Peoples

## Description

This **curated dataset** provides a structured and verified reference of the **48 indigenous or native languages of Peru** (44 Amazonian and 4 Andean across 18 linguistic families), documenting their language type, linguistic family, associated indigenous peoples, and ISO language codes.

This resource is the result of a systematic process of **research, curation, and standardization**. It consolidates official linguistic and ethnolinguistic records into a clean tabular format suitable for linguistics, anthropology, public policy research, and data science workflows.

A core value of this curated collection is its **source fidelity**: it preserves official terminology and spellings in Spanish (such as *Chamikuro* vs. *Chamicuro*, *Maijɨki*, *Murui-Muinanɨ*, and *Ese eja*) while transparently documenting edge cases and data caveats rather than silently altering or omitting them. In particular, it explicitly highlights repeated ISO codes (`inp` for *Ikitu* and *Iñapari*; `jqr` for *Jaqaru* and *Kawki*) and the single-speaker case of *Taushiro* (`trr`), where `peoples_speaking_language` is set to `NA` and linguistic classification notes from official sources are documented.

The purpose of this resource is to serve as a **clean, reliable reference table** for researchers and data practitioners working with Peruvian indigenous languages across R, Python, and other analytical environments.

## Language and Encoding

To ensure maximum technical compatibility and international reach, this dataset follows these standards:
1. **Metadata in English, Values in Spanish:** All variable names (column headers) are in English (`language_id`, `language_name`, `language_type`, `language_family`, `peoples_speaking_language`, `iso`), while data values are in Spanish, following the original terminology and official spellings of the languages.
2. **Data Integrity:** The dataset contains 48 rows (`PE_01` to `PE_48`) and 6 columns with strict source fidelity. Multi-value entries in `peoples_speaking_language` and `iso` are delimited by semicolons (`;`), and `peoples_speaking_language` is `NA` for `PE_41` (*Taushiro*). Two ISO code values appear across two entries each in the source records: `inp` (*Ikitu*, `PE_13`; *Iñapari*, `PE_14`) and `jqr` (*Jaqaru*, `PE_16`; *Kawki*, `PE_21`).
3. **Encoding:** The CSV file was validated in R using `readr::guess_encoding()`, which detected **UTF-8 encoding (confidence = 1.0)** (above `ISO-8859-1` at `0.32` and `ISO-8859-9` at `0.21`), ensuring full support for accented characters and official orthography across Windows, macOS, and Linux.
4. **Cross-Platform Compatibility (R and Python):** Both `.csv` and `.xlsx` formats were tested in R and Python without errors or warnings. In **R**, the `.xlsx` and `.csv` files were imported using `readxl::read_excel()` and `readr::read_csv()` respectively, parsing all 48 rows and 6 character columns (`language_id`, `language_name`, `language_type`, `language_family`, `peoples_speaking_language`, `iso`). In **Python**, both formats were imported via `pandas.read_excel()` and `pandas.read_csv()`, returning `(48, 6)` DataFrames with `1` missing value (`NaN` / `NA`) in `peoples_speaking_language` (`PE_41` — *Taushiro*).

## Data Structure

The dataset is provided in `.csv` and `.xlsx` formats, containing the following variables:

| Variable | Type | Description |
| :--- | :--- | :--- |
| `language_id` | Character | Alphanumeric identifier for each language record (Format: `PE_01` to `PE_48`). |
| `language_name` | Character | Official name of the indigenous or native language in Spanish. |
| `language_type` | Character | Broad classification of the language (`Amazónica` or `Andina`). |
| `language_family` | Character | Linguistic family associated with the language. |
| `peoples_speaking_language` | Character | Indigenous peoples associated with / speaking the language (semicolon-separated when multiple; `NA` for `PE_41` *Taushiro*). |
| `iso` | Character | Three-letter ISO language code(s) associated with the language (semicolon-separated when multiple). |

## Methodology and Quality

1. **Data Source:** Compiled and cross-checked across official Peruvian language entries and normative instruments (reviewing individual language records across the BDPI catalog rather than a single language entry):
   - [BDPI – Base de Datos de Pueblos Indígenas u Originarios (Lenguas)](https://bdpi.cultura.gob.pe/lenguas)
   - [Ministerio de Cultura – Resolución Ministerial N.° 000122-2025-MC (Anexo)](https://transparencia.cultura.gob.pe/sites/default/files/transparencia/2025/05/resoluciones-ministeriales/rm000122-2025-mc-anexo.pdf)
   - [UNTRM – Anexo 2: Lista de lenguas indígenas u originarias](https://untrm.edu.pe/paginas/docs/6882481-anexo-2.pdf)
   - [Ministerio de Cultura – Marco Normativo de Lenguas Indígenas u Originarias del Perú (2020)](https://www.culturacusco.gob.pe/wp-content/uploads/2017/07/MARCO-NORMATIVO-LENGUAS-INDIGENAS-U-ORIGINARIAS-DEL-PER%C3%9A_2020_publicaci%C3%B3n.pdf)
2. **Critical Data Notes and Caveats:** Column names use `snake_case` for consistent access in R, Python, and SQL. Key edge cases identified in the source records are explicitly preserved and documented:
   - **Repeated ISO codes (`inp`):** Shared by `PE_13` (*Ikitu*, family *Záparo*, speaking people *Ikitu*) and `PE_14` (*Iñapari*, family *Arawak*, speaking people *Iñapari*).
   - **Repeated ISO codes (`jqr`):** Shared by `PE_16` (*Jaqaru*, type *Andina*, family *Aru*, speaking people *Jaqaru*) and `PE_21` (*Kawki*, type *Andina*, family *Aru*, speaking people *Kawki*).
   - **Taushiro (`PE_41`, ISO `trr`):** Recorded with `peoples_speaking_language` as `NA` and `language_family` as `Záparo` following the structured source fields. According to the [BDPI Taushiro language record](https://bdpi.cultura.gob.pe/index.php/lenguas/taushiro), Taushiro (`trr`) has only one fluent speaker today—Amadeo García García, living in the Tigre River basin in the Loreto department—and is an Amazonian language whose linguistic affiliation has not been determined with certainty: some include it in the *Záparo* family (Beuchat and Rivet 1908), whereas Kaufman (1994) proposes a relationship with *Kandozi-Chapra* and the extinct *Omurano* (cited by Campbell 1997).
3. **Interoperability:** Both `.csv` and `.xlsx` formats were verified in R and Python without errors. See *Language and Encoding, item 4* for full details.

## License

This dataset is distributed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license. You are free to share and adapt the material as long as appropriate credit is given.

## Author

**Renzo Caceres Rossi**
* **ORCID:** [0009-0005-0744-854X](https://orcid.org/0009-0005-0744-854X)
* **GitHub:** [indigenous-languages-peru](https://github.com/lightbluetitan/indigenous-languages-peru)