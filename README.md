# Soil Tillage Detection Using Sentinel Data

This repository contains the Python scripts and resources associated with the study **"Detecting Soil Tillage in Portugal: Challenges and Insights from Rules-Based and Machine Learning Approaches using Sentinel-1 and Sentinel-2 Data"**. The research highlights the challenges in detecting soil tillage practices in Portugal using remote sensing data and presents different approaches to tackle these challenges.

## Table of Contents
- [Background](#background)
- [Data and Methods](#data-and-methods)
  - [Study Region](#study-region)
  - [Remote Sensing Data](#remote-sensing-data)
  - [Detection Approaches](#detection-approaches)
- [Results](#results)
- [Requirements](#requirements)
- [Usage](#usage)
- [Contributors](#contributors)
- [Funding](#funding)

---

## Background

Soil tillage operations like plowing and cultivation significantly impact soil health and the environment. This study leverages Sentinel-1 and Sentinel-2 satellite data to detect such operations in Portuguese agricultural parcels using rules-based and machine learning (ML) approaches.

---

## Data and Methods

### Study Region

The study focuses on mainland Portugal, covering various climate zones and agricultural systems, with an emphasis on regions prone to soil degradation due to climatic conditions.

### Remote Sensing Data

- **Sentinel-1**: Synthetic Aperture Radar (SAR) data (VV and VH polarizations).
- **Sentinel-2**: Optical data for calculating NDVI (Normalized Difference Vegetation Index).
- **Data Source**: All remote sensing data were obtained through [Google Earth Engine](https://earthengine.google.com/).

### Detection Approaches

#### Rules-Based Approach:
- Detects abrupt changes in SAR backscatter and verifies with NDVI or CR ratios.
- Threshold optimization for parameters like ΔVH and NDVI.

#### Machine Learning Approaches:
- **XGBoost (Imbalanced Dataset)**: Handles class imbalance with `scale_pos_weight`.
- **XGBoost (SMOTE)**: Uses Synthetic Minority Over-Sampling Technique to improve recall.

Performance was evaluated using precision, recall, F1, F2 scores, and AUC-ROC metrics.

---

## Results

- **Best Model**: XGBoost with SMOTE
  - **Recall**: 67%
  - **AUC-ROC**: 74%
  - **Precision**: 8%

The results demonstrate the potential of machine learning but highlight the need for further studies to refine and automate soil tillage detection.

## Usage

The trained models obtained from the study are available in the `models` folder. You can use these models for prediction or further analysis by loading them into your Python environment.

---

## Requirements

- **Python**: 3.8+
- **Key Python packages**:
  - `numpy`
  - `scikit-learn`
  - `scipy`
  - `imblearn`

---

## Contributors

- **Tiago G. Morais** (Primary Developer)
- **Ricardo F.M. Teixeira** (Supervision)
- **Tiago Domingos** (Contributor)
- *See the paper for the full list of authors.*

---

## Funding

This work was supported by the **Fundação para a Ciência e Tecnologia (FCT)** through several projects:

- GrassData (DSAIPA/DS/0074/2019)
- CEEC-IND/00365/2018/CP1572/CT0012
- UIDB/50009/2020
- UIDP/50009/2020
- LA/P/0083/2020
