# U.S. Forensic DNA Database Project

**Website:** [https://donadiojp.github.io/PODFRIDGE_Databases/](https://donadiojp.github.io/PODFRIDGE_Databases/)

## Overview

This repository contains data collection, processing, and analysis code for a comprehensive study of U.S. forensic DNA databases spanning 2001-2025. The project reconstructs the historical growth of the National DNA Index System (NDIS), compiles current state-level DNA database policies and statistics (SDIS), and standardizes demographic data from Freedom of Information Act (FOIA) requests.

## Associated Publication

This dataset is described in:

**Lasisi, T., Donadio, J.P., Muller, M., Wilson, J., Mooney, J., & Edge, M.D.** (2025). United States forensic DNA databases: national time series (2001–2025) and state cross-sections. 

**Dataset DOI:** [To be added]

## Project Components

### 1. NDIS Time Series Analysis (2001-2025)
Reconstructs the growth of the FBI's National DNA Index System using archived snapshots from the Internet Archive's Wayback Machine.

- **Data Source:** FBI CODIS-NDIS Statistics pages
- **Coverage:** Monthly snapshots from 2001-2025
- **Metrics:** Offender profiles, arrestee profiles, forensic profiles, participating laboratories, investigations aided
- **Methods:** Web scraping, HTML parsing, temporal validation, outlier detection

[View NDIS Scraping Methodology →](https://donadiojp.github.io/PODFRIDGE_Databases/ndis_scraping.html)

[View NDIS Analysis →](https://donadiojp.github.io/PODFRIDGE_Databases/ndis_analysis.html)

### 2. SDIS Cross-Sectional Summary (2025)
Compiles current state-level DNA database statistics and policy information across all 50 states and Washington D.C.

- **Data Source:** State government websites, legislative databases
- **Coverage:** Current snapshot (August 2025)
- **Content:** Profile counts by type (where available), arrestee collection policies, familial search authorization, statutory citations
- **Methods:** Systematic web searches, policy documentation, legal statute review

[View SDIS Analysis →](https://donadiojp.github.io/PODFRIDGE_Databases/sdis_summary.html)

### 3. FOIA Demographic Data Processing
Standardizes demographic composition data from state DNA databases obtained through public records requests documented in Murphy & Tong (2020).

- **Data Source:** FOIA responses from 7 states (Murphy & Tong, 2020, Appendix A)
- **Coverage:** 2012-2018 (varies by state)
- **Content:** Racial and gender composition by profile type (offender/arrestee/forensic)
- **Methods:** OCR processing, data standardization, quality validation

[View FOIA Analysis →](https://donadiojp.github.io/PODFRIDGE_Databases/foia_processing.html)

### 4. Annual DNA Collection Methodology
Documents the methodology and data sources used in Murphy & Tong (2020) for calculating annual DNA collection rates by race.

- **Data Source:** Murphy & Tong (2020, Appendix B)
- **Coverage:** All 50 states
- **Content:** Annual collection estimates, Census demographics, calculated collection rates by race
- **Methods:** Data provenance tracking, methodology documentation

[View Methodology →](https://donadiojp.github.io/PODFRIDGE_Databases/appendix_analysis.html)

## Repository Structure

PODFRIDGE_Databases/

├── index.qmd                          # Main website landing page

├── ndis_collection.qmd                # NDIS data collection notebook

├── ndis_analysis.qmd                  # NDIS technical validation & figures

├── sdis.qmd                           # SDIS compilation & analysis

├── foia.qmd                           # FOIA data processing

├── racial_disparities.qmd             # Murphy & Tong methodology documentation

├── _quarto.yml                        # Quarto website configuration

├── styles.css                         # Custom styling

├── scripts/                           # Helper functions & utilities

│   ├── wayback_scraper.R             # Wayback Machine API functions

│   ├── html_parsers.R                # Era-specific HTML parsing

│   ├── jurisdiction_mapping.R        # Name standardization

│   └── validation_functions.R        # Outlier detection & QC

├── data/                              # Data files (see data/README.md)

│   ├── raw/                          # Unprocessed source data

│   ├── intermediate/                 # Processing outputs

│   └── final/                        # Clean, versioned datasets

└── docs/                              # Rendered website (GitHub Pages)

## Authors

- **Tina Lasisi**
- **J. P. Donadio**
- **M. Muller**
- **J. Wilson**
- **J. Mooney**
- **M. D. Edge**

*Corresponding author: tlasisi@umich.edu*

## Technical Details

### Software Requirements

- Python (≥ 3.13)

- R (≥ 4.0)

- Quarto (≥ 1.3)

- Python packages: `requests`, `beautifulsoup4`, `lxml`, `pandas`, `tqdm`, `hashlib`, `collections`, `pathlib`, `datetime`, `os`

- R packages: `tidyverse`, `rvest`, `httr`, `lubridate`, `jsonlite`, `knitr`, `plotly`

### Key Methods

- **Web Scraping:** Internet Archive Wayback Machine API

- **Data Validation:** Monotonicity testing, median absolute deviation (MAD) outlier detection

- **External Validation:** Comparison with peer-reviewed publications and FBI press releases

- **Reproducibility:** All processing code available; versioned datasets archived on Zenodo

## Data Access

All final datasets are archived and publicly available on Zenodo:

**Zenodo Repository:** [DOI to be added upon publication]

The repository includes:
- `NDIS_time_series.csv` - Monthly NDIS statistics (2001-2025)
- `SDIS_cross_section.csv` - State-level profiles and policies (2025)
- `FOIA_Demographics.csv` - Demographic composition from FOIA responses
- `Annual_DNA_Collection.csv` - Annual collection rates (Murphy & Tong 2020)
- Raw HTML files, intermediate processing outputs, and complete documentation

For detailed data dictionaries and usage notes, see `data/README.md`.

## Citation

If you use these data or code, please cite both the dataset and the associated paper:
```bibtex
@article{lasisi2025dna,
  title={United States forensic DNA databases: national time series (2001–2025) and state cross-sections},
  author={Lasisi, Temi and Donadio, J. P. and Muller, M. and Wilson, J. and Mooney, J. and Edge, Michael D.},
  journal={-},
  year={2025},
  note={In press}
}

@dataset{lasisi2025dna_data,
  author={Lasisi, Temi and Donadio, J. P. and Muller, M. and Wilson, J. and Mooney, J. and Edge, Michael D.},
  title={United States forensic DNA databases: NDIS, SDIS, and FOIA datasets},
  year={2025},
  publisher={Zenodo},
  doi={[to be added]}
}
```

## License
Code: MIT License
Data: CC BY 4.0 (pending Zenodo publication; FOIA-derived data subject to original authors' permissions)

## Acknowledgments
We thank Erin Murphy for providing access to state-level demographic disclosures and FOIA response materials. We acknowledge the Internet Archive's Wayback Machine for preserving historical web content that made this reconstruction possible.

Last update: October 5th, 2025
