# SCLC-miRNA-Analysis
Integrative bioinformatics analysis of differentially expressed miRNAs in Small Cell Lung Cancer — hub gene identification &amp; drug repurposing in R
Overview
Small Cell Lung Cancer (SCLC) is one of the most aggressive forms of lung cancer with poor prognosis and limited treatment options. This project applies an end-to-end computational pipeline to identify dysregulated miRNAs in SCLC, trace their downstream gene targets, and repurpose existing drugs as potential therapeutic candidates.
This work forms the basis of my MS thesis in Computational Biotechnology at the University of Management and Technology (UMT), Sialkot.

Pipeline Summary
Raw GEO Data (GSE74190)
        ↓
Preprocessing & Normalization
        ↓
Differential miRNA Expression (limma / DESeq2)
        ↓
Target Gene Prediction
        ↓
PPI Network Construction (Cytoscape)
        ↓
Hub Gene Identification
        ↓
GO & KEGG Pathway Enrichment
        ↓
Computational Drug Repurposing



Dataset

Source: NCBI Gene Expression Omnibus (GEO)
Accession: GSE74190
Condition: SCLC tumor vs. normal tissue
Platform: miRNA expression microarray


Raw data not included in this repository. Download directly from GEO.


Repository Structure
SCLC-miRNA-Analysis/
├── scripts/
│   ├── 01_preprocessing.R        # Data loading and normalization
│   ├── 02_DEG_analysis.R         # Differential expression (limma)
│   ├── 03_hub_gene_ID.R          # PPI network and hub gene identification
│   ├── 04_GO_KEGG_enrichment.R   # Pathway enrichment analysis
│   └── 05_drug_repurposing.R     # Drug candidate screening
├── figures/
│   ├── Cytoscape_miRNA_mRNA_network.png
│   ├── GO_BP_barplot.png
│   ├── GO_CC_barplot.png
│   └── GO_MF_barplot.png
├── results/
│   ├── DE_miRNAs_SCLC_vs_Normal.csv
│   ├── GO_BP_results.csv
│   ├── GO_CC_results.csv
│   └── GO_MF_results.csv
└── README.md

Key Results

Identified differentially expressed miRNAs between SCLC tumor and normal samples
Constructed a miRNA-mRNA interaction network with 444 edges using Cytoscape
Identified hub genes via PPI network topology analysis
Performed GO enrichment across Biological Process, Cellular Component, and Molecular Function
Screened drug candidates via computational repurposing pipeline


Tools & R Packages
ToolPurpose
limma: Differential expression analysis
DESeq2 Expression normalization 
ggplot2 Data visualization
CytoscapeNetwork construction and visualization
clusterProfiler GO & KEGG enrichment
org.Hs.eg.dbHuman gene annotation

Figures
miRNA–mRNA Interaction Network
Show Image
GO Enrichment — Biological Process
Show Image
GO Enrichment — Cellular Component
Show Image
GO Enrichment — Molecular Function
Show Image

Requirements
Install required R packages:
rinstall.packages(c("ggplot2", "dplyr", "readr"))

if (!requireNamespace("BiocManager", quietly = TRUE))
  install.packages("BiocManager")

BiocManager::install(c("limma", "DESeq2", "clusterProfiler", "org.Hs.eg.db"))

Author
Quratulain Waseem
MS Computational Biotechnology — Gold Medalist
University of Management and Technology, Sialkot, Pakistan

LinkedIn: quratulain-waseem-239310353
ORCID: 0009-0003-9735-5632


Note
This repository contains analysis code and figures only. The manuscript based on this work is currently under preparation for journal submission.
