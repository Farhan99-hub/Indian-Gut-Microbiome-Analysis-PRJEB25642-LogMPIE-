# Indian-Gut-Microbiome-Analysis-PRJEB25642-LogMPIE-
This repository details an analysis of 10 single-end 16S rRNA amplicon samples from the LogMPIE gut microbiome project (ENA: PRJEB25642), a pan-India survey of gut microbial diversity
Objective
Process and analyze a select subset of samples using DADA2 + Phyloseq in R to infer microbial community structure and diversity.

Key Steps
Download single-end FASTQ files via SRA Toolkit.

Quality filtering and trimming (DADA2).

ASV inference, chimera removal, taxonomic assignment using SILVA v138.1.

Construction of a phyloseq object.

Visualization:

Taxonomic composition (phylum-level bar plot).

Alpha diversity (Observed richness, Shannon index).

Beta diversity (Bray–Curtis PCoA).

Observations
Dominant phyla: Bacteroidota, Firmicutes, Proteobacteria.

Wide variation in alpha diversity—some samples high in richness, others low.

Sample clustering in PCoA suggests distinct community structures among subjects.

Tools Used
R (DADA2, Phyloseq, ggplot2, dplyr)

SRA Toolkit

SILVA v138.1

Google Colab (execution environment)

