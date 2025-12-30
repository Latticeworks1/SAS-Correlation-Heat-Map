# SAS Correlation Heatmap for Cancer Alley Thesis

SAS code to generate annotated correlation heatmaps from environmental and health data analyzed in my M.S. thesis at Tulane University School of Public Health and Tropical Medicine.

**Thesis:** "Cancer Alley: Industrial Emissions and Cancer Incidence in Louisiana"

Examines census tract-level associations between toxic releases from industrial facilities (EPA TRI data) and cancer incidence (Louisiana Tumor Registry), adjusting for socioeconomic and behavioral risk factors.

---

## Overview

This heatmap visualizes Pearson correlations among:

- **Industrial exposure proxies** – CDens, RDens, NearF_D, NearR_D, SF_D
- **Socioeconomic factors** – GINI, Poverty, MedIncome  
- **Demographics** – Black
- **Behavioral risk factors** – Smoking, Binge, Obesity, CheckUps

---

## Repository Contents
```
.
├── correlation_heatmap.sas      # Main SAS script
├── CORRELATION_HEATMAP.pdf      # Example output
├── AllCanc_0303.csv             # Example dataset
└── README.md                    # You are here
```

**correlation_heatmap.sas**  
Complete SAS workflow that imports CSV data, computes correlations using PROC CORR, reshapes output with arrays, and generates an annotated heatmap using SGPLOT with HEATMAPParm and overlaid TEXT labels. Exports journal-ready PDF.

**CORRELATION_HEATMAP.pdf**  
Example output generated December 2025.

> **Note:** The actual thesis dataset contains sensitive health information and is not included in this repository. An example dataset is provided for demonstration.

---

## Requirements

- SAS 9.4 or later
- CSV input file with variables specified in the `corr_vars` macro variable

---

## Quick Start
```bash
git clone https://github.com/yourusername/cancer-alley-heatmap.git
cd cancer-alley-heatmap
```

Open `correlation_heatmap.sas` in SAS and update the data path:
```sas
/* Edit this line with your data path */
%let datapath = /path/to/your/data.csv;

/* Run the script */
%include "correlation_heatmap.sas";
```

The script will generate `CORRELATION_HEATMAP.pdf` in your working directory.

---

## Technical Highlights

- Macro-based variable management for maintainability
- Efficient PROC CORR output reshaping using SAS arrays
- Modern SGPLOT features: HEATMAPParm, custom color gradients, centered text overlays
- Publication-ready output formatting

---

## Contact

**Wendy Bogil**  
New Orleans, LA  
[wendybogil@gmail.com](mailto:wendybogil@gmail.com) | [LinkedIn](https://www.linkedin.com/in/wendybogil)

---

## License

This code is available for academic and research purposes.
