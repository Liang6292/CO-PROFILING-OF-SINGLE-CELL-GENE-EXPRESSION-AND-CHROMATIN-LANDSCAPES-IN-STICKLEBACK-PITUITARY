# CO-PROFILING OF SINGLE-CELL GENE EXPRESSION AND CHROMATIN LANDSCAPES IN STICKLEBACK PITUITARY

This repository contains the R code used in the analysis for the paper titled "CO-PROFILING OF SINGLE-CELL GENE EXPRESSION AND CHROMATIN LANDSCAPES IN STICKLEBACK PITUITARY." 

# Background
The pituitary gland is a key endocrine gland with various physiological functions including metabolism, growth, and reproduction. It comprises several distinct cell populations that release multiple polypeptide hormones. Although the major endocrine cell types are conserved across taxa, the regulatory mechanisms of gene expression and chromatin organization in specific cell types remain poorly understood. Here, we performed simultaneous profiling of the transcriptome and chromatin landscapes in the pituitary cells of the three-spined stickleback (Gasterosteus aculeatus), which represents a good model for investigating the genetic mechanisms underlying adaptive evolution. We obtained pairwise gene expression and chromatin profiles for 5184 cells under short- and long-day conditions. Using three independent clustering analyses, we identified 16 distinct cell clusters and validated their consistency. Moreover, we reported a novel cell type that exclusively expressed thyroid-stimulating hormone subunit beta 2 in teleost. These results advance our understanding of the regulatory dynamics occurring in the pituitary gland and provide a reference for future research on comparative physiology and evolutionary biology.

# Data Source
The raw reads and alignment files for single-cell RNA-seq and ATAC-seq are available through the DNA Data Bank of Japan (DDBJ) under the project accession DRP011961 (2024).
Preprocessed feature-barcode matrices can be accessed on Figshare vis 10.6084/m9.figshare.26795323.

# Analysis Workflow
This pipeline integrates RNA (GEX) and ATAC-seq data to identify photoperiod-responsive molecular markers through the following main steps:

1. Setup and Data Preparation

Load packages, import RNA and ATAC data, and create Seurat objects.
Build an annotation database and extract relevant gene expression and peak data.
Quality Control and Peak Processing

Filter low-quality data, recall peaks, and create a non-redundant peak set.
Quantify and integrate peaks as a new assay.
Multimodal Data Integration

Preprocess GEX and ATAC data separately, including normalization, feature selection, PCA, and LSI computation.
Find integration anchors and perform joint integration for combined analysis.
Clustering and Marker Identification

Conduct independent clustering (GEX, ATAC) and joint clustering (WNN).
Identify cell-specific markers: DEGs (for GEX) and DARs (for ATAC).
Motif and Photoperiod-Responsive Analysis

Perform motif scanning and activity computation for overrepresented motifs in DARs.
Identify photoperiod-responsive DEGs and DEMs in each cell cluster.
