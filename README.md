# BCB Captone Project

**Wearable-derived autonomic metrics for predicting metabolic and hepatic risk: insights from AI-READI**

- The code in this repository was used to complete a capstone project for a master's degree in Bioinformatics and Computational Biomedicine (BCB) obtained at Oregon Health & Science University (OHSU)
- This was completed as part of a National Library of Medicine (NLM) T-15 fellowship
- Date of completion: June 20, 2025

Final version: [OHSU Archives](https://digitalcollections.ohsu.edu/record/44709?v=pdf)

The project used data from the [AI-READI Dataset](https://docs.aireadi.org/docs/2/about) 

- The data is not included in this repository
- The project used public (not PHI protected) data

---

Juypter notebooks:

- The repository contains 4 Juypter notebooks that were used to extract and analyze data for the project
- `Capstone_DataExtraction.ipynb` was used to extract data from the various dataset files
- `Capstone_DataAnalysis.ipynb` was used for exploratory data analysis (EDA) and to build linear/logistic regression models
- `Capstone_FitbitData.ipynb` explored FitBit data more closely
- `Capstone_ML_Models.ipynb` explored data analysis using various ML models (not published in the final report)

---
## AI-READI Project: Dataset Description

- Version number: 2.0.0
- Publication date: 2024-11-08
- Identifier: https://doi.org/10.60775/fairhub.2

### Overview of the study

The Artificial Intelligence Ready and Equitable Atlas for Diabetes Insights (AI-READI) project seeks to create a flagship ethically-sourced dataset to enable future generations of artificial intelligence/machine learning (AI/ML) research to provide critical insights into type 2 diabetes mellitus (T2DM), including salutogenic pathways to return to health. The ability to understand and affect the course of complex, multi-organ diseases such as T2DM has been limited by a lack of well-designed, high quality, large, and inclusive multimodal datasets. The AI-READI team of investigators will aim to collect a cross-sectional dataset of 4,000 people and longitudinal data from 10% of the study cohort across the US. The study cohort will be balanced for self-reported race/ethnicity, gender, and diabetes disease stage. Data collection will be specifically designed to permit downstream pseudo-time manifold analysis, an approach used to predict disease trajectories by collecting and learning from complex, multimodal data from participants with differing disease severity (normal to insulin-dependent T2DM). The long-term objective for this project is to develop a foundational dataset in T2DM, agnostic to existing classification criteria or biases, which can be used to reconstruct a temporal atlas of T2DM development and reversal towards health (i.e., salutogenesis). Data will be optimized for downstream AI/ML research and made publicly available. This project will also create a roadmap for ethical and equitable research that focuses on the diversity of the research participants and the workforce involved at all stages of the research process (study design and data collection, curation, analysis, and sharing and collaboration).

### Description of the dataset

This dataset contains data from 1067 participants that was collected between July 19, 2023 and July, 31 2024. Data from multiple modalities are included. A full list is provided in the "Data Standards" section below. The data in this dataset contain no protected health information (PHI). Information related to the sex and race/ethnicity of the participants as well as medication used has also been removed.

The dataset contains 165,051 files and is around 2.01 TB in size.

A detailed description of the dataset is available in the AI-READI documentation for v2.0.0 of the dataset at [docs.aireadi.org](https://docs.aireadi.org/).

### Protocol

The protocol followed for collecting the data can be found in the AI-READI documentation for v2.0.0 of the dataset at [docs.aireadi.org](https://docs.aireadi.org/).

### Dataset access/restrictions

Accessing the dataset requires several steps, including:

- Login in through a verified ID system
- Agreeing to use the data only for type 2 diabetes related research.
- Agreeing to the license terms which set certain restrictions and obligations for data usage (see "License" section below).

### Data standards followed

This dataset is organized following the [Clinical Dataset Structure (CDS) v0.1.1](https://cds-specification.readthedocs.io/en/v0.1.1/). We refer to the CDS documentation for more details. Briefly, data is organized at the root level into one directory per datatype (c.f. Table below). Within each datatype folder, there is one folder per modality. Within each modality folder, there is one folder per device used to collect that modality. Within each device folder, there is one folder per participant. Each datatype, modality, and device folder is named using a name that best defines it. Each participant folder is named after the participant's ID number used in the study. For each datatype, the data files follow the standards listed in the Table below. More details are available in the dataset_structure_description.json metadata file included in this dataset.

| Datatype directory name   | Description                                                                                                                                                                                      | File format standard followed                                                                                                                                     |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| cardiac_ecg               | This directory contains electrocardiogram data collected by a 12 lead protocol (the current standard), Holter monitor, or smartwatch. The terms ECG and EKG are often used interchangeably.      | [WaveForm DataBase (WFDB)](https://wfdb.readthedocs.io/en/latest/wfdb.html)                                                                                       |
| clinical_data             | This directory contains clinical data collected through REDCap. Each CSV file in this directory is a one-to-one mapping to the OMOP CDM tables.                                                  | [Observational Medical Outcomes Partnership (OMOP) Common Data Model (CDM)](https://ohdsi.github.io/TheBookOfOhdsi)                                               |
| environment               | This directory contains data collected through an environmental sensor device custom built for the AI-READI project.                                                                             | [Earth Science Data Systems (ESDS) format](https://www.earthdata.nasa.gov/esdis/esco/standards-and-practices/ascii-file-format-guidelines-for-earth-science-data) |
| retinal_flio              | This directory contains data collected through fluorescence lifetime imaging ophthalmoscopy (FLIO), an imaging modality for in vivo measurement of lifetimes of endogenous retinal fluorophores. | [Digital Imaging and Communications in Medicine (DICOM)](http://medical.nema.org/)                                                                                |
| retinal_oct               | This directory contains data collected using optical coherence tomography (OCT), an imaging method using lasers that is used for mapping subsurface structure.                                   | [Digital Imaging and Communications in Medicine (DICOM)](http://medical.nema.org/)                                                                                |
| retinal_octa              | This directory contains data collected using optical coherence tomography angiography (OCTA), a non-invasive imaging technique that generates volumetric angiography images.                     | [Digital Imaging and Communications in Medicine (DICOM)](http://medical.nema.org/)                                                                                |
| retinal_photography       | This directory contains retinal photography data, which are 2D images. They are also referred to as fundus photography.                                                                          | [Digital Imaging and Communications in Medicine (DICOM)](http://medical.nema.org/)                                                                                |
| wearable_activity_monitor | This directory contains data collected through a wearable fitness tracker.                                                                                                                       | [Open mHealth](https://www.openmhealth.org/documentation/#/schema-docs/schema-library)                                                                            |
| wearable_blood_glucose    | This directory contains data collected through a continuous glucose monitoring (CGM) device.                                                                                                     | [Open mHealth](https://www.openmhealth.org/documentation/#/schema-docs/schema-library)                                                                            |

### Resources

All of our data files are in formats that are accessible with free software commonly used for such data types so no specific software is required. Some useful resources related to this dataset are listed below:

- Documentation of the dataset: [docs.aireadi.org](https://docs.aireadi.org/) (see 'Dataset v2.0.0' for this version of the dataset)
- AI-READI project website: [aireadi.org](https://aireadi.org/)
- Zenodo community of the AI-READI project: [zenodo.org/communities/aireadi](https://zenodo.org/communities/aireadi)
- GitHub organization of the AI-READI project: [github.com/AI-READI](https://github.com/AI-READI)


#### Changes between versions of the dataset

Changes between the current version of the dataset and the previous one are provided in details in the CHANGELOG file included in the dataset (also visible at docs.aireadi.org). A summary of the major changes is provided in the table below.

| Dataset      | v1.0.0 pilot    | year 2 data        | v2.0.0 main study  |
| ------------ | --------------- | ------------------ | ------------------ |
| Participants | 204             | 863                | 1067               |
| Data types   | 15+ data types  | +1 image device    | 15+ data types     |
| Processing   | custom / ad hoc | automated + custom | automated + custom |
| Release date | 5/3/2024        | included in v2.0.0 | 11/8/2024          |

### License

This work is licensed under a custom license specifically tailored to enable the reuse of the AI-READI dataset (and other clinical datasets) for commercial or research purposes while putting strong requirements around data usage, security, and secondary sharing to protect study participants, especially when data is reused for artificial intelligence (AI) and machine learning (ML) related applications. More details are available in the License file included in the dataset and also available at https://doi.org/10.5281/zenodo.10642459.

### Contact

For any questions, suggestions, or feedback related to this dataset, please go to https://aireadi.org/contact. We refer to the study_description.json and dataset_description.json metadata files included in this dataset for additional information about the contact person/entity, authors, and contributors of the dataset.

### Acknowledgement

The AI-READI project is supported by NIH grant [1OT2OD032644](https://reporter.nih.gov/search/1ADgncihCk6fdMRJdCnBjg/project-details/10471118) through the NIH Bridge2AI Common Fund program.



