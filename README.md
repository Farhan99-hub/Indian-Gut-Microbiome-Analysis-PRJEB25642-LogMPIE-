# PRJEB25642 Gut Microbiome — 10-Sample Analysis

This repository contains an in-silico analysis of **10 human gut microbiome samples** from **PRJEB25642 (LogMPIE)**. The workflow performs ASV inference (DADA2), taxonomic assignment (SILVA v138.1), and community analysis (alpha/beta diversity, relative abundance) using **R** in **Google Colab**.

> **Note:** This is a focused subset (10 samples) of the full LogMPIE cohort. The notebook is reproducible and includes all steps from raw reads to figures.

## Dataset
- **Accession:** PRJEB25642 (LogMPIE – Indian gut microbiome)
- **Type:** 16S rRNA amplicon (V3–V4) — Illumina
- **Samples analyzed:** 10 ERR samples (subset)

## Methods (overview)
- **ASV pipeline:** DADA2 (`filterAndTrim`, `learnErrors`, `dada`, `removeBimeraDenovo`)
- **Taxonomy:** SILVA v138.1 (`assignTaxonomy`)
- **Community analysis:** Alpha (Observed, Shannon), Beta (Bray–Curtis PCoA)
- **Composition:** Relative abundance at Phylum level; Top genera
- **Tools:** colab, dada2, ggplot2, phyloseq, R, silva, sra-toolkit

## Results (high-level)
- Alpha diversity varies notably across the 10 samples, indicating differences in richness and evenness.
- Bray–Curtis PCoA reveals separation between subsets of samples, suggesting distinct community structures.
- Phylum-level composition is dominated by **Bacteroidota** and **Firmicutes**, with **Proteobacteria** consistently present.
- **Post-chimera retention:** 54.99% of reads retained after chimera removal.

See **docs/results_summary.md** and **docs/figure_captions.md** for more details.

## Repository Structure
```
prjeb25642-10samples-gut-microbiome/
├── notebooks/
│   └── analysis.ipynb          
├── results/
│   ├── figures/                
│   └── tables/             
├── docs/
│   ├── results_summary.md
│   ├── figure_captions.md
│   └── methods.md
├── data/                      
├── scripts/                    
├── environment.yml             
├── LICENSE
└── README.md
```

## How to Reproduce
1. **Option A — Google Colab**
   - Upload `notebooks/analysis.ipynb` to Colab and run sequentially.
2. **Option B — Local (Conda)**
   ```bash
   conda env create -f environment.yml
   conda activate logmpie
   jupyter notebook notebooks/analysis.ipynb
   ```

---
## Citation - Dubey, A., Uppadhyaya, N., Nilawe, P. et al. LogMPIE, pan-India profiling of the human gut microbiome using 16S rRNA sequencing. Sci Data 5, 180232 (2018). https://doi.org/10.1038/sdata.2018.232
