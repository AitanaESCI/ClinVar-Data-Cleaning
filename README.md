# ClinVar-Data-Cleaning

This repository contains code to clean and filter genetic variant data from ClinVar, ensuring quality and consistency for downstream analysis. The primary goal is to preprocess the dataset for accurate Variant Effect Predictor (VEP) usage, allowing pathogenicity predictions on a curated dataset.


### Repository structure

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
│   ├── cleaned_ClinVar_dataset.csv
│   └── cleaned_Clinvar_dataset_inputVEP.vcf
├── docs/
│   ├── DatasetCollection_ClinVar.pptx
│   └── Thresholds_log.xlsx
├── notebooks/
│   └── ClinVar_DataCleaning.ipynb
└── scripts/
    └── VEP.py
```

### Directory overview

#### 1. `data/`

This directory contains both the raw and processed ClinVar datasets. The `variant_summary.txt` file includes the original variant dataset from ClinVar. The `clinvar_data_preVEP_grch38.csv` and `clinvar_data_preVEP_grch37.csv` files are the cleaned datasets before VEP processing, corresponding to different genome assemblies (GRCh37 and GRCh38). The `clinvar_data_inputVEP.vcf` files serve as input for the VEP tool, while the `clinvar_data_outputVEP.txt` files store the annotated results after running VEP. The final cleaned datasets (`cleaned_ClinVar_dataset.csv` and `.vcf`) are optimized for downstream pathogenicity predictions.


#### 2. `notebooks/`

This directory contains the main Jupyter Notebook (`ClinVar_DataCleaning.ipynb`), where the dataset preprocessing is implemented. The notebook details data cleaning steps, filtering criteria, handling of missing values, standardization of variant representation, and preparation for VEP input. The filtering steps remove also low-confidence variants and format the data correctly for annotation tools.


#### 3. `scripts/`

This directory contains the `VEP.py` script, which is used for parsing and post-processing results from the VEP tool. After running VEP, this script extracts relevant fields, formats the output for downstream analysis, and integrates key annotations required for pathogenicity predictions (i.e., filtering of column names, binarization of existing columns, etc).


#### 4. `docs/`

This directory contains documentation and supplementary resources. The `DatasetCollection_ClinVar.pptx` presentation provides an overview of the dataset sources, processing workflow, and filtering logic used in the cleaning pipeline. The `Thresholds_log.xlsx` file compiles literature-based threshold cutoffs for various pathogenicity predictors, detailing criteria used to interpret the VEP results and validate filtering choices.
