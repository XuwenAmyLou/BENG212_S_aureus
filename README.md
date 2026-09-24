# *Staphylococcus aureus* iModulon Discovery

A systems-biology workflow for identifying and characterizing independently modulated gene sets (**iModulons**) in non-MRSA *Staphylococcus aureus* NCTC 8325.

This repository contains the Winter 2023 BENG 212 team project by **Xuwen (Amy) Lou, Matthew Prasetyo, and Krishna Brunton**. The analysis turns public transcriptomic data into a quality-controlled expression compendium, applies independent component analysis, and interprets the resulting transcriptional modules using regulatory, functional, pathway, and motif evidence.

## Analysis workflow

| Folder | Purpose | Methods and outputs |
| --- | --- | --- |
| [`01-metadata-curation`](./01-metadata-curation) | Define the expression compendium | Public-study metadata collection, strain selection, and sample curation for NCTC 8325 |
| [`02-rnaseq-processing`](./02-rnaseq-processing) | Produce a consistent expression matrix | Genome references, read alignment outputs, MultiQC summaries, and log-TPM normalization |
| [`03-expression-quality-control`](./03-expression-quality-control) | Evaluate sample reliability | Metadata checks, replicate filtering, Pearson correlation, and expression-matrix QC |
| [`04-independent-component-analysis`](./04-independent-component-analysis) | Decompose transcriptional variation | Independent component analysis (ICA), dimensionality analysis, gene-weight matrix (`M`/`S`), and activity matrix (`A`) outputs |
| [`05-imodulon-characterization`](./05-imodulon-characterization) | Interpret and publish iModulons | Gene-table construction, k-means thresholding, transcriptional-regulatory-network enrichment, functional annotation, KEGG mapping, manual curation, MEME/TOMTOM motif analysis, explained variance, and iModulonDB export |

## Biological question

Can independent component analysis recover coherent transcriptional programs from public non-MRSA *S. aureus* RNA-seq data, and can those programs be linked to known regulators, pathways, functions, and sequence motifs?

## Tools and data

The notebooks use Python and Jupyter with pandas, SciPy, Biopython, and [PyModulon](https://github.com/SBRG/pymodulon). Supporting inputs include the NCTC 8325 genome annotation, processed expression data, sample metadata, KEGG annotations, eggNOG annotations, and transcriptional-regulatory-network information.

## Reproducibility notes

- The repository follows the analysis in execution order using numbered folders.
- Large intermediate and result files are retained to document the original course workflow.
- Some RNA-seq alignment outputs were produced collaboratively and are included as project inputs.
