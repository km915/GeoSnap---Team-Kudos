# GeoSnap: Land-Use Classification and Explainability from Sentinel-2 Imagery

This repository contains our solution for the **GeoSnap Challenge**, using the **EuroSAT** dataset for land-use classification and explainability on both RGB and multispectral Sentinel-2 imagery.

## Overview

The project investigates the impact of spectral information on classification performance by comparing multiple deep learning architectures across two modalities:

- **RGB (3-band) imagery**
- **Multispectral (13-band) Sentinel-2 imagery**

### Best Performing Models

| Modality | Model | Validation Accuracy |
|-----------|---------|-------------------|
| RGB | DenseNet121 | 98.0% |
| Multispectral | Spectral Attention CNN | 98.4% |

In addition to classification, the project includes explainability analyses using:

- **Grad-CAM** for spatial explanations
- **Spectral Attention Weights** for band importance analysis
- **NDVI / NDWI studies** for environmental interpretation

---

## Repository Structure

```text
.
├── Explainability notebook (Task 2)
│   ├── MS_attention_cnn
│   └── RGB_densenet121
│
├── Training & inference code (Task 1)
│   ├── Attention_CNN_approach.ipynb
│   ├── Base_CNN.ipynb
│   ├── ConvNext
│   └── DensNet121
│
├── prediction_csvs
│   ├── ms_predictions (attention+cnn).csv
│   └── rgb_predictions (densenet121).csv
│
└── Report.pdf
```

### Training & Inference

Contains notebooks for training and evaluating:

- Baseline CNN
- Spectral Attention CNN
- DenseNet121
- ConvNeXt

for both RGB and multispectral data.

### Explainability (Task 2)

Contains notebooks and generated visualisations for:

- Grad-CAM analysis
- Spectral attention weight analysis
- Confusion matrices
- NDVI / NDWI distribution studies

### Predictions

Final prediction CSVs generated using:

- DenseNet121 (RGB)
- Spectral Attention CNN (Multispectral)

---

## Key Findings

- Simply adding more spectral bands does **not** guarantee better performance.
- A domain-motivated **Spectral Attention CNN** outperformed larger architectures on the multispectral task.
- The learned attention weights automatically emphasized physically meaningful bands:
  - NIR for vegetation
  - Green/NIR relationships for water
  - SWIR bands for urban surfaces
- The model independently learned patterns closely related to **NDVI** and **NDWI**.

---

## Report

A detailed discussion of methodology, experiments, explainability results, and environmental insights can be found in:

`Report.pdf`

---

## Dataset

- EuroSAT Land Use / Land Cover Dataset
- Sentinel-2 RGB and 13-band multispectral imagery

---

## Authors

GeoSnap Challenge Submission
