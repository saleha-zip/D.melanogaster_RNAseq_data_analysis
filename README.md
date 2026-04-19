# Reference-based RNA-Seq Analysis (Galaxy)

## Overview

This project implements a complete reference-based RNA-Seq analysis pipeline using the Galaxy platform. The goal is to identify differential gene expression induced by phosphatidylserine (PS) depletion in *Drosophila melanogaster*.

The workflow includes read alignment, quantification, quality control, differential expression analysis, Gene Ontology (GO) enrichment, and visualization.

---

## Dataset

Seven RNA-Seq samples were analyzed:

* **Untreated (4 samples):**

  * GSM461176 (single-end)
  * GSM461177 (paired-end)
  * GSM461178 (paired-end)
  * GSM461182 (single-end)

* **Treated (3 samples):**

  * GSM461179 (single-end)
  * GSM461180 (paired-end)
  * GSM461181 (paired-end)

Counts files were obtained from preprocessed featureCounts outputs provided in the tutorial.

---

## Reference Genome

* Species: *Drosophila melanogaster*
* Genome build: dm6 (BDGP Release 6)

---

## Pipeline Steps

### 1. Alignment (Mapping)

Reads were aligned to the reference genome using STAR aligner in Galaxy. Output BAM files were generated for each sample.

### 2. Coverage Visualization

Strand-specific coverage tracks were generated:

* Strand 1: blue
* Strand 2: red

Visualization tools:

* IGV
* Sashimi plots
* JBrowse2

---

### 3. Read Quantification

Gene-level counts were obtained using featureCounts.

---

### 4. Quality Control

* Principal Component Analysis (PCA) to assess sample clustering
* Heatmaps to evaluate variability between samples

---

### 5. Differential Expression Analysis

Differential gene expression between treated and untreated samples was computed using DESeq2.

Outputs include:

* Log2 fold changes
* Adjusted p-values
* Lists of significantly up/downregulated genes

---

### 6. Gene Ontology (GO) Analysis

GO enrichment analysis was performed using GOseq to identify biological processes affected by PS depletion.

Gene length bias correction was applied using feature length data derived from the reference annotation.

---

## Key Results

* PCA shows separation between treated and untreated samples
* Differential expression analysis identifies genes responsive to PS depletion
* GO analysis highlights enriched biological processes

---

## Directory Structure

See project folder organization for details:

* `data/` → input datasets
* `results/` → outputs from each analysis step
* `figures/` → plots used in report
* `workflow/` → Galaxy workflow export

---

## Reproducibility

All steps were performed using the Galaxy platform following the official tutorial:
https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html

---

## Author

Saleha Asim

## Date

19th April, 2026

