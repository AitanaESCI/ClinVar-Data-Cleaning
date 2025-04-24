# ClinVar Data Cleaning

This repository contains code to clean and filter genetic variant data from ClinVar, ensuring quality and consistency for later analysis. The primary goal is to preprocess the dataset for accurate Variant Effect Predictor (VEP) usage, allowing pathogenicity predictions on a curated dataset.


## Repository structure

The repository is organized as follows:
```bash
├── README.md
├── data/
│   ├── variant_summary.txt
│   ├── clinvar_data_preVEP_grch38.csv
│   ├── clinvar_data_preVEP_grch37.csv
│   ├── clinvar_data_outputVEP_grch38.txt
│   ├── clinvar_data_outputVEP_grch37.txt
│   ├── clinvar_data_inputVEP_grch38.vcf
│   ├── clinvar_data_inputVEP_grch37.vcf
│   ├── cleaned_Clinvar_dataset_inputVEP.vcf
│   ├── cleaned_Clinvar_dataset_outputVEP.txt
│   ├── cleaned_Clinvar_dataset_parsed.csv
│   ├── cleaned_ClinVar_dataset.csv
│   ├── uniprotkb_reviewed_true_AND_organism_id_2025_04_09.list
│   └── cleaned_ClinVar_with_preds.csv
├── docs/
│   ├── Thresholds_log.xlsx
│   └── DatasetCollection_ClinVar.pdf
└── code/
    ├── ClinVar_DataCleaning.ipynb
    ├── merging_ClinVar.py
    └── parsing_ClinVar.py
```

## Directory overview

#### 1. `data/`

This directory contains all raw, intermediate, and final datasets used throughout the pipeline. It includes:
* Original and cleaned ClinVar datasets for both GRCh37 and GRCh38 assemblies.
* VEP input/output files in `.vcf` and `.txt` formats.
* Processed datasets formatted and filtered for pathogenicity prediction workflows.
* Reference lists used for gene/protein validation.

All files in this directory are generated or transformed at various stages of the preprocessing pipeline.

**Note**: due to file size limitations, this folder is not included directly in the repository. 
All files can be downloaded from [Google Drive/Zenodo/Figshare](linkhere!!). See the [Data availability](#data-availability) section for instructions.


#### 2. `docs/`

Contains supporting materials used during development and validation of the cleaning process:
* Threshold reference sheets with cutoff values from literature for interpreting pathogenicity predictors.
* Methodology documentation: presentation slides outlining dataset origin, quality control logic, and pipeline structure.


#### 3. `code/`

Includes all code used for dataset cleaning, transformation, and VEP integration:
* The main Jupyter notebook documents the cleaning and filtering pipeline.
* Supporting Python scripts handle specific steps like merging data or parsing VEP output.


## Data availability
To access the dataset files:
1. Visit [Google Drive/Zenodo/Figshare](linkhere!!)
2. Download the full `data/` directory and place it inside the repository.
3. Ensure the folder structure matches the one described above.
