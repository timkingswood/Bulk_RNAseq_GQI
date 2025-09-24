# Bulk_RNAseq_GQI
Fink et al. RNAseq_Code

# RNA-seq PCA Workflow (Publication-Ready)

This repository contains an R script to generate a **publication-quality PCA plot** from RNA-seq count data.  
The pipeline reads a raw count matrix (Excel), processes it with **DESeq2**, and outputs PCA figures in **high-resolution (1200 dpi)**.

---

## Features

- Input: Excel file with **raw unnormalized counts**  
- Conditions: `GQI`, `GQP`, `PBS`, `SDEC` (5 replicates each)  
- Automatic metadata construction (condition + replicate)  
- Variance stabilizing transformation (VST) using DESeq2  
- PCA plot with:
  - Fixed colors (GQI=purple, PBS=black, GQP=blue, SDEC=red)  
  - Bold dashed quadrant lines at **PC1=10** and **PC2=-5**  
  - Dotted grid lines  
  - All axis/legend text in bold  
- Export:
  - **Single column size** (~85 mm, 3.35 × 2.8 in)  
  - **Double column size** (~174 mm, 6.85 × 5.2 in)  
  - Formats: PNG + TIFF  
  - Resolution: **1200 dpi**

---

## Requirements

- R (≥ 4.0)  
- R packages:
  - `readxl`  
  - `data.table`  
  - `DESeq2`  
  - `ggplot2`  

Install missing packages via:

```r
install.packages(c("readxl","data.table","ggplot2"))
if (!requireNamespace("BiocManager", quietly = TRUE)) install.packages("BiocManager")
BiocManager::install("DESeq2")
