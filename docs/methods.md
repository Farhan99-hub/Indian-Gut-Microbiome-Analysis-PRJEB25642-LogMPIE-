# Methods (Brief)

**Data Source:** ENA Project PRJEB25642 (LogMPIE – Indian gut microbiome).  
**Subset:** 10 samples (ERR accessions).  
**Environment:** Google Colab (R + Bioconductor).

## Pipeline
1. **Data retrieval:** SRA Toolkit (`fasterq-dump`) for the 10 ERR samples.
2. **Preprocessing & ASV inference (DADA2):**
   - `filterAndTrim` (truncLen=150, maxEE=2, truncQ=2, rm.phix=TRUE)
   - `learnErrors` → `dada` for denoising
   - `makeSequenceTable` → `removeBimeraDenovo`
3. **Taxonomy:** `assignTaxonomy` against **SILVA v138.1**.
4. **Phyloseq analysis:** `plot_richness` (Observed, Shannon), `ordinate` (PCoA, Bray–Curtis) + `plot_ordination`.
5. **Composition:** `tax_glom` at Phylum; `plot_bar` for relative abundance.
6. **Visualization:** `ggplot2`-based plots within phyloseq & custom ggplot.

**Key Packages:** `dada2`, `phyloseq`, `ggplot2`, `Biostrings`, `microbiome`, `tidyverse`.  
**External:** SRA Toolkit; SILVA v138.1 reference FASTA.
