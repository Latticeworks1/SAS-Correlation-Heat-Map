# SAS Correlation Heatmap for Cancer Alley Thesis

SAS code to generate annotated correlation heatmaps from environmental and health data analyzed in my M.S. thesis at Tulane University School of Public Health and Tropical Medicine.

**Thesis:** *"Cancer Alley: Industrial Emissions and Cancer Incidence in Louisiana"*

Examines census tract-level associations between toxic releases from industrial facilities (EPA TRI data) and cancer incidence (Louisiana Tumor Registry), adjusting for socioeconomic and behavioral risk factors.

---

## Overview

This heatmap visualizes Pearson correlations among:

| Category | Variables |
|----------|-----------|
| **Industrial Exposure** | CDens, RDens, NearF_D, NearR_D, SF_D |
| **Socioeconomic Factors** | GINI, Poverty, MedIncome |
| **Demographics** | Black |
| **Behavioral Risk Factors** | Smoking, Binge, Obesity, CheckUps |

---

## Repository Contents

```
cancer-alley-heatmap/
├── correlation_heatmap.sas      # Main SAS script
├── CORRELATION_HEATMAP.pdf      # Example output
├── AllCanc_0303.csv             # Example dataset
└── README.md
```

**correlation_heatmap.sas**  
Imports CSV data, computes correlations using PROC CORR, reshapes output with arrays, generates annotated heatmap using SGPLOT with HEATMAPParm and overlaid TEXT labels. Exports to PDF.

**CORRELATION_HEATMAP.pdf**  
Example output (December 2025)

> **Note:** The actual thesis dataset contains sensitive health information and is not included. Example dataset provided for demonstration.

---

## Requirements

- SAS 9.4 or later
- CSV input with variables specified in `corr_vars` macro variable

---

## Quick Start

```bash
git clone https://github.com/yourusername/cancer-alley-heatmap.git
cd cancer-alley-heatmap
```

Update the data path in `correlation_heatmap.sas`:

```sas
/* Edit this line */
%let datapath = /path/to/your/data.csv;

/* Run the script */
%include "correlation_heatmap.sas";
```

Output: `CORRELATION_HEATMAP.pdf` in your working directory.

---

## Technical Highlights

- Macro-based variable management
- Efficient PROC CORR output reshaping using arrays
- Modern SGPLOT: HEATMAPParm, custom color gradients, centered text overlays
- Publication-ready PDF output

---

## Contact

**Wendy Bogil**  
New Orleans, LA  
[wendybogil@gmail.com](mailto:wendybogil@gmail.com) • [LinkedIn](https://www.linkedin.com/in/wendybogil)

---

## License

Available for academic and research purposes.
