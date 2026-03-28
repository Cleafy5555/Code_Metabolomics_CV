# Metabolomics analysis code

Annotated R scripts for the paper "STAGE-ALIGNED METABOLOMICS REVEALS HOST-DEPENDENT AND HYBRID-SPECIFIC RESPONSES DURING EARLY CLUBROOT INFECTION IN BRASSICA OLERACEA" and Chapter 4 of the thesis, covering stage-aligned LC-MS metabolomics processing, QC-guided normalisation, multivariate analyses, machine-learning classification, stage-associated driver extraction, and pathway summarisation in broccoli, broccolini, and gai-lan.

## Important note
This repository contains cleaned and annotated analysis code only. Raw LC-MS data, MS-DIAL exports, and other raw inputs are **not** included.

Because the original material supplied here was pasted working code rather than a final repository, these scripts are a **GitHub-oriented reconstruction** of the final workflow. They are organised around the thesis methods and results structure and are intended to be readable, editable, and easier to rerun than the original notebook-style files.

## Suggested folder structure
- `data/raw/` — MS-DIAL exports, schedule spreadsheets, extraction weights, and MetaboAnalyst outputs
- `data/processed/` — collated feature tables and reusable processed inputs
- `outputs/intermediate/` — intermediate CSVs written by the scripts
- `outputs/figures/` — figure outputs
- `outputs/tables/` — summary tables

## Script order
1. `00_collate_batches_pos.R`
2. `01_normalise_qcloess_pos.R`
3. `02_qc_diagnostics_pos.R`
4. `03_global_ordination_permanova.R`
5. `04_stage_driver_exports_and_overlap_sets.R`
6. `05_stage_pathway_plots.R`
7. `06_batchmatched_inoc_vs_control.R`
8. `07_ml_variety_repeated.R`
9. `08_ml_stage_and_joint_models.R`

## Main analyses represented
- Collation of MS-DIAL positive-mode batches into a master feature matrix
- Metadata parsing from sample IDs and schedule joins
- QC-guided LOESS normalisation, blank filtering, and QC-RSD gating
- PCA / PCoA, PERMANOVA, and PERMDISP
- Feature-level stage and inoculation contrasts
- Mummichog / MetaboAnalyst export tables and pathway plots
- Repeated elastic-net multinomial classification for variety and variety × stage
