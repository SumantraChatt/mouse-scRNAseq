# Seurat Analysis: Mouse scRNA-seq Gut Dataset

This repository contains code used for preprocessing and filtering single-cell RNA-seq data from the mouse gut, as analyzed using the [Seurat](https://satijalab.org/seurat/) package in R.

## 📂 Repository Contents

- `commands` — Script for creating Seurat objects, merging datasets, and performing basic filtering.
- `README.md` — Overview of project and instructions.

## 🧪 Analysis Overview

### ✅ Workflow Steps:

1. **Read 10X Data**  
   Load raw count matrices using `Read10X()` and create Seurat objects.

2. **Merge Datasets**  
   Merge multiple datasets (`ens1`, `ens2`) using `merge()`.

3. **Quality Control**  
   - Calculate `log10GenesPerUMI`
   - Compute mitochondrial ratio using `PercentageFeatureSet()`
   - Visual inspection of metadata

4. **Metadata Annotation**  
   - Add `sample` identifiers
   - Rename QC-related columns for clarity

5. **Filter Low-Quality Cells**  
   Retain only cells with:
   - `nUMI >= 500`
   - `nGene >= 250`
   - `log10GenesPerUMI > 0.80`
   - `mitoRatio < 0.20`

6. **Gene-Level Filtering**  
   - Keep genes expressed in ≥10 cells
   - Re-create a Seurat object with filtered features

7. **Save Output**  
   Store the cleaned object using `saveRDS()`.

## 📦 Environment

This code was written using:

- R version: `4.5.1`
- Seurat version: `5.3.1.0`
- Other dependencies:
  - `dplyr`
  - `Matrix`
  - `stringr`
  - patchwork
  - ggplot2
  - tidyverse
  - sctransform
  - scCustomize
  - monocle3
  - SeuratWrappers

## 📁 Data

You can replace `/directory/seurat_folder` with your own 10X Genomics output folders.


